# 创建Pod<a name="cce_02_0034"></a>

## 功能介绍<a name="scc86678262934086bfbe32385da35788"></a>

该API用于在指定Namespace下创建一个Pod对象。

## URI<a name="s83bc1fb06185462cb2e2665b169bc85c"></a>

POST /api/v1/namespaces/\{namespace\}/pods

[表1](#zh-cn_topic_0079615001_table32114614)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615001_table32114614"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615001_row42303331"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615001_p4017754"><a name="zh-cn_topic_0079615001_p4017754"></a><a name="zh-cn_topic_0079615001_p4017754"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p27173000203043"><a name="p27173000203043"></a><a name="p27173000203043"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p53529377203043"><a name="p53529377203043"></a><a name="p53529377203043"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615001_row63986108"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615001_p15492278"><a name="zh-cn_topic_0079615001_p15492278"></a><a name="zh-cn_topic_0079615001_p15492278"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615001_p46914996"><a name="zh-cn_topic_0079615001_p46914996"></a><a name="zh-cn_topic_0079615001_p46914996"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615001_p42018335"><a name="zh-cn_topic_0079615001_p42018335"></a><a name="zh-cn_topic_0079615001_p42018335"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615001_row29042598"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615001_p3640263"><a name="zh-cn_topic_0079615001_p3640263"></a><a name="zh-cn_topic_0079615001_p3640263"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615001_p26425925"><a name="zh-cn_topic_0079615001_p26425925"></a><a name="zh-cn_topic_0079615001_p26425925"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615001_p60125191"><a name="zh-cn_topic_0079615001_p60125191"></a><a name="zh-cn_topic_0079615001_p60125191"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079615001_d0e16631"></a>

**请求参数：**

请求参数的详细描述请参见[表3](请求数据结构.md#zh-cn_topic_0079614925_table60388168)。

**请求示例：**

```
{
    "apiVersion": "v1",
    "kind": "Pod",
    "metadata": {
        "labels": {
            "name": "pod-test"
        },
        "name": "pod-test"
    },
    "spec": {
        "containers": [
            {
                "image": "nginx:alpine",
                "imagePullPolicy": "Always",
                "name": "test",
                "resources": {
                    "requests": {
                        "cpu": "100m"
                    }
                }
            }
        ],
        "imagePullSecrets": [
            {
                "name": "default-secret"
            }
        ],
        "restartPolicy": "Always"
    }
}
```

## 响应消息<a name="s23649bc4d7154135b7153a5743022fcd"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079615001_d0e16631)。

**响应示例：**

```
{
    "kind": "Pod",
    "apiVersion": "v1",
    "metadata": {
        "name": "pod-test",
        "namespace": "development",
        "selfLink": "/api/v1/namespaces/development/pods/pod-test",
        "uid": "6f4ed218-b737-4466-981e-be231a631718",
        "resourceVersion": "10203",
        "creationTimestamp": "2021-10-14T01:47:36Z",
        "labels": {
            "name": "pod-test"
        },
        "annotations": {
            "kubernetes.io/psp": "psp-global"
        }
    },
    "spec": {
        "volumes": [
            {
                "name": "default-token-ddq7k",
                "secret": {
                    "secretName": "default-token-ddq7k",
                    "defaultMode": 420
                }
            }
        ],
        "containers": [
            {
                "name": "test",
                "image": "nginx:alpine",
                "resources": {
                    "requests": {
                        "cpu": "100m"
                    }
                },
                "volumeMounts": [
                    {
                        "name": "default-token-ddq7k",
                        "readOnly": true,
                        "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount"
                    }
                ],
                "terminationMessagePath": "/dev/termination-log",
                "terminationMessagePolicy": "File",
                "imagePullPolicy": "Always"
            }
        ],
        "restartPolicy": "Always",
        "terminationGracePeriodSeconds": 30,
        "dnsPolicy": "ClusterFirst",
        "serviceAccountName": "default",
        "serviceAccount": "default",
        "securityContext": {},
        "imagePullSecrets": [
            {
                "name": "default-secret"
            }
        ],
        "schedulerName": "default-scheduler",
        "tolerations": [
            {
                "key": "node.kubernetes.io/not-ready",
                "operator": "Exists",
                "effect": "NoExecute",
                "tolerationSeconds": 300
            },
            {
                "key": "node.kubernetes.io/unreachable",
                "operator": "Exists",
                "effect": "NoExecute",
                "tolerationSeconds": 300
            }
        ],
        "priority": 0,
        "dnsConfig": {
            "options": [
                {
                    "name": "single-request-reopen",
                    "value": ""
                },
                {
                    "name": "timeout",
                    "value": "2"
                }
            ]
        },
        "enableServiceLinks": true,
        "preemptionPolicy": "PreemptLowerPriority"
    },
    "status": {
        "phase": "Pending",
        "qosClass": "Burstable"
    }
}
```

## 状态码<a name="sbb2d9f14fc4a4197a3a609e7c568ab4d"></a>

[表2](#zh-cn_topic_0079615001_table20596071)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615001_table20596071"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615001_row9746163"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p57545694203043"><a name="p57545694203043"></a><a name="p57545694203043"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p30689603203043"><a name="p30689603203043"></a><a name="p30689603203043"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615001_row48621261"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615001_p46008046"><a name="zh-cn_topic_0079615001_p46008046"></a><a name="zh-cn_topic_0079615001_p46008046"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615001_p35664277"><a name="zh-cn_topic_0079615001_p35664277"></a><a name="zh-cn_topic_0079615001_p35664277"></a>This operation succeeds, and a Pod resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

