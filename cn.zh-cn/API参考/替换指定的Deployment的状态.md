# 替换指定的Deployment的状态<a name="cce_02_0125"></a>

## 功能介绍<a name="section66253823"></a>

This API is used to replace the status of a specified Deployment object under a specified Namespace, that is, to modify the value of the status field of the Deployment object.

## URI<a name="section59413503"></a>

PUT /apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\}/status （适用于1.9及以上版本的所有集群）

PUT /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/status （仅适用于1.15及以下版本的集群）

[表1](#d0e36203)描述该API的参数。

**表 1**  参数解释

<a name="d0e36203"></a>
<table><thead align="left"><tr id="row36263752"><th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="65.3034696530347%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row38698441"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p47565978"><a name="p47565978"></a><a name="p47565978"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.2 "><p id="p27639004"><a name="p27639004"></a><a name="p27639004"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="65.3034696530347%" headers="mcps1.2.4.1.3 "><p id="p24166838"><a name="p24166838"></a><a name="p24166838"></a>name of the Deployment</p>
</td>
</tr>
<tr id="row16174956"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p35103070"><a name="p35103070"></a><a name="p35103070"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.2 "><p id="p24776445"><a name="p24776445"></a><a name="p24776445"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="65.3034696530347%" headers="mcps1.2.4.1.3 "><p id="p60735024"><a name="p60735024"></a><a name="p60735024"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row9744309"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p51091554"><a name="p51091554"></a><a name="p51091554"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.2 "><p id="p44775191"><a name="p44775191"></a><a name="p44775191"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="65.3034696530347%" headers="mcps1.2.4.1.3 "><p id="p2911869"><a name="p2911869"></a><a name="p2911869"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section64959481"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建Deployment.md#table12862324102610)。

**请求示例：**

```
{
    "kind": "Deployment",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "name": "deploy-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/apps/v1beta1/namespaces/ns-12130306-s/deployments/deploy-12130306/status",
        "uid": "27072a31-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "418598",
        "generation": 2,
        "creationTimestamp": "2017-12-13T03:10:20Z",
        "labels": {
            "cce/appgroup": "deploy_test"
        },
        "annotations": {
            "deployment.kubernetes.io/revision": "1"
        },
        "enable": true
    },
    "spec": {
        "replicas": 1,
        "selector": {
            "matchLabels": {
                "cce/appgroup": "deploy_test"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "cce/appgroup": "deploy_test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "deploycon-12130306",
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
        "strategy": {
            "type": "RollingUpdate",
            "rollingUpdate": {
                "maxUnavailable": "25%",
                "maxSurge": "25%"
            }
        },
        "revisionHistoryLimit": 2,
        "progressDeadlineSeconds": 600
    },
    "status": {
        "observedGeneration": 2,
        "replicas": 1,
        "updatedReplicas": 1,
        "readyReplicas": 1,
        "availableReplicas": 1,
        "conditions": [
            {
                "type": "Progressing",
                "status": "True",
                "lastUpdateTime": "2017-12-13T03:10:20Z",
                "lastTransitionTime": "2017-12-13T03:10:20Z",
                "reason": "NewReplicaSetAvailable",
                "message": "ReplicaSet \"deploy-12130306-3417241766\" has successfully progressed."
            },
            {
                "type": "Available",
                "status": "True",
                "lastUpdateTime": "2017-12-13T03:10:23Z",
                "lastTransitionTime": "2017-12-13T03:10:23Z",
                "reason": "MinimumReplicasAvailable",
                "message": "Deployment has minimum availability."
            }
        ]
    }
}
```

## 响应消息<a name="section47764424"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Deployment.md#table12862324102610)。

**响应示例：**

```
{
    "kind": "Deployment",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "name": "deploy-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/apps/v1beta1/namespaces/ns-12130306-s/deployments/deploy-12130306/status",
        "uid": "27072a31-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "418632",
        "generation": 2,
        "creationTimestamp": "2017-12-13T03:10:20Z",
        "labels": {
            "cce/appgroup": "deploy_test"
        },
        "annotations": {
            "deployment.kubernetes.io/revision": "1"
        },
        "enable": true
    },
    "spec": {
        "replicas": 1,
        "selector": {
            "matchLabels": {
                "cce/appgroup": "deploy_test"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "cce/appgroup": "deploy_test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "deploycon-12130306",
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
        "strategy": {
            "type": "RollingUpdate",
            "rollingUpdate": {
                "maxUnavailable": "25%",
                "maxSurge": "25%"
            }
        },
        "revisionHistoryLimit": 2,
        "progressDeadlineSeconds": 600
    },
    "status": {
        "observedGeneration": 2,
        "replicas": 1,
        "updatedReplicas": 1,
        "readyReplicas": 1,
        "availableReplicas": 1,
        "conditions": [
            {
                "type": "Progressing",
                "status": "True",
                "lastUpdateTime": "2017-12-13T03:10:20Z",
                "lastTransitionTime": "2017-12-13T03:10:20Z",
                "reason": "NewReplicaSetAvailable",
                "message": "ReplicaSet \"deploy-12130306-3417241766\" has successfully progressed."
            },
            {
                "type": "Available",
                "status": "True",
                "lastUpdateTime": "2017-12-13T03:10:23Z",
                "lastTransitionTime": "2017-12-13T03:10:23Z",
                "reason": "MinimumReplicasAvailable",
                "message": "Deployment has minimum availability."
            }
        ]
    }
}
```

## 状态码<a name="section27226636"></a>

[表2](#d0e36292)描述API的状态码。

**表 2**  状态码

<a name="d0e36292"></a>
<table><thead align="left"><tr id="row17111977"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p43892873"><a name="p43892873"></a><a name="p43892873"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p65661834"><a name="p65661834"></a><a name="p65661834"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row17008339"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p35498253"><a name="p35498253"></a><a name="p35498253"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p56786272"><a name="p56786272"></a><a name="p56786272"></a>This operation succeeds, and a Deployment resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

