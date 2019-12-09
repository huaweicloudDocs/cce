# 列出ReplicationController<a name="cce_02_0022"></a>

## 功能介绍<a name="sf5a17335349148eb88d0beb5d3e6e920"></a>

该API用于获取ReplicationController列表。

## URI<a name="s4fb6e4a704534af5b6f7d5b6c4665d0c"></a>

GET /api/v1/replicationcontrollers

[表1](#table133310338720)  描述该API的参数。

**表 1**  参数描述

<a name="table133310338720"></a>
<table><thead align="left"><tr id="row183473319716"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p03416331711"><a name="p03416331711"></a><a name="p03416331711"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.2"><p id="p33415335713"><a name="p33415335713"></a><a name="p33415335713"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="41.41414141414141%" id="mcps1.2.4.1.3"><p id="p53514330710"><a name="p53514330710"></a><a name="p53514330710"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2355331679"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p16351033774"><a name="p16351033774"></a><a name="p16351033774"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.2 "><p id="p11351833570"><a name="p11351833570"></a><a name="p11351833570"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41.41414141414141%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614978_p61885537"><a name="zh-cn_topic_0079614978_p61885537"></a><a name="zh-cn_topic_0079614978_p61885537"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row1935153315716"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p13553319715"><a name="p13553319715"></a><a name="p13553319715"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.2 "><p id="p173533318712"><a name="p173533318712"></a><a name="p173533318712"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41.41414141414141%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614978_p8943813"><a name="zh-cn_topic_0079614978_p8943813"></a><a name="zh-cn_topic_0079614978_p8943813"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row133516333720"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p73518337714"><a name="p73518337714"></a><a name="p73518337714"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.2 "><p id="p2355332715"><a name="p2355332715"></a><a name="p2355332715"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41.41414141414141%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614978_p535220221585"><a name="zh-cn_topic_0079614978_p535220221585"></a><a name="zh-cn_topic_0079614978_p535220221585"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row3358332719"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p9355331273"><a name="p9355331273"></a><a name="p9355331273"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.2 "><p id="p8351633474"><a name="p8351633474"></a><a name="p8351633474"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41.41414141414141%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614978_p43063478"><a name="zh-cn_topic_0079614978_p43063478"></a><a name="zh-cn_topic_0079614978_p43063478"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row203563312716"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p173513335719"><a name="p173513335719"></a><a name="p173513335719"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.2 "><p id="p53573315715"><a name="p53573315715"></a><a name="p53573315715"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41.41414141414141%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614978_p20166978"><a name="zh-cn_topic_0079614978_p20166978"></a><a name="zh-cn_topic_0079614978_p20166978"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="row63511331774"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1636163312715"><a name="p1636163312715"></a><a name="p1636163312715"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.2 "><p id="p6361336711"><a name="p6361336711"></a><a name="p6361336711"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41.41414141414141%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614978_p47823744"><a name="zh-cn_topic_0079614978_p47823744"></a><a name="zh-cn_topic_0079614978_p47823744"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row18362336716"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p13613312719"><a name="p13613312719"></a><a name="p13613312719"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.2 "><p id="p163623310711"><a name="p163623310711"></a><a name="p163623310711"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41.41414141414141%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614978_p66818128"><a name="zh-cn_topic_0079614978_p66818128"></a><a name="zh-cn_topic_0079614978_p66818128"></a>Timeout for the list/watch call.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sca91069f08154e4d8f8c16e143ab22d6"></a>

N/A

## 响应消息<a name="s0ba96b4a4fb8454995065877449ab6db"></a>

**响应参数：**

响应参数的详细描述请参见[表2](响应数据结构.md#zh-cn_topic_0079614930_table5881294)。

**响应示例：**

```
{
    "kind": "ReplicationControllerList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/replicationcontrollers",
        "resourceVersion": "591671"
    },
    "items": [
        {
            "metadata": {
                "name": "rc-test",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/replicationcontrollers/rc-test",
                "uid": "4aabff80-fc1d-11e7-9c3c-fa163eb8ad1a",
                "resourceVersion": "506966",
                "generation": 1,
                "creationTimestamp": "2018-01-18T07:00:39Z",
                "labels": {
                    "name": "rc-test"
                },
                "enable": true
            },
            "spec": {
                "replicas": 1,
                "selector": {
                    "name": "rc-test"
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "name": "rc-test"
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "pod-test",
                                "image": "172.16.5.235:20202/test/nginx",
                                "resources": {},
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "Always"
                            }
                        ],
                        "restartPolicy": "Always",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "ClusterFirst",
                        "securityContext": {},
                        "imagePullSecrets": [
                            {
                                "name": "default-secret"
                            }
                        ],
                        "schedulerName": "default-scheduler"
                    }
                }
            },
            "status": {
                "replicas": 1,
                "fullyLabeledReplicas": 1,
                "readyReplicas": 1,
                "availableReplicas": 1,
                "observedGeneration": 1
            }
        }
    ]
}
```

## 状态码<a name="sc6fcd881fd2543f7bb48b92fa271e6c8"></a>

[表2](#zh-cn_topic_0079614978_table8264230)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614978_table8264230"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614978_row43889252"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p37476764194930"><a name="p37476764194930"></a><a name="p37476764194930"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p15719014194930"><a name="p15719014194930"></a><a name="p15719014194930"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614978_row57348967"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614978_p14754764"><a name="zh-cn_topic_0079614978_p14754764"></a><a name="zh-cn_topic_0079614978_p14754764"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16423958773"><a name="p16423958773"></a><a name="p16423958773"></a>This operation succeeds, and a group of ReplicationController resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

