# huawei-npu<a name="cce_01_0239"></a>

-   [插件简介](#section173631312185614)
-   [约束与限制](#section11172124718374)
-   [安装插件](#section189463341114)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1395073191112)
-   [版本记录](#section144262219109)

## 插件简介<a name="section173631312185614"></a>

huawei-npu是支持容器里使用huawei NPU设备的管理插件。

## 约束与限制<a name="section11172124718374"></a>

此插件支持[混合集群](购买混合集群.md)和[鲲鹏集群](购买鲲鹏集群.md)，集群版本需在1.13以上版本。

## 安装插件<a name="section189463341114"></a>

安装本插件后，可在“资源管理 \> 集群管理“中通过购买集群选用“AI加速型“节点，实现快速高效地处理推理和图像识别等工作。具体请参见[购买混合集群](购买混合集群.md)-[AI加速型](购买混合集群.md#li2017145914913)。

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**huawei-npu**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  该插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“huawei-npu“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“huawei-npu“插件时，会替换原先节点上的旧版本的“huawei-npu“插件，安装最新版本的“huawei-npu“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  单击“升级“即可升级“huawei-npu“插件。

## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**huawei-npu**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  huawei-npu版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="15.6%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="26.490000000000002%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="17.91%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row152684214528"><td class="cellrowborder" valign="top" width="15.6%" headers="mcps1.2.5.1.1 "><p id="p994205742120"><a name="p994205742120"></a><a name="p994205742120"></a>1.0.6</p>
</td>
<td class="cellrowborder" valign="top" width="26.490000000000002%" headers="mcps1.2.5.1.2 "><p id="p8942357182115"><a name="p8942357182115"></a><a name="p8942357182115"></a>混合集群 v1.(13|15|17).*</p>
<p id="p179427575218"><a name="p179427575218"></a><a name="p179427575218"></a>鲲鹏集群 v1.(13|15|17).*</p>
</td>
<td class="cellrowborder" valign="top" width="17.91%" headers="mcps1.2.5.1.3 "><p id="p1394215718215"><a name="p1394215718215"></a><a name="p1394215718215"></a>2020/10/27</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p7938191692314"><a name="p7938191692314"></a><a name="p7938191692314"></a>支持昇腾C75驱动</p>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="15.6%" headers="mcps1.2.5.1.1 "><p id="p19943145752110"><a name="p19943145752110"></a><a name="p19943145752110"></a>1.0.5</p>
</td>
<td class="cellrowborder" valign="top" width="26.490000000000002%" headers="mcps1.2.5.1.2 "><p id="p7943657162112"><a name="p7943657162112"></a><a name="p7943657162112"></a>混合集群 v1.(13|15|17).*</p>
<p id="p1194318572215"><a name="p1194318572215"></a><a name="p1194318572215"></a>鲲鹏集群 v1.(13|15|17).*</p>
</td>
<td class="cellrowborder" valign="top" width="17.91%" headers="mcps1.2.5.1.3 "><p id="p99431657112111"><a name="p99431657112111"></a><a name="p99431657112111"></a>2020/09/12</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p14952181642319"><a name="p14952181642319"></a><a name="p14952181642319"></a>支持容器里使用huawei NPU设备的管理插件</p>
</td>
</tr>
<tr id="row17524111141813"><td class="cellrowborder" valign="top" width="15.6%" headers="mcps1.2.5.1.1 "><p id="p294315752114"><a name="p294315752114"></a><a name="p294315752114"></a>1.0.3</p>
</td>
<td class="cellrowborder" valign="top" width="26.490000000000002%" headers="mcps1.2.5.1.2 "><p id="p16943175742113"><a name="p16943175742113"></a><a name="p16943175742113"></a>混合集群 v1.(13|15|17).*</p>
<p id="p1094345718213"><a name="p1094345718213"></a><a name="p1094345718213"></a>鲲鹏集群 v1.(13|15|17).*</p>
</td>
<td class="cellrowborder" valign="top" width="17.91%" headers="mcps1.2.5.1.3 "><p id="p12943125711218"><a name="p12943125711218"></a><a name="p12943125711218"></a>2020/07/25</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1965171632319"><a name="p1965171632319"></a><a name="p1965171632319"></a>支持容器里使用huawei NPU设备的管理插件</p>
</td>
</tr>
<tr id="row20524711182"><td class="cellrowborder" valign="top" width="15.6%" headers="mcps1.2.5.1.1 "><p id="p15943257162118"><a name="p15943257162118"></a><a name="p15943257162118"></a>1.0.1</p>
</td>
<td class="cellrowborder" valign="top" width="26.490000000000002%" headers="mcps1.2.5.1.2 "><p id="p1694335772113"><a name="p1694335772113"></a><a name="p1694335772113"></a>混合集群 v1.(13|15).*</p>
<p id="p1894325717219"><a name="p1894325717219"></a><a name="p1894325717219"></a>鲲鹏集群 v1.(13|15).*</p>
</td>
<td class="cellrowborder" valign="top" width="17.91%" headers="mcps1.2.5.1.3 "><p id="p1894395712219"><a name="p1894395712219"></a><a name="p1894395712219"></a>2020/03/13</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p14966716142320"><a name="p14966716142320"></a><a name="p14966716142320"></a>支持容器里使用huawei NPU设备的管理插件</p>
</td>
</tr>
<tr id="row9487166161815"><td class="cellrowborder" valign="top" width="15.6%" headers="mcps1.2.5.1.1 "><p id="p10943175762111"><a name="p10943175762111"></a><a name="p10943175762111"></a>1.0.0</p>
</td>
<td class="cellrowborder" valign="top" width="26.490000000000002%" headers="mcps1.2.5.1.2 "><p id="p194375762119"><a name="p194375762119"></a><a name="p194375762119"></a>混合集群 v1.(13|15).*</p>
<p id="p1194317579213"><a name="p1194317579213"></a><a name="p1194317579213"></a>鲲鹏集群 v1.(13|15).*</p>
</td>
<td class="cellrowborder" valign="top" width="17.91%" headers="mcps1.2.5.1.3 "><p id="p394365716215"><a name="p394365716215"></a><a name="p394365716215"></a>2020/02/19</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p13966111622312"><a name="p13966111622312"></a><a name="p13966111622312"></a>支持容器里使用huawei NPU设备的管理插件</p>
</td>
</tr>
</tbody>
</table>

