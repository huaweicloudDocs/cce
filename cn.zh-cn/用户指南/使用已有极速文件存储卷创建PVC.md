# 使用已有极速文件存储卷创建PVC<a name="cce_01_0272"></a>

CCE支持使用已有的极速文件存储来创建PersistentVolume，创建成功后，通过创建相应的PersistentVolumeClaim来绑定当前的PersistentVolume使用。

1.  登录SFS控制台，创建一个文件存储，记录文件存储的ID、共享路径和容量。
2.  请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令。
3.  新建一个yaml文件，用于创建PersistentVolume。假设文件名为**pv-efs-example.yaml**。

    **touch pv-efs-example.yaml**

    **vi pv-efs-example.yaml**

    -   **1.15及以上版本集群，yaml文件配置示例如下：**

        ```
        apiVersion: v1
        kind: PersistentVolume
        metadata:
          name: pv-efs-example
          annotations:
            pv.kubernetes.io/provisioned-by: everest-csi-provisioner
        spec:
          accessModes:
          - ReadWriteMany
          capacity:
            storage: 10Gi
          csi:
            driver: sfsturbo.csi.everest.io
            fsType: nfs
            volumeAttributes:
              everest.io/share-export-location: 192.168.0.169:/
              storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
            volumeHandle: 8962a2a2-a583-4b7f-bb74-fe76712d8414
          persistentVolumeReclaimPolicy: Delete
          storageClassName: csi-sfsturbo
        ```

        其中：

        -   driver：挂载依赖的存储驱动，极速文件存储配置为“sfsturbo.csi.everest.io”。
        -   everest.io/share-export-location：极速文件存储的共享路径。
        -   volumeHandle：极速文件存储的ID。

            获取方法：在CCE控制台中，单击左侧栏目树中的“资源管理-存储管理“，在“极速文件存储卷“页签下单击PVC的名称，在PVC详情页中复制“PVC UID“后的内容即可。

        -   storage：文件存储的大小。
        -   storageClassName：指定k8s storage class名称；极速文件存储卷需配置为"csi-sfsturbo”。

    -   **1.13及之前版本集群，yaml文件配置示例如下：**

        ```
        apiVersion: v1 
        kind: PersistentVolume 
        metadata: 
          name: pv-efs-example 
          annotations:
            pv.kubernetes.io/provisioned-by: flexvolume-huawei.com/fuxiefs
        spec: 
          accessModes: 
          - ReadWriteMany 
          capacity: 
            storage: 100Gi 
          flexVolume: 
            driver: huawei.com/fuxiefs 
            fsType: efs 
            options: 
              deviceMountPath: 192.168.0.169:/ 
              fsType: efs 
              volumeID: 8962a2a2-a583-4b7f-bb74-fe76712d8414 
          persistentVolumeReclaimPolicy: Delete 
          storageClassName: efs-standard
        ```

        其中：

        -   driver：挂载依赖的存储驱动，极速文件存储配置为“huawei.com/fuxiefs”。
        -   deviceMountPath：极速文件存储的共享路径。
        -   volumeID：极速文件存储的ID。

            获取方法：在CCE控制台中，单击左侧栏目树中的“资源管理-存储管理“，在“极速文件存储卷“页签下单击PVC的名称，在PVC详情页中复制“PVC UID“后的内容即可。

        -   storage：文件存储的大小。
        -   storageClassName：极速文件存储支持的卷类型，当前支持efs-standard、efs-performance（目前SFS Turbo不支持动态创建，所以此参数后续没有使用）。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >极速文件存储所在VPC，子网必须与工作负载规划部署的ECS虚拟机的VPC保持一致，安全组开放入方向端口\(111、445、2049、2051、20048\)。

4.  创建PV。

    **kubectl create -f pv-efs-example.yaml**

5.  新建一个yaml文件，用于创建PVC。假设文件名为**pvc-efs-example.yaml**。

    **touch pvc-efs-example.yaml**

    **vi pvc-efs-example.yaml**

    -   **1.15及以上版本集群，yaml文件配置示例如下：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          annotations:
            volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
          name: pvc-efs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 10Gi
          storageClassName: csi-sfsturbo
          volumeName: pv-efs-example
        ```

        其中：

        -   storageClassName：指定k8s storage class名称；需配置为"csi-sfsturbo”。
        -   storage：存储容量，单位Gi，必须和已有pv的storage大小保持一致。
        -   volumeName：PV的名称。

    -   **1.13及之前版本集群，yaml文件配置示例如下：**

        ```
        apiVersion: v1 
        kind: PersistentVolumeClaim 
        metadata: 
          annotations: 
            volume.beta.kubernetes.io/storage-class: efs-standard 
            volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxiefs 
          name: pvc-efs-example 
          namespace: default 
        spec: 
          accessModes: 
          - ReadWriteMany 
          resources: 
            requests: 
              storage: 100Gi 
          volumeName: pv-efs-example
        ```

        其中：

        -   volume.beta.kubernetes.io/storage-class：文件存储支持的读写方式，支持efs-standard、efs-performance。必须和已有PV保持一致。
        -   volume.beta.kubernetes.io/storage-provisioner：必须使用flexvolume-huawei.com/fuxiefs。
        -   storage：存储容量，单位Gi，必须和已有pv的storage大小保持一致。
        -   volumeName：PV的名称。

6.  创建PVC。

    **kubectl create -f pvc-efs-example.yaml**


