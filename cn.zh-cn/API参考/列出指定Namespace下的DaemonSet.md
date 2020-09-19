# 列出指定Namespace下的DaemonSet<a name="cce_02_0142"></a>

## 功能介绍<a name="section3005973"></a>

This API is used to list all DaemonSet resource objects under a specified Namespace.

## URI<a name="section27053763"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/daemonsets \(Supports 1.9 and 1.9+\)

GET /apis/extensions/v1beta1/namespaces/\{namespace\}/daemonsets \(Supports 1.15 and 1.15-\)

[表1](#d0e33074)描述该API的参数。

**表 1**  参数解释

<a name="d0e33074"></a>
<table><thead align="left"><tr id="row36987783"><th class="cellrowborder" valign="top" width="18.18%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="64.64999999999999%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15972553"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p18708431"><a name="p18708431"></a><a name="p18708431"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p38987949"><a name="p38987949"></a><a name="p38987949"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p3907340"><a name="p3907340"></a><a name="p3907340"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row35166068"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p29879222"><a name="p29879222"></a><a name="p29879222"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p4297933"><a name="p4297933"></a><a name="p4297933"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p12588321"><a name="p12588321"></a><a name="p12588321"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row46186029"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p50080870"><a name="p50080870"></a><a name="p50080870"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p30018704"><a name="p30018704"></a><a name="p30018704"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p6146157"><a name="p6146157"></a><a name="p6146157"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row55315414"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p51363521"><a name="p51363521"></a><a name="p51363521"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p66804541"><a name="p66804541"></a><a name="p66804541"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p42458737"><a name="p42458737"></a><a name="p42458737"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row46584320"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p15233596"><a name="p15233596"></a><a name="p15233596"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p25961797"><a name="p25961797"></a><a name="p25961797"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p22530818"><a name="p22530818"></a><a name="p22530818"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row1450776"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p50404031"><a name="p50404031"></a><a name="p50404031"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p56194702"><a name="p56194702"></a><a name="p56194702"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p55477038"><a name="p55477038"></a><a name="p55477038"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row29531300"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p43225088"><a name="p43225088"></a><a name="p43225088"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p11571200"><a name="p11571200"></a><a name="p11571200"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p64851980"><a name="p64851980"></a><a name="p64851980"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row46796915"><td class="cellrowborder" valign="top" width="18.18%" headers="mcps1.2.4.1.1 "><p id="p32453757"><a name="p32453757"></a><a name="p32453757"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p11508680"><a name="p11508680"></a><a name="p11508680"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.4.1.3 "><p id="p59787900"><a name="p59787900"></a><a name="p59787900"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section42157279"></a>

N/A

## 响应消息<a name="section43871194"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建DaemonSet.md#d0e31376)。

**响应示例：**

```
{
    "kind": "DaemonSetList",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/daemonsets",
        "resourceVersion": "419006"
    },
    "items": [
        {
            "metadata": {
                "name": "ds-12130306",
                "namespace": "ns-12130306-s",
                "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/daemonsets/ds-12130306",
                "uid": "dc72a82b-dfb3-11e7-9c19-fa163e2d897b",
                "resourceVersion": "419004",
                "generation": 1,
                "creationTimestamp": "2017-12-13T03:15:24Z",
                "labels": {
                    "name": "daemonset-test"
                },
                "enable": true
            },
            "spec": {
                "selector": {
                    "matchLabels": {
                        "name": "daemonset-test"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "name": "daemonset-test"
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "dscon-12130306",
                                "image": "172.16.5.235:20202/test/redis:latest",
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
                },
                "updateStrategy": {
                    "type": "OnDelete"
                },
                "templateGeneration": 1,
                "revisionHistoryLimit": 10
            },
            "status": {
                "currentNumberScheduled": 1,
                "numberMisscheduled": 0,
                "desiredNumberScheduled": 1,
                "numberReady": 0,
                "observedGeneration": 1,
                "updatedNumberScheduled": 1,
                "numberUnavailable": 1
            }
        }
    ]
}
```

## 状态码<a name="section59296429"></a>

[表2](#d0e33203)描述API的状态码。

**表 2**  状态码

<a name="d0e33203"></a>
<table><thead align="left"><tr id="row1501169"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p54485863"><a name="p54485863"></a><a name="p54485863"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p51278753"><a name="p51278753"></a><a name="p51278753"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row59938311"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p23165059"><a name="p23165059"></a><a name="p23165059"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p64430458"><a name="p64430458"></a><a name="p64430458"></a>This operation succeeds, and a DaemonSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

