# 更新指定的StatefulSet<a name="cce_02_0154"></a>

## 功能介绍<a name="section40645355"></a>

This API is used to update a StatefulSet object under a specific Namespace.

The following fields can be updated:

-   metadata.labels
-   metadata.clusterName
-   metadata.generateName
-   metadata.annotations
-   spec.replicas
-   template.containers

The other fields cannot be updated.

## URI<a name="section30263877"></a>

PATCH /apis/apps/v1/namespaces/\{namespace\}/statefulsets/\{name\} （适用于1.9及以上版本的所有集群）

PATCH /apis/apps/v1beta1/namespaces/\{namespace\}/statefulsets/\{name\} （仅适用于1.15及以下版本的集群）

[表1](#d0e39827)描述该API的参数。

**表 1**  参数解释

<a name="d0e39827"></a>
<table><thead align="left"><tr id="row21309757"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.15%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="62.629999999999995%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15310218"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p32168169"><a name="p32168169"></a><a name="p32168169"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p55484892"><a name="p55484892"></a><a name="p55484892"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p65091276"><a name="p65091276"></a><a name="p65091276"></a>Name of the StatefulSet.</p>
</td>
</tr>
<tr id="row48950574"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p5573539"><a name="p5573539"></a><a name="p5573539"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p48803529"><a name="p48803529"></a><a name="p48803529"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p60771783"><a name="p60771783"></a><a name="p60771783"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row10075143"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p10780286"><a name="p10780286"></a><a name="p10780286"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p787936"><a name="p787936"></a><a name="p787936"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p63822871"><a name="p63822871"></a><a name="p63822871"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section3939444"></a>

**请求参数：**

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/merge-patch+json
{
    "metadata": {
        "labels": {
            "app": "mysql-0"
        }
    }
}
```

## 响应消息<a name="section35455000"></a>

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
        "resourceVersion": "1924739",
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

## 状态码<a name="section50659546"></a>

[表2](#d0e39922)描述API的状态码。

**表 2**  状态码

<a name="d0e39922"></a>
<table><thead align="left"><tr id="row43842358"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p61570118"><a name="p61570118"></a><a name="p61570118"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p21123642"><a name="p21123642"></a><a name="p21123642"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row33293435"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p12413680"><a name="p12413680"></a><a name="p12413680"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p65984001"><a name="p65984001"></a><a name="p65984001"></a>This operation succeeds, and a StatefulSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

