# virtual kubelet<a name="cce_01_0135"></a>

-   [约束及限制](#section628693291119)
-   [安装插件](#section2237175619515)
-   [配置插件](#section162391856185111)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1624015695110)
-   [版本记录](#section144262219109)

Virtual Kubelet是基于社区Virtual Kubelet开源项目开发的插件，作为一种虚拟的kubelet用来连接Kubernetes集群和其他平台的API。Virtual Kubelet的主要场景是将Kubernetes API扩展到无服务器的容器平台（如CCI、Fargate和Hyper.sh等）。

基于该插件，支持华为云用户在短时高负载场景下，将部署在云容器引擎CCE上的无状态负载（Deployment）、有状态负载（StatefulSet）、普通任务（Job）三种资源类型的容器实例（Pod），弹性创建到[云容器实例CCI](https://support.huaweicloud.com/cci/index.html)服务上，以减少集群扩容带来的消耗。详情请参见[华为云CCE弹性到CCI](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_0134.html)。

开源社区地址：[https://github.com/virtual-kubelet/virtual-kubelet](https://github.com/virtual-kubelet/virtual-kubelet)

Virtual Kubelet插件具体如下功能：

-   **支持容器实例实现秒级弹性伸缩：**在集群资源不足时，无需新增节点，virtual kubelet插件将自动为您在[云容器实例CCI](https://support.huaweicloud.com/cci/index.html)侧创建容器实例，减少运维成本。
-   无缝对接华为云[容器镜像服务SWR](https://support.huaweicloud.com/swr/index.html)，支持使用公用镜像和私有镜像。
-   支持CCI容器实例的事件同步、监控、日志、exec、查看状态等操作。
-   支持查看虚拟弹性节点的节点容量信息。
-   支持CCE和CCI两侧实例的service网络互通。

## 约束及限制<a name="section628693291119"></a>

-   仅支持VPC网络模式的混合集群，仅限于v1.11及以上版本的集群使用。
-   使用时需同时配置Request和Limit，且CPU-Memory比例须符合CCI要求，pod才可以部署到CCI侧。
-   pod弹到CCI侧后，暂不支持改变负载的“数据存储 \> 本地磁盘“的Configmap/Secret键值。
-   调度到CCI的实例的存储类型只支持ConfigMap、Secret两种Volume类型。
-   暂不支持HostNetwork网络模式的容器实例（Pod）弹性到CCI。
-   实例的规格必须满足云容器实例CCI的[容器规范](https://support.huaweicloud.com/productdesc-cci/cci_03_0007.html)。
-   使用插件前需要用户在[CCI界面](https://console.huaweicloud.com/cci/?locale=zh-cn#/dashboard)对CCI服务进行授信。

## 安装插件<a name="section2237175619515"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击virtual kubelet插件下的“安装插件“。
2.  在“基本信息“步骤中，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  在“规格配置“步骤中，勾选“跨服务互通“后的选择框，可实现CCE集群中的Pod与CCI集群中的Pod通过Kubernetes Service互通。

    **图 1**  勾选“跨服务互通“<a name="fig14909180185319"></a>  
    ![](figures/勾选跨服务互通.png "勾选跨服务互通")

4.  单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 配置插件<a name="section162391856185111"></a>

您成功安装virtual kubelet插件后，仍需完成如下步骤才能使用。

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“工作负载“。
2.  在创建无状态工作负载或Job时，在“工作负载基本信息“步骤中，勾选“CCI弹性承载“。

    **图 2**  勾选“CCI弹性承载“<a name="fig610418228234"></a>  
    ![](figures/勾选CCI弹性承载.png "勾选CCI弹性承载")

3.  单击“下一步“继续创建相关资源。

## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“virtual kubelet“下的“升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“virtual kubelet“插件时，会替换原先节点上的旧版本的“virtual kubelet“插件，安装最新版本的“virtual kubelet“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  参考[安装插件](#section2237175619515)中参数说明配置参数后，单击“升级“即可升级“virtual kubelet“插件。

## 卸载插件<a name="section1624015695110"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击virtual kubelet下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  virtual kubelet版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="15.409999999999998%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="32.62%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="16.11%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="35.86%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row20708121810568"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p770801811563"><a name="p770801811563"></a><a name="p770801811563"></a>1.0.5</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p207081418145613"><a name="p207081418145613"></a><a name="p207081418145613"></a>混合集群 v1.13.*|v1.15.*|v1.17.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p157081318115619"><a name="p157081318115619"></a><a name="p157081318115619"></a>2021/03/01</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><p id="p7708141815616"><a name="p7708141815616"></a><a name="p7708141815616"></a>支持v1.17版本集群</p>
</td>
</tr>
<tr id="row152684214528"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p7429205131318"><a name="p7429205131318"></a><a name="p7429205131318"></a>1.0.3</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p3429125131312"><a name="p3429125131312"></a><a name="p3429125131312"></a>混合集群 v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p242920512138"><a name="p242920512138"></a><a name="p242920512138"></a>2020/11/17</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul1942912513134"></a><a name="ul1942912513134"></a><ul id="ul1942912513134"><li>使用Label而非Annotation标识弹性到CCI的负载</li><li>CCI资源池售罄时自动屏蔽Pod弹性到CCI</li></ul>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p134290517137"><a name="p134290517137"></a><a name="p134290517137"></a>1.0.2</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p138774791412"><a name="p138774791412"></a><a name="p138774791412"></a>混合集群 v1.13.*|v1.15.*</p>
<p id="p1429155191313"><a name="p1429155191313"></a><a name="p1429155191313"></a></p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p1342910514139"><a name="p1342910514139"></a><a name="p1342910514139"></a>2020/10/13</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul442918514135"></a><a name="ul442918514135"></a><ul id="ul442918514135"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row3409132191217"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p242965114135"><a name="p242965114135"></a><a name="p242965114135"></a>1.0.1</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p124291651161318"><a name="p124291651161318"></a><a name="p124291651161318"></a>混合集群 v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p2429451121312"><a name="p2429451121312"></a><a name="p2429451121312"></a>2020/08/11</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul34291751111317"></a><a name="ul34291751111317"></a><ul id="ul34291751111317"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row541043210125"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p242915191316"><a name="p242915191316"></a><a name="p242915191316"></a>0.4.5</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p1542945117136"><a name="p1542945117136"></a><a name="p1542945117136"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p1042918514135"><a name="p1042918514135"></a><a name="p1042918514135"></a>2020/03/02</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul1942945151310"></a><a name="ul1942945151310"></a><ul id="ul1942945151310"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row1699853821216"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p0429155113137"><a name="p0429155113137"></a><a name="p0429155113137"></a>0.4.4</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p14781111155"><a name="p14781111155"></a><a name="p14781111155"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p6429115112135"><a name="p6429115112135"></a><a name="p6429115112135"></a>2020/02/23</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul1742920515138"></a><a name="ul1742920515138"></a><ul id="ul1742920515138"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row169985383125"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p642919512136"><a name="p642919512136"></a><a name="p642919512136"></a>0.4.3</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p11429165101314"><a name="p11429165101314"></a><a name="p11429165101314"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p14429185131315"><a name="p14429185131315"></a><a name="p14429185131315"></a>2020/02/22</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul1742995121320"></a><a name="ul1742995121320"></a><ul id="ul1742995121320"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row3998153811121"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p1842955113138"><a name="p1842955113138"></a><a name="p1842955113138"></a>0.4.2</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p94291951191317"><a name="p94291951191317"></a><a name="p94291951191317"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p1442915119137"><a name="p1442915119137"></a><a name="p1442915119137"></a>2020/02/21</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul742925117132"></a><a name="ul742925117132"></a><ul id="ul742925117132"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row1799812389124"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p443045121312"><a name="p443045121312"></a><a name="p443045121312"></a>0.4.1</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p12430551151318"><a name="p12430551151318"></a><a name="p12430551151318"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p6430151171312"><a name="p6430151171312"></a><a name="p6430151171312"></a>2020/02/21</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul143010516137"></a><a name="ul143010516137"></a><ul id="ul143010516137"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row8148134517127"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p1243025141318"><a name="p1243025141318"></a><a name="p1243025141318"></a>0.4.0</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p6430105113136"><a name="p6430105113136"></a><a name="p6430105113136"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p243010519134"><a name="p243010519134"></a><a name="p243010519134"></a>2020/02/20</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul243025119134"></a><a name="ul243025119134"></a><ul id="ul243025119134"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row51481145201210"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p1243085191314"><a name="p1243085191314"></a><a name="p1243085191314"></a>0.3.8</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p443045151319"><a name="p443045151319"></a><a name="p443045151319"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p84302051101317"><a name="p84302051101317"></a><a name="p84302051101317"></a>2020/02/19</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul74301751151311"></a><a name="ul74301751151311"></a><ul id="ul74301751151311"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row914813453122"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p1525191012149"><a name="p1525191012149"></a><a name="p1525191012149"></a>0.3.6</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p132581011410"><a name="p132581011410"></a><a name="p132581011410"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p17250109146"><a name="p17250109146"></a><a name="p17250109146"></a>2020/02/18</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul82519106147"></a><a name="ul82519106147"></a><ul id="ul82519106147"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row10148164511216"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p626201021412"><a name="p626201021412"></a><a name="p626201021412"></a>0.3.5</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p1526161001414"><a name="p1526161001414"></a><a name="p1526161001414"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p22681021414"><a name="p22681021414"></a><a name="p22681021414"></a>2020/02/15</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul726181041416"></a><a name="ul726181041416"></a><ul id="ul726181041416"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row11487450124"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p72621081417"><a name="p72621081417"></a><a name="p72621081417"></a>0.3.4</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p112631013145"><a name="p112631013145"></a><a name="p112631013145"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p126101061414"><a name="p126101061414"></a><a name="p126101061414"></a>2020/02/10</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul1526101012147"></a><a name="ul1526101012147"></a><ul id="ul1526101012147"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row111491745121216"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p122616103147"><a name="p122616103147"></a><a name="p122616103147"></a>0.3.3</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p1626210101417"><a name="p1626210101417"></a><a name="p1626210101417"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p192611106145"><a name="p192611106145"></a><a name="p192611106145"></a>2020/02/07</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul12610103146"></a><a name="ul12610103146"></a><ul id="ul12610103146"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row51491045111219"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p14266101146"><a name="p14266101146"></a><a name="p14266101146"></a>0.3.2</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p726171015148"><a name="p726171015148"></a><a name="p726171015148"></a>混合集群 v1.11.*|v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p4264103143"><a name="p4264103143"></a><a name="p4264103143"></a>2020/02/05</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul12671019144"></a><a name="ul12671019144"></a><ul id="ul12671019144"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
<tr id="row20149114541213"><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.2.5.1.1 "><p id="p1626131041416"><a name="p1626131041416"></a><a name="p1626131041416"></a>0.2.9</p>
</td>
<td class="cellrowborder" valign="top" width="32.62%" headers="mcps1.2.5.1.2 "><p id="p162614106144"><a name="p162614106144"></a><a name="p162614106144"></a>混合集群 v1.11.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.11%" headers="mcps1.2.5.1.3 "><p id="p18261810181412"><a name="p18261810181412"></a><a name="p18261810181412"></a>2019/10/30</p>
</td>
<td class="cellrowborder" valign="top" width="35.86%" headers="mcps1.2.5.1.4 "><a name="ul726410131413"></a><a name="ul726410131413"></a><ul id="ul726410131413"><li>支持跨服务互通</li><li>卸载时资源清理回收</li></ul>
</td>
</tr>
</tbody>
</table>

