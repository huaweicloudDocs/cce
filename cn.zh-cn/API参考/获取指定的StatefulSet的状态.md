# 获取指定的StatefulSet的状态<a name="cce_02_0149"></a>

## 功能介绍<a name="section27242258"></a>

This API is used to read the status of a specified StatefulSet object under a specified Namespace.

## URI<a name="section43853730"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/statefulsets/\{name\}/status

**表 1**  参数解释

<a name="d0e38842"></a>
<table><thead align="left"><tr id="row20375378"><th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="63.26367363263674%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row40697101"><td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.4.1.1 "><p id="p8130848"><a name="p8130848"></a><a name="p8130848"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.2 "><p id="p54618989"><a name="p54618989"></a><a name="p54618989"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p62061978"><a name="p62061978"></a><a name="p62061978"></a>Name of the StatefulSet.</p>
</td>
</tr>
<tr id="row21686892"><td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.4.1.1 "><p id="p11807821"><a name="p11807821"></a><a name="p11807821"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.2 "><p id="p16909410"><a name="p16909410"></a><a name="p16909410"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p27484947"><a name="p27484947"></a><a name="p27484947"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row46037938"><td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.4.1.1 "><p id="p38085530"><a name="p38085530"></a><a name="p38085530"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.2 "><p id="p65029074"><a name="p65029074"></a><a name="p65029074"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p32863618"><a name="p32863618"></a><a name="p32863618"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section59139257"></a>

N/A

## 响应消息<a name="section62491271"></a>

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
        "selfLink": "/apis/apps/v1beta1/namespaces/default/statefulsets/mysql/status",
        "uid": "f5cf50f5-23fc-11e7-9c83-fa163ec08232",
        "resourceVersion": "1808945",
        "generation": 1,
        "creationTimestamp": "2017-04-18T06:05:02Z",
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
                "name": "-sz",
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

## 状态码<a name="section25550533"></a>

[表2](#d0e38919)描述API的状态码。

**表 2**  状态码

<a name="d0e38919"></a>
<table><thead align="left"><tr id="row25379235"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p42452127"><a name="p42452127"></a><a name="p42452127"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p16070288"><a name="p16070288"></a><a name="p16070288"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row26624990"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p9140592"><a name="p9140592"></a><a name="p9140592"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p2190511"><a name="p2190511"></a><a name="p2190511"></a>This operation succeeds, and a StatefulSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

