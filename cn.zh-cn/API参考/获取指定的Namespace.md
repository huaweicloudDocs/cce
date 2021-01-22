# 获取指定的Namespace<a name="cce_02_0052"></a>

## 功能介绍<a name="scf9d2368d0b84db5ada29db6edfd4bbd"></a>

该API用于获取指定的Namespace的详细信息。

## URI<a name="sb2f55ca34eb140d59a0949c9d56ac022"></a>

GET /api/v1/namespaces/\{name\}

[表1](#zh-cn_topic_0079614931_table56165728)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614931_table56165728"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614931_row20888703"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614931_p14263389"><a name="zh-cn_topic_0079614931_p14263389"></a><a name="zh-cn_topic_0079614931_p14263389"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.4.1.2"><p id="p20413034201629"><a name="p20413034201629"></a><a name="p20413034201629"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="46.464646464646464%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0079614931_p32345284"><a name="zh-cn_topic_0079614931_p32345284"></a><a name="zh-cn_topic_0079614931_p32345284"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614931_row2722332"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614931_p19182316"><a name="zh-cn_topic_0079614931_p19182316"></a><a name="zh-cn_topic_0079614931_p19182316"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614931_p10263773"><a name="zh-cn_topic_0079614931_p10263773"></a><a name="zh-cn_topic_0079614931_p10263773"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614931_p26059286"><a name="zh-cn_topic_0079614931_p26059286"></a><a name="zh-cn_topic_0079614931_p26059286"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614931_row33206990"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614931_p5411655"><a name="zh-cn_topic_0079614931_p5411655"></a><a name="zh-cn_topic_0079614931_p5411655"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614931_p35690909"><a name="zh-cn_topic_0079614931_p35690909"></a><a name="zh-cn_topic_0079614931_p35690909"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614931_p5282487"><a name="zh-cn_topic_0079614931_p5282487"></a><a name="zh-cn_topic_0079614931_p5282487"></a>Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated.</p>
</td>
</tr>
<tr id="re57ad01ee3a34ce8a3654fb86a2fda40"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="a63bd058863724e12b9d15146171392f0"><a name="a63bd058863724e12b9d15146171392f0"></a><a name="a63bd058863724e12b9d15146171392f0"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.4.1.2 "><p id="ae54f3dedf0af4ebfad7f25d07b720fa3"><a name="ae54f3dedf0af4ebfad7f25d07b720fa3"></a><a name="ae54f3dedf0af4ebfad7f25d07b720fa3"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614931_p398385119426"><a name="zh-cn_topic_0079614931_p398385119426"></a><a name="zh-cn_topic_0079614931_p398385119426"></a>Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="radf0b1c1f27e4c64ab4302c90a1be0e1"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="a6e0c1acd92cc45b38eb0423933ea7004"><a name="a6e0c1acd92cc45b38eb0423933ea7004"></a><a name="a6e0c1acd92cc45b38eb0423933ea7004"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.4.1.2 "><p id="aa87f0f2c7d234e6292a7f45884335324"><a name="aa87f0f2c7d234e6292a7f45884335324"></a><a name="aa87f0f2c7d234e6292a7f45884335324"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.4.1.3 "><p id="aae71f6e3574c4b11883d9f396d6b5924"><a name="aae71f6e3574c4b11883d9f396d6b5924"></a><a name="aae71f6e3574c4b11883d9f396d6b5924"></a>Should this value be exported. Export strips fields that a user can not specify.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sb8143102599b4bd19398ad00f0bcd799"></a>

N/A

## 响应消息<a name="sa8800f7e4a154473b712eb496a26a20a"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](创建Namespace.md#zh-cn_topic_0079615062_ref458675483)。

**响应示例：**

```
{
    "kind": "Namespace",
    "apiVersion": "v1",
    "metadata": {
        "name": "test",
        "selfLink": "/api/v1/namespaces/test",
        "uid": "00468bb2-fcef-11e7-9193-fa163ecdc4fd",
        "resourceVersion": "95092",
        "creationTimestamp": "2018-01-19T08:01:49Z",
        "labels": {
            "name": "test"
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

## 状态码<a name="s7e98581a81a84cc9b0ed724e05454b12"></a>

[表2](#zh-cn_topic_0079614931_table8575450)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614931_table8575450"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614931_row63149496"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p49872066201629"><a name="p49872066201629"></a><a name="p49872066201629"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0079614931_p60827539"><a name="zh-cn_topic_0079614931_p60827539"></a><a name="zh-cn_topic_0079614931_p60827539"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614931_row28083633"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614931_p60181840"><a name="zh-cn_topic_0079614931_p60181840"></a><a name="zh-cn_topic_0079614931_p60181840"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614931_p42890904"><a name="zh-cn_topic_0079614931_p42890904"></a><a name="zh-cn_topic_0079614931_p42890904"></a>This operation succeeds, and a Namespace resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

