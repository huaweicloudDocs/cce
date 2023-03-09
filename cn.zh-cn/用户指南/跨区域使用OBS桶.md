# 跨区域使用OBS桶<a name="cce_10_0392"></a>

默认情况下，Pod仅支持使用同一个区域（Region）的OBS桶。CCE支持工作负载使用其他区域的OBS桶，在某些场景下有利于提升OBS桶的资源利用率，但跨区域使用OBS相比同区域访问时延波动要更大。

## 约束与限制<a name="section1951334317186"></a>

-   当前支持在1.15及1.19版本的CCE集群中跨区域使用OBS。
-   Everest插件版本要求**1.2.32及以上**版本。
-   挂载存储的节点必须能够访问OBS桶，跨区域通常使用公网或专线打通。您可以在需要使用OBS的节点上Ping OBS的Endpoint来确定是否能够访问。
-   仅支持PV跨区域使用OBS桶，然后再使用PVC绑定PV，且PV回收策略必须为Retain。不支持使用StorageClass动态创建PVC跨区域使用OBS桶。

## 操作步骤<a name="section8729120144219"></a>

1.  创建名为paas-obs-endpoint的配置项，配置OBS所在区域和Endpoint。

    配置项名称固定为paas-obs-endpoint，命名空间固定为kube-system。

    区域名称和Endpoint以键值对形式对应，<region\_name\>和<endpoint\_address\>需替换为具体值，具体取值请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)，多个取值间使用逗号隔开。

    例如\{"cn-south-4": "https://obs.cn-south-4.myhuaweicloud.com:443", "cn-north-4": "https://obs.cn-north-4.myhuaweicloud.com:443"\}

    ```
    apiVersion: v1
    kind: ConfigMap
    metadata:
      name: paas-obs-endpoint   # 名称必须为paas-obs-endpoint
      namespace: kube-system    # 必须在kube-system命名空间下
    data:
      obs-endpoint: |
        {"<region_name>": "<endpoint_address>"}
    ```

2.  创建PV。

    如下所示，everest.io/region填入对应的OBS存储所在的region。

    ```
    kind: PersistentVolume
    apiVersion: v1
    metadata:
      name: testing-abc
      annotations:
        pv.kubernetes.io/bound-by-controller: 'yes'
        pv.kubernetes.io/provisioned-by: everest-csi-provisioner
    spec:
      capacity:
        storage: 1Gi
      csi:
        driver: obs.csi.everest.io
        volumeHandle: testing-abc             # OBS桶的名称
        fsType: s3fs                          # obsfs表示创建并行文件系统，推荐使用；s3fs表示创建对象桶
        volumeAttributes:
          everest.io/obs-volume-type: STANDARD
          everest.io/region: <region_name>       # OBS桶所在区域，需替换为具体取值
          storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
        nodePublishSecretRef:                 # 挂载OBS桶使用的AK/SK
          name: test-user
          namespace: default
      accessModes:
        - ReadWriteMany
      persistentVolumeReclaimPolicy: Retain   # PV回收策略必须为Retain
      storageClassName: csi-obs
      volumeMode: Filesystem
    ```

    nodePublishSecretRef为对象存储卷挂载使用的访问密钥（AK/SK），您需要使用AK/SK创建一个Secret，在创建PV时使用。详细说明请参见[对象存储卷挂载设置自定义访问密钥（AK/SK）](对象存储卷挂载设置自定义访问密钥（AK-SK）.md)。

3.  创建PVC。

    ```
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      name: pvc-test-abc
      namespace: default
      annotations:
        everest.io/obs-volume-type: STANDARD                         # 桶类型，当前支持标准（STANDARD）和低频（WARM）两种桶。
        csi.storage.k8s.io/fstype: s3fs                              # 文件类型，obsfs表示创建并行文件系统，推荐使用；s3fs表示创建对象桶
        volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
    spec:
      accessModes:
      - ReadWriteMany             # 对象存储必须为ReadWriteMany
      resources:
        requests:
          storage: 1Gi            # PVC申请容量大小，此处仅为校验需要（不能为空和0），设置的大小不起作用，此处设定为固定值1Gi
      storageClassName: csi-obs   # StorageClass的名称，对象存储为csi-obs
      volumeName: testing-abc     # PV的名称
    ```

4.  创建工作负载，并在容器配置中的数据存储选项中选择存储卷声明PVC，添加上述创建的PVC，如果工作负载能够正常创建成功，则说明可以跨区域使用OBS桶。

    ```
    apiVersion: apps/v1 
    kind: Deployment 
    metadata: 
      name: obs-deployment-example                        # 工作负载名称
      namespace: default 
    spec: 
      replicas: 1 
      selector: 
        matchLabels: 
          app: obs-deployment-example 
      template: 
        metadata: 
          labels: 
            app: obs-deployment-example 
        spec: 
          containers: 
          - image: nginx
            name: container-0 
            volumeMounts: 
            - mountPath: /tmp                       # 挂载路径
              name: pvc-obs-example 
          restartPolicy: Always
          imagePullSecrets:
            - name: default-secret
          volumes: 
          - name: pvc-obs-example  
            persistentVolumeClaim: 
              claimName: pvc-test-abc               # PVC名称
    ```


