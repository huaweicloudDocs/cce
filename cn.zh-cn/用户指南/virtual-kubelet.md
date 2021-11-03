# virtual-kubelet<a name="cce_01_0135"></a>

Virtual Kubelet是基于社区Virtual Kubelet开源项目开发的插件，作为一种虚拟的kubelet用来连接Kubernetes集群和其他平台的API。Virtual Kubelet的主要场景是将Kubernetes API扩展到无服务器的容器平台（如CCI）。

基于该插件，支持华为云用户在短时高负载场景下，将部署在云容器引擎CCE上的无状态负载（Deployment）、有状态负载（StatefulSet）、普通任务（Job）三种资源类型的容器实例（Pod），弹性创建到[云容器实例CCI](https://support.huaweicloud.com/cci/index.html)服务上，以减少集群扩容带来的消耗。详情请参见[华为云CCE弹性到CCI](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_0133.html)。

开源社区地址：[https://github.com/virtual-kubelet/virtual-kubelet](https://github.com/virtual-kubelet/virtual-kubelet)

Virtual Kubelet插件具体如下功能：

-   **支持容器实例实现秒级弹性伸缩：**在集群资源不足时，无需新增节点，virtual kubelet插件将自动为您在[云容器实例CCI](https://support.huaweicloud.com/cci/index.html)侧创建容器实例，减少运维成本。
-   无缝对接华为云[容器镜像服务SWR](https://support.huaweicloud.com/swr/index.html)，支持使用公用镜像和私有镜像。
-   支持CCI容器实例的事件同步、监控、日志、exec、查看状态等操作。
-   支持查看虚拟弹性节点的节点容量信息。
-   支持CCE和CCI两侧实例的service网络互通。

## 约束及限制<a name="section628693291119"></a>

-   仅支持VPC网络模式的CCE集群。

-   调度到CCI的实例的存储类型只支持ConfigMap、Secret、emptyDir、SFS、SFS Turbo几种Volume类型，其中emptyDir不支持子路径。
-   暂不支持守护进程集（DaemonSet）以及HostNetwork网络模式的容器实例（Pod）弹性到CCI。
-   跨CCE和CCI实例Service网络互通只支持集群内访问（ClusterIP）类型。
-   集群所在子网不能与10.247.0.0/16重叠，否则会与CCI命名空间下的Service网段冲突，导致无法使用。
-   使用插件前需要用户在[CCI界面](https://console.huaweicloud.com/cci/?locale=zh-cn#/dashboard)对CCI服务进行授信。
-   实例的规格必须满足云容器实例CCI的容器规范。
    1.  Pod的CPU取值范围为：0.25核\~32核，另外还可选48核和64核，且单个容器的CPU必须为0.25核的整数倍。
    2.  Pod的内存取值范围为：1GB\~512GB，且内存必须为1GB的整数倍。
    3.  Pod的CPU/内存配比值必须在1:2到1:8之间。
    4.  一个Pod内最多支持5个容器，单个容器最小配置是0.25核、0.2GB，最大同容器实例的最大配置。
    5.  资源的requests等于limits。


## 安装插件<a name="section2237175619515"></a>

1.  在CCE控制台中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击virtual-kubelet插件下的“安装插件“。
2.  在“基本信息“步骤中，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  在“规格配置“步骤中，勾选“跨服务互通“后的选择框，可实现CCE集群中的Pod与CCI集群中的Pod通过Kubernetes Service互通。

    **图 1**  勾选“跨服务互通“<a name="fig14909180185319"></a>  
    ![](figures/勾选跨服务互通.png "勾选跨服务互通")

4.  单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 使用插件<a name="section162391856185111"></a>

您成功安装virtual-kubelet插件后，按如下步骤创建可弹性到CCI的负载：

1.  在CCE控制台中，单击左侧导航栏的“工作负载“。
2.  在创建无状态工作负载或Job时，在“工作负载基本信息“步骤中，勾选“CCI弹性承载“。

    **图 2**  勾选“CCI弹性承载“<a name="fig610418228234"></a>  
    ![](figures/勾选CCI弹性承载.png "勾选CCI弹性承载")

3.  单击“下一步“继续创建相关资源。

## 升级插件<a name="section23441939916"></a>

1.  登录CCE控制台，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“virtual-kubelet“下的“升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“virtual-kubelet“插件时，会替换原先节点上的旧版本的“virtual-kubelet“插件，安装最新版本的“virtual-kubelet“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  参考[安装插件](#section2237175619515)中参数说明配置参数后，单击“升级“即可升级“virtual-kubelet“插件。

## 卸载插件<a name="section1624015695110"></a>

1.  在CCE控制台中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击virtual-kubelet下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

