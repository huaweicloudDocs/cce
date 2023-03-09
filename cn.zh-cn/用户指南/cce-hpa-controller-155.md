# cce-hpa-controller<a name="cce_01_0240"></a>

cce-hpa-controller插件是一款CCE自研的插件，能够基于CPU利用率、内存利用率等指标，对无状态工作负载进行弹性扩缩容。

安装本插件后，可在“弹性伸缩“页面的“工作负载伸缩“页签下，创建CustomedHPA策略。

## 主要功能<a name="section16202940121214"></a>

-   支持按照当前实例数的百分比进行扩缩容。
-   支持设置一次扩缩容的最小步长。
-   支持按照实际指标值执行不同的扩缩容动作。

## 约束与限制<a name="section147226815158"></a>

-   仅支持在v1.15及以上版本的CCE集群中安装本插件。
-   若cce-hpa-controller版本低于1.2.11，则必须安装[prometheus](prometheus-156.md)插件，若版本大于或等于1.2.11，则需要安装能够提供Metrics API的插件，如metrics-server和Prometheus。若使用Prometheus，需要将Prometheus注册为Metrics API的服务，详见[提供资源指标](prometheus-156.md#section13409107262)。

## 安装插件<a name="section046523415137"></a>

1.  登录CCE控制台，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击“cce-hpa-controller“下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  该插件可配置“单实例“或“自定义“规格，选择后单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section23441939916"></a>

1.  登录CCE控制台，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“cce-hpa-controller“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“cce-hpa-controller“插件时，会替换原先节点上的旧版本的“cce-hpa-controller“插件，安装最新版本的“cce-hpa-controller“插件以实现功能的快速升级。

2.  参考[安装插件](#section046523415137)中参数说明配置参数后，单击“升级“即可升级“cce-hpa-controller“插件。

## 卸载插件<a name="section1395073191112"></a>

1.  登录CCE控制台，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击“cce-hpa-controller“下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

