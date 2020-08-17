# 更新指定的Deployment<a name="cce_02_0129"></a>

## 功能介绍<a name="section59866645"></a>

This API is used to update a Deployment object under a specific Namespace.

The following fields can be updated:

-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.generation
-   metadata.creationTimestamp
-   metadata.deletionTimestamp
-   metadata.labels
-   metadata.clusterName
-   metadata.generateName
-   metadata.annotations
-   spec.replicas
-   template.contaions
-   spec.restartPolicy
-   spec.activeDeadlineSeconds

## URI<a name="section1928895"></a>

PATCH /apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\} \(Supports 1.9 and 1.9+\)

PATCH /apis/apps/v1beta1/namespaces/\{namespace\}/deployments/\{name\} \(Supports only1.7\)

PATCH /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments/\{name\} \(Compatible\)

[表1](#d0e36967)描述该API的参数。

**表 1**  参数解释

<a name="d0e36967"></a>
<table><thead align="left"><tr id="row62299817"><th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="66.32336766323368%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row28278868"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p8886982"><a name="p8886982"></a><a name="p8886982"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p48756965"><a name="p48756965"></a><a name="p48756965"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p57000088"><a name="p57000088"></a><a name="p57000088"></a>name of the DaemonSet</p>
</td>
</tr>
<tr id="row43238749"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p12677770"><a name="p12677770"></a><a name="p12677770"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p20266431"><a name="p20266431"></a><a name="p20266431"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p30968229"><a name="p30968229"></a><a name="p30968229"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row10278610"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p27261059"><a name="p27261059"></a><a name="p27261059"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p60662202"><a name="p60662202"></a><a name="p60662202"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p14691292"><a name="p14691292"></a><a name="p14691292"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section17360061"></a>

**请求参数：**

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例1，使用json-patch类型：**

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

**请求示例2，使用merge-patch类型：**

```
Content-Type: application/merge-patch+json
{
    "spec": {
        "template": {
            "spec": {
                "containers": [
                    {
                        "name": "deploycon-12130306",
                        "image": "172.16.5.235:20202/test/redis:latest"
                    }
                ]
            }
        }
    }
}
```

**请求示例3，使用strategic-merge-patch类型：**

```
Content-Type: application/strategic-merge-patch+json
{
    "spec": {
        "template": {
            "spec": {
                "containers": [
                    {
                        "name": "deploycon-12130306",
                    }
                ]
            }
        }
    }
}
```

## 响应消息<a name="section22022822"></a>

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
        "selfLink": "/apis/apps/v1beta1/namespaces/ns-12130306-s/deployments/deploy-12130306",
        "uid": "27072a31-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "418470",
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

## 状态码<a name="section63987677"></a>

[表2](#d0e37060)描述API的状态码。

**表 2**  状态码

<a name="d0e37060"></a>
<table><thead align="left"><tr id="row44413743"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p40743437"><a name="p40743437"></a><a name="p40743437"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p11884140"><a name="p11884140"></a><a name="p11884140"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row23091316"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p58457292"><a name="p58457292"></a><a name="p58457292"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p37420188"><a name="p37420188"></a><a name="p37420188"></a>This operation succeeds, and a Deployment resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

