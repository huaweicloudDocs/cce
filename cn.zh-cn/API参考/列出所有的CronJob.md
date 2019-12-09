# 列出所有的CronJob<a name="cce_02_0233"></a>

## 功能介绍<a name="section16726625"></a>

This API is used to obtain a CronJob list.

## URI<a name="section16321901"></a>

GET /apis/batch/v1beta1/cronjobs

[表1](#d0e42130)描述该API的参数。

**表 1**  参数解释

<a name="d0e42130"></a>
<table><thead align="left"><tr id="row60594871"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="26%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="41%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row40994086"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p210362011385"><a name="p210362011385"></a><a name="p210362011385"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p15101720153810"><a name="p15101720153810"></a><a name="p15101720153810"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p13100220203815"><a name="p13100220203815"></a><a name="p13100220203815"></a><span>object name and auth scope, such as for teams and projects.</span></p>
</td>
</tr>
<tr id="row2670901"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p5982020133817"><a name="p5982020133817"></a><a name="p5982020133817"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p1096202013383"><a name="p1096202013383"></a><a name="p1096202013383"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p4931520193818"><a name="p4931520193818"></a><a name="p4931520193818"></a>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</p>
</td>
</tr>
<tr id="row61274307"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p0921020163811"><a name="p0921020163811"></a><a name="p0921020163811"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p09117202383"><a name="p09117202383"></a><a name="p09117202383"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p789620143819"><a name="p789620143819"></a><a name="p789620143819"></a><span>A selector to restrict the list of returned objects by their fields. Defaults to everything.</span></p>
</td>
</tr>
<tr id="row47296321"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p288420103817"><a name="p288420103817"></a><a name="p288420103817"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p186920193819"><a name="p186920193819"></a><a name="p186920193819"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p48552015382"><a name="p48552015382"></a><a name="p48552015382"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row565833"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p2083122010387"><a name="p2083122010387"></a><a name="p2083122010387"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p98132033812"><a name="p98132033812"></a><a name="p98132033812"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p8795207385"><a name="p8795207385"></a><a name="p8795207385"></a><span>A selector to restrict the list of returned objects by their labels. Defaults to everything.</span></p>
</td>
</tr>
<tr id="row65613080"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p197815202386"><a name="p197815202386"></a><a name="p197815202386"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p18771620143814"><a name="p18771620143814"></a><a name="p18771620143814"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p9864421104411"><a name="p9864421104411"></a><a name="p9864421104411"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the continuefield on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.</p>
<p id="p686442144418"><a name="p686442144418"></a><a name="p686442144418"></a>The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row54475699"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p12754205380"><a name="p12754205380"></a><a name="p12754205380"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p573920103811"><a name="p573920103811"></a><a name="p573920103811"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p572142011381"><a name="p572142011381"></a><a name="p572142011381"></a><span>If </span><em id="i42947113443"><a name="i42947113443"></a><a name="i42947113443"></a>true</em><span>, then the output is pretty printed.</span></p>
</td>
</tr>
<tr id="row10366920153911"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p20367122011394"><a name="p20367122011394"></a><a name="p20367122011394"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p153689205397"><a name="p153689205397"></a><a name="p153689205397"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p636872093919"><a name="p636872093919"></a><a name="p636872093919"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it’s 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row1963852013398"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p1963852043911"><a name="p1963852043911"></a><a name="p1963852043911"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p163819204391"><a name="p163819204391"></a><a name="p163819204391"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p1163812201398"><a name="p1163812201398"></a><a name="p1163812201398"></a><span>Timeout for the list/watch call.</span></p>
</td>
</tr>
<tr id="row1905102011390"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p6905132010396"><a name="p6905132010396"></a><a name="p6905132010396"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p7905172093917"><a name="p7905172093917"></a><a name="p7905172093917"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p8905192013914"><a name="p8905192013914"></a><a name="p8905192013914"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section12679389"></a>

N/A

## 响应消息<a name="section47005641"></a>

**响应参数：**

响应参数的详细描述请参见[表4](响应数据结构.md#zh-cn_topic_0079614930_table6622802)。

**响应示例：**

```
{
  "kind": "CronJobList",
  "apiVersion": "batch/v1beta1",
  "metadata": {
    "selfLink": "/apis/batch/v1beta1/cronjobs",
    "resourceVersion": "442065"
  },
  "items": [
    {
      "metadata": {
        "name": "cronjob-test",
        "namespace": "default",
        "selfLink": "/apis/batch/v1beta1/namespaces/default/cronjobs/cronjob-test",
        "uid": "7cf2c54b-2201-11e8-96aa-fa163ecd089c",
        "resourceVersion": "441884",
        "creationTimestamp": "2018-03-07T12:17:22Z",
        "enable": true
      },
      "spec": {
        "schedule": "*/59 * * * *",
        "concurrencyPolicy": "Forbid",
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
    },
    {
      "metadata": {
        "name": "cronjob-test11",
        "namespace": "default",
        "selfLink": "/apis/batch/v1beta1/namespaces/default/cronjobs/cronjob-test11",
        "uid": "7b8312a5-2201-11e8-96aa-fa163ecd089c",
        "resourceVersion": "441597",
        "creationTimestamp": "2018-03-07T12:17:19Z",
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
                  "sjname": "cronjob-test11"
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

