# 删除所有的Pod<a name="cce_02_0116"></a>

## 功能介绍<a name="section45237642"></a>

This API is used to delete collection of Pod.

## URI<a name="section4485596"></a>

DELETE /api/v1/namespaces/\{namespace\}/pods

[表1](#d0e21437)描述该API的参数。

**表 1**  参数解释

<a name="d0e21437"></a>
<table><thead align="left"><tr id="row57643933"><th class="cellrowborder" valign="top" width="22.45%" id="mcps1.2.4.1.1"><p id="p38646995"><a name="p38646995"></a><a name="p38646995"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.33%" id="mcps1.2.4.1.2"><p id="p43398861"><a name="p43398861"></a><a name="p43398861"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61.22%" id="mcps1.2.4.1.3"><p id="p25646835"><a name="p25646835"></a><a name="p25646835"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row64127791"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p26968550"><a name="p26968550"></a><a name="p26968550"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p36968962"><a name="p36968962"></a><a name="p36968962"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p41695979"><a name="p41695979"></a><a name="p41695979"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row39719496"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p63162574"><a name="p63162574"></a><a name="p63162574"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p15894869"><a name="p15894869"></a><a name="p15894869"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p12416004"><a name="p12416004"></a><a name="p12416004"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row44635179"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p58679722"><a name="p58679722"></a><a name="p58679722"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p55437030"><a name="p55437030"></a><a name="p55437030"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p61214406"><a name="p61214406"></a><a name="p61214406"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row14058743"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p65016393"><a name="p65016393"></a><a name="p65016393"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p31836467"><a name="p31836467"></a><a name="p31836467"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p28617054"><a name="p28617054"></a><a name="p28617054"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row56226899"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p58084994"><a name="p58084994"></a><a name="p58084994"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p7264069"><a name="p7264069"></a><a name="p7264069"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p51518725"><a name="p51518725"></a><a name="p51518725"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row61015343"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p43295732"><a name="p43295732"></a><a name="p43295732"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p17293418"><a name="p17293418"></a><a name="p17293418"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p58589624"><a name="p58589624"></a><a name="p58589624"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row57544576"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p30599111"><a name="p30599111"></a><a name="p30599111"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p62608889"><a name="p62608889"></a><a name="p62608889"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p38155264"><a name="p38155264"></a><a name="p38155264"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row7853063"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p32118376"><a name="p32118376"></a><a name="p32118376"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p51451665"><a name="p51451665"></a><a name="p51451665"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p6835371"><a name="p6835371"></a><a name="p6835371"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## Request<a name="section40370367"></a>

N/A

## 响应消息<a name="section27788989"></a>

**响应参数：**

响应参数的详细描述请参见[表4](公共响应参数.md#zh-cn_topic_0079614930_table6622802)。

响应示例：

```
{
    "kind": "PodList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/delns-12130306/pods",
        "resourceVersion": "419153"
    },
    "items": [
        {
            "metadata": {
                "name": "pod-del-12130306",
                "namespace": "delns-12130306",
                "selfLink": "/api/v1/namespaces/delns-12130306/pods/pod-del-12130306",
                "uid": "026331da-dfb4-11e7-9c19-fa163e2d897b",
                "resourceVersion": "419153",
                "creationTimestamp": "2017-12-13T03:16:28Z",
                "labels": {
                    "cce/appgroup": "container"
                },
                "annotations": {
                    "kubernetes.io/availablezone": ""
                },
                "enable": true
            },
            "spec": {
                "volumes": [
                    {
                        "name": "default-token-zx6gk",
                        "secret": {
                            "secretName": "default-token-zx6gk",
                            "defaultMode": 384
                        }
                    }
                ],
                "containers": [
                    {
                        "name": "podcon-12130306",
                        "image": "172.16.5.235:20202/test/redis:v1",
                        "ports": [
                            {
                                "name": "tcp",
                                "containerPort": 80,
                                "protocol": "TCP"
                            }
                        ],
                        "resources": {},
                        "volumeMounts": [
                            {
                                "name": "default-token-zx6gk",
                                "readOnly": true,
                                "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount"
                            }
                        ],
                        "terminationMessagePath": "/dev/termination-log",
                        "terminationMessagePolicy": "File",
                        "imagePullPolicy": "IfNotPresent"
                    }
                ],
                "restartPolicy": "Always",
                "terminationGracePeriodSeconds": 30,
                "dnsPolicy": "ClusterFirst",
                "serviceAccountName": "default",
                "serviceAccount": "default",
                "nodeName": "192.168.0.197",
                "securityContext": {},
                "schedulerName": "default-scheduler"
            },
            "status": {
                "phase": "Pending",
                "conditions": [
                    {
                        "type": "Initialized",
                        "status": "True",
                        "lastProbeTime": null,
                        "lastTransitionTime": "2017-12-13T03:16:28Z"
                    },
                    {
                        "type": "Ready",
                        "status": "False",
                        "lastProbeTime": null,
                        "lastTransitionTime": "2017-12-13T03:16:28Z",
                        "reason": "ContainersNotReady",
                        "message": "containers with unready status: [podcon-12130306]"
                    },
                    {
                        "type": "PodScheduled",
                        "status": "True",
                        "lastProbeTime": null,
                        "lastTransitionTime": "2017-12-13T03:16:28Z"
                    }
                ],
                "hostIP": "192.168.0.197",
                "managementIP": "192.168.0.197",
                "startTime": "2017-12-13T03:16:28Z",
                "containerStatuses": [
                    {
                        "name": "podcon-12130306",
                        "state": {
                            "waiting": {
                                "reason": "ContainerCreating"
                            }
                        },
                        "lastState": {},
                        "ready": false,
                        "restartCount": 0,
                        "image": "172.16.5.235:20202/test/redis:v1",
                        "imageID": ""
                    }
                ],
                "qosClass": "BestEffort"
            }
        }
    ]
}
```

## 状态码<a name="section48774309"></a>

[表2](#d0e21565)描述API的状态码。

**表 2**  状态码

<a name="d0e21565"></a>
<table><thead align="left"><tr id="row9708404"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p48183242"><a name="p48183242"></a><a name="p48183242"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p10528566"><a name="p10528566"></a><a name="p10528566"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row47507485"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p22901097"><a name="p22901097"></a><a name="p22901097"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p43049602"><a name="p43049602"></a><a name="p43049602"></a>Delete a DaemonSet resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

