# 使用kubectl对接已有极速文件存储卷<a name="cce_01_0272"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的极速文件存储来创建PersistentVolume，创建成功后，通过创建相应的PersistentVolumeClaim来绑定当前的PersistentVolume使用。

## 前提条件<a name="section13181839131510"></a>

您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](Everest（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  登录SFS控制台，创建一个文件存储，记录文件存储的ID、共享路径和容量。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建两个yaml文件，用于创建PersistentVolume（PV）、PersistentVolumeClaim（PVC）。假设文件名分别为**pv-efs-example.yaml**、**pvc-efs-example.yaml**。

    **touch pv-efs-example.yaml** **pvc-efs-example.yaml**

    -   **vi pv-efs-example.yaml**

        **PV yaml文件配置示例如下：**

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
          claimRef:
            apiVersion: v1
            kind: PersistentVolumeClaim
            name: pvc-efs-example
            namespace: default
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

        **表 1**  关键参数说明

        <a name="table953204119"></a>
        <table><thead align="left"><tr id="row1666206115"><th class="cellrowborder" valign="top" width="35.89%" id="mcps1.2.3.1.1"><p id="p1662017116"><a name="p1662017116"></a><a name="p1662017116"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="64.11%" id="mcps1.2.3.1.2"><p id="p56820513"><a name="p56820513"></a><a name="p56820513"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1061620713"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p56120115"><a name="p56120115"></a><a name="p56120115"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p911192017111"><a name="p911192017111"></a><a name="p911192017111"></a>挂载依赖的存储驱动，极速文件存储配置为“sfsturbo.csi.everest.io”。</p>
        </td>
        </tr>
        <tr id="row6115201810"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p1911172013115"><a name="p1911172013115"></a><a name="p1911172013115"></a>everest.io/share-export-location</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p1812132017111"><a name="p1812132017111"></a><a name="p1812132017111"></a>极速文件存储的共享路径。</p>
        </td>
        </tr>
        <tr id="row181217201317"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p2127205115"><a name="p2127205115"></a><a name="p2127205115"></a>volumeHandle</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p331414324103"><a name="p331414324103"></a><a name="p331414324103"></a>极速文件存储的ID。</p>
        <p id="p1455172961010"><a name="p1455172961010"></a><a name="p1455172961010"></a>获取方法：在弹性文件服务控制台，单击SFS Turbo存储实例，在基本信息中可查看到ID。</p>
        </td>
        </tr>
        <tr id="row101220201616"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p4121201717"><a name="p4121201717"></a><a name="p4121201717"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p1373713106118"><a name="p1373713106118"></a><a name="p1373713106118"></a>文件存储的大小。</p>
        </td>
        </tr>
        <tr id="row118294312105"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p16741643171012"><a name="p16741643171012"></a><a name="p16741643171012"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p127424310105"><a name="p127424310105"></a><a name="p127424310105"></a>指定k8s storage class名称；极速文件存储卷需配置为"csi-sfsturbo”。</p>
        </td>
        </tr>
        <tr id="row1292142194111"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p19292122114413"><a name="p19292122114413"></a><a name="p19292122114413"></a>spec.claimRef.apiVersion</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p162921213418"><a name="p162921213418"></a><a name="p162921213418"></a>固定值"v1"。</p>
        </td>
        </tr>
        <tr id="row12530172512416"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p1053018258416"><a name="p1053018258416"></a><a name="p1053018258416"></a>spec.claimRef.kind</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p1353052584115"><a name="p1353052584115"></a><a name="p1353052584115"></a>固定值"PersistentVolumeClaim"。</p>
        </td>
        </tr>
        <tr id="row1513982864116"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p613972844115"><a name="p613972844115"></a><a name="p613972844115"></a>spec.claimRef.name</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p113912816416"><a name="p113912816416"></a><a name="p113912816416"></a>与下一步创建的pvc的name一致。</p>
        </td>
        </tr>
        <tr id="row86908177417"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p8691817114114"><a name="p8691817114114"></a><a name="p8691817114114"></a>spec.claimRef.namespace</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p1069111754110"><a name="p1069111754110"></a><a name="p1069111754110"></a>与下一步创建的pvc的namespace一致。</p>
        </td>
        </tr>
        </tbody>
        </table>

    -   **vi pvc-efs-example.yaml**

        **PVC yaml文件配置示例如下：**

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

        **表 2**  关键参数说明

        <a name="table154321323191412"></a>
        <table><thead align="left"><tr id="row1432192381417"><th class="cellrowborder" valign="top" width="31.929999999999996%" id="mcps1.2.3.1.1"><p id="p18433152391413"><a name="p18433152391413"></a><a name="p18433152391413"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="68.07%" id="mcps1.2.3.1.2"><p id="p19433192321419"><a name="p19433192321419"></a><a name="p19433192321419"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row164331623191417"><td class="cellrowborder" valign="top" width="31.929999999999996%" headers="mcps1.2.3.1.1 "><p id="p20433112371413"><a name="p20433112371413"></a><a name="p20433112371413"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="68.07%" headers="mcps1.2.3.1.2 "><p id="p6433142314144"><a name="p6433142314144"></a><a name="p6433142314144"></a>指定k8s storage class名称；需配置为"csi-sfsturbo”。</p>
        </td>
        </tr>
        <tr id="row184341223131415"><td class="cellrowborder" valign="top" width="31.929999999999996%" headers="mcps1.2.3.1.1 "><p id="p16434623161416"><a name="p16434623161416"></a><a name="p16434623161416"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="68.07%" headers="mcps1.2.3.1.2 "><p id="p4434102301418"><a name="p4434102301418"></a><a name="p4434102301418"></a>存储容量，单位Gi，必须和已有pv的storage大小保持一致。</p>
        </td>
        </tr>
        <tr id="row20434023121415"><td class="cellrowborder" valign="top" width="31.929999999999996%" headers="mcps1.2.3.1.1 "><p id="p1743410236141"><a name="p1743410236141"></a><a name="p1743410236141"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="68.07%" headers="mcps1.2.3.1.2 "><p id="p3435182316146"><a name="p3435182316146"></a><a name="p3435182316146"></a>PV的名称。</p>
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


