# 使用kubectl部署使用云硬盘卷的工作负载<a name="cce_01_0257"></a>

云硬盘创建或导入CCE后，可以在工作负载中挂载云硬盘。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>云硬盘不支持跨可用区挂载。在挂载前，您可以使用** kubectl get pvc**  命令查询当前集群所在分区下可用PVC。

1.  执行如下命令，配置名为“evs-pod-example.yaml“的创建Pod的yaml文件。

    **touch evs-pod-example.yaml**

    **vi evs-pod-example.yaml**

    在无状态工作负载中基于pvc共享式使用云硬盘存储示例：

    ```
    apiVersion: extensions/v1beta1 
    kind: Deployment 
    metadata: 
      name: evs-pod-example 
      namespace: default 
    spec: 
      replicas: 1 
      selector: 
        matchLabels: 
          app: evs-pod-example 
      template: 
        metadata: 
          labels: 
            app: evs-pod-example 
        spec: 
          containers: 
          - image: nginx
            name: container-0 
            volumeMounts: 
            - mountPath: /tmp 
              name: pvc-evs-example 
          restartPolicy: Always 
          volumes: 
          - name: pvc-evs-example 
            persistentVolumeClaim: 
              claimName: pvc-evs-auto-example
    ```

    其中：

    -   name：创建的无状态工作负载的名称。
    -   app：Pod工作负载名称。
    -   mountPath：容器内挂载路径，示例中挂载到“/tmp“路径。
    -   claimName：已有PVC名称。
    -   “spec.template.spec.containers.volumeMounts.name ”和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

    在有状态工作负载中基于PVCTemplate独占式使用云硬盘存储示例：

    -   **1.15及以上版本的集群，yaml示例如下：**

        ```
        apiVersion: apps/v1
        kind: StatefulSet
        metadata:
          name: deploy-evs-sata-in
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
              app: deploy-evs-sata-in
              failure-domain.beta.kubernetes.io/region: cn-north-4
              failure-domain.beta.kubernetes.io/zone: cn-north-4a
          template:
            metadata:
              labels:
                app: deploy-evs-sata-in
                failure-domain.beta.kubernetes.io/region: cn-north-4
                failure-domain.beta.kubernetes.io/zone: cn-north-4a
              annotations:
                metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
                pod.alpha.kubernetes.io/initialized: 'true'
            spec:
              containers:
                - name: container-0
                  image: 'nginx:1.12-alpine-perl'
                  env:
                    - name: PAAS_APP_NAME
                      value: deploy-evs-sata-in
                    - name: PAAS_NAMESPACE
                      value: default
                    - name: PAAS_PROJECT_ID
                      value: a2cd8e998dca42e98a41f596c636dbda
                  resources: {}
                  volumeMounts:
                    - name: bs-sata-mountoptionpvc
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
                name: bs-sata-mountoptionpvc
                namespace: default
                annotations:
                  everest.io/disk-volume-type: SATA
              spec:
                accessModes:
                  - ReadWriteOnce
                resources:
                  requests:
                    storage: 10Gi
                storageClassName: csi-disk   
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

    -   **1.13及之前版本，yaml示例如下：**

        ```
        apiVersion: apps/v1
        kind: StatefulSet
        metadata:
          name: deploy-evs-sata-in
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
              app: deploy-evs-sata-in
              failure-domain.beta.kubernetes.io/region: cn-north-4
              failure-domain.beta.kubernetes.io/zone: cn-north-4a
          template:
            metadata:
              labels:
                app: deploy-evs-sata-in
                failure-domain.beta.kubernetes.io/region: cn-north-4
                failure-domain.beta.kubernetes.io/zone: cn-north-4a
              annotations:
                metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
                pod.alpha.kubernetes.io/initialized: 'true'
            spec:
              containers:
                - name: container-0
                  image: 'nginx:1.12-alpine-perl'
                  env:
                    - name: PAAS_APP_NAME
                      value: deploy-evs-sata-in
                    - name: PAAS_NAMESPACE
                      value: default
                    - name: PAAS_PROJECT_ID
                      value: a2cd8e998dca42e98a41f596c636dbda
                  resources: {}
                  volumeMounts:
                    - name: bs-sata-mountoptionpvc
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
                name: bs-sata-mountoptionpvc
                annotations:
                  volume.beta.kubernetes.io/storage-class: sata
                  volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxivol
        
              spec:
                accessModes:
                  - ReadWriteMany
                resources:
                  requests:
                    storage: 10Gi
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

    **kubectl create -f evs-pod-example.yaml**

    创建完成后，登录CCE控制台，在左侧导航栏中选择“存储管理 \> 云硬盘存储卷“。单击PVC名称，在PVC详情页面可查看云硬盘和PVC的绑定关系。


