# 替换指定的Deployment的伸缩操作<a name="cce_02_0126"></a>

## 功能介绍<a name="section29254118"></a>

This API is used to replace scale of the specified Scale.

The following fields can be updated:

-   metadata.resourceVersion
-   metadata.creationTimestamp
-   spec.replicas

## URI<a name="section61960472"></a>

PUT /apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\}/scale \(Supports only1.9\)

PUT /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/scale \(Compatible\)

PUT /apis/apps/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/scale \(Supports only1.7\)

[表1](#d0e36373)描述该API的参数。

**表 1**  参数解释

<a name="d0e36373"></a>
<table><thead align="left"><tr id="row30327279"><th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="66.32336766323368%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row20449511"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p45797700"><a name="p45797700"></a><a name="p45797700"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p18626238"><a name="p18626238"></a><a name="p18626238"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p32330300"><a name="p32330300"></a><a name="p32330300"></a>name of the Scale</p>
</td>
</tr>
<tr id="row22537248"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p13577824"><a name="p13577824"></a><a name="p13577824"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p26061977"><a name="p26061977"></a><a name="p26061977"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p30645362"><a name="p30645362"></a><a name="p30645362"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row7372802"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p60326062"><a name="p60326062"></a><a name="p60326062"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p54572879"><a name="p54572879"></a><a name="p54572879"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p58327117"><a name="p58327117"></a><a name="p58327117"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section20773339"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建Deployment.md#table12862324102610)。

**请求示例：**

>![](public_sys-resources/icon-notice.gif) **注意：**   
>如果使用第一个URI：/apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\}/scale\(Supports only1.9\)，请将apiVersion的值修改为autoscaling/v1。  

```
{
    "kind": "Scale",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "name": "deploy-ex-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/deployments/deploy-ex-12130306/scale",
        "uid": "934db57d-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "418871",
        "creationTimestamp": "2017-12-13T03:13:22Z"
    },
    "spec": {
        "replicas": 1
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

## 响应消息<a name="section52742329"></a>

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
        "resourceVersion": "418903",
        "creationTimestamp": "2017-12-13T03:13:22Z"
    },
    "spec": {
        "replicas": 1
    },
    "status": {
        "replicas": 2,
        "selector": {
            "cce/appgroup": "deploy-ex-test"
        },
        "targetSelector": "cce/appgroup=deploy-ex-test"
    }
}
```

## 状态码<a name="section4918913"></a>

[表2](#d0e36462)描述API的状态码。

**表 2**  状态码

<a name="d0e36462"></a>
<table><thead align="left"><tr id="row53733915"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p57479854"><a name="p57479854"></a><a name="p57479854"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p25356606"><a name="p25356606"></a><a name="p25356606"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row40619186"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1819763"><a name="p1819763"></a><a name="p1819763"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p13183080"><a name="p13183080"></a><a name="p13183080"></a>This operation succeeds, and a Deployment resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

