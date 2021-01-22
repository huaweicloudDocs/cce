# 更新指定的DaemonSet的状态<a name="cce_02_0140"></a>

## 功能介绍<a name="section12089840"></a>

This API is used to update the status of a specified DaemonSet object under a specified Namespace.

## URI<a name="section41699700"></a>

PATCH /apis/apps/v1/namespaces/\{namespace\}/daemonsets/\{name\}/status \(Supports 1.9 and 1.9+\)

PATCH /apis/extensions/v1beta1/namespaces/\{namespace\}/daemonsets/\{name\}/status \(Supports 1.15 and 1.15-\)

[表1](#d0e33741)描述该API的参数。

**表 1**  参数解释

<a name="d0e33741"></a>
<table><thead align="left"><tr id="row5939791"><th class="cellrowborder" valign="top" width="23.23%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="59.599999999999994%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row30425858"><td class="cellrowborder" valign="top" width="23.23%" headers="mcps1.2.4.1.1 "><p id="p48575428"><a name="p48575428"></a><a name="p48575428"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p42295582"><a name="p42295582"></a><a name="p42295582"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="59.599999999999994%" headers="mcps1.2.4.1.3 "><p id="p3390137"><a name="p3390137"></a><a name="p3390137"></a>name of the DaemonSet</p>
</td>
</tr>
<tr id="row30511238"><td class="cellrowborder" valign="top" width="23.23%" headers="mcps1.2.4.1.1 "><p id="p55491237"><a name="p55491237"></a><a name="p55491237"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p65605208"><a name="p65605208"></a><a name="p65605208"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="59.599999999999994%" headers="mcps1.2.4.1.3 "><p id="p12421640"><a name="p12421640"></a><a name="p12421640"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row44685898"><td class="cellrowborder" valign="top" width="23.23%" headers="mcps1.2.4.1.1 "><p id="p62787967"><a name="p62787967"></a><a name="p62787967"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p52660581"><a name="p52660581"></a><a name="p52660581"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.599999999999994%" headers="mcps1.2.4.1.3 "><p id="p37648675"><a name="p37648675"></a><a name="p37648675"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section39752982"></a>

**请求参数：**

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/merge-patch+json
[
    {
        "op": "add",
        "path": "/status/numberAvailable",
        "value": 2
    }
]
```

## 响应消息<a name="section22232519"></a>

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
        "resourceVersion": "419051",
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
        "numberAvailable": 2
    }
}
```

## 状态码<a name="section65874944"></a>

[表2](#d0e33836)描述API的状态码。

**表 2**  状态码

<a name="d0e33836"></a>
<table><thead align="left"><tr id="row3408639"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p7664333"><a name="p7664333"></a><a name="p7664333"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p16831240"><a name="p16831240"></a><a name="p16831240"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row21153175"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p35685603"><a name="p35685603"></a><a name="p35685603"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p4852691"><a name="p4852691"></a><a name="p4852691"></a>This operation succeeds, and a DaemonSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

