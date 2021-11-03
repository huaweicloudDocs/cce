# 删除PV<a name="cce_02_0255_0"></a>

## 功能介绍<a name="section16489614164410"></a>

该API用于删除指定Namespace下的PV（PersistentVolume）对象，并可以选择是否保留后端云存储。该API已废弃，请使用[删除指定的PersistentVolume](删除指定的PersistentVolume.md)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>存储管理的URL格式为：https://\{clusterid\}.Endpoint/uri。其中\{clusterid\}为集群ID，uri为资源路径，也即API访问的路径。如果使用https://Endpoint/uri，则必须指定请求header中的X-Cluster-ID参数。

## URI<a name="section174901714154416"></a>

DELETE /api/v1/cloudpersistentvolumes/\{name\}

**表 1**  路径参数

<a name="table9491131434414"></a>
<table><thead align="left"><tr id="row1049161413440"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p649113142449"><a name="p649113142449"></a><a name="p649113142449"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p3491121418446"><a name="p3491121418446"></a><a name="p3491121418446"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p84923149440"><a name="p84923149440"></a><a name="p84923149440"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p114921614144413"><a name="p114921614144413"></a><a name="p114921614144413"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18491111484417"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1449271444412"><a name="p1449271444412"></a><a name="p1449271444412"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p124927144443"><a name="p124927144443"></a><a name="p124927144443"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p144938146442"><a name="p144938146442"></a><a name="p144938146442"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p164931614164419"><a name="p164931614164419"></a><a name="p164931614164419"></a>需要删除的PersistentVolume的名称</p>
<p id="p349319141447"><a name="p349319141447"></a><a name="p349319141447"></a>name格式为：Volume名称?deleteVolume=BOOLEAN&amp;storageType=云存储类型]，中括号内可省略，示例：</p>
<p id="p104931714164411"><a name="p104931714164411"></a><a name="p104931714164411"></a>volume-49f1?deleteVolume=true&amp;storageType=bs</p>
<p id="p449311494410"><a name="p449311494410"></a><a name="p449311494410"></a>volume-49f1</p>
<p id="p14947148449"><a name="p14947148449"></a><a name="p14947148449"></a>其中：</p>
<p id="p149481494412"><a name="p149481494412"></a><a name="p149481494412"></a>deleteVolume：删除PersistentVolume后是否保留后端关联的云存储。false表示不删除，ture表示删除，默认为false。</p>
<div class="note" id="note1649414141445"><a name="note1649414141445"></a><a name="note1649414141445"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1849401494415"><a name="p1849401494415"></a><a name="p1849401494415"></a>当为efs时，不支持删除存储，所以不能设为true。</p>
</div></div>
<p id="p1494161424411"><a name="p1494161424411"></a><a name="p1494161424411"></a>storageType：云存储的类型，和deleteVolume搭配使用。即deleteVolume和storageType必须同时配置。</p>
<div class="note" id="note134949141449"><a name="note134949141449"></a><a name="note134949141449"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul6495131424413"></a><a name="ul6495131424413"></a><ul id="ul6495131424413"><li>bs：EVS云存储</li><li>nfs：SFS弹性文件存储</li><li>obs：OBS对象存储 [&gt;   - efs：SFS Turbo极速文件存储</li></ul>
</div></div>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section24952146446"></a>

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row1749591413441"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p114961414144415"><a name="p114961414144415"></a><a name="p114961414144415"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p19496181417444"><a name="p19496181417444"></a><a name="p19496181417444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p18496201444413"><a name="p18496201444413"></a><a name="p18496201444413"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p6497131494411"><a name="p6497131494411"></a><a name="p6497131494411"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row184961014124411"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p114973147447"><a name="p114973147447"></a><a name="p114973147447"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1497101404411"><a name="p1497101404411"></a><a name="p1497101404411"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p184974145449"><a name="p184974145449"></a><a name="p184974145449"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p124971914134411"><a name="p124971914134411"></a><a name="p124971914134411"></a>消息体的类型（格式）</p>
<p id="p44976144449"><a name="p44976144449"></a><a name="p44976144449"></a>枚举值：</p>
<a name="ul4498131484418"></a><a name="ul4498131484418"></a><ul id="ul4498131484418"><li><strong id="b649816141448"><a name="b649816141448"></a><a name="b649816141448"></a>application/json;charset=utf-8</strong></li><li><strong id="b1149871413442"><a name="b1149871413442"></a><a name="b1149871413442"></a>application/json</strong></li></ul>
</td>
</tr>
<tr id="row14496514154418"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p3498191410444"><a name="p3498191410444"></a><a name="p3498191410444"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p12498121411443"><a name="p12498121411443"></a><a name="p12498121411443"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1449891414442"><a name="p1449891414442"></a><a name="p1449891414442"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p249851444411"><a name="p249851444411"></a><a name="p249851444411"></a>调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="认证鉴权.md">获取token</a>。</p>
<p id="p1649941419444"><a name="p1649941419444"></a><a name="p1649941419444"></a>最大长度：<strong id="b1749991412441"><a name="b1749991412441"></a><a name="b1749991412441"></a>16384</strong></p>
</td>
</tr>
<tr id="row74961814144410"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p144991414104418"><a name="p144991414104418"></a><a name="p144991414104418"></a>X-Cluster-ID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p194995143440"><a name="p194995143440"></a><a name="p194995143440"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p249921410441"><a name="p249921410441"></a><a name="p249921410441"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1499121424416"><a name="p1499121424416"></a><a name="p1499121424416"></a>集群 ID，使用<strong id="b17499171474418"><a name="b17499171474418"></a><a name="b17499171474418"></a>https://Endpoint/uri</strong>这种URL格式时必须指定此参数。获取方式请参见<a href="如何获取接口URI中参数.md">如何获取接口URI中参数</a></p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section3499114154419"></a>

**状态码： 200**

**表 3**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row145008146444"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1750181420445"><a name="p1750181420445"></a><a name="p1750181420445"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p75012146443"><a name="p75012146443"></a><a name="p75012146443"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p750131412446"><a name="p750131412446"></a><a name="p750131412446"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row205006140441"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1750116142446"><a name="p1750116142446"></a><a name="p1750116142446"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14501114174419"><a name="p14501114174419"></a><a name="p14501114174419"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p350171494416"><a name="p350171494416"></a><a name="p350171494416"></a>API版本，固定值<strong id="b350212142448"><a name="b350212142448"></a><a name="b350212142448"></a>v1</strong></p>
<p id="p1350241415449"><a name="p1350241415449"></a><a name="p1350241415449"></a>缺省值：<strong id="b45028147448"><a name="b45028147448"></a><a name="b45028147448"></a>v1</strong></p>
</td>
</tr>
<tr id="row65009149443"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p175021914114415"><a name="p175021914114415"></a><a name="p175021914114415"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1050211414416"><a name="p1050211414416"></a><a name="p1050211414416"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p650213144445"><a name="p650213144445"></a><a name="p650213144445"></a>API类型，固定值<strong id="b1150231404417"><a name="b1150231404417"></a><a name="b1150231404417"></a>PersistentVolume</strong></p>
<p id="p450214142448"><a name="p450214142448"></a><a name="p450214142448"></a>缺省值：<strong id="b15502614194420"><a name="b15502614194420"></a><a name="b15502614194420"></a>PersistentVolume</strong></p>
</td>
</tr>
<tr id="row85002142443"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18503314204410"><a name="p18503314204410"></a><a name="p18503314204410"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p10503191416447"><a name="p10503191416447"></a><a name="p10503191416447"></a><a href="#response_PersistentVolumeMetadata">PersistentVolumeMetadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p150318149448"><a name="p150318149448"></a><a name="p150318149448"></a>PersistentVolume的元数据信息</p>
</td>
</tr>
<tr id="row1550071484418"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1050319142441"><a name="p1050319142441"></a><a name="p1050319142441"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p75048147442"><a name="p75048147442"></a><a name="p75048147442"></a><a href="#response_PersistentVolumeSpec">PersistentVolumeSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p11504111418447"><a name="p11504111418447"></a><a name="p11504111418447"></a>PersistentVolume的规格信息</p>
</td>
</tr>
<tr id="row1500131418444"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p75042014164418"><a name="p75042014164418"></a><a name="p75042014164418"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1505814144420"><a name="p1505814144420"></a><a name="p1505814144420"></a><a href="#response_PersistentVolumeStatus">PersistentVolumeStatus</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p145051714184411"><a name="p145051714184411"></a><a name="p145051714184411"></a>PersistentVolume的状态信息</p>
</td>
</tr>
</tbody>
</table>

**表 4**  PersistentVolumeMetadata

<a name="response_PersistentVolumeMetadata"></a>
<table><thead align="left"><tr id="row1850571417444"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p16506314184411"><a name="p16506314184411"></a><a name="p16506314184411"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p15506214174418"><a name="p15506214174418"></a><a name="p15506214174418"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p1650641474413"><a name="p1650641474413"></a><a name="p1650641474413"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row125051114134414"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p175061146441"><a name="p175061146441"></a><a name="p175061146441"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p150651412449"><a name="p150651412449"></a><a name="p150651412449"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17507914184414"><a name="p17507914184414"></a><a name="p17507914184414"></a>PersistentVolume名称，可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符，同一namespace下name不能重复。</p>
</td>
</tr>
<tr id="row165051414184411"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p185076145442"><a name="p185076145442"></a><a name="p185076145442"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p20507151424417"><a name="p20507151424417"></a><a name="p20507151424417"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p13507114104412"><a name="p13507114104412"></a><a name="p13507114104412"></a>PersistentVolume标签，key/value对格式。</p>
<a name="ul75071714144416"></a><a name="ul75071714144416"></a><ul id="ul75071714144416"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</li><li>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li></ul>
<p id="p2050871418449"><a name="p2050871418449"></a><a name="p2050871418449"></a>示例："foo": "bar"</p>
</td>
</tr>
</tbody>
</table>

**表 5**  PersistentVolumeSpec

<a name="response_PersistentVolumeSpec"></a>
<table><thead align="left"><tr id="row185082147446"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p155081014134411"><a name="p155081014134411"></a><a name="p155081014134411"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p175091714144419"><a name="p175091714144419"></a><a name="p175091714144419"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p16509191444413"><a name="p16509191444413"></a><a name="p16509191444413"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1250815141446"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p8509141484417"><a name="p8509141484417"></a><a name="p8509141484417"></a>flexVolume</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16509161411448"><a name="p16509161411448"></a><a name="p16509161411448"></a><a href="#response_FlexVolume">FlexVolume</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p175091714104419"><a name="p175091714104419"></a><a name="p175091714104419"></a>Kubernetes的flexvolume存储插件</p>
</td>
</tr>
<tr id="row10508101416445"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p12510514124416"><a name="p12510514124416"></a><a name="p12510514124416"></a>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1651041420449"><a name="p1651041420449"></a><a name="p1651041420449"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p351011494413"><a name="p351011494413"></a><a name="p351011494413"></a>PersistentVolume的回收策略，包括：</p>
<a name="ul9510101412447"></a><a name="ul9510101412447"></a><ul id="ul9510101412447"><li>Retain：保留策略允许手动回收资源。当 PersistentVolumeClaim 被删除时，PersistentVolume 仍然存在，volume 被视为“已释放”。</li><li>Recycle：回收策略会在 volume上执行基本擦除（rm -rf / thevolume / *），可被再次声明使用。</li><li>Delete：对于支持删除回收策略的卷插件，删除操作将从 Kubernetes 中删除 PersistentVolume 对象，并删除外部基础架构中的关联存储资产。动态配置的卷继承其 StorageClass，默认为 Delete。</li></ul>
</td>
</tr>
<tr id="row7508714164411"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1151111474410"><a name="p1151111474410"></a><a name="p1151111474410"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p135111114194420"><a name="p135111114194420"></a><a name="p135111114194420"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p151141454420"><a name="p151141454420"></a><a name="p151141454420"></a>指定volume应该具有的访问模式。</p>
<a name="ul651116147447"></a><a name="ul651116147447"></a><ul id="ul651116147447"><li>ReadWriteOnce：该卷可以被单个节点以读/写模式挂载<div class="note" id="note551211411443"><a name="note551211411443"></a><a name="note551211411443"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p0512714124419"><a name="p0512714124419"></a><a name="p0512714124419"></a>集群版本为v1.13.10且storage-driver版本为1.0.19时，才支持此功能。</p>
</div></div>
</li><li>ReadOnlyMany：该卷可以被多个节点以只读模式挂载</li><li>ReadWriteMany：该卷可以被多个节点以读/写模式挂载</li></ul>
</td>
</tr>
</tbody>
</table>

**表 6**  FlexVolume

<a name="response_FlexVolume"></a>
<table><thead align="left"><tr id="row9513111413444"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p351411149442"><a name="p351411149442"></a><a name="p351411149442"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1051410147444"><a name="p1051410147444"></a><a name="p1051410147444"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p251441414444"><a name="p251441414444"></a><a name="p251441414444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row135132147448"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p451551410445"><a name="p451551410445"></a><a name="p451551410445"></a>driver</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1451520144441"><a name="p1451520144441"></a><a name="p1451520144441"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p2515191484411"><a name="p2515191484411"></a><a name="p2515191484411"></a>Flexvolume插件名称，请根据使用的存储类型填写：</p>
<a name="ul851591420447"></a><a name="ul851591420447"></a><ul id="ul851591420447"><li>huawei.com/fuxivol (EVS)</li><li>huawei.com/fuxinfs (SFS)</li><li>huawei.com/fuxiobs (OBS)</li><li>huawei.com/fuxiefs (SFS Turbo)</li></ul>
</td>
</tr>
<tr id="row11513714144416"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p12516131444416"><a name="p12516131444416"></a><a name="p12516131444416"></a>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p13516181494414"><a name="p13516181494414"></a><a name="p13516181494414"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1516314194420"><a name="p1516314194420"></a><a name="p1516314194420"></a>文件系统类型，请根据使用的存储类型填写：</p>
<a name="ul35164141444"></a><a name="ul35164141444"></a><ul id="ul35164141444"><li>ext4： EVS云硬盘存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0044.html" target="_blank" rel="noopener noreferrer">使用云硬盘存储卷</a>。</li><li>nfs：SFS弹性文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0111.html" target="_blank" rel="noopener noreferrer">使用文件存储卷</a>。</li><li>obs：OBS对象存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0160.html" target="_blank" rel="noopener noreferrer">使用对象存储卷</a>。</li><li>efs：SFS Turbo极速文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0125.html" target="_blank" rel="noopener noreferrer">使用极速文件存储卷</a>。</li></ul>
</td>
</tr>
<tr id="row135131214194418"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p651714144449"><a name="p651714144449"></a><a name="p651714144449"></a>options</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p7517714164414"><a name="p7517714164414"></a><a name="p7517714164414"></a><a href="#response_Options">Options</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p451781410444"><a name="p451781410444"></a><a name="p451781410444"></a>flexVolume配置项</p>
</td>
</tr>
</tbody>
</table>

**表 7**  Options

<a name="response_Options"></a>
<table><thead align="left"><tr id="row2518814194420"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p165197143441"><a name="p165197143441"></a><a name="p165197143441"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p95192141443"><a name="p95192141443"></a><a name="p95192141443"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p45190149440"><a name="p45190149440"></a><a name="p45190149440"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16518141419446"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1552011474413"><a name="p1552011474413"></a><a name="p1552011474413"></a>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p2520914184418"><a name="p2520914184418"></a><a name="p2520914184418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p185206147441"><a name="p185206147441"></a><a name="p185206147441"></a>文件系统类型，请根据使用的存储类型填写：</p>
<a name="ul4520131494413"></a><a name="ul4520131494413"></a><ul id="ul4520131494413"><li>ext4 (EVS)</li><li>nfs (SFS)</li><li>obs (OBS)</li><li>efs (SFS Turbo)</li></ul>
</td>
</tr>
<tr id="row17518114154410"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p16521201464410"><a name="p16521201464410"></a><a name="p16521201464410"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p205211514174414"><a name="p205211514174414"></a><a name="p205211514174414"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p0521171424415"><a name="p0521171424415"></a><a name="p0521171424415"></a>云存储所在的region。</p>
</td>
</tr>
<tr id="row851811141446"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p5521314134413"><a name="p5521314134413"></a><a name="p5521314134413"></a>volumeID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p115221614184418"><a name="p115221614184418"></a><a name="p115221614184418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1052201494413"><a name="p1052201494413"></a><a name="p1052201494413"></a>云存储的UUID，如果是OBS-bucket则填入名称</p>
</td>
</tr>
<tr id="row175186140441"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p175221114144419"><a name="p175221114144419"></a><a name="p175221114144419"></a>storageType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p852221410449"><a name="p852221410449"></a><a name="p852221410449"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p4522101404418"><a name="p4522101404418"></a><a name="p4522101404418"></a>指定云存储的类型。</p>
<a name="ul185226145448"></a><a name="ul185226145448"></a><ul id="ul185226145448"><li>bs (EVS)</li><li>nfs (SFS)</li><li>obs (OBS)</li><li>efs (SFS Turbo)</li></ul>
</td>
</tr>
</tbody>
</table>

**表 8**  PersistentVolumeStatus

<a name="response_PersistentVolumeStatus"></a>
<table><thead align="left"><tr id="row9523171414442"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1652413148447"><a name="p1652413148447"></a><a name="p1652413148447"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p9524414204415"><a name="p9524414204415"></a><a name="p9524414204415"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p105241414144415"><a name="p105241414144415"></a><a name="p105241414144415"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row19523161414413"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p12524714204410"><a name="p12524714204410"></a><a name="p12524714204410"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1552531418448"><a name="p1552531418448"></a><a name="p1552531418448"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p195251714184418"><a name="p195251714184418"></a><a name="p195251714184418"></a>显示volume实际具有的访问模式。</p>
</td>
</tr>
<tr id="row1652310148445"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p19525214124418"><a name="p19525214124418"></a><a name="p19525214124418"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p55251148444"><a name="p55251148444"></a><a name="p55251148444"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p20525131474414"><a name="p20525131474414"></a><a name="p20525131474414"></a>PersistentVolume当前所处的状态，包括：</p>
<a name="ul15525201464412"></a><a name="ul15525201464412"></a><ul id="ul15525201464412"><li>Available（可用）：还是空闲资源，没有被任何PVC绑定</li><li>Bound（已绑定）：卷已经被PVC绑定</li><li>Released（已释放）：之前绑定的PVC被删除，但是资源还未被集群重新声明</li><li>Failed（失败）：该卷的自动回收失败</li></ul>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section2526151420443"></a>

无

## 响应示例<a name="section852717143449"></a>

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

## 状态码<a name="section781151584412"></a>

<a name="status_code"></a>
<table><thead align="left"><tr id="row195314142448"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p1081191514411"><a name="p1081191514411"></a><a name="p1081191514411"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p28191510441"><a name="p28191510441"></a><a name="p28191510441"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row553161444416"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p19813159443"><a name="p19813159443"></a><a name="p19813159443"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p138101504416"><a name="p138101504416"></a><a name="p138101504416"></a>删除指定PersistentVolume作业下发成功。</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section1581101574419"></a>

请参见[错误码](错误码.md)。

