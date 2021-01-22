# 使用kubectl自动创建文件存储<a name="cce_01_0260"></a>

-   [操作场景](#section1062914713566)
-   [操作步骤](#section1530655595611)

## 操作场景<a name="section1062914713566"></a>

CCE支持使用PersistentVolumeClaim（PVC）的形式创建文件存储。

## 操作步骤<a name="section1530655595611"></a>

1.  请参见[通过kubectl或web-terminal插件操作CCE集群](通过kubectl或web-terminal插件操作CCE集群.md)配置kubectl命令。
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

        **表 1**  关键参数说明

        <a name="table628368131916"></a>
        <table><thead align="left"><tr id="row122837851917"><th class="cellrowborder" valign="top" width="35.25875971265211%" id="mcps1.2.3.1.1"><p id="p42830816196"><a name="p42830816196"></a><a name="p42830816196"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="64.7412402873479%" id="mcps1.2.3.1.2"><p id="p16284108101912"><a name="p16284108101912"></a><a name="p16284108101912"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1428438101916"><td class="cellrowborder" valign="top" width="35.25875971265211%" headers="mcps1.2.3.1.1 "><p id="p142843811197"><a name="p142843811197"></a><a name="p142843811197"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.7412402873479%" headers="mcps1.2.3.1.2 "><p id="p14367283124"><a name="p14367283124"></a><a name="p14367283124"></a>k8s storage class名称；使用“csi-nas”。</p>
        </td>
        </tr>
        <tr id="row428458201916"><td class="cellrowborder" valign="top" width="35.25875971265211%" headers="mcps1.2.3.1.1 "><p id="p202841483196"><a name="p202841483196"></a><a name="p202841483196"></a>name</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.7412402873479%" headers="mcps1.2.3.1.2 "><p id="p11284585196"><a name="p11284585196"></a><a name="p11284585196"></a>创建的PVC名称。</p>
        </td>
        </tr>
        <tr id="row192841589190"><td class="cellrowborder" valign="top" width="35.25875971265211%" headers="mcps1.2.3.1.1 "><p id="p6117131095712"><a name="p6117131095712"></a><a name="p6117131095712"></a>accessModes</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.7412402873479%" headers="mcps1.2.3.1.2 "><p id="p112851818196"><a name="p112851818196"></a><a name="p112851818196"></a>只支持ReadWriteMany，不支持ReadWriteOnly。</p>
        </td>
        </tr>
        <tr id="row6285158191916"><td class="cellrowborder" valign="top" width="35.25875971265211%" headers="mcps1.2.3.1.1 "><p id="p1828558101912"><a name="p1828558101912"></a><a name="p1828558101912"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.7412402873479%" headers="mcps1.2.3.1.2 "><p id="p415683820207"><a name="p415683820207"></a><a name="p415683820207"></a>存储容量，单位为Gi。</p>
        </td>
        </tr>
        </tbody>
        </table>

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

        **表 2**  关键参数说明

        <a name="table71355385813"></a>
        <table><thead align="left"><tr id="row141351434587"><th class="cellrowborder" valign="top" width="35.91404180158963%" id="mcps1.2.3.1.1"><p id="p151358385810"><a name="p151358385810"></a><a name="p151358385810"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="64.08595819841037%" id="mcps1.2.3.1.2"><p id="p7135331587"><a name="p7135331587"></a><a name="p7135331587"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row11351935589"><td class="cellrowborder" valign="top" width="35.91404180158963%" headers="mcps1.2.3.1.1 "><p id="p12135334586"><a name="p12135334586"></a><a name="p12135334586"></a>volume.beta.kubernetes.io/storage-class</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.08595819841037%" headers="mcps1.2.3.1.2 "><p id="p813603165815"><a name="p813603165815"></a><a name="p813603165815"></a>文件存储类型，当前支持标准文件协议类型（nfs-rw）。</p>
        </td>
        </tr>
        <tr id="row1413614317585"><td class="cellrowborder" valign="top" width="35.91404180158963%" headers="mcps1.2.3.1.1 "><p id="p1313610315580"><a name="p1313610315580"></a><a name="p1313610315580"></a>name</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.08595819841037%" headers="mcps1.2.3.1.2 "><p id="p121368345813"><a name="p121368345813"></a><a name="p121368345813"></a>创建的PVC名称。</p>
        </td>
        </tr>
        <tr id="row1713683175810"><td class="cellrowborder" valign="top" width="35.91404180158963%" headers="mcps1.2.3.1.1 "><p id="p20136133145811"><a name="p20136133145811"></a><a name="p20136133145811"></a>accessModes</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.08595819841037%" headers="mcps1.2.3.1.2 "><p id="p8136235589"><a name="p8136235589"></a><a name="p8136235589"></a>只支持ReadWriteMany，不支持ReadWriteOnly。</p>
        </td>
        </tr>
        <tr id="row1513614311583"><td class="cellrowborder" valign="top" width="35.91404180158963%" headers="mcps1.2.3.1.1 "><p id="p81361634589"><a name="p81361634589"></a><a name="p81361634589"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.08595819841037%" headers="mcps1.2.3.1.2 "><p id="p21361134586"><a name="p21361134586"></a><a name="p21361134586"></a>存储容量，单位为Gi。</p>
        </td>
        </tr>
        </tbody>
        </table>


3.  执行如下命令创建PVC。

    **kubectl create -f pvc-sfs-auto-example.yaml**

    命令执行完成后会在集群所在VPC内创建一个文件存储，您可以在“存储管理 \> 文件存储卷“中查看该文件系统，也可以在SFS的控制台中查看该文件系统。


