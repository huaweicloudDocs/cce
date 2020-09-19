# 更新指定的StatefulSet的状态<a name="cce_02_0155"></a>

## 功能介绍<a name="section6571668"></a>

This API is used to update the status of a specified StatefulSet object under a specified Namespace.

## URI<a name="section59145013"></a>

PATCH /apis/apps/v1/namespaces/\{namespace\}/statefulsets/\{name\}/status \(Supports 1.9 and 1.9+\)

PATCH /apis/apps/v1beta1/namespaces/\{namespace\}/statefulsets/\{name\}/status \(Supports 1.15 and 1.15-\)

[表1](#d0e39989)描述该API的参数。

**表 1**  参数解释

<a name="d0e39989"></a>
<table><thead align="left"><tr id="row47640502"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.15%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="62.629999999999995%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13407109"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p12234054"><a name="p12234054"></a><a name="p12234054"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p51434319"><a name="p51434319"></a><a name="p51434319"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p5430345"><a name="p5430345"></a><a name="p5430345"></a>Name of the StatefulSet.</p>
</td>
</tr>
<tr id="row48873112"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p66407998"><a name="p66407998"></a><a name="p66407998"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p10338728"><a name="p10338728"></a><a name="p10338728"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p32130622"><a name="p32130622"></a><a name="p32130622"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row20740150"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p2230586"><a name="p2230586"></a><a name="p2230586"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p46459807"><a name="p46459807"></a><a name="p46459807"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p5148045"><a name="p5148045"></a><a name="p5148045"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section62543072"></a>

**请求参数：**

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/json-patch+json
```

```
[
    {
        "op": "replace",
        "path": "/status/replicas",
        "value": 3
    }
]
```

## 响应消息<a name="section26016743"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建StatefulSet.md#d0e37568)。

**响应示例：**

```
{
    "kind": "StatefulSet",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "name": "numberlimit",
        "generateName": "sz",
        "namespace": "default",
        "selfLink": "/apis/apps/v1beta1/namespaces/default/statefulsets/numberlimit/status",
        "uid": "841f6be1-2a25-11e7-a2a3-fa163e3a4289",
        "resourceVersion": "1399731",
        "generation": 3,
        "creationTimestamp": "2017-04-26T02:10:27Z",
        "labels": {
            "app": "mysql"
        }
    },
    "spec": {
        "replicas": 1,
        "selector": {
            "matchLabels": {
                "app": "mysql"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "app": "mysql"
                }
            },
            "spec": {
                "containers": [
                    {
                        "name": "container01",
                        "image": "10.154.52.159:443/test/mongo:latest",
                        "ports": [
                            {
                                "containerPort": 80,
                                "protocol": "TCP"
                            }
                        ],
                        "resources": {
                            "limits": {
                                "cpu": "99M"
                            },
                            "requests": {
                                "cpu": "300M"
                            }
                        },
                        "terminationMessagePath": "/dev/termination-log",
                        "imagePullPolicy": "IfNotPresent"
                    }
                ],
                "restartPolicy": "Always",
                "terminationGracePeriodSeconds": 30,
                "dnsPolicy": "ClusterFirst",
                "securityContext": {}
            }
        },
        "serviceName": "service-number"
    },
    "status": {
        "replicas": 3
    }
}
```

## 状态码<a name="section32824097"></a>

[表2](#d0e40081)描述API的状态码。

**表 2**  状态码

<a name="d0e40081"></a>
<table><thead align="left"><tr id="row63565442"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p48527143"><a name="p48527143"></a><a name="p48527143"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p38384488"><a name="p38384488"></a><a name="p38384488"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row22135855"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p48173793"><a name="p48173793"></a><a name="p48173793"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9763176"><a name="p9763176"></a><a name="p9763176"></a>This operation succeeds, and a StatefulSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

