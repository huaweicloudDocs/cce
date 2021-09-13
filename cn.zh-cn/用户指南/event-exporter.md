# event-exporter<a name="cce_01_1126"></a>

## 插件简介<a name="section173631312185614"></a>

event-exporter用于将kubernetes事件上报至[CIE](https://support.huaweicloud.com/productdesc-cie/cie_productdesc_0001.html)。

## 约束与限制<a name="section11172124718374"></a>

-   仅支持在1.13及以上版本的[CCE集群](购买CCE集群.md)中安装本插件。
-   当前仅支持在“上海一”区域使用。

## 使用说明<a name="section0596254104114"></a>

event-exporter是使用CIE中的一环，CIE的具体使用方法请参见[CIE入门指引](https://support.huaweicloud.com/qs-cie/cie_qs_0001.html)。

## 安装插件<a name="section215134717391"></a>

1.  登录CCE控制台，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击“event-exporter“下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  “event-exporter“插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


