# 创建ReplicationController<a name="cce_02_0016"></a>

## 功能介绍<a name="sf70db589a84041ef9dced29703222a45"></a>

该API用于创建ReplicationController资源类型。

## URI<a name="s58267715f43d4b4594c42fbc549c050c"></a>

POST /api/v1/namespaces/\{namespace\}/replicationcontrollers

[表1](#zh-cn_topic_0079615078_table29772226)  描述该API的参数。

**表 1**  参数说明

<a name="zh-cn_topic_0079615078_table29772226"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615078_row36286570"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615078_p53531063"><a name="zh-cn_topic_0079615078_p53531063"></a><a name="zh-cn_topic_0079615078_p53531063"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p2005499620266"><a name="p2005499620266"></a><a name="p2005499620266"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0079615078_p36623759"><a name="zh-cn_topic_0079615078_p36623759"></a><a name="zh-cn_topic_0079615078_p36623759"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615078_row13734506"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615078_p38753177"><a name="zh-cn_topic_0079615078_p38753177"></a><a name="zh-cn_topic_0079615078_p38753177"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615078_p51999621"><a name="zh-cn_topic_0079615078_p51999621"></a><a name="zh-cn_topic_0079615078_p51999621"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615078_p51219733"><a name="zh-cn_topic_0079615078_p51219733"></a><a name="zh-cn_topic_0079615078_p51219733"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615078_row36003682"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615078_p30617153"><a name="zh-cn_topic_0079615078_p30617153"></a><a name="zh-cn_topic_0079615078_p30617153"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615078_p64070324"><a name="zh-cn_topic_0079615078_p64070324"></a><a name="zh-cn_topic_0079615078_p64070324"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615078_p22313764"><a name="zh-cn_topic_0079615078_p22313764"></a><a name="zh-cn_topic_0079615078_p22313764"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079615078_ref458783257"></a>

**请求参数：**

请求参数的详细描述请参见[表1](公共请求参数.md#zh-cn_topic_0079614925_table51284307)。

**请求示例：**

```
{
    "kind": "ReplicationController",
    "apiVersion": "v1",
    "metadata": {
        "name": "frontend-controller",
        "labels": {
            "cce/group": "frontend-controller",
            "name": "frontend"
        }
    },
    "spec": {
        "replicas": 2,
        "selector": {
            "cce/group": "frontend-controller",
            "name": "frontend"
        },
        "template": {
            "metadata": {
                "labels": {
                    "cce/group": "frontend-controller",
                    "name": "frontend"
                }
            },
            "spec": {
                "volumes": null,
                "containers": [
                    {
                        "name": "php-redis",
                        "image": "redis",
                        "ports": [
                            {
                                "containerPort": 80,
                                "protocol": "TCP"
                            }
                        ],
                        "imagePullPolicy": "IfNotPresent"
                    }
                ],
                "restartPolicy": "Always",
                "dnsPolicy": "ClusterFirst"
            }
        }
    }
}
```

## 响应消息<a name="s17b1fd8a9c8c4bc3bcf3e05f795861c6"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079615078_ref458783257)。

**响应示例：**

```
{
    "apiVersion": "v1",
    "kind": "ReplicationController",
    "metadata": {
        "creationTimestamp": "2017-06-23T08:40:52Z",
        "generation": 1,
        "labels": {
            "cce/group": "frontend-controller",
            "name": "frontend"
        },
        "name": "frontend-controller",
        "namespace": "default",
        "resourceVersion": "850929",
        "selfLink": "/api/v1/namespaces/default/replicationcontrollers/frontend-controller",
        "uid": "aa123f3f-57ef-11e7-97f8-fa163e61f3f9"
    },
    "spec": {
        "replicas": 2,
        "selector": {
            "cce/group": "frontend-controller",
            "name": "frontend"
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "cce/group": "frontend-controller",
                    "name": "frontend"
                }
            },
            "spec": {
                "containers": [
                    {
                        "image": "redis",
                        "imagePullPolicy": "IfNotPresent",
                        "name": "php-redis",
                        "ports": [
                            {
                                "containerPort": 80,
                                "protocol": "TCP"
                            }
                        ],
                        "resources": {},
                        "terminationMessagePath": "/dev/termination-log"
                    }
                ],
                "dnsPolicy": "ClusterFirst",
                "restartPolicy": "Always",
                "securityContext": {},
                "terminationGracePeriodSeconds": 30
            }
        }
    },
    "status": {
        "availableReplicas": 2,
        "fullyLabeledReplicas": 2,
        "observedGeneration": 1,
        "readyReplicas": 2,
        "replicas": 2
    }
}
```

## 状态码<a name="s33091caa928947d0a6280827c903169a"></a>

[表2](#zh-cn_topic_0079615078_table66623444)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615078_table66623444"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615078_row62669098"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p1701330220266"><a name="p1701330220266"></a><a name="p1701330220266"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0079615078_p63055227"><a name="zh-cn_topic_0079615078_p63055227"></a><a name="zh-cn_topic_0079615078_p63055227"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615078_row7199758"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615078_p46309534"><a name="zh-cn_topic_0079615078_p46309534"></a><a name="zh-cn_topic_0079615078_p46309534"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615078_p60084754"><a name="zh-cn_topic_0079615078_p60084754"></a><a name="zh-cn_topic_0079615078_p60084754"></a>This operation succeeds, and a ReplicationController resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

