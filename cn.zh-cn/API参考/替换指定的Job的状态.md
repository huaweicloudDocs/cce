# 替换指定的Job的状态<a name="cce_02_0163"></a>

## 功能介绍<a name="section43760555"></a>

This API is used to replace status of the specified Job.

## URI<a name="section58300681"></a>

PUT /apis/batch/v1/namespaces/\{namespace\}/jobs/\{name\}/status

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
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p26060242"><a name="p26060242"></a><a name="p26060242"></a>name of the Job</p>
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

请求参数的详细描述请参见[表2](创建Job.md#table8040885)。

**请求示例：**

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

## 响应消息<a name="section24734697"></a>

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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p21592892"><a name="p21592892"></a><a name="p21592892"></a>This operation succeeds, and a Job resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

