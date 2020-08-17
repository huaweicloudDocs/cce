# 列出指定的ReplicaSet<a name="cce_02_0182"></a>

## 功能介绍<a name="section19030251"></a>

This API is used to list all ReplicaSet resource objects under a specified Namespace.

## URI<a name="section37054533"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/replicasets  \(Supports 1.9 and 1.9+\)

GET /apis/extensions/v1beta1/namespaces/\{namespace\}/replicasets \(Compatible\)

[表1](#d0e45179)描述该API的参数。

**表 1**  参数解释

<a name="d0e45179"></a>
<table><thead align="left"><tr id="row64943380"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="63.26367363263674%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row61989525"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p55095590"><a name="p55095590"></a><a name="p55095590"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p33557800"><a name="p33557800"></a><a name="p33557800"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p33827266"><a name="p33827266"></a><a name="p33827266"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row36009944"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p31124362"><a name="p31124362"></a><a name="p31124362"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p38045417"><a name="p38045417"></a><a name="p38045417"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p61779932"><a name="p61779932"></a><a name="p61779932"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row19148481"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p7523118"><a name="p7523118"></a><a name="p7523118"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p5392803"><a name="p5392803"></a><a name="p5392803"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p39039766"><a name="p39039766"></a><a name="p39039766"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row15813575"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p5831238"><a name="p5831238"></a><a name="p5831238"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p2568302"><a name="p2568302"></a><a name="p2568302"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p6705894"><a name="p6705894"></a><a name="p6705894"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row60353047"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p56758667"><a name="p56758667"></a><a name="p56758667"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p34049315"><a name="p34049315"></a><a name="p34049315"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p6531144"><a name="p6531144"></a><a name="p6531144"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row58780298"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p63583725"><a name="p63583725"></a><a name="p63583725"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p50008080"><a name="p50008080"></a><a name="p50008080"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p24122651"><a name="p24122651"></a><a name="p24122651"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row15777271"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p2890611"><a name="p2890611"></a><a name="p2890611"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p32812906"><a name="p32812906"></a><a name="p32812906"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p40599750"><a name="p40599750"></a><a name="p40599750"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row29853438"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p2209388"><a name="p2209388"></a><a name="p2209388"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p44742706"><a name="p44742706"></a><a name="p44742706"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p280569"><a name="p280569"></a><a name="p280569"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section65055348"></a>

N/A

## 响应消息<a name="section48627224"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建StatefulSet.md#d0e37568)。

**响应示例**：

```
{
    "kind": "ReplicaSetList",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "selfLink": "/apis/extensions/v1beta1/namespaces/default/replicasets",
        "resourceVersion": "793174"
    },
    "items": [
        {
            "metadata": {
                "name": "deployment-test-800400086",
                "namespace": "default",
                "selfLink": "/apis/extensions/v1beta1/namespaces/default/replicasets/deployment-test-800400086",
                "uid": "67775454-df2f-11e7-961f-fa163ed139d5",
                "resourceVersion": "784294",
                "generation": 1,
                "creationTimestamp": "2017-12-12T11:27:15Z",
                "labels": {
                    "name": "deployment-test",
                    "pod-template-hash": "800400086"
                },
                "annotations": {
                    "deployment.kubernetes.io/desired-replicas": "1",
                    "deployment.kubernetes.io/max-replicas": "2",
                    "deployment.kubernetes.io/revision": "1"
                },
                "ownerReferences": [
                    {
                        "apiVersion": "extensions/v1beta1",
                        "kind": "Deployment",
                        "name": "deployment-test",
                        "uid": "6776d16b-df2f-11e7-961f-fa163ed139d5",
                        "controller": true,
                        "blockOwnerDeletion": true
                    }
                ],
                "enable": true
            },
            "spec": {
                "replicas": 1,
                "selector": {
                    "matchLabels": {
                        "name": "deployment-test",
                        "pod-template-hash": "800400086"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "name": "deployment-test",
                            "pod-template-hash": "800400086"
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "deployment-test",
                                "image": "172.16.5.235:20202/test/testnginx:v3",
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
                }
            },
            "status": {
                "replicas": 1,
                "fullyLabeledReplicas": 1,
                "observedGeneration": 1
            }
        },
        {
            "metadata": {
                "name": "test-pv-446136006",
                "namespace": "default",
                "selfLink": "/apis/extensions/v1beta1/namespaces/default/replicasets/test-pv-446136006",
                "uid": "3b3dee35-dfd7-11e7-961f-fa163ed139d5",
                "resourceVersion": "784441",
                "generation": 1,
                "creationTimestamp": "2017-12-13T07:28:36Z",
                "labels": {
                    "app": "test-pv",
                    "pod-template-hash": "446136006"
                },
                "annotations": {
                    "deployment.kubernetes.io/desired-replicas": "2",
                    "deployment.kubernetes.io/max-replicas": "2",
                    "deployment.kubernetes.io/revision": "1"
                },
                "ownerReferences": [
                    {
                        "apiVersion": "extensions/v1beta1",
                        "kind": "Deployment",
                        "name": "test-pv",
                        "uid": "3b3d3a22-dfd7-11e7-961f-fa163ed139d5",
                        "controller": true,
                        "blockOwnerDeletion": true
                    }
                ],
                "enable": true
            },
            "spec": {
                "replicas": 2,
                "selector": {
                    "matchLabels": {
                        "app": "test-pv",
                        "pod-template-hash": "446136006"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "app": "test-pv",
                            "pod-template-hash": "446136006"
                        },
                        "annotations": {
                            "metrics.alpha.kubernetes.io/custom-endpoints": "[{api:'',path:'',port:'',names:''}]"
                        },
                        "enable": true
                    },
                    "spec": {
                        "volumes": [
                            {
                                "name": "wwww",
                                "persistentVolumeClaim": {
                                    "claimName": "pvc1513149915389"
                                }
                            }
                        ],
                        "containers": [
                            {
                                "name": "container-0",
                                "image": "172.16.5.235:20202/test/nginx:latest",
                                "resources": {},
                                "volumeMounts": [
                                    {
                                        "name": "wwww",
                                        "readOnly": true,
                                        "mountPath": "/tmp0"
                                    }
                                ],
                                "lifecycle": {},
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "Always"
                            }
                        ],
                        "restartPolicy": "Always",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "ClusterFirst",
                        "securityContext": {},
                        "imagePullSecrets": [
                            {
                                "name": "default-secret"
                            }
                        ],
                        "affinity": {},
                        "schedulerName": "default-scheduler"
                    }
                }
            },
            "status": {
                "replicas": 2,
                "fullyLabeledReplicas": 2,
                "readyReplicas": 2,
                "availableReplicas": 2,
                "observedGeneration": 1
            }
        }
    ]
}
```

## 状态码<a name="section34991834"></a>

[表2](#d0e45308)描述API的状态码。

**表 2**  状态码

<a name="d0e45308"></a>
<table><thead align="left"><tr id="row6630185"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p174074"><a name="p174074"></a><a name="p174074"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p14100028"><a name="p14100028"></a><a name="p14100028"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1251606"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p34271281"><a name="p34271281"></a><a name="p34271281"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p24510389"><a name="p24510389"></a><a name="p24510389"></a>This operation succeeds, and a ReplicaSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

