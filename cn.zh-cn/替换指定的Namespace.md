# 替换指定的Namespace<a name="cce_02_0053"></a>

## 功能介绍<a name="se64c62bbc28a47689949a123d846c8ca"></a>

该API用于替换指定的Namespace的部分信息。

其中以下字段支持更新：

-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.generation
-   metadata.creationTimestamp
-   metadata.deletionTimestamp
-   metadata.labels
-   metadata.generateName
-   metadata.annotations

## URI<a name="sa913bc0ccab7450b8923451bf9f15c04"></a>

PUT /api/v1/namespaces/\{name\}

[表1](#zh-cn_topic_0079615038_table49444123)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615038_table49444123"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615038_row14601642"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615038_p41882373"><a name="zh-cn_topic_0079615038_p41882373"></a><a name="zh-cn_topic_0079615038_p41882373"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p13489349201632"><a name="p13489349201632"></a><a name="p13489349201632"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p18895455201632"><a name="p18895455201632"></a><a name="p18895455201632"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615038_row13608105"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615038_p28514710"><a name="zh-cn_topic_0079615038_p28514710"></a><a name="zh-cn_topic_0079615038_p28514710"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615038_p27990155"><a name="zh-cn_topic_0079615038_p27990155"></a><a name="zh-cn_topic_0079615038_p27990155"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615038_p52610097"><a name="zh-cn_topic_0079615038_p52610097"></a><a name="zh-cn_topic_0079615038_p52610097"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615038_row27655246"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615038_p25482430"><a name="zh-cn_topic_0079615038_p25482430"></a><a name="zh-cn_topic_0079615038_p25482430"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615038_p50810959"><a name="zh-cn_topic_0079615038_p50810959"></a><a name="zh-cn_topic_0079615038_p50810959"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615038_p22047016"><a name="zh-cn_topic_0079615038_p22047016"></a><a name="zh-cn_topic_0079615038_p22047016"></a>Name of the Namespace.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079615038_ref458676991"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建Namespace.md#zh-cn_topic_0079615062_ref458759029)。

**请求示例：**

```
{ 
   "apiVersion": "v1", 
     "kind": "Namespace", 
     "metadata": { 
         "name": "test", 
         "labels": { 
             "name": "test" 
         } 
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

## 响应消息<a name="s71d64222a34d4101aa1732e19c992943"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079615038_ref458676991)。

**响应示例：**

```
{
    "kind": "Namespace",
    "apiVersion": "v1",
    "metadata": {
        "name": "test",
        "selfLink": "/api/v1/namespaces/test",
        "uid": "00468bb2-fcef-11e7-9193-fa163ecdc4fd",
        "resourceVersion": "95099",
        "creationTimestamp": "2018-01-19T08:01:49Z",
        "labels": {
            "name": "test"
        },
        "annotations": {
            "test": "woil"
        },
        "enable": true
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

## 状态码<a name="sa1abf64108814721a77b395a50d806c0"></a>

[表2](#zh-cn_topic_0079615038_table42343927)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615038_table42343927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615038_row47812724"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p46755442201632"><a name="p46755442201632"></a><a name="p46755442201632"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p29094489201632"><a name="p29094489201632"></a><a name="p29094489201632"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615038_row11627434"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615038_p2298077"><a name="zh-cn_topic_0079615038_p2298077"></a><a name="zh-cn_topic_0079615038_p2298077"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615038_p51926520"><a name="zh-cn_topic_0079615038_p51926520"></a><a name="zh-cn_topic_0079615038_p51926520"></a>This operation succeeds, and a Namespace resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

