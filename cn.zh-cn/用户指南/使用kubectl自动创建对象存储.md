# 使用kubectl自动创建对象存储<a name="cce_01_0266"></a>

## 操作场景<a name="section1062914713566"></a>

动态使用OBS可以自动创建并挂载所期望的OBS对象存储，目前支持标准、低频两种类型的桶，分别对应obs-standard、obs-standard-ia。

## 前提条件<a name="section13181839131510"></a>

您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](Everest（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，配置名为“pvc-obs-auto-example.yaml”的创建PVC的yaml文件。

    **touch pvc-obs-auto-example.yaml**

    **vi pvc-obs-auto-example.yaml**

    **yaml配置示例如下：**

    ```
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      annotations:
        everest.io/obs-volume-type: STANDARD
        csi.storage.k8s.io/fstype: obsfs   
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

    **表 1**  关键参数说明

    <a name="table14312339123018"></a>
    <table><thead align="left"><tr id="row8312153953015"><th class="cellrowborder" valign="top" width="35.35%" id="mcps1.2.3.1.1"><p id="p11312143923015"><a name="p11312143923015"></a><a name="p11312143923015"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="64.64999999999999%" id="mcps1.2.3.1.2"><p id="p13313153914304"><a name="p13313153914304"></a><a name="p13313153914304"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1031311395306"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="p10313203914303"><a name="p10313203914303"></a><a name="p10313203914303"></a>everest.io/obs-volume-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="p2313133916301"><a name="p2313133916301"></a><a name="p2313133916301"></a>桶类型，当前支持标准（STANDARD）和低频（WARM）两种桶。</p>
    </td>
    </tr>
    <tr id="row731393993011"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="p143141539123014"><a name="p143141539123014"></a><a name="p143141539123014"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="p1231423983016"><a name="p1231423983016"></a><a name="p1231423983016"></a>创建的PVC名称。</p>
    </td>
    </tr>
    <tr id="row33147398308"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="p18314439163011"><a name="p18314439163011"></a><a name="p18314439163011"></a>accessModes</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="p20314183973011"><a name="p20314183973011"></a><a name="p20314183973011"></a>只支持ReadWriteMany，不支持ReadWriteOnly。</p>
    </td>
    </tr>
    <tr id="row1928842193316"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="p522572143315"><a name="p522572143315"></a><a name="p522572143315"></a>storage</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="p22266211339"><a name="p22266211339"></a><a name="p22266211339"></a>存储容量，单位为Gi，对OBS桶来说，此处仅为校验需要（不能为空和0），设置的大小不起作用，此处设定为固定值1Gi。</p>
    </td>
    </tr>
    <tr id="row4282162123317"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="p626403123418"><a name="p626403123418"></a><a name="p626403123418"></a>csi.storage.k8s.io/fstype</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="p122742123318"><a name="p122742123318"></a><a name="p122742123318"></a>文件类型，支持“obsfs”与“s3fs”，取值为s3fs时创建是obs对象桶，配套使用s3fs挂载；取值为obsfs时创建的是obs并行文件系统，配套使用obsfs挂载，推荐使用。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  执行如下命令创建PVC。

    **kubectl create -f pvc-obs-auto-example.yaml**

    命令执行完成后会在集群所在VPC内创建一个对象存储桶，您可以在“存储管理 \> 对象存储卷“中单击桶名称查看该桶，也可以在OBS的控制台中查看该桶。


