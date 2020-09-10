# 替换指定ConfigMap<a name="cce_02_0173"></a>

## 功能介绍<a name="section63540285"></a>

This API is used to replace the specified ConfigMap.

## URI<a name="section34991658"></a>

PUT /api/v1/namespaces/\{namespace\}/configmaps/\{name\}

[表1](#d0e43866)描述该API的参数。

**表 1**  参数解释

<a name="d0e43866"></a>
<table><thead align="left"><tr id="row28873940"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row5943917"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p11695287"><a name="p11695287"></a><a name="p11695287"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p7794181"><a name="p7794181"></a><a name="p7794181"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p27348928"><a name="p27348928"></a><a name="p27348928"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row44813761"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p6036042"><a name="p6036042"></a><a name="p6036042"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p19157363"><a name="p19157363"></a><a name="p19157363"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p8242532"><a name="p8242532"></a><a name="p8242532"></a>name of the ConfigMap</p>
</td>
</tr>
<tr id="row7073927"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p36117240"><a name="p36117240"></a><a name="p36117240"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p39815366"><a name="p39815366"></a><a name="p39815366"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p3819224"><a name="p3819224"></a><a name="p3819224"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="d0e43915"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建ConfigMap.md#d0e42951)。

**请求示例：**

```
{
    "kind": "ConfigMap",
    "apiVersion": "v1",
    "metadata": {
        "name": "test-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/api/v1/namespaces/ns-12130306-s/configmaps/test-12130306",
        "uid": "efd6d9e0-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "419141",
        "creationTimestamp": "2017-12-13T03:15:57Z",
        "enable": true
    },
    "data": {
        "property_1": "new1"
    }
}
```

## 响应消息<a name="section15752039"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建ConfigMap.md#d0e42951)。

**响应示例：**

```
{
    "kind": "ConfigMap",
    "apiVersion": "v1",
    "metadata": {
        "name": "test-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/api/v1/namespaces/ns-12130306-s/configmaps/test-12130306",
        "uid": "efd6d9e0-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "419143",
        "creationTimestamp": "2017-12-13T03:15:57Z",
        "enable": true
    },
    "data": {
        "property_1": "new1"
    }
}
```

## 状态码<a name="section7550625"></a>

[表2](#d0e43958)描述API的状态码。

**表 2**  状态码

<a name="d0e43958"></a>
<table><thead align="left"><tr id="row63594840"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p50908388"><a name="p50908388"></a><a name="p50908388"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p29938789"><a name="p29938789"></a><a name="p29938789"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row9122883"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p756069"><a name="p756069"></a><a name="p756069"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p61241652"><a name="p61241652"></a><a name="p61241652"></a>This operation succeeds, and a ConfigMap resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

