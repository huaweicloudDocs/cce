# 列出指定的StatefulSet<a name="cce_02_0153"></a>

## 功能介绍<a name="section42877597"></a>

This API is used to list all StatefulSet resource objects.

## URI<a name="section50354060"></a>

GET /apis/apps/v1/statefulsets \(Supports 1.9 and 1.9+\)

GET /apis/apps/v1beta1/statefulsets \(Supports 1.15 and 1.15-\)

[表1](#d0e39528)描述该API的参数。

**表 1**  参数解释

<a name="d0e39528"></a>
<table><thead align="left"><tr id="row4368152"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="63.26367363263674%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row47746152"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p42233099"><a name="p42233099"></a><a name="p42233099"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p65437867"><a name="p65437867"></a><a name="p65437867"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p65975855"><a name="p65975855"></a><a name="p65975855"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row56911786"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p46451968"><a name="p46451968"></a><a name="p46451968"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p4513070"><a name="p4513070"></a><a name="p4513070"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p30014429"><a name="p30014429"></a><a name="p30014429"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row1694413"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p3029727"><a name="p3029727"></a><a name="p3029727"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p44081350"><a name="p44081350"></a><a name="p44081350"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p57267774"><a name="p57267774"></a><a name="p57267774"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row45647922"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p6494215"><a name="p6494215"></a><a name="p6494215"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p56269392"><a name="p56269392"></a><a name="p56269392"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p61526902"><a name="p61526902"></a><a name="p61526902"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row16871207"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p24390498"><a name="p24390498"></a><a name="p24390498"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p29473326"><a name="p29473326"></a><a name="p29473326"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p38529202"><a name="p38529202"></a><a name="p38529202"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row11218505"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p36283733"><a name="p36283733"></a><a name="p36283733"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p53301294"><a name="p53301294"></a><a name="p53301294"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p22437563"><a name="p22437563"></a><a name="p22437563"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="row611481"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p49530000"><a name="p49530000"></a><a name="p49530000"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p52507055"><a name="p52507055"></a><a name="p52507055"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p25213087"><a name="p25213087"></a><a name="p25213087"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section50533362"></a>

N/A

## 响应消息<a name="section52147080"></a>

**响应参数：**

**表 2**  响应参数

<a name="table44321378"></a>
<table><thead align="left"><tr id="row4467942"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p26359045"><a name="p26359045"></a><a name="p26359045"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p54707896"><a name="p54707896"></a><a name="p54707896"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p2154600"><a name="p2154600"></a><a name="p2154600"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row40304892"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p43470813"><a name="p43470813"></a><a name="p43470813"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p31474930"><a name="p31474930"></a><a name="p31474930"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p66441379"><a name="p66441379"></a><a name="p66441379"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row61101506"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p50274986"><a name="p50274986"></a><a name="p50274986"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p45742050"><a name="p45742050"></a><a name="p45742050"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p14118546"><a name="p14118546"></a><a name="p14118546"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row59958055"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p24764287"><a name="p24764287"></a><a name="p24764287"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p59750244"><a name="p59750244"></a><a name="p59750244"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p4275369"><a name="p4275369"></a><a name="p4275369"></a>List of StatefulSets.具体请参见<a href="创建StatefulSet.md#d0e37568">表2</a>。</p>
</td>
</tr>
<tr id="row38478323"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p29736429"><a name="p29736429"></a><a name="p29736429"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p59840531"><a name="p59840531"></a><a name="p59840531"></a><a href="#d0e39691">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p2986183"><a name="p2986183"></a><a name="p2986183"></a>Standard list metadata.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="d0e39691"></a>
<table><thead align="left"><tr id="row5154030"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p14823285"><a name="p14823285"></a><a name="p14823285"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="31%" id="mcps1.2.4.1.2"><p id="p59835428"><a name="p59835428"></a><a name="p59835428"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44%" id="mcps1.2.4.1.3"><p id="p14831524"><a name="p14831524"></a><a name="p14831524"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row60502813"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1780790"><a name="p1780790"></a><a name="p1780790"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="31%" headers="mcps1.2.4.1.2 "><p id="p10026263"><a name="p10026263"></a><a name="p10026263"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p6820969"><a name="p6820969"></a><a name="p6820969"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row61388723"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p6430705"><a name="p6430705"></a><a name="p6430705"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="31%" headers="mcps1.2.4.1.2 "><p id="p51125107"><a name="p51125107"></a><a name="p51125107"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p47493026"><a name="p47493026"></a><a name="p47493026"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "StatefulSetList",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "selfLink": "/apis/apps/v1beta1/statefulsets",
        "resourceVersion": "1809953"
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

## 状态码<a name="section66670544"></a>

[表4](#d0e39743)描述API的状态码。

**表 4**  状态码

<a name="d0e39743"></a>
<table><thead align="left"><tr id="row60038784"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p31303356"><a name="p31303356"></a><a name="p31303356"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p52543941"><a name="p52543941"></a><a name="p52543941"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row28200834"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2566236"><a name="p2566236"></a><a name="p2566236"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p6538554"><a name="p6538554"></a><a name="p6538554"></a>This operation succeeds, and a group of StatefulSet resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

