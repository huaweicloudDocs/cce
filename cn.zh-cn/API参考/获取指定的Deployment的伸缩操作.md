# 获取指定的Deployment的伸缩操作<a name="cce_02_0124"></a>

## 功能介绍<a name="section47779875"></a>

This API is used to read scale of the specified Scale.

## URI<a name="section27365698"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\}/scale \(Supports 1.9 and 1.9+\)

GET /apis/apps/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/scale \(Supports only1.7\)

GET /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/scale \(Compatible\)

[表1](#d0e35851)描述该API的参数。

**表 1**  参数解释

<a name="d0e35851"></a>
<table><thead align="left"><tr id="row23454267"><th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="66.32336766323368%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row8437627"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.1 "><p id="p12359162"><a name="p12359162"></a><a name="p12359162"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.2 "><p id="p61568054"><a name="p61568054"></a><a name="p61568054"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p20956438"><a name="p20956438"></a><a name="p20956438"></a>name of the Scale</p>
</td>
</tr>
<tr id="row54390215"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.1 "><p id="p43531289"><a name="p43531289"></a><a name="p43531289"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.2 "><p id="p36373507"><a name="p36373507"></a><a name="p36373507"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p60572974"><a name="p60572974"></a><a name="p60572974"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row8285859"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.1 "><p id="p66002"><a name="p66002"></a><a name="p66002"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.2 "><p id="p5346197"><a name="p5346197"></a><a name="p5346197"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p30388821"><a name="p30388821"></a><a name="p30388821"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section44964695"></a>

N/A

## 响应消息<a name="section2029075"></a>

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
        "resourceVersion": "418871",
        "creationTimestamp": "2017-12-13T03:13:22Z"
    },
    "spec": {
        "replicas": 2
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

## 状态码<a name="section18261679"></a>

[表2](#d0e35928)描述API的状态码。

**表 2**  状态码

<a name="d0e35928"></a>
<table><thead align="left"><tr id="row52906506"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p57568585"><a name="p57568585"></a><a name="p57568585"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p32543833"><a name="p32543833"></a><a name="p32543833"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18804834"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p46796555"><a name="p46796555"></a><a name="p46796555"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p32424572"><a name="p32424572"></a><a name="p32424572"></a>This operation succeeds, and a Deployment resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

