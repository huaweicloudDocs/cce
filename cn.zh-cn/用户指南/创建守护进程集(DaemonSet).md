# 创建守护进程集\(DaemonSet\)<a name="cce_10_0216"></a>

## 操作场景<a name="section1479811467429"></a>

云容器引擎（CCE）提供多种类型的容器部署和管理能力，支持对容器工作负载的部署、配置、监控、扩容、升级、卸载、服务发现及负载均衡等特性。

其中守护进程集（DaemonSet）可以确保全部（或者某些）节点上仅运行一个Pod实例，当有节点加入集群时，也会为他们新增一个 Pod 。 当有节点从集群移除时，这些Pod也会被回收。删除 DaemonSet 将会删除它创建的所有Pod。

使用DaemonSet的一些典型用法：

-   运行集群存储daemon，例如在每个节点上运行glusterd、ceph。
-   在每个节点上运行日志收集daemon，例如fluentd、logstash。
-   在每个节点上运行监控daemon，例如Prometheus Node Exporter、collectd、Datadog代理、New Relic代理，或Ganglia gmond。

一种简单的用法是为每种类型的守护进程在所有的节点上都启动一个DaemonSet。一个稍微复杂的用法是为同一种守护进程部署多个DaemonSet；每个具有不同的标志， 并且对不同硬件类型具有不同的内存、CPU要求。

## 前提条件<a name="section7271245481"></a>

在创建守护进程集前，您需要存在一个可用集群。若没有可用集群 ，请参照[购买CCE集群](购买CCE集群.md)中内容创建。

## 通过控制台创建<a name="section1160483214207"></a>

1.  登录CCE控制台。
2.  进入集群，在左侧选择“工作负载“，在右上角单击“创建负载“。
3.  配置工作负载的信息。

    **基本信息**

    -   负载类型：选择守护进程DaemonSet。工作负载类型的介绍请参见[工作负载概述](工作负载概述.md)。
    -   负载名称：填写工作负载的名称。
    -   命名空间：选择工作负载的命名空间，默认为default。您可以单击后面的“创建命名空间“，命名空间的详细介绍请参见[创建命名空间](创建命名空间.md)。
    -   容器运行时：CCE集群默认使用普通运行时，CCE Turbo集群可以使用普通运行时或安全运行时。具体区别请参见[安全容器与普通容器](安全容器与普通容器.md)。
    -   时区同步：选择是否开启时区同步。开启后容器与节点使用相同时区（时区同步功能依赖容器中挂载的本地磁盘，请勿修改删除），时区同步详细介绍请参见[时区同步](时区同步.md)。

    **容器配置**

    -   容器信息

        Pod中可以配置多个容器，您可以单击右侧“添加容器“为Pod配置多个容器。

        -   基本信息：[容器基本信息](容器基本信息.md)
        -   生命周期：[设置容器生命周期](设置容器生命周期.md)
        -   健康检查：[设置容器健康检查](设置容器健康检查.md)
        -   环境变量：[设置环境变量](设置环境变量.md)
        -   数据存储：[存储概述](存储概述.md)

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >负载实例数大于1时，不支持挂载云硬盘类型的存储。

        -   安全设置：对容器权限进行设置，保护系统和其他容器不受其影响。请输入用户ID，容器将以当前用户权限运行。
        -   容器日志：[容器日志](容器日志.md)

    -   镜像访问凭证：用于访问镜像仓库的凭证，默认取值为default-secret，使用default-secret可访问SWR镜像仓库的镜像。default-secret详细说明请参见[default-secret](集群系统密钥说明.md#section11760122012591)。
    -   GPU显卡：默认为不限制。当集群中存在GPU节点时，工作负载实例可以调度到指定GPU显卡类型的节点上。

    **服务配置**

    服务（Service）是用来解决Pod访问问题的。每个Service有一个固定IP地址，Service将访问流量转发给Pod，而且Service可以给这些Pod做负载均衡。

    您也可以在创建完工作负载之后再创建Service，Service的概念和使用方法请参见[Service概述](Service概述.md)。

    **高级配置**

    -   升级策略：[工作负载升级配置](工作负载升级配置.md)
    -   调度策略：[调度策略（亲和与反亲和）](调度策略（亲和与反亲和）.md)
    -   标签与注解：[Pod标签与注解](Pod标签与注解.md)
    -   容忍策略：当工作负载实例所在的节点不可用时，系统将实例重新调度到其它可用节点的时间窗。迁移时间窗 \(s\)：请输入时间，默认为300秒。容忍与污点相关，请参见[容忍度（Toleration）](管理节点污点（taint）.md#section2047442210417)。
    -   DNS配置：[工作负载DNS配置说明](工作负载DNS配置说明.md)
    -   性能管理配置：[性能管理配置（性能瓶颈分析）](性能管理配置（性能瓶颈分析）.md)

4.  单击右下角“创建工作负载“。

## 通过kubectl命令行创建<a name="section856819324156"></a>

本节以nginx工作负载为例，说明kubectl命令创建工作负载的方法。

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  创建一个名为nginx-daemonset.yaml的描述文件。其中，nginx-daemonset.yaml为自定义名称，您可以随意命名。

    **vi nginx-daemonset.yaml**

    描述文件内容如下。此处仅为示例，daemonset的详细说明请参见[kubernetes官方文档](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)。

    ```
    apiVersion: apps/v1
    kind: DaemonSet
    metadata:
      name: nginx-daemonset
      labels:
        app: nginx-daemonset
    spec:
      selector:
        matchLabels:
          app: nginx-daemonset
      template:
        metadata:
          labels:
            app: nginx-daemonset
        spec:
          nodeSelector:                 # 节点选择，当节点拥有daemon=need时才在节点上创建Pod
            daemon: need
          containers:
          - name: nginx-daemonset
            image: nginx:alpine
            resources:
              limits:
                cpu: 250m
                memory: 512Mi
              requests:
                cpu: 250m
                memory: 512Mi
          imagePullSecrets:
          - name: default-secret
    ```

    这里可以看出没有Deployment或StatefulSet中的replicas参数，因为是每个节点固定一个。

    Pod模板中有个nodeSelector，指定了只在有“daemon=need“的节点上才创建Pod，如下图所示，DaemonSet只在指定标签的节点上创建Pod。如果需要在每一个节点上创建Pod可以删除该标签。

3.  创建daemonset。

    **kubectl create -f nginx-daemonset.yaml**

    回显如下表示已开始创建daemonset。

    ```
    daemonset.apps/nginx-daemonset created
    ```

4.  查看daemonset状态。

    **kubectl get ds**

    ```
    $ kubectl get ds
    NAME              DESIRED   CURRENT   READY   UP-TO-DATE   AVAILABLE   NODE SELECTOR   AGE
    nginx-daemonset   1         1         0       1            0           daemon=need     116s
    ```

5.  若工作负载需要被访问（集群内访问或节点访问），您需要设置访问方式，具体请参见[网络管理](网络管理.md)创建对应服务。

