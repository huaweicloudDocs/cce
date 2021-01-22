# 使用kubectl对接已有极速文件存储卷<a name="cce_01_0272"></a>

-   [操作场景](#section1062914713566)
-   [操作步骤](#section1530655595611)
-   [历史版本示例](#section7169123192317)

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的极速文件存储来创建PersistentVolume，创建成功后，通过创建相应的PersistentVolumeClaim来绑定当前的PersistentVolume使用。

## 操作步骤<a name="section1530655595611"></a>

1.  登录SFS控制台，创建一个文件存储，记录文件存储的ID、共享路径和容量。
2.  请参见[通过kubectl或web-terminal插件操作CCE集群](通过kubectl或web-terminal插件操作CCE集群.md)配置kubectl命令。
3.  新建两个yaml文件，用于创建PersistentVolume（PV）、PersistentVolumeClaim（PVC）。假设文件名分别为**pv-efs-example.yaml**、**pvc-efs-example.yaml**。

    **touch pv-efs-example.yaml** **pvc-efs-example.yaml**

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
    <td class="cellrowborder" valign="top" width="31.453145314531454%" headers="mcps1.1.4.1.3 "><p id="p13431164173218"><a name="p13431164173218"></a><a name="p13431164173218"></a>请参见<a href="#li14207124318108">1.15+ yaml文件配置示例</a></p>
    </td>
    </tr>
    <tr id="row132483424343"><td class="cellrowborder" valign="top" width="33.2033203320332%" headers="mcps1.1.4.1.1 "><p id="p102481242133410"><a name="p102481242133410"></a><a name="p102481242133410"></a>K8S version ≤ 1.13</p>
    </td>
    <td class="cellrowborder" valign="top" width="35.34353435343534%" headers="mcps1.1.4.1.2 "><p id="p1524819427346"><a name="p1524819427346"></a><a name="p1524819427346"></a>1.13及之前版本的集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.453145314531454%" headers="mcps1.1.4.1.3 "><p id="p16248134217345"><a name="p16248134217345"></a><a name="p16248134217345"></a>请参见<a href="#li17576947171010">1.13- yaml文件配置示例</a></p>
    </td>
    </tr>
    </tbody>
    </table>

    **1.15+（1.15及以上版本的集群）**

    -   <a name="li14207124318108"></a>**vi pv-efs-example.yaml**

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
        <table><thead align="left"><tr id="row1666206115"><th class="cellrowborder" valign="top" width="35.89033508723345%" id="mcps1.2.3.1.1"><p id="p1662017116"><a name="p1662017116"></a><a name="p1662017116"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="64.10966491276655%" id="mcps1.2.3.1.2"><p id="p56820513"><a name="p56820513"></a><a name="p56820513"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1061620713"><td class="cellrowborder" valign="top" width="35.89033508723345%" headers="mcps1.2.3.1.1 "><p id="p56120115"><a name="p56120115"></a><a name="p56120115"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.10966491276655%" headers="mcps1.2.3.1.2 "><p id="p911192017111"><a name="p911192017111"></a><a name="p911192017111"></a>挂载依赖的存储驱动，极速文件存储配置为“sfsturbo.csi.everest.io”。</p>
        </td>
        </tr>
        <tr id="row6115201810"><td class="cellrowborder" valign="top" width="35.89033508723345%" headers="mcps1.2.3.1.1 "><p id="p1911172013115"><a name="p1911172013115"></a><a name="p1911172013115"></a>everest.io/share-export-location</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.10966491276655%" headers="mcps1.2.3.1.2 "><p id="p1812132017111"><a name="p1812132017111"></a><a name="p1812132017111"></a>极速文件存储的共享路径。</p>
        </td>
        </tr>
        <tr id="row181217201317"><td class="cellrowborder" valign="top" width="35.89033508723345%" headers="mcps1.2.3.1.1 "><p id="p2127205115"><a name="p2127205115"></a><a name="p2127205115"></a>volumeHandle</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.10966491276655%" headers="mcps1.2.3.1.2 "><p id="p331414324103"><a name="p331414324103"></a><a name="p331414324103"></a>极速文件存储的ID。</p>
        <p id="p1455172961010"><a name="p1455172961010"></a><a name="p1455172961010"></a>获取方法：在CCE控制台中，单击左侧栏目树中的<span class="uicontrol" id="uicontrol645510295108"><a name="uicontrol645510295108"></a><a name="uicontrol645510295108"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol114557292102"><a name="uicontrol114557292102"></a><a name="uicontrol114557292102"></a>“极速文件存储卷”</span>页签下单击PVC的名称，在PVC详情页中复制<span class="uicontrol" id="uicontrol16455162911015"><a name="uicontrol16455162911015"></a><a name="uicontrol16455162911015"></a>“PVC UID”</span>后的内容即可。</p>
        </td>
        </tr>
        <tr id="row101220201616"><td class="cellrowborder" valign="top" width="35.89033508723345%" headers="mcps1.2.3.1.1 "><p id="p4121201717"><a name="p4121201717"></a><a name="p4121201717"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.10966491276655%" headers="mcps1.2.3.1.2 "><p id="p1373713106118"><a name="p1373713106118"></a><a name="p1373713106118"></a>文件存储的大小。</p>
        </td>
        </tr>
        <tr id="row118294312105"><td class="cellrowborder" valign="top" width="35.89033508723345%" headers="mcps1.2.3.1.1 "><p id="p16741643171012"><a name="p16741643171012"></a><a name="p16741643171012"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="64.10966491276655%" headers="mcps1.2.3.1.2 "><p id="p127424310105"><a name="p127424310105"></a><a name="p127424310105"></a>指定k8s storage class名称；极速文件存储卷需配置为"csi-sfsturbo”。</p>
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
        <table><thead align="left"><tr id="row1432192381417"><th class="cellrowborder" valign="top" width="31.933968976803754%" id="mcps1.2.3.1.1"><p id="p18433152391413"><a name="p18433152391413"></a><a name="p18433152391413"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="68.06603102319625%" id="mcps1.2.3.1.2"><p id="p19433192321419"><a name="p19433192321419"></a><a name="p19433192321419"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row164331623191417"><td class="cellrowborder" valign="top" width="31.933968976803754%" headers="mcps1.2.3.1.1 "><p id="p20433112371413"><a name="p20433112371413"></a><a name="p20433112371413"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="68.06603102319625%" headers="mcps1.2.3.1.2 "><p id="p6433142314144"><a name="p6433142314144"></a><a name="p6433142314144"></a>指定k8s storage class名称；需配置为"csi-sfsturbo”。</p>
        </td>
        </tr>
        <tr id="row184341223131415"><td class="cellrowborder" valign="top" width="31.933968976803754%" headers="mcps1.2.3.1.1 "><p id="p16434623161416"><a name="p16434623161416"></a><a name="p16434623161416"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="68.06603102319625%" headers="mcps1.2.3.1.2 "><p id="p4434102301418"><a name="p4434102301418"></a><a name="p4434102301418"></a>存储容量，单位Gi，必须和已有pv的storage大小保持一致。</p>
        </td>
        </tr>
        <tr id="row20434023121415"><td class="cellrowborder" valign="top" width="31.933968976803754%" headers="mcps1.2.3.1.1 "><p id="p1743410236141"><a name="p1743410236141"></a><a name="p1743410236141"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="68.06603102319625%" headers="mcps1.2.3.1.2 "><p id="p3435182316146"><a name="p3435182316146"></a><a name="p3435182316146"></a>PV的名称。</p>
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


## 历史版本示例<a name="section7169123192317"></a>

**K8S version ≤ 1.13（1.13及之前版本集群）**

-   <a name="li17576947171010"></a>**PV yaml文件配置示例如下：**

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
      flexVolume: 
        driver: huawei.com/fuxiefs 
        fsType: efs 
        options: 
          deviceMountPath: 192.168.0.169:/ 
          fsType: efs 
          volumeID: 8962a2a2-a583-4b7f-bb74-fe76712d8414 
      persistentVolumeReclaimPolicy: Delete 
      storageClassName: efs-standard
    ```

    **表 3**  关键参数说明

    <a name="table1857613471103"></a>
    <table><thead align="left"><tr id="row65751147161014"><th class="cellrowborder" valign="top" width="32.3169894245296%" id="mcps1.2.3.1.1"><p id="p10575114719102"><a name="p10575114719102"></a><a name="p10575114719102"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="67.6830105754704%" id="mcps1.2.3.1.2"><p id="p1357534717101"><a name="p1357534717101"></a><a name="p1357534717101"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row15756477108"><td class="cellrowborder" valign="top" width="32.3169894245296%" headers="mcps1.2.3.1.1 "><p id="p1557564718103"><a name="p1557564718103"></a><a name="p1557564718103"></a>driver</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.6830105754704%" headers="mcps1.2.3.1.2 "><p id="p2575114791013"><a name="p2575114791013"></a><a name="p2575114791013"></a>挂载依赖的存储驱动，极速文件存储配置为“huawei.com/fuxiefs”。</p>
    </td>
    </tr>
    <tr id="row5575134713108"><td class="cellrowborder" valign="top" width="32.3169894245296%" headers="mcps1.2.3.1.1 "><p id="p8575164721010"><a name="p8575164721010"></a><a name="p8575164721010"></a>deviceMountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.6830105754704%" headers="mcps1.2.3.1.2 "><p id="p8575124761010"><a name="p8575124761010"></a><a name="p8575124761010"></a>极速文件存储的共享路径。</p>
    </td>
    </tr>
    <tr id="row957514731018"><td class="cellrowborder" valign="top" width="32.3169894245296%" headers="mcps1.2.3.1.1 "><p id="p115758475102"><a name="p115758475102"></a><a name="p115758475102"></a>volumeID</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.6830105754704%" headers="mcps1.2.3.1.2 "><p id="p205751747141012"><a name="p205751747141012"></a><a name="p205751747141012"></a>极速文件存储的ID。</p>
    <p id="p14575124751019"><a name="p14575124751019"></a><a name="p14575124751019"></a>获取方法：在CCE控制台中，单击左侧栏目树中的<span class="uicontrol" id="uicontrol457515472101"><a name="uicontrol457515472101"></a><a name="uicontrol457515472101"></a>“资源管理-存储管理”</span>，在<span class="uicontrol" id="uicontrol9575154731010"><a name="uicontrol9575154731010"></a><a name="uicontrol9575154731010"></a>“极速文件存储卷”</span>页签下单击PVC的名称，在PVC详情页中复制<span class="uicontrol" id="uicontrol9575154716101"><a name="uicontrol9575154716101"></a><a name="uicontrol9575154716101"></a>“PVC UID”</span>后的内容即可。</p>
    </td>
    </tr>
    <tr id="row75761347101016"><td class="cellrowborder" valign="top" width="32.3169894245296%" headers="mcps1.2.3.1.1 "><p id="p18575147131016"><a name="p18575147131016"></a><a name="p18575147131016"></a>storage</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.6830105754704%" headers="mcps1.2.3.1.2 "><p id="p115751479106"><a name="p115751479106"></a><a name="p115751479106"></a>文件存储的大小。</p>
    </td>
    </tr>
    <tr id="row2057617470102"><td class="cellrowborder" valign="top" width="32.3169894245296%" headers="mcps1.2.3.1.1 "><p id="p557614715108"><a name="p557614715108"></a><a name="p557614715108"></a>storageClassName</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.6830105754704%" headers="mcps1.2.3.1.2 "><p id="p45761947201014"><a name="p45761947201014"></a><a name="p45761947201014"></a>极速文件存储支持的卷类型，当前支持efs-standard、efs-performance（目前SFS Turbo不支持动态创建，所以此参数后续没有使用）。</p>
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

    **表 4**  关键参数说明

    <a name="table1739110557150"></a>
    <table><thead align="left"><tr id="row439135512158"><th class="cellrowborder" valign="top" width="39.462480042575834%" id="mcps1.2.3.1.1"><p id="p11391105571516"><a name="p11391105571516"></a><a name="p11391105571516"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="60.53751995742416%" id="mcps1.2.3.1.2"><p id="p439255513157"><a name="p439255513157"></a><a name="p439255513157"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row739215556154"><td class="cellrowborder" valign="top" width="39.462480042575834%" headers="mcps1.2.3.1.1 "><p id="p3131325191618"><a name="p3131325191618"></a><a name="p3131325191618"></a>volume.beta.kubernetes.io/storage-class</p>
    </td>
    <td class="cellrowborder" valign="top" width="60.53751995742416%" headers="mcps1.2.3.1.2 "><p id="p23923555150"><a name="p23923555150"></a><a name="p23923555150"></a>文件存储支持的读写方式，支持efs-standard、efs-performance。必须和已有PV保持一致。</p>
    </td>
    </tr>
    <tr id="row18143134041612"><td class="cellrowborder" valign="top" width="39.462480042575834%" headers="mcps1.2.3.1.1 "><p id="p11431840161611"><a name="p11431840161611"></a><a name="p11431840161611"></a>volume.beta.kubernetes.io/storage-provisioner</p>
    </td>
    <td class="cellrowborder" valign="top" width="60.53751995742416%" headers="mcps1.2.3.1.2 "><p id="p714434016164"><a name="p714434016164"></a><a name="p714434016164"></a>必须使用flexvolume-huawei.com/fuxiefs。</p>
    </td>
    </tr>
    <tr id="row1339295514152"><td class="cellrowborder" valign="top" width="39.462480042575834%" headers="mcps1.2.3.1.1 "><p id="p83921559156"><a name="p83921559156"></a><a name="p83921559156"></a>storage</p>
    </td>
    <td class="cellrowborder" valign="top" width="60.53751995742416%" headers="mcps1.2.3.1.2 "><p id="p1839395518152"><a name="p1839395518152"></a><a name="p1839395518152"></a>存储容量，单位Gi，必须和已有pv的storage大小保持一致。</p>
    </td>
    </tr>
    <tr id="row1339365571519"><td class="cellrowborder" valign="top" width="39.462480042575834%" headers="mcps1.2.3.1.1 "><p id="p239365513155"><a name="p239365513155"></a><a name="p239365513155"></a>volumeName</p>
    </td>
    <td class="cellrowborder" valign="top" width="60.53751995742416%" headers="mcps1.2.3.1.2 "><p id="p10393455131513"><a name="p10393455131513"></a><a name="p10393455131513"></a>PV的名称。</p>
    </td>
    </tr>
    </tbody>
    </table>


