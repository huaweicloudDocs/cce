# 使用kubectl创建对象存储<a name="cce_01_0266"></a>

动态使用OBS云硬盘可以自动创建并挂载所期望的OBS对象存储，目前支持标准、低频两种类型的桶，分别对应obs-standard、obs-standard-ia。

1.  请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)连接集群配置kubectl命令。
2.  执行如下命令，配置名为“pvc-obs-auto-example.yaml”的创建PVC的yaml文件。

    **_touch pvc-obs-auto-example.yaml_**

    **_vi pvc-obs-auto-example.yaml_**

    **1.15及以上版本的集群，yaml配置示例如下：**

    ```
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      annotations:
        everest.io/obs-volume-type: STANDARD
        csi.storage.k8s.io/fstype: s3fs
      name: obs-warm-provision-pvc
      namespace: default
    spec:
      accessModes:
      - ReadWriteMany
      resources:
        requests:
          storage: 1Gi
      storageClassName: csi-obs
    ```

    其中：

    -   everest.io/obs-volume-type：桶类型，当前支持标准（STANDARD）和低频（WARM）两种桶。
    -   name：创建的PVC名称。
    -   storage：存储容量，单位为Gi，对OBS桶来说，此处仅为校验需要（不能为空和0），设置的大小不起作用，此处设定为固定值1Gi。
    -   csi.storage.k8s.io/fstype：文件类型，支持“obsfs”与“s3fs”,取值为s3fs时创建是obs对象桶，配套使用s3fs挂载；取值为obsfs时创建的是obs并行文件系统，配套使用obsfs挂载，推荐使用。

    **1.13及之前版本的集群，yaml示例如下：**

    ```
    apiVersion: v1 
    kind: PersistentVolumeClaim 
    metadata: 
      annotations: 
        volume.beta.kubernetes.io/storage-class: obs-standard                         # 对象存储桶类型，当前支持标准（obs-standard）和低频（obs-standard-ia）
    
      name: pvc-obs-auto-example                                                      # PVC名称
      namespace: default 
    spec: 
      accessModes: 
      - ReadWriteMany 
      resources: 
        requests: 
          storage: 1Gi              # 存储容量，单位为Gi，对OBS桶来说，此处仅为校验需要（不能为空和0），设置的大小不起作用，此处设定为固定值1Gi
    ```

    其中：

    -   volume.beta.kubernetes.io/storage-class：桶类型，当前支持标准（obs-standard）和低频（obs-standard-ia）两种桶。
    -   name：创建的PVC名称。
    -   storage：存储容量，单位为Gi，对OBS桶来说，此处仅为校验需要（不能为空和0），设置的大小不起作用，此处设定为固定值1Gi。

3.  执行如下命令创建PVC。

    **kubectl create -f pvc-obs-auto-example.yaml**

    命令执行完成后会在集群所在VPC内创建一个对象存储桶，您可以在“存储管理 \> 对象存储卷“中单击桶名称查看该桶，也可以在OBS的控制台中查看该桶。


