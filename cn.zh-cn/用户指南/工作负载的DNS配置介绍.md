# 工作负载的DNS配置介绍<a name="cce_01_0136"></a>

Kubernetes集群内置DNS插件Kube-DNS/CoreDNS，为集群内的工作负载提供域名解析服务。业务在高并发调用场景下，如果使用到域名解析服务，可能会触及到Kube-DNS/CoreDNS的性能瓶颈，导致DNS请求概率失败，影响用户业务正常运行。在Kubernetes使用的过程中，发现有些场景下工作负载的域名解析存在冗余的DNS查询，使得高并发场景更容易触及DNS的性能瓶颈。根据业务使用场景，对工作负载的DNS配置进行优化，能够在一定程度上减少DNS请求概率失败的问题。

## Linux系统域名解析文件配置项的介绍<a name="section1399416215718"></a>

在Linux系统的节点或者容器里执行cat /etc/resolv.conf命令，能够查看到DNS配置，以Kubernetes集群的容器DNS配置为例：

```
nameserver 10.247.x.x
search default.svc.cluster.local svc.cluster.local cluster.local
options ndots:5
```

**配置项说明：**

-   nameserver：容器解析域名时查询的DNS服务器的IP地址列表。如果设置为10.247.x.x说明DNS对接到Kube-DNS/CoreDNS，如果是其他IP地址，则表示采用华为云DNS或者用户自建的DNS。
-   search：定义域名的搜索域列表，当访问的域名不能被DNS解析时，会把该域名与搜索域列表中的域依次进行组合，并重新向DNS发起请求，直到域名被正确解析或者尝试完搜索域列表为止。对于CCE集群来说，容器的搜索域列表配置3个域，当解析一个不存在的域名时，会产生8次DNS查询，因为对于每个域名需要查询两次，分别是IPV4和IPV6。
-   options：定义域名解析配置文件的其他选项，常见的有timeout、attempts和ndots等等。Kubernetes集群容器的域名解析文件设置optiions ndots:5，这个参数选项的含义是：当域名的“.”个数小于ndots的值，则会先把域名与search搜索域列表进行组合后进行DNS查询，如果均没有被正确解析，最后再以域名本身去进行DNS查询；当域名的“.”个数大于或者等于ndots的值，则会先对域名本身进行DNS查询，如果没有被正确解析，再把域名与search搜索域列表依次进行组合后进行DNS查询。如：查询www.huaweicloud.com域名时，由于该域名的“.”个数为2，小于ndots的值，所以DNS查询请求的顺序依次为：www.huaweicloud.com.default.svc.cluster.local，www.huaweicloud.com.svc.cluster.local，www.huaweicloud.com.cluster.local和www.huaweicloud.com，需要发起至少7次DNS查询请求才能解析出该域名的IP。可以看出，这种配置在访问外部域名时，存在大量冗余的DNS查询，存在优化点。

>![](public_sys-resources/icon-note.gif) **说明：**   
>完整的Linux域名解析文件配置项说明可以参考文档：http://man7.org/linux/man-pages/man5/resolv.conf.5.html  

## Kubernetes集群工作负载的DNS相关配置项介绍<a name="section156871640577"></a>

前面已经分析过，工作负载在某些场景下会出现冗余的DNS查询。Kubernetes为工作负载提供了与DNS相关的配置选项，通过对工作负载进行DNS配置，能够在某些场景下有效地减少冗余的DNS查询，提升业务并发量。目前工作负载配置中与DNS相关的字段有**dnsPolicy**和**dnsConfig**。

**dnsPolicy字段说明：**

dnsPolicy字段是工作负载设置的DNS策略，默认值为“ClusterFirst”。基于dnsPolicy策略生成的域名解析文件会与dnsConfig设置的DNS参数进行合并，合并规则将在“dnsConfig字段说明”中说明，dnsPolicy当前支持四种参数值：

-   ClusterFirst：工作负载对接Kube-DNS/CoreDNS（CCE集群的Kube-DNS/CoreDNS默认级联华为云DNS）。这种场景下，容器既能够解析service注册的集群内部域名，也能够解析发布到互联网上的外部域名。由于该配置下，域名解析文件设置了search搜索域列表和ndots: 5，因此当访问外部域名和集群内部长域名（如kubernetes.default.svc.cluster.local）时，大部分域名都会优先遍历search搜索域列表，导致至少有6次无效的DNS查询，只有访问集群内部短域名（如kubernetes）时，才不存在无效的DNS查询。
-   ClusterFirstWithHostNet：对于配置主机网络的工作负载，默认配置kubelet的“--resolv-conf”参数指向的域名解析文件（CCE集群在该配置下对接华为云DNS）。当dnsPolicy设置为“ClusterFirstWithHostNet”时，工作负载对接Kube-DNS/CoreDNS。该配置下，容器的域名解析文件与“ClusterFirst”一致，也存在无效的DNS查询。
-   Default：容器的域名解析文件使用kubelet的“--resolv-conf”参数指向的域名解析文件（CCE集群在该配置下对接华为云DNS），没有配置search搜索域列表和options。该配置只能解析注册到互联网上的外部域名，无法解析集群内部域名，且不存在无效的DNS查询。
-   None：Kubernetes v1.9（Beta in v1.10）中引入的新选项值。设置为None之后，必须设置dnsConfig，此时容器的域名解析文件将完全通过dnsConfig的配置来生成。

**dnsConfig字段说明：**

dnsConfig为工作负载设置DNS参数，设置的参数将合并到基于dnsPolicy策略生成的域名解析文件中。当dnsPolicy为“None”，工作负载的域名解析文件完全由dnsConfig指定；当dnsPolicy不为“None”时，会在基于dnsPolicy生成的域名解析文件的基础上，追加dnsConfig中配置的dns参数。

-   nameservers：DNS的IP地址列表。当工作负载的dnsPolicy设置为“None”时，列表必须至少包含一个IP地址，否则此属性是可选的。列出的DNS的IP列表将合并到基于dnsPolicy生成的域名解析文件的nameserver字段中，并删除重复的地址。
-   searches：域名查询时的DNS搜索域列表，此属性是可选的。指定后，提供的搜索域列表将合并到基于dnsPolicy生成的域名解析文件的search字段中，并删除重复的域名。Kubernetes最多允许6个搜索域。
-   options：DNS的配置选项，其中每个对象可以具有name 属性（必需）和value属性（可选）。该字段中的内容将合并到基于dnsPolicy生成的域名解析文件的options字段中，dnsConfig的options的某些选项如果与基于dnsPolicy生成的域名解析文件的选项冲突，则会被dnsConfig所覆盖。

