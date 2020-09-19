# 替换指定的StatefulSet<a name="cce_02_0150"></a>

## 功能介绍<a name="section53648226"></a>

This API is used to replace a StatefulSet object under a specified Namespace.

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

The other fields cannot be updated.

## URI<a name="section13071992"></a>

PUT /apis/apps/v1/namespaces/\{namespace\}/statefulsets/\{name\} \(Supports 1.9 and 1.9+\)

PUT /apis/apps/v1beta1/namespaces/\{namespace\}/statefulsets/\{name\} \(Supports 1.15 and 1.15-\)

[表1](#d0e39017)描述该API的参数。

**表 1**  参数解释

<a name="d0e39017"></a>
<table><thead align="left"><tr id="row47561193"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="63.26367363263674%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row20654971"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p62439989"><a name="p62439989"></a><a name="p62439989"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p24474376"><a name="p24474376"></a><a name="p24474376"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p36267419"><a name="p36267419"></a><a name="p36267419"></a>Name of the StatefulSet.</p>
</td>
</tr>
<tr id="row57971316"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p65165002"><a name="p65165002"></a><a name="p65165002"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p43873846"><a name="p43873846"></a><a name="p43873846"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p64120605"><a name="p64120605"></a><a name="p64120605"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row40214539"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p36152249"><a name="p36152249"></a><a name="p36152249"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p42651031"><a name="p42651031"></a><a name="p42651031"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p32181453"><a name="p32181453"></a><a name="p32181453"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section50539068"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建StatefulSet.md#d0e37568)。

**请求示例：**

```
{
    "apiVersion": "apps/v1beta1",
    "kind": "StatefulSet",
    "metadata": {
        "generateName": "sz",
        "labels": {
            "app": "mysql-0"
        },
        "name": "mysql",
        "namespace": "default",
        "resourceVersion": "1923999"
    },
    "spec": {
        "replicas": 1,
        "serviceName": "mysql-service",
        "template": {
            "metadata": {
                "labels": {
                    "app": "mysql"
                }
            },
            "spec": {
                "containers": [
                    {
                        "image": "10.154.52.159:443/test/nginx:latest",
                        "imagePullPolicy": "IfNotPresent",
                        "name": "container01",
                        "ports": [
                            {
                                "containerPort": 80,
                                "protocol": "TCP"
                            }
                        ],
                        "resources": {},
                        "terminationGracePeriodSeconds": 100,
                        "terminationMessagePath": "/dev/termination-log"
                    }
                ]
            }
        },
        "volumeClaimTemplates": [
            {
                "metadata": {
                    "name": "db"
                },
                "spec": {
                    "accessModes": [
                        "ReadWriteOnce"
                    ],
                    "resources": {
                        "requests": {
                            "storage": "1Gi"
                        }
                    }
                }
            }
        ]
    }
}
```

## 响应消息<a name="section52198431"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建StatefulSet.md#d0e37568)。

**响应示例：**

```
{
    "kind": "StatefulSet",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "name": "mysql",
        "generateName": "sz",
        "namespace": "default",
        "selfLink": "/apis/apps/v1beta1/namespaces/default/statefulsets/mysql",
        "uid": "1688bdcb-24da-11e7-9c83-fa163ec08232",
        "resourceVersion": "1923999",
        "generation": 1,
        "creationTimestamp": "2017-04-19T08:27:55Z",
        "labels": {
            "app": "mysql-0"
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
                        "image": "10.154.52.159:443/test/nginx:latest",
                        "ports": [
                            {
                                "containerPort": 80,
                                "protocol": "TCP"
                            }
                        ],
                        "resources": {},
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
        "volumeClaimTemplates": [
            {
                "metadata": {
                    "name": "db",
                    "creationTimestamp": null
                },
                "spec": {
                    "accessModes": [
                        "ReadWriteOnce"
                    ],
                    "resources": {
                        "requests": {
                            "storage": "1Gi"
                        }
                    }
                },
                "status": {
                    "phase": "Pending"
                }
            }
        ],
        "serviceName": "mysql-service"
    },
    "status": {
        "replicas": 1
    }
}
```

## 状态码<a name="section23834"></a>

[表2](#d0e39106)描述API的状态码。

**表 2**  状态码

<a name="d0e39106"></a>
<table><thead align="left"><tr id="row46918656"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p42314824"><a name="p42314824"></a><a name="p42314824"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p4948704"><a name="p4948704"></a><a name="p4948704"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row65300720"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p54866977"><a name="p54866977"></a><a name="p54866977"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p15040154"><a name="p15040154"></a><a name="p15040154"></a>This operation succeeds, and a StatefulSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

