# 使用已有PVC创建有状态工作负载<a name="cce_01_0273"></a>

CCE支持使用已有的极速文件存储（SFS Turbo），创建有状态工作负载（StatefulSet）**。**

1.  参照创建文件存储卷中操作创建极速文件存储卷，记录极速文件存储卷名称。
2.  请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令。
3.  新建一个文件，用于创建工作负载。假设文件名为**efs-statefulset-example**.**yaml**。

    **touch efs-statefulset-example.yaml**

    **vi efs-statefulset-example.yaml**

    配置示例：

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: efs-statefulset-example
      namespace: default
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: efs-statefulset-example
      template:
        metadata:
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: 'true'
          labels:
            app: efs-statefulset-example
        spec:
          containers:
            - image: 'nginx:1.0.0'
              name: container-0
              resources:
                requests: {}
                limits: {}
              env:
                - name: PAAS_APP_NAME
                  value: efs-statefulset-example
                - name: PAAS_NAMESPACE
                  value: default
                - name: PAAS_PROJECT_ID
                  value: b18296881cc34f929baa8b9e95abf88b
              volumeMounts:
                - name: efs-statefulset-example
                  mountPath: /tmp
                  readOnly: false
                  subPath: ''
          imagePullSecrets:
            - name: default-secret
          terminationGracePeriodSeconds: 30
          volumes:
            - persistentVolumeClaim:
                claimName: cce-efs-import-jnr481gm-3y5o
              name: efs-statefulset-example
          affinity: {}
          tolerations:
            - key: node.kubernetes.io/not-ready
              operator: Exists
              effect: NoExecute
              tolerationSeconds: 300
            - key: node.kubernetes.io/unreachable
              operator: Exists
              effect: NoExecute
              tolerationSeconds: 300
      podManagementPolicy: OrderedReady
      serviceName: test
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

    **kubectl create -f  efs-statefulset-example.yaml**


