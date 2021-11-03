# 获取Replicasets<a name="cce_02_0336"></a>

## 功能介绍<a name="section206471255123112"></a>

list or watch objects of kind ReplicaSet

## URI<a name="section5904740103211"></a>

GET /apis/apps/v1/replicasets

**表 1**  Query参数

<a name="table1175263211819"></a>
<table><thead align="left"><tr id="row07481632101817"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p075220320181"><a name="p075220320181"></a><a name="p075220320181"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.010000000000002%" id="mcps1.2.5.1.2"><p id="p1897216223588"><a name="p1897216223588"></a><a name="p1897216223588"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.660000000000002%" id="mcps1.2.5.1.3"><p id="p8753203261813"><a name="p8753203261813"></a><a name="p8753203261813"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.95%" id="mcps1.2.5.1.4"><p id="p975703271816"><a name="p975703271816"></a><a name="p975703271816"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row174843216184"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p16757183210187"><a name="p16757183210187"></a><a name="p16757183210187"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="13.010000000000002%" headers="mcps1.2.5.1.2 "><p id="p175081340125818"><a name="p175081340125818"></a><a name="p175081340125818"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.660000000000002%" headers="mcps1.2.5.1.3 "><p id="p875873213184"><a name="p875873213184"></a><a name="p875873213184"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p13759432161816"><a name="p13759432161816"></a><a name="p13759432161816"></a>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</p>
</td>
</tr>
<tr id="row167491932191815"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p147591232161819"><a name="p147591232161819"></a><a name="p147591232161819"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="13.010000000000002%" headers="mcps1.2.5.1.2 "><p id="p6508640165818"><a name="p6508640165818"></a><a name="p6508640165818"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.660000000000002%" headers="mcps1.2.5.1.3 "><p id="p1875915320189"><a name="p1875915320189"></a><a name="p1875915320189"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p1876163251820"><a name="p1876163251820"></a><a name="p1876163251820"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row11749132181816"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p187612032121817"><a name="p187612032121817"></a><a name="p187612032121817"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="13.010000000000002%" headers="mcps1.2.5.1.2 "><p id="p75091540155812"><a name="p75091540155812"></a><a name="p75091540155812"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.660000000000002%" headers="mcps1.2.5.1.3 "><p id="p157624322186"><a name="p157624322186"></a><a name="p157624322186"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p1176214323187"><a name="p1176214323187"></a><a name="p1176214323187"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row11749153261819"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p177631032111820"><a name="p177631032111820"></a><a name="p177631032111820"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="13.010000000000002%" headers="mcps1.2.5.1.2 "><p id="p15096405589"><a name="p15096405589"></a><a name="p15096405589"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.660000000000002%" headers="mcps1.2.5.1.3 "><p id="p57631032161819"><a name="p57631032161819"></a><a name="p57631032161819"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p1764163281820"><a name="p1764163281820"></a><a name="p1764163281820"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row374914324184"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p19765163211185"><a name="p19765163211185"></a><a name="p19765163211185"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="13.010000000000002%" headers="mcps1.2.5.1.2 "><p id="p75091640125820"><a name="p75091640125820"></a><a name="p75091640125820"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.660000000000002%" headers="mcps1.2.5.1.3 "><p id="p1676533211812"><a name="p1676533211812"></a><a name="p1676533211812"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p177661732191818"><a name="p177661732191818"></a><a name="p177661732191818"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the `continue` field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.</p>
<p id="p1766153220187"><a name="p1766153220187"></a><a name="p1766153220187"></a></p>
<p id="p167671432141814"><a name="p167671432141814"></a><a name="p167671432141814"></a>The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row147501632201811"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p20767103271811"><a name="p20767103271811"></a><a name="p20767103271811"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="13.010000000000002%" headers="mcps1.2.5.1.2 "><p id="p16509174016584"><a name="p16509174016584"></a><a name="p16509174016584"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.660000000000002%" headers="mcps1.2.5.1.3 "><p id="p16768153219189"><a name="p16768153219189"></a><a name="p16768153219189"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p157691432171813"><a name="p157691432171813"></a><a name="p157691432171813"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row2750173271814"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p87701732161810"><a name="p87701732161810"></a><a name="p87701732161810"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="13.010000000000002%" headers="mcps1.2.5.1.2 "><p id="p3509114017587"><a name="p3509114017587"></a><a name="p3509114017587"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.660000000000002%" headers="mcps1.2.5.1.3 "><p id="p10770232111818"><a name="p10770232111818"></a><a name="p10770232111818"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p1677115322184"><a name="p1677115322184"></a><a name="p1677115322184"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row9750132171814"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p8772532111816"><a name="p8772532111816"></a><a name="p8772532111816"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="13.010000000000002%" headers="mcps1.2.5.1.2 "><p id="p3509144019581"><a name="p3509144019581"></a><a name="p3509144019581"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.660000000000002%" headers="mcps1.2.5.1.3 "><p id="p127728326189"><a name="p127728326189"></a><a name="p127728326189"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p14774133213187"><a name="p14774133213187"></a><a name="p14774133213187"></a>Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity.</p>
</td>
</tr>
<tr id="row107501032171816"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p6775143261817"><a name="p6775143261817"></a><a name="p6775143261817"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="13.010000000000002%" headers="mcps1.2.5.1.2 "><p id="p1150974075814"><a name="p1150974075814"></a><a name="p1150974075814"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.660000000000002%" headers="mcps1.2.5.1.3 "><p id="p1977573213185"><a name="p1977573213185"></a><a name="p1977573213185"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p277711329189"><a name="p277711329189"></a><a name="p277711329189"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section1991411610338"></a>

无

## 响应参数<a name="section12283327103318"></a>

状态码为 200 时:

**表 2**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row18786832141815"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1778711327185"><a name="p1778711327185"></a><a name="p1778711327185"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24.47%" id="mcps1.2.4.1.2"><p id="p157881322184"><a name="p157881322184"></a><a name="p157881322184"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="55.53%" id="mcps1.2.4.1.3"><p id="p88681653185813"><a name="p88681653185813"></a><a name="p88681653185813"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row87861832181810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p978814329182"><a name="p978814329182"></a><a name="p978814329182"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="24.47%" headers="mcps1.2.4.1.2 "><p id="p478903231810"><a name="p478903231810"></a><a name="p478903231810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="55.53%" headers="mcps1.2.4.1.3 "><p id="p1178963212183"><a name="p1178963212183"></a><a name="p1178963212183"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources</p>
</td>
</tr>
<tr id="row16786332181810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p2790133291811"><a name="p2790133291811"></a><a name="p2790133291811"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="24.47%" headers="mcps1.2.4.1.2 "><p id="p17791143211182"><a name="p17791143211182"></a><a name="p17791143211182"></a>Array of <a href="获取Replicasets.md">io.k8s.api.apps.v1.ReplicaSet</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="55.53%" headers="mcps1.2.4.1.3 "><p id="p19792193281812"><a name="p19792193281812"></a><a name="p19792193281812"></a>List of ReplicaSets. More info: https://kubernetes.io/docs/concepts/workloads/controllers/replicationcontroller</p>
</td>
</tr>
<tr id="row47867322189"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p47921328188"><a name="p47921328188"></a><a name="p47921328188"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="24.47%" headers="mcps1.2.4.1.2 "><p id="p979303214181"><a name="p979303214181"></a><a name="p979303214181"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="55.53%" headers="mcps1.2.4.1.3 "><p id="p1979323211189"><a name="p1979323211189"></a><a name="p1979323211189"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row1478683215182"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p47945326188"><a name="p47945326188"></a><a name="p47945326188"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="24.47%" headers="mcps1.2.4.1.2 "><p id="p2503122825912"><a name="p2503122825912"></a><a name="p2503122825912"></a>Array of <a href="获取Replicasets.md">io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="55.53%" headers="mcps1.2.4.1.3 "><p id="p15795153213184"><a name="p15795153213184"></a><a name="p15795153213184"></a>Standard list metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section235718456182"></a>

无

## 响应示例<a name="section1335817451187"></a>

状态码为 200 时:

```
{
    "apiVersion": "v1",
    "items": [
        {
            "apiVersion": "extensions/v1beta1",
            "kind": "ReplicaSet",
            "metadata": {
                "annotations": {
                    "deployment.kubernetes.io/desired-replicas": "2",
                    "deployment.kubernetes.io/max-replicas": "3",
                    "deployment.kubernetes.io/revision": "1"
                },
                "creationTimestamp": "2019-07-03T07:35:30Z",
                "generation": 1,
                "labels": {
                    "app": "coredns",
                    "k8s-app": "coredns",
                    "kubernetes.io/evictcritical": "",
                    "pod-template-hash": "85cb64445b",
                    "release": "cceaddon-coredns"
                },
                "name": "coredns-85cb64445b",
                "namespace": "kube-system",
                "ownerReferences": [
                    {
                        "apiVersion": "apps/v1",
                        "blockOwnerDeletion": true,
                        "controller": true,
                        "kind": "Deployment",
                        "name": "coredns",
                        "uid": "22573447-9d65-11e9-8d38-fa163eb8e88a"
                    }
                ],
                "resourceVersion": "3714356",
                "selfLink": "/apis/extensions/v1beta1/namespaces/kube-system/replicasets/coredns-85cb64445b",
                "uid": "22586f58-9d65-11e9-8d38-fa163eb8e88a"
            },
            "spec": {
                "replicas": 2,
                "selector": {
                    "matchLabels": {
                        "app": "coredns",
                        "k8s-app": "coredns",
                        "pod-template-hash": "85cb64445b"
                    }
                },
                "template": {
                    "metadata": {
                        "annotations": {
                            "checksum/config": "3095a9b4028195e7e0b8b22c550bf183d0b7a8a7eba20808b36081d0b39f8b81",
                            "scheduler.alpha.kubernetes.io/critical-pod": "",
                            "scheduler.alpha.kubernetes.io/tolerations": "[{\"key\":\"CriticalAddonsOnly\", \"operator\":\"Exists\"}]"
                        },
                        "creationTimestamp": null,
                        "labels": {
                            "app": "coredns",
                            "k8s-app": "coredns",
                            "kubernetes.io/evictcritical": "",
                            "pod-template-hash": "85cb64445b",
                            "release": "cceaddon-coredns"
                        }
                    },
                    "spec": {
                        "affinity": {
                            "podAntiAffinity": {
                                "requiredDuringSchedulingIgnoredDuringExecution": [
                                    {
                                        "labelSelector": {
                                            "matchExpressions": [
                                                {
                                                    "key": "app",
                                                    "operator": "In",
                                                    "values": [
                                                        "coredns"
                                                    ]
                                                }
                                            ]
                                        },
                                        "topologyKey": "kubernetes.io/hostname"
                                    }
                                ]
                            }
                        },
                        "containers": [
                            {
                                "args": [
                                    "-conf",
                                    "/etc/coredns/Corefile",
                                    "-rmem",
                                    "udp#8388608",
                                    "-wmem",
                                    "udp#1048576"
                                ],
                                "image": "100.79.1.215:20202/hwofficial/cce-coredns-linux-amd64:1.2.6.1",
                                "imagePullPolicy": "IfNotPresent",
                                "livenessProbe": {
                                    "failureThreshold": 5,
                                    "httpGet": {
                                        "path": "/health",
                                        "port": 8080,
                                        "scheme": "HTTP"
                                    },
                                    "initialDelaySeconds": 60,
                                    "periodSeconds": 10,
                                    "successThreshold": 1,
                                    "timeoutSeconds": 5
                                },
                                "name": "coredns",
                                "ports": [
                                    {
                                        "containerPort": 5353,
                                        "protocol": "UDP"
                                    }
                                ],
                                "readinessProbe": {
                                    "failureThreshold": 3,
                                    "httpGet": {
                                        "path": "/health",
                                        "port": 8080,
                                        "scheme": "HTTP"
                                    },
                                    "initialDelaySeconds": 3,
                                    "periodSeconds": 5,
                                    "successThreshold": 1,
                                    "timeoutSeconds": 3
                                },
                                "resources": {
                                    "limits": {
                                        "cpu": "500m",
                                        "memory": "512Mi"
                                    },
                                    "requests": {
                                        "cpu": "500m",
                                        "memory": "512Mi"
                                    }
                                },
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "volumeMounts": [
                                    {
                                        "mountPath": "/etc/coredns",
                                        "name": "config-volume"
                                    }
                                ]
                            }
                        ],
                        "dnsPolicy": "Default",
                        "restartPolicy": "Always",
                        "schedulerName": "default-scheduler",
                        "securityContext": {},
                        "serviceAccount": "coredns",
                        "serviceAccountName": "coredns",
                        "terminationGracePeriodSeconds": 30,
                        "tolerations": [
                            {
                                "effect": "NoExecute",
                                "key": "node.kubernetes.io/not-ready",
                                "operator": "Exists",
                                "tolerationSeconds": 60
                            },
                            {
                                "effect": "NoExecute",
                                "key": "node.kubernetes.io/unreachable",
                                "operator": "Exists",
                                "tolerationSeconds": 60
                            }
                        ],
                        "volumes": [
                            {
                                "configMap": {
                                    "defaultMode": 420,
                                    "items": [
                                        {
                                            "key": "Corefile",
                                            "path": "Corefile"
                                        }
                                    ],
                                    "name": "coredns"
                                },
                                "name": "config-volume"
                            }
                        ]
                    }
                }
            },
            "status": {
                "fullyLabeledReplicas": 2,
                "observedGeneration": 1,
                "replicas": 2
            }
        }
    ],
    "kind": "List",
    "metadata": {
        "resourceVersion": "",
        "selfLink": ""
    }
}
```

## 返回值<a name="section1344944581810"></a>

<a name="table532"></a>
<table><thead align="left"><tr id="row85451139191816"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p1744944581810"><a name="p1744944581810"></a><a name="p1744944581810"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p124491045201817"><a name="p124491045201817"></a><a name="p124491045201817"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1154583951818"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p444984519187"><a name="p444984519187"></a><a name="p444984519187"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p1544919456182"><a name="p1544919456182"></a><a name="p1544919456182"></a>OK</p>
</td>
</tr>
<tr id="row11545239201818"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p94491145151820"><a name="p94491145151820"></a><a name="p94491145151820"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p844944551817"><a name="p844944551817"></a><a name="p844944551817"></a>Unauthorized</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section14499456182"></a>

无

