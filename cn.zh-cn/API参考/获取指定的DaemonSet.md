# 获取指定的DaemonSet<a name="cce_02_0136"></a>

## 功能介绍<a name="section49931641"></a>

This API is used to read a DaemonSet object under a specified Namespace.

## URI<a name="section46731593"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/daemonsets/\{name\} \(Supports 1.9 and 1.9+\)

GET /apis/extensions/v1beta1/namespaces/\{namespace\}/daemonsets/\{name\} \(Compatible\)

[表1](#d0e32428)描述该API的参数。

**表 1**  参数描述

<a name="d0e32428"></a>
<table><thead align="left"><tr id="row9596482"><th class="cellrowborder" valign="top" width="18.18%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="64.64999999999999%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row46863169"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p37820334"><a name="p37820334"></a><a name="p37820334"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p43548195"><a name="p43548195"></a><a name="p43548195"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p37742921"><a name="p37742921"></a><a name="p37742921"></a>name of the DaemonSet</p>
</td>
</tr>
<tr id="row4141974"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p67064455"><a name="p67064455"></a><a name="p67064455"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p63511806"><a name="p63511806"></a><a name="p63511806"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p44182624"><a name="p44182624"></a><a name="p44182624"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row62099302"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p63987542"><a name="p63987542"></a><a name="p63987542"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p15608423"><a name="p15608423"></a><a name="p15608423"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p56322752"><a name="p56322752"></a><a name="p56322752"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row37142728"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p55770977"><a name="p55770977"></a><a name="p55770977"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p21155287"><a name="p21155287"></a><a name="p21155287"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p35856657"><a name="p35856657"></a><a name="p35856657"></a>Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="row54274459"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p34155063"><a name="p34155063"></a><a name="p34155063"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p15096715"><a name="p15096715"></a><a name="p15096715"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p14874432"><a name="p14874432"></a><a name="p14874432"></a>Should this value be exported.  Export strips fields that a user can not specify.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section17931154"></a>

N/A

## 响应消息<a name="section27162663"></a>

**响应参数：**

响应参数的详细说明请参见[表2](创建DaemonSet.md#d0e31376)。

**响应示例：**

```
{
    "kind": "DaemonSet",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "name": "ds-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/daemonsets/ds-12130306",
        "uid": "dc72a82b-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "419052",
        "generation": 1,
        "creationTimestamp": "2017-12-13T03:15:24Z",
        "labels": {
            "name": "daemonset-test"
        },
        "enable": true
    },
    "spec": {
        "selector": {
            "matchLabels": {
                "name": "daemonset-test"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "name": "daemonset-test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "dscon-12130306",
                        "image": "172.16.5.235:20202/test/redis:latest",
                        "resources": {},
                        "terminationMessagePath": "/dev/termination-log",
                        "terminationMessagePolicy": "File",
                        "imagePullPolicy": "IfNotPresent"
                    }
                ],
                "restartPolicy": "Always",
                "terminationGracePeriodSeconds": 30,
                "dnsPolicy": "ClusterFirst",
                "securityContext": {},
                "schedulerName": "default-scheduler"
            }
        },
        "updateStrategy": {
            "type": "OnDelete"
        },
        "templateGeneration": 1,
        "revisionHistoryLimit": 10
    },
    "status": {
        "currentNumberScheduled": 1,
        "numberMisscheduled": 0,
        "desiredNumberScheduled": 1,
        "numberReady": 1,
        "observedGeneration": 1,
        "updatedNumberScheduled": 1,
        "numberAvailable": 1
    }
}
```

## 状态码<a name="section43137375"></a>

[表2](#d0e32525)描述API的状态码。

**表 2**  状态码

<a name="d0e32525"></a>
<table><thead align="left"><tr id="row30213523"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p31376324"><a name="p31376324"></a><a name="p31376324"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p58454354"><a name="p58454354"></a><a name="p58454354"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row37182244"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p58971811"><a name="p58971811"></a><a name="p58971811"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11987382"><a name="p11987382"></a><a name="p11987382"></a>This operation succeeds, and a DaemonSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

