# 通过kubectl配置kube-dns/CoreDNS高可用<a name="cce_01_0162"></a>

通过kubernetes命令行工具来配置kube-dns/CoreDNS的高可用。

kube-dns/CoreDNS为集群提供了DNS服务。若集群中只部署了单个kube-dns/CoreDNS，则存在kube-dns/CoreDNS故障后影响整个集群运作的风险，因此建议为集群配置多个kube-dns/CoreDNS。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   在CCE中新建的kubernetes 1.11及以上版本集群默认会安装CoreDNS插件。
>-   更多DNS相关信息请参见[CoreDNS（系统资源插件，必装）](CoreDNS（系统资源插件-必装）.md)或[Kubernetes集群内置DNS配置说明](Kubernetes集群内置DNS配置说明.md)。

本章以混合集群为例，裸金属集群操作方式与其相同。

## 准备工作<a name="s749b044f6e864a919f0c0616cfad1dab"></a>

集群能够被互联网访问，或集群与客户端机器在同一个VPC下。

## 操作步骤<a name="s6797453bdad1452db7d603668deda069"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“资源管理 \> 集群管理”，单击待连接集群下的“kubectl“。
2.  根据界面提示的步骤设置集群API访问方式。
3.  根据界面提示的步骤配置命令行工具。

    命令行工具配置成功后，可使用命令行工具来手动配置kube-dns/CoreDNS高可用。

4.  登录客户端机器。
5.  编辑kube-dns/CoreDNS的deployment配置文件。

    下面以CoreDNS为例，执行命令如下：

    **kubectl edit deployment coredns -n kube-system**

    修改deployment配置文件中spec字段下的replicas参数为所需的CoreDNS实例数。

    示例：

    ```
    apiVersion: extensions/v1beta1
    kind: Deployment
    metadata:
      annotations:
        deployment.kubernetes.io/revision: "1"
      creationTimestamp: 2019-02-11T09:36:04Z
      generation: 1
      labels:
        app: coredns
        kubernetes-app: coredns
        kubernetes.io/cluster-service: "true"
        kubernetes.io/name: CoreDNS
        release: cceaddon-coredns
      name: coredns
      namespace: kube-system
      resourceVersion: "1927"
      selfLink: /apis/extensions/v1beta1/namespaces/kube-system/deployments/coredns
      uid: 737b9296-2de0-11e9-b629-fa163e7fb882
    spec:
      progressDeadlineSeconds: 600
      replicas: 2
      revisionHistoryLimit: 10
      selector:
        matchLabels:
          app: coredns
          kubernetes-app: coredns
      strategy:
        rollingUpdate:
          maxSurge: 10%
          maxUnavailable: 0
        type: RollingUpdate
      template:
        metadata:
          annotations:
            checksum/config: 3095a9b4028195e7e0b8b22c550bf183d0b7a8a7eba20808b36081d0b39f8b81
    ```


