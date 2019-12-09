# 删除Endpoints<a name="cce_02_0060"></a>

## 功能介绍<a name="s9a3aa9bd9aad49c9b61dc5701d11cc2f"></a>

该API用于删除一个Endpoints资源对象。

## URI<a name="s2360b8e77c4b43f98f1f30e4ff049deb"></a>

DELETE /api/v1/namespaces/\{namespace\}/endpoints/\{name\}

[表1](#zh-cn_topic_0079614926_table40569470)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614926_table40569470"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614926_row37024442"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614926_p46189825"><a name="zh-cn_topic_0079614926_p46189825"></a><a name="zh-cn_topic_0079614926_p46189825"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="22%" id="mcps1.2.4.1.2"><p id="p4707248621524"><a name="p4707248621524"></a><a name="p4707248621524"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p5477502721524"><a name="p5477502721524"></a><a name="p5477502721524"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614926_row19613673"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614926_p45203650"><a name="zh-cn_topic_0079614926_p45203650"></a><a name="zh-cn_topic_0079614926_p45203650"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614926_p37616995"><a name="zh-cn_topic_0079614926_p37616995"></a><a name="zh-cn_topic_0079614926_p37616995"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614926_p27077749"><a name="zh-cn_topic_0079614926_p27077749"></a><a name="zh-cn_topic_0079614926_p27077749"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614926_row31939521"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614926_p36964446"><a name="zh-cn_topic_0079614926_p36964446"></a><a name="zh-cn_topic_0079614926_p36964446"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614926_p41330139"><a name="zh-cn_topic_0079614926_p41330139"></a><a name="zh-cn_topic_0079614926_p41330139"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614926_p59406944"><a name="zh-cn_topic_0079614926_p59406944"></a><a name="zh-cn_topic_0079614926_p59406944"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614926_row64900454"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614926_p22445387"><a name="zh-cn_topic_0079614926_p22445387"></a><a name="zh-cn_topic_0079614926_p22445387"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614926_p6137036"><a name="zh-cn_topic_0079614926_p6137036"></a><a name="zh-cn_topic_0079614926_p6137036"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614926_p27337939"><a name="zh-cn_topic_0079614926_p27337939"></a><a name="zh-cn_topic_0079614926_p27337939"></a>Name of the Endpoints.</p>
</td>
</tr>
<tr id="r639a608941774508a55b6db2b8331c21"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a84a288d469bd417fb27ef523a03f414d"><a name="a84a288d469bd417fb27ef523a03f414d"></a><a name="a84a288d469bd417fb27ef523a03f414d"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="adfebfd028e054cfea37b104f27e594a3"><a name="adfebfd028e054cfea37b104f27e594a3"></a><a name="adfebfd028e054cfea37b104f27e594a3"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="a261cd589c0bb48b280abfbd511a51803"><a name="a261cd589c0bb48b280abfbd511a51803"></a><a name="a261cd589c0bb48b280abfbd511a51803"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="ref12f7f4002f48d3bdafa6b02e00fe65"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614926_p541773543919"><a name="zh-cn_topic_0079614926_p541773543919"></a><a name="zh-cn_topic_0079614926_p541773543919"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614926_p541719358399"><a name="zh-cn_topic_0079614926_p541719358399"></a><a name="zh-cn_topic_0079614926_p541719358399"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614926_p94174358394"><a name="zh-cn_topic_0079614926_p94174358394"></a><a name="zh-cn_topic_0079614926_p94174358394"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="r812b5a4bc04e413bb09546d41677b6f5"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a625b3a9d88f34dd1a6fe6f7170769234"><a name="a625b3a9d88f34dd1a6fe6f7170769234"></a><a name="a625b3a9d88f34dd1a6fe6f7170769234"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="a799e593c430f4929bf427344205d2335"><a name="a799e593c430f4929bf427344205d2335"></a><a name="a799e593c430f4929bf427344205d2335"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="af07b1aa7106141bebac3464b69f87773"><a name="af07b1aa7106141bebac3464b69f87773"></a><a name="af07b1aa7106141bebac3464b69f87773"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s10b67f4a83f84a8fbaabcbf839788a90"></a>

**请求参数**：

请求参数如[表2](#zh-cn_topic_0079614926_table29580916)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079614926_table29580916"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614926_row46987420"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614926_p47884646"><a name="zh-cn_topic_0079614926_p47884646"></a><a name="zh-cn_topic_0079614926_p47884646"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.18%" id="mcps1.2.5.1.2"><p id="p832688021524"><a name="p832688021524"></a><a name="p832688021524"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.11%" id="mcps1.2.5.1.3"><p id="p338864621524"><a name="p338864621524"></a><a name="p338864621524"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="38.91%" id="mcps1.2.5.1.4"><p id="p604490921524"><a name="p604490921524"></a><a name="p604490921524"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614926_row65253851"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614926_p51070612"><a name="zh-cn_topic_0079614926_p51070612"></a><a name="zh-cn_topic_0079614926_p51070612"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614926_p43078913"><a name="zh-cn_topic_0079614926_p43078913"></a><a name="zh-cn_topic_0079614926_p43078913"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.11%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614926_p66839947"><a name="zh-cn_topic_0079614926_p66839947"></a><a name="zh-cn_topic_0079614926_p66839947"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="38.91%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614926_p45326617"><a name="zh-cn_topic_0079614926_p45326617"></a><a name="zh-cn_topic_0079614926_p45326617"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="zh-cn_topic_0079614926_p5286373"><a name="zh-cn_topic_0079614926_p5286373"></a><a name="zh-cn_topic_0079614926_p5286373"></a>The value of this parameter is <strong id="b15675857202818"><a name="b15675857202818"></a><a name="b15675857202818"></a>DeleteOptions</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614926_row25543093"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614926_p55724670"><a name="zh-cn_topic_0079614926_p55724670"></a><a name="zh-cn_topic_0079614926_p55724670"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614926_p17404391"><a name="zh-cn_topic_0079614926_p17404391"></a><a name="zh-cn_topic_0079614926_p17404391"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.11%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614926_p469528"><a name="zh-cn_topic_0079614926_p469528"></a><a name="zh-cn_topic_0079614926_p469528"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="38.91%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614926_p38031802"><a name="zh-cn_topic_0079614926_p38031802"></a><a name="zh-cn_topic_0079614926_p38031802"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="zh-cn_topic_0079614926_p6741900"><a name="zh-cn_topic_0079614926_p6741900"></a><a name="zh-cn_topic_0079614926_p6741900"></a>The value of this parameter is <strong id="zh-cn_topic_0079614926_b60677108"><a name="zh-cn_topic_0079614926_b60677108"></a><a name="zh-cn_topic_0079614926_b60677108"></a>v1</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614926_row9223066"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614926_p8870892"><a name="zh-cn_topic_0079614926_p8870892"></a><a name="zh-cn_topic_0079614926_p8870892"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614926_p47453675"><a name="zh-cn_topic_0079614926_p47453675"></a><a name="zh-cn_topic_0079614926_p47453675"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.11%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614926_p18542462"><a name="zh-cn_topic_0079614926_p18542462"></a><a name="zh-cn_topic_0079614926_p18542462"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="38.91%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614926_p25544462"><a name="zh-cn_topic_0079614926_p25544462"></a><a name="zh-cn_topic_0079614926_p25544462"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
<p id="zh-cn_topic_0079614926_p28573568"><a name="zh-cn_topic_0079614926_p28573568"></a><a name="zh-cn_topic_0079614926_p28573568"></a>Value range of this parameter: &gt; 0.</p>
</td>
</tr>
<tr id="r8a1225bc41124a8f98e8a320debc7879"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a823a2d1ebb8741d3b3e10d39d98c4cce"><a name="a823a2d1ebb8741d3b3e10d39d98c4cce"></a><a name="a823a2d1ebb8741d3b3e10d39d98c4cce"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="a731b9e14f05f4db2b990752d652768d2"><a name="a731b9e14f05f4db2b990752d652768d2"></a><a name="a731b9e14f05f4db2b990752d652768d2"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.11%" headers="mcps1.2.5.1.3 "><p id="a247917470c204a50bc8b6d913c118959"><a name="a247917470c204a50bc8b6d913c118959"></a><a name="a247917470c204a50bc8b6d913c118959"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="38.91%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614926_p948943013401"><a name="zh-cn_topic_0079614926_p948943013401"></a><a name="zh-cn_topic_0079614926_p948943013401"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
<tr id="r9ddecd24c9f14203a6786dce4073f1fd"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a023c9806046f4668b0cda11709c089af"><a name="a023c9806046f4668b0cda11709c089af"></a><a name="a023c9806046f4668b0cda11709c089af"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="af73d5beb343c4017b1ec86b74c2f1f61"><a name="af73d5beb343c4017b1ec86b74c2f1f61"></a><a name="af73d5beb343c4017b1ec86b74c2f1f61"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.11%" headers="mcps1.2.5.1.3 "><p id="a68b7d1fcf9b248b690d47a5eaf5a0df7"><a name="a68b7d1fcf9b248b690d47a5eaf5a0df7"></a><a name="a68b7d1fcf9b248b690d47a5eaf5a0df7"></a><a href="#td963eecea01d406f99bfcb0ca63e8c82">preconditions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="38.91%" headers="mcps1.2.5.1.4 "><p id="ac72ee0a8d8434bd1b9382129b472a7dd"><a name="ac72ee0a8d8434bd1b9382129b472a7dd"></a><a name="ac72ee0a8d8434bd1b9382129b472a7dd"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="r9d4a453fffa94558a25a99954ad14b7c"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a1150a80acadb48d382dd4c7eb36dab90"><a name="a1150a80acadb48d382dd4c7eb36dab90"></a><a name="a1150a80acadb48d382dd4c7eb36dab90"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="a08fcefa675d54c52b07cc8e36026a91f"><a name="a08fcefa675d54c52b07cc8e36026a91f"></a><a name="a08fcefa675d54c52b07cc8e36026a91f"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.11%" headers="mcps1.2.5.1.3 "><p id="a402858e2a6804852a50b56743448de18"><a name="a402858e2a6804852a50b56743448de18"></a><a name="a402858e2a6804852a50b56743448de18"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="38.91%" headers="mcps1.2.5.1.4 "><p id="a7d8232545e2f437193459eae125a67e6"><a name="a7d8232545e2f437193459eae125a67e6"></a><a name="a7d8232545e2f437193459eae125a67e6"></a>Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  preconditions字段数据结构说明

<a name="td963eecea01d406f99bfcb0ca63e8c82"></a>
<table><thead align="left"><tr id="raa8614674ee544d9b6b5b35eae3c803a"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="a57793d5e0d6841f2ae89c0d74abc6dbc"><a name="a57793d5e0d6841f2ae89c0d74abc6dbc"></a><a name="a57793d5e0d6841f2ae89c0d74abc6dbc"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p2967165521524"><a name="p2967165521524"></a><a name="p2967165521524"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p5459388021524"><a name="p5459388021524"></a><a name="p5459388021524"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p6002819821524"><a name="p6002819821524"></a><a name="p6002819821524"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="re967a05bf902485480ca36a29262915e"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a55dc97ddc79d455ea753c811f3252473"><a name="a55dc97ddc79d455ea753c811f3252473"></a><a name="a55dc97ddc79d455ea753c811f3252473"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a2964f66ffe55445c81669b72ca80ea4f"><a name="a2964f66ffe55445c81669b72ca80ea4f"></a><a name="a2964f66ffe55445c81669b72ca80ea4f"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="afd11f896b6684b72976391abbf92db01"><a name="afd11f896b6684b72976391abbf92db01"></a><a name="afd11f896b6684b72976391abbf92db01"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a38457e838f0d42a5a1458e7bb9a86630"><a name="a38457e838f0d42a5a1458e7bb9a86630"></a><a name="a38457e838f0d42a5a1458e7bb9a86630"></a>Specifies the target UID.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{ 
   "kind": "DeleteOptions", 
   "apiVersion": "string", 
   "gracePeriodSeconds": 0 
 }
```

## 响应消息<a name="s8a97375c1e72438db25bc76f0d168b7c"></a>

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

## 状态码<a name="s28a95a5ebd724c6f9be910b49981bbf7"></a>

[表4](#zh-cn_topic_0079614926_table64901660)描述API的状态码。

**表 4**  状态码

<a name="zh-cn_topic_0079614926_table64901660"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614926_row46570941"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p2857733721524"><a name="p2857733721524"></a><a name="p2857733721524"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p3306296521524"><a name="p3306296521524"></a><a name="p3306296521524"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614926_row25979390"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614926_p23955812"><a name="zh-cn_topic_0079614926_p23955812"></a><a name="zh-cn_topic_0079614926_p23955812"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614926_p61372619"><a name="zh-cn_topic_0079614926_p61372619"></a><a name="zh-cn_topic_0079614926_p61372619"></a>Delete an Endpoint resource objectre successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

