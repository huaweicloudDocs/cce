# 使用kubectl对接已有文件存储<a name="cce_01_0319"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的文件存储来创建PersistentVolume，创建成功后，通过创建相应的PersistentVolumeClaim来绑定当前的PersistentVolume使用。

## 前提条件<a name="section1640173074515"></a>

您已经创建好一个CCE集群，并且在该集群中安装Flexvolume插件（[storage-driver](storage-driver（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.13及以下版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  登录SFS控制台，创建一个文件存储，记录文件存储的ID、共享路径和容量。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建两个yaml文件，用于创建PersistentVolume（PV）、PersistentVolumeClaim（PVC）。假设文件名分别为**pv-sfs-example.yaml**、**pvc-sfs-example.yaml**。

    **touch pv-sfs-example.yaml** **pvc-sfs-example.yaml**

    <a name="table184303411324"></a>
    <table><thead align="left"><tr id="row104311415322"><th class="cellrowborder" valign="top" width="33.2033203320332%" id="mcps1.1.4.1.1"><p id="p443118443220"><a name="p443118443220"></a><a name="p443118443220"></a>K8S集群版本（K8S version）</p>
    </th>
    <th class="cellrowborder" valign="top" width="35.34353435343534%" id="mcps1.1.4.1.2"><p id="p1431154113212"><a name="p1431154113212"></a><a name="p1431154113212"></a>说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="31.453145314531454%" id="mcps1.1.4.1.3"><p id="p14311346322"><a name="p14311346322"></a><a name="p14311346322"></a>yaml示例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row132483424343"><td class="cellrowborder" valign="top" width="33.2033203320332%" headers="mcps1.1.4.1.1 "><p id="p102481242133410"><a name="p102481242133410"></a><a name="p102481242133410"></a>1.11 ≤ K8S version &lt; 1.13</p>
    </td>
    <td class="cellrowborder" valign="top" width="35.34353435343534%" headers="mcps1.1.4.1.2 "><p id="p1524819427346"><a name="p1524819427346"></a><a name="p1524819427346"></a>1.11以上及1.13版本集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.453145314531454%" headers="mcps1.1.4.1.3 "><p id="p16248134217345"><a name="p16248134217345"></a><a name="p16248134217345"></a>请参见<a href="#li1252510101515">1.11~1.13 yaml文件配置示例</a></p>
    </td>
    </tr>
    <tr id="row72981940163417"><td class="cellrowborder" valign="top" width="33.2033203320332%" headers="mcps1.1.4.1.1 "><p id="p9298154043420"><a name="p9298154043420"></a><a name="p9298154043420"></a>K8S version = 1.9</p>
    </td>
    <td class="cellrowborder" valign="top" width="35.34353435343534%" headers="mcps1.1.4.1.2 "><p id="p1729814407349"><a name="p1729814407349"></a><a name="p1729814407349"></a>1.9版本集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.453145314531454%" headers="mcps1.1.4.1.3 "><p id="p529834014349"><a name="p529834014349"></a><a name="p529834014349"></a>请参见<a href="#li10858156164514">1.9 yaml文件配置示例</a></p>
    </td>
    </tr>
    </tbody>
    </table>

    **1.11 ≤ K8S version ≤ 1.13（1.11以上及1.13版本集群）**

    -   <a name="li1252510101515"></a>**PV yaml文件配置示例：**

        ```
        apiVersion: v1 
        kind: PersistentVolume 
        metadata: 
          name: pv-sfs-example 
          annotations:
            pv.kubernetes.io/provisioned-by: flexvolume-huawei.com/fuxinfs
        spec: 
          accessModes: 
          - ReadWriteMany 
          capacity: 
            storage: 10Gi 
          claimRef:
            apiVersion: v1
            kind: PersistentVolumeClaim
            name: pvc-sfs-example
            namespace: default
          flexVolume: 
            driver: huawei.com/fuxinfs 
            fsType: nfs 
            options: 
              deviceMountPath: <your_deviceMountPath>  #您的文件存储共享路径
              fsType: nfs 
              volumeID: f6976f9e-2493-419b-97ca-d7816008d91c 
          persistentVolumeReclaimPolicy: Delete 
          storageClassName: nfs-rw
        ```

        **表 1**  关键参数说明

        <a name="table3934731234"></a>
        <table><thead align="left"><tr id="row149341731534"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p149358311835"><a name="p149358311835"></a><a name="p149358311835"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p7935631739"><a name="p7935631739"></a><a name="p7935631739"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row793512311034"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p29357311432"><a name="p29357311432"></a><a name="p29357311432"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p49351131131"><a name="p49351131131"></a><a name="p49351131131"></a>挂载依赖的存储驱动，文件存储配置为“huawei.com/fuxinfs”。</p>
        </td>
        </tr>
        <tr id="row1093563112316"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p993515311335"><a name="p993515311335"></a><a name="p993515311335"></a>deviceMountPath</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p16935231434"><a name="p16935231434"></a><a name="p16935231434"></a>文件存储的共享路径。</p>
        <p id="p157371234845"><a name="p157371234845"></a><a name="p157371234845"></a>获取方法：在CCE控制台中，单击顶部的<span class="uicontrol" id="uicontrol1873715342418"><a name="uicontrol1873715342418"></a><a name="uicontrol1873715342418"></a>“服务列表 &gt; 存储 &gt; 弹性文件服务”</span>，在弹性文件服务列表中可以看到<span class="uicontrol" id="uicontrol37377341413"><a name="uicontrol37377341413"></a><a name="uicontrol37377341413"></a>“挂载地址”</span>列，即为文件存储的共享路径，如<a href="#fig9360194915556">图1</a>。</p>
        </td>
        </tr>
        <tr id="row993610311039"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p5936531137"><a name="p5936531137"></a><a name="p5936531137"></a>volumeID</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p2936133118317"><a name="p2936133118317"></a><a name="p2936133118317"></a>文件存储的ID。</p>
        <p id="p093612311432"><a name="p093612311432"></a><a name="p093612311432"></a>获取方法：在CCE控制台中，单击左侧栏目树中的<span class="uicontrol" id="uicontrol12857156545"><a name="uicontrol12857156545"></a><a name="uicontrol12857156545"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol1785725619411"><a name="uicontrol1785725619411"></a><a name="uicontrol1785725619411"></a>“文件存储卷”</span>页签下单击PVC的名称，在PVC详情页中复制<span class="uicontrol" id="uicontrol685718561642"><a name="uicontrol685718561642"></a><a name="uicontrol685718561642"></a>“PVC UID”</span>后的内容即可。</p>
        </td>
        </tr>
        <tr id="row093613116318"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p6936131332"><a name="p6936131332"></a><a name="p6936131332"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p893615311319"><a name="p893615311319"></a><a name="p893615311319"></a>文件存储的大小。</p>
        </td>
        </tr>
        <tr id="row1193611312034"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p129361313317"><a name="p129361313317"></a><a name="p129361313317"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p59361631933"><a name="p59361631933"></a><a name="p59361631933"></a>文件存储支持的读写方式，当前支持nfs-rw、nfs-ro。</p>
        </td>
        </tr>
        <tr id="row1513119244513"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p11313212457"><a name="p11313212457"></a><a name="p11313212457"></a>spec.claimRef.apiVersion</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p111311922456"><a name="p111311922456"></a><a name="p111311922456"></a>固定值"v1"。</p>
        </td>
        </tr>
        <tr id="row3844449452"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p28454434512"><a name="p28454434512"></a><a name="p28454434512"></a>spec.claimRef.kind</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p188452042450"><a name="p188452042450"></a><a name="p188452042450"></a>固定值"PersistentVolumeClaim"。</p>
        </td>
        </tr>
        <tr id="row1629208104518"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p112928815457"><a name="p112928815457"></a><a name="p112928815457"></a>spec.claimRef.name</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p9292178174514"><a name="p9292178174514"></a><a name="p9292178174514"></a>与下一步创建的pvc的name一致。</p>
        </td>
        </tr>
        <tr id="row15213155919448"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p42131059134414"><a name="p42131059134414"></a><a name="p42131059134414"></a>spec.claimRef.namespace</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p102136598446"><a name="p102136598446"></a><a name="p102136598446"></a>pvc的namespace；是下一步创建的pvc的namespace一致。</p>
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
            volume.beta.kubernetes.io/storage-class: nfs-rw
            volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxinfs
          name: pvc-sfs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 10Gi
          volumeName: pv-sfs-example
        ```

        **表 2**  关键参数说明

        <a name="table10792183512813"></a>
        <table><thead align="left"><tr id="row1879416351085"><th class="cellrowborder" valign="top" width="40.01%" id="mcps1.2.3.1.1"><p id="p1179416355820"><a name="p1179416355820"></a><a name="p1179416355820"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="59.99%" id="mcps1.2.3.1.2"><p id="p6794635582"><a name="p6794635582"></a><a name="p6794635582"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row8357105211816"><td class="cellrowborder" valign="top" width="40.01%" headers="mcps1.2.3.1.1 "><p id="p173577528812"><a name="p173577528812"></a><a name="p173577528812"></a>volume.beta.kubernetes.io/storage-class</p>
        </td>
        <td class="cellrowborder" valign="top" width="59.99%" headers="mcps1.2.3.1.2 "><p id="p491810248911"><a name="p491810248911"></a><a name="p491810248911"></a>文件存储支持的读写方式，支持nfs-rw 、nfs-ro。必须和已有PV保持一致。</p>
        </td>
        </tr>
        <tr id="row1269015485818"><td class="cellrowborder" valign="top" width="40.01%" headers="mcps1.2.3.1.1 "><p id="p1169111486814"><a name="p1169111486814"></a><a name="p1169111486814"></a>volume.beta.kubernetes.io/storage-provisioner</p>
        </td>
        <td class="cellrowborder" valign="top" width="59.99%" headers="mcps1.2.3.1.2 "><p id="p116929481812"><a name="p116929481812"></a><a name="p116929481812"></a>必须使用flexvolume-huawei.com/fuxinfs。</p>
        </td>
        </tr>
        <tr id="row37957351088"><td class="cellrowborder" valign="top" width="40.01%" headers="mcps1.2.3.1.1 "><p id="p15795735487"><a name="p15795735487"></a><a name="p15795735487"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="59.99%" headers="mcps1.2.3.1.2 "><p id="p19795153519813"><a name="p19795153519813"></a><a name="p19795153519813"></a>存储容量，单位Gi，必须和已有pv的storage大小保持一致。</p>
        </td>
        </tr>
        <tr id="row147951835388"><td class="cellrowborder" valign="top" width="40.01%" headers="mcps1.2.3.1.1 "><p id="p279512351189"><a name="p279512351189"></a><a name="p279512351189"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="59.99%" headers="mcps1.2.3.1.2 "><p id="p1179511352811"><a name="p1179511352811"></a><a name="p1179511352811"></a>PV的名称。</p>
        </td>
        </tr>
        </tbody>
        </table>

    **K8S version = 1.9（1.9版本集群）**

    -   <a name="li10858156164514"></a>**PV yaml文件配置示例：**

        ```
        apiVersion: v1 
        kind: PersistentVolume 
        metadata: 
          name: pv-sfs-example 
          namespace: default 
        spec: 
          accessModes: 
          - ReadWriteMany 
          capacity: 
            storage: 10Gi 
          flexVolume: 
            driver: huawei.com/fuxinfs 
            fsType: nfs 
            options: 
              deviceMountPath: <your_deviceMountPath>  #您的文件存储共享路径
              fsType: nfs 
              kubernetes.io/namespace: default 
              volumeID: f6976f9e-2493-419b-97ca-d7816008d91c 
          persistentVolumeReclaimPolicy: Delete 
          storageClassName: nfs-rw
        ```

        **表 3**  关键参数说明

        <a name="table28568561454"></a>
        <table><thead align="left"><tr id="row78551956154510"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p185565634512"><a name="p185565634512"></a><a name="p185565634512"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p1885512569451"><a name="p1885512569451"></a><a name="p1885512569451"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row17855656204514"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p685565614519"><a name="p685565614519"></a><a name="p685565614519"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p78551356174510"><a name="p78551356174510"></a><a name="p78551356174510"></a>挂载依赖的存储驱动，文件存储配置为“huawei.com/fuxinfs”。</p>
        </td>
        </tr>
        <tr id="row1856195610455"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p14855205674516"><a name="p14855205674516"></a><a name="p14855205674516"></a>deviceMountPath</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1685555619456"><a name="p1685555619456"></a><a name="p1685555619456"></a>文件存储的共享路径。</p>
        <p id="p4856155611458"><a name="p4856155611458"></a><a name="p4856155611458"></a>获取方法：在CCE控制台中，单击顶部的<span class="uicontrol" id="uicontrol15855115611455"><a name="uicontrol15855115611455"></a><a name="uicontrol15855115611455"></a>“服务列表 &gt; 存储 &gt; 弹性文件服务”</span>，在弹性文件服务列表中可以看到<span class="uicontrol" id="uicontrol1485635634510"><a name="uicontrol1485635634510"></a><a name="uicontrol1485635634510"></a>“挂载地址”</span>列，即为文件存储的共享路径，如<a href="#fig9360194915556">图1</a>。</p>
        </td>
        </tr>
        <tr id="row2856165619453"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1985610564458"><a name="p1985610564458"></a><a name="p1985610564458"></a>volumeID</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p12856155616454"><a name="p12856155616454"></a><a name="p12856155616454"></a>文件存储的ID。</p>
        <p id="p108561156184519"><a name="p108561156184519"></a><a name="p108561156184519"></a>获取方法：在CCE控制台中，单击左侧栏目树中的<span class="uicontrol" id="uicontrol188568563451"><a name="uicontrol188568563451"></a><a name="uicontrol188568563451"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol178562056204516"><a name="uicontrol178562056204516"></a><a name="uicontrol178562056204516"></a>“文件存储卷”</span>页签下单击PVC的名称，在PVC详情页中复制<span class="uicontrol" id="uicontrol5856105618457"><a name="uicontrol5856105618457"></a><a name="uicontrol5856105618457"></a>“PVC UID”</span>后的内容即可。</p>
        </td>
        </tr>
        <tr id="row1785665684516"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1856856174516"><a name="p1856856174516"></a><a name="p1856856174516"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p78566564458"><a name="p78566564458"></a><a name="p78566564458"></a>文件存储的大小。</p>
        </td>
        </tr>
        <tr id="row13856165614457"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p14856756134516"><a name="p14856756134516"></a><a name="p14856756134516"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p19856356124520"><a name="p19856356124520"></a><a name="p19856356124520"></a>文件存储支持的读写方式，当前支持nfs-rw、nfs-ro。</p>
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
            volume.beta.kubernetes.io/storage-class: nfs-rw
            volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxinfs
          name: pvc-sfs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 10Gi
          volumeName: pv-sfs-example
          volumeNamespace: default
        ```

        **表 4**  关键参数说明

        <a name="table585755619458"></a>
        <table><thead align="left"><tr id="row1585714564459"><th class="cellrowborder" valign="top" width="41.67%" id="mcps1.2.3.1.1"><p id="p18857175610459"><a name="p18857175610459"></a><a name="p18857175610459"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="58.330000000000005%" id="mcps1.2.3.1.2"><p id="p13857156104514"><a name="p13857156104514"></a><a name="p13857156104514"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row785735644514"><td class="cellrowborder" valign="top" width="41.67%" headers="mcps1.2.3.1.1 "><p id="p1785745654517"><a name="p1785745654517"></a><a name="p1785745654517"></a>volume.beta.kubernetes.io/storage-class</p>
        </td>
        <td class="cellrowborder" valign="top" width="58.330000000000005%" headers="mcps1.2.3.1.2 "><p id="p4857056104511"><a name="p4857056104511"></a><a name="p4857056104511"></a>文件存储支持的读写方式，支持nfs-rw 、nfs-ro。必须和已有PV保持一致。</p>
        </td>
        </tr>
        <tr id="row16857125615456"><td class="cellrowborder" valign="top" width="41.67%" headers="mcps1.2.3.1.1 "><p id="p1785715624516"><a name="p1785715624516"></a><a name="p1785715624516"></a>volume.beta.kubernetes.io/storage-provisioner</p>
        </td>
        <td class="cellrowborder" valign="top" width="58.330000000000005%" headers="mcps1.2.3.1.2 "><p id="p7857056174514"><a name="p7857056174514"></a><a name="p7857056174514"></a>必须使用flexvolume-huawei.com/fuxinfs。</p>
        </td>
        </tr>
        <tr id="row18857195644515"><td class="cellrowborder" valign="top" width="41.67%" headers="mcps1.2.3.1.1 "><p id="p1085711566457"><a name="p1085711566457"></a><a name="p1085711566457"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="58.330000000000005%" headers="mcps1.2.3.1.2 "><p id="p58571756174515"><a name="p58571756174515"></a><a name="p58571756174515"></a>存储容量，单位Gi，必须和已有pv的storage大小保持一致。</p>
        </td>
        </tr>
        <tr id="row98571856184519"><td class="cellrowborder" valign="top" width="41.67%" headers="mcps1.2.3.1.1 "><p id="p685720560459"><a name="p685720560459"></a><a name="p685720560459"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="58.330000000000005%" headers="mcps1.2.3.1.2 "><p id="p118572568450"><a name="p118572568450"></a><a name="p118572568450"></a>PV的名称。</p>
        </td>
        </tr>
        </tbody>
        </table>

    **图 1**  弹性文件存储-共享路径<a name="fig9360194915556"></a>  
    ![](figures/弹性文件存储-共享路径-33.png "弹性文件存储-共享路径-33")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >文件存储所在VPC必须与工作负载规划部署的ECS虚拟机的VPC保持一致。

4.  创建PV。

    **kubectl create -f pv-sfs-example.yaml**

5.  创建PVC。

    **kubectl create -f pvc-sfs-example.yaml**


