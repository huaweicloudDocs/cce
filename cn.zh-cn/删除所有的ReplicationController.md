# 删除所有的ReplicationController<a name="cce_02_0115"></a>

## 功能介绍<a name="section8059889"></a>

This API is used to delete collection of ReplicationController.

## URI<a name="section5430140"></a>

DELETE /api/v1/namespaces/\{namespace\}/replicationcontrollers

[表1](#d0e16442)描述该API的参数。

**表 1**  参数解释

<a name="d0e16442"></a>
<table><thead align="left"><tr id="row53393491"><th class="cellrowborder" valign="top" width="22.45%" id="mcps1.2.4.1.1"><p id="p29905529"><a name="p29905529"></a><a name="p29905529"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.33%" id="mcps1.2.4.1.2"><p id="p6428791"><a name="p6428791"></a><a name="p6428791"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61.22%" id="mcps1.2.4.1.3"><p id="p50970102"><a name="p50970102"></a><a name="p50970102"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row34937630"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p11375766"><a name="p11375766"></a><a name="p11375766"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p49021830"><a name="p49021830"></a><a name="p49021830"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p11345303"><a name="p11345303"></a><a name="p11345303"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row34998867"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p16335992"><a name="p16335992"></a><a name="p16335992"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p48146961"><a name="p48146961"></a><a name="p48146961"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p7589767"><a name="p7589767"></a><a name="p7589767"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row1199040"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p30013387"><a name="p30013387"></a><a name="p30013387"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p15165287"><a name="p15165287"></a><a name="p15165287"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p20428731"><a name="p20428731"></a><a name="p20428731"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row49640858"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p61486582"><a name="p61486582"></a><a name="p61486582"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p14357279"><a name="p14357279"></a><a name="p14357279"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p22088956"><a name="p22088956"></a><a name="p22088956"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row64582882"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p63830953"><a name="p63830953"></a><a name="p63830953"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p2924696"><a name="p2924696"></a><a name="p2924696"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p35573848"><a name="p35573848"></a><a name="p35573848"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row51729182"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p29314202"><a name="p29314202"></a><a name="p29314202"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p25640122"><a name="p25640122"></a><a name="p25640122"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p63583974"><a name="p63583974"></a><a name="p63583974"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row35384861"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p47601479"><a name="p47601479"></a><a name="p47601479"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p30514610"><a name="p30514610"></a><a name="p30514610"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p55764358"><a name="p55764358"></a><a name="p55764358"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row32117174"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p51354297"><a name="p51354297"></a><a name="p51354297"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p66057401"><a name="p66057401"></a><a name="p66057401"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p49049245"><a name="p49049245"></a><a name="p49049245"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## Request<a name="section48871261"></a>

N/A

## 响应消息<a name="section37188165"></a>

**响应参数：**

响应参数的详细描述请参见[表2](公共响应参数.md#zh-cn_topic_0079614930_table5881294)。

响应示例：

```
{
    "kind": "ReplicationControllerList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/delns-12130306/replicationcontrollers",
        "resourceVersion": "419242"
    },
    "items": [
        {
            "metadata": {
                "name": "rc-del-12130306",
                "namespace": "delns-12130306",
                "selfLink": "/api/v1/namespaces/delns-12130306/replicationcontrollers/rc-del-12130306",
                "uid": "1465eea3-dfb4-11e7-9c19-fa163e2d897b",
                "resourceVersion": "419242",
                "generation": 1,
                "creationTimestamp": "2017-12-13T03:16:58Z",
                "labels": {
                    "cce/appgroup": "test"
                },
                "enable": true
            },
            "spec": {
                "replicas": 0,
                "selector": {
                    "cce/appgroup": "test"
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "cce/appgroup": "test"
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "rccon-12130306",
                                "image": "172.16.5.235:20202/test/redis:v1",
                                "ports": [
                                    {
                                        "containerPort": 6379,
                                        "protocol": "TCP"
                                    }
                                ],
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
                "replicas": 0,
                "observedGeneration": 1
            }
        }
    ]
}
```

## 状态码<a name="section66258029"></a>

[表2](#d0e16569)描述API的状态码。

**表 2**  状态码

<a name="d0e16569"></a>
<table><thead align="left"><tr id="row16396929"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p53082843"><a name="p53082843"></a><a name="p53082843"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p4743009"><a name="p4743009"></a><a name="p4743009"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row48639485"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p47484180"><a name="p47484180"></a><a name="p47484180"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p21013392"><a name="p21013392"></a><a name="p21013392"></a>Delete a DaemonSet resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

