# 通过kubectl连接集群<a name="cce_01_0107"></a>

若您需要从客户端机器访问kubernetes集群，可以选择使用kubernetes命令行工具kubectl。

本章以混合集群为例，GPU集群和裸金属集群操作方式与其相同。

## 准备工作<a name="section3271162319436"></a>

CCE支持VPC网络内访问集群和互联网方式访问集群。

-   VPC网络内访问：您需要在“弹性云服务器“控制台购买一台云服务器，并确保和当前集群在同个VPC内。
-   互联网访问：您需要准备一台能连接公网的云服务器。

## 操作步骤<a name="section37321625113110"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“资源管理 \> 集群管理”，单击待连接集群下的“命令行工具 \>  kubectl”。

    **图 1**  单击kubectl<a name="fig118327236614"></a>  
    ![](figures/单击kubectl.png "单击kubectl")

2.  请参照界面中的提示信息完成集群连接。

    **图 2**  通过kubectl连接集群<a name="fig1366811551535"></a>  
    ![](figures/通过kubectl连接集群.png "通过kubectl连接集群")


## 相关操作<a name="section422912118536"></a>

连接集群后，您可以使用Kubernetes管理工作负载，具体请参见[Kubectl使用指南](Kubectl使用指南.md)。

