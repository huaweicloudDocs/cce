# Tf-operator<a name="cce_01_0199"></a>

-   [插件简介](#section173631312185614)
-   [约束与限制](#section58764833810)
-   [安装插件](#section3843632115420)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1484453212546)
-   [版本记录](#section144262219109)

## 插件简介<a name="section173631312185614"></a>

Tf-operator是一个管理Kubernetes上tensorflow应用程序生命周期的operator，旨在像在Kubernetes上运行其他工作负载一样简单的指定和运行tensorflow应用程序。

社区官方项目及文档：[https://github.com/kubeflow/tf-operator](https://github.com/kubeflow/tf-operator)

## 约束与限制<a name="section58764833810"></a>

插件支持[混合集群](购买混合集群.md)，集群版本需为1.13及以上版本。

## 安装插件<a name="section3843632115420"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**tf-operator**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  tf-operator插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“tf-operator“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“tf-operator“插件时，会替换原先节点上的旧版本的“tf-operator“插件，安装最新版本的“tf-operator“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  单击“升级“即可升级“tf-operator“插件。

## 卸载插件<a name="section1484453212546"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**tf-operator**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  tf-operator版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="24%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row152684214528"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p7749727182713"><a name="p7749727182713"></a><a name="p7749727182713"></a>1.0.1</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p9749132710278"><a name="p9749132710278"></a><a name="p9749132710278"></a>混合集群 v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1474915278271"><a name="p1474915278271"></a><a name="p1474915278271"></a>2020/07/15</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p32361858132716"><a name="p32361858132716"></a><a name="p32361858132716"></a>Tensorflow operator支持volcano批调度。</p>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p1174917271275"><a name="p1174917271275"></a><a name="p1174917271275"></a>1.0.0</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p37491327122719"><a name="p37491327122719"></a><a name="p37491327122719"></a>混合集群 v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p19749192742717"><a name="p19749192742717"></a><a name="p19749192742717"></a>2020/06/22</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1923745822717"><a name="p1923745822717"></a><a name="p1923745822717"></a>Tensorflow operator是一个管理Kubernetes上的Tensorflow应用程序生命周期的operator，旨在像在Kubernetes上运行其他工作负载一样简单的指定和运行Tensorflow应用程序。</p>
</td>
</tr>
</tbody>
</table>

