# 获取指定的DaemonSet的状态<a name="cce_02_0137"></a>

## 功能介绍<a name="section8900016"></a>

This API is used to read the status of a specified DaemonSet object under a specified Namespace.

## URI<a name="section12991283"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/daemonsets/\{name\}/status \(Supports 1.9 and 1.9+\)

GET /apis/extensions/v1beta1/namespaces/\{namespace\}/daemonsets/\{name\}/status \(Supports 1.15 and 1.15-\)

[表1](#d0e32595)描述该API的参数。

**表 1**  参数解释

<a name="d0e32595"></a>
<table><thead align="left"><tr id="row42328115"><th class="cellrowborder" valign="top" width="18.36816318368163%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="65.3034696530347%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row7083912"><td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.4.1.1 "><p id="p36926006"><a name="p36926006"></a><a name="p36926006"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p38216549"><a name="p38216549"></a><a name="p38216549"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="65.3034696530347%" headers="mcps1.2.4.1.3 "><p id="p8532797"><a name="p8532797"></a><a name="p8532797"></a>name of the DaemonSet</p>
</td>
</tr>
<tr id="row9686311"><td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.4.1.1 "><p id="p46393742"><a name="p46393742"></a><a name="p46393742"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p66905650"><a name="p66905650"></a><a name="p66905650"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="65.3034696530347%" headers="mcps1.2.4.1.3 "><p id="p50648570"><a name="p50648570"></a><a name="p50648570"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row53183951"><td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.4.1.1 "><p id="p12932809"><a name="p12932809"></a><a name="p12932809"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p40924636"><a name="p40924636"></a><a name="p40924636"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="65.3034696530347%" headers="mcps1.2.4.1.3 "><p id="p26561199"><a name="p26561199"></a><a name="p26561199"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section49812686"></a>

N/A

## 响应消息<a name="section45660994"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建DaemonSet.md#d0e31376)。

**响应示例：**

```
{
    "kind": "DaemonSet",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "name": "ds-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/daemonsets/ds-12130306/status",
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

## 状态码<a name="section8295769"></a>

[表2](#d0e32673)描述API的状态码。

**表 2**  状态码

<a name="d0e32673"></a>
<table><thead align="left"><tr id="row56897427"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p45288850"><a name="p45288850"></a><a name="p45288850"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p44518222"><a name="p44518222"></a><a name="p44518222"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49206190"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p26278426"><a name="p26278426"></a><a name="p26278426"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p48177787"><a name="p48177787"></a><a name="p48177787"></a>This operation succeeds, and a DaemonSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

