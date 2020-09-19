# 使用kubectl创建云硬盘<a name="cce_01_0255"></a>

CCE支持使用PersistentVolumeClaim（PVC）的形式创建云硬盘。

1.  请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令。
2.  执行如下命令，配置名为“pvc-evs-auto-example.yaml”的创建PVC的yaml文件。

    **touch pvc-evs-auto-example.yaml**

    **vi pvc-evs-auto-example.yaml**

    -   **1.15及以上版本的集群，yaml文件配置示例如下：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          name: pvc-evs-auto-example
          namespace: default
          annotations:
            everest.io/disk-volume-type: SATA
          labels:
            failure-domain.beta.kubernetes.io/region: cn-north-4
            failure-domain.beta.kubernetes.io/zone: cn-north-4a
        spec:
          accessModes:
          - ReadWriteOnce
          resources:
            requests:
              storage: 10Gi
          storageClassName: csi-disk
        ```

        其中：

        -   everest.io/disk-volume-type：云硬盘类型，全大写；当前支持高I/O（SAS）、超高I/O（SSD）和普通I/O（SATA）。
        -   failure-domain.beta.kubernetes.io/region：集群所在的region。Region对应的值请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。
        -   failure-domain.beta.kubernetes.io/zone：创建云硬盘所在的可用区，必须和工作负载规划的可用区保持一致。zone对应的值请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。
        -   storage：存储容量，单位为Gi。
        -   storageClassName：存储卷动态供应关联的k8s storage class名称；v1.15集群使用的csi关联的storage class名称是csi-disk
        -   accessModes:  指定读写模式，1.15集群版本只支持非共享卷，此字段设置为“ReadWriteOnce”。

    -   **1.15之前的1.9、1.11、1.13版本集群，yaml文件配置示例如下：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          name: pvc-evs-auto-example
          namespace: default
          annotations:
            volume.beta.kubernetes.io/storage-class: sata
          labels:
            failure-domain.beta.kubernetes.io/region: cn-north-4
            failure-domain.beta.kubernetes.io/zone: cn-north-4a
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 10Gi
        ```

        其中：

        -   volume.beta.kubernetes.io/storage-class：云硬盘类型，当前支持高I/O（sas）、超高I/O（ssd）和普通I/O（sata）。
        -   failure-domain.beta.kubernetes.io/region：集群所在的region。Region对应的值请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。
        -   failure-domain.beta.kubernetes.io/zone：创建云硬盘所在的可用区，必须和工作负载规划的可用区保持一致。zone对应的值请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。
        -   storage：存储容量，单位为Gi。
        -   accessModes:  指定读写模式，支持配置“ReadWriteMany”（共享卷）与“ReadWriteOnly”（非共享卷）。

3.  执行如下命令创建PVC。

    **kubectl create -f pvc-evs-auto-example.yaml**

    命令执行完成后，会在集群所在分区创建EVS云硬盘，您可以在“存储管理 \> 云硬盘存储卷“中查看该云硬盘，也可以在EVS的控制台中根据卷名称查看该硬盘。


