# 列出所有Job<a name="cce_02_0165"></a>

## 功能介绍<a name="section16726625"></a>

This API is used to obtain a Job list.

## URI<a name="section16321901"></a>

GET /apis/batch/v1/jobs

[表1](#d0e42328)描述该API的参数。

**表 1**  参数解释

<a name="d0e42328"></a>
<table><thead align="left"><tr id="row18545824"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="27%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row380171"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p30793901"><a name="p30793901"></a><a name="p30793901"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p11278076"><a name="p11278076"></a><a name="p11278076"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p41108959"><a name="p41108959"></a><a name="p41108959"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row34436316"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p37878201"><a name="p37878201"></a><a name="p37878201"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p48235422"><a name="p48235422"></a><a name="p48235422"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p14755124"><a name="p14755124"></a><a name="p14755124"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row65687257"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p19067578"><a name="p19067578"></a><a name="p19067578"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p970017"><a name="p970017"></a><a name="p970017"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p36053777"><a name="p36053777"></a><a name="p36053777"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row56048538"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p43637758"><a name="p43637758"></a><a name="p43637758"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p44997510"><a name="p44997510"></a><a name="p44997510"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p20919707"><a name="p20919707"></a><a name="p20919707"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row54059637"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p16754504"><a name="p16754504"></a><a name="p16754504"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p14937563"><a name="p14937563"></a><a name="p14937563"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p1983062"><a name="p1983062"></a><a name="p1983062"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="row17847562"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p36366454"><a name="p36366454"></a><a name="p36366454"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p60001629"><a name="p60001629"></a><a name="p60001629"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p28293801"><a name="p28293801"></a><a name="p28293801"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row53317625"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p23760343"><a name="p23760343"></a><a name="p23760343"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p45539597"><a name="p45539597"></a><a name="p45539597"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p64828740"><a name="p64828740"></a><a name="p64828740"></a>Timeout for the list/watch call.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section12679389"></a>

N/A

## 响应消息<a name="section47005641"></a>

**响应参数：**

响应参数的详细描述请参见[表4](公共响应参数.md#zh-cn_topic_0079614930_table6622802)。

**响应示例：**

```
{
    "kind": "JobList",
    "apiVersion": "batch/v1",
    "metadata": {
        "selfLink": "/apis/batch/v1/jobs",
        "resourceVersion": "419065"
    },
    "items": [
        {
            "metadata": {
                "name": "jobs-12130306",
                "namespace": "ns-12130306-s",
                "selfLink": "/apis/batch/v1/namespaces/ns-12130306-s/jobs/jobs-12130306",
                "uid": "eed6b02b-dfb3-11e7-9c19-fa163e2d897b",
                "resourceVersion": "419064",
                "creationTimestamp": "2017-12-13T03:15:55Z",
                "labels": {
                    "name": "job-test"
                },
                "enable": true
            },
            "spec": {
                "parallelism": 1,
                "completions": 1,
                "selector": {
                    "matchLabels": {
                        "controller-uid": "eed6b02b-dfb3-11e7-9c19-fa163e2d897b"
                    }
                },
                "template": {
                    "metadata": {
                        "name": "jobs-12130306",
                        "creationTimestamp": null,
                        "labels": {
                            "controller-uid": "eed6b02b-dfb3-11e7-9c19-fa163e2d897b",
                            "job-name": "jobs-12130306",
                            "name": "job-test"
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "jobs-12130306",
                                "image": "172.16.5.235:20202/test/redis:latest",
                                "resources": {},
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "Always"
                            }
                        ],
                        "restartPolicy": "Never",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "ClusterFirst",
                        "securityContext": {},
                        "schedulerName": "default-scheduler"
                    }
                }
            },
            "status": {
                "startTime": "2017-12-13T03:15:55Z",
                "active": 1
            }
        }
    ]
}
```

## 状态码<a name="section20397585"></a>

[表2](#d0e42449)描述API的状态码。

**表 2**  状态码

<a name="d0e42449"></a>
<table><thead align="left"><tr id="row61111097"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p51051833"><a name="p51051833"></a><a name="p51051833"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p41557789"><a name="p41557789"></a><a name="p41557789"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row10737742"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p64450739"><a name="p64450739"></a><a name="p64450739"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p53127348"><a name="p53127348"></a><a name="p53127348"></a>This operation succeeds, and the Job of a group of Pod objects are returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

