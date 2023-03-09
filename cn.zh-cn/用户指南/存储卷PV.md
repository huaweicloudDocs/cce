# 存储卷PV<a name="cce_10_0379"></a>

PV描述的是一个集群里的持久化存储卷，和节点一样，属于集群级别资源。

## 约束与限制<a name="section13324112843915"></a>

-   在新版控制台（需要将**集群升级到1.19.10及以上**并且**Everest存储插件升级到1.2.10及以上**）PV资源已经正式开放给用户管理；旧版控制台仍保持导入使用或者是通过动态创建方式进行创建，用户无法通过控制台对PV资源进行生命周期管理。
-   支持多个PV挂载同一个SFS或SFS Turbo，但有如下限制：
    -   多个不同的PVC/PV使用同一个底层SFS或SFS Turbo卷时，且被同一Pod使用会出现问题，需要避免这么使用。
    -   PV中persistentVolumeReclaimPolicy参数需设置为Retain，否则可能存在一个PV删除时，级联删除底层卷，其他关联这个底层卷的PV会由于底层存储不在了，使用出现异常。
    -   重复用底层存储时，建议在应用层做好多读多写的隔离保护，防止产生的数据覆盖和丢失。

-   通过YAML创建PV时，存储资源如果为包周期资源，YAML中的persistentVolumeReclaimPolicy字段请勿设置为Delete，否则可能导致级联删除异常。关于PV回收策略详情请参见[PV回收策略](#section19999142414413)。

## 存储卷访问模式<a name="section43881411172418"></a>

PV只能以底层存储资源所支持的方式挂载到宿主系统上。例如，文件存储可以支持多个节点读写，云硬盘只能被一个节点读写。

-   ReadWriteOnce：卷可以被一个节点以读写方式挂载，云硬盘存储卷支持此类型。
-   ReadWriteMany：卷可以被多个节点以读写方式挂载，文件存储、对象存储、极速文件存储支持此类型。

**表 1**  云存储支持访问模式

<a name="table773195654210"></a>
<table><thead align="left"><tr id="row773135617420"><th class="cellrowborder" valign="top" width="23.352335233523352%" id="mcps1.2.4.1.1"><p id="p10731155674211"><a name="p10731155674211"></a><a name="p10731155674211"></a>存储类型</p>
</th>
<th class="cellrowborder" valign="top" width="36.023602360236026%" id="mcps1.2.4.1.2"><p id="p12731115614425"><a name="p12731115614425"></a><a name="p12731115614425"></a>ReadWriteOnce</p>
</th>
<th class="cellrowborder" valign="top" width="40.624062406240625%" id="mcps1.2.4.1.3"><p id="p3731556114214"><a name="p3731556114214"></a><a name="p3731556114214"></a>ReadWriteMany</p>
</th>
</tr>
</thead>
<tbody><tr id="row773165604217"><td class="cellrowborder" valign="top" width="23.352335233523352%" headers="mcps1.2.4.1.1 "><p id="p12731185618427"><a name="p12731185618427"></a><a name="p12731185618427"></a>云硬盘EVS</p>
</td>
<td class="cellrowborder" valign="top" width="36.023602360236026%" headers="mcps1.2.4.1.2 "><p id="p87311956124218"><a name="p87311956124218"></a><a name="p87311956124218"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="40.624062406240625%" headers="mcps1.2.4.1.3 "><p id="p27311556164218"><a name="p27311556164218"></a><a name="p27311556164218"></a>×</p>
</td>
</tr>
<tr id="row17731956134214"><td class="cellrowborder" valign="top" width="23.352335233523352%" headers="mcps1.2.4.1.1 "><p id="p873115610428"><a name="p873115610428"></a><a name="p873115610428"></a>文件存储SFS</p>
</td>
<td class="cellrowborder" valign="top" width="36.023602360236026%" headers="mcps1.2.4.1.2 "><p id="p15731856104219"><a name="p15731856104219"></a><a name="p15731856104219"></a>×</p>
</td>
<td class="cellrowborder" valign="top" width="40.624062406240625%" headers="mcps1.2.4.1.3 "><p id="p1675417266441"><a name="p1675417266441"></a><a name="p1675417266441"></a>√</p>
</td>
</tr>
<tr id="row1873105654216"><td class="cellrowborder" valign="top" width="23.352335233523352%" headers="mcps1.2.4.1.1 "><p id="p12731125644217"><a name="p12731125644217"></a><a name="p12731125644217"></a>对象存储OBS</p>
</td>
<td class="cellrowborder" valign="top" width="36.023602360236026%" headers="mcps1.2.4.1.2 "><p id="p47311556184213"><a name="p47311556184213"></a><a name="p47311556184213"></a>×</p>
</td>
<td class="cellrowborder" valign="top" width="40.624062406240625%" headers="mcps1.2.4.1.3 "><p id="p12369172711443"><a name="p12369172711443"></a><a name="p12369172711443"></a>√</p>
</td>
</tr>
<tr id="row757122118433"><td class="cellrowborder" valign="top" width="23.352335233523352%" headers="mcps1.2.4.1.1 "><p id="p135713211435"><a name="p135713211435"></a><a name="p135713211435"></a>极速文件存储SFS Turbo</p>
</td>
<td class="cellrowborder" valign="top" width="36.023602360236026%" headers="mcps1.2.4.1.2 "><p id="p155713210434"><a name="p155713210434"></a><a name="p155713210434"></a>×</p>
</td>
<td class="cellrowborder" valign="top" width="40.624062406240625%" headers="mcps1.2.4.1.3 "><p id="p7960162715446"><a name="p7960162715446"></a><a name="p7960162715446"></a>√</p>
</td>
</tr>
</tbody>
</table>

## PV回收策略<a name="section19999142414413"></a>

PV回收策略用于指定删除PVC时，底层卷的回收策略，支持设定Delete、Retain回收策略。

-   Delete：删除PVC，PV资源与底层存储资源均被删除。
-   Retain：删除PVC，PV资源与底层存储资源均不会被删除，需要手动删除回收。PVC删除后PV资源状态为“已释放（Released）”，不能直接再次被PVC绑定使用。

Everest还支持一种删除PVC时不删除底层存储资源的使用方法，当前仅支持使用YAML创建。PV回收策略设置为Delete，添加annotations“everest.io/reclaim-policy: retain-volume-only”，这样删除PVC，PV会被删除，但底层存储资源会保留。

## 创建云硬盘EVS存储卷<a name="section12315152464120"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>创建EVS存储卷有如下要求。
>-   非系统盘，非专属盘，非共享盘。
>-   云硬盘类型为支持类型（普通IO，高IO，超高IO，通用SSD），云硬盘模式为 SCSI。
>-   云硬盘未冻结，云硬盘状态可用，云硬盘未被使用。
>-   若云硬盘加密，所使用的密钥状态需可用。

**使用控制台创建**

1.  登录CCE控制台。
2.  单击集群名称进入集群，在左侧选择“容器存储“，在右侧选择“存储卷“页签。
3.  单击右上角“创建存储卷“，在弹出的窗口中填写存储卷参数。
    -   存储卷类型：选择“云硬盘“。
    -   选择云硬盘。（仅支持选择集群所属企业项目和 default 企业项目下的云硬盘）。
    -   PV名称：输入PV名称。
    -   访问模式：ReadWriteOnce。
    -   回收策略：Delete或Retain，具体解释请参见[PV回收策略](#section19999142414413)。

4.  单击“创建“。

**使用YAML创建**

```
apiVersion: v1
kind: PersistentVolume
metadata:
  annotations:
    pv.kubernetes.io/provisioned-by: everest-csi-provisioner
    everest.io/reclaim-policy: retain-volume-only         # 可选字段，删除PV，保留底层存储卷
  name: cce-evs-test
  labels:
    failure-domain.beta.kubernetes.io/region: cn-north-4
    failure-domain.beta.kubernetes.io/zone: cn-north-4b
spec:
  accessModes:
    - ReadWriteOnce     # 访问模式，云硬盘必须为ReadWriteOnce
  capacity:
    storage: 10Gi       # 云硬盘的容量，单位为Gi，取值范围 1-32768
  csi:
    driver: disk.csi.everest.io     # 挂载依赖的存储驱动
    fsType: ext4
    volumeHandle: 459581af-e78c-4356-9e78-eaf9cd8525eb   #云硬盘的volumeID
    volumeAttributes:
      everest.io/disk-mode: SCSI           # 云硬盘的磁盘模式，仅支持SCSI
      everest.io/disk-volume-type: SAS     # 云硬盘的类型
      storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
      everest.io/crypt-key-id: 0992dbda-6340-470e-a74e-4f0db288ed82    # 可选字段，加密密钥ID，使用加密盘的时候填写
      everest.io/enterprise-project-id: 86bfc701-9d9e-4871-a318-6385aa368183  # 可选字段，企业项目ID，如果指定企业项目，则创建PVC时也需要指定相同的企业项目，否则PVC无法绑定PV。
  persistentVolumeReclaimPolicy: Delete    # 回收策略
  storageClassName: csi-disk               # 存储类名称，云硬盘必须为csi-disk
```

**表 2**  关键参数说明

<a name="table1819001615355"></a>
<table><thead align="left"><tr id="row1519121663519"><th class="cellrowborder" valign="top" width="43.769999999999996%" id="mcps1.2.3.1.1"><p id="p18191161619356"><a name="p18191161619356"></a><a name="p18191161619356"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="56.230000000000004%" id="mcps1.2.3.1.2"><p id="p1919116161353"><a name="p1919116161353"></a><a name="p1919116161353"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1693515261514"><td class="cellrowborder" valign="top" width="43.769999999999996%" headers="mcps1.2.3.1.1 "><p id="p59357261258"><a name="p59357261258"></a><a name="p59357261258"></a>everest.io/reclaim-policy: retain-volume-only</p>
</td>
<td class="cellrowborder" valign="top" width="56.230000000000004%" headers="mcps1.2.3.1.2 "><p id="p125111321387"><a name="p125111321387"></a><a name="p125111321387"></a>可选字段</p>
<p id="p725113210818"><a name="p725113210818"></a><a name="p725113210818"></a>目前仅支持配置“retain-volume-only”</p>
<p id="p12251163219812"><a name="p12251163219812"></a><a name="p12251163219812"></a>everest插件版本需 &gt;= 1.2.9且回收策略为Delete时生效。如果回收策略是Delete且当前值设置为“retain-volume-only”删除PVC回收逻辑为：删除PV，保留底层存储卷。</p>
</td>
</tr>
<tr id="row6232511129"><td class="cellrowborder" valign="top" width="43.769999999999996%" headers="mcps1.2.3.1.1 "><p id="p857144622619"><a name="p857144622619"></a><a name="p857144622619"></a>failure-domain.beta.kubernetes.io/region</p>
</td>
<td class="cellrowborder" valign="top" width="56.230000000000004%" headers="mcps1.2.3.1.2 "><p id="p991323413456"><a name="p991323413456"></a><a name="p991323413456"></a>集群所在的region。</p>
<p id="p92141648132614"><a name="p92141648132614"></a><a name="p92141648132614"></a>Region对应的值请参见<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。</p>
</td>
</tr>
<tr id="row2318123021219"><td class="cellrowborder" valign="top" width="43.769999999999996%" headers="mcps1.2.3.1.1 "><p id="p957446102612"><a name="p957446102612"></a><a name="p957446102612"></a>failure-domain.beta.kubernetes.io/zone</p>
</td>
<td class="cellrowborder" valign="top" width="56.230000000000004%" headers="mcps1.2.3.1.2 "><p id="p3378436154620"><a name="p3378436154620"></a><a name="p3378436154620"></a>创建云硬盘所在的可用区，必须和工作负载规划的可用区保持一致。</p>
<p id="p11213204892611"><a name="p11213204892611"></a><a name="p11213204892611"></a>zone对应的值请参见<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。</p>
</td>
</tr>
<tr id="row8618742488"><td class="cellrowborder" valign="top" width="43.769999999999996%" headers="mcps1.2.3.1.1 "><p id="p12618134114814"><a name="p12618134114814"></a><a name="p12618134114814"></a>volumeHandle</p>
</td>
<td class="cellrowborder" valign="top" width="56.230000000000004%" headers="mcps1.2.3.1.2 "><p id="p146181448489"><a name="p146181448489"></a><a name="p146181448489"></a>云硬盘的volumeID。</p>
<p id="p1069118611491"><a name="p1069118611491"></a><a name="p1069118611491"></a><strong id="b31904107492"><a name="b31904107492"></a><a name="b31904107492"></a>获取方法：</strong>在云服务器控制台，单击左侧栏目树中的<span class="uicontrol" id="uicontrol1312794911"><a name="uicontrol1312794911"></a><a name="uicontrol1312794911"></a>“云硬盘 &gt; 磁盘”</span>，单击要对接的云硬盘名称进入详情页，在<span class="uicontrol" id="uicontrol10631021112"><a name="uicontrol10631021112"></a><a name="uicontrol10631021112"></a>“概览信息”</span>页签下单击<span class="uicontrol" id="uicontrol17311878495"><a name="uicontrol17311878495"></a><a name="uicontrol17311878495"></a>“ID”</span>后的复制图标即可获取云硬盘的volumeID。</p>
</td>
</tr>
<tr id="row6149172219514"><td class="cellrowborder" valign="top" width="43.769999999999996%" headers="mcps1.2.3.1.1 "><p id="p2137102735114"><a name="p2137102735114"></a><a name="p2137102735114"></a>everest.io/disk-volume-type</p>
</td>
<td class="cellrowborder" valign="top" width="56.230000000000004%" headers="mcps1.2.3.1.2 "><p id="p191376271512"><a name="p191376271512"></a><a name="p191376271512"></a>云硬盘类型，全大写。</p>
<a name="ul1099913293217"></a><a name="ul1099913293217"></a><ul id="ul1099913293217"><li>SAS：高I/O</li><li>SSD：超高I/O</li><li>GPSSD：通用型SSD</li><li>ESSD：极速型SSD</li></ul>
</td>
</tr>
<tr id="row66049431458"><td class="cellrowborder" valign="top" width="43.769999999999996%" headers="mcps1.2.3.1.1 "><p id="p16604154314513"><a name="p16604154314513"></a><a name="p16604154314513"></a>everest.io/crypt-key-id</p>
</td>
<td class="cellrowborder" valign="top" width="56.230000000000004%" headers="mcps1.2.3.1.2 "><p id="p46531143965"><a name="p46531143965"></a><a name="p46531143965"></a>卷为加密卷时为必填，填写创建加密秘钥的ID。</p>
</td>
</tr>
<tr id="row1523031819502"><td class="cellrowborder" valign="top" width="43.769999999999996%" headers="mcps1.2.3.1.1 "><p id="p13230418135016"><a name="p13230418135016"></a><a name="p13230418135016"></a>everest.io/enterprise-project-id</p>
</td>
<td class="cellrowborder" valign="top" width="56.230000000000004%" headers="mcps1.2.3.1.2 "><p id="p1936802710471"><a name="p1936802710471"></a><a name="p1936802710471"></a>可选字段</p>
<p id="p1023011885013"><a name="p1023011885013"></a><a name="p1023011885013"></a>云硬盘的企业项目ID。如果指定企业项目，则创建PVC时也需要指定相同的企业项目，否则PVC无法绑定PV。</p>
<p id="p5212183515119"><a name="p5212183515119"></a><a name="p5212183515119"></a><strong id="b18187175418567"><a name="b18187175418567"></a><a name="b18187175418567"></a>获取方法</strong>：在云服务器控制台，单击左侧栏目树中的<span class="uicontrol" id="uicontrol2066043145319"><a name="uicontrol2066043145319"></a><a name="uicontrol2066043145319"></a>“云硬盘 &gt; 磁盘”</span>，单击要对接的云硬盘名称进入详情页，在“概览信息”页签下找到“管理信息”中的企业项目，单击并进入对应的企业项目控制台，复制对应的ID值即可获取云硬盘所属的企业项目的ID。</p>
</td>
</tr>
<tr id="row142351542711"><td class="cellrowborder" valign="top" width="43.769999999999996%" headers="mcps1.2.3.1.1 "><p id="p1323585418713"><a name="p1323585418713"></a><a name="p1323585418713"></a>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="56.230000000000004%" headers="mcps1.2.3.1.2 "><p id="p29951981584"><a name="p29951981584"></a><a name="p29951981584"></a>集群版本号&gt;=1.19.10且everest插件版本&gt;=1.2.9时正式开放回收策略支持。</p>
<p id="p1995198389"><a name="p1995198389"></a><a name="p1995198389"></a>支持Delete、Retain回收策略。</p>
<p id="p139951481289"><a name="p139951481289"></a><a name="p139951481289"></a><strong id="b10742153312475"><a name="b10742153312475"></a><a name="b10742153312475"></a>Delete</strong>:</p>
<a name="ul1999516818817"></a><a name="ul1999516818817"></a><ul id="ul1999516818817"><li>Delete且不设置everest.io/reclaim-policy：删除PVC，PV资源与云硬盘均被删除。</li><li>Delete且设置everest.io/reclaim-policy=retain-volume-only：删除PVC，PV资源被删除，云硬盘资源会保留。</li></ul>
<p id="p1099515819810"><a name="p1099515819810"></a><a name="p1099515819810"></a><strong id="b1363103794714"><a name="b1363103794714"></a><a name="b1363103794714"></a>Retain</strong>：删除PVC，PV资源与底层存储资源均不会被删除，需要手动删除回收。PVC删除后PV资源状态为“已释放（Released）”，不能直接再次被PVC绑定使用。</p>
<p id="p1849613104811"><a name="p1849613104811"></a><a name="p1849613104811"></a>如果数据安全性要求较高，建议使用<strong id="b1785333964819"><a name="b1785333964819"></a><a name="b1785333964819"></a>Retain</strong>以免误删数据。</p>
</td>
</tr>
</tbody>
</table>

## 创建文件存储SFS存储卷<a name="section1923816719915"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   SFS必须与集群在同一个VPC内。
>-   当前SFS 1.0文件存储处于售罄状态，CCE控制台已经屏蔽创建，存量SFS 1.0仍可以使用YAML方式创建PV。
>-   SFS 3.0文件存储当前正在各region逐步上线中，部分region可能还未支持，请您耐心等待。使用SFS 3.0时，集群中需要安装2.0.9及以上版本的everest插件。

**使用控制台创建**

1.  登录CCE控制台。
2.  单击集群名称进入集群，在左侧选择“容器存储“，在右侧选择“存储卷“页签。
3.  单击右上角“创建存储卷“，在弹出的窗口中填写存储卷参数。
    -   存储卷类型：选择“文件存储“。
    -   选择文件存储资源。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >使用SFS 3.0文件存储时，您需要提前在集群所在VPC创建一个VPC终端节点，这样集群就可以通过VPC终端节点访问SFS 3.0容量型文件系统。配置VPC终端节点的方法请参见[配置VPC终端节点](https://support.huaweicloud.com/qs-sfs/sfs_01_0134.html)。

    -   PV名称：输入PV名称。
    -   访问模式：ReadWriteMany。
    -   回收策略：Delete或Retain，具体解释请参见[PV回收策略](#section19999142414413)。
    -   挂载参数：文件存储卷支持设置挂载参数，具体可填写参数请参见[设置挂载参数](设置挂载参数.md)。

4.  单击“创建“。

**使用YAML创建**

```
apiVersion: v1
kind: PersistentVolume
metadata:
  annotations:
    pv.kubernetes.io/provisioned-by: everest-csi-provisioner
    everest.io/reclaim-policy: retain-volume-only      # 可选字段，删除PV，保留底层存储卷
  name: cce-sfs-test
spec:
  accessModes:
  - ReadWriteMany      # 访问模式，文件存储必须为ReadWriteMany
  capacity:
    storage: 1Gi       # 文件存储容量大小
  csi:
    driver: nas.csi.everest.io    # 挂载依赖的存储驱动
    fsType: nfs
    volumeHandle: 30b3d92a-0bc7-4610-b484-534660db81be   # 文件存储的ID
    volumeAttributes:
      everest.io/share-export-location: sfs-nas01.cn-north-4.myhuaweicloud.com:/share-436304e8  
      storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
  persistentVolumeReclaimPolicy: Retain    # 回收策略
  storageClassName: csi-nas                # 存储类名称：csi-nas表示使用SFS 1.0；csi-sfs表示使用SFS 3.0
  mountOptions: []                         # 挂载参数
```

**表 3**  关键参数说明

<a name="table71355385813"></a>
<table><thead align="left"><tr id="row141351434587"><th class="cellrowborder" valign="top" width="32.5%" id="mcps1.2.3.1.1"><p id="p151358385810"><a name="p151358385810"></a><a name="p151358385810"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="67.5%" id="mcps1.2.3.1.2"><p id="p7135331587"><a name="p7135331587"></a><a name="p7135331587"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16418161611148"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p15990111731412"><a name="p15990111731412"></a><a name="p15990111731412"></a>everest.io/reclaim-policy: retain-volume-only</p>
</td>
<td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p499071711415"><a name="p499071711415"></a><a name="p499071711415"></a>可选字段</p>
<p id="p16990141718140"><a name="p16990141718140"></a><a name="p16990141718140"></a>目前仅支持配置“retain-volume-only”</p>
<p id="p199011711412"><a name="p199011711412"></a><a name="p199011711412"></a>everest插件版本需 &gt;= 1.2.9且回收策略为Delete时生效。如果回收策略是Delete且当前值设置为“retain-volume-only”删除PVC回收逻辑为：删除PV，保留底层存储卷。</p>
</td>
</tr>
<tr id="row1713683175810"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p20136133145811"><a name="p20136133145811"></a><a name="p20136133145811"></a>volumeHandle</p>
</td>
<td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><a name="ul5922134121016"></a><a name="ul5922134121016"></a><ul id="ul5922134121016"><li>使用SFS容量型文件存储：填写文件存储的ID。<p id="p1182583515019"><a name="p1182583515019"></a><a name="p1182583515019"></a>获取方法：在CCE控制台，单击顶部的<span class="uicontrol" id="uicontrol198251135202"><a name="uicontrol198251135202"></a><a name="uicontrol198251135202"></a>“服务列表 &gt; 存储 &gt; 弹性文件服务”</span>，在弹性文件服务列表中单击对应的弹性文件服务名称，在详情页中复制<span class="uicontrol" id="uicontrol1682513351503"><a name="uicontrol1682513351503"></a><a name="uicontrol1682513351503"></a>“ID”</span>后的内容即可。</p>
</li><li>使用SFS 3.0容量型文件存储：填写文件存储的名称。</li></ul>
</td>
</tr>
<tr id="row12163348416"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p737873912413"><a name="p737873912413"></a><a name="p737873912413"></a>everest.io/share-export-location</p>
</td>
<td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p1737815391842"><a name="p1737815391842"></a><a name="p1737815391842"></a>文件存储的共享路径。</p>
<p id="p13378143918414"><a name="p13378143918414"></a><a name="p13378143918414"></a>获取方法：在CCE控制台，单击顶部的<span class="uicontrol" id="uicontrol4378113912413"><a name="uicontrol4378113912413"></a><a name="uicontrol4378113912413"></a>“服务列表 &gt; 存储 &gt; 弹性文件服务”</span>，在弹性文件服务列表中可以看到<span class="uicontrol" id="uicontrol14378239242"><a name="uicontrol14378239242"></a><a name="uicontrol14378239242"></a>“挂载地址”</span>列，即为文件存储的共享路径。</p>
</td>
</tr>
<tr id="row161237179516"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p201237171151"><a name="p201237171151"></a><a name="p201237171151"></a>mountOptions</p>
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
<tr id="row10670145113012"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p85401647163019"><a name="p85401647163019"></a><a name="p85401647163019"></a>everest.io/crypt-key-id</p>
</td>
<td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p8540154712305"><a name="p8540154712305"></a><a name="p8540154712305"></a>卷为加密卷时为必填，填写创建加密秘钥的ID。</p>
</td>
</tr>
<tr id="row10842104516303"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p7540204719305"><a name="p7540204719305"></a><a name="p7540204719305"></a>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p5540154712308"><a name="p5540154712308"></a><a name="p5540154712308"></a>集群版本号&gt;=1.19.10且everest插件版本&gt;=1.2.9时正式开放回收策略支持。</p>
<p id="p1154016478304"><a name="p1154016478304"></a><a name="p1154016478304"></a>支持Delete、Retain回收策略。</p>
<p id="p11540124713309"><a name="p11540124713309"></a><a name="p11540124713309"></a><strong id="b168481115016"><a name="b168481115016"></a><a name="b168481115016"></a>Delete</strong>:</p>
<a name="ul35408479304"></a><a name="ul35408479304"></a><ul id="ul35408479304"><li>Delete且不设置everest.io/reclaim-policy：删除PVC，PV资源与文件存储均被删除。</li><li>Delete且设置everest.io/reclaim-policy=retain-volume-only：删除PVC，PV资源被删除，文件存储资源会保留。</li></ul>
<p id="p105411447133020"><a name="p105411447133020"></a><a name="p105411447133020"></a><strong id="b57894143502"><a name="b57894143502"></a><a name="b57894143502"></a>Retain</strong>：删除PVC，PV资源与底层存储资源均不会被删除，需要手动删除回收。PVC删除后PV资源状态为“已释放（Released）”，不能直接再次被PVC绑定使用。</p>
<p id="p5668154145019"><a name="p5668154145019"></a><a name="p5668154145019"></a>如果数据安全性要求较高，建议使用<strong id="b627615515501"><a name="b627615515501"></a><a name="b627615515501"></a>Retain</strong>以免误删数据。</p>
</td>
</tr>
<tr id="row1592510188155"><td class="cellrowborder" valign="top" width="32.5%" headers="mcps1.2.3.1.1 "><p id="p19926161817153"><a name="p19926161817153"></a><a name="p19926161817153"></a>storageClassName</p>
</td>
<td class="cellrowborder" valign="top" width="67.5%" headers="mcps1.2.3.1.2 "><p id="p1292610188155"><a name="p1292610188155"></a><a name="p1292610188155"></a>存储类名称，支持配置csi-sfs或csi-nas。</p>
<a name="ul44351024162012"></a><a name="ul44351024162012"></a><ul id="ul44351024162012"><li>csi-sfs：推荐使用，表示使用SFS 3.0容量型文件存储。</li><li>csi-nas：表示使用SFS 1.0容量型文件存储。</li></ul>
</td>
</tr>
</tbody>
</table>

## 创建对象存储OBS存储卷<a name="section13401181013912"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>安全容器不支持使用对象存储卷。
>OBS限制单用户创建100个桶，但是CCE使用OBS桶为单个工作负载挂载一个桶，当工作负载数量较多时，容易导致桶数量超过限制，OBS桶无法创建。建议此种场景下直接通过OBS的API或SDK使用OBS，不在工作负载中挂载OBS桶。

**使用控制台创建**

1.  登录CCE控制台。
2.  单击集群名称进入集群，在左侧选择“容器存储“，在右侧选择“存储卷“页签。
3.  单击右上角“创建存储卷“，在弹出的窗口中填写存储卷参数。
    -   存储卷类型：选择“对象存储“。
    -   选择对象存储资源。
    -   PV名称：输入PV名称。
    -   访问模式：ReadWriteMany。
    -   回收策略：Delete或Retain，具体解释请参见[PV回收策略](#section19999142414413)。
    -   密钥：对象存储卷挂载支持设置自定义访问密钥（AK/SK），您可以使用AK/SK创建一个Secret，然后挂载到PV。详细说明请参见[对象存储卷挂载设置自定义访问密钥（AK/SK）](对象存储卷挂载设置自定义访问密钥（AK-SK）.md)。
    -   挂载参数：对象存储卷支持设置挂载参数，具体可填写参数请参见[设置挂载参数](设置挂载参数.md)。

4.  单击“创建“。

**使用YAML创建**

```
apiVersion: v1
kind: PersistentVolume
metadata:
  annotations:
    pv.kubernetes.io/provisioned-by: everest-csi-provisioner
    everest.io/reclaim-policy: retain-volume-only         # 可选字段，删除PV，保留底层存储卷
  name: cce-obs-test
spec:
  accessModes:
  - ReadWriteMany                      # 访问模式，对象存储必须为ReadWriteMany
  capacity:
    storage: 1Gi      # 存储容量，此处填写仅因为PV的格式需要，取值大小无实际意义，可任意填写，不会因为填写的值而限制实际使用OBS空间大小。
  csi:
    driver: obs.csi.everest.io         # 挂载依赖的存储驱动
    fsType: obsfs                      # 对象存储文件类型
    volumeHandle: cce-obs-bucket       # 对象存储的桶名称
    volumeAttributes:
      everest.io/obs-volume-type: STANDARD
      everest.io/region: cn-north-4
      everest.io/enterprise-project-id: 86bfc701-9d9e-4871-a318-6385aa368183  # 可选字段，企业项目ID，如果指定企业项目，则创建PVC时也需要指定相同的企业项目，否则PVC无法绑定PV。
      storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
    nodePublishSecretRef:
      name: test-user
      namespace: default
  persistentVolumeReclaimPolicy: Retain       # 回收策略
  storageClassName: csi-obs                   # 存储类名称，对象存储必须为csi-obs
  mountOptions: []                            # 挂载参数
```

**表 4**  关键参数说明

<a name="table1897325023619"></a>
<table><thead align="left"><tr id="row2973195019365"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p1973155063611"><a name="p1973155063611"></a><a name="p1973155063611"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p139741150123614"><a name="p139741150123614"></a><a name="p139741150123614"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row768273923117"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p87921540193114"><a name="p87921540193114"></a><a name="p87921540193114"></a>everest.io/reclaim-policy: retain-volume-only</p>
</td>
<td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p20792184011318"><a name="p20792184011318"></a><a name="p20792184011318"></a>可选字段</p>
<p id="p2792440143119"><a name="p2792440143119"></a><a name="p2792440143119"></a>目前仅支持配置“retain-volume-only”</p>
<p id="p19792164013313"><a name="p19792164013313"></a><a name="p19792164013313"></a>everest插件版本需 &gt;= 1.2.9且回收策略为Delete时生效。如果回收策略是Delete且当前值设置为“retain-volume-only”删除PVC回收逻辑为：删除PV，保留底层存储卷。</p>
</td>
</tr>
<tr id="row79175211559"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p15794144011386"><a name="p15794144011386"></a><a name="p15794144011386"></a>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p9794134093811"><a name="p9794134093811"></a><a name="p9794134093811"></a>文件类型，支持“obsfs”与“s3fs”，取值为s3fs时创建是obs对象桶，配套使用s3fs挂载；取值为obsfs时创建的是obs并行文件系统，配套使用obsfs挂载，推荐使用。</p>
</td>
</tr>
<tr id="row3112104155614"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p8846313115612"><a name="p8846313115612"></a><a name="p8846313115612"></a>volumeHandle</p>
</td>
<td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p17846013115614"><a name="p17846013115614"></a><a name="p17846013115614"></a>对象存储的桶名称。</p>
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
<tr id="row1493318542619"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p7542185615614"><a name="p7542185615614"></a><a name="p7542185615614"></a>everest.io/enterprise-project-id</p>
</td>
<td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p931095105911"><a name="p931095105911"></a><a name="p931095105911"></a>可选字段</p>
<p id="p12542195619614"><a name="p12542195619614"></a><a name="p12542195619614"></a>对象存储的企业项目ID。如果指定企业项目，则创建PVC时也需要指定相同的企业项目，否则PVC无法绑定PV。</p>
<p id="p1854220561065"><a name="p1854220561065"></a><a name="p1854220561065"></a><strong id="b954265615615"><a name="b954265615615"></a><a name="b954265615615"></a>获取方法</strong>：在对象存储服务控制台，单击左侧栏目树中的<span class="uicontrol" id="uicontrol205426561065"><a name="uicontrol205426561065"></a><a name="uicontrol205426561065"></a>“桶列表”</span>或“并行文件系统”，单击要对接的对象存储名称进入详情页，在“基本信息”页签下找到企业项目，单击并进入对应的企业项目控制台，复制对应的ID值即可获取对象存储所属的企业项目的ID。</p>
</td>
</tr>
<tr id="row169751506362"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1362313208576"><a name="p1362313208576"></a><a name="p1362313208576"></a>nodePublishSecretRef</p>
</td>
<td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1214194318595"><a name="p1214194318595"></a><a name="p1214194318595"></a>对象存储卷挂载支持设置自定义访问密钥（AK/SK），您可以使用AK/SK创建一个Secret，然后挂载到PV。详细说明请参见<a href="对象存储卷挂载设置自定义访问密钥（AK-SK）.md">对象存储卷挂载设置自定义访问密钥（AK/SK）</a>。</p>
</td>
</tr>
<tr id="row19499851182010"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1549918517204"><a name="p1549918517204"></a><a name="p1549918517204"></a>mountOptions</p>
</td>
<td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p10499051132019"><a name="p10499051132019"></a><a name="p10499051132019"></a>挂载参数，具体请参见<a href="设置挂载参数.md#section1254912109811">对象存储挂载参数</a>。</p>
</td>
</tr>
<tr id="row219716449316"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1274655318312"><a name="p1274655318312"></a><a name="p1274655318312"></a>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1074616532313"><a name="p1074616532313"></a><a name="p1074616532313"></a>集群版本号&gt;=1.19.10且everest插件版本&gt;=1.2.9时正式开放回收策略支持。</p>
<p id="p10746105353119"><a name="p10746105353119"></a><a name="p10746105353119"></a>支持Delete、Retain回收策略。</p>
<p id="p147461153173114"><a name="p147461153173114"></a><a name="p147461153173114"></a><strong id="b1217715293503"><a name="b1217715293503"></a><a name="b1217715293503"></a>Delete</strong>:</p>
<a name="ul14746853183117"></a><a name="ul14746853183117"></a><ul id="ul14746853183117"><li>Delete且不设置everest.io/reclaim-policy：删除PVC，PV资源与对象存储均被删除。</li><li>Delete且设置everest.io/reclaim-policy=retain-volume-only：删除PVC，PV资源被删除，对象存储资源会保留。</li></ul>
<p id="p137462053133111"><a name="p137462053133111"></a><a name="p137462053133111"></a><strong id="b148811831125014"><a name="b148811831125014"></a><a name="b148811831125014"></a>Retain</strong>：删除PVC，PV资源与底层存储资源均不会被删除，需要手动删除回收。PVC删除后PV资源状态为“已释放（Released）”，不能直接再次被PVC绑定使用。</p>
<p id="p778102518503"><a name="p778102518503"></a><a name="p778102518503"></a>如果数据安全性要求较高，建议使用<strong id="b1868152519509"><a name="b1868152519509"></a><a name="b1868152519509"></a>Retain</strong>以免误删数据。</p>
</td>
</tr>
</tbody>
</table>

## 创建极速文件存储SFS Turbo存储卷<a name="section746701219919"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>SFS Turbo必须与集群在同一个VPC内。

**使用控制台创建**

1.  登录CCE控制台。
2.  单击集群名称进入集群，在左侧选择“容器存储“，在右侧选择“存储卷“页签。
3.  单击右上角“创建存储卷“，在弹出的窗口中填写存储卷参数。
    -   存储卷类型：选择“极速文件存储“。
    -   选择极速文件存储资源。
    -   PV名称：输入PV名称。
    -   访问模式：ReadWriteMany。
    -   回收策略：Retain，具体解释请参见[PV回收策略](#section19999142414413)。
    -   挂载参数：极速文件存储卷支持设置挂载参数，具体可填写参数请参见[设置挂载参数](设置挂载参数.md)。

4.  单击“创建“。

**使用YAML创建**

```
apiVersion: v1
kind: PersistentVolume
metadata:
  annotations:
    pv.kubernetes.io/provisioned-by: everest-csi-provisioner
  name: cce-sfsturbo-test
spec:
  accessModes:
    - ReadWriteMany       # 访问模式，极速文件存储必须为ReadWriteMany
  capacity:
    storage: 100.00Gi     # 极速文件存储容量大小
  csi:
    driver: sfsturbo.csi.everest.io    # 挂载依赖的存储驱动
    fsType: nfs
    volumeHandle: 6674bd0a-d760-49de-bb9e-805c7883f047      # 极速文件存储的ID。
    volumeAttributes:
      everest.io/share-export-location: 192.168.0.85:/      # 极速文件存储的共享路径
      storage.kubernetes.io/csiProvisionerIdentity: everest-csi-provisioner
  persistentVolumeReclaimPolicy: Retain     # 回收策略
  storageClassName: csi-sfsturbo            # 存储类名称，极速文件存储必须为csi-sfsturbo
  mountOptions: []                          # 挂载参数
```

**表 5**  关键参数说明

<a name="table953204119"></a>
<table><thead align="left"><tr id="row1666206115"><th class="cellrowborder" valign="top" width="35.89%" id="mcps1.2.3.1.1"><p id="p1662017116"><a name="p1662017116"></a><a name="p1662017116"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="64.11%" id="mcps1.2.3.1.2"><p id="p56820513"><a name="p56820513"></a><a name="p56820513"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1061620713"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p2127205115"><a name="p2127205115"></a><a name="p2127205115"></a>volumeHandle</p>
</td>
<td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p331414324103"><a name="p331414324103"></a><a name="p331414324103"></a>极速文件存储的ID。</p>
<p id="p1455172961010"><a name="p1455172961010"></a><a name="p1455172961010"></a>获取方法：在弹性文件服务控制台，单击SFS Turbo存储实例，在基本信息中可查看到ID。</p>
</td>
</tr>
<tr id="row6115201810"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p1911172013115"><a name="p1911172013115"></a><a name="p1911172013115"></a>everest.io/share-export-location</p>
</td>
<td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p1812132017111"><a name="p1812132017111"></a><a name="p1812132017111"></a>极速文件存储的共享路径。</p>
</td>
</tr>
<tr id="row18678549121716"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p18225195111714"><a name="p18225195111714"></a><a name="p18225195111714"></a>mountOptions</p>
</td>
<td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p102261251111713"><a name="p102261251111713"></a><a name="p102261251111713"></a>挂载参数。</p>
<p id="p16226251151710"><a name="p16226251151710"></a><a name="p16226251151710"></a>不设置时默认配置为如下配置，具体说明请参见<a href="设置挂载参数.md#section14888047833">文件存储挂载参数</a>。</p>
<pre class="screen" id="screen162263516171"><a name="screen162263516171"></a><a name="screen162263516171"></a>mountOptions:
- vers=3
- timeo=600
- nolock
- hard</pre>
</td>
</tr>
<tr id="row1761104195212"><td class="cellrowborder" valign="top" width="35.89%" headers="mcps1.2.3.1.1 "><p id="p166175137524"><a name="p166175137524"></a><a name="p166175137524"></a>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="64.11%" headers="mcps1.2.3.1.2 "><p id="p146171913195219"><a name="p146171913195219"></a><a name="p146171913195219"></a>集群版本号&gt;=1.19.10且everest插件版本&gt;=1.2.9时正式开放回收策略支持。</p>
<p id="p1661719131526"><a name="p1661719131526"></a><a name="p1661719131526"></a>支持Delete、Retain回收策略。</p>
<p id="p261701305213"><a name="p261701305213"></a><a name="p261701305213"></a><strong id="b1861731316521"><a name="b1861731316521"></a><a name="b1861731316521"></a>Delete</strong>:</p>
<a name="ul86171313175216"></a><a name="ul86171313175216"></a><ul id="ul86171313175216"><li>Delete且不设置everest.io/reclaim-policy：删除PVC，PV资源与极速文件存储均被删除。</li><li>Delete且设置everest.io/reclaim-policy=retain-volume-only：删除PVC，PV资源被删除，极速文件存储资源会保留。</li></ul>
<p id="p261761313522"><a name="p261761313522"></a><a name="p261761313522"></a><strong id="b156171613145218"><a name="b156171613145218"></a><a name="b156171613145218"></a>Retain</strong>：删除PVC，PV资源与底层存储资源均不会被删除，需要手动删除回收。PVC删除后PV资源状态为“已释放（Released）”，不能直接再次被PVC绑定使用。</p>
<p id="p1361771316526"><a name="p1361771316526"></a><a name="p1361771316526"></a>如果数据安全性要求较高，建议使用<strong id="b10617513115216"><a name="b10617513115216"></a><a name="b10617513115216"></a>Retain</strong>以免误删数据。</p>
</td>
</tr>
</tbody>
</table>

