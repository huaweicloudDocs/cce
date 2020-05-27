# 获取指定的CronJob的状态<a name="cce_02_0229"></a>

## 功能介绍<a name="section872215"></a>

This API is used to read the status of the specified CronJob.

## URI<a name="section7849943"></a>

GET /apis/batch/v1beta1/namespaces/\{namespace\}/cronjobs/\{name\}/status

[表1](#d0e41637)描述该API的参数。

**表 1**  参数解释

<a name="d0e41637"></a>
<table><thead align="left"><tr id="row38510554"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="36.36363636363636%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row52377634"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p14729974"><a name="p14729974"></a><a name="p14729974"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p52277209"><a name="p52277209"></a><a name="p52277209"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p6595574"><a name="p6595574"></a><a name="p6595574"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row59360169"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p43444365"><a name="p43444365"></a><a name="p43444365"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p29332670"><a name="p29332670"></a><a name="p29332670"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p27136035"><a name="p27136035"></a><a name="p27136035"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row42897724"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p52163659"><a name="p52163659"></a><a name="p52163659"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p64506883"><a name="p64506883"></a><a name="p64506883"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p57675019"><a name="p57675019"></a><a name="p57675019"></a>Name of the CronJob.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section3540627"></a>

N/A

## 响应消息<a name="section31865643"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建CronJob.md#table8040885)。

**响应示例：**

```
{
  "kind": "CronJob",
  "apiVersion": "batch/v1beta1",
  "metadata": {
    "name": "cronjob-test",
    "namespace": "default",
    "selfLink": "/apis/batch/v1beta1/namespaces/default/cronjobs/cronjob-test/status",
    "uid": "7cf2c54b-2201-11e8-96aa-fa163ecd089c",
    "resourceVersion": "441600",
    "creationTimestamp": "2018-03-07T12:17:22Z",
    "enable": true
  },
  "spec": {
    "schedule": "*/59 * * * *",
    "concurrencyPolicy": "Allow",
    "suspend": false,
    "jobTemplate": {
      "metadata": {
        "creationTimestamp": null,
        "enable": true
      },
      "spec": {
        "template": {
          "metadata": {
            "creationTimestamp": null,
            "labels": {
              "sjname": "cronjob-test"
            },
            "enable": true
          },
          "spec": {
            "containers": [
              {
                "name": "container-0",
                "image": "nginx:stable-perl",
                "resources": {

                },
                "lifecycle": {

                },
                "terminationMessagePath": "/dev/termination-log",
                "terminationMessagePolicy": "File",
                "imagePullPolicy": "IfNotPresent"
              }
            ],
            "restartPolicy": "OnFailure",
            "terminationGracePeriodSeconds": 30,
            "dnsPolicy": "ClusterFirst",
            "securityContext": {

            },
            "imagePullSecrets": [
              {
                "name": "default-secret"
              }
            ],
            "schedulerName": "default-scheduler"
          }
        }
      }
    },
    "successfulJobsHistoryLimit": 3,
    "failedJobsHistoryLimit": 1
  },
  "status": {

  }
}
```

## 状态码<a name="section18355338"></a>

[表2](#d0e41716)描述API的状态码。

**表 2**  状态码

<a name="d0e41716"></a>
<table><thead align="left"><tr id="row49104241"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p18020555"><a name="p18020555"></a><a name="p18020555"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p50378833"><a name="p50378833"></a><a name="p50378833"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row54153709"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p24374276"><a name="p24374276"></a><a name="p24374276"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p28159360"><a name="p28159360"></a><a name="p28159360"></a>This operation succeeds, and a CronJob resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

