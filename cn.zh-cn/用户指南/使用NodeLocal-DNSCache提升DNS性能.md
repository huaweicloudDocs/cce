# 使用NodeLocal DNSCache提升DNS性能<a name="cce_10_0362"></a>

## 应用现状<a name="section1374833194817"></a>

集群在做DNS解析时，如果请求量大，那CoreDNS将承受压力，会有如下影响。

-   查询变慢，影响业务性能。
-   为保证性能，CoreDNS需要更高规格的配置。

## 解决方案<a name="section184982553516"></a>

NodeLocal DNSCache 通过在集群节点上运行 DNS缓存代理来提高集群 DNS 性能。

启用NodeLocal DNSCache之后，DNS查询所遵循的路径如下图所示。

**图 1**  NodeLocal DNSCache查询路径<a name="fig36421622164815"></a>  
![](figures/NodeLocal-DNSCache查询路径.png "NodeLocal-DNSCache查询路径")

## 插件安装<a name="section0938141194810"></a>

CCE提供了[node-local-dns](node-local-dns.md)插件，可以方便的安装NodeLocal DNSCache。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   node-local-dns插件仅支持1.19及以上版本集群。
>-   NodeLocal DNSCache不提供Hosts、Rewrite等插件能力，仅作为CoreDNS的透明缓存代理。如有需要，可在CoreDNS配置中修改。
>-   kube-system命名空间下的Pod不支持自动注入。
>-   CCI上不支持NodeLocal DNSCache。当负载动态弹性伸缩到CCI时，CCI上Pod会因为无法联通NodeLocal DNSCache导致域名解析超时，此时可进行注入豁免。

1.  （可选）修改CoreDNS配置，让CoreDNS优先采用UDP协议与上游DNS服务器通信。

    NodeLocal DNSCache采用TCP协议与CoreDNS进行通信，CoreDNS会根据请求来源使用的协议与上游DNS服务器进行通信。当使用了NodeLocal DNSCache时，访问上游DNS服务器时会使用TCP协议，而云上DNS服务器对TCP协议支持有限，如果您使用了NodeLocal DNSCache，您需要修改CoreDNS配置，让其总是优先采用UDP协议与上游DNS服务器进行通信，避免解析异常。

    执行如下命令修改。

    **kubectl edit configmap coredns -nkube-system**

    在forward插件中指定请求上游的协议为perfer\_udp，修改之后CoreDNS会优先使用UDP协议与上游通信。

    ```
    forward . /etc/resolv.conf { prefer_udp }
    ```

2.  登录CCE控制台，单击集群名称进入集群，在左侧导航栏中选择“插件管理“，在右侧找到**node-local-dns**，单击“安装“。
3.  在安装插件页面，选择插件规格，并配置相关参数。

    **enable\_dnsconfig\_admission**：是否自动注入DNSConfig至新建的Pod中。默认为**false**，设置为**true**表示支持自动注入，避免您手工配置Pod YAML进行注入。

4.  完成以上配置后，单击“安装“。

## 使用NodeLocal DNSCache<a name="section454110448388"></a>

有两种方式可以使用NodeLocal DNSCache：

-   自动注入：创建Pod时自动配置Pod的dnsConfig字段。（kube-system命名空间下的Pod不支持自动注入）
-   手动配置：手动配置Pod的dnsConfig字段，从而使用NodeLocal DNSCache。

**自动注入**

自动注入需要满足如下条件：

-   插件需要将**enable\_dnsconfig\_admission**参数配置为**true**
-   命名空间添加node-local-dns-injection=enabled标签

    **kubectl label namespace  _default _  node-local-dns-injection=enabled**

-   新建Pod不位于kube-system和kube-public命名空间
-   新建Pod没有被打上禁用DNS注入node-local-dns-injection=disabled标签
-   新建Pod的网络为hostNetwork且DNSPolicy为ClusterFirstWithHostNet，或Pod为非hostNetwork且DNSPolicy为ClusterFirst

开启自动注入后，创建的Pod会自动添加如下dnsConfig字段，nameservers中除了NodeLocal DNSCache的地址169.254.20.10外，还添加了CoreDNS的地址10.247.3.10，保障了业务DNS请求高可用。

```
  dnsConfig:
    nameservers:
      - 169.254.20.10
      - 10.247.3.10
    searches:
      - default.svc.cluster.local
      - svc.cluster.local
      - cluster.local
    options:
      - name: timeout
        value: ''
      - name: ndots
        value: '5'
      - name: single-request-reopen
```

**手动配置**

手动配置即自行给Pod加上dnsConfig配置。

创建一个Pod，将dnsconfig配置为169.254.20.10。

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - image: nginx:alpine
    name: container-0
  dnsConfig:
    nameservers:
    - 169.254.20.10
    searches:
    - default.svc.cluster.local
    - svc.cluster.local
    - cluster.local
    options:
    - name: ndots
      value: '2'
  imagePullSecrets:
  - name: default-secret
```

