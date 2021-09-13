# 更新指定的Namespace<a name="cce_02_0057"></a>

## 功能介绍<a name="sc61ab07a6774411fb5e23e4e03f0e408"></a>

该API用于更新指定Namespace部分信息。

其中以下字段支持更新：

-   metadata.name
-   metadata.namespace
-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.uid
-   metadata.labels
-   metadata.generateName
-   metadata.annotations
-   metadata.deletionGracePeriodSeconds

## URI<a name="s5c4ede3df2254d4f9f948470a4167390"></a>

PATCH /api/v1/namespaces/\{name\}

[表1](#zh-cn_topic_0079614923_table59025204)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614923_table59025204"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614923_row63400648"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614923_p35178835"><a name="zh-cn_topic_0079614923_p35178835"></a><a name="zh-cn_topic_0079614923_p35178835"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p22220716201640"><a name="p22220716201640"></a><a name="p22220716201640"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p55047609201640"><a name="p55047609201640"></a><a name="p55047609201640"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614923_row19774328"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614923_p58216758"><a name="zh-cn_topic_0079614923_p58216758"></a><a name="zh-cn_topic_0079614923_p58216758"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614923_p17936932"><a name="zh-cn_topic_0079614923_p17936932"></a><a name="zh-cn_topic_0079614923_p17936932"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614923_p43605354"><a name="zh-cn_topic_0079614923_p43605354"></a><a name="zh-cn_topic_0079614923_p43605354"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614923_row56903870"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614923_p45810748"><a name="zh-cn_topic_0079614923_p45810748"></a><a name="zh-cn_topic_0079614923_p45810748"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614923_p19683111"><a name="zh-cn_topic_0079614923_p19683111"></a><a name="zh-cn_topic_0079614923_p19683111"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614923_p50828134"><a name="zh-cn_topic_0079614923_p50828134"></a><a name="zh-cn_topic_0079614923_p50828134"></a>Name of the Namespace.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s4d6a0dae909c4b3d800845ccdd482356"></a>

请求参数：

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/json-patch+json
[ 
 { 
     "op": "add", 
     "path": "/spec/finalizers/0", 
     "value": "kubernetes" 
 } 
 ]
```

## 响应消息<a name="s89a8214dd2d7407393601192524b8ada"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](创建Namespace.md#zh-cn_topic_0079615062_ref458675483)

**响应示例：**

```
{ 
   "kind": "Namespace", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "helloworld", 
     "selfLink": "/api/v1/namespaces/helloworld", 
     "uid": "1298d13a-5d34-11e6-aeb9-286ed488fafe", 
     "resourceVersion": "3043", 
     "creationTimestamp": "2016-08-08T06:48:11Z" 
   }, 
   "spec": { 
     "finalizers": [ 
       "kubernetes" 
     ] 
   }, 
   "status": { 
     "phase": "Active" 
   } 
 }
```

## 状态码<a name="s49d4dd78f7d2431d8a003bd92b596d76"></a>

[表2](#zh-cn_topic_0079614923_table61464796)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614923_table61464796"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614923_row24265995"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p6837280201640"><a name="p6837280201640"></a><a name="p6837280201640"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p16948825201640"><a name="p16948825201640"></a><a name="p16948825201640"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614923_row37389755"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614923_p8671305"><a name="zh-cn_topic_0079614923_p8671305"></a><a name="zh-cn_topic_0079614923_p8671305"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614923_p31287108"><a name="zh-cn_topic_0079614923_p31287108"></a><a name="zh-cn_topic_0079614923_p31287108"></a>This operation succeeds, and a Namespace resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

