# 使用kubectl对接已有对象存储<a name="cce_01_0267"></a>

-   [操作场景](#section1062914713566)
-   [操作步骤](#section1530655595611)
-   [历史版本示例](#section999841112554)

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的对象存储来创建PersistentVolume，并通过创建对应PersistentVolumeClaim绑定当前PersistentVolume使用。

## 操作步骤<a name="section1530655595611"></a>

1.  登录OBS控制台，创建对象存储桶，记录桶名称和存储类型。
2.  请参见[通过kubectl或web-terminal插件操作CCE集群](通过kubectl或web-terminal插件操作CCE集群.md)配置kubectl命令。
3.  新建两个yaml文件，用于创建PersistentVolume（PV）、PersistentVolumeClaim（PVC），假设文件名为**pv-obs-example.yaml、pvc-obs-example.yaml。**

    **touch pv-obs-example.yaml** **pvc-obs-example.yaml**

    <a name="table184303411324"></a>
    <table><thead align="left"><tr id="row104311415322"><th class="cellrowborder" valign="top" width="33.2033203320332%" id="mcps1.1.4.1.1"><p id="p443118443220"><a name="p443118443220"></a><a name="p443118443220"></a>K8S集群版本（K8S version）</p>
    </th>
    <th class="cellrowborder" valign="top" width="35.34353435343534%" id="mcps1.1.4.1.2"><p id="p1431154113212"><a name="p1431154113212"></a><a name="p1431154113212"></a>说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="31.453145314531454%" id="mcps1.1.4.1.3"><p id="p14311346322"><a name="p14311346322"></a><a name="p14311346322"></a>yaml示例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row19431184193219"><td class="cellrowborder" valign="top" width="33.2033203320332%" headers="mcps1.1.4.1.1 "><p id="p174311433220"><a name="p174311433220"></a><a name="p174311433220"></a>1.15+</p>
    </td>
    <td class="cellrowborder" valign="top" width="35.34353435343534%" headers="mcps1.1.4.1.2 "><p id="p194315417329"><a name="p194315417329"></a><a name="p194315417329"></a>1.15及以上版本的集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.453145314531454%" headers="mcps1.1.4.1.3 "><p id="p13431164173218"><a name="p13431164173218"></a><a name="p13431164173218"></a>请参见<a href="#li16267181610528">1.15+ yaml文件配置示例</a></p>
    </td>
    </tr>
    <tr id="row543118415321"><td class="cellrowborder" valign="top" width="33.2033203320332%" headers="mcps1.1.4.1.1 "><p id="p1743111463216"><a name="p1743111463216"></a><a name="p1743111463216"></a>1.11 ≤ K8S version ≤ 1.13</p>
    </td>
    <td class="cellrowborder" valign="top" width="35.34353435343534%" headers="mcps1.1.4.1.2 "><p id="p743119413320"><a name="p743119413320"></a><a name="p743119413320"></a>1.11以上及1.13版本集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.453145314531454%" headers="mcps1.1.4.1.3 "><p id="p13431246327"><a name="p13431246327"></a><a name="p13431246327"></a>请参见<a href="#li45671840132016">1.11~1.13 yaml文件配置示例</a></p>
    </td>
    </tr>
    <tr id="row72981940163417"><td class="cellrowborder" valign="top" width="33.2033203320332%" headers="mcps1.1.4.1.1 "><p id="p9298154043420"><a name="p9298154043420"></a><a name="p9298154043420"></a>K8S version = 1.9</p>
    </td>
    <td class="cellrowborder" valign="top" width="35.34353435343534%" headers="mcps1.1.4.1.2 "><p id="p1729814407349"><a name="p1729814407349"></a><a name="p1729814407349"></a>1.9版本集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.453145314531454%" headers="mcps1.1.4.1.3 "><p id="p529834014349"><a name="p529834014349"></a><a name="p529834014349"></a>请参见<a href="#li154036581589">1.9 yaml文件配置示例</a></p>
    </td>
    </tr>
    </tbody>
    </table>

    **1.15+（1.15及以上版本的集群）**

    -   <a name="li16267181610528"></a>**vi pv-obs-example.yaml**

        **PV yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolume
        metadata:
          name: pv-obs-example
          annotations:
            pv.kubernetes.io/provisioned-by: everest-csi-provisioner
        spec:
          accessModes:
          - ReadWriteMany
          capacity:
            storage: 1Gi
          csi:
            driver: obs.csi.everest.io
            fsType: s3fs
            volumeAttributes:
              everest.io/obs-volume-type: STANDARD
              everest.io/region: cn-north-7
              storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
            volumeHandle: obs-normal-static-pv
          persistentVolumeReclaimPolicy: Delete
          storageClassName: csi-obs
        ```

        **表 1**  关键参数说明

        <a name="table1897325023619"></a>
        <table><thead align="left"><tr id="row2973195019365"><th class="cellrowborder" valign="top" width="26.42980935875217%" id="mcps1.2.3.1.1"><p id="p1973155063611"><a name="p1973155063611"></a><a name="p1973155063611"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="73.57019064124783%" id="mcps1.2.3.1.2"><p id="p139741150123614"><a name="p139741150123614"></a><a name="p139741150123614"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row3974350153618"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p2974155083619"><a name="p2974155083619"></a><a name="p2974155083619"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1497425012362"><a name="p1497425012362"></a><a name="p1497425012362"></a>挂载依赖的存储驱动，对象存储配置为“obs.csi.everest.io”。</p>
        </td>
        </tr>
        <tr id="row2974950133612"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p1497565093618"><a name="p1497565093618"></a><a name="p1497565093618"></a>everest.io/obs-volume-type</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1975145003618"><a name="p1975145003618"></a><a name="p1975145003618"></a>存储类型，包括STANDARD（标准桶）、WARM（低频访问桶）。</p>
        </td>
        </tr>
        <tr id="row12975850123614"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p17975150193613"><a name="p17975150193613"></a><a name="p17975150193613"></a>everest.io/region</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p10975150173615"><a name="p10975150173615"></a><a name="p10975150173615"></a>对象存储所在的region。具体请参见<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。</p>
        </td>
        </tr>
        <tr id="row169751506362"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p109751750123619"><a name="p109751750123619"></a><a name="p109751750123619"></a>volumeHandle</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p15442275406"><a name="p15442275406"></a><a name="p15442275406"></a>对象存储的桶名称。</p>
        <p id="p1032619419408"><a name="p1032619419408"></a><a name="p1032619419408"></a>获取方法：在CCE控制台中，单击左侧栏目树中的<span class="uicontrol" id="uicontrol183266415404"><a name="uicontrol183266415404"></a><a name="uicontrol183266415404"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol1632612417407"><a name="uicontrol1632612417407"></a><a name="uicontrol1632612417407"></a>“对象存储卷”</span>页签下单击PVC的名称，在PVC详情页的<span class="uicontrol" id="uicontrol1132618419403"><a name="uicontrol1132618419403"></a><a name="uicontrol1132618419403"></a>“PV详情”</span>页签下复制<span class="uicontrol" id="uicontrol1532614474012"><a name="uicontrol1532614474012"></a><a name="uicontrol1532614474012"></a>“PV名称”</span>后的内容即可。</p>
        </td>
        </tr>
        <tr id="row19821194014381"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p1915805418408"><a name="p1915805418408"></a><a name="p1915805418408"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p6794194043817"><a name="p6794194043817"></a><a name="p6794194043817"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
        </td>
        </tr>
        <tr id="row4820124093813"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p189611127144116"><a name="p189611127144116"></a><a name="p189611127144116"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1379412408389"><a name="p1379412408389"></a><a name="p1379412408389"></a>k8s storage class名称；需配置为"csi-obs”。</p>
        </td>
        </tr>
        <tr id="row5819194015382"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p15794144011386"><a name="p15794144011386"></a><a name="p15794144011386"></a>fsType</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p9794134093811"><a name="p9794134093811"></a><a name="p9794134093811"></a>文件类型，支持“obsfs”与“s3fs”，取值为s3fs时创建是obs对象桶，配套使用s3fs挂载；取值为obsfs时创建的是obs并行文件系统，配套使用obsfs挂载，推荐使用。</p>
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
            csi.storage.k8s.io/fstype: s3fs
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
        <table><thead align="left"><tr id="row1284810475478"><th class="cellrowborder" valign="top" width="26.42980935875217%" id="mcps1.2.3.1.1"><p id="p68481747184720"><a name="p68481747184720"></a><a name="p68481747184720"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="73.57019064124783%" id="mcps1.2.3.1.2"><p id="p48481247174712"><a name="p48481247174712"></a><a name="p48481247174712"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row5848104764712"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p6835956174716"><a name="p6835956174716"></a><a name="p6835956174716"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p118491347144716"><a name="p118491347144716"></a><a name="p118491347144716"></a>PV的名称。</p>
        </td>
        </tr>
        <tr id="row28491947164715"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p128492047114717"><a name="p128492047114717"></a><a name="p128492047114717"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p88494472478"><a name="p88494472478"></a><a name="p88494472478"></a>存储容量，单位为Gi。此处配置为固定值1Gi，必须和已有pv的storage大小保持一致。</p>
        </td>
        </tr>
        <tr id="row1684914470476"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p1844087134910"><a name="p1844087134910"></a><a name="p1844087134910"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p10850164734713"><a name="p10850164734713"></a><a name="p10850164734713"></a>k8s storage class名称；需配置为"csi-obs”。</p>
        </td>
        </tr>
        <tr id="row38501647114713"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p485084724716"><a name="p485084724716"></a><a name="p485084724716"></a>everest.io/obs-volume-type</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1885164717473"><a name="p1885164717473"></a><a name="p1885164717473"></a>obs存储类型；当前支持标准（STANDARD）和低频（WARM）两种存储类型。</p>
        </td>
        </tr>
        <tr id="row15851154744719"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p485134744716"><a name="p485134744716"></a><a name="p485134744716"></a>csi.storage.k8s.io/fstype</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1985154719470"><a name="p1985154719470"></a><a name="p1985154719470"></a>指定文件类型，支持“obsfs”与“s3fs”。取值为s3fs时说明使用的obs对象桶，配套使用s3fs挂载；取值为obsfs时说明使用的是obs并行文件系统，配套使用obsfs挂载。</p>
        </td>
        </tr>
        </tbody>
        </table>


4.  创建PV。

    **kubectl create -f pv-obs-example.yaml**

5.  创建PVC。

    **kubectl create -f pvc-obs-example.yaml**


## 历史版本示例<a name="section999841112554"></a>

**1.11 ≤ K8S version ≤ 1.13（1.11以上及1.13版本集群）**

-   <a name="li45671840132016"></a>**PV yaml文件配置示例：**

    ```
    apiVersion: v1 
    kind: PersistentVolume 
    metadata: 
      name: pv-obs-example 
      annotations:
        pv.kubernetes.io/provisioned-by: flexvolume-huawei.com/fuxiobs
    spec: 
      accessModes: 
      - ReadWriteMany 
      capacity: 
        storage: 1Gi 
      flexVolume: 
        driver: huawei.com/fuxiobs 
        fsType: obs 
        options: 
          fsType: obs 
          region: cn-north-4 
          storage_class: STANDARD 
          volumeID: test-obs 
      persistentVolumeReclaimPolicy: Delete 
      storageClassName: obs-standard
    ```

    **表 3**  关键参数说明

    <a name="table832713405430"></a>
    <table><thead align="left"><tr id="row53276406434"><th class="cellrowborder" valign="top" width="26.42980935875217%" id="mcps1.2.3.1.1"><p id="p15327134014433"><a name="p15327134014433"></a><a name="p15327134014433"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="73.57019064124783%" id="mcps1.2.3.1.2"><p id="p133274408432"><a name="p133274408432"></a><a name="p133274408432"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row432714020436"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p13328540134319"><a name="p13328540134319"></a><a name="p13328540134319"></a>driver</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1032814074320"><a name="p1032814074320"></a><a name="p1032814074320"></a>挂载依赖的存储驱动，对象存储配置为“huawei.com/fuxiobs”。</p>
    </td>
    </tr>
    <tr id="row132834014431"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p13979181319442"><a name="p13979181319442"></a><a name="p13979181319442"></a>storage_class</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p83281740134319"><a name="p83281740134319"></a><a name="p83281740134319"></a>存储类型，包括STANDARD（标准桶）、STANDARD_IA（低频访问桶）。</p>
    </td>
    </tr>
    <tr id="row1332819409437"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p997612588441"><a name="p997612588441"></a><a name="p997612588441"></a>region</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1328940164315"><a name="p1328940164315"></a><a name="p1328940164315"></a>对象存储所在的region。具体请参见<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。</p>
    </td>
    </tr>
    <tr id="row5328440194311"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p143286409433"><a name="p143286409433"></a><a name="p143286409433"></a>volumeID</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1676410385454"><a name="p1676410385454"></a><a name="p1676410385454"></a>对象存储的桶名称。</p>
    <p id="p35271835134519"><a name="p35271835134519"></a><a name="p35271835134519"></a>获取方法：在CCE控制台中，单击左侧栏目树中的<span class="uicontrol" id="uicontrol352753584520"><a name="uicontrol352753584520"></a><a name="uicontrol352753584520"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol1527103511453"><a name="uicontrol1527103511453"></a><a name="uicontrol1527103511453"></a>“对象存储卷”</span>页签下单击PVC的名称，在PVC详情页的<span class="uicontrol" id="uicontrol5527235154518"><a name="uicontrol5527235154518"></a><a name="uicontrol5527235154518"></a>“PV详情”</span>页签下复制<span class="uicontrol" id="uicontrol135274356453"><a name="uicontrol135274356453"></a><a name="uicontrol135274356453"></a>“PV名称”</span>后的内容即可。</p>
    </td>
    </tr>
    <tr id="row203291940144319"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p4330114084310"><a name="p4330114084310"></a><a name="p4330114084310"></a>storage</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p183313401430"><a name="p183313401430"></a><a name="p183313401430"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
    </td>
    </tr>
    <tr id="row833154011434"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p8331174074312"><a name="p8331174074312"></a><a name="p8331174074312"></a>storageClassName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1733111407435"><a name="p1733111407435"></a><a name="p1733111407435"></a>对象存储支持的存储类型，包括obs-standard（标准）、obs-standard-ia（低频）。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **PVC yaml文件配置示例：**

    ```
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      annotations:
        volume.beta.kubernetes.io/storage-class: obs-standard
        volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxiobs
      name: pvc-obs-example
      namespace: default
    spec:
      accessModes:
      - ReadWriteMany
      resources:
        requests:
          storage: 1Gi
      volumeName: pv-obs-example
    ```

    **表 4**  关键参数说明

    <a name="table19249175815503"></a>
    <table><thead align="left"><tr id="row1425005815020"><th class="cellrowborder" valign="top" width="37.356876810594564%" id="mcps1.2.3.1.1"><p id="p1525045817501"><a name="p1525045817501"></a><a name="p1525045817501"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="62.643123189405436%" id="mcps1.2.3.1.2"><p id="p162501858165014"><a name="p162501858165014"></a><a name="p162501858165014"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row725065865014"><td class="cellrowborder" valign="top" width="37.356876810594564%" headers="mcps1.2.3.1.1 "><p id="p152504582506"><a name="p152504582506"></a><a name="p152504582506"></a>volume.beta.kubernetes.io/storage-class</p>
    </td>
    <td class="cellrowborder" valign="top" width="62.643123189405436%" headers="mcps1.2.3.1.2 "><p id="p1425185812509"><a name="p1425185812509"></a><a name="p1425185812509"></a>对象存储支持的存储类型，包括obs-standard、obs-standard-ia。</p>
    </td>
    </tr>
    <tr id="row1025175814505"><td class="cellrowborder" valign="top" width="37.356876810594564%" headers="mcps1.2.3.1.1 "><p id="p1825125813505"><a name="p1825125813505"></a><a name="p1825125813505"></a>volume.beta.kubernetes.io/storage-provisioner</p>
    </td>
    <td class="cellrowborder" valign="top" width="62.643123189405436%" headers="mcps1.2.3.1.2 "><p id="p1825195895012"><a name="p1825195895012"></a><a name="p1825195895012"></a>必须使用flexvolume-huawei.com/fuxiobs。</p>
    </td>
    </tr>
    <tr id="row17251115805017"><td class="cellrowborder" valign="top" width="37.356876810594564%" headers="mcps1.2.3.1.1 "><p id="p2025185817509"><a name="p2025185817509"></a><a name="p2025185817509"></a>volumeName</p>
    </td>
    <td class="cellrowborder" valign="top" width="62.643123189405436%" headers="mcps1.2.3.1.2 "><p id="p9251125875017"><a name="p9251125875017"></a><a name="p9251125875017"></a>PV的名称。</p>
    </td>
    </tr>
    <tr id="row8251165845018"><td class="cellrowborder" valign="top" width="37.356876810594564%" headers="mcps1.2.3.1.1 "><p id="p22521858135013"><a name="p22521858135013"></a><a name="p22521858135013"></a>storage</p>
    </td>
    <td class="cellrowborder" valign="top" width="62.643123189405436%" headers="mcps1.2.3.1.2 "><p id="p1525285819508"><a name="p1525285819508"></a><a name="p1525285819508"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
    </td>
    </tr>
    </tbody>
    </table>


**K8S version = 1.9（1.9版本集群）**

-   <a name="li154036581589"></a>**PV yaml文件配置示例：**

    ```
    apiVersion: v1 
    kind: PersistentVolume 
    metadata: 
      name: pv-obs-example 
      namespace: default  
    spec: 
      accessModes: 
      - ReadWriteMany 
      capacity: 
        storage: 1Gi 
      flexVolume: 
        driver: huawei.com/fuxiobs 
        fsType: obs 
        options: 
          fsType: obs 
          kubernetes.io/namespace: default 
          region: cn-north-4 
          storage_class: STANDARD 
          volumeID: test-obs 
      persistentVolumeReclaimPolicy: Delete 
      storageClassName: obs-standard
    ```

    **表 5**  关键参数说明

    <a name="table1940115586588"></a>
    <table><thead align="left"><tr id="row10400145816580"><th class="cellrowborder" valign="top" width="26.42980935875217%" id="mcps1.2.3.1.1"><p id="p1840065885817"><a name="p1840065885817"></a><a name="p1840065885817"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="73.57019064124783%" id="mcps1.2.3.1.2"><p id="p64001058145818"><a name="p64001058145818"></a><a name="p64001058145818"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row164002584588"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p44009581587"><a name="p44009581587"></a><a name="p44009581587"></a>driver</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p740075825813"><a name="p740075825813"></a><a name="p740075825813"></a>挂载依赖的存储驱动，对象存储配置为“huawei.com/fuxiobs”。</p>
    </td>
    </tr>
    <tr id="row6400165875813"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p1340075815814"><a name="p1340075815814"></a><a name="p1340075815814"></a>storage_class</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1840015819589"><a name="p1840015819589"></a><a name="p1840015819589"></a>存储类型，包括STANDARD（标准桶）、STANDARD_IA（低频访问桶）。</p>
    </td>
    </tr>
    <tr id="row7400175895815"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p74008588581"><a name="p74008588581"></a><a name="p74008588581"></a>region</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p16400165817587"><a name="p16400165817587"></a><a name="p16400165817587"></a>对象存储所在的region。具体请参见<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。</p>
    </td>
    </tr>
    <tr id="row10401758105816"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p124003586586"><a name="p124003586586"></a><a name="p124003586586"></a>volumeID</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1401165813584"><a name="p1401165813584"></a><a name="p1401165813584"></a>对象存储的桶名称。</p>
    <p id="p8401155845819"><a name="p8401155845819"></a><a name="p8401155845819"></a>获取方法：在CCE控制台中，单击左侧栏目树中的<span class="uicontrol" id="uicontrol10401145835812"><a name="uicontrol10401145835812"></a><a name="uicontrol10401145835812"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol940195855818"><a name="uicontrol940195855818"></a><a name="uicontrol940195855818"></a>“对象存储卷”</span>页签下单击PVC的名称，在PVC详情页的<span class="uicontrol" id="uicontrol240175885817"><a name="uicontrol240175885817"></a><a name="uicontrol240175885817"></a>“PV详情”</span>页签下复制<span class="uicontrol" id="uicontrol34011658155818"><a name="uicontrol34011658155818"></a><a name="uicontrol34011658155818"></a>“PV名称”</span>后的内容即可。</p>
    </td>
    </tr>
    <tr id="row1240112584582"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p9401105845814"><a name="p9401105845814"></a><a name="p9401105845814"></a>storage</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p14401145814587"><a name="p14401145814587"></a><a name="p14401145814587"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
    </td>
    </tr>
    <tr id="row5401175812585"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p1401195816581"><a name="p1401195816581"></a><a name="p1401195816581"></a>storageClassName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p164013584586"><a name="p164013584586"></a><a name="p164013584586"></a>对象存储支持的存储类型，包括obs-standard（标准）、obs-standard-ia（低频）。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **PVC yaml文件配置示例：**

    ```
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      annotations:
        volume.beta.kubernetes.io/storage-class: obs-standard
        volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxiobs
      name: pvc-obs-example
      namespace: default
    spec:
      accessModes:
      - ReadWriteMany
      resources:
        requests:
          storage: 1Gi
      volumeName: pv-obs-example
      volumeNamespace: default
    ```

    **表 6**  关键参数说明

    <a name="table19403105818582"></a>
    <table><thead align="left"><tr id="row1140216585581"><th class="cellrowborder" valign="top" width="36.74125874125874%" id="mcps1.2.3.1.1"><p id="p1402658115814"><a name="p1402658115814"></a><a name="p1402658115814"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="63.25874125874126%" id="mcps1.2.3.1.2"><p id="p240210586584"><a name="p240210586584"></a><a name="p240210586584"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row040235815582"><td class="cellrowborder" valign="top" width="36.74125874125874%" headers="mcps1.2.3.1.1 "><p id="p1640212587584"><a name="p1640212587584"></a><a name="p1640212587584"></a>volume.beta.kubernetes.io/storage-class</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.25874125874126%" headers="mcps1.2.3.1.2 "><p id="p240285855820"><a name="p240285855820"></a><a name="p240285855820"></a>对象存储支持的存储类型，包括obs-standard、obs-standard-ia。</p>
    </td>
    </tr>
    <tr id="row1040216587588"><td class="cellrowborder" valign="top" width="36.74125874125874%" headers="mcps1.2.3.1.1 "><p id="p4402125810586"><a name="p4402125810586"></a><a name="p4402125810586"></a>volume.beta.kubernetes.io/storage-provisioner</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.25874125874126%" headers="mcps1.2.3.1.2 "><p id="p440245815818"><a name="p440245815818"></a><a name="p440245815818"></a>必须使用flexvolume-huawei.com/fuxiobs。</p>
    </td>
    </tr>
    <tr id="row1640245845818"><td class="cellrowborder" valign="top" width="36.74125874125874%" headers="mcps1.2.3.1.1 "><p id="p10402175816583"><a name="p10402175816583"></a><a name="p10402175816583"></a>volumeName</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.25874125874126%" headers="mcps1.2.3.1.2 "><p id="p14402125817583"><a name="p14402125817583"></a><a name="p14402125817583"></a>PV的名称。</p>
    </td>
    </tr>
    <tr id="row24021658155817"><td class="cellrowborder" valign="top" width="36.74125874125874%" headers="mcps1.2.3.1.1 "><p id="p2402125819582"><a name="p2402125819582"></a><a name="p2402125819582"></a>storage</p>
    </td>
    <td class="cellrowborder" valign="top" width="63.25874125874126%" headers="mcps1.2.3.1.2 "><p id="p44022582583"><a name="p44022582583"></a><a name="p44022582583"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
    </td>
    </tr>
    </tbody>
    </table>


