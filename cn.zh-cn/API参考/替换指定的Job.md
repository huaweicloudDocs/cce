# 替换指定的Job<a name="cce_02_0162"></a>

## 功能介绍<a name="section11097543"></a>

This API is used to replace the specified Job.

## URI<a name="section32769029"></a>

PUT /apis/batch/v1/namespaces/\{namespace\}/jobs/\{name\}

[表1](#d0e41812)描述该API的参数。

**表 1**  参数解释

<a name="d0e41812"></a>
<table><thead align="left"><tr id="row66886321"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row43988572"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p6304590"><a name="p6304590"></a><a name="p6304590"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p40909805"><a name="p40909805"></a><a name="p40909805"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p25359904"><a name="p25359904"></a><a name="p25359904"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row26912549"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p32432850"><a name="p32432850"></a><a name="p32432850"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p9815175"><a name="p9815175"></a><a name="p9815175"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p56831725"><a name="p56831725"></a><a name="p56831725"></a>name of the Job</p>
</td>
</tr>
<tr id="row41723482"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p24158859"><a name="p24158859"></a><a name="p24158859"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p10710594"><a name="p10710594"></a><a name="p10710594"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p62251748"><a name="p62251748"></a><a name="p62251748"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="d0e41861"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建Job.md#table8040885)。

**请求示例：**

```
{
    "metadata": {
        "name": "jobs-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/batch/v1/namespaces/ns-12130306-s/jobs/jobs-12130306",
        "uid": "eed6b02b-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "419068",
        "creationTimestamp": "2017-12-13T03:15:55Z",
        "labels": {
            "app": "new-jobs",
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
```

## 响应消息<a name="section37045669"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Job.md#table8040885)。

**响应示例：**

```
{
    "kind": "Job",
    "apiVersion": "batch/v1",
    "metadata": {
        "name": "jobs-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/batch/v1/namespaces/ns-12130306-s/jobs/jobs-12130306",
        "uid": "eed6b02b-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "419068",
        "creationTimestamp": "2017-12-13T03:15:55Z",
        "labels": {
            "app": "new-jobs",
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
```

## 状态码<a name="section64975570"></a>

[表2](#d0e41904)描述API的状态码。

**表 2**  状态码

<a name="d0e41904"></a>
<table><thead align="left"><tr id="row40602325"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p453999"><a name="p453999"></a><a name="p453999"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p36773941"><a name="p36773941"></a><a name="p36773941"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row25899281"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p17466984"><a name="p17466984"></a><a name="p17466984"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p5539620"><a name="p5539620"></a><a name="p5539620"></a>This operation succeeds, and a Job resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

