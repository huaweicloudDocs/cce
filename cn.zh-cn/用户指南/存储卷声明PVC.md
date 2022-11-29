# 存储卷声明PVC<a name="cce_10_0378"></a>

PVC描述的是负载对存储卷的申领，PVC的申领会消耗集群中存量的PV资源，若集群中无存量PV资源，会动态创建底层存储及PV资源；创建PVC时，需描述请求的持久化存储的属性，比如，Volume存储的大小、可读写权限等等。

## 约束与限制<a name="section516692464018"></a>

创建PVC会先匹配集群中是否有配置相同、且状态为可用状态的PV，如果存在，PVC将首先选择可匹配的，且为可用状态的PV进行绑定，在集群中无满足匹配条件的PV时，动态创建新的存储。

<a name="table3531229104018"></a>
<table><thead align="left"><tr id="row4618142917405"><th class="cellrowborder" valign="top" width="12.62126212621262%" id="mcps1.1.5.1.1"><p id="p1961812916400"><a name="p1961812916400"></a><a name="p1961812916400"></a>字段含义</p>
</th>
<th class="cellrowborder" valign="top" width="28.002800280028005%" id="mcps1.1.5.1.2"><p id="p17618529114015"><a name="p17618529114015"></a><a name="p17618529114015"></a>pvc字段</p>
</th>
<th class="cellrowborder" valign="top" width="34.963496349634966%" id="mcps1.1.5.1.3"><p id="p661810299404"><a name="p661810299404"></a><a name="p661810299404"></a>pv字段</p>
</th>
<th class="cellrowborder" valign="top" width="24.412441244124413%" id="mcps1.1.5.1.4"><p id="p1461892915408"><a name="p1461892915408"></a><a name="p1461892915408"></a>匹配逻辑</p>
</th>
</tr>
</thead>
<tbody><tr id="row176183299407"><td class="cellrowborder" valign="top" width="12.62126212621262%" headers="mcps1.1.5.1.1 "><p id="p16181229124014"><a name="p16181229124014"></a><a name="p16181229124014"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="28.002800280028005%" headers="mcps1.1.5.1.2 "><p id="p561862974016"><a name="p561862974016"></a><a name="p561862974016"></a>pvc.metadata.labels(failure-domain.beta.kubernetes.io/region或者topology.kubernetes.io/region)</p>
</td>
<td class="cellrowborder" valign="top" width="34.963496349634966%" headers="mcps1.1.5.1.3 "><p id="p17618192914013"><a name="p17618192914013"></a><a name="p17618192914013"></a>pv.metadata.labels(failure-domain.beta.kubernetes.io/region或者topology.kubernetes.io/region)</p>
</td>
<td class="cellrowborder" valign="top" width="24.412441244124413%" headers="mcps1.1.5.1.4 "><p id="p106181296406"><a name="p106181296406"></a><a name="p106181296406"></a>同时定义/不被定义，若定义需要内容一致</p>
</td>
</tr>
<tr id="row9618172917407"><td class="cellrowborder" valign="top" width="12.62126212621262%" headers="mcps1.1.5.1.1 "><p id="p11618229124014"><a name="p11618229124014"></a><a name="p11618229124014"></a>zone</p>
</td>
<td class="cellrowborder" valign="top" width="28.002800280028005%" headers="mcps1.1.5.1.2 "><p id="p6618122915409"><a name="p6618122915409"></a><a name="p6618122915409"></a>pvc.metadata.labels(failure-domain.beta.kubernetes.io/zone或者topology.kubernetes.io/zone)</p>
</td>
<td class="cellrowborder" valign="top" width="34.963496349634966%" headers="mcps1.1.5.1.3 "><p id="p116181429104018"><a name="p116181429104018"></a><a name="p116181429104018"></a>pv.metadata.labels(failure-domain.beta.kubernetes.io/zone或者topology.kubernetes.io/zone)</p>
</td>
<td class="cellrowborder" valign="top" width="24.412441244124413%" headers="mcps1.1.5.1.4 "><p id="p196185293400"><a name="p196185293400"></a><a name="p196185293400"></a>同时定义/不被定义，若定义需要内容一致</p>
</td>
</tr>
<tr id="row146187298409"><td class="cellrowborder" valign="top" width="12.62126212621262%" headers="mcps1.1.5.1.1 "><p id="p861813298407"><a name="p861813298407"></a><a name="p861813298407"></a>云硬盘类型</p>
</td>
<td class="cellrowborder" valign="top" width="28.002800280028005%" headers="mcps1.1.5.1.2 "><p id="p18618142911400"><a name="p18618142911400"></a><a name="p18618142911400"></a>pvc.metadata.annotations(everest.io/disk-volume-type)</p>
</td>
<td class="cellrowborder" valign="top" width="34.963496349634966%" headers="mcps1.1.5.1.3 "><p id="p561832912407"><a name="p561832912407"></a><a name="p561832912407"></a>pv.spec.csi.volumeAttributes(everest.io/disk-volume-type)</p>
</td>
<td class="cellrowborder" valign="top" width="24.412441244124413%" headers="mcps1.1.5.1.4 "><p id="p18618192974019"><a name="p18618192974019"></a><a name="p18618192974019"></a>同时定义/不被定义，若定义需要内容一致</p>
</td>
</tr>
<tr id="row136181029104012"><td class="cellrowborder" valign="top" width="12.62126212621262%" headers="mcps1.1.5.1.1 "><p id="p166181229164014"><a name="p166181229164014"></a><a name="p166181229164014"></a>秘钥id</p>
</td>
<td class="cellrowborder" valign="top" width="28.002800280028005%" headers="mcps1.1.5.1.2 "><p id="p20618229204012"><a name="p20618229204012"></a><a name="p20618229204012"></a>pvc.metadata.annotations(everest.io/crypt-key-id)</p>
</td>
<td class="cellrowborder" valign="top" width="34.963496349634966%" headers="mcps1.1.5.1.3 "><p id="p136181429134010"><a name="p136181429134010"></a><a name="p136181429134010"></a>pv.spec.csi.volumeAttributes(everest.io/crypt-key-id)</p>
</td>
<td class="cellrowborder" valign="top" width="24.412441244124413%" headers="mcps1.1.5.1.4 "><p id="p361832918405"><a name="p361832918405"></a><a name="p361832918405"></a>同时定义/不被定义，若定义需要内容一致</p>
</td>
</tr>
<tr id="row152355613310"><td class="cellrowborder" valign="top" width="12.62126212621262%" headers="mcps1.1.5.1.1 "><p id="p13523165618338"><a name="p13523165618338"></a><a name="p13523165618338"></a>企业项目id</p>
</td>
<td class="cellrowborder" valign="top" width="28.002800280028005%" headers="mcps1.1.5.1.2 "><p id="p652313567335"><a name="p652313567335"></a><a name="p652313567335"></a>pvc.metadata.annotations(everest.io/enterprise-project-id)</p>
</td>
<td class="cellrowborder" valign="top" width="34.963496349634966%" headers="mcps1.1.5.1.3 "><p id="p052311569334"><a name="p052311569334"></a><a name="p052311569334"></a>pv.spec.csi.volumeAttributes(everest.io/enterprise-project-id)</p>
</td>
<td class="cellrowborder" valign="top" width="24.412441244124413%" headers="mcps1.1.5.1.4 "><p id="p17523165673314"><a name="p17523165673314"></a><a name="p17523165673314"></a>同时定义/不被定义，若定义需要内容一致</p>
</td>
</tr>
<tr id="row106182299407"><td class="cellrowborder" valign="top" width="12.62126212621262%" headers="mcps1.1.5.1.1 "><p id="p16618102913400"><a name="p16618102913400"></a><a name="p16618102913400"></a>accessMode</p>
</td>
<td class="cellrowborder" valign="top" width="28.002800280028005%" headers="mcps1.1.5.1.2 "><p id="p1461817293407"><a name="p1461817293407"></a><a name="p1461817293407"></a>accessMode</p>
</td>
<td class="cellrowborder" valign="top" width="34.963496349634966%" headers="mcps1.1.5.1.3 "><p id="p06186293402"><a name="p06186293402"></a><a name="p06186293402"></a>accessMode</p>
</td>
<td class="cellrowborder" valign="top" width="24.412441244124413%" headers="mcps1.1.5.1.4 "><p id="p1361812964011"><a name="p1361812964011"></a><a name="p1361812964011"></a>内容一致</p>
</td>
</tr>
<tr id="row96181929134020"><td class="cellrowborder" valign="top" width="12.62126212621262%" headers="mcps1.1.5.1.1 "><p id="p1961892918405"><a name="p1961892918405"></a><a name="p1961892918405"></a>存储类</p>
</td>
<td class="cellrowborder" valign="top" width="28.002800280028005%" headers="mcps1.1.5.1.2 "><p id="p1761842954017"><a name="p1761842954017"></a><a name="p1761842954017"></a>storageclass</p>
</td>
<td class="cellrowborder" valign="top" width="34.963496349634966%" headers="mcps1.1.5.1.3 "><p id="p56181629114017"><a name="p56181629114017"></a><a name="p56181629114017"></a>storageclass</p>
</td>
<td class="cellrowborder" valign="top" width="24.412441244124413%" headers="mcps1.1.5.1.4 "><p id="p14618102994011"><a name="p14618102994011"></a><a name="p14618102994011"></a>内容一致</p>
</td>
</tr>
</tbody>
</table>

## 存储卷访问模式<a name="section43881411172418"></a>

PV只能以底层存储资源所支持的方式挂载到宿主系统上。例如，文件存储可以支持多个节点读写，云硬盘只能被一个节点读写。

-   ReadWriteOnce：卷可以被一个节点以读写方式挂载，云硬盘存储卷支持此类型。
-   ReadWriteMany：卷可以被多个节点以读写方式挂载，文件存储、对象存储、极速文件存储支持此类型。

**表 1**  支持访问模式

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
<tr id="row1189515363219"><td class="cellrowborder" valign="top" width="23.352335233523352%" headers="mcps1.2.4.1.1 "><p id="p4896253143213"><a name="p4896253143213"></a><a name="p4896253143213"></a>本地持久卷LocalPV</p>
</td>
<td class="cellrowborder" valign="top" width="36.023602360236026%" headers="mcps1.2.4.1.2 "><p id="p6521733310"><a name="p6521733310"></a><a name="p6521733310"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="40.624062406240625%" headers="mcps1.2.4.1.3 "><p id="p9523714332"><a name="p9523714332"></a><a name="p9523714332"></a>×</p>
</td>
</tr>
</tbody>
</table>

## 企业项目支持说明<a name="section732811741614"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>该功能需要Everest插件升级到1.2.33及以上版本。

-   [使用存储类创建PVC](#section155911631134310)：

    CCE支持使用存储类创建云硬盘和对象存储类型PVC时指定企业项目，将创建的存储资源（云硬盘和对象存储）归属于指定的企业项目下，**企业项目可选为集群所属的企业项目或default企业项目**。

    若不指定企业项目，则创建的存储资源默认使用存储类StorageClass中指定的企业项目。

    -   对于自定义的StorageClass，可以在StorageClass中指定企业项目，详见[指定StorageClass的企业项目](存储类StorageClass.md#section878918816267)。StorageClass中如不指定的企业项目，则默认为default企业项目。
    -   对于CCE提供的 csi-disk 和 csi-obs 存储类，所创建的存储资源属于default企业项目。

-   [使用存储卷PV创建PVC](#section139251655204319)：

    使用PV创建PVC时，因为存储资源在创建时已经指定了企业项目，如果PVC中指定企业项目，则务必确保在PVC和PV中指定的everest.io/enterprise-project-id保持一致，否则两者无法正常绑定。


## 使用存储类创建PVC<a name="section155911631134310"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   使用存储类创建的底层云硬盘、文件存储和对象存储均为按需计费模式。
>-   当前SFS 1.0文件存储处于售罄状态，CCE控制台已经屏蔽创建，存量SFS 1.0仍可以使用YAML方式创建PV。
>-   SFS 3.0文件存储当前正在各region逐步上线中，部分region可能还未支持，请您耐心等待。使用SFS 3.0时，集群中需要安装2.0.8及以上版本的everest插件。

存储类（StorageClass）描述了集群中的存储类型“分类”，在创建PVC需要可以指定StorageClass，动态创建PV及底层存储资源。

**使用控制台创建**

1.  登录CCE控制台。
2.  进入集群，在左侧选择“容器存储“，在右侧选择“存储卷声明“页签。
3.  单击右上角“创建存储声明“，在弹出的窗口中填写存储卷“声明“参数。
    -   存储卷声明类型：请根据您的需求进行选择。
    -   PVC名称：指定PVC的名称。
    -   创建方式：选择“动态创建“。
    -   存储类：选择需要的存储类型。当前支持如下几类存储动态创建。
        -   csi-disk：云硬盘。
        -   csi-local-topology：本地持久卷。
        -   csi-sfs：SFS 3.0容量型文件存储。
        -   csi-obs：对象存储。

    -   可用区（仅云硬盘支持）：选择云硬盘所在可用区。
    -   云硬盘类型（仅云硬盘支持）：选择云硬盘的类型。云硬盘类型在不同区域会有所不同。

        -   高I/O
        -   超高I/O
        -   通用型SSD
        -   极速型SSD

        具体请参见[这里](https://support.huaweicloud.com/productdesc-evs/zh-cn_topic_0044524691.html)了解如何选择磁盘类型。

    -   访问模式：ReadWriteOnce和ReadWriteMany，具体请参见[存储卷访问模式](#section43881411172418)。
    -   存储池（仅本地持久卷支持）：显示支持本地持久卷的节点，具体请参见[本地持久存储卷和临时存储卷](本地持久存储卷和临时存储卷.md)。
    -   容量（仅云硬盘和文件存储支持）：存储的容量大小。仅云硬盘和文件存储需要配置，对象存储无需配置。
    -   加密（仅云硬盘和文件存储支持）：勾选底层存储是否加密，勾选后需要选择使用的加密密钥。仅云硬盘和文件存储支持加密。
    -   密钥（仅对象存储支持）：对象存储需要选择访问密钥，具体使用请参见[对象存储卷挂载设置自定义访问密钥（AK/SK）](对象存储卷挂载设置自定义访问密钥（AK-SK）.md)。
    -   企业项目（仅云硬盘和对象存储支持）：集群所属的企业项目或default企业项目。

4.  单击“创建“。

**使用YAML创建**

云硬盘YAML示例。

-   failure-domain.beta.kubernetes.io/region：集群所在的region。

    Region对应的值请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。

-   failure-domain.beta.kubernetes.io/zone：创建云硬盘所在的可用区，必须和工作负载规划的可用区保持一致。

    zone对应的值请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。

-   everest.io/enterprise-project-id：企业项目ID。仅支持集群所属企业项目和default企业项目，"0"表示default企业项目。

    **获取方法**：在CCE控制台，单击左侧栏目树中的“集群管理“，选择集群，并进入指定的集群详情页，在“基本信息”页签下找到企业项目，点击并进入对应的企业项目控制台，复制对应的ID值即可获取集群所属的企业项目的ID。


```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-evs-auto-example
  namespace: default
  annotations:
    everest.io/disk-volume-type: SSD    # 云硬盘的类型
    everest.io/crypt-key-id: 0992dbda-6340-470e-a74e-4f0db288ed82  # 可选字段，密钥的id，使用该密钥加密云硬盘
    everest.io/enterprise-project-id: 86bfc701-9d9e-4871-a318-6385aa368183  # 可选字段，企业项目id，Everest需升级到1.2.33及以上版本，仅支持集群所属企业项目和default企业项目，"0"表示default企业项目。
  labels:
    failure-domain.beta.kubernetes.io/region: cn-north-4
    failure-domain.beta.kubernetes.io/zone: cn-north-4b
spec:
  accessModes:
  - ReadWriteOnce               # 云硬盘必须为ReadWriteOnce
  resources:
    requests:
      storage: 10Gi             # 云硬盘大小，取值范围 1-32768
  storageClassName: csi-disk    # StorageClass类型为云硬盘
```

本地持久卷YAML示例，本地持久卷使用要求在节点上导入了本地持久卷，具体请参见[本地持久存储卷和临时存储卷](本地持久存储卷和临时存储卷.md)。

```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-local-example
  namespace: default
spec:
  accessModes:
  - ReadWriteOnce               # 必须为ReadWriteOnce
  resources:
    requests:
      storage: 10Gi             # 本地持久存储卷大小
  storageClassName: csi-local-topology    # StorageClass类型为csi-local-topology
```

文件存储YAML示例：

```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name:  pvc-sfs-auto-example
  namespace: default
  annotations: {}
spec:
  accessModes:
  - ReadWriteMany                  # 文件存储必须为ReadWriteMany
  resources:
    requests:
      storage: 10Gi                # 文件存储大小
  storageClassName: csi-sfs        # 该StorageClass类型为SFS3.0容量型文件存储
```

对象存储YAML示例：

```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: obs-warm-provision-pvc
  namespace: default
  annotations:
    everest.io/obs-volume-type: STANDARD      # 桶类型，当前支持标准（STANDARD）和低频（WARM）两种桶。
    csi.storage.k8s.io/fstype: obsfs          # 文件类型，obsfs表示创建并行文件系统，推荐使用；s3fs表示创建对象桶
    everest.io/enterprise-project-id: 86bfc701-9d9e-4871-a318-6385aa368183  # 可选字段，企业项目id，Everest需升级到1.2.33及以上版本，仅支持集群所属企业项目和default企业项目，"0"表示default企业项目。
spec:
  accessModes:
  - ReadWriteMany                  # 对象存储必须为ReadWriteMany
  resources:
    requests:
      storage: 1Gi                 # 此处仅为校验需要（不能为空和0），设置的大小不起作用，此处设定为固定值1Gi
  storageClassName: csi-obs        # StorageClass类型为对象存储
```

## 使用存储卷PV创建PVC<a name="section139251655204319"></a>

如果已经创建了PV，则可以创建PVC申请PV的资源。

**使用控制台创建**

1.  登录CCE控制台。
2.  进入集群，在左侧选择“容器存储“，在右侧选择“存储卷声明“页签。
3.  单击右上角“创建存储声明“，在弹出的窗口中填写存储卷“声明“参数。
    -   存储卷声明类型：请根据您的需求进行选择。
    -   PVC名称：指定PVC的名称。
    -   创建方式：选择“已有存储卷“。
    -   关联存储卷：选择要关联的存储卷，即PV。

4.  单击“创建“。

**使用YAML创建**

云硬盘YAML示例。

-   failure-domain.beta.kubernetes.io/region：集群所在的region。

    Region对应的值请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。

-   failure-domain.beta.kubernetes.io/zone：创建云硬盘所在的可用区，必须和工作负载规划的可用区保持一致。

    zone对应的值请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。


```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-test
  namespace: default
  annotations:
    everest.io/disk-volume-type: SAS                                # 云硬盘的类型
    everest.io/crypt-key-id: fe0757de-104c-4b32-99c5-ee832b3bcaa3   # 可选字段，密钥的id，使用该密钥加密云硬盘
    volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
    everest.io/enterprise-project-id: 86bfc701-9d9e-4871-a318-6385aa368183  # 可选字段，如果指定企业项目，需保证与PV中指定的everest.io/enterprise-project-id一致，否则无法绑定
  labels:
    failure-domain.beta.kubernetes.io/region: cn-north-4
    failure-domain.beta.kubernetes.io/zone: cn-north-4b
spec:
  accessModes:
  - ReadWriteOnce                # 云硬盘必须为ReadWriteOnce
  resources:
    requests:
      storage: 10Gi              
  storageClassName: csi-disk     # StorageClass的名称，云硬盘为csi-disk
  volumeName: cce-evs-test       # PV的名称
```

文件存储示例：

```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-sfs-test
  namespace: default
  annotations:
    volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
spec:
  accessModes:
  - ReadWriteMany              # 文件存储必须为ReadWriteMany
  resources:
    requests:
      storage: 100Gi           # PVC申请容量大小
  storageClassName: csi-nas    # StorageClass的名称，SFS3.0容量型对应值为csi-sfs
  volumeName: cce-sfs-test     # PV的名称
```

对象存储示例：

```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-obs-test
  namespace: default
  annotations:
    everest.io/obs-volume-type: STANDARD                         # 桶类型，当前支持标准（STANDARD）和低频（WARM）两种桶。
    csi.storage.k8s.io/fstype: obsfs                             # 文件类型，obsfs表示创建并行文件系统，推荐使用；s3fs表示创建对象桶
    csi.storage.k8s.io/node-publish-secret-name: test-user
    csi.storage.k8s.io/node-publish-secret-namespace: default
    volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
    everest.io/enterprise-project-id: 86bfc701-9d9e-4871-a318-6385aa368183  # 可选字段，如果指定企业项目，需保证与PV中指定的everest.io/enterprise-project-id一致，否则无法绑定
spec:
  accessModes:
  - ReadWriteMany             # 对象存储必须为ReadWriteMany
  resources:
    requests:
      storage: 1Gi            # PVC申请容量大小，此处仅为校验需要（不能为空和0），设置的大小不起作用，此处设定为固定值1Gi
  storageClassName: csi-obs   # StorageClass的名称，对象存储为csi-obs
  volumeName: cce-obs-test    # PV的名称
```

极速文件存储示例：

```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-test
  namespace: default
  annotations:
    volume.beta.kubernetes.io/storage-provisioner: everest-csi-provisioner
spec:
  accessModes:
    - ReadWriteMany               # 极速文件存储必须为ReadWriteMany
  resources:
    requests:
      storage: 100Gi              # PVC申请容量大小
  storageClassName: csi-sfsturbo  # StorageClass的名称，极速文件存储为csi-sfsturbo
  volumeName: pv-sfsturbo-test         # PV的名称
```

## 使用快照创建PVC<a name="section181681453141710"></a>

通过快照创建云硬盘PVC时，磁盘类型、磁盘模式、加密属性需和快照源云硬盘保持一致。

**使用控制台创建**

1.  登录CCE控制台。
2.  进入集群，在左侧选择“容器存储“，在右侧选择“快照与备份“页签。
3.  找到需要创建PVC的快照，单击“创建存储卷声明“，并在弹出窗口中指定PVC的名称。
4.  单击“创建“。

**使用YAML创建**

```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-test
  namespace: default
  annotations:
    everest.io/disk-volume-type: SSD     # 云硬盘类型，需要与快照源云硬盘保持一致
  labels:
    failure-domain.beta.kubernetes.io/region: cn-north-4
    failure-domain.beta.kubernetes.io/zone: cn-north-4b
spec:
  accessModes:
  - ReadWriteOnce
  resources:
    requests:
      storage: '10'
  storageClassName: csi-disk
  dataSource:
    name: cce-disksnap-test             # 快照的名称
    kind: VolumeSnapshot
    apiGroup: snapshot.storage.k8s.io
```

## 在工作负载中使用PVC<a name="section5239114931711"></a>

-   [部署带云硬盘存储卷EVS的工作负载](部署带云硬盘存储卷EVS的工作负载.md)
-   [部署带极速文件存储卷SFS Turbo的无状态工作负载](部署带极速文件存储卷SFS-Turbo的无状态工作负载.md)
-   [部署带极速文件存储卷SFS Turbo的有状态工作负载](部署带极速文件存储卷SFS-Turbo的有状态工作负载.md)
-   [部署带对象存储卷OBS的无状态工作负载](部署带对象存储卷OBS的无状态工作负载.md)
-   [部署带对象存储卷OBS的有状态工作负载](部署带对象存储卷OBS的有状态工作负载.md)
-   [部署带文件存储卷SFS的无状态工作负载](部署带文件存储卷SFS的无状态工作负载.md)
-   [部署带文件存储卷SFS的有状态工作负载](部署带文件存储卷SFS的有状态工作负载.md)

