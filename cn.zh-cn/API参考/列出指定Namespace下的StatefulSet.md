# 列出指定Namespace下的StatefulSet<a name="cce_02_0152"></a>

## 功能介绍<a name="section55184758"></a>

This API is used to list all StatefulSet resource objects under a specified Namespace.

## URI<a name="section26900781"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/statefulsets

**表 1**  参数解释

<a name="d0e39332"></a>
<table><thead align="left"><tr id="row16249415"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="63.26367363263674%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row33792834"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p52865065"><a name="p52865065"></a><a name="p52865065"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p54211835"><a name="p54211835"></a><a name="p54211835"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p29082530"><a name="p29082530"></a><a name="p29082530"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row60416185"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p61872826"><a name="p61872826"></a><a name="p61872826"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p45643011"><a name="p45643011"></a><a name="p45643011"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p6096445"><a name="p6096445"></a><a name="p6096445"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row54868012"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p15123986"><a name="p15123986"></a><a name="p15123986"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p17083324"><a name="p17083324"></a><a name="p17083324"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p38603562"><a name="p38603562"></a><a name="p38603562"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row11887742"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p23383013"><a name="p23383013"></a><a name="p23383013"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p14975921"><a name="p14975921"></a><a name="p14975921"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p5090122"><a name="p5090122"></a><a name="p5090122"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row45811103"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p19711829"><a name="p19711829"></a><a name="p19711829"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p53154316"><a name="p53154316"></a><a name="p53154316"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p10532331"><a name="p10532331"></a><a name="p10532331"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row27682122"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p27659385"><a name="p27659385"></a><a name="p27659385"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p25817701"><a name="p25817701"></a><a name="p25817701"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p10858997"><a name="p10858997"></a><a name="p10858997"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row30622110"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p64471840"><a name="p64471840"></a><a name="p64471840"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p54836538"><a name="p54836538"></a><a name="p54836538"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p12574613"><a name="p12574613"></a><a name="p12574613"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row46062658"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p40087841"><a name="p40087841"></a><a name="p40087841"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p25889684"><a name="p25889684"></a><a name="p25889684"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p16689668"><a name="p16689668"></a><a name="p16689668"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section40780438"></a>

N/A

## 响应消息<a name="section31479628"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建StatefulSet.md#d0e37568)。

**响应示例：**

```
{
    "kind": "StatefulSetList",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "selfLink": "/apis/apps/v1beta1/namespaces/default/statefulsets",
        "resourceVersion": "1809849"
    },
    "items": [
        {
            "metadata": {
                "name": "mysql",
                "generateName": "sz",
                "namespace": "default",
                "selfLink": "/apis/apps/v1beta1/namespaces/default/statefulsets/mysql",
                "uid": "f5cf50f5-23fc-11e7-9c83-fa163ec08232",
                "resourceVersion": "1809843",
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
    ]
}
```

## 状态码<a name="section14881199"></a>

[表2](#d0e39461)描述API的状态码。

**表 2**  状态码

<a name="d0e39461"></a>
<table><thead align="left"><tr id="row5459157"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p39538597"><a name="p39538597"></a><a name="p39538597"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p48509806"><a name="p48509806"></a><a name="p48509806"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row36980183"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p42604808"><a name="p42604808"></a><a name="p42604808"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p28437418"><a name="p28437418"></a><a name="p28437418"></a>This operation succeeds, and a StatefulSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

