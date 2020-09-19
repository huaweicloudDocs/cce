# 使用kubectl部署使用对象存储卷的工作负载<a name="cce_01_0269"></a>

1.  执行如下命令，配置名为“obs-pod-example.yaml“的创建Pod的yaml文件。

    **touch obs-pod-example.yaml**

    **vi obs-pod-example.yaml**

    在无状态工作负载中基于pvc共享式使用对象存储示例：

    ```
    apiVersion: extensions/v1beta1 
    kind: Deployment 
    metadata: 
      name: obs-pod-example                        # 工作负载名称
      namespace: default 
    spec: 
      replicas: 1 
      selector: 
        matchLabels: 
          app: obs-pod-example 
      template: 
        metadata: 
          labels: 
            app: obs-pod-example 
        spec: 
          containers: 
          - image: nginx 
            name: container-0 
            volumeMounts: 
            - mountPath: /tmp                       # 挂载路径
              name: pvc-obs-example 
          restartPolicy: Always 
          volumes: 
          - name: pvc-obs-example  
            persistentVolumeClaim: 
              claimName: pvc-obs-auto-example       # PVC名称
    ```

    其中：

    -   name：创建的Pod名称。
    -   app：Pod工作负载名称。
    -   mountPath：容器内挂载路径。
    -   “spec.template.spec.containers.volumeMounts.name”和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

    在有状态工作负载中基于PVCTemplate独占式使用对象存储。

    **1.15及以上版本的集群，yaml文件配置示例：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: deploy-obs-standard-in
      namespace: default
      generation: 1
      labels:
        appgroup: ''
      annotations:
        container.io/container-0: https://console.huaweicloud.com/swr/dockerimage/nginx.png
        description: ''
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: deploy-obs-standard-in
      template:
        metadata:
          labels:
            app: deploy-obs-standard-in
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: 'true'
        spec:
          containers:
            - name: container-0
              image: 'nginx:1.12-alpine-perl'
              env:
                - name: PAAS_APP_NAME
                  value: deploy-obs-standard-in
                - name: PAAS_NAMESPACE
                  value: default
                - name: PAAS_PROJECT_ID
                  value: a2cd8e998dca42e98a41f596c636dbda
              resources: {}
              volumeMounts:
                - name: obs-bs-standard-mountoptionpvc
                  mountPath: /tmp
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
            name: obs-bs-standard-mountoptionpvc
            namespace: default
            annotations:
              everest.io/obs-volume-type: STANDARD
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 1Gi
            storageClassName: csi-obs
      serviceName: wwww
      podManagementPolicy: OrderedReady
      updateStrategy:
        type: RollingUpdate
      revisionHistoryLimit: 10
    ```

    其中:

    -   name：创建的工作负载名称。
    -   image：工作负载的镜像。
    -   mountPath：容器内挂载路径，示例中挂载到“/tmp“路径。

    -   serviceName：工作负载对应的服务，服务创建过程请参见[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)。
    -   “spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

    **1.13及之前版本示例：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    
    metadata:
      name: deploy-obs-standard-in
      namespace: default
      generation: 1
      labels:
        appgroup: ''
      annotations:
        container.io/container-0: https://console.huaweicloud.com/swr/dockerimage/nginx.png
        description: ''
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: deploy-obs-standard-in
      template:
        metadata:
          labels:
            app: deploy-obs-standard-in
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: 'true'
        spec:
          containers:
            - name: container-0
              image: 'nginx:1.12-alpine-perl'
              env:
                - name: PAAS_APP_NAME
                  value: deploy-obs-standard-in
                - name: PAAS_NAMESPACE
                  value: default
                - name: PAAS_PROJECT_ID
                  value: a2cd8e998dca42e98a41f596c636dbda
              resources: {}
              volumeMounts:
                - name: obs-bs-standard-mountoptionpvc
                  mountPath: /tmp
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
            name: obs-bs-standard-mountoptionpvc
            annotations:
              volume.beta.kubernetes.io/storage-class: obs-standard
              volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxiobs
    
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 1Gi
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

    **kubectl create -f obs-pod-example.yaml**

    创建完成后，在CCE界面“存储管理 \> 对象存储卷”中单击PVC名称，在PVC详情页面可查看对象存储服务和PVC的绑定关系。


