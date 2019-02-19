# Dashboard插件<a name="cce_01_0128"></a>

## 插件简介<a name="section1418513434428"></a>

Kubernetes Dashboard是Kubernetes集群的基于Web的通用UI。它允许用户管理在集群中运行的应用程序并对其进行故障排除，以及管理集群本身。

>![](public_sys-resources/icon-note.gif) **说明：**   
>当前华为云CCE提供的Dashboard插件已将对应镜像升级到v1.10.1版本，不受Kubernetes Dashboard漏洞CVE-2018-18264影响。  
>安全漏洞CVE-2018-18264的详细信息，请参考：  
>-   [https://github.com/kubernetes/dashboard/pull/3289](https://github.com/kubernetes/dashboard/pull/3289?spm=a2c4g.11186623.2.10.34d16d21dGsJMe)  
>-   [https://github.com/kubernetes/dashboard/pull/3400](https://github.com/kubernetes/dashboard/pull/3400?spm=a2c4g.11186623.2.11.34d16d21dGsJMe)  
>-   [https://github.com/kubernetes/dashboard/releases/tag/v1.10.1](https://github.com/kubernetes/dashboard/releases/tag/v1.10.1)  

## 安装步骤<a name="section46701613154319"></a>

1.  在CCE控制台中，单击左侧导航栏的“资源管理  \>  插件管理“，在“插件市场“中，单击dashboard插件下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步”。
3.  单击“安装“。安装完成后，在当前集群的各节点上会安装该插件实例。
4.  回到“插件市场“界面，单击dashboard插件进入详情界面，根据简介中的使用说明完成剩余步骤。

## 权限修改<a name="section10659162018415"></a>

安装Dashboard插件后初始角色的权限较低，若想让Dashboard界面支持更多操作，需自行在后台对RBAC相关资源进行修改。

**具体修改方式：**

可对名为“kubernetes-dashboard-minimal”这个角色中的规则进行调整。当需要集群级别的角色时，要将原本的Role和RoleBinding替换为ClusterRole和ClusterRoleBinding，并按需求配置ClusterRole中的规则。

关于使用RBAC的具体细节可参看文档：[https://kubernetes.io/docs/reference/access-authn-authz/rbac/](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)。

## 升级插件<a name="section455343310401"></a>

1.  在CCE控制台中，单击左侧导航栏的“资源管理 \> 插件管理“，在“插件实例“页签中，单击dashboard下的“ 升级“，如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作；若升级按钮可点击，则点击升级按钮即可升级dashboard插件。升级dashboard插件时，会替换原先节点上的旧版本的dashboard插件，安装最新版本的dashboard插件以实现dashboard功能的快速升级。
2.  在弹出的窗口中，单击“确认“，可升级该插件。

## 卸载插件<a name="section20765191931911"></a>

1.  在CCE控制台中，单击左侧导航栏的“资源管理 \> 插件管理“，在“插件实例“页签中，单击dashboard下的“ 卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

>![](public_sys-resources/icon-notice.gif) **注意：**   
>目前只支持nodeport访问，用户必须绑定EIP才能在浏览器访问，访问方式https://eip:访问端口。  

