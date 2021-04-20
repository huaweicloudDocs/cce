# web-terminal<a name="cce_01_0134"></a>

web-terminal是一款非常轻巧的终端服务器，支持在Web界面上使用Kubectl命令。它支持通过标准的Web浏览器和HTTP协议提供远程CLI，提供灵活的接口便于集成到独立系统中，可直接作为一个服务连接，通过cmdb获取信息并登录服务器。

web-terminal可以在Node.js支持的所有操作系统上运行，而不依赖于本机模块，快速且易于安装，支持多会话。

开源社区地址：[https://github.com/rabchev/web-terminal](https://github.com/rabchev/web-terminal)

## 约束与限制<a name="section628693291119"></a>

集群为1.9及以上版本时，才支持此功能。

## 安装插件<a name="section41861311141210"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“ 插件管理“，在“插件市场“页签下，单击**web-terminal**插件下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  <a name="li153748218613"></a>在规格配置页面，配置以下参数。
    -   用户名：默认为root，不可修改。
    -   密码：登录web-terminal的密码，请务必记住该密码。
    -   确认密码：重新准确输入该密码。
    -   访问类型：
        -   节点访问：该插件默认以NodePort形式提供访问，需为集群任意一个节点绑定弹性IP才能使用。若集群没有绑定弹性IP，需绑定弹性IP。
        -   负载均衡：选择弹性负载均衡实例。若无弹性负载均衡实例，需新建[共享型弹性负载均衡](https://console.huaweicloud.com/vpc/#/ulb/createUlb)，完成后单击刷新按钮。负载均衡实例需与当前集群处于相同VPC且为公网类型。

    -   端口配置：访问类型为负载均衡时，需端口配置。
        -   协议：固定为TCP。
        -   容器端口：容器镜像中工作负载实际监听端口，为默认值，无法更改。
        -   访问端口：容器端口最终映射到负载均衡服务地址的端口，用负载均衡服务地址访问工作负载时使用，端口范围为1-65535，可任意指定。


4.  单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 使用web-terminal插件连接集群<a name="section115151890220"></a>

**方式一：**

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“资源管理 \> 集群管理“。
2.  单击集群下方的“命令行工具 \> web-terminal“进入插件实例详情页。

    **图 1**  使用web-terminal连接集群<a name="fig363789132816"></a>  
    ![](figures/使用web-terminal连接集群.png "使用web-terminal连接集群")

3.  单击插件详情页中访问地址后的链接即可访问。

    **图 2**  web-terminal插件访问地址<a name="fig109178487467"></a>  
    ![](figures/web-terminal插件访问地址.png "web-terminal插件访问地址")


**方式二：**

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“。
2.  在“插件实例”中，正确选择插件所在的集群，单击“web-terminal”进入详情页。
3.  单击插件详情页中访问地址后的链接即可访问。

## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“web-terminal“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“web-terminal“插件时，会替换原先节点上的旧版本的“web-terminal“插件，安装最新版本的“web-terminal“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  参考[安装插件](#li153748218613)中参数说明配置参数后，单击“升级“即可升级“web-terminal“插件。

## 卸载插件<a name="section65651488131"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击web-terminal下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

