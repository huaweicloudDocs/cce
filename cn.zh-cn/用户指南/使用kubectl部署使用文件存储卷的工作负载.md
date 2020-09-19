# 使用kubectl部署使用文件存储卷的工作负载<a name="cce_01_0263"></a>

1.  执行如下命令，配置名为“sfs-pod-example.yaml”的创建Pod的yaml文件。

    **_touch sfs-pod-example.yaml_**

    **_vi sfs-pod-example.yaml_**

    在无状态工作负载中基于pvc共享式使用文件存储示例：

    ```
    apiVersion: extensions/v1beta1 
    kind: Deployment 
    metadata: 
      name: sfs-pod-example                                # 工作负载名称
      namespace: default 
    spec: 
      replicas: 1 
      selector: 
        matchLabels: 
          app: sfs-pod-example 
      template: 
        metadata: 
          labels: 
            app: sfs-pod-example 
        spec: 
          containers: 
          - image: nginx 
            name: container-0 
            volumeMounts: 
            - mountPath: /tmp                                # 挂载路径
              name: pvc-sfs-example 
          restartPolicy: Always 
          volumes: 
          - name: pvc-sfs-example 
            persistentVolumeClaim: 
              claimName: pvc-sfs-auto-example                # 挂载PVC
    ```

    其中：

    -   name：创建的Pod名称。
    -   app：Pod工作负载名称。
    -   mountPath：容器内挂载路径，此处示例中为“/tmp“。
    -   “spec.template.spec.containers.volumeMounts.name” 和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

    在有状态工作负载中基于PVCTemplate独占式使用文件存储：

    **1.15及以上版本的集群，yaml配置示例如下：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: deploy-sfs-nfs-rw-in
      namespace: default
      generation: 1
      labels:
        appgroup: ''
      annotations:
        container.io/container-0: 'https://console.huaweicloud.com/swr/dockerimage/nginx.png'
        description: ''
    spec:
      replicas: 2
      selector:
        matchLabels:
          app: deploy-sfs-nfs-rw-in
      template:
        metadata:
          labels:
            app: deploy-sfs-nfs-rw-in
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: 'true'
        spec:
          containers:
            - name: container-0
              image: 'nginx:1.12-alpine-perl'
              env:
                - name: PAAS_APP_NAME
                  value: deploy-sfs-nfs-rw-in
                - name: PAAS_NAMESPACE
                  value: default
                - name: PAAS_PROJECT_ID
                  value: 8190a2a1692c46f284585c56fc0e2fb9
              resources: {}
              volumeMounts:
                - name: bs-nfs-rw-mountoptionpvc
                  mountPath: /aaa
              terminationMessagePath: /dev/termination-log
              terminationMessagePolicy: File
              imagePullPolicy: IfNotPresent
          restartPolicy: Always
          terminationGracePeriodSeconds: 30
          dnsPolicy: ClusterFirst
          securityContext: {}
          imagePullSecrets:
            - name: default-secret
          affinity: {}
          schedulerName: default-scheduler
      volumeClaimTemplates:
        - metadata:
            name: bs-nfs-rw-mountoptionpvc
            namespace: default
            annotations: {}
            enable: true
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 11Gi
            storageClassName: csi-nas
      serviceName: wwww
      podManagementPolicy: OrderedReady
      updateStrategy:
        type: RollingUpdate
      revisionHistoryLimit: 10
    ```

    其中：

    -   name：创建的工作负载名称。
    -   image：工作负载的镜像。
    -   mountPath：容器内挂载路径，示例中挂载到“/tmp“路径。
    -   serviceName：工作负载对应的服务，服务创建过程请参见[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)。
    -   “spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

    **1.13及之前集群版本示例：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    
    metadata:
      name: deploy-sfs-nfs-rw-in
      namespace: default
      generation: 1
      labels:
        appgroup: ''
      annotations:
        container.io/container-0: 'https://console.huaweicloud.com/swr/dockerimage/nginx.png'
        description: ''
    spec:
      replicas: 2
      selector:
        matchLabels:
          app: deploy-sfs-nfs-rw-in
      template:
        metadata:
          labels:
            app: deploy-sfs-nfs-rw-in
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: 'true'
        spec:
          containers:
            - name: container-0
              image: 'nginx:1.12-alpine-perl'
              env:
                - name: PAAS_APP_NAME
                  value: deploy-sfs-nfs-rw-in
                - name: PAAS_NAMESPACE
                  value: default
                - name: PAAS_PROJECT_ID
                  value: 8190a2a1692c46f284585c56fc0e2fb9
              resources: {}
              volumeMounts:
                - name: bs-nfs-rw-mountoptionpvc
                  mountPath: /aaa
              terminationMessagePath: /dev/termination-log
              terminationMessagePolicy: File
              imagePullPolicy: IfNotPresent
          restartPolicy: Always
          terminationGracePeriodSeconds: 30
          dnsPolicy: ClusterFirst
          securityContext: {}
          imagePullSecrets:
            - name: default-secret
          affinity: {}
          schedulerName: default-scheduler
      volumeClaimTemplates:
        - metadata:
            name: bs-nfs-rw-mountoptionpvc
            creationTimestamp: null
            annotations:
              volume.beta.kubernetes.io/storage-class: nfs-rw
              volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxinfs
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 11Gi
      serviceName: wwww
      podManagementPolicy: OrderedReady
      updateStrategy:
        type: RollingUpdate
      revisionHistoryLimit: 10
    ```

    其中：

    -   name：创建的工作负载名称。
    -   image：工作负载的镜像。
    -   mountPath：容器内挂载路径，示例中挂载到“/tmp“路径。
    -   serviceName：工作负载对应的服务，服务创建过程请参见[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)。
    -   “spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

2.  执行如下命令创建Pod。

    **kubectl create -f sfs-pod-example.yaml**

    创建完成后，登录CCE控制台，在左侧导航栏中选择“存储管理 \> 文件存储卷”。单击PVC名称，在PVC详情页面可查看文件存储服务和PVC的绑定关系。


