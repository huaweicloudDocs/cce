# 使用kubectl自动创建对象存储<a name="cce_10_0325"></a>

## 操作场景<a name="section1062914713566"></a>

动态使用OBS可以自动创建并挂载所期望的OBS对象存储，目前支持标准、低频两种类型的桶，分别对应obs-standard、obs-standard-ia。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.13及以下版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，配置名为“pvc-obs-auto-example.yaml”的创建PVC的yaml文件。

    **touch pvc-obs-auto-example.yaml**

    **vi pvc-obs-auto-example.yaml**

    **yaml示例如下：**

    ```
    apiVersion: v1 
    kind: PersistentVolumeClaim 
    metadata: 
      annotations: 
        volume.beta.kubernetes.io/storage-class: obs-standard  # 对象存储桶类型，当前支持标准（obs-standard）和低频（obs-standard-ia）
      name: pvc-obs-auto-example  # PVC名称
      namespace: default 
    spec: 
      accessModes: 
      - ReadWriteMany 
      resources: 
        requests: 
          storage: 1Gi   # 存储容量，单位为Gi，对OBS桶来说，此处仅为校验需要（不能为空和0），设置的大小不起作用，此处设定为固定值1Gi
    ```

    **表 1**  关键参数说明

    <a name="table1897325023619"></a>
    <table><thead align="left"><tr id="row2973195019365"><th class="cellrowborder" valign="top" width="35.809999999999995%" id="mcps1.2.3.1.1"><p id="p1973155063611"><a name="p1973155063611"></a><a name="p1973155063611"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="64.19%" id="mcps1.2.3.1.2"><p id="p139741150123614"><a name="p139741150123614"></a><a name="p139741150123614"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3974350153618"><td class="cellrowborder" valign="top" width="35.809999999999995%" headers="mcps1.2.3.1.1 "><p id="p2974155083619"><a name="p2974155083619"></a><a name="p2974155083619"></a>volume.beta.kubernetes.io/storage-class</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.19%" headers="mcps1.2.3.1.2 "><p id="p1497425012362"><a name="p1497425012362"></a><a name="p1497425012362"></a>桶类型，当前支持标准（obs-standard）和低频（obs-standard-ia）两种桶。</p>
    </td>
    </tr>
    <tr id="row2974950133612"><td class="cellrowborder" valign="top" width="35.809999999999995%" headers="mcps1.2.3.1.1 "><p id="p1497565093618"><a name="p1497565093618"></a><a name="p1497565093618"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.19%" headers="mcps1.2.3.1.2 "><p id="p1975145003618"><a name="p1975145003618"></a><a name="p1975145003618"></a>创建的PVC名称。</p>
    </td>
    </tr>
    <tr id="row12975850123614"><td class="cellrowborder" valign="top" width="35.809999999999995%" headers="mcps1.2.3.1.1 "><p id="p17975150193613"><a name="p17975150193613"></a><a name="p17975150193613"></a>accessModes</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.19%" headers="mcps1.2.3.1.2 "><p id="p10975150173615"><a name="p10975150173615"></a><a name="p10975150173615"></a>只支持ReadWriteMany，不支持ReadWriteOnly。</p>
    </td>
    </tr>
    <tr id="row169751506362"><td class="cellrowborder" valign="top" width="35.809999999999995%" headers="mcps1.2.3.1.1 "><p id="p109751750123619"><a name="p109751750123619"></a><a name="p109751750123619"></a>storage</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.19%" headers="mcps1.2.3.1.2 "><p id="p119761450113614"><a name="p119761450113614"></a><a name="p119761450113614"></a>存储容量，单位为Gi，对OBS桶来说，此处仅为校验需要（不能为空和0），设置的大小不起作用，此处设定为固定值1Gi。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  执行如下命令创建PVC。

    **kubectl create -f pvc-obs-auto-example.yaml**

    命令执行完成后会在集群所在VPC内创建一个对象存储桶，您可以在“存储管理 \> 对象存储卷“中单击桶名称查看该桶，也可以在OBS的控制台查看该桶。


