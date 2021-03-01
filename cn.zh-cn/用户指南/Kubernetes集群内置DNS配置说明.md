# Kubernetes集群内置DNS配置说明<a name="cce_01_0133"></a>

-   [工作负载的DNS配置介绍](#section119521837203315)
-   [工作负载的DNS配置实践](#section12309936102318)

## 工作负载的DNS配置介绍<a name="section119521837203315"></a>

Kubernetes集群内置DNS插件Kube-DNS/CoreDNS，为集群内的工作负载提供域名解析服务。业务在高并发调用场景下，如果使用到域名解析服务，可能会触及到Kube-DNS/CoreDNS的性能瓶颈，导致DNS请求概率失败，影响用户业务正常运行。在Kubernetes使用的过程中，发现有些场景下工作负载的域名解析存在冗余的DNS查询，使得高并发场景更容易触及DNS的性能瓶颈。根据业务使用场景，对工作负载的DNS配置进行优化，能够在一定程度上减少DNS请求概率失败的问题。

更多DNS相关信息请参见[CoreDNS（系统资源插件，必装）](CoreDNS（系统资源插件-必装）.md)或[通过kubectl配置kube-dns/CoreDNS高可用](通过kubectl配置kube-dns-CoreDNS高可用.md)。

**Linux系统域名解析文件配置项的介绍**

在Linux系统的节点或者容器里执行cat /etc/resolv.conf命令，能够查看到DNS配置，以Kubernetes集群的容器DNS配置为例：

```
nameserver 10.247.x.x
search default.svc.cluster.local svc.cluster.local cluster.local
options ndots:5
```

**配置项说明：**

-   nameserver：容器解析域名时查询的DNS服务器的IP地址列表。如果设置为10.247.x.x说明DNS对接到Kube-DNS/CoreDNS，如果是其他IP地址，则表示采用华为云DNS或者用户自建的DNS。
-   search：定义域名的搜索域列表，当访问的域名不能被DNS解析时，会把该域名与搜索域列表中的域依次进行组合，并重新向DNS发起请求，直到域名被正确解析或者尝试完搜索域列表为止。对于CCE集群来说，容器的搜索域列表配置3个域，当解析一个不存在的域名时，会产生8次DNS查询，因为对于每个域名需要查询两次，分别是IPv4和IPv6。
-   options：定义域名解析配置文件的其他选项，常见的有timeout、attempts和ndots等等。Kubernetes集群容器的域名解析文件设置为options ndots:5，该参数的含义是当域名的“.”个数小于ndots的值，会先把域名与search搜索域列表进行组合后进行DNS查询，如果均没有被正确解析，再以域名本身去进行DNS查询。当域名的“.”个数大于或者等于ndots的值，会先对域名本身进行DNS查询，如果没有被正确解析，再把域名与search搜索域列表依次进行组合后进行DNS查询。如查询www.huaweicloud.com域名时，由于该域名的“.”个数为2，小于ndots的值，所以DNS查询请求的顺序依次为：www.huaweicloud.com.default.svc.cluster.local、www.huaweicloud.com.svc.cluster.local、 www.huaweicloud.com.cluster.local和www.huaweicloud.com，需要发起至少7次DNS查询请求才能解析出该域名的IP。可以看出，这种配置在访问外部域名时，存在大量冗余的DNS查询，存在优化点。

>![](public_sys-resources/icon-note.gif) **说明：** 
>完整的Linux域名解析文件配置项说明可以参考文档：[http://man7.org/linux/man-pages/man5/resolv.conf.5.html](http://man7.org/linux/man-pages/man5/resolv.conf.5.html)。

-   **Kubernetes集群应用的DNS相关配置项介绍**

    前面已经分析过，应用在某些场景下会出现冗余的DNS查询。Kubernetes为应用提供了与DNS相关的配置选项，通过对应用进行DNS配置，能够在某些场景下有效地减少冗余的DNS查询，提升业务并发量。目前应用配置中与DNS相关的字段有**dnsPolicy**和**dnsConfig**。

    **dnsPolicy字段说明：**

    dnsPolicy字段是应用设置的DNS策略，默认值为“ClusterFirst”。基于dnsPolicy策略生成的域名解析文件会与dnsConfig设置的DNS参数进行合并，合并规则将在“dnsConfig字段说明”中说明，dnsPolicy当前支持四种参数值：

    -   ClusterFirst：应用对接Kube-DNS/CoreDNS（CCE集群的Kube-DNS/CoreDNS默认级联华为云DNS）。这种场景下，容器既能够解析service注册的集群内部域名，也能够解析发布到互联网上的外部域名。由于该配置下，域名解析文件设置了search搜索域列表和ndots: 5，因此当访问外部域名和集群内部长域名（如kubernetes.default.svc.cluster.local）时，大部分域名都会优先遍历search搜索域列表，导致至少有6次无效的DNS查询，只有访问集群内部短域名（如kubernetes）时，才不存在无效的DNS查询。
    -   ClusterFirstWithHostNet：对于配置主机网络的应用，默认配置kubelet的“--resolv-conf”参数指向的域名解析文件（CCE集群在该配置下对接华为云DNS）。当dnsPolicy设置为“ClusterFirstWithHostNet”时，应用对接Kube-DNS/CoreDNS。该配置下，容器的域名解析文件与“ClusterFirst”一致，也存在无效的DNS查询。
    -   Default：容器的域名解析文件使用kubelet的“--resolv-conf”参数指向的域名解析文件（CCE集群在该配置下对接华为云DNS），没有配置search搜索域列表和options。该配置只能解析注册到互联网上的外部域名，无法解析集群内部域名，且不存在无效的DNS查询。
    -   None：Kubernetes v1.9（Beta in v1.10）中引入的新选项值。设置为None之后，必须设置dnsConfig，此时容器的域名解析文件将完全通过dnsConfig的配置来生成。

    **dnsConfig字段说明：**

    dnsConfig为应用设置DNS参数，设置的参数将合并到基于dnsPolicy策略生成的域名解析文件中。当dnsPolicy为“None”，应用的域名解析文件完全由dnsConfig指定；当dnsPolicy不为“None”时，会在基于dnsPolicy生成的域名解析文件的基础上，追加dnsConfig中配置的dns参数。

    -   nameservers：DNS的IP地址列表。当应用的dnsPolicy设置为“None”时，列表必须至少包含一个IP地址，否则此属性是可选的。列出的DNS的IP列表将合并到基于dnsPolicy生成的域名解析文件的nameserver字段中，并删除重复的地址。
    -   searches：域名查询时的DNS搜索域列表，此属性是可选的。指定后，提供的搜索域列表将合并到基于dnsPolicy生成的域名解析文件的search字段中，并删除重复的域名。Kubernetes最多允许6个搜索域。
    -   options：DNS的配置选项，其中每个对象可以具有name属性（必需）和value属性（可选）。该字段中的内容将合并到基于dnsPolicy生成的域名解析文件的options字段中，dnsConfig的options的某些选项如果与基于dnsPolicy生成的域名解析文件的选项冲突，则会被dnsConfig所覆盖。


## 工作负载的DNS配置实践<a name="section12309936102318"></a>

前面介绍了Linux系统域名解析文件以及Kubernetes为应用提供的DNS相关配置项，下面将举例介绍应用如何进行DNS配置。

-   **场景1 对接kubernetes内置的Kube-DNS/CoreDNS**

    **场景说明：**

    这种方式适用于应用中的域名解析只涉及集群内部域名，或者集群内部域名+外部域名两种方式，应用默认采用这种配置。

    **示例：**

    ```
    apiVersion: v1
    kind: Pod
    metadata:
      namespace: default
      name: dns-example
    spec:
      containers:
      - name: test
        image: nginx
      dnsPolicy: ClusterFirst
    ```

    该配置下容器的域名解析文件将如下所示：

    ```
    nameserver 10.247.3.10
    search default.svc.cluster.local svc.cluster.local cluster.local
    options ndots:5
    ```

-   **场景2 直接对接华为云DNS**

    **场景说明：**

    这种方式适用于应用只访问注册到互联网的外部域名，该场景不能解析集群内部域名。

    **示例：**

    ```
    apiVersion: v1
    kind: Pod
    metadata:
      namespace: default
      name: dns-example
    spec:
      containers:
      - name: test
        image: nginx
      dnsPolicy: Default //使用kubelet的“--resolv-conf”参数指向的域名解析文件（CCE集群在该配置下对接华为云DNS）
    ```

    该配置下容器的域名解析文件将如下所示：

    ```
    nameserver 10.125.x.x
    ```

-   **场景3 主机网络模式的应用对接Kube-DNS/CoreDNS**

    **场景说明：**

    对于配置主机网络模式的应用，默认对接华为云DNS，如果应用需要对接Kube-DNS/CoreDNS，需将dnsPolicy设置为“ClusterFirstWithHostNet”。

    **示例：**

    ```
    apiVersion: extensions/v1beta1
    kind: Deployment
    metadata:
      name: nginx
    spec:
      template:
        metadata:
          labels:
            app: nginx
        spec:
          hostNetwork: true
          dnsPolicy: ClusterFirstWithHostNet
          containers:
          - name: nginx
            image: nginx:1.7.9
            ports:
            - containerPort: 80
    ```

    该配置下容器的域名解析文件将如下所示：

    ```
    nameserver 10.247.3.10
    search default.svc.cluster.local svc.cluster.local cluster.local
    options ndots:5
    ```

-   **场景4 自定义应用的域名配置**

    **场景说明：**

    用户可以完全自定义配置应用的域名解析文件，这种方式非常灵活，dnsPolicy和dnsConfig配合使用，几乎能够满足所有使用场景，如对接用户自建DNS的场景、串联多个DNS的场景以及优化DNS配置选项的场景等等。

    **示例1：对接用户自建DNS**

    该配置下，dnsPolicy为“None”，应用的域名解析文件完全根据dnsConfig配置生成。

    ```
    apiVersion: v1
    kind: Pod
    metadata:
      namespace: default
      name: dns-example
    spec:
      containers:
      - name: test
        image: nginx
      dnsPolicy: "None"
      dnsConfig:
        nameservers:
        - 10.2.3.4 //用户自建DNS的IP地址
        searches:
        - ns1.svc.cluster.local
        - my.dns.search.suffix
        options:
        - name: ndots
          value: "2"
        - name: timeout
          value: "3"
    ```

    该配置下容器的域名解析文件将如下所示：

    ```
    nameserver 10.2.3.4
    search ns1.svc.cluster.local my.dns.search.suffix
    options timeout:3 ndots:2
    ```

    **示例2：修改域名解析文件的ndots选项，减少无效的DNS查询**

    该配置下，dnsPolicy不为“None”，会在基于dnsPolicy生成的域名解析文件的基础上，追加dnsConfig中配置的dns参数。

    ```
    apiVersion: v1
    kind: Pod
    metadata:
      namespace: default
      name: dns-example
    spec:
      containers:
      - name: test
        image: nginx
      dnsPolicy: "ClusterFirst"
      dnsConfig:
        options:
        - name: ndots
          value: "2" //该配置会将基于ClusterFirst策略生成的域名解析文件的ndots:5参数改写为ndots:2
    ```

    该配置下容器的域名解析文件将如下所示：

    ```
    nameserver 10.247.3.10
    search default.svc.cluster.local svc.cluster.local cluster.local
    options ndots:2
    ```


