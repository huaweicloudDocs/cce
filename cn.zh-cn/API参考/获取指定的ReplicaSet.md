# 获取指定的ReplicaSet<a name="cce_02_0335"></a>

## 功能介绍<a name="section9325173016187"></a>

This API is used to read the ReplicaSets in a specified namespace.

## URI<a name="section10326103011818"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/replicasets/\{name\}

GET /apis/extensions/v1beta1/namespaces/\{namespace\}/replicasets/\{name\}

**表 1**  Query参数

<a name="table17330930161813"></a>
<table><thead align="left"><tr id="row17328430101819"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p173301630161811"><a name="p173301630161811"></a><a name="p173301630161811"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.089999999999998%" id="mcps1.2.5.1.2"><p id="p47543634618"><a name="p47543634618"></a><a name="p47543634618"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.58%" id="mcps1.2.5.1.3"><p id="p17331143051812"><a name="p17331143051812"></a><a name="p17331143051812"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p14332103012182"><a name="p14332103012182"></a><a name="p14332103012182"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row232823017187"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p7332330161816"><a name="p7332330161816"></a><a name="p7332330161816"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="13.089999999999998%" headers="mcps1.2.5.1.2 "><p id="p38331926114618"><a name="p38331926114618"></a><a name="p38331926114618"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.58%" headers="mcps1.2.5.1.3 "><p id="p153332030181810"><a name="p153332030181810"></a><a name="p153332030181810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p133341830111815"><a name="p133341830111815"></a><a name="p133341830111815"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row13328133013187"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p6335173014189"><a name="p6335173014189"></a><a name="p6335173014189"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="13.089999999999998%" headers="mcps1.2.5.1.2 "><p id="p1283352611468"><a name="p1283352611468"></a><a name="p1283352611468"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.58%" headers="mcps1.2.5.1.3 "><p id="p19335430171810"><a name="p19335430171810"></a><a name="p19335430171810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1033618300180"><a name="p1033618300180"></a><a name="p1033618300180"></a>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</p>
</td>
</tr>
<tr id="row832873071812"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p2033712306189"><a name="p2033712306189"></a><a name="p2033712306189"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="13.089999999999998%" headers="mcps1.2.5.1.2 "><p id="p108336268468"><a name="p108336268468"></a><a name="p108336268468"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.58%" headers="mcps1.2.5.1.3 "><p id="p833716303187"><a name="p833716303187"></a><a name="p833716303187"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1933910301183"><a name="p1933910301183"></a><a name="p1933910301183"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row83291430161815"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p1633963015187"><a name="p1633963015187"></a><a name="p1633963015187"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="13.089999999999998%" headers="mcps1.2.5.1.2 "><p id="p1283392620461"><a name="p1283392620461"></a><a name="p1283392620461"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.58%" headers="mcps1.2.5.1.3 "><p id="p11340130121818"><a name="p11340130121818"></a><a name="p11340130121818"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p3341133051810"><a name="p3341133051810"></a><a name="p3341133051810"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row032923015189"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p16341193018180"><a name="p16341193018180"></a><a name="p16341193018180"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="13.089999999999998%" headers="mcps1.2.5.1.2 "><p id="p98348268465"><a name="p98348268465"></a><a name="p98348268465"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.58%" headers="mcps1.2.5.1.3 "><p id="p10341330181816"><a name="p10341330181816"></a><a name="p10341330181816"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p12343203081817"><a name="p12343203081817"></a><a name="p12343203081817"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row5329183014185"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p33430305186"><a name="p33430305186"></a><a name="p33430305186"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="13.089999999999998%" headers="mcps1.2.5.1.2 "><p id="p17834926174614"><a name="p17834926174614"></a><a name="p17834926174614"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.58%" headers="mcps1.2.5.1.3 "><p id="p8344133014187"><a name="p8344133014187"></a><a name="p8344133014187"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p11344143041815"><a name="p11344143041815"></a><a name="p11344143041815"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the `continue` field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.</p>
<p id="p16345183021815"><a name="p16345183021815"></a><a name="p16345183021815"></a></p>
<p id="p1134513013181"><a name="p1134513013181"></a><a name="p1134513013181"></a>The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row1329530161817"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p034513303184"><a name="p034513303184"></a><a name="p034513303184"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="13.089999999999998%" headers="mcps1.2.5.1.2 "><p id="p483412614611"><a name="p483412614611"></a><a name="p483412614611"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.58%" headers="mcps1.2.5.1.3 "><p id="p12345123001819"><a name="p12345123001819"></a><a name="p12345123001819"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p134613011812"><a name="p134613011812"></a><a name="p134613011812"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row43296305181"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p18347173020184"><a name="p18347173020184"></a><a name="p18347173020184"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="13.089999999999998%" headers="mcps1.2.5.1.2 "><p id="p108341426134610"><a name="p108341426134610"></a><a name="p108341426134610"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.58%" headers="mcps1.2.5.1.3 "><p id="p11347730181813"><a name="p11347730181813"></a><a name="p11347730181813"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1834863014182"><a name="p1834863014182"></a><a name="p1834863014182"></a>Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity.</p>
</td>
</tr>
<tr id="row53291630111812"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p1334853015181"><a name="p1334853015181"></a><a name="p1334853015181"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="13.089999999999998%" headers="mcps1.2.5.1.2 "><p id="p1883472614610"><a name="p1883472614610"></a><a name="p1883472614610"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.58%" headers="mcps1.2.5.1.3 "><p id="p634914302185"><a name="p634914302185"></a><a name="p634914302185"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p17349193012186"><a name="p17349193012186"></a><a name="p17349193012186"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section14350103011185"></a>

无

## 响应参数<a name="section580612429340"></a>

状态码为 200 时:

**表 2**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row1635263014180"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p435343061810"><a name="p435343061810"></a><a name="p435343061810"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p6354193021816"><a name="p6354193021816"></a><a name="p6354193021816"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p2355193018185"><a name="p2355193018185"></a><a name="p2355193018185"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row7352133013188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p2355130171811"><a name="p2355130171811"></a><a name="p2355130171811"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p113560309188"><a name="p113560309188"></a><a name="p113560309188"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p13561730151811"><a name="p13561730151811"></a><a name="p13561730151811"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row20352153021812"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p2357113016180"><a name="p2357113016180"></a><a name="p2357113016180"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p735717308182"><a name="p735717308182"></a><a name="p735717308182"></a>Array of  io.k8s.api.core.v1.Namespace objects</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p5358230111814"><a name="p5358230111814"></a><a name="p5358230111814"></a>Items is the list of Namespace objects in the list. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/</p>
</td>
</tr>
<tr id="row18352630151819"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1536018305185"><a name="p1536018305185"></a><a name="p1536018305185"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16361030101820"><a name="p16361030101820"></a><a name="p16361030101820"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p936173014186"><a name="p936173014186"></a><a name="p936173014186"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="row1835213012185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p4362183021816"><a name="p4362183021816"></a><a name="p4362183021816"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p73621309182"><a name="p73621309182"></a><a name="p73621309182"></a>Array of io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta objects</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1436210305187"><a name="p1436210305187"></a><a name="p1436210305187"></a>Standard list metadata.</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section5883530141815"></a>

无

## 响应示例<a name="section1188373019183"></a>

状态码为 200 时:

```
{
    "apiVersion": "extensions/v1beta1",
    "kind": "ReplicaSet",
    "metadata": {
        "annotations": {
            "deployment.kubernetes.io/desired-replicas": "1",
            "deployment.kubernetes.io/max-replicas": "2",
            "deployment.kubernetes.io/revision": "1"
        },
        "creationTimestamp": "2019-07-03T03:29:52Z",
        "generation": 1,
        "labels": {
            "app": "web-terminal",
            "pod-template-hash": "68cb66c8bf",
            "release": "cceaddon-web-terminal"
        },
        "name": "web-terminal-68cb66c8bf",
        "namespace": "default",
        "ownerReferences": [
            {
                "apiVersion": "apps/v1",
                "blockOwnerDeletion": true,
                "controller": true,
                "kind": "Deployment",
                "name": "web-terminal",
                "uid": "d1d6c18e-9d42-11e9-8d38-fa163eb8e88a"
            }
        ],
        "resourceVersion": "3675383",
        "selfLink": "/apis/extensions/v1beta1/namespaces/default/replicasets/web-terminal-68cb66c8bf",
        "uid": "d1d810bf-9d42-11e9-8d38-fa163eb8e88a"
    },
    "spec": {
        "replicas": 1,
        "selector": {
            "matchLabels": {
                "app": "web-terminal",
                "pod-template-hash": "68cb66c8bf"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "app": "web-terminal",
                    "pod-template-hash": "68cb66c8bf",
                    "release": "cceaddon-web-terminal"
                }
            },
            "spec": {
                "containers": [
                    {
                        "env": [
                            {
                                "name": "PASSWORD",
                                "value": ""
                            }
                        ],
                        "image": "10.79.1.215:20202/hwofficial/web-terminal:1.0.2",
                        "imagePullPolicy": "IfNotPresent",
                        "name": "web-terminal",
                        "resources": {
                            "limits": {
                                "cpu": "200m",
                                "memory": "512Mi"
                            },
                            "requests": {
                                "cpu": "100m",
                                "memory": "256Mi"
                            }
                        },
                        "terminationMessagePath": "/dev/termination-log",
                        "terminationMessagePolicy": "File"
                    }
                ],
                "dnsPolicy": "ClusterFirst",
                "restartPolicy": "Always",
                "schedulerName": "default-scheduler",
                "securityContext": {},
                "serviceAccount": "web-terminal",
                "serviceAccountName": "web-terminal",
                "terminationGracePeriodSeconds": 30
            }
        }
    },
    "status": {
        "availableReplicas": 1,
        "fullyLabeledReplicas": 1,
        "observedGeneration": 1,
        "readyReplicas": 1,
        "replicas": 1
    }
}
```

## 返回值<a name="section19891103071813"></a>

<a name="table511"></a>
<table><thead align="left"><tr id="row12538123091810"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p10891230181820"><a name="p10891230181820"></a><a name="p10891230181820"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p14891530111816"><a name="p14891530111816"></a><a name="p14891530111816"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row155381230121813"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p689163061815"><a name="p689163061815"></a><a name="p689163061815"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p289163021811"><a name="p289163021811"></a><a name="p289163021811"></a>OK</p>
</td>
</tr>
<tr id="row12538183017180"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p15891030171811"><a name="p15891030171811"></a><a name="p15891030171811"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p118921530121818"><a name="p118921530121818"></a><a name="p118921530121818"></a>Unauthorized</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section889214305184"></a>

无

