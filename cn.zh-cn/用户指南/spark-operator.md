# spark-operator<a name="cce_01_0155"></a>

-   [插件简介](#section1880716117376)
-   [约束与限制](#section11172124718374)
-   [安装插件](#section564214328158)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1395073191112)
-   [版本记录](#section144262219109)

## 插件简介<a name="section1880716117376"></a>

Spark operator是一个管理Kubernetes上的Apache Spark应用程序生命周期的operator，旨在像在Kubernetes上运行其他工作负载一样简单的指定和运行spark应用程序。

使用Spark Operator管理Spark应用，能更好的利用Kubernetes原生能力控制和管理Spark应用的生命周期，包括应用状态监控、日志获取、应用运行控制等，弥补Spark on Kubernetes方案在集成Kubernetes上与其他类型的负载之间存在的差距。

Spark Operator包括如下几个组件：

1.  SparkApplication控制器：该控制器用于创建、更新、删除SparkApplication对象，同时控制器还会监控相应的事件，执行相应的动作。
2.  Submission Runner：负责调用spark-submit提交Spark作业，作业提交的流程完全复用Spark on K8s的模式。
3.  Spark Pod Monitor：监控Spark作业相关Pod的状态，并同步到控制器中。
4.  Mutating Admission Webhook：可选模块，基于注解来实现Driver/Executor Pod的一些定制化需求。
5.  SparkCtl：用于和Spark Operator交互的命令行工具。

Spark Operator除了实现基本的作业提交外，还支持如下特性：

-   声明式的作业管理。
-   支持更新SparkApplication对象后自动重新提交作业。
-   支持可配置的重启策略。
-   支持失败重试。
-   集成prometheus，可以收集和转发Spark应用级别的度量和Driver/Executor的度量到prometheus中。

项目地址：[https://github.com/GoogleCloudPlatform/spark-on-k8s-operator](https://github.com/GoogleCloudPlatform/spark-on-k8s-operator)

## 约束与限制<a name="section11172124718374"></a>

此插件仅支持[混合集群](购买混合集群.md)，集群版本仅支持1.13版本。

## 安装插件<a name="section564214328158"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**Spark operator**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  Spark operator插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“Spark operator“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“Spark operator“插件时，会替换原先节点上的旧版本的“Spark operator“插件，安装最新版本的“Spark operator“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  单击“升级“即可升级“Spark operator“插件。

## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**Spark operator**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  Spark operator版本记录

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
<tbody><tr id="row152684214528"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p83741234132610"><a name="p83741234132610"></a><a name="p83741234132610"></a>1.0.2</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p5375734182613"><a name="p5375734182613"></a><a name="p5375734182613"></a>混合集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p13754347263"><a name="p13754347263"></a><a name="p13754347263"></a>2020/01/09</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1175315376261"><a name="p1175315376261"></a><a name="p1175315376261"></a>Spark operator是一个管理Kubernetes上的Apache Spark应用程序生命周期的operator，旨在像在Kubernetes上运行其他工作负载一样简单的指定和运行spark应用程序。</p>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p737523462613"><a name="p737523462613"></a><a name="p737523462613"></a>1.0.1</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p137573482617"><a name="p137573482617"></a><a name="p137573482617"></a>混合集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p14375534162617"><a name="p14375534162617"></a><a name="p14375534162617"></a>2019/11/18</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p197796375263"><a name="p197796375263"></a><a name="p197796375263"></a>Spark operator是一个管理Kubernetes上的Apache Spark应用程序生命周期的operator，旨在像在Kubernetes上运行其他工作负载一样简单的指定和运行spark应用程序。</p>
</td>
</tr>
</tbody>
</table>

