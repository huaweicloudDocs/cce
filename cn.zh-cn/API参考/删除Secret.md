# 删除Secret<a name="cce_02_0044"></a>

## 功能介绍<a name="s33443b62a3884400b29be7af1a63ce43"></a>

该API用于删除指定Namespace下的Secret对象。

## URI<a name="sb59375acc1994f429f8cabd5b1bf4b80"></a>

DELETE /api/v1/namespaces/\{namespace\}/secrets/\{name\}

[表1](#zh-cn_topic_0079615047_table8667044)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615047_table8667044"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row41088586"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p39841133"><a name="zh-cn_topic_0079615047_p39841133"></a><a name="zh-cn_topic_0079615047_p39841133"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p9546513203257"><a name="p9546513203257"></a><a name="p9546513203257"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p35070093203257"><a name="p35070093203257"></a><a name="p35070093203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row29933900"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p8726850"><a name="zh-cn_topic_0079615047_p8726850"></a><a name="zh-cn_topic_0079615047_p8726850"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p35786256"><a name="zh-cn_topic_0079615047_p35786256"></a><a name="zh-cn_topic_0079615047_p35786256"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p13005663"><a name="zh-cn_topic_0079615047_p13005663"></a><a name="zh-cn_topic_0079615047_p13005663"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row50486336"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p62861417"><a name="zh-cn_topic_0079615047_p62861417"></a><a name="zh-cn_topic_0079615047_p62861417"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p58610051"><a name="zh-cn_topic_0079615047_p58610051"></a><a name="zh-cn_topic_0079615047_p58610051"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p49793718"><a name="zh-cn_topic_0079615047_p49793718"></a><a name="zh-cn_topic_0079615047_p49793718"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row45490280"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p60834034"><a name="zh-cn_topic_0079615047_p60834034"></a><a name="zh-cn_topic_0079615047_p60834034"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p28609704"><a name="zh-cn_topic_0079615047_p28609704"></a><a name="zh-cn_topic_0079615047_p28609704"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p35684724"><a name="zh-cn_topic_0079615047_p35684724"></a><a name="zh-cn_topic_0079615047_p35684724"></a>Name of the Secret.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="see27f791d3ac4acfa5128d4b61126f2f"></a>

**请求参数：**

请求参数如[表2](#zh-cn_topic_0079615047_table10894532)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079615047_table10894532"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row27851360"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615047_p41367663"><a name="zh-cn_topic_0079615047_p41367663"></a><a name="zh-cn_topic_0079615047_p41367663"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.18%" id="mcps1.2.5.1.2"><p id="p11434212203257"><a name="p11434212203257"></a><a name="p11434212203257"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p53755986203257"><a name="p53755986203257"></a><a name="p53755986203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28%" id="mcps1.2.5.1.4"><p id="p59267649203257"><a name="p59267649203257"></a><a name="p59267649203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row33398680"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615047_p20938598"><a name="zh-cn_topic_0079615047_p20938598"></a><a name="zh-cn_topic_0079615047_p20938598"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615047_p18304888"><a name="zh-cn_topic_0079615047_p18304888"></a><a name="zh-cn_topic_0079615047_p18304888"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615047_p6300983"><a name="zh-cn_topic_0079615047_p6300983"></a><a name="zh-cn_topic_0079615047_p6300983"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615047_p40617610"><a name="zh-cn_topic_0079615047_p40617610"></a><a name="zh-cn_topic_0079615047_p40617610"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="zh-cn_topic_0079615047_p30014175"><a name="zh-cn_topic_0079615047_p30014175"></a><a name="zh-cn_topic_0079615047_p30014175"></a>The value of this parameter is <strong id="b15675857202818"><a name="b15675857202818"></a><a name="b15675857202818"></a>DeleteOptions</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row15229100"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615047_p25597569"><a name="zh-cn_topic_0079615047_p25597569"></a><a name="zh-cn_topic_0079615047_p25597569"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615047_p60137223"><a name="zh-cn_topic_0079615047_p60137223"></a><a name="zh-cn_topic_0079615047_p60137223"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615047_p39276901"><a name="zh-cn_topic_0079615047_p39276901"></a><a name="zh-cn_topic_0079615047_p39276901"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615047_p27312452"><a name="zh-cn_topic_0079615047_p27312452"></a><a name="zh-cn_topic_0079615047_p27312452"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="zh-cn_topic_0079615047_p44485484"><a name="zh-cn_topic_0079615047_p44485484"></a><a name="zh-cn_topic_0079615047_p44485484"></a>The value of this parameter is <strong id="zh-cn_topic_0079615047_b64825036"><a name="zh-cn_topic_0079615047_b64825036"></a><a name="zh-cn_topic_0079615047_b64825036"></a>v1</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row46554414"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615047_p12811205"><a name="zh-cn_topic_0079615047_p12811205"></a><a name="zh-cn_topic_0079615047_p12811205"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615047_p31074713"><a name="zh-cn_topic_0079615047_p31074713"></a><a name="zh-cn_topic_0079615047_p31074713"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615047_p34023825"><a name="zh-cn_topic_0079615047_p34023825"></a><a name="zh-cn_topic_0079615047_p34023825"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615047_p4466454"><a name="zh-cn_topic_0079615047_p4466454"></a><a name="zh-cn_topic_0079615047_p4466454"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
<p id="zh-cn_topic_0079615047_p40198088"><a name="zh-cn_topic_0079615047_p40198088"></a><a name="zh-cn_topic_0079615047_p40198088"></a>Value range of this parameter: &gt; 0.</p>
</td>
</tr>
<tr id="r5127218248e44810aef8009970b099fe"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="af2819716cf77473687ccab24616a578e"><a name="af2819716cf77473687ccab24616a578e"></a><a name="af2819716cf77473687ccab24616a578e"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="a641ed44081304841a5fd30190451fa21"><a name="a641ed44081304841a5fd30190451fa21"></a><a name="a641ed44081304841a5fd30190451fa21"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a38577330aabe498982d7e5570c56ca61"><a name="a38577330aabe498982d7e5570c56ca61"></a><a name="a38577330aabe498982d7e5570c56ca61"></a><a href="#cce_02_0044__t3a3f9a21f2254ea1a37ab173af770d4b">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="add861d80e28b4c3abeb4aaba2bc1656e"><a name="add861d80e28b4c3abeb4aaba2bc1656e"></a><a name="add861d80e28b4c3abeb4aaba2bc1656e"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="r280ac76ab36f441a9340fd44c7c18eca"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a0bf8df19415f4b5bacf092be129b8cdd"><a name="a0bf8df19415f4b5bacf092be129b8cdd"></a><a name="a0bf8df19415f4b5bacf092be129b8cdd"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="ad17b008e7916427d97b66618d77c9284"><a name="ad17b008e7916427d97b66618d77c9284"></a><a name="ad17b008e7916427d97b66618d77c9284"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a44d8e6006792468ab7322ab1cfa791ef"><a name="a44d8e6006792468ab7322ab1cfa791ef"></a><a name="a44d8e6006792468ab7322ab1cfa791ef"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a81268fbf98a84f07a0a4492319b5b36a"><a name="a81268fbf98a84f07a0a4492319b5b36a"></a><a name="a81268fbf98a84f07a0a4492319b5b36a"></a>Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  preconditions字段数据结构说明

<a name="t3a3f9a21f2254ea1a37ab173af770d4b"></a>
<table><thead align="left"><tr id="rdf23a66a2e97487dadafe65b50690fd6"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="aceada35a29e04de7b4366e0429c828e7"><a name="aceada35a29e04de7b4366e0429c828e7"></a><a name="aceada35a29e04de7b4366e0429c828e7"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p6896990203257"><a name="p6896990203257"></a><a name="p6896990203257"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p21785280203257"><a name="p21785280203257"></a><a name="p21785280203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p19777271203257"><a name="p19777271203257"></a><a name="p19777271203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r440e4627ef3f46bcb2819e8054930c91"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="ade720eb2e553427598834fad82739f47"><a name="ade720eb2e553427598834fad82739f47"></a><a name="ade720eb2e553427598834fad82739f47"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a7afebb3677e84e6d9567a2e465b8c2d9"><a name="a7afebb3677e84e6d9567a2e465b8c2d9"></a><a name="a7afebb3677e84e6d9567a2e465b8c2d9"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a4623a62cb6324c1c900e9a92971f774d"><a name="a4623a62cb6324c1c900e9a92971f774d"></a><a name="a4623a62cb6324c1c900e9a92971f774d"></a>types.UID</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a065c010ac9d74729897e30c457cae2bd"><a name="a065c010ac9d74729897e30c457cae2bd"></a><a name="a065c010ac9d74729897e30c457cae2bd"></a>Specifies the target UID.</p>
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

## 响应消息<a name="s00e4933458e84b218d5369e1c39bfae6"></a>

**响应参数：**

响应参数如[表4](#zh-cn_topic_0079615047_table30941925)所示。

**表 4**  参数描述

<a name="zh-cn_topic_0079615047_table30941925"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row37328119"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p3678790"><a name="zh-cn_topic_0079615047_p3678790"></a><a name="zh-cn_topic_0079615047_p3678790"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p56650888203257"><a name="p56650888203257"></a><a name="p56650888203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p25319233203257"><a name="p25319233203257"></a><a name="p25319233203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row44834872"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p7745977"><a name="zh-cn_topic_0079615047_p7745977"></a><a name="zh-cn_topic_0079615047_p7745977"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p23444395"><a name="zh-cn_topic_0079615047_p23444395"></a><a name="zh-cn_topic_0079615047_p23444395"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p19947829"><a name="zh-cn_topic_0079615047_p19947829"></a><a name="zh-cn_topic_0079615047_p19947829"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row45312739"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p46453253"><a name="zh-cn_topic_0079615047_p46453253"></a><a name="zh-cn_topic_0079615047_p46453253"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p4617172"><a name="zh-cn_topic_0079615047_p4617172"></a><a name="zh-cn_topic_0079615047_p4617172"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p38446647"><a name="zh-cn_topic_0079615047_p38446647"></a><a name="zh-cn_topic_0079615047_p38446647"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row10475508"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p43209809"><a name="zh-cn_topic_0079615047_p43209809"></a><a name="zh-cn_topic_0079615047_p43209809"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p10333622"><a name="zh-cn_topic_0079615047_p10333622"></a><a name="zh-cn_topic_0079615047_p10333622"></a><a href="#cce_02_0044__zh-cn_topic_0079615047_table10041872">表5</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p31717068"><a name="zh-cn_topic_0079615047_p31717068"></a><a name="zh-cn_topic_0079615047_p31717068"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row17018161"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p36293778"><a name="zh-cn_topic_0079615047_p36293778"></a><a name="zh-cn_topic_0079615047_p36293778"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p54114937"><a name="zh-cn_topic_0079615047_p54114937"></a><a name="zh-cn_topic_0079615047_p54114937"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p21233739"><a name="zh-cn_topic_0079615047_p21233739"></a><a name="zh-cn_topic_0079615047_p21233739"></a>Status of the operation. One of: "Success" or "Failure".</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row56885929"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p44357513"><a name="zh-cn_topic_0079615047_p44357513"></a><a name="zh-cn_topic_0079615047_p44357513"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p36188810"><a name="zh-cn_topic_0079615047_p36188810"></a><a name="zh-cn_topic_0079615047_p36188810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p45612499"><a name="zh-cn_topic_0079615047_p45612499"></a><a name="zh-cn_topic_0079615047_p45612499"></a>A human-readable description of the status of this operation.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row7859315"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p32624764"><a name="zh-cn_topic_0079615047_p32624764"></a><a name="zh-cn_topic_0079615047_p32624764"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p25360226"><a name="zh-cn_topic_0079615047_p25360226"></a><a name="zh-cn_topic_0079615047_p25360226"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p40912396"><a name="zh-cn_topic_0079615047_p40912396"></a><a name="zh-cn_topic_0079615047_p40912396"></a>A machine-readable description of why this operation is in the "Failure" status. If this value is empty there is no information available. A Reason clarifies an HTTP status code but does not override it.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row32667246"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p28801274"><a name="zh-cn_topic_0079615047_p28801274"></a><a name="zh-cn_topic_0079615047_p28801274"></a>details</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p51201854"><a name="zh-cn_topic_0079615047_p51201854"></a><a name="zh-cn_topic_0079615047_p51201854"></a><a href="#cce_02_0044__zh-cn_topic_0079615047_table23267991">表6</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p53709539"><a name="zh-cn_topic_0079615047_p53709539"></a><a name="zh-cn_topic_0079615047_p53709539"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row13623809"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p29786778"><a name="zh-cn_topic_0079615047_p29786778"></a><a name="zh-cn_topic_0079615047_p29786778"></a>code</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p63918823"><a name="zh-cn_topic_0079615047_p63918823"></a><a name="zh-cn_topic_0079615047_p63918823"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p10042193"><a name="zh-cn_topic_0079615047_p10042193"></a><a name="zh-cn_topic_0079615047_p10042193"></a>Suggested HTTP return code for this status, 0 if not set.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  metadata字段数据结构说明

<a name="zh-cn_topic_0079615047_table10041872"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row4239285"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p7837765"><a name="zh-cn_topic_0079615047_p7837765"></a><a name="zh-cn_topic_0079615047_p7837765"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p16832548203257"><a name="p16832548203257"></a><a name="p16832548203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p21259186203257"><a name="p21259186203257"></a><a name="p21259186203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row63891552"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p7833234"><a name="zh-cn_topic_0079615047_p7833234"></a><a name="zh-cn_topic_0079615047_p7833234"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p30512241"><a name="zh-cn_topic_0079615047_p30512241"></a><a name="zh-cn_topic_0079615047_p30512241"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p55572452"><a name="zh-cn_topic_0079615047_p55572452"></a><a name="zh-cn_topic_0079615047_p55572452"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row30390025"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p45672950"><a name="zh-cn_topic_0079615047_p45672950"></a><a name="zh-cn_topic_0079615047_p45672950"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p8521451"><a name="zh-cn_topic_0079615047_p8521451"></a><a name="zh-cn_topic_0079615047_p8521451"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p19148945"><a name="zh-cn_topic_0079615047_p19148945"></a><a name="zh-cn_topic_0079615047_p19148945"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 6**  details字段数据结构说明

<a name="zh-cn_topic_0079615047_table23267991"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row467118"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p37836574"><a name="zh-cn_topic_0079615047_p37836574"></a><a name="zh-cn_topic_0079615047_p37836574"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p32915338203257"><a name="p32915338203257"></a><a name="p32915338203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p48896756203257"><a name="p48896756203257"></a><a name="p48896756203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row11018834"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p20110389"><a name="zh-cn_topic_0079615047_p20110389"></a><a name="zh-cn_topic_0079615047_p20110389"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p18328792"><a name="zh-cn_topic_0079615047_p18328792"></a><a name="zh-cn_topic_0079615047_p18328792"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p8237155"><a name="zh-cn_topic_0079615047_p8237155"></a><a name="zh-cn_topic_0079615047_p8237155"></a>The name attribute of the resource associated with the status StatusReason (when there is a single name which can be described).</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row7025535"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p32197499"><a name="zh-cn_topic_0079615047_p32197499"></a><a name="zh-cn_topic_0079615047_p32197499"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p57860594"><a name="zh-cn_topic_0079615047_p57860594"></a><a name="zh-cn_topic_0079615047_p57860594"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p56196558"><a name="zh-cn_topic_0079615047_p56196558"></a><a name="zh-cn_topic_0079615047_p56196558"></a>The kind attribute of the resource associated with the status StatusReason. On some operations may differ from the requested resource Kind.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row36006982"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p30884404"><a name="zh-cn_topic_0079615047_p30884404"></a><a name="zh-cn_topic_0079615047_p30884404"></a>causes</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p18608762"><a name="zh-cn_topic_0079615047_p18608762"></a><a name="zh-cn_topic_0079615047_p18608762"></a><a href="#cce_02_0044__zh-cn_topic_0079615047_table8085329">表7</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p30914753"><a name="zh-cn_topic_0079615047_p30914753"></a><a name="zh-cn_topic_0079615047_p30914753"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row9797324"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p55385783"><a name="zh-cn_topic_0079615047_p55385783"></a><a name="zh-cn_topic_0079615047_p55385783"></a>retryAfterSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p57063414"><a name="zh-cn_topic_0079615047_p57063414"></a><a name="zh-cn_topic_0079615047_p57063414"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p58733810"><a name="zh-cn_topic_0079615047_p58733810"></a><a name="zh-cn_topic_0079615047_p58733810"></a>If specified, the time in seconds before the operation should be retried.</p>
</td>
</tr>
<tr id="r0d1d58b07bd040818c28c28ba70ade83"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a37b4a7b3504040c8b24983f9f034d212"><a name="a37b4a7b3504040c8b24983f9f034d212"></a><a name="a37b4a7b3504040c8b24983f9f034d212"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p198842574110"><a name="zh-cn_topic_0079615047_p198842574110"></a><a name="zh-cn_topic_0079615047_p198842574110"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="aa4615c1a43234eb19bfd9f0ad4658d5e"><a name="aa4615c1a43234eb19bfd9f0ad4658d5e"></a><a name="aa4615c1a43234eb19bfd9f0ad4658d5e"></a>UID of the resource. (when there is a single resource which can be described).</p>
</td>
</tr>
<tr id="rc0e343be5f114feeaa79e099c6662dbe"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p199461439422"><a name="zh-cn_topic_0079615047_p199461439422"></a><a name="zh-cn_topic_0079615047_p199461439422"></a>group</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p094619316422"><a name="zh-cn_topic_0079615047_p094619316422"></a><a name="zh-cn_topic_0079615047_p094619316422"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="ac139fb12d76c4626b1a8e77f2eaf561a"><a name="ac139fb12d76c4626b1a8e77f2eaf561a"></a><a name="ac139fb12d76c4626b1a8e77f2eaf561a"></a>The group attribute of the resource associated with the status StatusReason.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  causes字段数据结构说明

<a name="zh-cn_topic_0079615047_table8085329"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row2488285"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p224543"><a name="zh-cn_topic_0079615047_p224543"></a><a name="zh-cn_topic_0079615047_p224543"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p40819061203257"><a name="p40819061203257"></a><a name="p40819061203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p18009654203257"><a name="p18009654203257"></a><a name="p18009654203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row12212497"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p49688181"><a name="zh-cn_topic_0079615047_p49688181"></a><a name="zh-cn_topic_0079615047_p49688181"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p65319718"><a name="zh-cn_topic_0079615047_p65319718"></a><a name="zh-cn_topic_0079615047_p65319718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p56405771"><a name="zh-cn_topic_0079615047_p56405771"></a><a name="zh-cn_topic_0079615047_p56405771"></a>A machine-readable description of the cause of the error. If this value is empty there is no information available.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row37889892"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p49182451"><a name="zh-cn_topic_0079615047_p49182451"></a><a name="zh-cn_topic_0079615047_p49182451"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p24355627"><a name="zh-cn_topic_0079615047_p24355627"></a><a name="zh-cn_topic_0079615047_p24355627"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p26648755"><a name="zh-cn_topic_0079615047_p26648755"></a><a name="zh-cn_topic_0079615047_p26648755"></a>A human-readable description of the cause of the error. This field may be presented as-is to a reader.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row38512204"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p32480848"><a name="zh-cn_topic_0079615047_p32480848"></a><a name="zh-cn_topic_0079615047_p32480848"></a>field</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p13703032"><a name="zh-cn_topic_0079615047_p13703032"></a><a name="zh-cn_topic_0079615047_p13703032"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p36203821"><a name="zh-cn_topic_0079615047_p36203821"></a><a name="zh-cn_topic_0079615047_p36203821"></a>The field of the resource that has caused this error, as named by its JSON serialization. May include dot and postfix notation for nested attributes. Arrays are zero-indexed. Fields may appear more than once in an array of causes due to fields having multiple errors.</p>
</td>
</tr>
</tbody>
</table>

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

## 状态码<a name="s25ccd5e4fb8949dd9dee7a70d15c0810"></a>

[表8](#zh-cn_topic_0079615047_table5659105)描述API的状态码。

**表 8**  状态码

<a name="zh-cn_topic_0079615047_table5659105"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row40139983"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p36672758203257"><a name="p36672758203257"></a><a name="p36672758203257"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p17703441203257"><a name="p17703441203257"></a><a name="p17703441203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row4146549"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615047_p326206"><a name="zh-cn_topic_0079615047_p326206"></a><a name="zh-cn_topic_0079615047_p326206"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615047_p26422695"><a name="zh-cn_topic_0079615047_p26422695"></a><a name="zh-cn_topic_0079615047_p26422695"></a>Delete a secret resource objectre successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

