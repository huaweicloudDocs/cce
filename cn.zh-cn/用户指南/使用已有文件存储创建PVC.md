# 使用已有文件存储创建PVC<a name="cce_01_0261"></a>

CCE支持使用已有的文件存储来创建PersistentVolume，创建成功后，通过创建相应的PersistentVolumeClaim来绑定当前的PersistentVolume使用。

1.  登录SFS控制台，创建一个文件存储，记录文件存储的ID、共享路径和容量。
2.  请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令。
3.  新建一个yaml文件，用于创建PersistentVolume。假设文件名为**pv-sfs-example.yaml**。

    **touch pv-sfs-example.yaml**

    **vi pv-sfs-example.yaml**

    -   **1.15及以上版本的集群，yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolume
        metadata:
          name: pv-sfs-example
          annotations:
            pv.kubernetes.io/provisioned-by: everest-csi-provisioner
        spec:
          accessModes:
          - ReadWriteMany
          capacity:
            storage: 10Gi
          csi:
            driver: nas.csi.everest.io
            fsType: nfs
            volumeAttributes:
              everest.io/share-export-location: sfs-nas01.cn-north-4.myhuaweicloud.com:/share-436304e8
              storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
            volumeHandle: 682f00bb-ace0-41d8-9b3e-913c9aa6b695
          persistentVolumeReclaimPolicy: Delete
          storageClassName: csi-nas
        ```

        其中：

        -   driver：挂载依赖的存储驱动，文件存储配置为“nas.csi.everest.io”。
        -   everest.io/share-export-location：文件存储的共享路径。

            获取方法：在CCE控制台中，单击顶部的“服务列表 \> 存储 \> 弹性文件服务“，在弹性文件服务列表中可以看到“挂载地址“列，即为文件存储的共享路径，如[图1](#fig9360194915556)。

        -   volumeHandle：文件存储的ID。

            获取方法：在CCE控制台中，单击顶部的“服务列表 \> 存储 \> 弹性文件服务“，在弹性文件服务列表中单击对应的弹性文件服务名称，在详情页中复制“ID“后的内容即可。

        -   storage：文件存储的大小。
        -   storageClassName：k8s storage class名称；需配置为"csi-nas"。

    -   **1.11及1.13版本集群，yaml文件配置示例：**

        ```
        apiVersion: v1 
        kind: PersistentVolume 
        metadata: 
          name: pv-sfs-example 
          annotations:
            pv.kubernetes.io/provisioned-by: flexvolume-huawei.com/fuxinfs
        spec: 
          accessModes: 
          - ReadWriteMany 
          capacity: 
            storage: 10Gi 
          flexVolume: 
            driver: huawei.com/fuxinfs 
            fsType: nfs 
            options: 
              deviceMountPath: sfs-nas1.southchina.huaweicloud.com:/share-73bdfafd
              fsType: nfs 
              volumeID: f6976f9e-2493-419b-97ca-d7816008d91c 
          persistentVolumeReclaimPolicy: Delete 
          storageClassName: nfs-rw
        ```

        其中：

        -   driver：挂载依赖的存储驱动，文件存储配置为“huawei.com/fuxinfs”。
        -   deviceMountPath：文件存储的共享路径。

            获取方法：在CCE控制台中，单击顶部的“服务列表 \> 存储 \> 弹性文件服务“，在弹性文件服务列表中可以看到“挂载地址“列，即为文件存储的共享路径，如[图1](#fig9360194915556)。

        -   volumeID：文件存储的ID。

            获取方法：在CCE控制台中，单击左侧栏目树中的“资源管理-存储管理“，在“文件存储卷“页签下单击PVC的名称，在PVC详情页中复制“PVC UID“后的内容即可。

        -   storage：文件存储的大小。
        -   storageClassName：文件存储支持的读写方式，当前支持nfs-rw、nfs-ro。

    -   **1.9版本集群的yaml文件配置示例：**

        ```
        apiVersion: v1 
        kind: PersistentVolume 
        metadata: 
          name: pv-sfs-example 
          namespace: default 
        spec: 
          accessModes: 
          - ReadWriteMany 
          capacity: 
            storage: 10Gi 
          flexVolume: 
            driver: huawei.com/fuxinfs 
            fsType: nfs 
            options: 
              deviceMountPath: sfs-nas1.southchina.huaweicloud.com:/share-73bdfafd
              fsType: nfs 
              kubernetes.io/namespace: default 
              volumeID: f6976f9e-2493-419b-97ca-d7816008d91c 
          persistentVolumeReclaimPolicy: Delete 
          storageClassName: nfs-rw
        ```

        其中：

        -   driver：挂载依赖的存储驱动，文件存储配置为“huawei.com/fuxinfs”。
        -   deviceMountPath：文件存储的共享路径。

            获取方法：在CCE控制台中，单击顶部的“服务列表 \> 存储 \> 弹性文件服务“，在弹性文件服务列表中可以看到“挂载地址“列，即为文件存储的共享路径，如[图1](#fig9360194915556)。

        -   volumeID：文件存储的ID。

            获取方法：在CCE控制台中，单击左侧栏目树中的“资源管理-存储管理“，在“文件存储卷“页签下单击PVC的名称，在PVC详情页中复制“PVC UID“后的内容即可。

        -   storage：文件存储的大小。
        -   storageClassName：文件存储支持的读写方式，当前支持nfs-rw、nfs-ro。

    **图 1**  弹性文件存储-共享路径<a name="fig9360194915556"></a>  
    ![](figures/弹性文件存储-共享路径.png "弹性文件存储-共享路径")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >文件存储所在VPC必须与工作负载规划部署的ECS虚拟机的VPC保持一致。

4.  创建PV。

    **kubectl create -f pv-sfs-example.yaml**

5.  新建一个yaml文件，用于创建PVC。假设文件名为**pvc-sfs-example.yaml**。

    **touch pvc-sfs-example.yaml**

    **vi pvc-sfs-example.yaml**

    -   **1.15及以上版本的集群，yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          annotations:
            volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
          name: pvc-sfs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 10Gi
          storageClassName: csi-nas
          volumeName: pv-sfs-example
        ```

        其中：

        -   storageClassName：需配置为"csi-nas"。必须和已有PV保持一致。
        -   storage：存储容量，单位Gi，必须和已有pv的storage大小保持一致。
        -   volumeName：PV的名称。

    -   **1.11及1.13版本集群，yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          annotations:
            volume.beta.kubernetes.io/storage-class: nfs-rw
            volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxinfs
          name: pvc-sfs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 10Gi
          volumeName: pv-sfs-example
        ```

        其中：

        -   volume.beta.kubernetes.io/storage-class：文件存储支持的读写方式，支持nfs-rw 、nfs-ro。必须和已有PV保持一致。
        -   volume.beta.kubernetes.io/storage-provisioner：必须使用flexvolume-huawei.com/fuxinfs。
        -   storage：存储容量，单位Gi，必须和已有pv的storage大小保持一致。
        -   volumeName：PV的名称。

    -   **1.9版本集群的yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          annotations:
            volume.beta.kubernetes.io/storage-class: nfs-rw
            volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxinfs
          name: pvc-sfs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 10Gi
          volumeName: pv-sfs-example
          volumeNamespace: default
        ```

        其中：

        -   volume.beta.kubernetes.io/storage-class：文件存储支持的读写方式，支持nfs-rw 、nfs-ro。必须和已有PV保持一致。
        -   volume.beta.kubernetes.io/storage-provisioner：必须使用flexvolume-huawei.com/fuxinfs。
        -   storage：存储容量，单位Gi，必须和已有pv的storage大小保持一致。
        -   volumeName：PV的名称。

6.  创建PVC。

    **kubectl create -f pvc-sfs-example.yaml**


