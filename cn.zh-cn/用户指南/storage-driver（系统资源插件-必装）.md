# storage-driver（系统资源插件，必装）<a name="cce_01_0127"></a>

-   [插件简介](#section25311744154917)
-   [约束与限制](#section3993231122718)
-   [安装插件](#section776571919194)
-   [升级插件](#section455343310401)
-   [卸载插件](#section20765191931911)

## 插件简介<a name="section25311744154917"></a>

storage-driver插件是用于对接华为云块存储、文件存储、对象存储、极速文件存储等Iaas存储服务的FlexVolume驱动。

storage-driver是一款云存储驱动插件，北向遵循标准容器平台存储驱动接口。实现Kubernetes Flex Volume标准接口，提供容器使用华为云EVS块存储、SFS文件存储、OBS 对象存储、SFS Turbo 极速文件存储等华为云IAAS存储的能力。通过安装升级云存储插件可以实现云存储功能的快速安装和更新升级。

**该插件为系统资源插件，kubernetes 1.13及以下版本的集群在创建时默认安装。**

## 约束与限制<a name="section3993231122718"></a>

-   v1.15.11-r1是Flexvolume fuxi（即storage-driver）和CSI（即[Everest](Everest（系统资源插件-必装）.md)插件）兼容接管的过渡版本，在v1.17集群中已经去除了对Flexvolume fuxi的支持，请您将Flexvolume fuxi的使用切换CSI Everest上。
-   CSI Everest兼容接管Flexvolume fuxi后，原有功能保持不变，但请注意不要新建fuxi Flexvolume的存储，否则将导致部分存储功能异常。
-   当存储功能有升级或者BUG修复时，用户无需升级集群或新建集群来升级存储功能，仅需安装或升级storage-driver插件。
-   本插件仅支持在**v1.13及以下版本**的集群中安装，v1.15及以上版本集群创建时默认必装[Everest](Everest（系统资源插件-必装）.md)插件。

## 安装插件<a name="section776571919194"></a>

本插件为系统默认安装，若因特殊情况卸载后，可参照如下步骤重新安装。

在云容器引擎CCE中，kubernetes 1.11及以上版本的新建集群，将会默认安装storage-driver插件。

未安装storage-driver插件的集群，可参考如下步骤进行安装：

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件市场“页签下，单击**storage-driver**插件下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  云存储插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section455343310401"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**storage-driver**下的“升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级storage-driver插件时，会替换原先节点上的旧版本的storage-driver插件，安装最新版本的storage-driver插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  云存储插件暂未开放可配置参数，直接单击“升级“即可升级storage-driver插件。

## 卸载插件<a name="section20765191931911"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**storage-driver**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

