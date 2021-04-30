# volcano<a name="cce_01_0193"></a>

## 插件简介<a name="section173631312185614"></a>

Volcano是一个基于Kubernetes的批处理平台，提供了机器学习、深度学习、生物信息学、基因组学及其他大数据应用所需要而Kubernetes当前缺失的一系列特性。

Volcano源自于华为云高性能批量计算解决方案，在支撑华为云一站式AI开发平台ModelArts、云容器实例CCI等服务稳定运行中发挥重要作用。Volcano提供了高性能任务调度引擎、高性能异构芯片管理、高性能任务运行管理等通用计算能力，通过接入AI、大数据、基因、渲染等诸多行业计算框架服务终端用户。\(目前Volcano项目已经在Github开源\)

Volcano针对计算型应用提供了作业调度、作业管理、队列管理等多项功能，主要特性包括：

-   丰富的计算框架支持：通过CRD提供了批量计算任务的通用API，通过提供丰富的插件及作业生命周期高级管理，支持TensorFlow，MPI，Spark等计算框架容器化运行在Kubernetes上。
-   高级调度：面向批量计算、高性能计算场景提供丰富的高级调度能力，包括成组调度，优先级抢占、装箱、资源预留、任务拓扑关系等。
-   队列管理：支持分队列调度，提供队列优先级、多级队列等复杂任务调度能力。

项目开源地址：[https://github.com/volcano-sh/volcano](https://github.com/volcano-sh/volcano)

## 约束与限制<a name="section11172124718374"></a>

支持在1.13及以上版本的[CCE集群](购买CCE集群.md)和[鲲鹏集群](购买鲲鹏集群.md)中安装本插件。

## 安装插件<a name="section564214328158"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**Volcano**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  Volcano插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“Volcano“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“Volcano“插件时，会替换原先节点上的旧版本的“Volcano“插件，安装最新版本的“Volcano“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  单击“升级“即可升级“Volcano“插件。

## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**Volcano**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

