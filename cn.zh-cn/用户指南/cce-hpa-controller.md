# cce-hpa-controller<a name="cce_10_0240"></a>

cce-hpa-controller插件是一款CCE自研的插件，能够基于CPU利用率、内存利用率等指标，对无状态工作负载进行弹性扩缩容。

安装本插件后，可在“弹性伸缩“页面的“工作负载伸缩“页签下，创建CustomedHPA策略，具体请参见[创建工作负载弹性伸缩（CustomedHPA）](创建工作负载弹性伸缩（CustomedHPA）.md)。

## 主要功能<a name="section16202940121214"></a>

-   支持按照当前实例数的百分比进行扩缩容。
-   支持设置一次扩缩容的最小步长。
-   支持按照实际指标值执行不同的扩缩容动作。

## 约束与限制<a name="section147226815158"></a>

-   仅支持在v1.15及以上版本的CCE集群中安装本插件。
-   若cce-hpa-controller版本低于1.2.11，则必须安装[prometheus](prometheus.md)插件，若版本大于或等于1.2.11，则需要安装能够提供Metrics API的插件，如metrics-server和Prometheus。若使用Prometheus，需要将Prometheus注册为Metrics API的服务，详见[提供资源指标](prometheus.md#section13409107262)。

## 安装插件<a name="section046523415137"></a>

1.  登录CCE控制台，进入集群，单击左侧导航栏的“插件管理“，在右侧找到**cce-hpa-controller**，单击“安装“。
2.  该插件可配置“单实例“或“自定义“规格，选择后单击“安装“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >单实例仅用于验证场景，商用场景请根据集群规格使用"自定义"资源配置，cce-hpa-controller插件的规格大小主要受集群中总容器数量和伸缩策略数量影响，通常场景下建议每5000容器配置CPU 500m, 内存1000Mi资源，每1000伸缩策略CPU 100m，内存500Mi。


