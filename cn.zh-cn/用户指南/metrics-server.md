# metrics-server<a name="cce_10_0205"></a>

从Kubernetes 1.8开始，Kubernetes通过Metrics API提供资源使用指标，例如容器CPU和内存使用率。这些度量可以由用户直接访问（例如，通过使用kubectl top命令），或者由集群中的控制器（例如，Horizontal Pod Autoscaler）使用来进行决策，具体的组件为Metrics-Server，用来替换之前的heapster，heapster从1.11开始逐渐被废弃。

Metrics Server是集群核心资源监控数据的聚合器，您可以在CCE控制台快速安装本插件。

安装本插件后，可在“弹性伸缩“页面的“工作负载伸缩“页签下，创建HPA策略，具体请参见[创建工作负载弹性伸缩（HPA）](创建工作负载弹性伸缩（HPA）.md)。

社区官方项目及文档：[https://github.com/kubernetes-sigs/metrics-server](https://github.com/kubernetes-sigs/metrics-server)。

## 安装插件<a name="section1962241123816"></a>

1.  登录CCE控制台，单击左侧导航栏的“插件管理“，在右侧找到**metrics-server**，单击“安装“。
2.  该插件可配置“单实例“或“高可用“规格，选择后单击“安装“。

