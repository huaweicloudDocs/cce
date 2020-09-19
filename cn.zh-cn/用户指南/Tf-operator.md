# Tf-operator<a name="cce_01_0199"></a>

## 插件简介<a name="section173631312185614"></a>

Tf-operator是一个管理Kubernetes上tensorflow应用程序生命周期的operator，旨在像在Kubernetes上运行其他工作负载一样简单的指定和运行tensorflow应用程序。

社区官方项目及文档：[https://github.com/kubeflow/tf-operator](https://github.com/kubeflow/tf-operator)

## 使用约束<a name="section58764833810"></a>

插件支持[混合集群](购买混合集群.md)，集群版本需为1.13及以上版本。

## 安装插件<a name="section3843632115420"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**tf-operator**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  tf-operator插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回插件管理“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 卸载插件<a name="section1484453212546"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**tf-operator**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

