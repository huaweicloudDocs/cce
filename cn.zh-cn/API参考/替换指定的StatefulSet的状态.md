# 替换指定的StatefulSet的状态<a name="cce_02_0151"></a>

## 功能介绍<a name="section50502051"></a>

This API is used to replace the status of a specified StatefulSet object under a specified Namespace, that is, to modify the value of the  **status**  field of the StatefulSet object.

## URI<a name="section51865283"></a>

PUT /apis/apps/v1/namespaces/\{namespace\}/statefulsets/\{name\}/status \(Supports 1.9 and 1.9+\)

PUT /apis/apps/v1beta1/namespaces/\{namespace\}/statefulsets/\{name\}/status \(Supports 1.15 and 1.15-\)

[表1](#d0e39176)描述该API的参数。

**表 1**  参数解释

<a name="d0e39176"></a>
<table><thead align="left"><tr id="row55394367"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="63.26367363263674%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row56690650"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p28539942"><a name="p28539942"></a><a name="p28539942"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p30033962"><a name="p30033962"></a><a name="p30033962"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p16831887"><a name="p16831887"></a><a name="p16831887"></a>Name of the StatefulSet.</p>
</td>
</tr>
<tr id="row17269261"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p56632934"><a name="p56632934"></a><a name="p56632934"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p23864947"><a name="p23864947"></a><a name="p23864947"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p54012573"><a name="p54012573"></a><a name="p54012573"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row16351112"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p49371687"><a name="p49371687"></a><a name="p49371687"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p39683735"><a name="p39683735"></a><a name="p39683735"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p60265984"><a name="p60265984"></a><a name="p60265984"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section64134368"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建StatefulSet.md#d0e37568)。

**请求示例：**

```
{
    "apiVersion": "apps/v1beta1",
    "kind": "StatefulSet",
    "metadata": {
        "generateName": "sz",
        "name": "numberlimit",
        "namespace": "default"
    },
    "spec": {
        "replicas": 1,
        "serviceName": "service-number",
        "template": {
            "metadata": {
                "labels": {
                    "app": "mysql"
                }
            },
            "spec": {
                "containers": [
                    {
                        "image": "10.154.52.159:443/test/mongo:latest",
                        "imagePullPolicy": "IfNotPresent",
                        "name": "container01",
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
                                "cpu": "0.3G"
                            }
                        },
                        "terminationMessagePath": "/dev/termination-log"
                    }
                ]
            }
        }
    },
    "status": {
        "replicas": 3
    }
}
```

## 响应消息<a name="section40338403"></a>

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
        "resourceVersion": "1399495",
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

## 状态码<a name="section27501309"></a>

[表2](#d0e39265)描述API的状态码。

**表 2**  状态码

<a name="d0e39265"></a>
<table><thead align="left"><tr id="row18495904"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p21773275"><a name="p21773275"></a><a name="p21773275"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p18804863"><a name="p18804863"></a><a name="p18804863"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row46798898"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p32614431"><a name="p32614431"></a><a name="p32614431"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p24523244"><a name="p24523244"></a><a name="p24523244"></a>This operation succeeds, and a StatefulSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

