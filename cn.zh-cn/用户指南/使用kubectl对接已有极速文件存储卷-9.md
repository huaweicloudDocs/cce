# 使用kubectl对接已有极速文件存储卷<a name="cce_01_0332"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的极速文件存储来创建PersistentVolume，创建成功后，通过创建相应的PersistentVolumeClaim来绑定当前的PersistentVolume使用。

## 前提条件<a name="section1640173074515"></a>

您已经创建好一个CCE集群，并且在该集群中安装Flexvolume插件（[storage-driver](storage-driver（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.13及以下版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  登录SFS控制台，创建一个文件存储，记录文件存储的ID、共享路径和容量。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建两个yaml文件，用于创建PersistentVolume（PV）、PersistentVolumeClaim（PVC）。假设文件名分别为**pv-efs-example.yaml**、**pvc-efs-example.yaml**。

    **touch pv-efs-example.yaml** **pvc-efs-example.yaml**

    -   **PV yaml文件配置示例如下：**

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
          claimRef:
            apiVersion: v1
            kind: PersistentVolumeClaim
            name: pvc-efs-example
            namespace: default
          flexVolume: 
            driver: huawei.com/fuxiefs 
            fsType: efs 
            options: 
              deviceMountPath: <your_deviceMountPath>  #您的极速文件存储共享路径 
              fsType: efs 
              volumeID: 8962a2a2-a583-4b7f-bb74-fe76712d8414 
          persistentVolumeReclaimPolicy: Delete 
          storageClassName: efs-standard
        ```

        **表 1**  关键参数说明

        <a name="table1857613471103"></a>
        <table><thead align="left"><tr id="row65751147161014"><th class="cellrowborder" valign="top" width="32.32%" id="mcps1.2.3.1.1"><p id="p10575114719102"><a name="p10575114719102"></a><a name="p10575114719102"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="67.67999999999999%" id="mcps1.2.3.1.2"><p id="p1357534717101"><a name="p1357534717101"></a><a name="p1357534717101"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row15756477108"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p1557564718103"><a name="p1557564718103"></a><a name="p1557564718103"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p2575114791013"><a name="p2575114791013"></a><a name="p2575114791013"></a>挂载依赖的存储驱动，极速文件存储配置为“huawei.com/fuxiefs”。</p>
        </td>
        </tr>
        <tr id="row5575134713108"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p8575164721010"><a name="p8575164721010"></a><a name="p8575164721010"></a>deviceMountPath</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p8575124761010"><a name="p8575124761010"></a><a name="p8575124761010"></a>极速文件存储的共享路径。</p>
        </td>
        </tr>
        <tr id="row957514731018"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p115758475102"><a name="p115758475102"></a><a name="p115758475102"></a>volumeID</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p205751747141012"><a name="p205751747141012"></a><a name="p205751747141012"></a>极速文件存储的ID。</p>
        <p id="p14575124751019"><a name="p14575124751019"></a><a name="p14575124751019"></a>获取方法：在CCE控制台中，单击左侧栏目树中的<span class="uicontrol" id="uicontrol457515472101"><a name="uicontrol457515472101"></a><a name="uicontrol457515472101"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol9575154731010"><a name="uicontrol9575154731010"></a><a name="uicontrol9575154731010"></a>“极速文件存储卷”</span>页签下单击PVC的名称，在PVC详情页中复制<span class="uicontrol" id="uicontrol9575154716101"><a name="uicontrol9575154716101"></a><a name="uicontrol9575154716101"></a>“PVC UID”</span>后的内容即可。</p>
        </td>
        </tr>
        <tr id="row75761347101016"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p18575147131016"><a name="p18575147131016"></a><a name="p18575147131016"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p115751479106"><a name="p115751479106"></a><a name="p115751479106"></a>文件存储的大小。</p>
        </td>
        </tr>
        <tr id="row2057617470102"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p557614715108"><a name="p557614715108"></a><a name="p557614715108"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p45761947201014"><a name="p45761947201014"></a><a name="p45761947201014"></a>极速文件存储支持的卷类型，当前支持efs-standard、efs-performance（目前SFS Turbo不支持动态创建，所以此参数后续没有使用）。</p>
        </td>
        </tr>
        <tr id="row17100922145816"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p31001822145820"><a name="p31001822145820"></a><a name="p31001822145820"></a>spec.claimRef.apiVersion</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p21000227587"><a name="p21000227587"></a><a name="p21000227587"></a>固定值"v1"。</p>
        </td>
        </tr>
        <tr id="row19278192545812"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p122788253581"><a name="p122788253581"></a><a name="p122788253581"></a>spec.claimRef.kind</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p20278325145819"><a name="p20278325145819"></a><a name="p20278325145819"></a>固定值"PersistentVolumeClaim"。</p>
        </td>
        </tr>
        <tr id="row275172845812"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p13753281589"><a name="p13753281589"></a><a name="p13753281589"></a>spec.claimRef.name</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p1175172855817"><a name="p1175172855817"></a><a name="p1175172855817"></a>与下一步创建的pvc的name一致。</p>
        </td>
        </tr>
        <tr id="row9112631195811"><td class="cellrowborder" valign="top" width="32.32%" headers="mcps1.2.3.1.1 "><p id="p101121531185818"><a name="p101121531185818"></a><a name="p101121531185818"></a>spec.claimRef.namespace</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.3.1.2 "><p id="p10112531115815"><a name="p10112531115815"></a><a name="p10112531115815"></a>与下一步创建的pvc的namespace一致。</p>
        </td>
        </tr>
        </tbody>
        </table>

    -   **PVC yaml文件配置示例如下：**

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

        **表 2**  关键参数说明

        <a name="table1739110557150"></a>
        <table><thead align="left"><tr id="row439135512158"><th class="cellrowborder" valign="top" width="39.46%" id="mcps1.2.3.1.1"><p id="p11391105571516"><a name="p11391105571516"></a><a name="p11391105571516"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="60.540000000000006%" id="mcps1.2.3.1.2"><p id="p439255513157"><a name="p439255513157"></a><a name="p439255513157"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row739215556154"><td class="cellrowborder" valign="top" width="39.46%" headers="mcps1.2.3.1.1 "><p id="p3131325191618"><a name="p3131325191618"></a><a name="p3131325191618"></a>volume.beta.kubernetes.io/storage-class</p>
        </td>
        <td class="cellrowborder" valign="top" width="60.540000000000006%" headers="mcps1.2.3.1.2 "><p id="p23923555150"><a name="p23923555150"></a><a name="p23923555150"></a>文件存储支持的读写方式，支持efs-standard、efs-performance。必须和已有PV保持一致。</p>
        </td>
        </tr>
        <tr id="row18143134041612"><td class="cellrowborder" valign="top" width="39.46%" headers="mcps1.2.3.1.1 "><p id="p11431840161611"><a name="p11431840161611"></a><a name="p11431840161611"></a>volume.beta.kubernetes.io/storage-provisioner</p>
        </td>
        <td class="cellrowborder" valign="top" width="60.540000000000006%" headers="mcps1.2.3.1.2 "><p id="p714434016164"><a name="p714434016164"></a><a name="p714434016164"></a>必须使用flexvolume-huawei.com/fuxiefs。</p>
        </td>
        </tr>
        <tr id="row1339295514152"><td class="cellrowborder" valign="top" width="39.46%" headers="mcps1.2.3.1.1 "><p id="p83921559156"><a name="p83921559156"></a><a name="p83921559156"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="60.540000000000006%" headers="mcps1.2.3.1.2 "><p id="p1839395518152"><a name="p1839395518152"></a><a name="p1839395518152"></a>存储容量，单位Gi，必须和已有pv的storage大小保持一致。</p>
        </td>
        </tr>
        <tr id="row1339365571519"><td class="cellrowborder" valign="top" width="39.46%" headers="mcps1.2.3.1.1 "><p id="p239365513155"><a name="p239365513155"></a><a name="p239365513155"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="60.540000000000006%" headers="mcps1.2.3.1.2 "><p id="p10393455131513"><a name="p10393455131513"></a><a name="p10393455131513"></a>PV的名称。</p>
        </td>
        </tr>
        </tbody>
        </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >极速文件存储所在VPC，子网必须与工作负载规划部署的ECS虚拟机的VPC保持一致，安全组开放入方向端口\(111、445、2049、2051、20048\)。

4.  创建PV。

    **kubectl create -f pv-efs-example.yaml**

5.  创建PVC。

    **kubectl create -f pvc-efs-example.yaml**


