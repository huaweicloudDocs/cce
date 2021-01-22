# 删除Secret<a name="cce_02_0044"></a>

## 功能介绍<a name="s33443b62a3884400b29be7af1a63ce43"></a>

该API用于删除指定Namespace下的Secret对象。

## URI<a name="sb59375acc1994f429f8cabd5b1bf4b80"></a>

DELETE /api/v1/namespaces/\{namespace\}/secrets/\{name\}

[表1](#zh-cn_topic_0079615047_table8667044)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615047_table8667044"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row41088586"><th class="cellrowborder" valign="top" width="17.481748174817483%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p39841133"><a name="zh-cn_topic_0079615047_p39841133"></a><a name="zh-cn_topic_0079615047_p39841133"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.21182118211821%" id="mcps1.2.4.1.2"><p id="p9546513203257"><a name="p9546513203257"></a><a name="p9546513203257"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="64.3064306430643%" id="mcps1.2.4.1.3"><p id="p35070093203257"><a name="p35070093203257"></a><a name="p35070093203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row50486336"><td class="cellrowborder" valign="top" width="17.481748174817483%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p62861417"><a name="zh-cn_topic_0079615047_p62861417"></a><a name="zh-cn_topic_0079615047_p62861417"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="18.21182118211821%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p58610051"><a name="zh-cn_topic_0079615047_p58610051"></a><a name="zh-cn_topic_0079615047_p58610051"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="64.3064306430643%" headers="mcps1.2.4.1.3 "><p id="p9404112815234"><a name="p9404112815234"></a><a name="p9404112815234"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row45490280"><td class="cellrowborder" valign="top" width="17.481748174817483%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p60834034"><a name="zh-cn_topic_0079615047_p60834034"></a><a name="zh-cn_topic_0079615047_p60834034"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="18.21182118211821%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p28609704"><a name="zh-cn_topic_0079615047_p28609704"></a><a name="zh-cn_topic_0079615047_p28609704"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="64.3064306430643%" headers="mcps1.2.4.1.3 "><p id="p37971831132312"><a name="p37971831132312"></a><a name="p37971831132312"></a>Name of the Secret.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="see27f791d3ac4acfa5128d4b61126f2f"></a>

**请求参数：**

请求参数如[表2](#table13766144711235)所示。

**表 2**  参数描述

<a name="table13766144711235"></a>
<table><thead align="left"><tr id="row7767104712314"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="p16767547192317"><a name="p16767547192317"></a><a name="p16767547192317"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.18%" id="mcps1.2.5.1.2"><p id="p117671547102319"><a name="p117671547102319"></a><a name="p117671547102319"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p177671347152314"><a name="p177671347152314"></a><a name="p177671347152314"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28%" id="mcps1.2.5.1.4"><p id="p3767104711236"><a name="p3767104711236"></a><a name="p3767104711236"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row19767144713233"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p1776774712312"><a name="p1776774712312"></a><a name="p1776774712312"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="p19767154719236"><a name="p19767154719236"></a><a name="p19767154719236"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p18767154710235"><a name="p18767154710235"></a><a name="p18767154710235"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615047_p40617610"><a name="zh-cn_topic_0079615047_p40617610"></a><a name="zh-cn_topic_0079615047_p40617610"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="p1767164717231"><a name="p1767164717231"></a><a name="p1767164717231"></a>The value of this parameter is <strong id="b15675857202818"><a name="b15675857202818"></a><a name="b15675857202818"></a>DeleteOptions</strong>.</p>
</td>
</tr>
<tr id="row9767124717239"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p117671473237"><a name="p117671473237"></a><a name="p117671473237"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="p5767184710233"><a name="p5767184710233"></a><a name="p5767184710233"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p197676474235"><a name="p197676474235"></a><a name="p197676474235"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615047_p27312452"><a name="zh-cn_topic_0079615047_p27312452"></a><a name="zh-cn_topic_0079615047_p27312452"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="p8767547202311"><a name="p8767547202311"></a><a name="p8767547202311"></a>The value of this parameter is <strong id="b97676478235"><a name="b97676478235"></a><a name="b97676478235"></a>v1</strong>.</p>
</td>
</tr>
<tr id="row18767747112320"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p15767124717231"><a name="p15767124717231"></a><a name="p15767124717231"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="p1076715471239"><a name="p1076715471239"></a><a name="p1076715471239"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p076794722315"><a name="p076794722315"></a><a name="p076794722315"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="p1276784742313"><a name="p1276784742313"></a><a name="p1276784742313"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
<p id="zh-cn_topic_0079615047_p40198088"><a name="zh-cn_topic_0079615047_p40198088"></a><a name="zh-cn_topic_0079615047_p40198088"></a>Value range of this parameter: &gt; 0.</p>
</td>
</tr>
<tr id="row10768194714236"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p776884714239"><a name="p776884714239"></a><a name="p776884714239"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="p2076894712235"><a name="p2076894712235"></a><a name="p2076894712235"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p1276884752317"><a name="p1276884752317"></a><a name="p1276884752317"></a><a href="#t3a3f9a21f2254ea1a37ab173af770d4b">preconditions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="p676874711234"><a name="p676874711234"></a><a name="p676874711234"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="row18768194717233"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p67683479237"><a name="p67683479237"></a><a name="p67683479237"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="p18768124710237"><a name="p18768124710237"></a><a name="p18768124710237"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p37681447112316"><a name="p37681447112316"></a><a name="p37681447112316"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="p137681474239"><a name="p137681474239"></a><a name="p137681474239"></a>Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list.</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p21785280203257"><a name="p21785280203257"></a><a name="p21785280203257"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p19777271203257"><a name="p19777271203257"></a><a name="p19777271203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r440e4627ef3f46bcb2819e8054930c91"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="ade720eb2e553427598834fad82739f47"><a name="ade720eb2e553427598834fad82739f47"></a><a name="ade720eb2e553427598834fad82739f47"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a7afebb3677e84e6d9567a2e465b8c2d9"><a name="a7afebb3677e84e6d9567a2e465b8c2d9"></a><a name="a7afebb3677e84e6d9567a2e465b8c2d9"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a22ac63c8187b498d89bf40f317c194a4"><a name="a22ac63c8187b498d89bf40f317c194a4"></a><a name="a22ac63c8187b498d89bf40f317c194a4"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p426585314246"><a name="p426585314246"></a><a name="p426585314246"></a>Specifies the target UID.</p>
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

## 响应消息<a name="section1087613914251"></a>

**响应参数：**

响应参数如[表4](#table13877539132512)所示。

**表 4**  参数描述

<a name="table13877539132512"></a>
<table><thead align="left"><tr id="row587743922513"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p587712393259"><a name="p587712393259"></a><a name="p587712393259"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p2877539102515"><a name="p2877539102515"></a><a name="p2877539102515"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p187713912254"><a name="p187713912254"></a><a name="p187713912254"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16877439182511"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p687793916253"><a name="p687793916253"></a><a name="p687793916253"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p118771139192510"><a name="p118771139192510"></a><a name="p118771139192510"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p19877203922511"><a name="p19877203922511"></a><a name="p19877203922511"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row1887753919258"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p8877133919255"><a name="p8877133919255"></a><a name="p8877133919255"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p178771639202519"><a name="p178771639202519"></a><a name="p178771639202519"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p13877639162518"><a name="p13877639162518"></a><a name="p13877639162518"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row787716394254"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p58772039172513"><a name="p58772039172513"></a><a name="p58772039172513"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p128771339172515"><a name="p128771339172515"></a><a name="p128771339172515"></a><a href="#table12878113992515">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p188781539162517"><a name="p188781539162517"></a><a name="p188781539162517"></a>-</p>
</td>
</tr>
<tr id="row3878153911251"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p11878113916254"><a name="p11878113916254"></a><a name="p11878113916254"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p78781239102519"><a name="p78781239102519"></a><a name="p78781239102519"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p21233739"><a name="zh-cn_topic_0079615047_p21233739"></a><a name="zh-cn_topic_0079615047_p21233739"></a>Status of the operation. One of: "Success" or "Failure".</p>
</td>
</tr>
<tr id="row1187843915255"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p88781839172511"><a name="p88781839172511"></a><a name="p88781839172511"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1387883914254"><a name="p1387883914254"></a><a name="p1387883914254"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p4878163982511"><a name="p4878163982511"></a><a name="p4878163982511"></a>A human-readable description of the status of this operation.</p>
</td>
</tr>
<tr id="row13878133982513"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p13878739122513"><a name="p13878739122513"></a><a name="p13878739122513"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p11878839172516"><a name="p11878839172516"></a><a name="p11878839172516"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p58781639162513"><a name="p58781639162513"></a><a name="p58781639162513"></a>A machine-readable description of why this operation is in the "Failure" status. If this value is empty there is no information available. A Reason clarifies an HTTP status code but does not override it.</p>
</td>
</tr>
<tr id="row168789399259"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p387893972513"><a name="p387893972513"></a><a name="p387893972513"></a>details</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p3878143913252"><a name="p3878143913252"></a><a name="p3878143913252"></a><a href="#table17879339152516">details</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p4878339172519"><a name="p4878339172519"></a><a name="p4878339172519"></a>-</p>
</td>
</tr>
<tr id="row7878039132513"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1787803916252"><a name="p1787803916252"></a><a name="p1787803916252"></a>code</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p5878439192519"><a name="p5878439192519"></a><a name="p5878439192519"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p12878539192515"><a name="p12878539192515"></a><a name="p12878539192515"></a>Suggested HTTP return code for this status, 0 if not set.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  metadata字段数据结构说明

<a name="table12878113992515"></a>
<table><thead align="left"><tr id="row178791039172515"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="p138791239112519"><a name="p138791239112519"></a><a name="p138791239112519"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p8879639132514"><a name="p8879639132514"></a><a name="p8879639132514"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p1287943922519"><a name="p1287943922519"></a><a name="p1287943922519"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row987963962518"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p14879143912513"><a name="p14879143912513"></a><a name="p14879143912513"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p138797394259"><a name="p138797394259"></a><a name="p138797394259"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p55572452"><a name="zh-cn_topic_0079615047_p55572452"></a><a name="zh-cn_topic_0079615047_p55572452"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row38791539122517"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p1087903982519"><a name="p1087903982519"></a><a name="p1087903982519"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p587933922513"><a name="p587933922513"></a><a name="p587933922513"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p19148945"><a name="zh-cn_topic_0079615047_p19148945"></a><a name="zh-cn_topic_0079615047_p19148945"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 6**  details字段数据结构说明

<a name="table17879339152516"></a>
<table><thead align="left"><tr id="row16879183992516"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="p17879193911255"><a name="p17879193911255"></a><a name="p17879193911255"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p1787963932517"><a name="p1787963932517"></a><a name="p1787963932517"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p1288063920251"><a name="p1288063920251"></a><a name="p1288063920251"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row188011397257"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p18802396256"><a name="p18802396256"></a><a name="p18802396256"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p688011397258"><a name="p688011397258"></a><a name="p688011397258"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p168808393251"><a name="p168808393251"></a><a name="p168808393251"></a>The name attribute of the resource associated with the status StatusReason (when there is a single name which can be described).</p>
</td>
</tr>
<tr id="row88801039162517"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p888013972516"><a name="p888013972516"></a><a name="p888013972516"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p28801639112511"><a name="p28801639112511"></a><a name="p28801639112511"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p5880113911259"><a name="p5880113911259"></a><a name="p5880113911259"></a>The kind attribute of the resource associated with the status StatusReason. On some operations may differ from the requested resource Kind.</p>
</td>
</tr>
<tr id="row1888063922514"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p10880103918253"><a name="p10880103918253"></a><a name="p10880103918253"></a>causes</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p1788083912515"><a name="p1788083912515"></a><a name="p1788083912515"></a><a href="#table1688123912516">causes</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p0880839162514"><a name="p0880839162514"></a><a name="p0880839162514"></a>-</p>
</td>
</tr>
<tr id="row1788013916254"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p19880203912511"><a name="p19880203912511"></a><a name="p19880203912511"></a>retryAfterSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p1788023919257"><a name="p1788023919257"></a><a name="p1788023919257"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p1588016392259"><a name="p1588016392259"></a><a name="p1588016392259"></a>If specified, the time in seconds before the operation should be retried.</p>
</td>
</tr>
<tr id="row6880113911259"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p8880239152513"><a name="p8880239152513"></a><a name="p8880239152513"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p16880173962514"><a name="p16880173962514"></a><a name="p16880173962514"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p1688193920259"><a name="p1688193920259"></a><a name="p1688193920259"></a>UID of the resource. (when there is a single resource which can be described).</p>
</td>
</tr>
<tr id="row3881103920259"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p19881133942513"><a name="p19881133942513"></a><a name="p19881133942513"></a>group</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p38812390254"><a name="p38812390254"></a><a name="p38812390254"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="ac139fb12d76c4626b1a8e77f2eaf561a"><a name="ac139fb12d76c4626b1a8e77f2eaf561a"></a><a name="ac139fb12d76c4626b1a8e77f2eaf561a"></a>The group attribute of the resource associated with the status StatusReason.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  causes字段数据结构说明

<a name="table1688123912516"></a>
<table><thead align="left"><tr id="row208811439132512"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="p1088133962516"><a name="p1088133962516"></a><a name="p1088133962516"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p0881539122513"><a name="p0881539122513"></a><a name="p0881539122513"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p288113902516"><a name="p288113902516"></a><a name="p288113902516"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row588120390253"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p8881143992512"><a name="p8881143992512"></a><a name="p8881143992512"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p488119393250"><a name="p488119393250"></a><a name="p488119393250"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p388111398258"><a name="p388111398258"></a><a name="p388111398258"></a>A machine-readable description of the cause of the error. If this value is empty there is no information available.</p>
</td>
</tr>
<tr id="row148811739132516"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p58811539162512"><a name="p58811539162512"></a><a name="p58811539162512"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p48821439192514"><a name="p48821439192514"></a><a name="p48821439192514"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p58829393251"><a name="p58829393251"></a><a name="p58829393251"></a>A human-readable description of the cause of the error. This field may be presented as-is to a reader.</p>
</td>
</tr>
<tr id="row58829391253"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p388203910254"><a name="p388203910254"></a><a name="p388203910254"></a>field</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="p1788243952514"><a name="p1788243952514"></a><a name="p1788243952514"></a>String</p>
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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p188922206273"><a name="p188922206273"></a><a name="p188922206273"></a>Delete a secret resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

