# 替换指定的CronJob的状态<a name="cce_02_0231"></a>

## 功能介绍<a name="section43760555"></a>

This API is used to replace status of the specified CronJob.

## URI<a name="section58300681"></a>

PUT /apis/batch/v1beta1/namespaces/\{namespace\}/cronjobs/\{name\}/status

[表1](#d0e41971)描述该API的参数。

**表 1**  参数解释

<a name="d0e41971"></a>
<table><thead align="left"><tr id="row65203523"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row59355196"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p43041563"><a name="p43041563"></a><a name="p43041563"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p63814603"><a name="p63814603"></a><a name="p63814603"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1600372"><a name="p1600372"></a><a name="p1600372"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row14403349"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p25820581"><a name="p25820581"></a><a name="p25820581"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p11092289"><a name="p11092289"></a><a name="p11092289"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p26060242"><a name="p26060242"></a><a name="p26060242"></a>name of the CronJob</p>
</td>
</tr>
<tr id="row33215594"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p6108613"><a name="p6108613"></a><a name="p6108613"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p25035657"><a name="p25035657"></a><a name="p25035657"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p14622300"><a name="p14622300"></a><a name="p14622300"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="d0e42020"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建CronJob.md#table8040885)。

**请求示例：**

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

## 响应消息<a name="section24734697"></a>

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

## 状态码<a name="section21285686"></a>

[表2](#d0e42063)描述API的状态码。

**表 2**  状态码

<a name="d0e42063"></a>
<table><thead align="left"><tr id="row42895616"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p51992856"><a name="p51992856"></a><a name="p51992856"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p50671784"><a name="p50671784"></a><a name="p50671784"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row10773849"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p266578"><a name="p266578"></a><a name="p266578"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p21592892"><a name="p21592892"></a><a name="p21592892"></a>This operation succeeds, and a CronJob resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

