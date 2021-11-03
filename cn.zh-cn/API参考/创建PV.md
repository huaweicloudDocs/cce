# 创建PV<a name="cce_02_0256_0"></a>

## 功能介绍<a name="section1337912142448"></a>

该API用于通过指定云存储服务中的云存储（如EVS、SFS、OBS）去创建PV（PersistentVolume）。该API已废弃，请使用[创建PersistentVolume](创建PersistentVolume.md)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>存储管理的URL格式为：https://\{clusterid\}.Endpoint/uri。其中\{clusterid\}为集群ID，uri为资源路径，也即API访问的路径。如果使用https://Endpoint/uri，则必须指定请求header中的X-Cluster-ID参数。

## URI<a name="section103801014104412"></a>

POST /api/v1/cloudpersistentvolumes

## 请求参数<a name="section738081414414"></a>

**表 1**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row138010146447"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1138151420448"><a name="p1138151420448"></a><a name="p1138151420448"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p2381111474417"><a name="p2381111474417"></a><a name="p2381111474417"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p0381101484411"><a name="p0381101484411"></a><a name="p0381101484411"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p638281494412"><a name="p638281494412"></a><a name="p638281494412"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row538121424414"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p63825142440"><a name="p63825142440"></a><a name="p63825142440"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p13382161464418"><a name="p13382161464418"></a><a name="p13382161464418"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p113821814134416"><a name="p113821814134416"></a><a name="p113821814134416"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p338231414419"><a name="p338231414419"></a><a name="p338231414419"></a>消息体的类型（格式）</p>
<p id="p6382101434417"><a name="p6382101434417"></a><a name="p6382101434417"></a>枚举值：</p>
<a name="ul93831114194416"></a><a name="ul93831114194416"></a><ul id="ul93831114194416"><li><strong id="b4383191424416"><a name="b4383191424416"></a><a name="b4383191424416"></a>application/json;charset=utf-8</strong></li><li><strong id="b838381418444"><a name="b838381418444"></a><a name="b838381418444"></a>application/json</strong></li></ul>
</td>
</tr>
<tr id="row938112147445"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p9383514164412"><a name="p9383514164412"></a><a name="p9383514164412"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p16383151434416"><a name="p16383151434416"></a><a name="p16383151434416"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p0383151415447"><a name="p0383151415447"></a><a name="p0383151415447"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p83831314134415"><a name="p83831314134415"></a><a name="p83831314134415"></a>调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="认证鉴权.md">获取token</a>。</p>
<p id="p638415148440"><a name="p638415148440"></a><a name="p638415148440"></a>最大长度：<strong id="b0384141464411"><a name="b0384141464411"></a><a name="b0384141464411"></a>16384</strong></p>
</td>
</tr>
<tr id="row11381191424410"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1138418143449"><a name="p1138418143449"></a><a name="p1138418143449"></a>X-Cluster-ID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p038471404412"><a name="p038471404412"></a><a name="p038471404412"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1238441411443"><a name="p1238441411443"></a><a name="p1238441411443"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p83841614204417"><a name="p83841614204417"></a><a name="p83841614204417"></a>集群 ID，使用<strong id="b338471415447"><a name="b338471415447"></a><a name="b338471415447"></a>https://Endpoint/uri</strong>这种URL格式时必须指定此参数。获取方式请参见<a href="如何获取接口URI中参数.md">如何获取接口URI中参数</a></p>
</td>
</tr>
</tbody>
</table>

**表 2**  请求Body参数

<a name="requestParameter"></a>
<table><thead align="left"><tr id="row5385714184416"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p838691416448"><a name="p838691416448"></a><a name="p838691416448"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p123871514194413"><a name="p123871514194413"></a><a name="p123871514194413"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p12387514134413"><a name="p12387514134413"></a><a name="p12387514134413"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p138721412446"><a name="p138721412446"></a><a name="p138721412446"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13385141418448"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p838721410440"><a name="p838721410440"></a><a name="p838721410440"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p123881014124419"><a name="p123881014124419"></a><a name="p123881014124419"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p11388141494411"><a name="p11388141494411"></a><a name="p11388141494411"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1538811142441"><a name="p1538811142441"></a><a name="p1538811142441"></a>API版本，固定值<strong id="b173881149447"><a name="b173881149447"></a><a name="b173881149447"></a>v1</strong></p>
<p id="p153881714114412"><a name="p153881714114412"></a><a name="p153881714114412"></a>缺省值：<strong id="b2388171410441"><a name="b2388171410441"></a><a name="b2388171410441"></a>v1</strong></p>
</td>
</tr>
<tr id="row1138551414412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p538891404417"><a name="p538891404417"></a><a name="p538891404417"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p20388161494418"><a name="p20388161494418"></a><a name="p20388161494418"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p18389111410448"><a name="p18389111410448"></a><a name="p18389111410448"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p03892144445"><a name="p03892144445"></a><a name="p03892144445"></a>API类型，固定值<strong id="b17389121416444"><a name="b17389121416444"></a><a name="b17389121416444"></a>PersistentVolume</strong></p>
<p id="p438941484416"><a name="p438941484416"></a><a name="p438941484416"></a>缺省值：<strong id="b93892149448"><a name="b93892149448"></a><a name="b93892149448"></a>PersistentVolume</strong></p>
</td>
</tr>
<tr id="row6385614144412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1338951416440"><a name="p1338951416440"></a><a name="p1338951416440"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1438918146444"><a name="p1438918146444"></a><a name="p1438918146444"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p33897145443"><a name="p33897145443"></a><a name="p33897145443"></a><a href="#request_PersistentVolumeMetadata">PersistentVolumeMetadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p103901814144414"><a name="p103901814144414"></a><a name="p103901814144414"></a>PersistentVolume的元数据信息</p>
</td>
</tr>
<tr id="row14385141412444"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p19390151414411"><a name="p19390151414411"></a><a name="p19390151414411"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1390161415448"><a name="p1390161415448"></a><a name="p1390161415448"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p19390161420441"><a name="p19390161420441"></a><a name="p19390161420441"></a><a href="#request_PersistentVolumeSpec">PersistentVolumeSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p13390121412445"><a name="p13390121412445"></a><a name="p13390121412445"></a>PersistentVolume的规格信息</p>
</td>
</tr>
<tr id="row838513149448"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18390131416447"><a name="p18390131416447"></a><a name="p18390131416447"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p143911214194415"><a name="p143911214194415"></a><a name="p143911214194415"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p3391214104417"><a name="p3391214104417"></a><a name="p3391214104417"></a><a href="#request_PersistentVolumeStatus">PersistentVolumeStatus</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p5391514174418"><a name="p5391514174418"></a><a name="p5391514174418"></a>PersistentVolume的状态信息</p>
</td>
</tr>
</tbody>
</table>

**表 3**  PersistentVolumeMetadata

<a name="request_PersistentVolumeMetadata"></a>
<table><thead align="left"><tr id="row16391914154419"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p93925142443"><a name="p93925142443"></a><a name="p93925142443"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p539221454417"><a name="p539221454417"></a><a name="p539221454417"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p7392191417442"><a name="p7392191417442"></a><a name="p7392191417442"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p1639391420446"><a name="p1639391420446"></a><a name="p1639391420446"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row143911614194410"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1439331454415"><a name="p1439331454415"></a><a name="p1439331454415"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p43931614124410"><a name="p43931614124410"></a><a name="p43931614124410"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p93937141440"><a name="p93937141440"></a><a name="p93937141440"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p14393141444412"><a name="p14393141444412"></a><a name="p14393141444412"></a>PersistentVolume名称，可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符，同一namespace下name不能重复。</p>
</td>
</tr>
<tr id="row939231419444"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1439331424412"><a name="p1439331424412"></a><a name="p1439331424412"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14394121424410"><a name="p14394121424410"></a><a name="p14394121424410"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p143941814184417"><a name="p143941814184417"></a><a name="p143941814184417"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p9394181413444"><a name="p9394181413444"></a><a name="p9394181413444"></a>PersistentVolume标签，key/value对格式。</p>
<a name="ul8394914144414"></a><a name="ul8394914144414"></a><ul id="ul8394914144414"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</li><li>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li></ul>
<p id="p0394614174417"><a name="p0394614174417"></a><a name="p0394614174417"></a>示例："foo": "bar"</p>
</td>
</tr>
</tbody>
</table>

**表 4**  PersistentVolumeSpec

<a name="request_PersistentVolumeSpec"></a>
<table><thead align="left"><tr id="row239512148443"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p93953143447"><a name="p93953143447"></a><a name="p93953143447"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p10395111419444"><a name="p10395111419444"></a><a name="p10395111419444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1239641474417"><a name="p1239641474417"></a><a name="p1239641474417"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p113963142440"><a name="p113963142440"></a><a name="p113963142440"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row4395171434412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p839631464414"><a name="p839631464414"></a><a name="p839631464414"></a>flexVolume</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p17396161474418"><a name="p17396161474418"></a><a name="p17396161474418"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p19396111454411"><a name="p19396111454411"></a><a name="p19396111454411"></a><a href="#request_FlexVolume">FlexVolume</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p639717144448"><a name="p639717144448"></a><a name="p639717144448"></a>Kubernetes的flexvolume存储插件</p>
</td>
</tr>
<tr id="row3395201444413"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1839715145447"><a name="p1839715145447"></a><a name="p1839715145447"></a>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p73974147441"><a name="p73974147441"></a><a name="p73974147441"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p239716143440"><a name="p239716143440"></a><a name="p239716143440"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1039719143441"><a name="p1039719143441"></a><a name="p1039719143441"></a>PersistentVolume的回收策略，包括：</p>
<a name="ul8397151416444"></a><a name="ul8397151416444"></a><ul id="ul8397151416444"><li>Retain：保留策略允许手动回收资源。当 PersistentVolumeClaim 被删除时，PersistentVolume 仍然存在，volume 被视为“已释放”。</li><li>Recycle：回收策略会在 volume上执行基本擦除（rm -rf / thevolume / *），可被再次声明使用。</li><li>Delete：对于支持删除回收策略的卷插件，删除操作将从 Kubernetes 中删除 PersistentVolume 对象，并删除外部基础架构中的关联存储资产。动态配置的卷继承其 StorageClass，默认为 Delete。</li></ul>
</td>
</tr>
<tr id="row10395101424411"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p33985144449"><a name="p33985144449"></a><a name="p33985144449"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p143981214114417"><a name="p143981214114417"></a><a name="p143981214114417"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1139861454416"><a name="p1139861454416"></a><a name="p1139861454416"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p113981714154414"><a name="p113981714154414"></a><a name="p113981714154414"></a>指定volume应该具有的访问模式。</p>
<a name="ul19398151412443"></a><a name="ul19398151412443"></a><ul id="ul19398151412443"><li>ReadWriteOnce：该卷可以被单个节点以读/写模式挂载<div class="note" id="note1039961417447"><a name="note1039961417447"></a><a name="note1039961417447"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p103994142449"><a name="p103994142449"></a><a name="p103994142449"></a>集群版本为v1.13.10且storage-driver版本为1.0.19时，才支持此功能。</p>
</div></div>
</li><li>ReadOnlyMany：该卷可以被多个节点以只读模式挂载</li><li>ReadWriteMany：该卷可以被多个节点以读/写模式挂载</li></ul>
</td>
</tr>
</tbody>
</table>

**表 5**  FlexVolume

<a name="request_FlexVolume"></a>
<table><thead align="left"><tr id="row1740041474418"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p16401714144414"><a name="p16401714144414"></a><a name="p16401714144414"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p540181413448"><a name="p540181413448"></a><a name="p540181413448"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p7401414104419"><a name="p7401414104419"></a><a name="p7401414104419"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p54011914174412"><a name="p54011914174412"></a><a name="p54011914174412"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row104001514184419"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p13401161412445"><a name="p13401161412445"></a><a name="p13401161412445"></a>driver</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1402714164418"><a name="p1402714164418"></a><a name="p1402714164418"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p204026146449"><a name="p204026146449"></a><a name="p204026146449"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p740220142442"><a name="p740220142442"></a><a name="p740220142442"></a>Flexvolume插件名称，请根据使用的存储类型填写：</p>
<a name="ul1340241434416"></a><a name="ul1340241434416"></a><ul id="ul1340241434416"><li>huawei.com/fuxivol (EVS)</li><li>huawei.com/fuxinfs (SFS)</li><li>huawei.com/fuxiobs (OBS)</li><li>huawei.com/fuxiefs (SFS Turbo)</li></ul>
</td>
</tr>
<tr id="row10400131414446"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p174031714104412"><a name="p174031714104412"></a><a name="p174031714104412"></a>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p11404814184413"><a name="p11404814184413"></a><a name="p11404814184413"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p114043146444"><a name="p114043146444"></a><a name="p114043146444"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p440451464417"><a name="p440451464417"></a><a name="p440451464417"></a>文件系统类型，请根据使用的存储类型填写：</p>
<a name="ul24045142448"></a><a name="ul24045142448"></a><ul id="ul24045142448"><li>ext4： EVS云硬盘存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0044.html" target="_blank" rel="noopener noreferrer">使用云硬盘存储卷</a>。</li><li>nfs：SFS弹性文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0111.html" target="_blank" rel="noopener noreferrer">使用文件存储卷</a>。</li><li>obs：OBS对象存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0160.html" target="_blank" rel="noopener noreferrer">使用对象存储卷</a>。</li><li>efs：SFS Turbo极速文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0125.html" target="_blank" rel="noopener noreferrer">使用极速文件存储卷</a>。</li></ul>
</td>
</tr>
<tr id="row640001412448"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p3405314164419"><a name="p3405314164419"></a><a name="p3405314164419"></a>options</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p7405161415441"><a name="p7405161415441"></a><a name="p7405161415441"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p18405514114420"><a name="p18405514114420"></a><a name="p18405514114420"></a><a href="#request_Options">Options</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p11406151410445"><a name="p11406151410445"></a><a name="p11406151410445"></a>flexVolume配置项</p>
</td>
</tr>
</tbody>
</table>

**表 6**  Options

<a name="request_Options"></a>
<table><thead align="left"><tr id="row3406214194411"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p3407121474412"><a name="p3407121474412"></a><a name="p3407121474412"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p17407814154411"><a name="p17407814154411"></a><a name="p17407814154411"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p34071514124410"><a name="p34071514124410"></a><a name="p34071514124410"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p3407214124419"><a name="p3407214124419"></a><a name="p3407214124419"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row64062142440"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p8407614204411"><a name="p8407614204411"></a><a name="p8407614204411"></a>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p16408151474418"><a name="p16408151474418"></a><a name="p16408151474418"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p44089144448"><a name="p44089144448"></a><a name="p44089144448"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p640871411449"><a name="p640871411449"></a><a name="p640871411449"></a>文件系统类型，请根据使用的存储类型填写：</p>
<a name="ul1540801420440"></a><a name="ul1540801420440"></a><ul id="ul1540801420440"><li>ext4 (EVS)</li><li>nfs (SFS)</li><li>obs (OBS)</li><li>efs (SFS Turbo)</li></ul>
</td>
</tr>
<tr id="row74061214194414"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p134093148441"><a name="p134093148441"></a><a name="p134093148441"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14409121474411"><a name="p14409121474411"></a><a name="p14409121474411"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p940961474414"><a name="p940961474414"></a><a name="p940961474414"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p14093143442"><a name="p14093143442"></a><a name="p14093143442"></a>云存储所在的region。</p>
</td>
</tr>
<tr id="row1340681411440"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p8409191418443"><a name="p8409191418443"></a><a name="p8409191418443"></a>volumeID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1141051444419"><a name="p1141051444419"></a><a name="p1141051444419"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1241015149447"><a name="p1241015149447"></a><a name="p1241015149447"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p134103147449"><a name="p134103147449"></a><a name="p134103147449"></a>云存储的UUID，如果是OBS-bucket则填入名称</p>
</td>
</tr>
<tr id="row0406191404413"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p104101814194418"><a name="p104101814194418"></a><a name="p104101814194418"></a>storageType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p15410914204412"><a name="p15410914204412"></a><a name="p15410914204412"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p3410914174410"><a name="p3410914174410"></a><a name="p3410914174410"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p8411614104414"><a name="p8411614104414"></a><a name="p8411614104414"></a>指定云存储的类型。</p>
<a name="ul741151494416"></a><a name="ul741151494416"></a><ul id="ul741151494416"><li>bs (EVS)</li><li>nfs (SFS)</li><li>obs (OBS)</li><li>efs (SFS Turbo)</li></ul>
</td>
</tr>
</tbody>
</table>

**表 7**  PersistentVolumeStatus

<a name="request_PersistentVolumeStatus"></a>
<table><thead align="left"><tr id="row941211424410"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p14412161417443"><a name="p14412161417443"></a><a name="p14412161417443"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p341211444410"><a name="p341211444410"></a><a name="p341211444410"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1541212144449"><a name="p1541212144449"></a><a name="p1541212144449"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p1413191434414"><a name="p1413191434414"></a><a name="p1413191434414"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row8412131415442"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1941391474419"><a name="p1941391474419"></a><a name="p1941391474419"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p17413151410446"><a name="p17413151410446"></a><a name="p17413151410446"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1341341412442"><a name="p1341341412442"></a><a name="p1341341412442"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p84131214124417"><a name="p84131214124417"></a><a name="p84131214124417"></a>显示volume实际具有的访问模式。</p>
</td>
</tr>
<tr id="row341214147444"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p94133141443"><a name="p94133141443"></a><a name="p94133141443"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p7414111454417"><a name="p7414111454417"></a><a name="p7414111454417"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p0414181474410"><a name="p0414181474410"></a><a name="p0414181474410"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p10414714164414"><a name="p10414714164414"></a><a name="p10414714164414"></a>PersistentVolume当前所处的状态，包括：</p>
<a name="ul3414161420441"></a><a name="ul3414161420441"></a><ul id="ul3414161420441"><li>Available（可用）：还是空闲资源，没有被任何PVC绑定</li><li>Bound（已绑定）：卷已经被PVC绑定</li><li>Released（已释放）：之前绑定的PVC被删除，但是资源还未被集群重新声明</li><li>Failed（失败）：该卷的自动回收失败</li></ul>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section4415141444418"></a>

**状态码： 201**

**表 8**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row8415114144419"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1541661474416"><a name="p1541661474416"></a><a name="p1541661474416"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p13416114134416"><a name="p13416114134416"></a><a name="p13416114134416"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p10416414134411"><a name="p10416414134411"></a><a name="p10416414134411"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row9415171411448"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p11417214114419"><a name="p11417214114419"></a><a name="p11417214114419"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p3417151411444"><a name="p3417151411444"></a><a name="p3417151411444"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p104174145444"><a name="p104174145444"></a><a name="p104174145444"></a>API版本，固定值<strong id="b74171414124419"><a name="b74171414124419"></a><a name="b74171414124419"></a>v1</strong></p>
<p id="p1041711418446"><a name="p1041711418446"></a><a name="p1041711418446"></a>缺省值：<strong id="b154171114184420"><a name="b154171114184420"></a><a name="b154171114184420"></a>v1</strong></p>
</td>
</tr>
<tr id="row1415131454419"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p7417111411440"><a name="p7417111411440"></a><a name="p7417111411440"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1841713148446"><a name="p1841713148446"></a><a name="p1841713148446"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p164180141447"><a name="p164180141447"></a><a name="p164180141447"></a>API类型，固定值<strong id="b141851410448"><a name="b141851410448"></a><a name="b141851410448"></a>PersistentVolume</strong></p>
<p id="p8418121494416"><a name="p8418121494416"></a><a name="p8418121494416"></a>缺省值：<strong id="b54181714124410"><a name="b54181714124410"></a><a name="b54181714124410"></a>PersistentVolume</strong></p>
</td>
</tr>
<tr id="row2415314124413"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p6418181418442"><a name="p6418181418442"></a><a name="p6418181418442"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p18418111416448"><a name="p18418111416448"></a><a name="p18418111416448"></a><a href="#response_PersistentVolumeMetadata">PersistentVolumeMetadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19418114194413"><a name="p19418114194413"></a><a name="p19418114194413"></a>PersistentVolume的元数据信息</p>
</td>
</tr>
<tr id="row11416121444419"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1418141412447"><a name="p1418141412447"></a><a name="p1418141412447"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p154191614124418"><a name="p154191614124418"></a><a name="p154191614124418"></a><a href="#response_PersistentVolumeSpec">PersistentVolumeSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p24191514114419"><a name="p24191514114419"></a><a name="p24191514114419"></a>PersistentVolume的规格信息</p>
</td>
</tr>
<tr id="row6416414134412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p64192149445"><a name="p64192149445"></a><a name="p64192149445"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1341913146449"><a name="p1341913146449"></a><a name="p1341913146449"></a><a href="#response_PersistentVolumeStatus">PersistentVolumeStatus</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19991161464418"><a name="p19991161464418"></a><a name="p19991161464418"></a>PersistentVolume的状态信息</p>
</td>
</tr>
</tbody>
</table>

**表 9**  PersistentVolumeMetadata

<a name="response_PersistentVolumeMetadata"></a>
<table><thead align="left"><tr id="row1742111484412"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1199171416444"><a name="p1199171416444"></a><a name="p1199171416444"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p12991171424411"><a name="p12991171424411"></a><a name="p12991171424411"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p8992111484420"><a name="p8992111484420"></a><a name="p8992111484420"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row17421191464411"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p17992141414449"><a name="p17992141414449"></a><a name="p17992141414449"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14992191417440"><a name="p14992191417440"></a><a name="p14992191417440"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p179921314114411"><a name="p179921314114411"></a><a name="p179921314114411"></a>PersistentVolume名称，可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符，同一namespace下name不能重复。</p>
</td>
</tr>
<tr id="row442111419442"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p12992181444410"><a name="p12992181444410"></a><a name="p12992181444410"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p9992151484410"><a name="p9992151484410"></a><a name="p9992151484410"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p129927142443"><a name="p129927142443"></a><a name="p129927142443"></a>PersistentVolume标签，key/value对格式。</p>
<a name="ul699241484418"></a><a name="ul699241484418"></a><ul id="ul699241484418"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</li><li>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li></ul>
<p id="p189925142442"><a name="p189925142442"></a><a name="p189925142442"></a>示例："foo": "bar"</p>
</td>
</tr>
</tbody>
</table>

**表 10**  PersistentVolumeSpec

<a name="response_PersistentVolumeSpec"></a>
<table><thead align="left"><tr id="row842371454413"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p189921014104412"><a name="p189921014104412"></a><a name="p189921014104412"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p699211418447"><a name="p699211418447"></a><a name="p699211418447"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p9992131417444"><a name="p9992131417444"></a><a name="p9992131417444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row17423141454417"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p6992201414417"><a name="p6992201414417"></a><a name="p6992201414417"></a>flexVolume</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1199261464411"><a name="p1199261464411"></a><a name="p1199261464411"></a><a href="#response_FlexVolume">FlexVolume</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1999281410447"><a name="p1999281410447"></a><a name="p1999281410447"></a>Kubernetes的flexvolume存储插件</p>
</td>
</tr>
<tr id="row134231214154412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18992151434412"><a name="p18992151434412"></a><a name="p18992151434412"></a>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p159931314104416"><a name="p159931314104416"></a><a name="p159931314104416"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p099361411449"><a name="p099361411449"></a><a name="p099361411449"></a>PersistentVolume的回收策略，包括：</p>
<a name="ul69934142440"></a><a name="ul69934142440"></a><ul id="ul69934142440"><li>Retain：保留策略允许手动回收资源。当 PersistentVolumeClaim 被删除时，PersistentVolume 仍然存在，volume 被视为“已释放”。</li><li>Recycle：回收策略会在 volume上执行基本擦除（rm -rf / thevolume / *），可被再次声明使用。</li><li>Delete：对于支持删除回收策略的卷插件，删除操作将从 Kubernetes 中删除 PersistentVolume 对象，并删除外部基础架构中的关联存储资产。动态配置的卷继承其 StorageClass，默认为 Delete。</li></ul>
</td>
</tr>
<tr id="row1942314141445"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p499371404418"><a name="p499371404418"></a><a name="p499371404418"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1799341415445"><a name="p1799341415445"></a><a name="p1799341415445"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p599331414420"><a name="p599331414420"></a><a name="p599331414420"></a>指定volume应该具有的访问模式。</p>
<a name="ul12993181414442"></a><a name="ul12993181414442"></a><ul id="ul12993181414442"><li>ReadWriteOnce：该卷可以被单个节点以读/写模式挂载<div class="note" id="note799311145444"><a name="note799311145444"></a><a name="note799311145444"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p69934147443"><a name="p69934147443"></a><a name="p69934147443"></a>集群版本为v1.13.10且storage-driver版本为1.0.19时，才支持此功能。</p>
</div></div>
</li><li>ReadOnlyMany：该卷可以被多个节点以只读模式挂载</li><li>ReadWriteMany：该卷可以被多个节点以读/写模式挂载</li></ul>
</td>
</tr>
</tbody>
</table>

**表 11**  FlexVolume

<a name="response_FlexVolume"></a>
<table><thead align="left"><tr id="row14426414134410"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p89938141447"><a name="p89938141447"></a><a name="p89938141447"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p16993141419446"><a name="p16993141419446"></a><a name="p16993141419446"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p17994191418446"><a name="p17994191418446"></a><a name="p17994191418446"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2426201414445"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1994161418440"><a name="p1994161418440"></a><a name="p1994161418440"></a>driver</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p13994114144411"><a name="p13994114144411"></a><a name="p13994114144411"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p7994111464420"><a name="p7994111464420"></a><a name="p7994111464420"></a>Flexvolume插件名称，请根据使用的存储类型填写：</p>
<a name="ul599481413448"></a><a name="ul599481413448"></a><ul id="ul599481413448"><li>huawei.com/fuxivol (EVS)</li><li>huawei.com/fuxinfs (SFS)</li><li>huawei.com/fuxiobs (OBS)</li><li>huawei.com/fuxiefs (SFS Turbo)</li></ul>
</td>
</tr>
<tr id="row10426181418441"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p199411142448"><a name="p199411142448"></a><a name="p199411142448"></a>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p19942014184411"><a name="p19942014184411"></a><a name="p19942014184411"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p499471412446"><a name="p499471412446"></a><a name="p499471412446"></a>文件系统类型，请根据使用的存储类型填写：</p>
<a name="ul1994121454410"></a><a name="ul1994121454410"></a><ul id="ul1994121454410"><li>ext4： EVS云硬盘存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0044.html" target="_blank" rel="noopener noreferrer">使用云硬盘存储卷</a>。</li><li>nfs：SFS弹性文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0111.html" target="_blank" rel="noopener noreferrer">使用文件存储卷</a>。</li><li>obs：OBS对象存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0160.html" target="_blank" rel="noopener noreferrer">使用对象存储卷</a>。</li><li>efs：SFS Turbo极速文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0125.html" target="_blank" rel="noopener noreferrer">使用极速文件存储卷</a>。</li></ul>
</td>
</tr>
<tr id="row8426914184419"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p499416142441"><a name="p499416142441"></a><a name="p499416142441"></a>options</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p179941814194417"><a name="p179941814194417"></a><a name="p179941814194417"></a><a href="#response_Options">Options</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p8994014164410"><a name="p8994014164410"></a><a name="p8994014164410"></a>flexVolume配置项</p>
</td>
</tr>
</tbody>
</table>

**表 12**  Options

<a name="response_Options"></a>
<table><thead align="left"><tr id="row742913146449"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p17995914174413"><a name="p17995914174413"></a><a name="p17995914174413"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p13995414154420"><a name="p13995414154420"></a><a name="p13995414154420"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p19995121412442"><a name="p19995121412442"></a><a name="p19995121412442"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1442971417448"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15995181420445"><a name="p15995181420445"></a><a name="p15995181420445"></a>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p209951414184417"><a name="p209951414184417"></a><a name="p209951414184417"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p69951114114416"><a name="p69951114114416"></a><a name="p69951114114416"></a>文件系统类型，请根据使用的存储类型填写：</p>
<a name="ul9995151464418"></a><a name="ul9995151464418"></a><ul id="ul9995151464418"><li>ext4 (EVS)</li><li>nfs (SFS)</li><li>obs (OBS)</li><li>efs (SFS Turbo)</li></ul>
</td>
</tr>
<tr id="row18429171413440"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p299531444413"><a name="p299531444413"></a><a name="p299531444413"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p69951514174417"><a name="p69951514174417"></a><a name="p69951514174417"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19995111484416"><a name="p19995111484416"></a><a name="p19995111484416"></a>云存储所在的region。</p>
</td>
</tr>
<tr id="row1842961415446"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p999518143445"><a name="p999518143445"></a><a name="p999518143445"></a>volumeID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p199515149443"><a name="p199515149443"></a><a name="p199515149443"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p29954148448"><a name="p29954148448"></a><a name="p29954148448"></a>云存储的UUID，如果是OBS-bucket则填入名称</p>
</td>
</tr>
<tr id="row142911416444"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p13995914174413"><a name="p13995914174413"></a><a name="p13995914174413"></a>storageType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p18995414184413"><a name="p18995414184413"></a><a name="p18995414184413"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p18995111412441"><a name="p18995111412441"></a><a name="p18995111412441"></a>指定云存储的类型。</p>
<a name="ul14995814114414"></a><a name="ul14995814114414"></a><ul id="ul14995814114414"><li>bs (EVS)</li><li>nfs (SFS)</li><li>obs (OBS)</li><li>efs (SFS Turbo)</li></ul>
</td>
</tr>
</tbody>
</table>

**表 13**  PersistentVolumeStatus

<a name="response_PersistentVolumeStatus"></a>
<table><thead align="left"><tr id="row11432191444410"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p899691484417"><a name="p899691484417"></a><a name="p899691484417"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p3996111413448"><a name="p3996111413448"></a><a name="p3996111413448"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p13996121464414"><a name="p13996121464414"></a><a name="p13996121464414"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row184321414114420"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p179961014164417"><a name="p179961014164417"></a><a name="p179961014164417"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p29965146442"><a name="p29965146442"></a><a name="p29965146442"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1499612149448"><a name="p1499612149448"></a><a name="p1499612149448"></a>显示volume实际具有的访问模式。</p>
</td>
</tr>
<tr id="row164321614154414"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1599631414419"><a name="p1599631414419"></a><a name="p1599631414419"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p17996141474417"><a name="p17996141474417"></a><a name="p17996141474417"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p599631474415"><a name="p599631474415"></a><a name="p599631474415"></a>PersistentVolume当前所处的状态，包括：</p>
<a name="ul49967141447"></a><a name="ul49967141447"></a><ul id="ul49967141447"><li>Available（可用）：还是空闲资源，没有被任何PVC绑定</li><li>Bound（已绑定）：卷已经被PVC绑定</li><li>Released（已释放）：之前绑定的PVC被删除，但是资源还未被集群重新声明</li><li>Failed（失败）：该卷的自动回收失败</li></ul>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section15996414194417"></a>

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


## 响应示例<a name="section199891418446"></a>

**状态码： 201**

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

## 状态码<a name="section169994142447"></a>

<a name="status_code"></a>
<table><thead align="left"><tr id="row1944131444420"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p18999114104416"><a name="p18999114104416"></a><a name="p18999114104416"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p1699918148441"><a name="p1699918148441"></a><a name="p1699918148441"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row84411314144411"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p19999141464417"><a name="p19999141464417"></a><a name="p19999141464417"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p13999191424418"><a name="p13999191424418"></a><a name="p13999191424418"></a>创建PersistentVolume作业下发成功。</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section60161515442"></a>

请参见[错误码](错误码.md)。

