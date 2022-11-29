# 创建有状态负载\(StatefulSet\)<a name="cce_10_0048"></a>

## 操作场景<a name="section530452474212"></a>

在运行过程中会保存数据或状态的工作负载称为“有状态工作负载（statefulset）”。例如Mysql，它需要存储产生的新数据。

因为容器可以在不同主机间迁移，所以在宿主机上并不会保存数据，这依赖于CCE提供的高可用存储卷，将存储卷挂载在容器上，从而实现有状态工作负载的数据持久化。

## 约束与限制<a name="section6329175411713"></a>

-   当您删除或扩缩有状态负载时，为保证数据安全，系统并不会删除它所关联的存储卷。
-   当您删除一个有状态负载时，为实现有状态负载中的Pod可以有序停止，请在删除之前将副本数缩容到0。
-   您需要在创建有状态负载的同时，创建一个Headless Service，用于解决有状态负载Pod互相访问的问题，详情请参见[Headless Service](Headless-Service.md)。
-   节点不可用时，Pod状态变为“未就绪“，此时需要手工删除有状态工作负载的Pod，Pod实例才会迁移到正常节点上。

## 前提条件<a name="section1734962819219"></a>

-   在创建容器工作负载前，您需要存在一个可用集群。若没有请参照[购买CCE集群](购买CCE集群.md)中内容创建。
-   若工作负载需要被外网访问，请确保集群中至少有一个节点已绑定弹性IP，或已创建负载均衡实例。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >单个实例（Pod）内如果有多个容器，请确保容器使用的端口不冲突 ，否则部署会失败。


## 通过控制台创建<a name="section16385130102112"></a>

1.  登录CCE控制台。
2.  进入集群，在左侧选择“工作负载“，在右上角单击“创建负载“。
3.  配置工作负载的信息。

    **基本信息**

    -   负载类型：选择有状态工作负载StatefulSet。工作负载类型的介绍请参见[工作负载概述](工作负载概述.md)。
    -   负载名称：填写工作负载的名称。
    -   命名空间：选择工作负载的命名空间，默认为default。您可以单击后面的“创建命名空间“，命名空间的详细介绍请参见[创建命名空间](创建命名空间.md)。
    -   实例数量：填写实例的数量，也就是Pod的数量。
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
            >-   有状态负载不支持挂载已有云硬盘，请使用“动态存储”挂载云硬盘。
            >-   负载创建完成后，动态存储不支持更新。

        -   安全设置：对容器权限进行设置，保护系统和其他容器不受其影响。请输入用户ID，容器将以当前用户权限运行。
        -   容器日志：[容器日志](容器日志.md)

    -   镜像访问凭证：用于访问镜像仓库的凭证，默认取值为default-secret，使用default-secret可访问SWR镜像仓库的镜像。default-secret详细说明请参见[default-secret](集群系统密钥说明.md#section11760122012591)。
    -   GPU显卡：默认为不限制。当集群中存在GPU节点时，工作负载实例可以调度到指定GPU显卡类型的节点上。

    **实例间发现服务配置**

    Headless Service用于解决StatefulSet内Pod互相访问的问题，Headless Service给每个Pod提供固定的访问域名。具体请参见[Headless Service](Headless-Service.md)。

    **服务配置**

    服务（Service）是用来解决Pod访问问题的。每个Service有一个固定IP地址，Service将访问流量转发给Pod，而且Service可以给这些Pod做负载均衡。

    您也可以在创建完工作负载之后再创建Service，Service的概念和使用方法请参见[Service概述](Service概述.md)。

    **高级配置**

    -   升级策略：[工作负载升级配置](工作负载升级配置.md)
    -   调度策略：[调度策略（亲和与反亲和）](调度策略（亲和与反亲和）.md)
    -   实例管理策略（podManagementPolicy）：

        对于某些分布式系统来说，StatefulSet 的顺序性保证是不必要和/或者不应该的。 这些系统仅仅要求唯一性和身份标志。

        -   有序策略：默认实例管理策略，有状态负载会逐个的、按顺序的进行部署、删除、伸缩实例, 只有前一个实例部署Ready或者删除完成后，有状态负载才会操作后一个实例。
        -   并行策略：支持有状态负载并行创建或者删除所有的实例，有状态负载发生变更时立刻在实例上生效。

    -   标签与注解：[Pod标签与注解](Pod标签与注解.md)
    -   DNS配置：[工作负载DNS配置说明](工作负载DNS配置说明.md)
    -   性能管理配置：[性能管理配置（性能瓶颈分析）](性能管理配置（性能瓶颈分析）.md)

4.  单击右下角“创建工作负载“。

## 通过kubectl命令行创建<a name="section113441881214"></a>

本节以etcd为例来进行说明。

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  创建一个名为etcd-statefulset.yaml的文件。

    其中，etcd-statefulset.yaml为自定义名称，您可以随意命名。

    **vi etcd-statefulset.yaml**

    以下内容仅为示例，若需要了解statefulset的详细内容，请参考[kubernetes官方文档](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)。

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: etcd
    spec:
      replicas: 2
      selector:
        matchLabels:
          app: etcd
      serviceName: etcd-svc
      template:
        metadata:
          labels:
            app: etcd
        spec:
          containers:
          - env:
            - name: PAAS_APP_NAME
              value: tesyhhj
            - name: PAAS_NAMESPACE
              value: default
            - name: PAAS_PROJECT_ID
              value: 9632fae707ce4416a0ab1e3e121fe555
            image: etcd    #若使用“开源镜像中心”的镜像，可直接填写镜像名称；若使用“我的镜像”中的镜像，请在SWR中获取具体镜像地址。
            imagePullPolicy: IfNotPresent
            name: container-0
      updateStrategy:
        type: RollingUpdate
    ```

    **vi etcd-headless.yaml**

    ```
    apiVersion: v1
    kind: Service
    metadata:
      labels:
        app: etcd
      name: etcd-svc
    spec:
      clusterIP: None
      ports:
      - name: etcd-svc
        port: 3120
        protocol: TCP
        targetPort: 3120
      selector:
        app: etcd
      sessionAffinity: None
      type: ClusterIP
    ```

3.  创建工作负载以及对应headless服务。

    **kubectl create -f etcd-statefulset.yaml**

    回显如下，表示有状态工作负载（stateful）已创建成功。

    ```
    statefulset.apps/etcd created
    ```

    **kubectl create -f  **etcd-headless**.yaml**

    回显如下，表示对应headless服务已创建成功。

    ```
    service/etcd-svc created
    ```

4.  若工作负载需要被访问（集群内访问或节点访问），您需要设置访问方式，具体请参见[网络管理](网络管理.md)创建对应服务。

