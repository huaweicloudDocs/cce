# Tf-operator<a name="cce_01_0199"></a>

-   [插件简介](#section173631312185614)
-   [约束与限制](#section58764833810)
-   [安装插件](#section3843632115420)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1484453212546)

## 插件简介<a name="section173631312185614"></a>

Tf-operator是一个管理Kubernetes上tensorflow应用程序生命周期的operator，旨在像在Kubernetes上运行其他工作负载一样简单的指定和运行tensorflow应用程序。

社区官方项目及文档：[https://github.com/kubeflow/tf-operator](https://github.com/kubeflow/tf-operator)

## 约束与限制<a name="section58764833810"></a>

-   插件支持[CCE集群](购买CCE集群.md)，仅支持1.13和1.15版本的集群。
-   部分Region不支持本插件，具体以控制台为准。

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

