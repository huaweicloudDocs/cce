# 创建Windows集群<a name="cce_01_0155"></a>

Windows集群是基于Kubernetes来提供高计算和高网络性能的且运行在Windows操作系统上的容器集群。

CCE当前仅支持在申请Windows容器公测之后才能使用Windows容器功能。

## 使用说明<a name="section17501059161919"></a>

CCE中的Windows集群中的节点需要使用windows server 1709操作系统镜像，该镜像需要提工单申请。申请通过后，CCE技术支持会为您提供该镜像。

获取该基础镜像后，您可以根据业务情况来使用。

-   场景一：若您希望直接使用Windows server 1709基础镜像。

    请基于已获取的基础镜像创建ECS弹性云服务器，并纳管到CCE的Windows集群中。该操作系统镜像中内置了windowsservercore:1709和aspnet:1709基础容器镜像，用户可以基于windowsservercore:1709或aspnet:1709作为基础镜像进行容器化改造业务。

    -   windowsservercore:1709：主要用于开发容器应用。与dockerhub官网使用方法相同，详细请参见[官网文档](https://hub.docker.com/r/microsoft/windowsservercore/)。
    -   aspnet:1709：基于IIS服务开发web类网站应用。与dockerhub官网使用方法相同，详细请参见[官网文档](https://hub.docker.com/r/microsoft/aspnet/ )，使用的镜像版本为microsoft/aspnet:3.5-windowsservercore-1709。

-   场景二：若您希望Windows server 1709操作系统镜像中内置业务所需的容器基础镜像，或者需要其它容器基础镜像如aspnet。

    请基于已获取的基础镜像，重新制作内置业务所需的镜像。并基于制作好的镜像创建ECS弹性云服务器，再纳管到CCE的Windows集群中。基于自定义镜像作为base制作容器镜像。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >微软镜像的base层是链接到微软官方仓库的，因此应用部署时会从微软官方拉取Base镜像，可能将导致应用部署耗时长或失败。  


## 使用约束<a name="section11968551101619"></a>

当前Windows容器处于公测阶段，在使用过程中存在以下限制及约束：

-   当前Windows1709为半年度支持版本，该版本提供18个月的维护期，预计2019年3月份过期。后续支持半年度版本升级。

    Windows操作系统半年度版本升级的过程需要重启操作系统。

    Windows操作系统版本升级后，无法兼容当前容器基础镜像，用户需要重新基于新版本的Windows容器基础镜像重新制作容器，并且全部更新。

-   Windows容器挂载存储时，容器挂载目录需为空目录，否则容器会启动失败。Windows容器中目录不为空时不支持挂载云硬盘。
-   当前Windows上Nano基础镜像100MB，其中.NET版本为.NET Core，如果需要使用老版本.NET，需要采用Windows Server Core 1709基础镜像，当前有3G大小，正在发展中，后续Windows会优化裁剪。
-   Windows 容器编排仅支持Windows版本镜像；
-   Windows集群节点的HNS容器网络启动之后，不支持命令行docker run，docker build等操作。

