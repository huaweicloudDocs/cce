# event-exporter<a name="cce_01_1126"></a>

## 插件简介<a name="section173631312185614"></a>

event-exporter用于将kubernetes事件转换为告警并上报至告警中心，用户可查看容器告警信息。

## 约束与限制<a name="section11172124718374"></a>

仅支持在1.13及以上版本的[CCE集群](购买CCE集群.md)中安装本插件。

## 安装插件<a name="section215134717391"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击“event-exporter“下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  “event-exporter“插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section97665415343"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“event-exporter“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“event-exporter“插件时，会替换原先节点上的旧版本的“event-exporter“插件，安装最新版本的“event-exporter“插件以实现功能的快速升级。

2.  在升级插件基本信息页面，选择插件升级到的版本，单击“下一步”。
3.  event-exporter插件暂未开放可配置参数，直接单击“升级”。

    升级完成后，在插件实例列表中，可查看到插件版本已升级到目标版本。


## 卸载插件<a name="section20773114133417"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“event-exporter“下的“ 卸载“。
2.  在弹出的窗口中，单击“确定”，可卸载插件。

## 页面告警信息查看<a name="section7775448346"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“监控中心”。
2.  在应用运维管理页面，选择“告警 \> 告警列表”，可以查看容器告警信息。

