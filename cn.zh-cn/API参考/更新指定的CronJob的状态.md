# 更新指定的CronJob的状态<a name="cce_02_0234"></a>

## 功能介绍<a name="section21968375"></a>

This API is used to update the status of a specified CronJob under a specified Namespace.

## URI<a name="section63497648"></a>

PATCH /apis/batch/v1beta1/namespaces/\{namespace\}/cronjobs/\{name\}/status

[表1](#d0e42516)描述该API的参数。

**表 1**  参数解释

<a name="d0e42516"></a>
<table><thead align="left"><tr id="row63644049"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.15%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="62.629999999999995%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row31205664"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p44630865"><a name="p44630865"></a><a name="p44630865"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p58330314"><a name="p58330314"></a><a name="p58330314"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p27135028"><a name="p27135028"></a><a name="p27135028"></a>Name of the Job.</p>
</td>
</tr>
<tr id="row42888667"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p51430001"><a name="p51430001"></a><a name="p51430001"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p5080523"><a name="p5080523"></a><a name="p5080523"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p8869201"><a name="p8869201"></a><a name="p8869201"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row12713953"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p23197269"><a name="p23197269"></a><a name="p23197269"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p67039530"><a name="p67039530"></a><a name="p67039530"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p61492872"><a name="p61492872"></a><a name="p61492872"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section34607923"></a>

**请求参数：**

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/json-patch+json 
"status": {
    "active": [
        {
            "apiVersion": "batch",
            "kind": "Job",
            "name": "cronjob-test-1520425800",
            "namespace": "default",
            "resourceVersion": "442542",
            "uid": "75aede3f-2203-11e8-96aa-fa163ecd089c"
        }
    ],
    "lastScheduleTime": "2018-03-07T12:30:00Z"
}
```

## 响应消息<a name="section43035858"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建CronJob.md#table8040885)。

**响应示例：**

```
{
    "apiVersion": "batch/v1beta1",
    "kind": "CronJob",
    "metadata": {
        "creationTimestamp": "2018-03-07T12:17:22Z",
        "enable": true,
        "name": "cronjob-test",
        "namespace": "default",
        "resourceVersion": "442543",
        "selfLink": "/apis/batch/v1beta1/namespaces/default/cronjobs/cronjob-test",
        "uid": "7cf2c54b-2201-11e8-96aa-fa163ecd089c"
    },
    "spec": {
        "concurrencyPolicy": "Forbid",
        "failedJobsHistoryLimit": 1,
        "jobTemplate": {
            "metadata": {
                "creationTimestamp": null,
                "enable": true
            },
            "spec": {
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "enable": true,
                        "labels": {
                            "sjname": "cronjob-test"
                        }
                    },
                    "spec": {
                        "containers": [
                            {
                                "image": "nginx:stable-perl",
                                "imagePullPolicy": "IfNotPresent",
                                "lifecycle": {},
                                "name": "container-0",
                                "resources": {},
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File"
                            }
                        ],
                        "dnsPolicy": "ClusterFirst",
                        "imagePullSecrets": [
                            {
                                "name": "default-secret"
                            }
                        ],
                        "restartPolicy": "OnFailure",
                        "schedulerName": "default-scheduler",
                        "securityContext": {},
                        "terminationGracePeriodSeconds": 30
                    }
                }
            }
        },
        "schedule": "*/2 * * * *",
        "successfulJobsHistoryLimit": 3,
        "suspend": false
    },
    "status": {
        "active": [
            {
                "apiVersion": "batch",
                "kind": "Job",
                "name": "cronjob-test-1520425800",
                "namespace": "default",
                "resourceVersion": "442542",
                "uid": "75aede3f-2203-11e8-96aa-fa163ecd089c"
            }
        ],
        "lastScheduleTime": "2018-03-07T12:30:00Z"
    }
}
```

## 状态码<a name="section51778404"></a>

[表2](#d0e42609)描述API的状态码。

**表 2**  状态码

<a name="d0e42609"></a>
<table><thead align="left"><tr id="row22100021"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p45271266"><a name="p45271266"></a><a name="p45271266"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p43093911"><a name="p43093911"></a><a name="p43093911"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row945917"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p9510459"><a name="p9510459"></a><a name="p9510459"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p32149754"><a name="p32149754"></a><a name="p32149754"></a>This operation succeeds, and a Job resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

