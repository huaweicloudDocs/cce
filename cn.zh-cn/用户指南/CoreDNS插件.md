# CoreDNS插件<a name="cce_01_0129"></a>

CoreDNS插件是一款通过链式插件的方式给Kubernetes提供域名解析服务的DNS服务器。（仅在kubernetes 1.11及以上版本的集群支持）

## 插件简介<a name="section25311744154917"></a>

CoreDNS是一款由CNCF孵化的开源软件，用于Cloud-Native环境下的DNS服务器和服务发现解决方案。CoreDNS实现了插件链式架构，能够按需组合插件，运行效率高、配置灵活。在kubernetes集群中使用CoreDNS能够自动发现集群内的服务，并为这些服务提供域名解析。同时，通过级联华为云的DNS服务器，还能够为集群内的工作负载提供外部域名的解析服务。目前CoreDNS已经成为社区kubernetes 1.11及以上版本集群推荐的DNS服务器解决方案。

## 使用场景<a name="section202191122814"></a>

在CCE中新建的kubernetes 1.11集群默认会安装CoreDNS插件，当插件有升级或者BUG修复时，用户无需升级集群或新建集群来升级，仅需安装或升级CoreDNS插件。

## 为CoreDNS配置存根域<a name="section5202157467"></a>

集群管理员可以修改CoreDNS Corefile的ConfigMap以更改服务发现的工作方式。使用插件proxy可对CoreDNS的存根域进行配置。

若集群管理员有一个位于10.150.0.1的Consul域名解析服务器，并且所有Consul的域名都带有.consul.local的后缀。在CoreDNS的ConfigMap中添加如下信息即可将该域名服务器配置在CoreDNS中：

```
consul.local:53 {
        errors
        cache 30
        proxy . 10.150.0.1
    }
```

修改后最终的ConfigMap如下所示：

```
apiVersion: v1
data:
  Corefile: |-
    .:5353 {
        cache 30
        errors
        health
        kubernetes cluster.local in-addr.arpa ip6.arpa {
          pods insecure
          upstream /etc/resolv.conf
          fallthrough in-addr.arpa ip6.arpa
        }
        loadbalance round_robin
        prometheus 0.0.0.0:9153
        proxy . /etc/resolv.conf
        reload
    }

    consul.local:5353 {
        errors
        cache 30
        proxy . 10.150.0.1
    }
kind: ConfigMap
metadata:
  name: coredns
  namespace: kube-system
```

## kubernetes中的域名解析逻辑<a name="section1860523212152"></a>

可以为每个 Pod 设置 DNS 策略。当前 Kubernetes 支持两种 Pod 特定的 DNS 策略：“Default” 和 “ClusterFirst”，可以通过 dnsPolicy 标志来指定这些策略。

>![](public_sys-resources/icon-note.gif) **说明：**   
>“Default” 不是默认的 DNS 策略。如果没有显式地指定  _dnsPolicy_，将会使用“ClusterFirst”。  

**“Default”DNS 策略**

如果 dnsPolicy 被设置为“Default”，则名字解析配置会继承自 Pod 运行所在的节点。 自定义上游域名服务器和存根域不能够与这个策略一起使用。

**“ClusterFirst”DNS 策略**

如果 dnsPolicy 被设置为“ClusterFirst”，处理名字解析有所不同，依赖于是否配置了存根域和上游 DNS 服务器。

**未进行自定义配置：**没有匹配上配置的集群域名后缀的任何请求，例如 “www.kubernetes.io”，将会被转发到继承自节点的上游域名服务器。

**进行自定义配置：**如果配置了存根域和上游 DNS 服务器，DNS 查询将基于下面的流程对请求进行路由：

1.  查询首先被发送到 kube-dns 中的 DNS 缓存层。
2.  从缓存层，检查请求的后缀，并根据下面的情况转发到对应的 DNS 上：
    -   具有集群后缀的名字（例如“.cluster.local”）：请求被发送到 kube-dns。

    -   具有存根域后缀的名字（例如“.acme.local”）：请求被发送到配置的自定义 DNS 解析器（例如：监听在 1.2.3.4）。
    -   未能匹配上后缀的名字（例如“widget.com”）：请求被转发到上游 DNS（例如：Google 公共 DNS 服务器，8.8.8.8 和 8.8.4.4）。


**图 1**  路由请求流程<a name="fig7582181514118"></a>  
![](figures/路由请求流程.png "路由请求流程")

## 安装插件<a name="section776571919194"></a>

在CCE中新建的kubernetes 1.11版本集群中默认会安装CoreDNS插件，CoreDNS插件仅在kubernetes 1.11及以上版本的集群支持安装。

## 升级插件<a name="section19566181513486"></a>

1.  在CCE控制台中，单击左侧导航栏的“资源管理 \> 插件管理“，在“插件实例“页签中，选择对应的集群，单击**coredns**下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作；  
    >-   若升级按钮可点击，则点击升级按钮即可升级coredns插件。  
    >-   升级coredns插件时，会替换原先节点上的旧版本的coredns插件，安装最新版本的coredns插件以实现功能的快速升级。  

2.  在弹出的窗口中，单击“确认“，可升级该插件。

## 卸载插件<a name="section7582615184814"></a>

1.  在CCE控制台中，单击左侧导航栏的“资源管理 \> 插件管理“，在“插件实例“页签中，选择对应的集群，单击**coredns**下的“ 卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

