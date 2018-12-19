# 列出指定Namespace下的Job<a name="cce_02_0164"></a>

## 功能介绍<a name="section51751064"></a>

This API is used to list all Jod resource objects under a specified Namespace.

## URI<a name="section63106395"></a>

GET /apis/batch/v1/namespaces/\{namespace\}/jobs

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
<tbody><tr id="row40994086"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p32186706"><a name="p32186706"></a><a name="p32186706"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p56986361"><a name="p56986361"></a><a name="p56986361"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p52492549"><a name="p52492549"></a><a name="p52492549"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row2670901"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p15016403"><a name="p15016403"></a><a name="p15016403"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p8369097"><a name="p8369097"></a><a name="p8369097"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p6808256"><a name="p6808256"></a><a name="p6808256"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row61274307"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p64271838"><a name="p64271838"></a><a name="p64271838"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p38636365"><a name="p38636365"></a><a name="p38636365"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p42537849"><a name="p42537849"></a><a name="p42537849"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row47296321"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p5796754"><a name="p5796754"></a><a name="p5796754"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p66883924"><a name="p66883924"></a><a name="p66883924"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p37345572"><a name="p37345572"></a><a name="p37345572"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row565833"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p45832525"><a name="p45832525"></a><a name="p45832525"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p21447008"><a name="p21447008"></a><a name="p21447008"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p59486125"><a name="p59486125"></a><a name="p59486125"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="row65613080"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p13059244"><a name="p13059244"></a><a name="p13059244"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p51165837"><a name="p51165837"></a><a name="p51165837"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p50792098"><a name="p50792098"></a><a name="p50792098"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row54475699"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p50455538"><a name="p50455538"></a><a name="p50455538"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p60366810"><a name="p60366810"></a><a name="p60366810"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p57873426"><a name="p57873426"></a><a name="p57873426"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row51098787"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p45361111"><a name="p45361111"></a><a name="p45361111"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="p50371375"><a name="p50371375"></a><a name="p50371375"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p53549588"><a name="p53549588"></a><a name="p53549588"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section31086645"></a>

N/A

## 响应消息<a name="section11344351"></a>

**响应参数：**

响应参数的详细描述请参见[表4](公共响应参数.md#zh-cn_topic_0079614930_table6622802)。

**响应示例：**

```
{
    "kind": "JobList",
    "apiVersion": "batch/v1",
    "metadata": {
        "selfLink": "/apis/batch/v1/namespaces/default/jobs",
        "resourceVersion": "7589"
    },
    "items": [
        {
            "metadata": {
                "name": "",
                "namespace": "default",
                "selfLink": "/apis/batch/v1/namespaces/default/jobs/",
                "uid": "d93a3569-a2be-11e6-a008-fa043d458cc7",
                "resourceVersion": "7482",
                "creationTimestamp": "2016-11-04T18:45:25Z"
            },
            "spec": {
                "parallelism": 1,
                "completions": 1,
                "selector": {
                    "matchLabels": {
                        "controller-uid": "d93a3569-a2be-11e6-a008-fa043d458cc7"
                    }
                },
                "template": {
                    "metadata": {
                        "name": "",
                        "creationTimestamp": null,
                        "labels": {
                            "controller-uid": "d93a3569-a2be-11e6-a008-fa043d458cc7",
                            "job-name": ""
                        }
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "pi",
                                "image": "perl",
                                "command": [
                                    "perl",
                                    "-Mbignum=bpi",
                                    "-wle",
                                    "print bpi(2000)"
                                ],
                                "resources": {},
                                "terminationMessagePath": "/dev/termination-log",
                                "imagePullPolicy": "Always"
                            }
                        ],
                        "restartPolicy": "Never",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "ClusterFirst",
                        "securityContext": {}
                    }
                }
            },
            "status": {
                "startTime": "2016-11-04T18:45:25Z",
                "active": 1
            }
        }
    ]
}
```

## 状态码<a name="section34990298"></a>

[表2](#d0e42261)描述API的状态码。

**表 2**  状态码

<a name="d0e42261"></a>
<table><thead align="left"><tr id="row59414131"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p47815306"><a name="p47815306"></a><a name="p47815306"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p47834569"><a name="p47834569"></a><a name="p47834569"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49394905"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p41564386"><a name="p41564386"></a><a name="p41564386"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11272075"><a name="p11272075"></a><a name="p11272075"></a>This operation succeeds, and a group of Job resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

