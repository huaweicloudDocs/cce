# 创建PV（已废弃）<a name="cce_02_0256"></a>

## 功能介绍

该API用于通过指定云存储服务中的云存储（如EVS、SFS、OBS）去创建PV（PersistentVolume）。

>![](public_sys-resources/icon-note.gif) **说明：** 
>存储管理的URL格式为：**https://\{clusterid\}.Endpoint/uri**。其中\*\*\{clusterid\}**为集群ID，**uri**为资源路径，也即API访问的路径。 \>如果使用**https://Endpoint/uri\*\*，则必须指定请求header中的**X-Cluster-ID**参数。

## 调试

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?product=CCE&api=CreateCloudPersistentVolumes)中调试该接口。

## URI

POST /api/v1/cloudpersistentvolumes

## 请求参数

**表 1**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>消息体的类型（格式）</p>
<p>枚举值：</p>
<ul><li><p>application/json;charset=utf-8</p>
</li><li><p>application/json</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="https://support.huaweicloud.com/api-cce/cce_02_0004.html#cce_02_0004__section2417768214391" target="_blank" rel="noopener noreferrer">获取token</a>。</p>
<p>最大长度：16384</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>X-Cluster-ID</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>集群 ID，使用<strong>https://Endpoint/uri</strong>这种URL格式时必须指定此参数。获取方式请参见<a href="https://support.huaweicloud.com/api-cce/cce_02_0271.html" target="_blank" rel="noopener noreferrer">如何获取接口URI中参数</a></p>
</td>
</tr>
</tbody>
</table>

**表 2**  请求Body参数

<a name="requestParameter"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>API版本，固定值<strong>v1</strong></p>
<p>缺省值：v1</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>kind</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>API类型，固定值<strong>PersistentVolume</strong></p>
<p>缺省值：PersistentVolume</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p><a href="#request_PersistentVolumeMetadata">PersistentVolumeMetadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>PersistentVolume的元数据信息</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>spec</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p><a href="#request_PersistentVolumeSpec">PersistentVolumeSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>PersistentVolume的规格信息</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>status</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p><a href="#request_PersistentVolumeStatus">PersistentVolumeStatus</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>PersistentVolume的状态信息</p>
</td>
</tr>
</tbody>
</table>

**表 3**  PersistentVolumeMetadata

<a name="request_PersistentVolumeMetadata"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>name</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>PersistentVolume名称，可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符，同一namespace下name不能重复。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>labels</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>PersistentVolume标签，key/value对格式。</p>
<ul><li><p>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</p>
</li><li><p>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</p>
</li></ul>
<p>示例："foo": "bar"</p>
</td>
</tr>
</tbody>
</table>

**表 4**  PersistentVolumeSpec

<a name="request_PersistentVolumeSpec"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>flexVolume</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p><a href="#request_FlexVolume">FlexVolume</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>Kubernetes的flexvolume存储插件</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>PersistentVolume的回收策略，包括：</p>
<ul><li><p>Retain：保留策略允许手动回收资源。当 PersistentVolumeClaim 被删除时，PersistentVolume 仍然存在，volume 被视为“已释放”。</p>
</li><li><p>Recycle：回收策略会在 volume上执行基本擦除（rm -rf / thevolume / *），可被再次声明使用。</p>
</li><li><p>Delete：对于支持删除回收策略的卷插件，删除操作将从 Kubernetes 中删除 PersistentVolume 对象，并删除外部基础架构中的关联存储资产。动态配置的卷继承其 StorageClass，默认为 Delete。</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>指定volume应该具有的访问模式。</p>
<ul><li><p>ReadWriteOnce：该卷可以被单个节点以读/写模式挂载</p>
<div class="note"><span class="notetitle"> 说明： </span><div class="notebody"><p>集群版本为v1.13.10且storage-driver版本为1.0.19时，才支持此功能。</p>
</div></div>
</li><li><p>ReadOnlyMany：该卷可以被多个节点以只读模式挂载</p>
</li><li><p>ReadWriteMany：该卷可以被多个节点以读/写模式挂载</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

**表 5**  FlexVolume

<a name="request_FlexVolume"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>driver</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>Flexvolume插件名称，请根据使用的存储类型填写：</p>
<ul><li><p>huawei.com/fuxivol (EVS)</p>
</li><li><p>huawei.com/fuxinfs (SFS)</p>
</li><li><p>huawei.com/fuxiobs (OBS)</p>
</li><li><p>huawei.com/fuxiefs (SFS Turbo)</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>文件系统类型，请根据使用的存储类型填写：</p>
<ul><li><p>ext4： EVS云硬盘存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0044.html" target="_blank" rel="noopener noreferrer">使用云硬盘存储卷</a>。</p>
</li><li><p>nfs：SFS弹性文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0111.html" target="_blank" rel="noopener noreferrer">使用文件存储卷</a>。</p>
</li><li><p>obs：OBS对象存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0160.html" target="_blank" rel="noopener noreferrer">使用对象存储卷</a>。</p>
</li><li><p>efs：SFS Turbo极速文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0125.html" target="_blank" rel="noopener noreferrer">使用极速文件存储卷</a>。</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>options</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p><a href="#request_Options">Options</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>flexVolume配置项</p>
</td>
</tr>
</tbody>
</table>

**表 6**  Options

<a name="request_Options"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>文件系统类型，请根据使用的存储类型填写：</p>
<ul><li><p>ext4 (EVS)</p>
</li><li><p>nfs (SFS)</p>
</li><li><p>obs (OBS)</p>
</li><li><p>efs (SFS Turbo)</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>region</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>云存储所在的region。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>volumeID</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>云存储的UUID，如果是OBS-bucket则填入名称</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>storageType</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>指定云存储的类型。</p>
<ul><li><p>bs (EVS)</p>
</li><li><p>nfs (SFS)</p>
</li><li><p>obs (OBS)</p>
</li><li><p>efs (SFS Turbo)</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

**表 7**  PersistentVolumeStatus

<a name="request_PersistentVolumeStatus"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>显示volume实际具有的访问模式。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>phase</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p>PersistentVolume当前所处的状态，包括：</p>
<ul><li><p>Available（可用）：还是空闲资源，没有被任何PVC绑定</p>
</li><li><p>Bound（已绑定）：卷已经被PVC绑定</p>
</li><li><p>Released（已释放）：之前绑定的PVC被删除，但是资源还未被集群重新声明</p>
</li><li><p>Failed（失败）：该卷的自动回收失败</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

## 响应参数

**状态码为 201 时: **

**表 8**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>API版本，固定值<strong>v1</strong></p>
<p>缺省值：v1</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>API类型，固定值<strong>PersistentVolume</strong></p>
<p>缺省值：PersistentVolume</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_PersistentVolumeMetadata">PersistentVolumeMetadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>PersistentVolume的元数据信息</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_PersistentVolumeSpec">PersistentVolumeSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>PersistentVolume的规格信息</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_PersistentVolumeStatus">PersistentVolumeStatus</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>PersistentVolume的状态信息</p>
</td>
</tr>
</tbody>
</table>

**表 9**  PersistentVolumeMetadata

<a name="response_PersistentVolumeMetadata"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>PersistentVolume名称，可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符，同一namespace下name不能重复。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>PersistentVolume标签，key/value对格式。</p>
<ul><li><p>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</p>
</li><li><p>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</p>
</li></ul>
<p>示例："foo": "bar"</p>
</td>
</tr>
</tbody>
</table>

**表 10**  PersistentVolumeSpec

<a name="response_PersistentVolumeSpec"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>flexVolume</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_FlexVolume">FlexVolume</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>Kubernetes的flexvolume存储插件</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>PersistentVolume的回收策略，包括：</p>
<ul><li><p>Retain：保留策略允许手动回收资源。当 PersistentVolumeClaim 被删除时，PersistentVolume 仍然存在，volume 被视为“已释放”。</p>
</li><li><p>Recycle：回收策略会在 volume上执行基本擦除（rm -rf / thevolume / *），可被再次声明使用。</p>
</li><li><p>Delete：对于支持删除回收策略的卷插件，删除操作将从 Kubernetes 中删除 PersistentVolume 对象，并删除外部基础架构中的关联存储资产。动态配置的卷继承其 StorageClass，默认为 Delete。</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>指定volume应该具有的访问模式。</p>
<ul><li><p>ReadWriteOnce：该卷可以被单个节点以读/写模式挂载</p>
<div class="note"><span class="notetitle"> 说明： </span><div class="notebody"><p>集群版本为v1.13.10且storage-driver版本为1.0.19时，才支持此功能。</p>
</div></div>
</li><li><p>ReadOnlyMany：该卷可以被多个节点以只读模式挂载</p>
</li><li><p>ReadWriteMany：该卷可以被多个节点以读/写模式挂载</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

**表 11**  FlexVolume

<a name="response_FlexVolume"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>driver</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>Flexvolume插件名称，请根据使用的存储类型填写：</p>
<ul><li><p>huawei.com/fuxivol (EVS)</p>
</li><li><p>huawei.com/fuxinfs (SFS)</p>
</li><li><p>huawei.com/fuxiobs (OBS)</p>
</li><li><p>huawei.com/fuxiefs (SFS Turbo)</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>文件系统类型，请根据使用的存储类型填写：</p>
<ul><li><p>ext4： EVS云硬盘存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0044.html" target="_blank" rel="noopener noreferrer">使用云硬盘存储卷</a>。</p>
</li><li><p>nfs：SFS弹性文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0111.html" target="_blank" rel="noopener noreferrer">使用文件存储卷</a>。</p>
</li><li><p>obs：OBS对象存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0160.html" target="_blank" rel="noopener noreferrer">使用对象存储卷</a>。</p>
</li><li><p>efs：SFS Turbo极速文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0125.html" target="_blank" rel="noopener noreferrer">使用极速文件存储卷</a>。</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>options</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_Options">Options</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>flexVolume配置项</p>
</td>
</tr>
</tbody>
</table>

**表 12**  Options

<a name="response_Options"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>文件系统类型，请根据使用的存储类型填写：</p>
<ul><li><p>ext4 (EVS)</p>
</li><li><p>nfs (SFS)</p>
</li><li><p>obs (OBS)</p>
</li><li><p>efs (SFS Turbo)</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>region</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>云存储所在的region。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>volumeID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>云存储的UUID，如果是OBS-bucket则填入名称</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>storageType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>指定云存储的类型。</p>
<ul><li><p>bs (EVS)</p>
</li><li><p>nfs (SFS)</p>
</li><li><p>obs (OBS)</p>
</li><li><p>efs (SFS Turbo)</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

**表 13**  PersistentVolumeStatus

<a name="response_PersistentVolumeStatus"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>显示volume实际具有的访问模式。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>phase</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>PersistentVolume当前所处的状态，包括：</p>
<ul><li><p>Available（可用）：还是空闲资源，没有被任何PVC绑定</p>
</li><li><p>Bound（已绑定）：卷已经被PVC绑定</p>
</li><li><p>Released（已释放）：之前绑定的PVC被删除，但是资源还未被集群重新声明</p>
</li><li><p>Failed（失败）：该卷的自动回收失败</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

## 请求示例

-   指定EVS云硬盘ID创建PersistentVolume 1.9版本的集群样例：

    ```
    {
      "apiVersion" : "v1",
      "kind" : "PersistentVolume",
      "metadata" : {
        "labels" : {
          "name" : "pv-test"
        },
        "name" : "pv-test"
      },
      "spec" : {
        "accessModes" : [ "ReadWriteMany" ],
        "flexVolume" : {
          "driver" : "huawei.com/fuxivol",
          "fsType" : "ext4",
          "options" : {
            "fsType" : "ext4",
            "kubernetes.io/namespace" : "default",
            "region" : "southchina",
            "volumeID" : "76e01b29-08b9-11e8-9ca5-1051722006ec",
            "storageType" : "bs"
          }
        },
        "persistentVolumeReclaimPolicy" : "Delete"
      }
    }
    ```

-   ```
{
  "apiVersion" : "v1",
  "kind" : "PersistentVolume",
  "metadata" : {
    "labels" : {
      "name" : "pv-test"
    },
    "name" : "pv-test"
  },
  "spec" : {
    "accessModes" : [ "ReadWriteMany" ],
    "flexVolume" : {
      "driver" : "huawei.com/fuxivol",
      "fsType" : "ext4",
      "options" : {
        "fsType" : "ext4",
        "region" : "southchina",
        "volumeID" : "76e01b29-08b9-11e8-9ca5-1051722006ec",
        "storageType" : "bs"
      }
    },
    "persistentVolumeReclaimPolicy" : "Delete"
  }
}
```


## 响应示例

**状态码为 201 时: **

创建PersistentVolume作业下发成功。

```
{
  "kind" : "PersistentVolume",
  "apiVersion" : "v1",
  "metadata" : {
    "name" : "pv-test",
    "namespace" : "default",
    "selfLink" : "/api/v1/namespaces/default/persistentvolumes/pv-test",
    "uid" : "e174188f-ff21-11e7-855b-fa163eaf5675",
    "resourceVersion" : "174229",
    "creationTimestamp" : "2018-01-22T03:11:03Z",
    "labels" : {
      "name" : "pv-test"
    },
    "enable" : true
  },
  "spec" : {
    "capacity" : {
      "storage" : "1Gi"
    },
    "accessModes" : [ "ReadWriteMany" ],
    "flexVolume" : {
      "driver" : "huawei.com/fuxivol",
      "fsType" : "ext4",
      "options" : {
        "fsType" : "ext4",
        "kubernetes.io/namespace" : "default",
        "volumeID" : "0781b22f-4d89-4e9c-b026-80e545cea16c"
      }
    },
    "persistentVolumeReclaimPolicy" : "Delete"
  },
  "status" : {
    "phase" : "Pending"
  }
}
```

## 状态码

<a name="table20"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p>状态码 </p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p>201</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p>创建PersistentVolume作业下发成功。</p>
</td>
</tr>
</tbody>
</table>

## 错误码

请参见[错误码](错误码.md)。

