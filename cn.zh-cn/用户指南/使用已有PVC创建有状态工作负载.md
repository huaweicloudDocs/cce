# 使用已有PVC创建有状态工作负载<a name="cce_01_0262"></a>

CCE支持使用已有的文件存储（PersistentVolumeClaim），创建有状态工作负载（StatefulSet）**。**

1.  参照[创建文件存储卷](使用文件存储卷.md#section1191025105819)中操作创建文件存储卷，记录文件存储卷名称。
2.  请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令。
3.  新建一个PVC文件，用于创建工作负载。假设文件名为**sfs-statefulset-example**.**yaml**。

    **touch sfs-statefulset-example.yaml**

    **vi sfs-statefulset-example.yaml**

    配置示例：

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: sfs-statefulset-example
      namespace: default
    spec:
      podManagementPolicy: OrderedReady
      replicas: 2
      revisionHistoryLimit: 10
      selector:
        matchLabels:
          app: sfs-statefulset-example
      serviceName: qwqq
      template:
        metadata:
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: "true"
          creationTimestamp: null
          labels:
            app: sfs-statefulset-example
        spec:
          affinity: {}
          containers:
          - env:
            - name: PAAS_APP_NAME
              value: sfs-statefulset-example
            - name: PAAS_NAMESPACE
              value: default
            - name: PAAS_PROJECT_ID
              value: b7bb7d77a2974a8fa8985cbfb63f23c0
            image: nginx:latest
            imagePullPolicy: Always
            name: container-0
            resources: {}
            terminationMessagePath: /dev/termination-log
            terminationMessagePolicy: File
            volumeMounts:
            - mountPath: /tmp
              name: pvc-sfs-example
          dnsPolicy: ClusterFirst
          imagePullSecrets:
          - name: default-secret
          restartPolicy: Always
          schedulerName: default-scheduler
          securityContext: {}
          terminationGracePeriodSeconds: 30
          volumes:
            - name: pvc-sfs-example
              persistentVolumeClaim:
                claimName: cce-sfs-demo
          tolerations:
          - effect: NoExecute
            key: node.kubernetes.io/not-ready
            operator: Exists
            tolerationSeconds: 300
          - effect: NoExecute
            key: node.kubernetes.io/unreachable
            operator: Exists
            tolerationSeconds: 300
      updateStrategy:
        type: RollingUpdate
    ```

    其中：

    -   spec.template.spec.containers.volumeMounts.name和spec.template.spec.volumes.name有映射关系，必须保持一致。
    -   replicas：实例数。
    -   name：新建工作负载的名称。
    -   image：新建工作负载使用的镜像。
    -   mountPath：容器内挂载路径。
    -   serviceName：工作负载对应的服务，服务创建过程请参见[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)。
    -   claimName：已有PVC名称。

4.  创建有状态工作负载。

    **kubectl create -f  sfs-statefulset-example .yaml**


