# 使用kubectl对接已有文件存储<a name="cce_01_0261"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的文件存储来创建PersistentVolume，创建成功后，通过创建相应的PersistentVolumeClaim来绑定当前的PersistentVolume使用。

## 前提条件<a name="section13181839131510"></a>

您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](Everest（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  登录SFS控制台，创建一个文件存储，记录文件存储的ID、共享路径和容量。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建两个yaml文件，用于创建PersistentVolume（PV）、PersistentVolumeClaim（PVC）。假设文件名分别为**pv-sfs-example.yaml**、**pvc-sfs-example.yaml**。

    **touch pv-sfs-example.yaml** **pvc-sfs-example.yaml**

    -   **vi pv-sfs-example.yaml**

        **PV yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolume
        metadata:
          name: pv-sfs-example
          annotations:
            pv.kubernetes.io/provisioned-by: everest-csi-provisioner
        spec:
          mountOptions:
          - hard
          - timeo=600
          - nolock
          accessModes:
          - ReadWriteMany
          capacity:
            storage: 10Gi
          claimRef:
            apiVersion: v1
            kind: PersistentVolumeClaim
            name: pvc-sfs-example
            namespace: default
          csi:
            driver: nas.csi.everest.io
            fsType: nfs
            volumeAttributes:
              everest.io/share-export-location: sfs-nas01.cn-north-4.myhuaweicloud.com:/share-436304e8 
              storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
            volumeHandle: 682f00bb-ace0-41d8-9b3e-913c9aa6b695
          persistentVolumeReclaimPolicy: Delete
          storageClassName: csi-nas
        ```

        **表 1**  关键参数说明

        <a name="table71355385813"></a>
        <table><thead align="left"><tr id="row141351434587"><th class="cellrowborder" valign="top" width="32.5%" id="mcps1.2.3.1.1"><p id="p151358385810"><a name="p151358385810"></a><a name="p151358385810"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="67.5%" id="mcps1.2.3.1.2"><p id="p7135331587"><a name="p7135331587"></a><a name="p7135331587"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row11351935589"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p12135334586"><a name="p12135334586"></a><a name="p12135334586"></a>driver</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p813603165815"><a name="p813603165815"></a><a name="p813603165815"></a>挂载依赖的存储驱动，文件存储配置为“nas.csi.everest.io”。</p>
        </td>
        </tr>
        <tr id="row1413614317585"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p1313610315580"><a name="p1313610315580"></a><a name="p1313610315580"></a>everest.io/share-export-location</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p1948318151509"><a name="p1948318151509"></a><a name="p1948318151509"></a>文件存储的共享路径。</p>
        <p id="p69251111300"><a name="p69251111300"></a><a name="p69251111300"></a>获取方法：在CCE控制台中，单击顶部的<span class="uicontrol" id="uicontrol3925211607"><a name="uicontrol3925211607"></a><a name="uicontrol3925211607"></a>“服务列表 &gt; 存储 &gt; 弹性文件服务”</span>，在弹性文件服务列表中可以看到<span class="uicontrol" id="uicontrol17925911606"><a name="uicontrol17925911606"></a><a name="uicontrol17925911606"></a>“挂载地址”</span>列，即为文件存储的共享路径，如<a href="#fig9360194915556">图1</a>。</p>
        </td>
        </tr>
        <tr id="row1713683175810"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p20136133145811"><a name="p20136133145811"></a><a name="p20136133145811"></a>volumeHandle</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p557443910014"><a name="p557443910014"></a><a name="p557443910014"></a>文件存储的ID。</p>
        <p id="p1182583515019"><a name="p1182583515019"></a><a name="p1182583515019"></a>获取方法：在CCE控制台中，单击顶部的<span class="uicontrol" id="uicontrol198251135202"><a name="uicontrol198251135202"></a><a name="uicontrol198251135202"></a>“服务列表 &gt; 存储 &gt; 弹性文件服务”</span>，在弹性文件服务列表中单击对应的弹性文件服务名称，在详情页中复制<span class="uicontrol" id="uicontrol1682513351503"><a name="uicontrol1682513351503"></a><a name="uicontrol1682513351503"></a>“ID”</span>后的内容即可。</p>
        </td>
        </tr>
        <tr id="row1513614311583"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p81361634589"><a name="p81361634589"></a><a name="p81361634589"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p21361134586"><a name="p21361134586"></a><a name="p21361134586"></a>文件存储的大小。</p>
        </td>
        </tr>
        <tr id="row1971411166119"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p186979167112"><a name="p186979167112"></a><a name="p186979167112"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p5697516413"><a name="p5697516413"></a><a name="p5697516413"></a>k8s storage class名称；需配置为"csi-nas"。</p>
        </td>
        </tr>
        <tr id="row161237179516"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p201237171151"><a name="p201237171151"></a><a name="p201237171151"></a>spec.mountOptions</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p1912313175512"><a name="p1912313175512"></a><a name="p1912313175512"></a>挂载参数。</p>
        <p id="p78621554981"><a name="p78621554981"></a><a name="p78621554981"></a>不设置时默认配置为如下配置，具体说明请参见<a href="设置挂载参数.md#section14888047833">文件存储挂载参数</a>。</p>
        <pre class="screen" id="screen1779155351116"><a name="screen1779155351116"></a><a name="screen1779155351116"></a>mountOptions:
        - vers=3
        - timeo=600
        - nolock
        - hard</pre>
        </td>
        </tr>
        <tr id="row658819374312"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p1058833703118"><a name="p1058833703118"></a><a name="p1058833703118"></a>spec.claimRef.apiVersion</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p258873719315"><a name="p258873719315"></a><a name="p258873719315"></a>固定值"v1"。</p>
        </td>
        </tr>
        <tr id="row2920113263210"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p992020326321"><a name="p992020326321"></a><a name="p992020326321"></a>spec.claimRef.kind</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p12920173273210"><a name="p12920173273210"></a><a name="p12920173273210"></a>固定值"PersistentVolumeClaim"。</p>
        </td>
        </tr>
        <tr id="row129025589324"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p3902105812328"><a name="p3902105812328"></a><a name="p3902105812328"></a>spec.claimRef.name</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p1390214584329"><a name="p1390214584329"></a><a name="p1390214584329"></a>pvc名称；与下一步创建的pvc的name一致。</p>
        </td>
        </tr>
        <tr id="row524722613348"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p12471526163420"><a name="p12471526163420"></a><a name="p12471526163420"></a>spec.claimRef.namespace</p>
        </td>
        <td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p1524792623415"><a name="p1524792623415"></a><a name="p1524792623415"></a>pvc的namespace；与下一步创建的pvc的namespace一致。</p>
        </td>
        </tr>
        </tbody>
        </table>

    -   **vi pvc-sfs-example.yaml**

        **PVC yaml文件配置示例：**

        ```
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          annotations:
            volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
          name: pvc-sfs-example
          namespace: default
        spec:
          accessModes:
          - ReadWriteMany
          resources:
            requests:
              storage: 10Gi
          storageClassName: csi-nas
          volumeName: pv-sfs-example
        ```

        **表 2**  关键参数说明

        <a name="table7611858765"></a>
        <table><thead align="left"><tr id="row18612583613"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p12610586618"><a name="p12610586618"></a><a name="p12610586618"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p106215587619"><a name="p106215587619"></a><a name="p106215587619"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row166316582064"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1993615311673"><a name="p1993615311673"></a><a name="p1993615311673"></a>storageClassName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p863175810616"><a name="p863175810616"></a><a name="p863175810616"></a>需配置为"csi-nas"。必须和已有PV保持一致。</p>
        </td>
        </tr>
        <tr id="row146495811614"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p56419580613"><a name="p56419580613"></a><a name="p56419580613"></a>storage</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p176415581165"><a name="p176415581165"></a><a name="p176415581165"></a>存储容量，单位Gi，必须和已有pv的storage大小保持一致。</p>
        </td>
        </tr>
        <tr id="row11641258763"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p20506155615718"><a name="p20506155615718"></a><a name="p20506155615718"></a>volumeName</p>
        </td>
        <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1765105811614"><a name="p1765105811614"></a><a name="p1765105811614"></a>PV的名称。</p>
        </td>
        </tr>
        </tbody>
        </table>

    **图 1**  弹性文件存储-共享路径<a name="fig9360194915556"></a>  
    ![](figures/弹性文件存储-共享路径.png "弹性文件存储-共享路径")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >文件存储所在VPC必须与工作负载规划部署的ECS虚拟机的VPC保持一致。

4.  创建PV。

    **kubectl create -f pv-sfs-example.yaml**

5.  创建PVC。

    **kubectl create -f pvc-sfs-example.yaml**


