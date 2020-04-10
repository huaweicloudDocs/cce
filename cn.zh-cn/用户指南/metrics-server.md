# metrics-server<a name="cce_01_0205"></a>

从Kubernetes 1.8开始，Kubernetes通过Metrics API提供资源使用指标，例如容器CPU和内存使用率。这些度量可以由用户直接访问（例如，通过使用kubectl top命令），或者由集群中的控制器（例如，Horizontal Pod Autoscaler）使用来进行决策，具体的组件为Metrics-Server，用来替换之前的heapster，heapster从1.11开始逐渐被废弃。

Metrics-Server是集群核心资源监控数据的聚合器，您可以在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中快速安装本插件。

社区官方项目及文档：[https://github.com/kubernetes-sigs/metrics-server](https://github.com/kubernetes-sigs/metrics-server)。

## 使用限制<a name="section885073715114"></a>

仅支持v1.13及以上版本的混合集群和裸金属集群安装本插件。

## 安装插件<a name="section1962241123816"></a>

安装本插件后，可在“弹性伸缩“页面的“工作负载伸缩“页签中，创建HPA策略，具体请参见[工作负载伸缩](工作负载伸缩.md)。

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签中，单击“Metrics Server“下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  该插件可配置“单实例“或“高可用“规格，选择后单击“安装“。

    待插件安装完成后，单击“返回插件管理“，在“插件实例“页签中，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签中，选择对应的集群，单击“Metrics Server“下的“卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

