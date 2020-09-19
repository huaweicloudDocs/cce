# 使用kubectl创建文件存储<a name="cce_01_0260"></a>

CCE支持使用PersistentVolumeClaim（PVC）的形式创建文件存储。

1.  请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令。
2.  执行如下命令，配置名为“pvc-sfs-auto-example.yaml“的创建PVC的yaml文件。

    **touch pvc-sfs-auto-example.yaml**

    **vi pvc-sfs-auto-example.yaml**

    -   **1.15及以上版本的集群，yaml文件配置示例如下：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          name:  pvc-sfs-auto-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 10Gi
          storageClassName: csi-nas
        ```

        其中：

        -   storageClassName：k8s storage class名称；使用“csi-nas”。
        -   name：创建的PVC名称。
        -   storage：存储容量，单位为Gi。

    -   **1.13以及之前版本集群，yaml文件配置示例如下：**

        ```
        apiVersion: v1 
        kind: PersistentVolumeClaim 
        metadata: 
          annotations: 
            volume.beta.kubernetes.io/storage-class: nfs-rw
          name: pvc-sfs-auto-example 
          namespace: default 
        spec: 
          accessModes: 
          - ReadWriteMany 
          resources: 
            requests: 
              storage: 10Gi
        ```

        其中：

        -   volume.beta.kubernetes.io/storage-class：文件存储类型，当前支持标准文件协议类型（nfs-rw）。
        -   name：创建的PVC名称。
        -   storage：存储容量，单位为Gi。

3.  执行如下命令创建PVC。

    **kubectl create -f pvc-sfs-auto-example.yaml**

    命令执行完成后会在集群所在VPC内创建一个文件存储，您可以在“存储管理 \> 文件存储卷“中查看该文件系统，也可以在SFS的控制台中查看该文件系统。


