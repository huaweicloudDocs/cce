# 更新指定的DaemonSet<a name="cce_02_0139"></a>

## 功能介绍<a name="section3515545"></a>

This API is used to update a DaemonSet object under a specific Namespace.

The following fields can be updated:

-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.labels
-   spec.selector
-   spec.template.spec.containers
-   spec.templateGeneration
-   spec.revisionHistoryLimit

The other fields cannot be updated.

## URI<a name="section31639905"></a>

PATCH /apis/apps/v1/namespaces/\{namespace\}/daemonsets/\{name\} （适用于1.9及以上版本的所有集群）

PATCH /apis/extensions/v1beta1/namespaces/\{namespace\}/daemonsets/\{name\} （仅适用于1.15及以下版本的集群）

[表1](#d0e33576)描述该API的参数。

**表 1**  参数解释

<a name="d0e33576"></a>
<table><thead align="left"><tr id="row63400708"><th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="66.32336766323368%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49750336"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p3245433"><a name="p3245433"></a><a name="p3245433"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p61553490"><a name="p61553490"></a><a name="p61553490"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p19776755"><a name="p19776755"></a><a name="p19776755"></a>name of the DaemonSet</p>
</td>
</tr>
<tr id="row43773070"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p55957807"><a name="p55957807"></a><a name="p55957807"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p36288557"><a name="p36288557"></a><a name="p36288557"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p53692015"><a name="p53692015"></a><a name="p53692015"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row13466094"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p17011793"><a name="p17011793"></a><a name="p17011793"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p35778030"><a name="p35778030"></a><a name="p35778030"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p12339307"><a name="p12339307"></a><a name="p12339307"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section16323694"></a>

**请求参数：**

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/json-patch+json
[
    {
        "op": "add",
        "path": "/spec/template/spec/containers/0/image",
        "value": "172.16.5.235:20202/test/redis:latest"
    }
]
```

## 响应消息<a name="section12695519"></a>

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
        "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/daemonsets/ds-12130306",
        "uid": "dc72a82b-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "419012",
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

## 状态码<a name="section47150815"></a>

[表2](#d0e33671)描述API的状态码。

**表 2**  状态码

<a name="d0e33671"></a>
<table><thead align="left"><tr id="row63854776"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p4854401"><a name="p4854401"></a><a name="p4854401"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p57662206"><a name="p57662206"></a><a name="p57662206"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row40127128"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p29071926"><a name="p29071926"></a><a name="p29071926"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p6015809"><a name="p6015809"></a><a name="p6015809"></a>This operation succeeds, and a DaemonSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

