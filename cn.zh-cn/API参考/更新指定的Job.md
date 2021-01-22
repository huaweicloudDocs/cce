# 更新指定的Job<a name="cce_02_0167"></a>

## 功能介绍<a name="section44235199"></a>

This API is used to update the specified Job.

The following fields can be updated:

-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.creationTimestamp
-   metadata.name
-   metadata.namespace
-   metadata.labels
-   spec.parallelism
-   spec.completions
-   spec.selector

## URI<a name="section62572474"></a>

PATCH /apis/batch/v1/namespaces/\{namespace\}/jobs/\{name\}

[表1](#d0e42697)描述该API的参数。

**表 1**  参数解释

<a name="d0e42697"></a>
<table><thead align="left"><tr id="row25506777"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.61%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row63715316"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p60666976"><a name="p60666976"></a><a name="p60666976"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p15078020"><a name="p15078020"></a><a name="p15078020"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p13360137"><a name="p13360137"></a><a name="p13360137"></a>name of the Job</p>
</td>
</tr>
<tr id="row53132375"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p8755152"><a name="p8755152"></a><a name="p8755152"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p38078717"><a name="p38078717"></a><a name="p38078717"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p64477255"><a name="p64477255"></a><a name="p64477255"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row43424386"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p27714369"><a name="p27714369"></a><a name="p27714369"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p30271441"><a name="p30271441"></a><a name="p30271441"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p36067674"><a name="p36067674"></a><a name="p36067674"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section26281361"></a>

**请求参数：**

“Content-Type“消息头说明请参见[PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/merge-patch+json
```

```
{
    "op": "replace",
    "path": "/status",
    "value": "Available"
}
```

## 响应消息<a name="section35205659"></a>

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
        "resourceVersion": "419066",
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
                        "image": "10.125.5.235:20202/test/redis:latest",
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

## 状态码<a name="section48415483"></a>

[表2](#d0e42791)描述API的状态码。

**表 2**  状态码

<a name="d0e42791"></a>
<table><thead align="left"><tr id="row7304508"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p54794282"><a name="p54794282"></a><a name="p54794282"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p9151897"><a name="p9151897"></a><a name="p9151897"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row3106225"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p50277657"><a name="p50277657"></a><a name="p50277657"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p45958393"><a name="p45958393"></a><a name="p45958393"></a>This operation succeeds, and a Job resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

