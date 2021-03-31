# CoreDNS（系统资源插件，必装）<a name="cce_01_0129"></a>

-   [插件简介](#section25311744154917)
-   [约束与限制](#section10849134521812)
-   [安装插件](#section776571919194)
-   [为CoreDNS配置存根域](#section5202157467)
-   [kubernetes中的域名解析逻辑](#section1860523212152)
-   [升级插件](#section19566181513486)
-   [卸载插件](#section7582615184814)

## 插件简介<a name="section25311744154917"></a>

CoreDNS插件是一款通过链式插件的方式为Kubernetes提供域名解析服务的DNS服务器。

CoreDNS是由CNCF孵化的开源软件，用于Cloud-Native环境下的DNS服务器和服务发现解决方案。CoreDNS实现了插件链式架构，能够按需组合插件，运行效率高、配置灵活。在kubernetes集群中使用CoreDNS能够自动发现集群内的服务，并为这些服务提供域名解析。同时，通过级联华为云的DNS服务器，还能够为集群内的工作负载提供外部域名的解析服务。

**该插件为系统资源插件，kubernetes 1.11及以上版本的集群在创建时默认安装。**

目前CoreDNS已经成为社区kubernetes 1.11及以上版本集群推荐的DNS服务器解决方案。

CoreDNS官网：[https://coredns.io/](https://coredns.io/)

开源社区地址：[https://github.com/coredns/coredns](https://github.com/coredns/coredns)

>![](public_sys-resources/icon-note.gif) **说明：** 
>DNS详细使用方法请参见[Kubernetes集群内置DNS配置说明](Kubernetes集群内置DNS配置说明.md)或[通过kubectl配置kube-dns/CoreDNS高可用](通过kubectl配置kube-dns-CoreDNS高可用.md)。

## 约束与限制<a name="section10849134521812"></a>

-   若需要升级CoreDNS插件，请确保集群中的节点数大于等于CoreDNS的实例数，且CoreDNS的所有实例都处于运行状态，否则将导致升级失败。
-   CoreDNS正常运行需要集群中至少有两个节点，在升级CoreDNS插件时，请确保CoreDNS的所有实例都处于运行状态。

## 安装插件<a name="section776571919194"></a>

本插件为系统默认安装，若因特殊情况卸载后，可参照如下步骤重新安装。

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件市场“页签下，单击**coredns**插件下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  在“规格配置“步骤中，可配置如下参数：

    **表 1**  cordns插件参数配置

    <a name="table924319911495"></a>
    <table><thead align="left"><tr id="row42442974913"><th class="cellrowborder" valign="top" width="24%" id="mcps1.2.3.1.1"><p id="p17244793496"><a name="p17244793496"></a><a name="p17244793496"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="76%" id="mcps1.2.3.1.2"><p id="p42441596495"><a name="p42441596495"></a><a name="p42441596495"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1137014404511"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p11370134095120"><a name="p11370134095120"></a><a name="p11370134095120"></a>插件规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p937064085113"><a name="p937064085113"></a><a name="p937064085113"></a>并发域名解析能力，请根据业务需求选择插件规格。</p>
    </td>
    </tr>
    <tr id="row83701240105118"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p3370040165116"><a name="p3370040165116"></a><a name="p3370040165116"></a>实例数</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p93701640145120"><a name="p93701640145120"></a><a name="p93701640145120"></a>选择上方插件规格后，显示插件中的实例数，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row4370840165119"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p937054045117"><a name="p937054045117"></a><a name="p937054045117"></a>容器</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1437014065110"><a name="p1437014065110"></a><a name="p1437014065110"></a>选择插件规格后，显示插件容器的CPU和内存配额，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row12370940175116"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p237044095117"><a name="p237044095117"></a><a name="p237044095117"></a>提示</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1493852310547"><a name="p1493852310547"></a><a name="p1493852310547"></a>关于本插件的注意事项，请仔细阅读。</p>
    </td>
    </tr>
    <tr id="row53701440125116"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p8370124035118"><a name="p8370124035118"></a><a name="p8370124035118"></a>存根域</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1837104015118"><a name="p1837104015118"></a><a name="p1837104015118"></a>单击<span class="uicontrol" id="uicontrol1158517458572"><a name="uicontrol1158517458572"></a><a name="uicontrol1158517458572"></a>“添加”</span>，您可对自定义的域名配置域名服务器，格式为一个键值对，键为DNS后缀域名，值为一个或一组DNS IP地址，如"acme.local -- 1.2.3.4,6.7.8.9"。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  完成以上配置后，单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 为CoreDNS配置存根域<a name="section5202157467"></a>

集群管理员可以修改CoreDNS Corefile的ConfigMap以更改服务发现的工作方式。使用插件proxy可对CoreDNS的存根域进行配置。

若集群管理员有一个位于10.150.0.1的Consul域名解析服务器，并且所有Consul的域名都带有.consul.local的后缀。

执行以下命令，在CoreDNS的ConfigMap中添加如下信息即可将该域名服务器配置在CoreDNS中：

**kubectl edit configmap coredns -n kube-system**

```
consul.local:5353 {
        errors
        cache 30
        proxy . 10.150.0.1
    }
```

**v1.15.11及之后的集群版本**，修改后最终的ConfigMap如下所示：

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
        forward . /etc/resolv.conf
        reload
    }

    consul.local:5353 {
        errors
        cache 30
        forward . 10.150.0.1
    }
kind: ConfigMap
metadata:
  name: coredns
  namespace: kube-system
```

**1.15.11之前的集群版本**，修改后最终的ConfigMap如下所示：

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

DNS策略可以在每个pod基础上进行设置，目前，Kubernetes支持**Default、ClusterFirst、ClusterFirstWithHostNet和None**四种DNS策略，具体请参见[https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/](https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/)。这些策略在pod-specific的**dnsPolicy**字段中指定。

-   **“Default”**：如果dnsPolicy被设置为“Default”，则名称解析配置将从pod运行的节点继承。 自定义上游域名服务器和存根域不能够与这个策略一起使用。
-   **“ClusterFirst”：**如果dnsPolicy被设置为“ClusterFirst”，任何与配置的集群域后缀不匹配的DNS查询（例如，www.kubernetes.io）将转发到从该节点继承的上游名称服务器。集群管理员可能配置了额外的存根域和上游DNS服务器。
-   **“ClusterFirstWithHostNet”：**对于使用hostNetwork运行的Pod，您应该明确设置其DNS策略“ClusterFirstWithHostNet”。
-   **“None”：**它允许Pod忽略Kubernetes环境中的DNS设置。应使用dnsConfigPod规范中的字段提供所有DNS设置 。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   Kubernetes 1.10及以上版本，支持Default、ClusterFirst、ClusterFirstWithHostNet和None四种策略；低于Kubernetes 1.10版本，仅支持default、ClusterFirst和ClusterFirstWithHostNet三种。
>-   “Default”不是默认的DNS策略。如果dnsPolicy的Flag没有特别指明，则默认使用“**ClusterFirst**”。

**路由请求流程：**

未配置存根域：没有匹配上配置的集群域名后缀的任何请求，例如 “www.kubernetes.io”，将会被转发到继承自节点的上游域名服务器。

已配置存根域：如果配置了存根域和上游DNS服务器，DNS查询将基于下面的流程对请求进行路由：

1.  查询首先被发送到coredns中的DNS缓存层。
2.  从缓存层，检查请求的后缀，并根据下面的情况转发到对应的DNS上：
    -   具有集群后缀的名字（例如“.cluster.local”）：请求被发送到coredns。

    -   具有存根域后缀的名字（例如“.acme.local”）：请求被发送到配置的自定义DNS解析器（例如：监听在 1.2.3.4）。
    -   未能匹配上后缀的名字（例如“widget.com”）：请求被转发到上游DNS。


**图 1**  路由请求流程<a name="fig7582181514118"></a>  
![](figures/路由请求流程.png "路由请求流程")

## 升级插件<a name="section19566181513486"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**coredns**下的“升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级coredns插件时，会替换原先节点上的旧版本的coredns插件，安装最新版本的coredns插件以实现功能的快速升级。如果升级出现异常，请卸载插件后重新安装和配置。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  参照[表2](#table1410658238)配置插件安装参数。配置完成后，单击“升级“即可升级coredns插件。

    **表 2**  安装插件说明

    <a name="table1410658238"></a>
    <table><thead align="left"><tr id="row10111254234"><th class="cellrowborder" valign="top" width="21.240000000000002%" id="mcps1.2.3.1.1"><p id="p1711053236"><a name="p1711053236"></a><a name="p1711053236"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="78.75999999999999%" id="mcps1.2.3.1.2"><p id="p10119522319"><a name="p10119522319"></a><a name="p10119522319"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1611957237"><td class="cellrowborder" valign="top" width="21.240000000000002%" headers="mcps1.2.3.1.1 "><p id="p16111158235"><a name="p16111158235"></a><a name="p16111158235"></a>插件规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.75999999999999%" headers="mcps1.2.3.1.2 "><p id="p71111552319"><a name="p71111552319"></a><a name="p71111552319"></a>并发域名解析能力。请根据业务需求选择插件规格。</p>
    </td>
    </tr>
    <tr id="row15111555233"><td class="cellrowborder" valign="top" width="21.240000000000002%" headers="mcps1.2.3.1.1 "><p id="p121114510237"><a name="p121114510237"></a><a name="p121114510237"></a>存根域</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.75999999999999%" headers="mcps1.2.3.1.2 "><p id="p2111453233"><a name="p2111453233"></a><a name="p2111453233"></a>用户可对自定义的域名配置域名服务器，格式为一个键值对，键为DNS后缀域名，值为一个或一组DNS IP地址，如"acme.local -- 1.2.3.4,6.7.8.9"。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 卸载插件<a name="section7582615184814"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**coredns**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

