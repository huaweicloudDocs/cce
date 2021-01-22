# metrics-server<a name="cce_01_0205"></a>

-   [约束与限制](#section885073715114)
-   [安装插件](#section1962241123816)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1395073191112)
-   [版本记录](#section144262219109)

从Kubernetes 1.8开始，Kubernetes通过Metrics API提供资源使用指标，例如容器CPU和内存使用率。这些度量可以由用户直接访问（例如，通过使用kubectl top命令），或者由集群中的控制器（例如，Horizontal Pod Autoscaler）使用来进行决策，具体的组件为Metrics-Server，用来替换之前的heapster，heapster从1.11开始逐渐被废弃。

Metrics Server是集群核心资源监控数据的聚合器，您可以在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中快速安装本插件。

社区官方项目及文档：[https://github.com/kubernetes-sigs/metrics-server](https://github.com/kubernetes-sigs/metrics-server)。

## 约束与限制<a name="section885073715114"></a>

仅支持v1.13及以上版本的混合集群安装本插件。

## 安装插件<a name="section1962241123816"></a>

安装本插件后，可在“弹性伸缩“页面的“工作负载伸缩“页签下，创建HPA策略，具体请参见[创建工作负载伸缩策略](创建工作负载伸缩策略.md)。

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击“metrics-server“下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  该插件可配置“单实例“或“高可用“规格，选择后单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“metrics-server“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“metrics-server“插件时，会替换原先节点上的旧版本的“metrics-server“插件，安装最新版本的“metrics-server“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  参考[安装插件](#section1962241123816)中参数说明配置参数后，单击“升级“即可升级“metrics-server“插件。

## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击“Metrics Server“下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  metrics-server版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="34.260000000000005%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="20.28%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="29.459999999999997%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row152684214528"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p17262516104819"><a name="p17262516104819"></a><a name="p17262516104819"></a>1.0.5</p>
</td>
<td class="cellrowborder" valign="top" width="34.260000000000005%" headers="mcps1.2.5.1.2 "><p id="p3262131634816"><a name="p3262131634816"></a><a name="p3262131634816"></a>混合集群 v1.13.*|v1.15.*|v1.17.*</p>
</td>
<td class="cellrowborder" valign="top" width="20.28%" headers="mcps1.2.5.1.3 "><p id="p16262016124812"><a name="p16262016124812"></a><a name="p16262016124812"></a>2020/11/06</p>
</td>
<td class="cellrowborder" valign="top" width="29.459999999999997%" headers="mcps1.2.5.1.4 "><p id="p2774144024820"><a name="p2774144024820"></a><a name="p2774144024820"></a>更新至社区v0.3.7版本</p>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p132624161482"><a name="p132624161482"></a><a name="p132624161482"></a>1.0.3</p>
</td>
<td class="cellrowborder" valign="top" width="34.260000000000005%" headers="mcps1.2.5.1.2 "><p id="p1262516144818"><a name="p1262516144818"></a><a name="p1262516144818"></a>混合集群 v1.13.*|v1.15.*|v1.17.*</p>
</td>
<td class="cellrowborder" valign="top" width="20.28%" headers="mcps1.2.5.1.3 "><p id="p1226221614819"><a name="p1226221614819"></a><a name="p1226221614819"></a>2020/08/19</p>
</td>
<td class="cellrowborder" valign="top" width="29.459999999999997%" headers="mcps1.2.5.1.4 "><p id="p97991940154815"><a name="p97991940154815"></a><a name="p97991940154815"></a>新插件</p>
</td>
</tr>
<tr id="row97875912317"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p182629162489"><a name="p182629162489"></a><a name="p182629162489"></a>1.0.0</p>
</td>
<td class="cellrowborder" valign="top" width="34.260000000000005%" headers="mcps1.2.5.1.2 "><p id="p12262716154820"><a name="p12262716154820"></a><a name="p12262716154820"></a>混合集群 v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="20.28%" headers="mcps1.2.5.1.3 "><p id="p52628160486"><a name="p52628160486"></a><a name="p52628160486"></a>2019/12/16</p>
</td>
<td class="cellrowborder" valign="top" width="29.459999999999997%" headers="mcps1.2.5.1.4 "><p id="p7825240164812"><a name="p7825240164812"></a><a name="p7825240164812"></a>新插件</p>
</td>
</tr>
</tbody>
</table>

