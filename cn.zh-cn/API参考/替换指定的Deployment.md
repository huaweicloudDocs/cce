# 替换指定的Deployment<a name="cce_02_0097"></a>

## 功能介绍<a name="section172959268501"></a>

该API用于替换指定的Deployment对象。

其中以下字段支持更新：

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

## URI<a name="section1524832914503"></a>

PUT /apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\} \(Supports only1.9\)

PUT /apis/apps/v1beta1/namespaces/\{namespace\}/deployments/\{name\} \(Supports only1.7\)

PUT /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments/\{name\} \(Compatible\)

[表1](#table14970324122818)描述该API的参数

**表 1**  参数

<a name="table14970324122818"></a>
<table><thead align="left"><tr id="row0971162417289"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="a976d4718ebbf43e691f355b454666ba3"><a name="a976d4718ebbf43e691f355b454666ba3"></a><a name="a976d4718ebbf43e691f355b454666ba3"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.4.1.2"><p id="p6151164282819"><a name="p6151164282819"></a><a name="p6151164282819"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="56.99999999999999%" id="mcps1.2.4.1.3"><p id="p21518421288"><a name="p21518421288"></a><a name="p21518421288"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row83198295289"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p153191729102818"><a name="p153191729102818"></a><a name="p153191729102818"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.4.1.2 "><p id="p63193293289"><a name="p63193293289"></a><a name="p63193293289"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="56.99999999999999%" headers="mcps1.2.4.1.3 "><p id="p231992915285"><a name="p231992915285"></a><a name="p231992915285"></a>name of the Deployment</p>
</td>
</tr>
<tr id="row6971102432818"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p397172413282"><a name="p397172413282"></a><a name="p397172413282"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.4.1.2 "><p id="p14971824142810"><a name="p14971824142810"></a><a name="p14971824142810"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="56.99999999999999%" headers="mcps1.2.4.1.3 "><p id="p89717240289"><a name="p89717240289"></a><a name="p89717240289"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row11971122412819"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p1597142412282"><a name="p1597142412282"></a><a name="p1597142412282"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.4.1.2 "><p id="p497132410288"><a name="p497132410288"></a><a name="p497132410288"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="56.99999999999999%" headers="mcps1.2.4.1.3 "><p id="p1597132420289"><a name="p1597132420289"></a><a name="p1597132420289"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section1244125315509"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建Deployment.md#table12862324102610)。

**请求示例：**

```
{
    "kind": "Deployment",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "name": "deploy-example",
        "namespace": "default",
        "selfLink": "/apis/apps/v1beta1/namespaces/default/deployments/deploy-example",
        "uid": "27072a31-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "418453",
        "generation": 1,
        "creationTimestamp": "2017-12-13T03:10:20Z",
        "labels": {
            "app": "test"
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
                "app": "test"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "app": "test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "deploycon-12130306",
                        "image": "nginx",
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
        "observedGeneration": 1,
        "conditions": [
            {
                "type": "Available",
                "status": "True",
                "lastUpdateTime": "2017-12-13T03:10:20Z",
                "lastTransitionTime": "2017-12-13T03:10:20Z",
                "reason": "MinimumReplicasAvailable",
                "message": "Deployment has minimum availability."
            },
            {
                "type": "Progressing",
                "status": "True",
                "lastUpdateTime": "2017-12-13T03:10:20Z",
                "lastTransitionTime": "2017-12-13T03:10:20Z",
                "reason": "NewReplicaSetAvailable",
                "message": "ReplicaSet \"deploy-12130306-3417241766\" has successfully progressed."
            }
        ]
    }
}
```

## 响应消息<a name="section59181834162920"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Deployment.md#table12862324102610)。

**响应示例：**

```
{
    "apiVersion": "apps/v1beta1",
    "kind": "Deployment",
    "metadata": {
        "annotations": {
            "deployment.kubernetes.io/revision": "1"
        },
        "creationTimestamp": "2017-11-09T01:35:00Z",
        "enable": true,
        "generation": 1,
        "labels": {
            "app": "test"
        },
        "name": "deployment-example",
        "namespace": "default",
        "resourceVersion": "12857132",
        "selfLink": "/apis/apps/v1beta1/namespaces/default/deployments/deployment-example",
        "uid": "33a5e8fd-c4ee-11e7-aad0-286ed488d4c6"
    },
    "spec": {
        "replicas": 3,
        "selector": {
            "matchLabels": {
                "app": "test"
            }
        },
        "strategy": {
            "rollingUpdate": {
                "maxSurge": 1,
                "maxUnavailable": 1
            },
            "type": "RollingUpdate"
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "enable": true,
                "labels": {
                    "app": "test"
                }
            },
            "spec": {
                "containers": [
                    {
                        "image": "nginx:1.13.6",
                        "imagePullPolicy": "Always",
                        "name": "nginx",
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
        "conditions": [
            {
                "lastTransitionTime": "2017-11-10T17:02:50Z",
                "lastUpdateTime": "2017-11-10T01:35:01Z",
                "message": "Deployment does not have minimum availability.",
                "reason": "MinimumReplicasUnavailable",
                "status": "False",
                "type": "Available"
            }
        ],
        "observedGeneration": 1,
        "replicas": 3,
        "unavailableReplicas": 3,
        "updatedReplicas": 3
    }
}
```

状态码

[表2](#tba7e7375aafb4111a16990b2ada529cb)描述API的状态码。

**表 2**  状态码

<a name="tba7e7375aafb4111a16990b2ada529cb"></a>
<table><thead align="left"><tr id="re5fb2a906b384aa288601fcc449b33f1"><th class="cellrowborder" valign="top" width="47%" id="mcps1.2.3.1.1"><p id="p7478104103014"><a name="p7478104103014"></a><a name="p7478104103014"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="53%" id="mcps1.2.3.1.2"><p id="p1847954163013"><a name="p1847954163013"></a><a name="p1847954163013"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="ra2f69c00f8444dff82e2c6ae35c9c214"><td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.3.1.1 "><p id="a945d7039505e4e87bbff604606492324"><a name="a945d7039505e4e87bbff604606492324"></a><a name="a945d7039505e4e87bbff604606492324"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.3.1.2 "><p id="a33a7137eb9484957bc44bc63637e52b9"><a name="a33a7137eb9484957bc44bc63637e52b9"></a><a name="a33a7137eb9484957bc44bc63637e52b9"></a>This operation succeeds, and a  Development resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

