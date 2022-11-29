# Dashboard<a name="cce_10_0128"></a>

## 插件简介<a name="section1418513434428"></a>

Kubernetes Dashboard是一个旨在为Kubernetes世界带来通用监控和操作Web界面的项目，集合了命令行可以操作的所有命令。

使用Kubernetes Dashboard，您可以：

-   向Kubernetes集群部署容器化应用
-   诊断容器化应用的问题
-   管理集群的资源
-   查看集群上所运行的应用程序
-   创建、修改Kubernetes上的资源（例如Deployment、Job、DaemonSet等）
-   展示集群上发生的错误

例如：您可以伸缩一个Deployment、执行滚动更新、重启一个Pod或部署一个新的应用程序。

**开源社区地址：**[https://github.com/kubernetes/dashboard](https://github.com/kubernetes/dashboard)

>![](public_sys-resources/icon-note.gif) **说明：** 
>当前CCE提供的Dashboard插件已将对应镜像升级到最新版本，不受Kubernetes Dashboard漏洞CVE-2018-18264影响。
>安全漏洞CVE-2018-18264的详细信息，请参考：
>-   [https://github.com/kubernetes/dashboard/pull/3289](https://github.com/kubernetes/dashboard/pull/3289?spm=a2c4g.11186623.2.10.34d16d21dGsJMe)
>-   [https://github.com/kubernetes/dashboard/pull/3400](https://github.com/kubernetes/dashboard/pull/3400?spm=a2c4g.11186623.2.11.34d16d21dGsJMe)
>-   [https://github.com/kubernetes/dashboard/releases/tag/v1.10.1](https://github.com/kubernetes/dashboard/releases/tag/v1.10.1)

## 安装步骤<a name="section46701613154319"></a>

1.  登录CCE控制台，进入集群，单击左侧导航栏的“插件管理“，在右侧找到**dashboard**，单击“安装“。
2.  在规格配置页面，配置以下参数。
    -   证书配置：dashboard服务端使用的证书。
        -   使用自定义证书。
            -   证书文件：单击![](figures/zh-cn_image_0000001244141149.png)查看证书文件样例参考。
            -   证书私钥：单击![](figures/zh-cn_image_0000001199341260.png)查看证书私钥样例参考。

        -   使用默认证书。

            >![](public_sys-resources/icon-notice.gif) **须知：** 
            >dashboard默认生成的证书不合法，将影响浏览器正常访问，建议您选择手动上传合法证书，以便通过浏览器校验，保证连接的安全性。


3.  单击“安装“。

## 访问dashboard<a name="section15288141117362"></a>

1.  登录CCE控制台，进入集群，单击左侧导航栏的“插件管理“，确认dashboard插件状态为“运行中“后，单击“访问“。
2.  在CCE控制台弹出的窗口中复制token。
3.  在登录页面中选择“令牌”的登录方式，粘贴输入复制的token，单击“登录“按钮。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >本插件默认不支持使用证书认证的kubeconfig进行登录，推荐使用令牌方式登录。详细信息请参考：[https://github.com/kubernetes/dashboard/issues/2474\#issuecomment-348912376](https://github.com/kubernetes/dashboard/issues/2474#issuecomment-348912376)

    **图 1**  令牌方式登录<a name="fig2040714531230"></a>  
    ![](figures/令牌方式登录.png "令牌方式登录")

4.  登录后效果，如[图2](#fig12780143011555)。

    **图 2**  Dashboard概览页<a name="fig12780143011555"></a>  
    ![](figures/Dashboard概览页.png "Dashboard概览页")


## 权限修改<a name="section10659162018415"></a>

安装Dashboard插件后初始角色仅拥有对大部分资源的只读权限，若想让Dashboard界面支持更多操作，需自行在后台对RBAC相关资源进行修改。

**具体修改方式：**

可对名为“kubernetes-dashboard-minimal”这个ClusterRole中的规则进行调整。

关于使用RBAC的具体细节可参看文档：[https://kubernetes.io/docs/reference/access-authn-authz/rbac/](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)。

## 附：访问报错解决方法<a name="section913875232612"></a>

使用Chrome浏览器访问时，会出现如下“ERR\_CERT\_INVALID”的报错导致无法正常进入登录界面，原因是dashboard默认生成的证书未通过Chrome校验，当前有以下两种解决方式：

**图 3**  Chrome浏览器报错信息<a name="fig1873703218416"></a>  
![](figures/Chrome浏览器报错信息.png "Chrome浏览器报错信息")

-   方式一：使用火狐浏览器访问链接，为当前地址添加“例外”后即可进入登录页面。
-   方式二：通过启动Chrome时添加“--ignore-certificate-errors”开关忽略证书报错。

    Windows：保存链接地址，关闭所有已经打开的Chrome浏览器窗口，Windows键 +“R”弹出“运行”对话框，输入“chrome --ignore-certificate-errors”启动新的chrome窗口，输入地址进入登录界面。


