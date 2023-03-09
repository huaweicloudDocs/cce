# storage-driver（系统资源插件，已废弃）<a name="cce_10_0127"></a>

## 插件简介<a name="section25311744154917"></a>

storage-driver是一款云存储驱动插件，北向遵循标准容器平台存储驱动接口。实现Kubernetes Flex Volume标准接口，提供容器使用EVS块存储、SFS文件存储、OBS 对象存储、SFS Turbo 极速文件存储的能力。通过安装升级云存储插件可以实现云存储功能的快速安装和更新升级。

**该插件为系统资源插件，kubernetes 1.13及以下版本的集群在创建时默认安装。**

## 约束与限制<a name="section3993231122718"></a>

-   在CCE所创的集群中，Kubernetes v1.15.11版本是Flexvolume插件（storage-driver）被CSI插件（[Everest](everest（系统资源插件-必装）.md)）兼容接管的过渡版本，v1.17及之后版本的集群中将彻底去除对Flexvolume插件（storage-driver）的支持，请您将Flexvolume插件的使用切换到CSI插件上。
-   CSI插件（[Everest](everest（系统资源插件-必装）.md)）兼容接管Flexvolume插件（storage-driver）后，原有功能保持不变，但请注意不要新建Flexvolume插件（storage-driver）的存储，否则将导致部分存储功能异常。
-   本插件仅支持在**v1.13及以下版本**的集群中安装，v1.15及以上版本的集群在创建时默认安装[Everest](everest（系统资源插件-必装）.md)插件。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >在**v1.13及以下版本**的集群中，当存储功能有升级或者BUG修复时，用户无需升级集群或新建集群来升级存储功能，仅需安装或升级storage-driver插件。


## 安装插件<a name="section776571919194"></a>

本插件为系统默认安装，若因特殊情况卸载后，可参照如下步骤重新安装。

未安装storage-driver插件的集群，可参考如下步骤进行安装：

1.  登录CCE控制台，单击集群名称进入集群，在左侧导航栏中选择“插件管理“，在右侧找到**storage-driver**，单击“安装“。
2.  云存储插件暂未开放可配置参数，直接单击“安装“。

