# virtual kubelet插件<a name="cce_01_0135"></a>

一款支持用户在CCE部署的Job、Deployment、Pod三种资源类型弹性扩容时，将实例调度到CCI的插件，可以减少因为扩容集群产生的费用。

## 使用约束<a name="section628693291119"></a>

-   暂不支持非VPC网络模式的集群。
-   调度到CCI的实例的存储类型只支持SFS、Confimap、Secret三种存储。
-   实例的规格必须满足云容器实例CCI的[容器规范](https://support.huaweicloud.com/productdesc-cci/cci_03_0007.html)。
-   使用插件前需要用户在[CCI界面](https://console.huaweicloud.com/cci)对CCI服务进行授信。

## 安装插件步骤<a name="section2237175619515"></a>

1.  在CCE控制台中，单击左侧导航栏的“资源管理  \>  插件管理“，在“插件市场“中，单击virtual kubelet插件下的“安装插件“。
2.  需要CCE和CCI两侧实例网络互通时，请在安装插件时勾选“service互通“。
3.  在安装插件页面，选择安装的集群和插件版本，单击“下一步“。
4.  单击“安装“。安装完成后，会在当前集群中安装该插件实例。

## 配置插件步骤<a name="section162391856185111"></a>

成功安装virtual kubelet后，仍需完成如下步骤才能使用。

1.  在创建无状态工作负载、Job时，填写基本信息流程中，勾选“CCI弹性承载“。
2.  单击“下一步“继续创建相关资源。

## 卸载插件<a name="section1624015695110"></a>

1.  在CCE控制台中，单击左侧导航栏的“资源管理 \> 插件管理“，在“插件实例“页签中，选择对应的集群，单击virtual kubelet下的“卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

