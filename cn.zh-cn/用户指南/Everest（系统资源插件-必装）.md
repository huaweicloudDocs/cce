# Everest（系统资源插件，必装）<a name="cce_01_0066"></a>

## 插件简介<a name="section25311744154917"></a>

Everest是一个云原生容器存储系统，基于CSI为Kubernetes v1.15.6及以上版本集群对接华为云云硬盘服务 EVS、对象存储服务 OBS、弹性文件服务 SFS、极速文件存储 SFS Turbo等存储服务的能力。

**该插件为系统资源插件，kubernetes 1.15及以上版本的集群在创建时默认安装。**

## 使用限制<a name="section202191122814"></a>

-   仅支持**v1.15及以上版本**的混合集群和裸金属集群安装本插件。
-   v1.13及以下版本集群创建时默认必装[storage-driver](storage-driver（系统资源插件-必装）.md)插件。

## 安装插件<a name="section168341157155317"></a>

本插件为系统默认安装，若因特殊情况卸载后，可参照如下步骤重新安装。

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“中，单击“everest“插件下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  该插件可配置“单实例“或“高可用“规格，选择后单击“安装“。

    待插件安装完成后，单击“返回插件管理“，在“插件实例“页签中，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section414918421496"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件市场“中，选择对应的集群，单击“everest“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。  
    >-   升级everest插件时，会替换原先节点上的旧版本的everest插件，安装最新版本的everest插件以实现功能的快速升级。  

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  该插件可配置“单实例“或“高可用“规格，选择后单击“升级“即可升级“everest“插件。

## 卸载插件<a name="section610455514114"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签中，选择对应的集群，单击“everest“下的“卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

