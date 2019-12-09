# 删除Namespace<a name="cce_02_0051"></a>

## 功能介绍<a name="sd3cfd7eb5e604cbfacc39f3d39217286"></a>

该API用于删除一个Namespace。

## URI<a name="sb360ead1682b4a91886de13dec66f5c4"></a>

DELETE /api/v1/namespaces/\{name\}

[表1](#zh-cn_topic_0079615060_table31198475)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615060_table31198475"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615060_row10758903"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615060_p66164776"><a name="zh-cn_topic_0079615060_p66164776"></a><a name="zh-cn_topic_0079615060_p66164776"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="23%" id="mcps1.2.4.1.2"><p id="p2285494921117"><a name="p2285494921117"></a><a name="p2285494921117"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="44%" id="mcps1.2.4.1.3"><p id="p3931158921117"><a name="p3931158921117"></a><a name="p3931158921117"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615060_row46130559"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615060_p45587811"><a name="zh-cn_topic_0079615060_p45587811"></a><a name="zh-cn_topic_0079615060_p45587811"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615060_p1625174"><a name="zh-cn_topic_0079615060_p1625174"></a><a name="zh-cn_topic_0079615060_p1625174"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615060_p64530307"><a name="zh-cn_topic_0079615060_p64530307"></a><a name="zh-cn_topic_0079615060_p64530307"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615060_row55501577"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615060_p66442792"><a name="zh-cn_topic_0079615060_p66442792"></a><a name="zh-cn_topic_0079615060_p66442792"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615060_p13157104"><a name="zh-cn_topic_0079615060_p13157104"></a><a name="zh-cn_topic_0079615060_p13157104"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615060_p59092488"><a name="zh-cn_topic_0079615060_p59092488"></a><a name="zh-cn_topic_0079615060_p59092488"></a>Name of the Namespace.</p>
</td>
</tr>
<tr id="rb4b98780ec4947749cd70a13580cbd2a"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615060_p427182983911"><a name="zh-cn_topic_0079615060_p427182983911"></a><a name="zh-cn_topic_0079615060_p427182983911"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615060_p827162911396"><a name="zh-cn_topic_0079615060_p827162911396"></a><a name="zh-cn_topic_0079615060_p827162911396"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="a694bff5476754aee8d6cfe59c3b1825d"><a name="a694bff5476754aee8d6cfe59c3b1825d"></a><a name="a694bff5476754aee8d6cfe59c3b1825d"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="r0ac2448870d94693b737e1401fe3c64c"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a331c14c2f28e4c8a901952fe930ad5c5"><a name="a331c14c2f28e4c8a901952fe930ad5c5"></a><a name="a331c14c2f28e4c8a901952fe930ad5c5"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="a301f889a07ba4c4ab3bd4314bae0df0e"><a name="a301f889a07ba4c4ab3bd4314bae0df0e"></a><a name="a301f889a07ba4c4ab3bd4314bae0df0e"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615060_p157076445396"><a name="zh-cn_topic_0079615060_p157076445396"></a><a name="zh-cn_topic_0079615060_p157076445396"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="r60cb73a9905946e18477437d9bd30d97"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615060_p447118462392"><a name="zh-cn_topic_0079615060_p447118462392"></a><a name="zh-cn_topic_0079615060_p447118462392"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="a318694aa068f4384a683351e4ef97d16"><a name="a318694aa068f4384a683351e4ef97d16"></a><a name="a318694aa068f4384a683351e4ef97d16"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="ae473bba629a542729271da7f9a71f051"><a name="ae473bba629a542729271da7f9a71f051"></a><a name="ae473bba629a542729271da7f9a71f051"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s868ed9032ac544a8908766b83229eba1"></a>

请求参数：

请求参数如[表2](#zh-cn_topic_0079615060_table12350826)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079615060_table12350826"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615060_row59925661"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615060_p22140377"><a name="zh-cn_topic_0079615060_p22140377"></a><a name="zh-cn_topic_0079615060_p22140377"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p5941476021117"><a name="p5941476021117"></a><a name="p5941476021117"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p4786627521117"><a name="p4786627521117"></a><a name="p4786627521117"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p5196307921117"><a name="p5196307921117"></a><a name="p5196307921117"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615060_row26965262"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615060_p36702580"><a name="zh-cn_topic_0079615060_p36702580"></a><a name="zh-cn_topic_0079615060_p36702580"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615060_p20119003"><a name="zh-cn_topic_0079615060_p20119003"></a><a name="zh-cn_topic_0079615060_p20119003"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615060_p19026538"><a name="zh-cn_topic_0079615060_p19026538"></a><a name="zh-cn_topic_0079615060_p19026538"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615060_p64754634"><a name="zh-cn_topic_0079615060_p64754634"></a><a name="zh-cn_topic_0079615060_p64754634"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="zh-cn_topic_0079615060_p45920800"><a name="zh-cn_topic_0079615060_p45920800"></a><a name="zh-cn_topic_0079615060_p45920800"></a>The value of this parameter is <strong id="b15675857202818"><a name="b15675857202818"></a><a name="b15675857202818"></a>DeleteOptions</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615060_row28597308"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615060_p34680572"><a name="zh-cn_topic_0079615060_p34680572"></a><a name="zh-cn_topic_0079615060_p34680572"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615060_p57662920"><a name="zh-cn_topic_0079615060_p57662920"></a><a name="zh-cn_topic_0079615060_p57662920"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615060_p40184969"><a name="zh-cn_topic_0079615060_p40184969"></a><a name="zh-cn_topic_0079615060_p40184969"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615060_p33757095"><a name="zh-cn_topic_0079615060_p33757095"></a><a name="zh-cn_topic_0079615060_p33757095"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="zh-cn_topic_0079615060_p35378404"><a name="zh-cn_topic_0079615060_p35378404"></a><a name="zh-cn_topic_0079615060_p35378404"></a>The value of this parameter is <strong id="zh-cn_topic_0079615060_b49970185"><a name="zh-cn_topic_0079615060_b49970185"></a><a name="zh-cn_topic_0079615060_b49970185"></a>v1</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615060_row47078488"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615060_p55261147"><a name="zh-cn_topic_0079615060_p55261147"></a><a name="zh-cn_topic_0079615060_p55261147"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615060_p46967960"><a name="zh-cn_topic_0079615060_p46967960"></a><a name="zh-cn_topic_0079615060_p46967960"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615060_p46308405"><a name="zh-cn_topic_0079615060_p46308405"></a><a name="zh-cn_topic_0079615060_p46308405"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615060_p59993306"><a name="zh-cn_topic_0079615060_p59993306"></a><a name="zh-cn_topic_0079615060_p59993306"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
<p id="zh-cn_topic_0079615060_p3068848"><a name="zh-cn_topic_0079615060_p3068848"></a><a name="zh-cn_topic_0079615060_p3068848"></a>Value range of this parameter: &gt; 0.</p>
</td>
</tr>
<tr id="r19040324b1f24cda95ec85960de3bca9"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="ab1e7d75ba345492f873d6a74e51551ae"><a name="ab1e7d75ba345492f873d6a74e51551ae"></a><a name="ab1e7d75ba345492f873d6a74e51551ae"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a643998607448401cb98bac030344b4bf"><a name="a643998607448401cb98bac030344b4bf"></a><a name="a643998607448401cb98bac030344b4bf"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a3986d3fe4dff4241a1be5661e918570b"><a name="a3986d3fe4dff4241a1be5661e918570b"></a><a name="a3986d3fe4dff4241a1be5661e918570b"></a><a href="#td7fe8359dfff482f80c7050b45a5757d">preconditions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="ad98125a30297474b93b89524d135d843"><a name="ad98125a30297474b93b89524d135d843"></a><a name="ad98125a30297474b93b89524d135d843"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="r0d94f9c3b84c4841a3b412dd768e585f"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a2f5404495acc44138b2da399670b552e"><a name="a2f5404495acc44138b2da399670b552e"></a><a name="a2f5404495acc44138b2da399670b552e"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a7d1a05dfea7545be8b5dfba718ab95d9"><a name="a7d1a05dfea7545be8b5dfba718ab95d9"></a><a name="a7d1a05dfea7545be8b5dfba718ab95d9"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a6ff5290565884f038bc86768d81f7751"><a name="a6ff5290565884f038bc86768d81f7751"></a><a name="a6ff5290565884f038bc86768d81f7751"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a3e126a3a35c44347be63adba0965022a"><a name="a3e126a3a35c44347be63adba0965022a"></a><a name="a3e126a3a35c44347be63adba0965022a"></a>Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list.</p>
</td>
</tr>
<tr id="rec7650e13a8441f8abd08e52437496e3"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a42c8b588353e46da9f8e20eee887737c"><a name="a42c8b588353e46da9f8e20eee887737c"></a><a name="a42c8b588353e46da9f8e20eee887737c"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a81de60680b404a06a35dbe20680da9e9"><a name="a81de60680b404a06a35dbe20680da9e9"></a><a name="a81de60680b404a06a35dbe20680da9e9"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a9608d104d8784c84987487afa052171b"><a name="a9608d104d8784c84987487afa052171b"></a><a name="a9608d104d8784c84987487afa052171b"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a5b5e1dc98e7b47a493acb015bd084bfd"><a name="a5b5e1dc98e7b47a493acb015bd084bfd"></a><a name="a5b5e1dc98e7b47a493acb015bd084bfd"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  preconditions字段数据结构说明

<a name="td7fe8359dfff482f80c7050b45a5757d"></a>
<table><thead align="left"><tr id="r97d5bdf8c4ab42e591321f597bda73ea"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="ad27e47b8528642b09e02a98b9dbe622d"><a name="ad27e47b8528642b09e02a98b9dbe622d"></a><a name="ad27e47b8528642b09e02a98b9dbe622d"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p1148402521117"><a name="p1148402521117"></a><a name="p1148402521117"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p5779081021117"><a name="p5779081021117"></a><a name="p5779081021117"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p5054406521117"><a name="p5054406521117"></a><a name="p5054406521117"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r0c75e5ce18d44ea998aa935959656d78"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a3b84bb4fa94b47bca77c01e177233136"><a name="a3b84bb4fa94b47bca77c01e177233136"></a><a name="a3b84bb4fa94b47bca77c01e177233136"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="aacbe12ffc60d4349bcd771ea5adab2a1"><a name="aacbe12ffc60d4349bcd771ea5adab2a1"></a><a name="aacbe12ffc60d4349bcd771ea5adab2a1"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="af2902bee155b481bbe36519db6f753d3"><a name="af2902bee155b481bbe36519db6f753d3"></a><a name="af2902bee155b481bbe36519db6f753d3"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a4a7e22f4f9334640a32fa9e3e190832a"><a name="a4a7e22f4f9334640a32fa9e3e190832a"></a><a name="a4a7e22f4f9334640a32fa9e3e190832a"></a>Specifies the target UID.</p>
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

## 响应消息<a name="s40c3210a927d4400b708d17d3f0a3cbe"></a>

**响应参数：**

响应参数的详细描述请参见[表2](删除Secret.md#table13766144711235)。

**响应示例：**

```
{ 
   "kind": "Namespace", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "ry", 
     "selfLink": "/api/v1/namespaces/ry", 
     "uid": "3f585ca0-5a58-11e6-b444-286ed488fafe", 
     "resourceVersion": "289585", 
     "creationTimestamp": "2016-08-04T15:29:34Z", 
     "deletionTimestamp": "2016-08-04T15:29:50Z", 
     "labels": {
       "name": "development"
     }
   }, 
   "spec": { 
     "finalizers": [ 
       "kubernetes" 
     ] 
   }, 
   "status": { 
     "phase": "Terminating" 
   } 
 }
```

## 状态码<a name="s379564af9d9b4e6c915ee4629fc129e5"></a>

[表4](#zh-cn_topic_0079615060_table44048571)描述API的状态码。

**表 4**  状态码

<a name="zh-cn_topic_0079615060_table44048571"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615060_row48163256"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p4561445121117"><a name="p4561445121117"></a><a name="p4561445121117"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p378306821117"><a name="p378306821117"></a><a name="p378306821117"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615060_row4281684"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615060_p11272110"><a name="zh-cn_topic_0079615060_p11272110"></a><a name="zh-cn_topic_0079615060_p11272110"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615060_p40625737"><a name="zh-cn_topic_0079615060_p40625737"></a><a name="zh-cn_topic_0079615060_p40625737"></a>Delete a Namespace resource objectre successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

