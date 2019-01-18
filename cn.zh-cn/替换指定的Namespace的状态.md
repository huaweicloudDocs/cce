# 替换指定的Namespace的状态<a name="cce_02_0054"></a>

## 功能介绍<a name="s78dfbbcdb6d145fa829c1398bdff12cb"></a>

该API用于更新指定Namespace的状态信息，即修改namespace对象status各字段的值。

当namespace.deletionTimestamp为空值时，phase只能配置为Active；

当namespace.deletionTimestamp不为空值时，phase只能配置为Terminating。

## URI<a name="se9bde8d3a3a34d63a0b229178d79fb98"></a>

PUT /api/v1/namespaces/\{name\}/status

[表1](#zh-cn_topic_0079615057_table45307656)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615057_table45307656"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615057_row38953736"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615057_p1136017"><a name="zh-cn_topic_0079615057_p1136017"></a><a name="zh-cn_topic_0079615057_p1136017"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p44972123201637"><a name="p44972123201637"></a><a name="p44972123201637"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p18863308201637"><a name="p18863308201637"></a><a name="p18863308201637"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615057_row14679294"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615057_p48172185"><a name="zh-cn_topic_0079615057_p48172185"></a><a name="zh-cn_topic_0079615057_p48172185"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615057_p9632925"><a name="zh-cn_topic_0079615057_p9632925"></a><a name="zh-cn_topic_0079615057_p9632925"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615057_p42069424"><a name="zh-cn_topic_0079615057_p42069424"></a><a name="zh-cn_topic_0079615057_p42069424"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615057_row51347269"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615057_p65488131"><a name="zh-cn_topic_0079615057_p65488131"></a><a name="zh-cn_topic_0079615057_p65488131"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615057_p2938434"><a name="zh-cn_topic_0079615057_p2938434"></a><a name="zh-cn_topic_0079615057_p2938434"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615057_p36686634"><a name="zh-cn_topic_0079615057_p36686634"></a><a name="zh-cn_topic_0079615057_p36686634"></a>Name of the Namespace.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079615057_ref458679189"></a>

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
             "openshift.com/origin", 
             "kubernetes" 
         ] 
     }, 
     "status": { 
         "phase": "Active" 
     } 
 }
```

## 响应消息<a name="s22137f9d150f4ebd8a284f006b9a87e9"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079615057_ref458679189)。

**响应示例：**

```
{
    "kind": "Namespace",
    "apiVersion": "v1",
    "metadata": {
        "name": "test",
        "selfLink": "/api/v1/namespaces/test/status",
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
        "phase": "Terminating"
    }
}
```

## 状态码<a name="sebf55a3e1af64b8abeda106aac36ac25"></a>

[表2](#zh-cn_topic_0079615057_table5115727)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615057_table5115727"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615057_row16339495"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p37586310201637"><a name="p37586310201637"></a><a name="p37586310201637"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p24592292201637"><a name="p24592292201637"></a><a name="p24592292201637"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615057_row60797095"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615057_p25617672"><a name="zh-cn_topic_0079615057_p25617672"></a><a name="zh-cn_topic_0079615057_p25617672"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615057_p61765553"><a name="zh-cn_topic_0079615057_p61765553"></a><a name="zh-cn_topic_0079615057_p61765553"></a>This operation succeeds, and a Namespace resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

