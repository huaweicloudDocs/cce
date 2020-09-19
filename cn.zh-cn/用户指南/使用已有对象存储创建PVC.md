# 使用已有对象存储创建PVC<a name="cce_01_0267"></a>

CCE支持使用已有的对象存储来创建PersistentVolume，并通过创建对应PersistentVolumeClaim绑定当前PersistentVolume使用。

1.  登录OBS控制台，创建对象存储桶，记录桶名称和存储类型。
2.  请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令。
3.  新建一个文件，用于创建PV，假设文件名为**pv-obs-example.yaml。**

    **touch pv-obs-example.yaml**

    **vi pv-obs-example.yaml**

    -   **1.15及以上版本的集群，yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolume
        metadata:
          name: pv-obs-example
          annotations:
            pv.kubernetes.io/provisioned-by: everest-csi-provisioner
        spec:
          accessModes:
          - ReadWriteMany
          capacity:
            storage: 1Gi
          csi:
            driver: obs.csi.everest.io
            fsType: s3fs
            volumeAttributes:
              everest.io/obs-volume-type: STANDARD
              everest.io/region: cn-north-7
              storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
            volumeHandle: obs-normal-static-pv
          persistentVolumeReclaimPolicy: Delete
          storageClassName: csi-obs
        ```

        其中：

        -   driver：挂载依赖的存储驱动，对象存储配置为“obs.csi.everest.io”。
        -   everest.io/obs-volume-type：存储类型，包括STANDARD（标准桶）、WARM（低频访问桶）。
        -   everest.io/region：对象存储所在的region。具体请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。
        -   volumeHandle：对象存储的桶名称。

            获取方法：在CCE控制台中，单击左侧栏目树中的“资源管理-存储管理“，在“对象存储卷“页签下单击PVC的名称，在PVC详情页的“PV详情“页签下复制“PV名称“后的内容即可。

        -   storage：存储容量，单位为Gi。此处配置为固定值1Gi。
        -   storageClassName：k8s storage class名称；需配置为"csi-obs”。
        -   fsType：文件类型，支持“obsfs”与“s3fs”,取值为s3fs时创建是obs对象桶，配套使用s3fs挂载；取值为obsfs时创建的是obs并行文件系统，配套使用obsfs挂载，推荐使用。

    -   **1.11及1.13版本集群的yaml文件配置示例：**

        ```
        apiVersion: v1 
        kind: PersistentVolume 
        metadata: 
          name: pv-obs-example 
          annotations:
            pv.kubernetes.io/provisioned-by: flexvolume-huawei.com/fuxiobs
        spec: 
          accessModes: 
          - ReadWriteMany 
          capacity: 
            storage: 1Gi 
          flexVolume: 
            driver: huawei.com/fuxiobs 
            fsType: obs 
            options: 
              fsType: obs 
              region: cn-north-4 
              storage_class: STANDARD 
              volumeID: test-obs 
          persistentVolumeReclaimPolicy: Delete 
          storageClassName: obs-standard
        ```

        其中：

        -   driver：挂载依赖的存储驱动，对象存储配置为“huawei.com/fuxiobs”。
        -   storage\_class：存储类型，包括STANDARD（标准桶）、STANDARD\_IA（低频访问桶）。
        -   region：对象存储所在的region。具体请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。
        -   volumeID：对象存储的桶名称。

            获取方法：在CCE控制台中，单击左侧栏目树中的“资源管理-存储管理“，在“对象存储卷“页签下单击PVC的名称，在PVC详情页的“PV详情“页签下复制“PV名称“后的内容即可。

        -   storage：存储容量，单位为Gi。此处配置为固定值1Gi。
        -   storageClassName：对象存储支持的存储类型，包括obs-standard（标准）、obs-standard-ia（低频）。

    -   **1.9版本集群的yaml文件配置示例：**

        ```
        apiVersion: v1 
        kind: PersistentVolume 
        metadata: 
          name: pv-obs-example 
          namespace: default  
        spec: 
          accessModes: 
          - ReadWriteMany 
          capacity: 
            storage: 1Gi 
          flexVolume: 
            driver: huawei.com/fuxiobs 
            fsType: obs 
            options: 
              fsType: obs 
              kubernetes.io/namespace: default 
              region: cn-north-4 
              storage_class: STANDARD 
              volumeID: test-obs 
          persistentVolumeReclaimPolicy: Delete 
          storageClassName: obs-standard
        ```

        其中：

        -   driver：挂载依赖的存储驱动，对象存储配置为“huawei.com/fuxiobs”。
        -   storage\_class：存储类型，包括STANDARD（标准桶）、STANDARD\_IA（低频访问桶）。
        -   region：对象存储所在的region。具体请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。
        -   volumeID：对象存储的桶名称。

            获取方法：在CCE控制台中，单击左侧栏目树中的“资源管理-存储管理“，在“对象存储卷“页签下单击PVC的名称，在PVC详情页的“PV详情“页签下复制“PV名称“后的内容即可。

        -   storage：存储容量，单位为Gi。此处配置为固定值1Gi。
        -   storageClassName：对象存储支持的存储类型，包括obs-standard（标准）、obs-standard-ia（低频）。

4.  创建PV。

    **kubectl create -f pv-obs-example.yaml**

5.  创建一个yaml文件，用于创建PVC。假设文件名为**pvc-obs-example.yaml**  。

    **touch pvc-obs-example.yaml**

    **vi pvc-obs-example.yaml**

    -   **1.15及以上版本的集群，yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          annotations:
            volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
            everest.io/obs-volume-type: STANDARD
            csi.storage.k8s.io/fstype: s3fs
          name: pvc-obs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 1Gi
          storageClassName: csi-obs
          volumeName: pv-obs-example
        ```

        其中：

        -   volumeName：PV的名称。
        -   storage：存储容量，单位为Gi。此处配置为固定值1Gi，必须和已有pv的storage大小保持一致。
        -   storageClassName：k8s storage class名称；需配置为"csi-obs”。
        -   everest.io/obs-volume-type：obs存储类型；当前支持标准（STANDARD）和低频（WARM）两种存储类型。
        -   csi.storage.k8s.io/fstype：指定文件类型，支持“obsfs”与“s3fs”。取值为s3fs时说明使用的obs对象桶，配套使用s3fs挂载；取值为obsfs时说明使用的是obs并行文件系统，配套使用obsfs挂载。

    -   **1.11及1.13版本集群的yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          annotations:
            volume.beta.kubernetes.io/storage-class: obs-standard
            volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxiobs
          name: pvc-obs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 1Gi
          volumeName: pv-obs-example
        ```

        其中：

        -   volume.beta.kubernetes.io/storage-class：对象存储支持的存储类型，包括obs-standard、obs-standard-ia。
        -   volume.beta.kubernetes.io/storage-provisioner：必须使用flexvolume-huawei.com/fuxiobs。
        -   volumeName：PV的名称。
        -   storage：存储容量，单位为Gi。此处配置为固定值1Gi。

    -   **1.9版本集群的yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          annotations:
            volume.beta.kubernetes.io/storage-class: obs-standard
            volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxiobs
          name: pvc-obs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 1Gi
          volumeName: pv-obs-example
          volumeNamespace: default
        ```

        其中：

        -   volume.beta.kubernetes.io/storage-class：对象存储支持的存储类型，包括obs-standard、obs-standard-ia。
        -   volume.beta.kubernetes.io/storage-provisioner：必须使用flexvolume-huawei.com/fuxiobs。
        -   volumeName：PV的名称。
        -   storage：存储容量，单位为Gi。此处配置为固定值1Gi。

6.  创建PVC。

    **kubectl create -f pvc-obs-example.yaml**


