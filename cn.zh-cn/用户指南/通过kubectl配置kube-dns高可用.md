# 通过kubectl配置kube-dns高可用<a name="cce_01_0162"></a>

通过kubernetes命令行工具来配置kube-dns的高可用。

kube-dns为集群提供了DNS服务。若集群中只部署了单个kube-dns，则存在kube-dns故障后影响整个集群运作的风险，因此建议为集群配置多个kube-dns。

本章以虚拟机集群为例，裸金属集群操作方式与其相同。

## 前提条件<a name="s749b044f6e864a919f0c0616cfad1dab"></a>

集群能够被互联网访问，或集群与客户端机器在同一个VPC下。

## 操作步骤<a name="s6797453bdad1452db7d603668deda069"></a>

1.  登录CCE控制台，选择“资源管理 \> 集群管理”，单击待连接集群下的“kubectl“。
2.  根据界面提示的步骤设置集群API访问方式。
3.  根据界面提示的步骤配置命令行工具。

    命令行工具配置成功后，可使用命令行工具来手动配置kube-dns高可用。

4.  登录客户端机器。
5.  编辑kube-dns的deployment配置文件。

    **kubectl edit deployment kube-dns -n kube-system**

    修改deployment配置文件中spec字段下的replicas参数为所需的kube-dns实例数。

    示例：

    ```
    apiVersion: extensions/v1beta1
    kind: Deployment
    metadata:
      annotations:
        deployment.kubernetes.io/revision: "1"
      creationTimestamp: 2018-03-27T13:58:35Z
      enable: true
      generation: 1
      labels:
        addonmanager.kubernetes.io/mode: Reconcile
        k8s-app: kube-dns
        kubernetes.io/cluster-service: "true"
        kubernetes.io/lock: "true"
      name: kube-dns
      namespace: kube-system
      resourceVersion: "211"
      selfLink: /apis/extensions/v1beta1/namespaces/kube-system/deployments/kube-dns
      uid: f168e8c8-31c6-11e8-954c-fa163e673ffd
    spec:
      replicas: 1
      selector:
        matchLabels:
          k8s-app: kube-dns
      strategy:
        rollingUpdate:
          maxSurge: 10%
          maxUnavailable: 0
        type: RollingUpdate
      template:
        ......
    ```


