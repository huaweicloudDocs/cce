# metrics-server<a name="cce_01_0205"></a>

-   [约束与限制](#section885073715114)
-   [安装插件](#section1962241123816)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1395073191112)

从Kubernetes 1.8开始，Kubernetes通过Metrics API提供资源使用指标，例如容器CPU和内存使用率。这些度量可以由用户直接访问（例如，通过使用kubectl top命令），或者由集群中的控制器（例如，Horizontal Pod Autoscaler）使用来进行决策，具体的组件为Metrics-Server，用来替换之前的heapster，heapster从1.11开始逐渐被废弃。

Metrics Server是集群核心资源监控数据的聚合器，您可以在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中快速安装本插件。

社区官方项目及文档：[https://github.com/kubernetes-sigs/metrics-server](https://github.com/kubernetes-sigs/metrics-server)。

## 约束与限制<a name="section885073715114"></a>

仅支持v1.13及以上版本的CCE集群安装本插件。

## 安装插件<a name="section1962241123816"></a>

安装本插件后，可在“弹性伸缩“页面的“工作负载伸缩“页签下，创建HPA策略，具体请参见[创建工作负载弹性伸缩（HPA）](创建工作负载弹性伸缩（HPA）.md)。

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

