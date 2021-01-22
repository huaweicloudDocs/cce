# 更新指定的Deployment的伸缩操作<a name="cce_02_0131"></a>

## 功能介绍<a name="section62265761"></a>

This API is used to partially update scale of the specified Scale.

The following fields can be updated:

-   metadata.resourceVersion
-   metadata.creationTimestamp
-   spec.replicas

## URI<a name="section23520938"></a>

PATCH /apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\}/scale \(Supports 1.9 and 1.9+\)

PATCH /apis/apps/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/scale \(Supports only1.7\)

PATCH /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/scale \(Supports 1.15 and 1.15-\)

[表1](#d0e37306)描述该API的参数。

**表 1**  参数解释

<a name="d0e37306"></a>
<table><thead align="left"><tr id="row41369621"><th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="66.32336766323368%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row33508240"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p29812883"><a name="p29812883"></a><a name="p29812883"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p66033360"><a name="p66033360"></a><a name="p66033360"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p47101933"><a name="p47101933"></a><a name="p47101933"></a>name of the Scale</p>
</td>
</tr>
<tr id="row21264215"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p44679848"><a name="p44679848"></a><a name="p44679848"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p62297901"><a name="p62297901"></a><a name="p62297901"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p12965198"><a name="p12965198"></a><a name="p12965198"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row49577925"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p56389021"><a name="p56389021"></a><a name="p56389021"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p4107973"><a name="p4107973"></a><a name="p4107973"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p64310373"><a name="p64310373"></a><a name="p64310373"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section10361851"></a>

**请求参数：**

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/json-patch+json
[
    {
        "op": "add",
        "path": "/spec/replicas",
        "value": 2
    }
]
```

## 响应消息<a name="section26147797"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Deployment.md#table12862324102610)。

**响应示例：**

```
{
    "kind": "Scale",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "name": "deploy-ex-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/deployments/deploy-ex-12130306/scale",
        "uid": "934db57d-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "418857",
        "creationTimestamp": "2017-12-13T03:13:22Z"
    },
    "spec": {
        "replicas": 2
    },
    "status": {
        "replicas": 1,
        "selector": {
            "cce/appgroup": "deploy-ex-test"
        },
        "targetSelector": "cce/appgroup=deploy-ex-test"
    }
}
```

## 状态码<a name="section34003585"></a>

[表2](#d0e37399)描述API的状态码。

**表 2**  状态码

<a name="d0e37399"></a>
<table><thead align="left"><tr id="row19360173"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p24670187"><a name="p24670187"></a><a name="p24670187"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p52128170"><a name="p52128170"></a><a name="p52128170"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row61632274"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p26158282"><a name="p26158282"></a><a name="p26158282"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p38446074"><a name="p38446074"></a><a name="p38446074"></a>This operation succeeds, and a Deployment resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

