# 列出指定Namespace下的ConfigMap<a name="cce_02_0174"></a>

## 功能介绍<a name="section28826295"></a>

This API is used to list all ConfigMap resource objects under a specified Namespace.

## URI<a name="section58110069"></a>

GET /api/v1/namespaces/\{namespace\}/configmaps

[表1](#d0e44025)描述该API的参数。

**表 1**  参数解释

<a name="d0e44025"></a>
<table><thead align="left"><tr id="row39963513"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="26%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="41%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row48716603"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p53730785"><a name="p53730785"></a><a name="p53730785"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p57226335"><a name="p57226335"></a><a name="p57226335"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p4821598"><a name="p4821598"></a><a name="p4821598"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row43394390"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p25284664"><a name="p25284664"></a><a name="p25284664"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p34791919"><a name="p34791919"></a><a name="p34791919"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p66682083"><a name="p66682083"></a><a name="p66682083"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row63267839"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p24421336"><a name="p24421336"></a><a name="p24421336"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p31971234"><a name="p31971234"></a><a name="p31971234"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p39533189"><a name="p39533189"></a><a name="p39533189"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row20254383"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p29992297"><a name="p29992297"></a><a name="p29992297"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p13456975"><a name="p13456975"></a><a name="p13456975"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p12241315"><a name="p12241315"></a><a name="p12241315"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row43062978"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p65549214"><a name="p65549214"></a><a name="p65549214"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p7886151"><a name="p7886151"></a><a name="p7886151"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p34798500"><a name="p34798500"></a><a name="p34798500"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="row44751050"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p956433"><a name="p956433"></a><a name="p956433"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p10362240"><a name="p10362240"></a><a name="p10362240"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p34035136"><a name="p34035136"></a><a name="p34035136"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row37880774"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p48443842"><a name="p48443842"></a><a name="p48443842"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p31637090"><a name="p31637090"></a><a name="p31637090"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p12467470"><a name="p12467470"></a><a name="p12467470"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row45098373"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p29089583"><a name="p29089583"></a><a name="p29089583"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p7446042"><a name="p7446042"></a><a name="p7446042"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p66258542"><a name="p66258542"></a><a name="p66258542"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section53228577"></a>

N/A

## 响应消息<a name="section9295148"></a>

**响应参数：**

响应参数的详细描述请参见[表4](公共响应参数.md#zh-cn_topic_0079614930_table6622802)。

**响应示例：**

```
{
    "kind": "ConfigMapList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/ns-12130306-s/configmaps",
        "resourceVersion": "419140"
    },
    "items": [
        {
            "metadata": {
                "name": "test-12130306",
                "namespace": "ns-12130306-s",
                "selfLink": "/api/v1/namespaces/ns-12130306-s/configmaps/test-12130306",
                "uid": "efd6d9e0-dfb3-11e7-9c19-fa163e2d897b",
                "resourceVersion": "419081",
                "creationTimestamp": "2017-12-13T03:15:57Z",
                "enable": true
            },
            "data": {
                "property_1": "test"
            }
        }
    ]
}
```

## 状态码<a name="section16547471"></a>

[表2](#d0e44156)描述API的状态码。

**表 2**  状态码

<a name="d0e44156"></a>
<table><thead align="left"><tr id="row36507281"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p4299803"><a name="p4299803"></a><a name="p4299803"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p12739753"><a name="p12739753"></a><a name="p12739753"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row25287076"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p34987251"><a name="p34987251"></a><a name="p34987251"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p15395071"><a name="p15395071"></a><a name="p15395071"></a>This operation succeeds, and a group of ConfigMap resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

