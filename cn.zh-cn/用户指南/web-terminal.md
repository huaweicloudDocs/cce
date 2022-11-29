# web-terminal<a name="cce_10_0134"></a>

web-terminal是一款非常轻巧的终端服务器，支持在Web界面上使用Kubectl命令。它支持通过标准的Web浏览器和HTTP协议提供远程CLI，提供灵活的接口便于集成到独立系统中，可直接作为一个服务连接，通过cmdb获取信息并登录服务器。

web-terminal可以在Node.js支持的所有操作系统上运行，而不依赖于本机模块，快速且易于安装，支持多会话。

开源社区地址：[https://github.com/rabchev/web-terminal](https://github.com/rabchev/web-terminal)

## 约束与限制<a name="section628693291119"></a>

-   仅支持在1.21及以下版本的集群中安装此插件，暂不支持ARM集群。
-   web-terminal插件当前版本处于beta阶段中，后续将使用cloudshell方案代替，请根据实际场景选择体验。
-   web-terminal中kubectl具有高级别操作权限，限账号以及具有CCE Administrator权限的IAM用户安装此插件，如需收缩插件中kubectl权限，请参见[收缩web-terminal权限](#section62000142412)操作。
-   集群必须安装CoreDNS才能使用web-terminal。

## 注意事项<a name="section1357919311966"></a>

web-terminal插件能够对CCE集群进行管理，请用户妥善保管好登录密码，避免密码泄漏造成损失。

## 安装插件<a name="section41861311141210"></a>

1.  登录CCE控制台，进入集群，单击左侧导航栏的“ 插件管理“，在右侧找到**web-terminal**，单击“安装“。
2.  配置以下参数。
    -   访问类型：固定为节点访问，该插件默认以NodePort形式提供访问，需为集群任意一个节点绑定弹性IP才能使用。若集群没有绑定弹性IP，需绑定弹性IP。
    -   用户名：默认为root，不可修改。
    -   密码：登录web-terminal的密码，请务必记住该密码。web-terminal插件能够对CCE集群进行管理，请用户妥善保管好登录密码，避免密码泄漏造成损失。
    -   确认密码：重新准确输入该密码。

3.  单击“安装“。

## 使用web-terminal插件连接集群<a name="section115151890220"></a>

1.  登录CCE控制台，进入集群，单击左侧导航栏的“插件管理“。
2.  在右侧找到web-terminal，单击“访问“。

## 收缩web-terminal权限<a name="section62000142412"></a>

web-terminal插件安装后，其kubectl默认使用cluster-admin ClusterRole权限，能够操作该集群k8s资源，若需手动配置为其他类型权限，可通过kubectl edit clusterrolebinding web-terminal修改web-terminal ServiceAccount绑定其他权限的ClusterRole。

ClusterRole、ClusterRoleBinding相关配置说明请参见[命名空间权限（Kubernetes RBAC授权）](命名空间权限（Kubernetes-RBAC授权）.md)。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>-   手动配置的web-terminal权限在web-terminal插件升级时存在被重置风险，需注意做好备份在插件升级后重新配置。
>-   使用kubectl修改clusterrolebinding配置需确保当前kubectl有修改clusterrolebinding资源操作权限。

