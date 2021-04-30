# npd<a name="cce_01_0132"></a>

## 插件简介<a name="section173631312185614"></a>

node-problem-detector（简称：npd）是一款监控集群节点异常事件的插件，以及对接第三方监控平台功能的组件。它是一个在每个节点上运行的守护程序，可从不同的守护进程中搜集节点问题并将其报告给apiserver。node-problem-detector可以作为DaemonSet运行， 也可以独立运行。

有关社区开源项目node-problem-detector的详细信息，请参见[node-problem-detector](https://github.com/kubernetes/node-problem-detector)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>为快速提升您NPD插件的能力和可靠性，2020年12月30日后系统将定期自动升级插件到最新版本，升级过程会重启各节点上的NPD容器，但不会对您的业务造成影响。若您想提前体验，可以主动在CCE控制台的“插件管理”页面进行升级。升级插件方法请参见[升级插件](#section136451128328)。
>我们强烈建议您进行此次升级，如果您不希望升级npd插件，可以通过提交工单免除此次升级。

## 约束与限制<a name="section11172124718374"></a>

仅1.13以上版本的CCE集群支持此功能，暂不支持鲲鹏集群。

## 安装插件<a name="section189463341114"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**npd**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  npd插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**npd**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 升级插件<a name="section136451128328"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**npd**下的“升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。

2.  在基本信息页面选择集群和插件版本，单击“下一步“。
3.  云存储插件暂未开放可配置参数，直接单击“升级“即可升级npd插件。

