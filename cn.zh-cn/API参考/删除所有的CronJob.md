# 删除所有的CronJob<a name="cce_02_0227"></a>

## 功能介绍<a name="section19866817"></a>

This API is used to delete collection of CronJob.

## URI<a name="section44583626"></a>

DELETE /apis/batch/v1beta1/namespaces/\{namespace\}/cronjobs

[表1](#d0e41256)描述该API的参数。

**表 1**  参数解释

<a name="d0e41256"></a>
<table><thead align="left"><tr id="row32355125"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="63%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row56345869"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p612709"><a name="p612709"></a><a name="p612709"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p49629453"><a name="p49629453"></a><a name="p49629453"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p60562733"><a name="p60562733"></a><a name="p60562733"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row8193690"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p59709154"><a name="p59709154"></a><a name="p59709154"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p4603319"><a name="p4603319"></a><a name="p4603319"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p37324544"><a name="p37324544"></a><a name="p37324544"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row376580"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p30502999"><a name="p30502999"></a><a name="p30502999"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p54823826"><a name="p54823826"></a><a name="p54823826"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p11544926"><a name="p11544926"></a><a name="p11544926"></a>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</p>
</td>
</tr>
<tr id="row36795474"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p27643385"><a name="p27643385"></a><a name="p27643385"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p24521733"><a name="p24521733"></a><a name="p24521733"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p40103390"><a name="p40103390"></a><a name="p40103390"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row25386195"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p43015881"><a name="p43015881"></a><a name="p43015881"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p61734336"><a name="p61734336"></a><a name="p61734336"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p34425311"><a name="p34425311"></a><a name="p34425311"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row41392350"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p64446029"><a name="p64446029"></a><a name="p64446029"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p52745849"><a name="p52745849"></a><a name="p52745849"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p44555337"><a name="p44555337"></a><a name="p44555337"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row65453714"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p150612"><a name="p150612"></a><a name="p150612"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p12199598"><a name="p12199598"></a><a name="p12199598"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p48643401"><a name="p48643401"></a><a name="p48643401"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the continue field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true. The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row35137430"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p27559605"><a name="p27559605"></a><a name="p27559605"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p17735528"><a name="p17735528"></a><a name="p17735528"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p27291672"><a name="p27291672"></a><a name="p27291672"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row44298458"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p31405327"><a name="p31405327"></a><a name="p31405327"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p60803573"><a name="p60803573"></a><a name="p60803573"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p26142387"><a name="p26142387"></a><a name="p26142387"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row33954899"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p65992330"><a name="p65992330"></a><a name="p65992330"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p43778476"><a name="p43778476"></a><a name="p43778476"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63%" headers="mcps1.2.4.1.3 "><p id="p56395683"><a name="p56395683"></a><a name="p56395683"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section65708320"></a>

**请求参数：**

请求参数的详细描述请参见[表2](删除Job.md#d0e41006)。

**请求示例：**

-   只删除CronJob（对应Job和Pod不删除）

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "gracePeriodSeconds": 0,
        "propagationPolicy": "Orphan"
    }
    ```

-   前台级联删除（按照Pod-\>Job-\>CronJob的顺序进行删除）

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Foreground"
    }
    ```

-   后台级联删除（按照CronJob-\>Job-\>Pod的顺序进行删除）

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Background"
    }
    ```


## 响应消息<a name="section54503971"></a>

**响应参数：**

响应参数的详细描述请参见[表22](响应数据结构.md#t6c6ba0cfa7084a419291c2d12d305875)。

**响应示例：**

```
{
  "kind": "CronJobList",
  "apiVersion": "batch/v1beta1",
  "metadata": {
    "selfLink": "/apis/batch/v1beta1/namespaces/default/cronjobs",
    "resourceVersion": "441539"
  },
  "items": [
    {
      "metadata": {
        "name": "cronjob-test",
        "namespace": "default",
        "selfLink": "/apis/batch/v1beta1/namespaces/default/cronjobs/cronjob-test",
        "uid": "53ea08bb-2201-11e8-96aa-fa163ecd089c",
        "resourceVersion": "441513",
        "creationTimestamp": "2018-03-07T12:16:13Z",
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
  ]
}
```

## 状态码<a name="section20773692"></a>

[表2](#d0e41404)描述API的状态码。

**表 2**  状态码

<a name="d0e41404"></a>
<table><thead align="left"><tr id="row65506768"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p4447995"><a name="p4447995"></a><a name="p4447995"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p24743290"><a name="p24743290"></a><a name="p24743290"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row58049462"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p4385942"><a name="p4385942"></a><a name="p4385942"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p19716994"><a name="p19716994"></a><a name="p19716994"></a>Delete a Job resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

