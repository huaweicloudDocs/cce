# 管理容器组\(Pod\)<a name="cce_01_0013"></a>

容器组（Pod）是 Kubernetes 中最小的可部署单元。一个 Pod（容器组）包含了一个应用程序容器（某些情况下是多个容器）、存储资源、一个唯一的网络 IP 地址、以及一些确定容器该如何运行的选项。Pod 容器组代表了 Kubernetes 中一个独立的应用程序运行实例，该实例可能由单个容器或者几个紧耦合在一起的容器组成。

Kubernetes 集群中的 Pod 存在如下两种使用途径：

-   一个 Pod 中只运行一个容器。"one-container-per-pod" 是 Kubernetes 中最常见的使用方式。此时，您可以认为 Pod 容器组是该容器的 wrapper，Kubernetes 通过 Pod 管理容器，而不是直接管理容器。
-   一个 Pod 中运行多个需要互相协作的容器。您可以将多个紧密耦合、共享资源且始终在一起运行的容器编排在同一个 Pod 中，可能的情况有：
    -   Content management systems, file and data loaders, local cache managers 等
    -   log and checkpoint backup, compression, rotation, snapshotting 等
    -   data change watchers, log tailers, logging and monitoring adapters, event publishers 等
    -   proxies, bridges, adapters 等
    -   controllers, managers, configurators, and updaters


您可以在云容器引擎CCE中方便的管理容器组（Pod），如编辑YAML、监控、删除等操作。

## 编辑YAML<a name="section13937181015513"></a>

可通过在线YAML编辑窗对容器组（Pod）的YAML文件进行修改和下载。

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“工作负载 \> 容器组 Pod”。
2.  单击实例列表中后的“编辑YAML“，在弹出的“编辑YAML“窗中可对当前容器组（Pod）的YAML文件进行修改。
3.  单击“修改“，在弹出的提示框中单击“确定“，完成修改。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果实例由其他工作负载创建，暂不支持在容器组（Pod）中单独修改。  

4.  （可选）在“编辑YAML“窗中，单击“下载“，可下载该YAML文件。

## 实例监控<a name="section88077333511"></a>

您可以通过CCE控制台查看工作负载实例的CPU、内存使用情况以及网络上行和下行速率、磁盘的读写速率，以确定需要的资源规格。

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“工作负载 \> 容器组 Pod”。
2.  单击实例列表中后的“监控“，可查看相应实例的CPU使用率、内存使用率以及网络上行和下行速率、磁盘的读写速率。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >实例处于非运行状态时，无法查看实例的监控数据。  


## 删除实例<a name="section1917010503513"></a>

若实例无需再使用，您可以将其删除。实例删除后，将无法恢复，请谨慎操作。

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“工作负载 \> 容器组 Pod”。
2.  单击待删除实例后的“删除“，即可删除该实例。

    请仔细阅读系统提示。

3.  单击“确定“。

## 相关链接<a name="section367274071320"></a>

-   [The Distributed System Toolkit: Patterns for Composite Containers](https://kubernetes.io/blog/2015/06/the-distributed-system-toolkit-patterns)
-   [Container Design Patterns](https://kubernetes.io/blog/2016/06/container-design-patterns/)

