# 删除PV（废弃）<a name="cce_02_0255"></a>

## 功能介绍

该API用于删除指定Namespace下的PV（PersistentVolume）对象，并可以选择是否保留后端云存储。

>![](public_sys-resources/icon-note.gif) **说明：** 
>存储管理的URL格式为：https://\{clusterid\}.Endpoint/uri。其中\{clusterid\}为集群ID，uri为资源路径，也即API访问的路径。如果使用https://Endpoint/uri，则必须指定请求header中的X-Cluster-ID参数。

## 调试

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?product=CCE&api=DeleteCloudPersistentVolumes)中调试该接口。

## URI

DELETE /api/v1/cloudpersistentvolumes/\{name\}

**表 1**  路径参数

<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>需要删除的PersistentVolume的名称</p>
<p>name格式为：Volume名称[?deleteVolume=BOOLEAN&amp;storageType=云存储类型]，中括号内可省略，示例：</p>
<p>volume-49f1?deleteVolume=true&amp;storageType=bs</p>
<p>volume-49f1</p>
<p>其中：</p>
<p>deleteVolume：删除PersistentVolume后是否保留后端关联的云存储。false表示不删除，ture表示删除，默认为false。</p>
<div class="note"><span class="notetitle"> 说明： </span><div class="notebody"><p>当为efs时，不支持删除存储，所以不能设为true。</p>
</div></div>
<p>storageType：云存储的类型，和deleteVolume搭配使用。即deleteVolume和storageType必须同时配置。</p>
<div class="note"><span class="notetitle"> 说明： </span><div class="notebody"><ul><li><p>bs：EVS云硬盘存储</p>
</li></ul>
</div></div>
<div class="note"><span class="notetitle"> 说明： </span><div class="notebody"><ul><li><p>nfs：SFS弹性文件存储</p>
</li></ul>
</div></div>
<div class="note"><span class="notetitle"> 说明： </span><div class="notebody"><ul><li><p>obs：OBS对象存储</p>
</li></ul>
</div></div>
<div class="note"><span class="notetitle"> 说明： </span><div class="notebody"><ul><li><p>efs：SFS Turbo极速文件存储</p>
</li></ul>
</div></div>
</td>
</tr>
</tbody>
</table>

## 请求参数

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>消息体的类型（格式）</p>
<p>缺省值：<strong>application/json</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>"调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="https://support.huaweicloud.com/api-cce/cce_02_0004.html#cce_02_0004__section2417768214391" target="_blank" rel="noopener noreferrer">获取token</a>。"</p>
<p>最大长度：<strong>16384</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>X-Cluster-ID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>集群ID，使用<strong>https://Endpoint/uri</strong>这种URL格式时必须指定此参数。获取方式请参见<a href="https://support.huaweicloud.com/api-cce/cce_02_0271.html" target="_blank" rel="noopener noreferrer">如何获取接口URI中参数</a></p>
</td>
</tr>
</tbody>
</table>

## 响应参数

**状态码： 200**

**表 3**  响应Body参数

<a name="response_PersistentVolume"></a>
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
<p>缺省值：<strong>v1</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>API类型，固定值<strong>PersistentVolume</strong></p>
<p>缺省值：<strong>PersistentVolume</strong></p>
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

**表 4**  PersistentVolumeMetadata

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

<p>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</p>
<ul><li><p>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</p>
</li></ul>
<p>示例："foo": "bar"</p>
</td>
</tr>
</tbody>
</table>

**表 5**  PersistentVolumeSpec

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

**表 6**  FlexVolume

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

**表 7**  Options

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
<ul><li><p>bs (EVS云硬盘存储)</p>
</li><li><p>nfs (SFS弹性文件存储)</p>
</li><li><p>obs (OBS对象存储)</p>
</li><li><p>efs (SFS Turbo)</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

**表 8**  PersistentVolumeStatus

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

无

## 响应示例

**状态码： 200**

删除指定PersistentVolume作业下发成功。

```
{
  "kind" : "PersistentVolume",
  "apiVersion" : "v1",
  "metadata" : {
    "name" : "pv-test",
    "selfLink" : "/api/v1/persistentvolumes/pv-test",
    "uid" : "0d93181d-3628-11e7-9093-fa163e8c373b",
    "resourceVersion" : "180886",
    "creationTimestamp" : "2017-05-11T08:58:51Z",
    "labels" : {
      "app" : "test"
    }
  },
  "spec" : {
    "flexVolume" : {
      "driver" : "huawei.com/fuxivol",
      "fsType" : "ext4",
      "options" : {
        "fsType" : "ext4",
        "kubernetes.io/namespace" : "default",
        "volumeID" : "0781b22f-4d89-4e9c-b026-80e545cea16c"
      }
    },
    "capacity" : {
      "storage" : "1Gi"
    },
    "accessModes" : [ "ReadWriteMany" ],
    "persistentVolumeReclaimPolicy" : "Delete"
  },
  "status" : {
    "phase" : "Available"
  }
}
```

## 状态码

<a name="status_code"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p>状态码 </p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p>删除指定PersistentVolume作业下发成功。</p>
</td>
</tr>
</tbody>
</table>

## 错误码

请参见[错误码](错误码.md)。

