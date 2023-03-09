# 使用kubectl对接已有对象存储<a name="cce_10_0326"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的对象存储来创建PersistentVolume，并通过创建对应PersistentVolumeClaim绑定当前PersistentVolume使用。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.13及以下版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  登录OBS控制台，创建对象存储桶，记录桶名称和存储类型。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建两个yaml文件，用于创建PersistentVolume（PV）、PersistentVolumeClaim（PVC），假设文件名为**pv-obs-example.yaml、pvc-obs-example.yaml。**

    **touch pv-obs-example.yaml** **pvc-obs-example.yaml**

    <a name="table184303411324"></a>
    <table><thead align="left"><tr id="row104311415322"><th class="cellrowborder" valign="top" width="33.2033203320332%" id="mcps1.1.4.1.1"><p id="p443118443220"><a name="p443118443220"></a><a name="p443118443220"></a>K8s集群版本（K8s version）</p>
    </th>
    <th class="cellrowborder" valign="top" width="35.34353435343534%" id="mcps1.1.4.1.2"><p id="p1431154113212"><a name="p1431154113212"></a><a name="p1431154113212"></a>说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="31.453145314531454%" id="mcps1.1.4.1.3"><p id="p14311346322"><a name="p14311346322"></a><a name="p14311346322"></a>yaml示例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row543118415321"><td class="cellrowborder" valign="top" width="33.2033203320332%" headers="mcps1.1.4.1.1 "><p id="p1743111463216"><a name="p1743111463216"></a><a name="p1743111463216"></a>1.11 ≤ K8s version ≤ 1.13</p>
    </td>
    <td class="cellrowborder" valign="top" width="35.34353435343534%" headers="mcps1.1.4.1.2 "><p id="p743119413320"><a name="p743119413320"></a><a name="p743119413320"></a>1.11以上及1.13版本集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.453145314531454%" headers="mcps1.1.4.1.3 "><p id="p13431246327"><a name="p13431246327"></a><a name="p13431246327"></a>请参见<a href="#li45671840132016">1.11~1.13 yaml文件配置示例</a></p>
    </td>
    </tr>
    <tr id="row72981940163417"><td class="cellrowborder" valign="top" width="33.2033203320332%" headers="mcps1.1.4.1.1 "><p id="p9298154043420"><a name="p9298154043420"></a><a name="p9298154043420"></a>K8s version = 1.9</p>
    </td>
    <td class="cellrowborder" valign="top" width="35.34353435343534%" headers="mcps1.1.4.1.2 "><p id="p1729814407349"><a name="p1729814407349"></a><a name="p1729814407349"></a>1.9版本集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.453145314531454%" headers="mcps1.1.4.1.3 "><p id="p529834014349"><a name="p529834014349"></a><a name="p529834014349"></a>请参见<a href="#li154036581589">1.9 yaml文件配置示例</a></p>
    </td>
    </tr>
    </tbody>
    </table>

    **1.11 ≤ K8s version ≤ 1.13（1.11以上及1.13版本集群）**

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
          claimRef:
            apiVersion: v1
            kind: PersistentVolumeClaim
            name: pvc-obs-example
            namespace: default
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

        **表 1**  关键参数说明

        <a name="table832713405430"></a>
        <table><thead align="left"><tr id="row53276406434"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p15327134014433"><a name="p15327134014433"></a><a name="p15327134014433"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p133274408432"><a name="p133274408432"></a><a name="p133274408432"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row432714020436"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p13328540134319"><a name="p13328540134319"></a><a name="p13328540134319"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1032814074320"><a name="p1032814074320"></a><a name="p1032814074320"></a>挂载依赖的存储驱动，对象存储配置为“huawei.com/fuxiobs”。</p>
        </td>
        </tr>
        <tr id="row132834014431"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p13979181319442"><a name="p13979181319442"></a><a name="p13979181319442"></a>storage_class</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p83281740134319"><a name="p83281740134319"></a><a name="p83281740134319"></a>存储类型，包括STANDARD（标准桶）、STANDARD_IA（低频访问桶）。</p>
        </td>
        </tr>
        <tr id="row1332819409437"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p997612588441"><a name="p997612588441"></a><a name="p997612588441"></a>region</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p173851644195213"><a name="p173851644195213"></a><a name="p173851644195213"></a>集群所在的region。</p>
        </td>
        </tr>
        <tr id="row5328440194311"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p143286409433"><a name="p143286409433"></a><a name="p143286409433"></a>volumeID</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1676410385454"><a name="p1676410385454"></a><a name="p1676410385454"></a>对象存储的桶名称。</p>
        <p id="p35271835134519"><a name="p35271835134519"></a><a name="p35271835134519"></a>获取方法：在CCE控制台，单击左侧栏目树中的<span class="uicontrol" id="uicontrol352753584520"><a name="uicontrol352753584520"></a><a name="uicontrol352753584520"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol1527103511453"><a name="uicontrol1527103511453"></a><a name="uicontrol1527103511453"></a>“对象存储卷”</span>页签下单击PVC的名称，在PVC详情页的<span class="uicontrol" id="uicontrol5527235154518"><a name="uicontrol5527235154518"></a><a name="uicontrol5527235154518"></a>“PV详情”</span>页签下复制<span class="uicontrol" id="uicontrol135274356453"><a name="uicontrol135274356453"></a><a name="uicontrol135274356453"></a>“PV名称”</span>后的内容即可。</p>
        </td>
        </tr>
        <tr id="row203291940144319"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p4330114084310"><a name="p4330114084310"></a><a name="p4330114084310"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p183313401430"><a name="p183313401430"></a><a name="p183313401430"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
        </td>
        </tr>
        <tr id="row833154011434"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p8331174074312"><a name="p8331174074312"></a><a name="p8331174074312"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1733111407435"><a name="p1733111407435"></a><a name="p1733111407435"></a>对象存储支持的存储类型，包括obs-standard（标准）、obs-standard-ia（低频）。</p>
        </td>
        </tr>
        <tr id="row211494345516"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p20114194315517"><a name="p20114194315517"></a><a name="p20114194315517"></a>spec.claimRef.apiVersion</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1211412438557"><a name="p1211412438557"></a><a name="p1211412438557"></a>固定值"v1"。</p>
        </td>
        </tr>
        <tr id="row16358204720552"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p123581247115512"><a name="p123581247115512"></a><a name="p123581247115512"></a>spec.claimRef.kind</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p3358647155515"><a name="p3358647155515"></a><a name="p3358647155515"></a>固定值"PersistentVolumeClaim"。</p>
        </td>
        </tr>
        <tr id="row149212505557"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p13921250125513"><a name="p13921250125513"></a><a name="p13921250125513"></a>spec.claimRef.name</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p13921195013554"><a name="p13921195013554"></a><a name="p13921195013554"></a>与下一步创建的pvc的name一致。</p>
        </td>
        </tr>
        <tr id="row38145495515"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p168205418552"><a name="p168205418552"></a><a name="p168205418552"></a>spec.claimRef.namespace</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1821854205512"><a name="p1821854205512"></a><a name="p1821854205512"></a>与下一步创建的pvc的namespace一致。</p>
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

        **表 2**  关键参数说明

        <a name="table19249175815503"></a>
        <table><thead align="left"><tr id="row1425005815020"><th class="cellrowborder" valign="top" width="37.36%" id="mcps1.2.3.1.1"><p id="p1525045817501"><a name="p1525045817501"></a><a name="p1525045817501"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="62.63999999999999%" id="mcps1.2.3.1.2"><p id="p162501858165014"><a name="p162501858165014"></a><a name="p162501858165014"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row725065865014"><td class="cellrowborder" valign="top" width="37.36%" headers="mcps1.2.3.1.1 "><p id="p152504582506"><a name="p152504582506"></a><a name="p152504582506"></a>volume.beta.kubernetes.io/storage-class</p>
        </td>
        <td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.3.1.2 "><p id="p1425185812509"><a name="p1425185812509"></a><a name="p1425185812509"></a>对象存储支持的存储类型，包括obs-standard、obs-standard-ia。</p>
        </td>
        </tr>
        <tr id="row1025175814505"><td class="cellrowborder" valign="top" width="37.36%" headers="mcps1.2.3.1.1 "><p id="p1825125813505"><a name="p1825125813505"></a><a name="p1825125813505"></a>volume.beta.kubernetes.io/storage-provisioner</p>
        </td>
        <td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.3.1.2 "><p id="p1825195895012"><a name="p1825195895012"></a><a name="p1825195895012"></a>必须使用flexvolume-huawei.com/fuxiobs。</p>
        </td>
        </tr>
        <tr id="row17251115805017"><td class="cellrowborder" valign="top" width="37.36%" headers="mcps1.2.3.1.1 "><p id="p2025185817509"><a name="p2025185817509"></a><a name="p2025185817509"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.3.1.2 "><p id="p9251125875017"><a name="p9251125875017"></a><a name="p9251125875017"></a>PV的名称。</p>
        </td>
        </tr>
        <tr id="row8251165845018"><td class="cellrowborder" valign="top" width="37.36%" headers="mcps1.2.3.1.1 "><p id="p22521858135013"><a name="p22521858135013"></a><a name="p22521858135013"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.3.1.2 "><p id="p1525285819508"><a name="p1525285819508"></a><a name="p1525285819508"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
        </td>
        </tr>
        </tbody>
        </table>

    **K8s version = 1.9（1.9版本集群）**

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

        **表 3**  关键参数说明

        <a name="table1940115586588"></a>
        <table><thead align="left"><tr id="row10400145816580"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p1840065885817"><a name="p1840065885817"></a><a name="p1840065885817"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p64001058145818"><a name="p64001058145818"></a><a name="p64001058145818"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row164002584588"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p44009581587"><a name="p44009581587"></a><a name="p44009581587"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p740075825813"><a name="p740075825813"></a><a name="p740075825813"></a>挂载依赖的存储驱动，对象存储配置为“huawei.com/fuxiobs”。</p>
        </td>
        </tr>
        <tr id="row6400165875813"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1340075815814"><a name="p1340075815814"></a><a name="p1340075815814"></a>storage_class</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1840015819589"><a name="p1840015819589"></a><a name="p1840015819589"></a>存储类型，包括STANDARD（标准桶）、STANDARD_IA（低频访问桶）。</p>
        </td>
        </tr>
        <tr id="row7400175895815"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p74008588581"><a name="p74008588581"></a><a name="p74008588581"></a>region</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p281983218918"><a name="p281983218918"></a><a name="p281983218918"></a>集群所在的region。</p>
        </td>
        </tr>
        <tr id="row10401758105816"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p124003586586"><a name="p124003586586"></a><a name="p124003586586"></a>volumeID</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1401165813584"><a name="p1401165813584"></a><a name="p1401165813584"></a>对象存储的桶名称。</p>
        <p id="p8401155845819"><a name="p8401155845819"></a><a name="p8401155845819"></a>获取方法：在CCE控制台，单击左侧栏目树中的<span class="uicontrol" id="uicontrol10401145835812"><a name="uicontrol10401145835812"></a><a name="uicontrol10401145835812"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol940195855818"><a name="uicontrol940195855818"></a><a name="uicontrol940195855818"></a>“对象存储卷”</span>页签下单击PVC的名称，在PVC详情页的<span class="uicontrol" id="uicontrol240175885817"><a name="uicontrol240175885817"></a><a name="uicontrol240175885817"></a>“PV详情”</span>页签下复制<span class="uicontrol" id="uicontrol34011658155818"><a name="uicontrol34011658155818"></a><a name="uicontrol34011658155818"></a>“PV名称”</span>后的内容即可。</p>
        </td>
        </tr>
        <tr id="row1240112584582"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p9401105845814"><a name="p9401105845814"></a><a name="p9401105845814"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p14401145814587"><a name="p14401145814587"></a><a name="p14401145814587"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
        </td>
        </tr>
        <tr id="row5401175812585"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1401195816581"><a name="p1401195816581"></a><a name="p1401195816581"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p164013584586"><a name="p164013584586"></a><a name="p164013584586"></a>对象存储支持的存储类型，包括obs-standard（标准）、obs-standard-ia（低频）。</p>
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

        **表 4**  关键参数说明

        <a name="table19403105818582"></a>
        <table><thead align="left"><tr id="row1140216585581"><th class="cellrowborder" valign="top" width="36.74%" id="mcps1.2.3.1.1"><p id="p1402658115814"><a name="p1402658115814"></a><a name="p1402658115814"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="63.260000000000005%" id="mcps1.2.3.1.2"><p id="p240210586584"><a name="p240210586584"></a><a name="p240210586584"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row040235815582"><td class="cellrowborder" valign="top" width="36.74%" headers="mcps1.2.3.1.1 "><p id="p1640212587584"><a name="p1640212587584"></a><a name="p1640212587584"></a>volume.beta.kubernetes.io/storage-class</p>
        </td>
        <td class="cellrowborder" valign="top" width="63.260000000000005%" headers="mcps1.2.3.1.2 "><p id="p240285855820"><a name="p240285855820"></a><a name="p240285855820"></a>对象存储支持的存储类型，包括obs-standard、obs-standard-ia。</p>
        </td>
        </tr>
        <tr id="row1040216587588"><td class="cellrowborder" valign="top" width="36.74%" headers="mcps1.2.3.1.1 "><p id="p4402125810586"><a name="p4402125810586"></a><a name="p4402125810586"></a>volume.beta.kubernetes.io/storage-provisioner</p>
        </td>
        <td class="cellrowborder" valign="top" width="63.260000000000005%" headers="mcps1.2.3.1.2 "><p id="p440245815818"><a name="p440245815818"></a><a name="p440245815818"></a>必须使用flexvolume-huawei.com/fuxiobs。</p>
        </td>
        </tr>
        <tr id="row1640245845818"><td class="cellrowborder" valign="top" width="36.74%" headers="mcps1.2.3.1.1 "><p id="p10402175816583"><a name="p10402175816583"></a><a name="p10402175816583"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="63.260000000000005%" headers="mcps1.2.3.1.2 "><p id="p14402125817583"><a name="p14402125817583"></a><a name="p14402125817583"></a>PV的名称。</p>
        </td>
        </tr>
        <tr id="row24021658155817"><td class="cellrowborder" valign="top" width="36.74%" headers="mcps1.2.3.1.1 "><p id="p2402125819582"><a name="p2402125819582"></a><a name="p2402125819582"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="63.260000000000005%" headers="mcps1.2.3.1.2 "><p id="p44022582583"><a name="p44022582583"></a><a name="p44022582583"></a>存储容量，单位为Gi。此处配置为固定值1Gi。</p>
        </td>
        </tr>
        </tbody>
        </table>

4.  创建PV。

    **kubectl create -f pv-obs-example.yaml**

5.  创建PVC。

    **kubectl create -f pvc-obs-example.yaml**


