# 删除ReplicationController<a name="cce_02_0017"></a>

## 功能介绍<a name="s5747c90803404cebac5522bd31bb3f8d"></a>

该API用于删除一个ReplicationController对象。

## URI<a name="s321f1aad41ae47c1a8068b0b4d75544b"></a>

DELETE /api/v1/namespaces/\{namespace\}/replicationcontrollers/\{name\}

[表1](#table20952959185814)  描述该API的参数。

**表 1**  参数描述

<a name="table20952959185814"></a>
<table><thead align="left"><tr id="row295335975813"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="p3953115995818"><a name="p3953115995818"></a><a name="p3953115995818"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24%" id="mcps1.2.4.1.2"><p id="p49531659185811"><a name="p49531659185811"></a><a name="p49531659185811"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="43%" id="mcps1.2.4.1.3"><p id="p695315592588"><a name="p695315592588"></a><a name="p695315592588"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row79531859165812"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p9953125995814"><a name="p9953125995814"></a><a name="p9953125995814"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="p895375995811"><a name="p895375995811"></a><a name="p895375995811"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615022_p18701191"><a name="zh-cn_topic_0079615022_p18701191"></a><a name="zh-cn_topic_0079615022_p18701191"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row1895313599588"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p1195311591582"><a name="p1195311591582"></a><a name="p1195311591582"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="p795335915582"><a name="p795335915582"></a><a name="p795335915582"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615022_p57038501"><a name="zh-cn_topic_0079615022_p57038501"></a><a name="zh-cn_topic_0079615022_p57038501"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row795318598584"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p2095355935819"><a name="p2095355935819"></a><a name="p2095355935819"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="p1795355975811"><a name="p1795355975811"></a><a name="p1795355975811"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615022_p14115254"><a name="zh-cn_topic_0079615022_p14115254"></a><a name="zh-cn_topic_0079615022_p14115254"></a>Name of the ReplicationController.</p>
</td>
</tr>
<tr id="row895315912582"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p16953155965810"><a name="p16953155965810"></a><a name="p16953155965810"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="p595325955813"><a name="p595325955813"></a><a name="p595325955813"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="a3888cf1469fe422a82b73359100852df"><a name="a3888cf1469fe422a82b73359100852df"></a><a name="a3888cf1469fe422a82b73359100852df"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="row159535593582"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p179531559165817"><a name="p179531559165817"></a><a name="p179531559165817"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="p13953135919583"><a name="p13953135919583"></a><a name="p13953135919583"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="p109531659155816"><a name="p109531659155816"></a><a name="p109531659155816"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="row13953175916584"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p1495335915583"><a name="p1495335915583"></a><a name="p1495335915583"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="p2954125912581"><a name="p2954125912581"></a><a name="p2954125912581"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="p1295435912582"><a name="p1295435912582"></a><a name="p1295435912582"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sfeeed7fc760b4675971307ccef72d6e8"></a>

**请求参数：**

请求参数[表2](#table155694255916)所示。

**表 2**  参数描述

<a name="table155694255916"></a>
<table><thead align="left"><tr id="row12571642185920"><th class="cellrowborder" valign="top" width="21.23787621237876%" id="mcps1.2.5.1.1"><p id="p7571242175915"><a name="p7571242175915"></a><a name="p7571242175915"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.2"><p id="p175714425594"><a name="p175714425594"></a><a name="p175714425594"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.3"><p id="p15784212593"><a name="p15784212593"></a><a name="p15784212593"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28607139286072%" id="mcps1.2.5.1.4"><p id="p85794215594"><a name="p85794215594"></a><a name="p85794215594"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1257442185920"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="p75764215597"><a name="p75764215597"></a><a name="p75764215597"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p135710421597"><a name="p135710421597"></a><a name="p135710421597"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="p657134225912"><a name="p657134225912"></a><a name="p657134225912"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615022_p36140984"><a name="zh-cn_topic_0079615022_p36140984"></a><a name="zh-cn_topic_0079615022_p36140984"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="p257144275920"><a name="p257144275920"></a><a name="p257144275920"></a>The value of this parameter is <strong id="b15675857202818"><a name="b15675857202818"></a><a name="b15675857202818"></a>DeleteOptions</strong>.</p>
</td>
</tr>
<tr id="row16570428591"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="p4571542125915"><a name="p4571542125915"></a><a name="p4571542125915"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p1357342195911"><a name="p1357342195911"></a><a name="p1357342195911"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="p1658124219592"><a name="p1658124219592"></a><a name="p1658124219592"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615022_p22051680"><a name="zh-cn_topic_0079615022_p22051680"></a><a name="zh-cn_topic_0079615022_p22051680"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="zh-cn_topic_0079615022_p64247400"><a name="zh-cn_topic_0079615022_p64247400"></a><a name="zh-cn_topic_0079615022_p64247400"></a>The value of this parameter is <strong id="zh-cn_topic_0079615022_b41355692"><a name="zh-cn_topic_0079615022_b41355692"></a><a name="zh-cn_topic_0079615022_b41355692"></a>v1</strong>.</p>
</td>
</tr>
<tr id="row1558184218594"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="p11581042165914"><a name="p11581042165914"></a><a name="p11581042165914"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p165824211592"><a name="p165824211592"></a><a name="p165824211592"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="p658104235920"><a name="p658104235920"></a><a name="p658104235920"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="p165820422593"><a name="p165820422593"></a><a name="p165820422593"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
<p id="zh-cn_topic_0079615022_p29715215"><a name="zh-cn_topic_0079615022_p29715215"></a><a name="zh-cn_topic_0079615022_p29715215"></a>Value range of this parameter: &gt; 0.</p>
</td>
</tr>
<tr id="row185854245914"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="p195844217595"><a name="p195844217595"></a><a name="p195844217595"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p1581442125916"><a name="p1581442125916"></a><a name="p1581442125916"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="p145812422596"><a name="p145812422596"></a><a name="p145812422596"></a><a href="#t3a8090faae4c480e8d828b60733ee26b">preconditions field</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="adde6361a8883447ea08809a3ab85df80"><a name="adde6361a8883447ea08809a3ab85df80"></a><a name="adde6361a8883447ea08809a3ab85df80"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="row4583426592"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="p8585421598"><a name="p8585421598"></a><a name="p8585421598"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p658174235914"><a name="p658174235914"></a><a name="p658174235914"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="p1658104255914"><a name="p1658104255914"></a><a name="p1658104255914"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="a460647973009439bbbc60961afb267b9"><a name="a460647973009439bbbc60961afb267b9"></a><a name="a460647973009439bbbc60961afb267b9"></a>Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object’s finalizers list.</p>
</td>
</tr>
<tr id="row1258104210596"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="p2058124295914"><a name="p2058124295914"></a><a name="p2058124295914"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p125854212596"><a name="p125854212596"></a><a name="p125854212596"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="p35874215913"><a name="p35874215913"></a><a name="p35874215913"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615022_p73081155274"><a name="zh-cn_topic_0079615022_p73081155274"></a><a name="zh-cn_topic_0079615022_p73081155274"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  preconditions field

<a name="t3a8090faae4c480e8d828b60733ee26b"></a>
<table><thead align="left"><tr id="r050d9d4e0ad24fefa38bad1731766a0b"><th class="cellrowborder" valign="top" width="21.23787621237876%" id="mcps1.2.5.1.1"><p id="a48de4193a53843b99c89be953cc16685"><a name="a48de4193a53843b99c89be953cc16685"></a><a name="a48de4193a53843b99c89be953cc16685"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.2"><p id="p1475941202627"><a name="p1475941202627"></a><a name="p1475941202627"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.3"><p id="p52442372202627"><a name="p52442372202627"></a><a name="p52442372202627"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28607139286072%" id="mcps1.2.5.1.4"><p id="p19973728202627"><a name="p19973728202627"></a><a name="p19973728202627"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rf0024bc1460b4b04ad4faca77becf865"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="ab992cf650bd64da5978b780151b7fdef"><a name="ab992cf650bd64da5978b780151b7fdef"></a><a name="ab992cf650bd64da5978b780151b7fdef"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="a5cf9652fc97b44098b8cf80794e90979"><a name="a5cf9652fc97b44098b8cf80794e90979"></a><a name="a5cf9652fc97b44098b8cf80794e90979"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="ad6ec4d630fb841209ee868a1081b67f9"><a name="ad6ec4d630fb841209ee868a1081b67f9"></a><a name="ad6ec4d630fb841209ee868a1081b67f9"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="af1d73e53e5f14faa8c1cd732d95bda76"><a name="af1d73e53e5f14faa8c1cd732d95bda76"></a><a name="af1d73e53e5f14faa8c1cd732d95bda76"></a>Specifies the target UID.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{ 
   "kind": "DeleteOptions", 
   "apiVersion": "v1", 
   "gracePeriodSeconds": 10 
 }
```

## 响应消息<a name="s4da39fa13fba4e569244d7d50b1e5008"></a>

**响应参数：**

响应参数的详细描述请参见[表2](删除Secret.md#table13766144711235)。

**响应示例：**

```
{ 
   "kind": "Status", 
   "apiVersion": "v1", 
   "metadata": {}, 
   "status": "Success", 
   "code": 200 
 }
```

## 状态码<a name="s346bdf8f56a948aa9de120782aa68e6f"></a>

[表4](#zh-cn_topic_0079615022_table8174376)描述API的状态码。

**表 4**  状态码

<a name="zh-cn_topic_0079615022_table8174376"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615022_row33408077"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p49527675202627"><a name="p49527675202627"></a><a name="p49527675202627"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p52318773202627"><a name="p52318773202627"></a><a name="p52318773202627"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615022_row34146301"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615022_p14387025"><a name="zh-cn_topic_0079615022_p14387025"></a><a name="zh-cn_topic_0079615022_p14387025"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615022_p24498377"><a name="zh-cn_topic_0079615022_p24498377"></a><a name="zh-cn_topic_0079615022_p24498377"></a>Delete a ReplicationController resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

