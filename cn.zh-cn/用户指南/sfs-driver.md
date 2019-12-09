# sfs-driver<a name="cce_01_0068"></a>

## 插件简介<a name="section25311744154917"></a>

sfs-driver插件用于对接SFS文件存储服务的FlexVolume驱动，是一款文件存储驱动插件，北向遵循标准容器平台存储驱动接口。实现Kubernetes Flex Volume标准接口，提供容器使用SFS文件存储的能力。通过安装升级sfs-driver文件存储插件可以实现文件存储插件的快速安装和更新升级。

## 使用场景<a name="section202191122814"></a>

当文件存储功能有升级或者BUG修复时，用户无需升级集群或新建集群来升级存储功能，仅需安装或升级文件存储插件。

## 安装插件<a name="section15573161754711"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“ 插件管理“，在“插件市场“中，单击**sfs-driver**插件下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步“。
3.  文件存储插件暂未开放可配置参数，直接单击“安装“。

    安装完成后，在当前集群的各节点上会安装该插件，替换原先节点上的文件存储插件，以实现文件存储功能的快速升级。


## 卸载插件<a name="section610455514114"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“ 插件管理“，在“插件实例“页签中，选择对应的集群，单击**sfs-driver**下的“卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

