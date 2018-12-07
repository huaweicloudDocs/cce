# 删除ReplicationController<a name="cce_02_0017"></a>

## 功能介绍<a name="s5747c90803404cebac5522bd31bb3f8d"></a>

该API用于删除一个ReplicationController对象。

## URI<a name="s321f1aad41ae47c1a8068b0b4d75544b"></a>

DELETE /api/v1/namespaces/\{namespace\}/replicationcontrollers/\{name\}

[表1](#zh-cn_topic_0079615022_table33241097)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615022_table33241097"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615022_row30792978"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615022_p11203266"><a name="zh-cn_topic_0079615022_p11203266"></a><a name="zh-cn_topic_0079615022_p11203266"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24%" id="mcps1.2.4.1.2"><p id="p9012723202627"><a name="p9012723202627"></a><a name="p9012723202627"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="43%" id="mcps1.2.4.1.3"><p id="p58941999202627"><a name="p58941999202627"></a><a name="p58941999202627"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615022_row43905974"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615022_p66723033"><a name="zh-cn_topic_0079615022_p66723033"></a><a name="zh-cn_topic_0079615022_p66723033"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615022_p35856572"><a name="zh-cn_topic_0079615022_p35856572"></a><a name="zh-cn_topic_0079615022_p35856572"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615022_p18701191"><a name="zh-cn_topic_0079615022_p18701191"></a><a name="zh-cn_topic_0079615022_p18701191"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615022_row61545578"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615022_p19135896"><a name="zh-cn_topic_0079615022_p19135896"></a><a name="zh-cn_topic_0079615022_p19135896"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615022_p6503710"><a name="zh-cn_topic_0079615022_p6503710"></a><a name="zh-cn_topic_0079615022_p6503710"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615022_p57038501"><a name="zh-cn_topic_0079615022_p57038501"></a><a name="zh-cn_topic_0079615022_p57038501"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615022_row43584464"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615022_p40680699"><a name="zh-cn_topic_0079615022_p40680699"></a><a name="zh-cn_topic_0079615022_p40680699"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615022_p6802298"><a name="zh-cn_topic_0079615022_p6802298"></a><a name="zh-cn_topic_0079615022_p6802298"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615022_p14115254"><a name="zh-cn_topic_0079615022_p14115254"></a><a name="zh-cn_topic_0079615022_p14115254"></a>Name of the ReplicationController.</p>
</td>
</tr>
<tr id="r8b29b3b239eb400f83ccef6a61165277"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615022_p79721228245"><a name="zh-cn_topic_0079615022_p79721228245"></a><a name="zh-cn_topic_0079615022_p79721228245"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="a8dfb1d35e80f4a6187c5114b0aba8f3a"><a name="a8dfb1d35e80f4a6187c5114b0aba8f3a"></a><a name="a8dfb1d35e80f4a6187c5114b0aba8f3a"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="a3888cf1469fe422a82b73359100852df"><a name="a3888cf1469fe422a82b73359100852df"></a><a name="a3888cf1469fe422a82b73359100852df"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="r794e8ce80a4e417b8e40536c6c1e4acd"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615022_p431816409248"><a name="zh-cn_topic_0079615022_p431816409248"></a><a name="zh-cn_topic_0079615022_p431816409248"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="aa3bfc37083f145c6805eece45694b24e"><a name="aa3bfc37083f145c6805eece45694b24e"></a><a name="aa3bfc37083f145c6805eece45694b24e"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="a50711542a8084997a27a5bc58aba7434"><a name="a50711542a8084997a27a5bc58aba7434"></a><a name="a50711542a8084997a27a5bc58aba7434"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="rf3b9e4c9947e4bada04136b8e630fe42"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a1b08c853484943eb964954083aa19e02"><a name="a1b08c853484943eb964954083aa19e02"></a><a name="a1b08c853484943eb964954083aa19e02"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="a5cae07739953470386addabe6deee858"><a name="a5cae07739953470386addabe6deee858"></a><a name="a5cae07739953470386addabe6deee858"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="ae2c50bbee2be48138a3a09de3925f667"><a name="ae2c50bbee2be48138a3a09de3925f667"></a><a name="ae2c50bbee2be48138a3a09de3925f667"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sfeeed7fc760b4675971307ccef72d6e8"></a>

**请求参数：**

请求参数[表2](#zh-cn_topic_0079615022_table30734425)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079615022_table30734425"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615022_row32559554"><th class="cellrowborder" valign="top" width="21.23787621237876%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615022_p20078207"><a name="zh-cn_topic_0079615022_p20078207"></a><a name="zh-cn_topic_0079615022_p20078207"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.2"><p id="p31061528202627"><a name="p31061528202627"></a><a name="p31061528202627"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.3"><p id="p32955836202627"><a name="p32955836202627"></a><a name="p32955836202627"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28607139286072%" id="mcps1.2.5.1.4"><p id="p52177089202627"><a name="p52177089202627"></a><a name="p52177089202627"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615022_row21391575"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615022_p54996047"><a name="zh-cn_topic_0079615022_p54996047"></a><a name="zh-cn_topic_0079615022_p54996047"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615022_p25494807"><a name="zh-cn_topic_0079615022_p25494807"></a><a name="zh-cn_topic_0079615022_p25494807"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615022_p51813463"><a name="zh-cn_topic_0079615022_p51813463"></a><a name="zh-cn_topic_0079615022_p51813463"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615022_p36140984"><a name="zh-cn_topic_0079615022_p36140984"></a><a name="zh-cn_topic_0079615022_p36140984"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="zh-cn_topic_0079615022_p56833404"><a name="zh-cn_topic_0079615022_p56833404"></a><a name="zh-cn_topic_0079615022_p56833404"></a>The value of this parameter is <strong id="b15675857202818"><a name="b15675857202818"></a><a name="b15675857202818"></a>DeleteOptions</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615022_row40103025"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615022_p27119578"><a name="zh-cn_topic_0079615022_p27119578"></a><a name="zh-cn_topic_0079615022_p27119578"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615022_p49202208"><a name="zh-cn_topic_0079615022_p49202208"></a><a name="zh-cn_topic_0079615022_p49202208"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615022_p25955882"><a name="zh-cn_topic_0079615022_p25955882"></a><a name="zh-cn_topic_0079615022_p25955882"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615022_p22051680"><a name="zh-cn_topic_0079615022_p22051680"></a><a name="zh-cn_topic_0079615022_p22051680"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="zh-cn_topic_0079615022_p64247400"><a name="zh-cn_topic_0079615022_p64247400"></a><a name="zh-cn_topic_0079615022_p64247400"></a>The value of this parameter is <strong id="zh-cn_topic_0079615022_b41355692"><a name="zh-cn_topic_0079615022_b41355692"></a><a name="zh-cn_topic_0079615022_b41355692"></a>v1</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615022_row36656908"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615022_p16419601"><a name="zh-cn_topic_0079615022_p16419601"></a><a name="zh-cn_topic_0079615022_p16419601"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615022_p54919327"><a name="zh-cn_topic_0079615022_p54919327"></a><a name="zh-cn_topic_0079615022_p54919327"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615022_p19280477"><a name="zh-cn_topic_0079615022_p19280477"></a><a name="zh-cn_topic_0079615022_p19280477"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615022_p18214771"><a name="zh-cn_topic_0079615022_p18214771"></a><a name="zh-cn_topic_0079615022_p18214771"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
<p id="zh-cn_topic_0079615022_p29715215"><a name="zh-cn_topic_0079615022_p29715215"></a><a name="zh-cn_topic_0079615022_p29715215"></a>Value range of this parameter: &gt; 0.</p>
</td>
</tr>
<tr id="r6b97a7c8cc7d4409bd1531959bf711b7"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="acc6d9b41f92341aaba4c9a4800898eaa"><a name="acc6d9b41f92341aaba4c9a4800898eaa"></a><a name="acc6d9b41f92341aaba4c9a4800898eaa"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="a313ae3fe00b64d3bbc74295e2d7a5ffb"><a name="a313ae3fe00b64d3bbc74295e2d7a5ffb"></a><a name="a313ae3fe00b64d3bbc74295e2d7a5ffb"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="a96cbbc3d348e40c9900233b931ab0f1c"><a name="a96cbbc3d348e40c9900233b931ab0f1c"></a><a name="a96cbbc3d348e40c9900233b931ab0f1c"></a><a href="#cce_02_0017__t3a8090faae4c480e8d828b60733ee26b">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="adde6361a8883447ea08809a3ab85df80"><a name="adde6361a8883447ea08809a3ab85df80"></a><a name="adde6361a8883447ea08809a3ab85df80"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="r188da27370d84052bd717ac5365469b0"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="a8bcb3526e1454925897b739853b69b34"><a name="a8bcb3526e1454925897b739853b69b34"></a><a name="a8bcb3526e1454925897b739853b69b34"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="a61b04cc068bf484ebf341ffdbce552a3"><a name="a61b04cc068bf484ebf341ffdbce552a3"></a><a name="a61b04cc068bf484ebf341ffdbce552a3"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="a08e4a2c5b9124fee8bfa832905ef0601"><a name="a08e4a2c5b9124fee8bfa832905ef0601"></a><a name="a08e4a2c5b9124fee8bfa832905ef0601"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="a460647973009439bbbc60961afb267b9"><a name="a460647973009439bbbc60961afb267b9"></a><a name="a460647973009439bbbc60961afb267b9"></a>Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object’s finalizers list.</p>
</td>
</tr>
<tr id="r6293b24122974f26b4ce44e16ca58bef"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615022_p73089511270"><a name="zh-cn_topic_0079615022_p73089511270"></a><a name="zh-cn_topic_0079615022_p73089511270"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615022_p43083542713"><a name="zh-cn_topic_0079615022_p43083542713"></a><a name="zh-cn_topic_0079615022_p43083542713"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="a9fca4a7920c648a5aee5a0c6d5968933"><a name="a9fca4a7920c648a5aee5a0c6d5968933"></a><a name="a9fca4a7920c648a5aee5a0c6d5968933"></a>String</p>
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
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.3"><p id="p52442372202627"><a name="p52442372202627"></a><a name="p52442372202627"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28607139286072%" id="mcps1.2.5.1.4"><p id="p19973728202627"><a name="p19973728202627"></a><a name="p19973728202627"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rf0024bc1460b4b04ad4faca77becf865"><td class="cellrowborder" valign="top" width="21.23787621237876%" headers="mcps1.2.5.1.1 "><p id="ab992cf650bd64da5978b780151b7fdef"><a name="ab992cf650bd64da5978b780151b7fdef"></a><a name="ab992cf650bd64da5978b780151b7fdef"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="a5cf9652fc97b44098b8cf80794e90979"><a name="a5cf9652fc97b44098b8cf80794e90979"></a><a name="a5cf9652fc97b44098b8cf80794e90979"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="ad6ec4d630fb841209ee868a1081b67f9"><a name="ad6ec4d630fb841209ee868a1081b67f9"></a><a name="ad6ec4d630fb841209ee868a1081b67f9"></a>types.UID</p>
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

响应参数的详细描述请参见[表4](删除Secret.md#zh-cn_topic_0079615047_table30941925)。

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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615022_p24498377"><a name="zh-cn_topic_0079615022_p24498377"></a><a name="zh-cn_topic_0079615022_p24498377"></a>Delete a ReplicationController resource objectre successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

