# 删除Pod<a name="cce_02_0035"></a>

## 功能介绍<a name="s741ec6c50c454471bb3292d7950b0098"></a>

该API用于删除指定Namespace下的某个Pod对象。

## URI<a name="s7d7ef3af438c482abce017b9cb2ad884"></a>

DELETE /api/v1/namespaces/\{namespace\}/pods/\{name\}

[表1](#zh-cn_topic_0079615056_table52824818)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615056_table52824818"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615056_row59343410"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615056_p42086942"><a name="zh-cn_topic_0079615056_p42086942"></a><a name="zh-cn_topic_0079615056_p42086942"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="22%" id="mcps1.2.4.1.2"><p id="p6618481203046"><a name="p6618481203046"></a><a name="p6618481203046"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p66334913203046"><a name="p66334913203046"></a><a name="p66334913203046"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615056_row13311722"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615056_p4507703"><a name="zh-cn_topic_0079615056_p4507703"></a><a name="zh-cn_topic_0079615056_p4507703"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615056_p29579681"><a name="zh-cn_topic_0079615056_p29579681"></a><a name="zh-cn_topic_0079615056_p29579681"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615056_p47143951"><a name="zh-cn_topic_0079615056_p47143951"></a><a name="zh-cn_topic_0079615056_p47143951"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615056_row12923797"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615056_p40194609"><a name="zh-cn_topic_0079615056_p40194609"></a><a name="zh-cn_topic_0079615056_p40194609"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615056_p34537922"><a name="zh-cn_topic_0079615056_p34537922"></a><a name="zh-cn_topic_0079615056_p34537922"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615056_p46108336"><a name="zh-cn_topic_0079615056_p46108336"></a><a name="zh-cn_topic_0079615056_p46108336"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615056_row12321845"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615056_p58545401"><a name="zh-cn_topic_0079615056_p58545401"></a><a name="zh-cn_topic_0079615056_p58545401"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615056_p44557004"><a name="zh-cn_topic_0079615056_p44557004"></a><a name="zh-cn_topic_0079615056_p44557004"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615056_p52347609"><a name="zh-cn_topic_0079615056_p52347609"></a><a name="zh-cn_topic_0079615056_p52347609"></a>Name of the Pod.</p>
</td>
</tr>
<tr id="rf0174cc788d1406791ebac9b6df8acd6"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a9c85576f378c4573b485d43745475398"><a name="a9c85576f378c4573b485d43745475398"></a><a name="a9c85576f378c4573b485d43745475398"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615056_p777074816124"><a name="zh-cn_topic_0079615056_p777074816124"></a><a name="zh-cn_topic_0079615056_p777074816124"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="a1843ce09947646f88cd95ea3763333df"><a name="a1843ce09947646f88cd95ea3763333df"></a><a name="a1843ce09947646f88cd95ea3763333df"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="rb1ed5b6bf60f472cb3ebfd7cf2da6608"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a39b66f9d415342329a82762fdbf8b74f"><a name="a39b66f9d415342329a82762fdbf8b74f"></a><a name="a39b66f9d415342329a82762fdbf8b74f"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="aa77cf8a04e5241ce98460b55c28a32c4"><a name="aa77cf8a04e5241ce98460b55c28a32c4"></a><a name="aa77cf8a04e5241ce98460b55c28a32c4"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="aac08fb72b4494c9fab0ef0063ef57cd4"><a name="aac08fb72b4494c9fab0ef0063ef57cd4"></a><a name="aac08fb72b4494c9fab0ef0063ef57cd4"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="read1142efb9a4dfc9b8b9a886405f90f"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615056_p549795241210"><a name="zh-cn_topic_0079615056_p549795241210"></a><a name="zh-cn_topic_0079615056_p549795241210"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="a1a32896b6e3f4d75855c467213f67b58"><a name="a1a32896b6e3f4d75855c467213f67b58"></a><a name="a1a32896b6e3f4d75855c467213f67b58"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615056_p174970527122"><a name="zh-cn_topic_0079615056_p174970527122"></a><a name="zh-cn_topic_0079615056_p174970527122"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s60dd10d6b3e449f19dba8169c1fe4661"></a>

**请求参数：**

请求参数如[表2](#zh-cn_topic_0079615056_table5661318)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079615056_table5661318"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615056_row48534398"><th class="cellrowborder" valign="top" width="21.42785721427857%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615056_p38972142"><a name="zh-cn_topic_0079615056_p38972142"></a><a name="zh-cn_topic_0079615056_p38972142"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.548045195480455%" id="mcps1.2.5.1.2"><p id="p30994462203046"><a name="p30994462203046"></a><a name="p30994462203046"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.3"><p id="p27523455203046"><a name="p27523455203046"></a><a name="p27523455203046"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28607139286072%" id="mcps1.2.5.1.4"><p id="p14807377203046"><a name="p14807377203046"></a><a name="p14807377203046"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615056_row66900997"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615056_p50271656"><a name="zh-cn_topic_0079615056_p50271656"></a><a name="zh-cn_topic_0079615056_p50271656"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.548045195480455%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615056_p45472307"><a name="zh-cn_topic_0079615056_p45472307"></a><a name="zh-cn_topic_0079615056_p45472307"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615056_p59378255"><a name="zh-cn_topic_0079615056_p59378255"></a><a name="zh-cn_topic_0079615056_p59378255"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615056_p44909347"><a name="zh-cn_topic_0079615056_p44909347"></a><a name="zh-cn_topic_0079615056_p44909347"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="zh-cn_topic_0079615056_p1530946"><a name="zh-cn_topic_0079615056_p1530946"></a><a name="zh-cn_topic_0079615056_p1530946"></a>The value of this parameter is <strong id="b15675857202818"><a name="b15675857202818"></a><a name="b15675857202818"></a>DeleteOptions</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615056_row56897822"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615056_p45320903"><a name="zh-cn_topic_0079615056_p45320903"></a><a name="zh-cn_topic_0079615056_p45320903"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.548045195480455%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615056_p47114532"><a name="zh-cn_topic_0079615056_p47114532"></a><a name="zh-cn_topic_0079615056_p47114532"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615056_p58180766"><a name="zh-cn_topic_0079615056_p58180766"></a><a name="zh-cn_topic_0079615056_p58180766"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615056_p15021596"><a name="zh-cn_topic_0079615056_p15021596"></a><a name="zh-cn_topic_0079615056_p15021596"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="zh-cn_topic_0079615056_p976640"><a name="zh-cn_topic_0079615056_p976640"></a><a name="zh-cn_topic_0079615056_p976640"></a>The value of this parameter is <strong id="zh-cn_topic_0079615056_b8789767"><a name="zh-cn_topic_0079615056_b8789767"></a><a name="zh-cn_topic_0079615056_b8789767"></a>v1</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615056_row11999040"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615056_p32398201"><a name="zh-cn_topic_0079615056_p32398201"></a><a name="zh-cn_topic_0079615056_p32398201"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.548045195480455%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615056_p7008594"><a name="zh-cn_topic_0079615056_p7008594"></a><a name="zh-cn_topic_0079615056_p7008594"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615056_p30825203"><a name="zh-cn_topic_0079615056_p30825203"></a><a name="zh-cn_topic_0079615056_p30825203"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615056_p13813509"><a name="zh-cn_topic_0079615056_p13813509"></a><a name="zh-cn_topic_0079615056_p13813509"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
<p id="zh-cn_topic_0079615056_p57212719"><a name="zh-cn_topic_0079615056_p57212719"></a><a name="zh-cn_topic_0079615056_p57212719"></a>Value range of this parameter: &gt; 0.</p>
</td>
</tr>
<tr id="rc0e8a381ea0949378733eaaadae917a3"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="abfe8f196190c4d459b298b39fce2f46b"><a name="abfe8f196190c4d459b298b39fce2f46b"></a><a name="abfe8f196190c4d459b298b39fce2f46b"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.548045195480455%" headers="mcps1.2.5.1.2 "><p id="a38ccfeab36664ea9a4721c54895bf3d0"><a name="a38ccfeab36664ea9a4721c54895bf3d0"></a><a name="a38ccfeab36664ea9a4721c54895bf3d0"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="a6c2825385ff64f5185b992b264a53265"><a name="a6c2825385ff64f5185b992b264a53265"></a><a name="a6c2825385ff64f5185b992b264a53265"></a><a href="#cce_02_0035__te7bcdc459ad245a4b6c9a5be1cfbc24f">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="a72d2875166ad476b8c4f9f40113297d8"><a name="a72d2875166ad476b8c4f9f40113297d8"></a><a name="a72d2875166ad476b8c4f9f40113297d8"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="rec20949a394845cc9d503aa763550437"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="aea42ed0480f74d96a10d101e003f6a9b"><a name="aea42ed0480f74d96a10d101e003f6a9b"></a><a name="aea42ed0480f74d96a10d101e003f6a9b"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.548045195480455%" headers="mcps1.2.5.1.2 "><p id="aa09bcb5543994a59a234061d4ff15324"><a name="aa09bcb5543994a59a234061d4ff15324"></a><a name="aa09bcb5543994a59a234061d4ff15324"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="a00fe296143e94eb2847e0c2cd18d4c9b"><a name="a00fe296143e94eb2847e0c2cd18d4c9b"></a><a name="a00fe296143e94eb2847e0c2cd18d4c9b"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="a2c3ffcbe23c540b3a778b6fd2bf0f61f"><a name="a2c3ffcbe23c540b3a778b6fd2bf0f61f"></a><a name="a2c3ffcbe23c540b3a778b6fd2bf0f61f"></a>Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list.</p>
</td>
</tr>
<tr id="r3b5776abebb04fa0af5ffa60c6c6c926"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="a260af5d37c804884b2fe77a654c482b9"><a name="a260af5d37c804884b2fe77a654c482b9"></a><a name="a260af5d37c804884b2fe77a654c482b9"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="19.548045195480455%" headers="mcps1.2.5.1.2 "><p id="a29554b124a664417b5c6f29fd6c3b83c"><a name="a29554b124a664417b5c6f29fd6c3b83c"></a><a name="a29554b124a664417b5c6f29fd6c3b83c"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="a4241077a915f4723b4c0596120f64d3d"><a name="a4241077a915f4723b4c0596120f64d3d"></a><a name="a4241077a915f4723b4c0596120f64d3d"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615056_p854231911149"><a name="zh-cn_topic_0079615056_p854231911149"></a><a name="zh-cn_topic_0079615056_p854231911149"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  preconditions字段数据结构说明

<a name="te7bcdc459ad245a4b6c9a5be1cfbc24f"></a>
<table><thead align="left"><tr id="r47fbe453ffeb4bb58232916e90c75848"><th class="cellrowborder" valign="top" width="21.42785721427857%" id="mcps1.2.5.1.1"><p id="aa13dcb4f36d043c8817f61cb2af81a5d"><a name="aa13dcb4f36d043c8817f61cb2af81a5d"></a><a name="aa13dcb4f36d043c8817f61cb2af81a5d"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.548045195480455%" id="mcps1.2.5.1.2"><p id="p53426314203046"><a name="p53426314203046"></a><a name="p53426314203046"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.3"><p id="p32564158203046"><a name="p32564158203046"></a><a name="p32564158203046"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28607139286072%" id="mcps1.2.5.1.4"><p id="p20451135203046"><a name="p20451135203046"></a><a name="p20451135203046"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rabd2228d64044966a0327e0564968c2e"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="a7665ba863b83480ba82d980c3b6c4170"><a name="a7665ba863b83480ba82d980c3b6c4170"></a><a name="a7665ba863b83480ba82d980c3b6c4170"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.548045195480455%" headers="mcps1.2.5.1.2 "><p id="a607f700011a9424b994100759d5f31fb"><a name="a607f700011a9424b994100759d5f31fb"></a><a name="a607f700011a9424b994100759d5f31fb"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.3 "><p id="a40fd1d52f6394b74b93e0d31bc9d8c0d"><a name="a40fd1d52f6394b74b93e0d31bc9d8c0d"></a><a name="a40fd1d52f6394b74b93e0d31bc9d8c0d"></a>types.UID</p>
</td>
<td class="cellrowborder" valign="top" width="39.28607139286072%" headers="mcps1.2.5.1.4 "><p id="ad13b53d1e88a48a69ecafbfa92063a74"><a name="ad13b53d1e88a48a69ecafbfa92063a74"></a><a name="ad13b53d1e88a48a69ecafbfa92063a74"></a>Specifies the target UID.</p>
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

## 响应消息<a name="s3687f13ac2bf4e5494185bac214448ff"></a>

**响应参数：**

请求参数的详细描述请参见[表4](删除Secret.md#zh-cn_topic_0079615047_table30941925)。

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

## 状态码<a name="sb708a925922c4906ac99d1ac2c6751e5"></a>

[表4](#zh-cn_topic_0079615056_table50951864)描述API的状态码。

**表 4**  状态码

<a name="zh-cn_topic_0079615056_table50951864"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615056_row65026214"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p41872640203046"><a name="p41872640203046"></a><a name="p41872640203046"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p36240679203046"><a name="p36240679203046"></a><a name="p36240679203046"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615056_row21145452"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615056_p35060088"><a name="zh-cn_topic_0079615056_p35060088"></a><a name="zh-cn_topic_0079615056_p35060088"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615056_p179841688599"><a name="zh-cn_topic_0079615056_p179841688599"></a><a name="zh-cn_topic_0079615056_p179841688599"></a>Delete a Pod resource objectre successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

