# 替换指定的Namespace的Finalize值<a name="cce_02_0055"></a>

## 功能介绍<a name="s5e1060eaef574f08a8dd061ec40e6157"></a>

该API用于替换指定Namespce的finalize的值。

## URI<a name="s7acf80d17ff84f0c9c2b7eb00f80eb00"></a>

PUT /api/v1/namespaces/\{name\}/finalize

[表1](#zh-cn_topic_0079615020_table40478462)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615020_table40478462"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615020_row34476226"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615020_p41110918"><a name="zh-cn_topic_0079615020_p41110918"></a><a name="zh-cn_topic_0079615020_p41110918"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p4951575721146"><a name="p4951575721146"></a><a name="p4951575721146"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p5135336221146"><a name="p5135336221146"></a><a name="p5135336221146"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615020_row66066743"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615020_p49805933"><a name="zh-cn_topic_0079615020_p49805933"></a><a name="zh-cn_topic_0079615020_p49805933"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615020_p7748772"><a name="zh-cn_topic_0079615020_p7748772"></a><a name="zh-cn_topic_0079615020_p7748772"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615020_p23670787"><a name="zh-cn_topic_0079615020_p23670787"></a><a name="zh-cn_topic_0079615020_p23670787"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615020_row12872118"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615020_p36008632"><a name="zh-cn_topic_0079615020_p36008632"></a><a name="zh-cn_topic_0079615020_p36008632"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615020_p31018066"><a name="zh-cn_topic_0079615020_p31018066"></a><a name="zh-cn_topic_0079615020_p31018066"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615020_p29435437"><a name="zh-cn_topic_0079615020_p29435437"></a><a name="zh-cn_topic_0079615020_p29435437"></a>Name of the Namespace.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079615020_ref458679422"></a>

请求参数：

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

## 响应消息<a name="s3398a68b6b4a4acea2b731d527a51b83"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079615020_ref458679422)。

**响应示例：**

```
{
    "kind": "Namespace",
    "apiVersion": "v1",
    "metadata": {
        "name": "test",
        "selfLink": "/api/v1/namespaces/test/finalize",
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

## 状态码<a name="s7e7c27ac6cea4d3da1df2bfdcf6c65f5"></a>

[表2](#zh-cn_topic_0079615020_table28761840)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615020_table28761840"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615020_row27551015"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p665304121146"><a name="p665304121146"></a><a name="p665304121146"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p202540921146"><a name="p202540921146"></a><a name="p202540921146"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615020_row61624137"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615020_p25499238"><a name="zh-cn_topic_0079615020_p25499238"></a><a name="zh-cn_topic_0079615020_p25499238"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615020_p52172387"><a name="zh-cn_topic_0079615020_p52172387"></a><a name="zh-cn_topic_0079615020_p52172387"></a>This operation succeeds, and a Namespace resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

