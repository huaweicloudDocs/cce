# 更新指定的ConfigMap<a name="cce_02_0176"></a>

## 功能介绍<a name="section62552745"></a>

This API is used to update the specified ConfigMap.

The following fields can be updated:

-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.generation
-   metadata.creationTimestamp
-   metadata.deletionTimestamp
-   metadata.labels
-   metadata.clusterName
-   metadata.generateName
-   metadata.annotations
-   spec.replicas
-   spec.restartPolicy
-   spec.activeDeadlineSeconds

## URI<a name="section26103793"></a>

PATCH /api/v1/namespaces/\{namespace\}/configmaps/\{name\}

[表1](#d0e44438)描述该API的参数。

**表 1**  参数解释

<a name="d0e44438"></a>
<table><thead align="left"><tr id="row33489305"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.61%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row14067825"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p65752073"><a name="p65752073"></a><a name="p65752073"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p24317681"><a name="p24317681"></a><a name="p24317681"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p23575121"><a name="p23575121"></a><a name="p23575121"></a>name of the Job</p>
</td>
</tr>
<tr id="row10849502"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p6394470"><a name="p6394470"></a><a name="p6394470"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p48190075"><a name="p48190075"></a><a name="p48190075"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p11081988"><a name="p11081988"></a><a name="p11081988"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row32629032"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p25705915"><a name="p25705915"></a><a name="p25705915"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p1804342"><a name="p1804342"></a><a name="p1804342"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p11934018"><a name="p11934018"></a><a name="p11934018"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section33607552"></a>

**请求参数：**

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/merge-patch+json
```

```
{
    "data": {
        "property_1": "new"
    }
}
```

## 响应消息<a name="section34032518"></a>

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
        "resourceVersion": "419141",
        "creationTimestamp": "2017-12-13T03:15:57Z",
        "enable": true
    },
    "data": {
        "property_1": "new"
    }
}
```

## 状态码<a name="section37857212"></a>

[表2](#d0e44533)描述API的状态码。

**表 2**  状态码

<a name="d0e44533"></a>
<table><thead align="left"><tr id="row14217584"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p10773671"><a name="p10773671"></a><a name="p10773671"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p252187"><a name="p252187"></a><a name="p252187"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row20427187"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p43989464"><a name="p43989464"></a><a name="p43989464"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p6376817"><a name="p6376817"></a><a name="p6376817"></a>This operation succeeds, and a ConfigMap resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

