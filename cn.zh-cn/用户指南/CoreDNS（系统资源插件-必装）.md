# CoreDNS（系统资源插件，必装）<a name="cce_01_0129"></a>

## 插件简介<a name="section25311744154917"></a>

CoreDNS插件是一款通过链式插件的方式为Kubernetes提供域名解析服务的DNS服务器。

CoreDNS是由CNCF孵化的开源软件，用于Cloud-Native环境下的DNS服务器和服务发现解决方案。CoreDNS实现了插件链式架构，能够按需组合插件，运行效率高、配置灵活。在kubernetes集群中使用CoreDNS能够自动发现集群内的服务，并为这些服务提供域名解析。同时，通过级联华为云的DNS服务器，还能够为集群内的工作负载提供外部域名的解析服务。目前CoreDNS已经成为社区kubernetes 1.11及以上版本集群推荐的DNS服务器解决方案。

**该插件为系统资源插件，kubernetes 1.11及以上版本的集群在创建时默认安装。**

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   当CoreDNS插件有升级或者BUG修复时，您不必升级集群或新建集群，仅需安装或升级CoreDNS插件即可。
>-   DNS详细使用方法请参见[Kubernetes集群内置DNS配置说明](Kubernetes集群内置DNS配置说明.md)或[通过kubectl配置kube-dns/CoreDNS高可用](通过kubectl配置kube-dns-CoreDNS高可用.md)。

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

    待插件安装完成后，单击“返回插件管理“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 为CoreDNS配置存根域<a name="section5202157467"></a>

集群管理员可以修改CoreDNS Corefile的ConfigMap以更改服务发现的工作方式。使用插件proxy可对CoreDNS的存根域进行配置。

若集群管理员有一个位于10.150.0.1的Consul域名解析服务器，并且所有Consul的域名都带有.consul.local的后缀。在CoreDNS的ConfigMap中添加如下信息即可将该域名服务器配置在CoreDNS中：

```
consul.local:5353 {
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

DNS策略可以在每个pod基础上进行设置，目前，Kubernetes支持**Default、ClusterFirst、ClusterFirstWithHostNet和None**四种DNS策略，具体请参见[https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/](https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/)。这些策略在pod-specific的**dnsPolicy**  字段中指定。

-   **“Default”**：如果dnsPolicy被设置为“Default”，则名称解析配置将从pod运行的节点继承。 自定义上游域名服务器和存根域不能够与这个策略一起使用。
-   **“ClusterFirst”：**如果dnsPolicy被设置为“ClusterFirst”，任何与配置的集群域后缀不匹配的DNS查询（例如，www.kubernetes.io）将转发到从该节点继承的上游名称服务器。集群管理员可能配置了额外的存根域和上游DNS服务器。
-   **“ClusterFirstWithHostNet”：**对于使用hostNetwork运行的Pod，您应该明确设置其DNS策略“ClusterFirstWithHostNet”。
-   **“None”：**它允许Pod忽略Kubernetes环境中的DNS设置。应使用dnsConfigPod规范中的字段提供所有DNS设置 。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   Kubernetes 1.10及以上版本，支持Default、ClusterFirst、ClusterFirstWithHostNet和None四种策略；低于Kubernetes 1.10版本，仅支持default、ClusterFirst和ClusterFirstWithHostNet三种。
>-   “Default”不是默认的DNS策略。如果dnsPolicy的Flag没有特别指明，则默认使用“**ClusterFirst**”。

**路由请求流程：**

未配置存根域：没有匹配上配置的集群域名后缀的任何请求，例如 “www.kubernetes.io”，将会被转发到继承自节点的上游域名服务器。

已配置存根域：如果配置了存根域和上游 DNS 服务器，DNS 查询将基于下面的流程对请求进行路由：

1.  查询首先被发送到 coredns 中的 DNS 缓存层。
2.  从缓存层，检查请求的后缀，并根据下面的情况转发到对应的 DNS 上：
    -   具有集群后缀的名字（例如“.cluster.local”）：请求被发送到 coredns。

    -   具有存根域后缀的名字（例如“.acme.local”）：请求被发送到配置的自定义 DNS 解析器（例如：监听在 1.2.3.4）。
    -   未能匹配上后缀的名字（例如“widget.com”）：请求被转发到上游 DNS。


**图 1**  路由请求流程<a name="fig7582181514118"></a>  
![](figures/路由请求流程.png "路由请求流程")

## 升级插件<a name="section19566181513486"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**coredns**下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级coredns插件时，会替换原先节点上的旧版本的coredns插件，安装最新版本的coredns插件以实现功能的快速升级。

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

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**coredns**下的“ 卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

## 版本记录<a name="section1945192816714"></a>

**表 3**  coredns版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="11.24%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="29.68%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="18.44%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="40.64%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row12566114195411"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p956611419541"><a name="p956611419541"></a><a name="p956611419541"></a><span id="ph5234641125416"><a name="ph5234641125416"></a><a name="ph5234641125416"></a>1.17.1</span></p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p122317499543"><a name="p122317499543"></a><a name="p122317499543"></a>混合集群 v1.17.*</p>
<p id="p1123119493546"><a name="p1123119493546"></a><a name="p1123119493546"></a>裸金属集群 v1.17.*</p>
<p id="p10231949155412"><a name="p10231949155412"></a><a name="p10231949155412"></a>鲲鹏集群 v1.17.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p2566141405412"><a name="p2566141405412"></a><a name="p2566141405412"></a><span id="ph55484125514"><a name="ph55484125514"></a><a name="ph55484125514"></a>2020/08/19</span></p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><p id="p1456681414548"><a name="p1456681414548"></a><a name="p1456681414548"></a><span id="ph2851112035514"><a name="ph2851112035514"></a><a name="ph2851112035514"></a>支持1.17集群</span></p>
</td>
</tr>
<tr id="row97875912317"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p19246621182"><a name="p19246621182"></a><a name="p19246621182"></a>1.15.3</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p20246102588"><a name="p20246102588"></a><a name="p20246102588"></a>混合集群 v1.15.*</p>
<p id="p2024642382"><a name="p2024642382"></a><a name="p2024642382"></a>裸金属集群 v1.15.*</p>
<p id="p324616215819"><a name="p324616215819"></a><a name="p324616215819"></a>鲲鹏集群 v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p132462210818"><a name="p132462210818"></a><a name="p132462210818"></a>2020/07/27</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><p id="p17922112020594"><a name="p17922112020594"></a><a name="p17922112020594"></a>同步社区修改，修复kube-apiserver down，coredns crash issue</p>
</td>
</tr>
<tr id="row187865919236"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p72461227810"><a name="p72461227810"></a><a name="p72461227810"></a>1.15.2</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p98181511911"><a name="p98181511911"></a><a name="p98181511911"></a>混合集群 v1.15.*</p>
<p id="p48186511919"><a name="p48186511919"></a><a name="p48186511919"></a>裸金属集群 v1.15.*</p>
<p id="p981855992"><a name="p981855992"></a><a name="p981855992"></a>鲲鹏集群 v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p132461929812"><a name="p132461929812"></a><a name="p132461929812"></a>2020/07/27</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><p id="p0923220195912"><a name="p0923220195912"></a><a name="p0923220195912"></a>同步社区修改，修复kube-apiserver down，coredns crash issue</p>
</td>
</tr>
<tr id="row14788592234"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p12247722082"><a name="p12247722082"></a><a name="p12247722082"></a>1.15.1</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p106871785917"><a name="p106871785917"></a><a name="p106871785917"></a>混合集群 v1.15.*</p>
<p id="p76871814916"><a name="p76871814916"></a><a name="p76871814916"></a>裸金属集群 v1.15.*</p>
<p id="p166877810911"><a name="p166877810911"></a><a name="p166877810911"></a>鲲鹏集群 v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p2024711211816"><a name="p2024711211816"></a><a name="p2024711211816"></a>2019/12/16</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><p id="p89251420175911"><a name="p89251420175911"></a><a name="p89251420175911"></a>支持鲲鹏集群</p>
</td>
</tr>
<tr id="row1878859102318"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p132471025814"><a name="p132471025814"></a><a name="p132471025814"></a>1.13.4</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p1124702488"><a name="p1124702488"></a><a name="p1124702488"></a>混合集群 v1.13.*</p>
<p id="p3247152183"><a name="p3247152183"></a><a name="p3247152183"></a>裸金属集群 v1.13.*</p>
<p id="p8247221289"><a name="p8247221289"></a><a name="p8247221289"></a>鲲鹏集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p162471620812"><a name="p162471620812"></a><a name="p162471620812"></a>2020/04/04</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><p id="p14925420185912"><a name="p14925420185912"></a><a name="p14925420185912"></a>支持新版本集群</p>
</td>
</tr>
<tr id="row15919281555"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p102471214818"><a name="p102471214818"></a><a name="p102471214818"></a>1.13.3</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p16509204113917"><a name="p16509204113917"></a><a name="p16509204113917"></a>混合集群 v1.13.*</p>
<p id="p1450916411392"><a name="p1450916411392"></a><a name="p1450916411392"></a>裸金属集群 v1.13.*</p>
<p id="p4509941597"><a name="p4509941597"></a><a name="p4509941597"></a>鲲鹏集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p124710211817"><a name="p124710211817"></a><a name="p124710211817"></a>2019/07/02</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><p id="p392652018595"><a name="p392652018595"></a><a name="p392652018595"></a>适配ARM集群</p>
</td>
</tr>
<tr id="row1878459102313"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p10247521982"><a name="p10247521982"></a><a name="p10247521982"></a>1.13.2</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p1593154515918"><a name="p1593154515918"></a><a name="p1593154515918"></a>混合集群 v1.13.*</p>
<p id="p193154516913"><a name="p193154516913"></a><a name="p193154516913"></a>裸金属集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p1624772982"><a name="p1624772982"></a><a name="p1624772982"></a>2019/09/26</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><p id="p1792732016596"><a name="p1792732016596"></a><a name="p1792732016596"></a>支持服务网段可配置</p>
</td>
</tr>
<tr id="row3799599239"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p0247628816"><a name="p0247628816"></a><a name="p0247628816"></a>1.2.7</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p73876541598"><a name="p73876541598"></a><a name="p73876541598"></a>混合集群 v1.11.*</p>
<p id="p038765414910"><a name="p038765414910"></a><a name="p038765414910"></a>裸金属集群 v1.11.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p19247162086"><a name="p19247162086"></a><a name="p19247162086"></a>2019/06/10</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><p id="p192782025920"><a name="p192782025920"></a><a name="p192782025920"></a>支持服务网段可配置</p>
</td>
</tr>
</tbody>
</table>

