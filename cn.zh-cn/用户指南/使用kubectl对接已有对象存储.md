# 使用kubectl对接已有对象存储<a name="cce_01_0267"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的对象存储来创建PersistentVolume，并通过创建对应PersistentVolumeClaim绑定当前PersistentVolume使用。

## 前提条件<a name="section13181839131510"></a>

您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](Everest（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  登录OBS控制台，创建对象存储桶，记录桶名称和存储类型。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建两个yaml文件，用于创建PersistentVolume（PV）、PersistentVolumeClaim（PVC），假设文件名为**pv-obs-example.yaml、pvc-obs-example.yaml。**

    **touch pv-obs-example.yaml** **pvc-obs-example.yaml**

    -   **vi pv-obs-example.yaml**

        **PV yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolume
        metadata:
          name: pv-obs-example
          annotations:
            pv.kubernetes.io/provisioned-by: everest-csi-provisioner
        spec:
          mountOptions:
          - umask=0027
          - uid=10000,gid=10000
          accessModes:
          - ReadWriteMany
          capacity:
            storage: 1Gi
          claimRef:
            apiVersion: v1
            kind: PersistentVolumeClaim
            name: pvc-obs-example
            namespace: default
          csi:
            driver: obs.csi.everest.io
            fsType: obsfs
            volumeAttributes:
              everest.io/obs-volume-type: STANDARD
              everest.io/region: cn-north-4
              storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
            volumeHandle: obs-normal-static-pv
          persistentVolumeReclaimPolicy: Delete
          storageClassName: csi-obs
        ```

        **表 1**  关键参数说明

        <a name="table1897325023619"></a>
        <table><thead align="left"><tr id="row2973195019365"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p1973155063611"><a name="p1973155063611"></a><a name="p1973155063611"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p139741150123614"><a name="p139741150123614"></a><a name="p139741150123614"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row3974350153618"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p2974155083619"><a name="p2974155083619"></a><a name="p2974155083619"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1497425012362"><a name="p1497425012362"></a><a name="p1497425012362"></a>挂载依赖的存储驱动，对象存储配置为“obs.csi.everest.io”。</p>
        </td>
        </tr>
        <tr id="row2974950133612"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1497565093618"><a name="p1497565093618"></a><a name="p1497565093618"></a>everest.io/obs-volume-type</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1975145003618"><a name="p1975145003618"></a><a name="p1975145003618"></a>存储类型，包括STANDARD（标准桶）、WARM（低频访问桶）。</p>
        </td>
        </tr>
        <tr id="row12975850123614"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p17975150193613"><a name="p17975150193613"></a><a name="p17975150193613"></a>everest.io/region</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p8485153732813"><a name="p8485153732813"></a><a name="p8485153732813"></a>OBS存储区域。</p>
        <p id="p10975150173615"><a name="p10975150173615"></a><a name="p10975150173615"></a>Region对应的值请参见<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。</p>
        </td>
        </tr>
        <tr id="row169751506362"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p109751750123619"><a name="p109751750123619"></a><a name="p109751750123619"></a>volumeHandle</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p15442275406"><a name="p15442275406"></a><a name="p15442275406"></a>对象存储的桶名称。</p>
        </td>
        </tr>
        <tr id="row19821194014381"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1915805418408"><a name="p1915805418408"></a><a name="p1915805418408"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p6794194043817"><a name="p6794194043817"></a><a name="p6794194043817"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
        </td>
        </tr>
        <tr id="row4820124093813"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p189611127144116"><a name="p189611127144116"></a><a name="p189611127144116"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1379412408389"><a name="p1379412408389"></a><a name="p1379412408389"></a>k8s storage class名称；需配置为"csi-obs”。</p>
        </td>
        </tr>
        <tr id="row5819194015382"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p15794144011386"><a name="p15794144011386"></a><a name="p15794144011386"></a>fsType</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p9794134093811"><a name="p9794134093811"></a><a name="p9794134093811"></a>文件类型，支持“obsfs”与“s3fs”，取值为s3fs时创建是obs对象桶，配套使用s3fs挂载；取值为obsfs时创建的是obs并行文件系统，配套使用obsfs挂载，推荐使用。</p>
        </td>
        </tr>
        <tr id="row19499851182010"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1549918517204"><a name="p1549918517204"></a><a name="p1549918517204"></a>spec.mountOptions</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p10499051132019"><a name="p10499051132019"></a><a name="p10499051132019"></a>挂载参数，具体请参见<a href="设置挂载参数.md#section1254912109811">对象存储挂载参数</a>。</p>
        </td>
        </tr>
        <tr id="row19752165415352"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p147528541353"><a name="p147528541353"></a><a name="p147528541353"></a>spec.claimRef.apiVersion</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p275385483520"><a name="p275385483520"></a><a name="p275385483520"></a>固定值"v1"。</p>
        </td>
        </tr>
        <tr id="row175571658173518"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p2557105803519"><a name="p2557105803519"></a><a name="p2557105803519"></a>spec.claimRef.kind</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p19557195820357"><a name="p19557195820357"></a><a name="p19557195820357"></a>固定值"PersistentVolumeClaim"。</p>
        </td>
        </tr>
        <tr id="row457015283616"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p13571102113610"><a name="p13571102113610"></a><a name="p13571102113610"></a>spec.claimRef.name</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p157114233611"><a name="p157114233611"></a><a name="p157114233611"></a>pvc名称；与下一步创建的pvc的name一致。</p>
        </td>
        </tr>
        <tr id="row89616163615"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p997146183617"><a name="p997146183617"></a><a name="p997146183617"></a>spec.claimRef.namespace</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p6976643614"><a name="p6976643614"></a><a name="p6976643614"></a>pvc的namespace；是下一步创建的pvc的namespace一致。</p>
        </td>
        </tr>
        </tbody>
        </table>

    -   **vi pvc-obs-example.yaml**

        **PVC yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          annotations:
            volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
            everest.io/obs-volume-type: STANDARD
            csi.storage.k8s.io/fstype: obsfs
          name: pvc-obs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 1Gi
          storageClassName: csi-obs
          volumeName: pv-obs-example
        ```

        **表 2**  关键参数说明

        <a name="table18848104713475"></a>
        <table><thead align="left"><tr id="row1284810475478"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p68481747184720"><a name="p68481747184720"></a><a name="p68481747184720"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p48481247174712"><a name="p48481247174712"></a><a name="p48481247174712"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row5848104764712"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p6835956174716"><a name="p6835956174716"></a><a name="p6835956174716"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p118491347144716"><a name="p118491347144716"></a><a name="p118491347144716"></a>PV的名称。</p>
        </td>
        </tr>
        <tr id="row28491947164715"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p128492047114717"><a name="p128492047114717"></a><a name="p128492047114717"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p88494472478"><a name="p88494472478"></a><a name="p88494472478"></a>存储容量，单位为Gi。此处配置为固定值1Gi，必须和已有pv的storage大小保持一致。</p>
        </td>
        </tr>
        <tr id="row1684914470476"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1844087134910"><a name="p1844087134910"></a><a name="p1844087134910"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p10850164734713"><a name="p10850164734713"></a><a name="p10850164734713"></a>k8s storage class名称；需配置为"csi-obs”。</p>
        </td>
        </tr>
        <tr id="row38501647114713"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p485084724716"><a name="p485084724716"></a><a name="p485084724716"></a>everest.io/obs-volume-type</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1885164717473"><a name="p1885164717473"></a><a name="p1885164717473"></a>obs存储类型；当前支持标准（STANDARD）和低频（WARM）两种存储类型。</p>
        </td>
        </tr>
        <tr id="row15851154744719"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p485134744716"><a name="p485134744716"></a><a name="p485134744716"></a>csi.storage.k8s.io/fstype</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1985154719470"><a name="p1985154719470"></a><a name="p1985154719470"></a>指定文件类型，支持“obsfs”与“s3fs”。取值为s3fs时说明使用的obs对象桶，配套使用s3fs挂载；取值为obsfs时说明使用的是obs并行文件系统，配套使用obsfs挂载。</p>
        </td>
        </tr>
        </tbody>
        </table>

4.  创建PV。

    **kubectl create -f pv-obs-example.yaml**

5.  创建PVC。

    **kubectl create -f pvc-obs-example.yaml**


