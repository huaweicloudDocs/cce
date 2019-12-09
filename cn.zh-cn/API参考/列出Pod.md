# 列出Pod<a name="cce_02_0040"></a>

## 功能介绍<a name="s2c7f113b12b14c1a8227582e4f8b46c1"></a>

该API用于获取一个Pod列表。

## URI<a name="sf6f9f8f5dd594423a05d7da7d1f2fb77"></a>

GET /api/v1/pods

[表1](#zh-cn_topic_0079614951_table32684898)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614951_table32684898"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614951_row18934104"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614951_p57267493"><a name="zh-cn_topic_0079614951_p57267493"></a><a name="zh-cn_topic_0079614951_p57267493"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="27%" id="mcps1.2.4.1.2"><p id="p13002682201918"><a name="p13002682201918"></a><a name="p13002682201918"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.4.1.3"><p id="p46584307201918"><a name="p46584307201918"></a><a name="p46584307201918"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614951_row21462253"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614951_p60720939"><a name="zh-cn_topic_0079614951_p60720939"></a><a name="zh-cn_topic_0079614951_p60720939"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614951_p19449066"><a name="zh-cn_topic_0079614951_p19449066"></a><a name="zh-cn_topic_0079614951_p19449066"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614951_p31870546"><a name="zh-cn_topic_0079614951_p31870546"></a><a name="zh-cn_topic_0079614951_p31870546"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614951_row18399460"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614951_p13961307"><a name="zh-cn_topic_0079614951_p13961307"></a><a name="zh-cn_topic_0079614951_p13961307"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614951_p57124111"><a name="zh-cn_topic_0079614951_p57124111"></a><a name="zh-cn_topic_0079614951_p57124111"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614951_p63650279"><a name="zh-cn_topic_0079614951_p63650279"></a><a name="zh-cn_topic_0079614951_p63650279"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="rd1927794757e4cdbadd7602264f3028d"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a5757fdbde20c43588414db2b7e0a5d9d"><a name="a5757fdbde20c43588414db2b7e0a5d9d"></a><a name="a5757fdbde20c43588414db2b7e0a5d9d"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="a22fc8d77253e48829c7a07fcc9cbf1d8"><a name="a22fc8d77253e48829c7a07fcc9cbf1d8"></a><a name="a22fc8d77253e48829c7a07fcc9cbf1d8"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="a5068ef5baef746068bf8b3ba4e10e511"><a name="a5068ef5baef746068bf8b3ba4e10e511"></a><a name="a5068ef5baef746068bf8b3ba4e10e511"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614951_row35981604"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614951_p28828846"><a name="zh-cn_topic_0079614951_p28828846"></a><a name="zh-cn_topic_0079614951_p28828846"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614951_p53435217"><a name="zh-cn_topic_0079614951_p53435217"></a><a name="zh-cn_topic_0079614951_p53435217"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614951_p33285300"><a name="zh-cn_topic_0079614951_p33285300"></a><a name="zh-cn_topic_0079614951_p33285300"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614951_row31132245"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614951_p38683899"><a name="zh-cn_topic_0079614951_p38683899"></a><a name="zh-cn_topic_0079614951_p38683899"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614951_p46388151"><a name="zh-cn_topic_0079614951_p46388151"></a><a name="zh-cn_topic_0079614951_p46388151"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614951_p66452718"><a name="zh-cn_topic_0079614951_p66452718"></a><a name="zh-cn_topic_0079614951_p66452718"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614951_row61203556"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614951_p58541026"><a name="zh-cn_topic_0079614951_p58541026"></a><a name="zh-cn_topic_0079614951_p58541026"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614951_p44202640"><a name="zh-cn_topic_0079614951_p44202640"></a><a name="zh-cn_topic_0079614951_p44202640"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614951_p23644054"><a name="zh-cn_topic_0079614951_p23644054"></a><a name="zh-cn_topic_0079614951_p23644054"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614951_row11469898"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614951_p56646536"><a name="zh-cn_topic_0079614951_p56646536"></a><a name="zh-cn_topic_0079614951_p56646536"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614951_p24966707"><a name="zh-cn_topic_0079614951_p24966707"></a><a name="zh-cn_topic_0079614951_p24966707"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614951_p9037362"><a name="zh-cn_topic_0079614951_p9037362"></a><a name="zh-cn_topic_0079614951_p9037362"></a>Timeout for the list/watch call.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s1a2c64dedce04c55b45709c2dbc3f225"></a>

N/A

## 响应消息<a name="s1b03b47bea774f76a73a7f73d8510c40"></a>

**响应参数：**

响应参数的详细描述请参见[表4](响应数据结构.md#zh-cn_topic_0079614930_table6622802)。

**响应示例：**

```
{
    "kind": "PodList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/pods",
        "resourceVersion": "1550321"
    },
    "items": [
        {
            "metadata": {
                "name": "fdsfsd-ddnft",
                "generateName": "fdsfsd-",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/pods/fdsfsd-ddnft",
                "uid": "753a45bc-57c4-11e7-afb7-fa163e218692",
                "resourceVersion": "1449034",
                "creationTimestamp": "2017-06-23T03:31:35Z",
                "labels": {
                    "cce/appgroup": "gfsad",
                    "name": "fdsfsd"
                },
                "annotations": {
                    "kubernetes.io/created-by": "{\"kind\":\"SerializedReference\",\"apiVersion\":\"v1\",\"reference\":{\"kind\":\"ReplicationController\",\"namespace\":\"default\",\"name\":\"fdsfsd\",\"uid\":\"7539c329-57c4-11e7-afb7-fa163e218692\",\"apiVersion\":\"v1\",\"resourceVersion\":\"956153\"}}\n",
                    "kubernetes.io/limit-ranger": "LimitRanger plugin set: cpu request for container container01"
                },
                "ownerReferences": [
                    {
                        "apiVersion": "v1",
                        "kind": "ReplicationController",
                        "name": "fdsfsd",
                        "uid": "7539c329-57c4-11e7-afb7-fa163e218692",
                        "controller": true
                    }
                ]
            },
            "spec": {
                "volumes": [
                    {
                        "name": "default-token-863rh",
                        "secret": {
                            "secretName": "default-token-863rh",
                            "defaultMode": 420
                        }
                    }
                ],
                "containers": [
                    {
                        "name": "container01",
                        "image": "10.154.52.159:443/test/apache-php:latest",
                        "ports": [
                            {
                                "containerPort": 80,
                                "protocol": "TCP"
                            }
                        ],
                        "resources": {
                            "requests": {
                                "cpu": "100m"
                            }
                        },
                        "volumeMounts": [
                            {
                                "name": "default-token-863rh",
                                "readOnly": true,
                                "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount"
                            }
                        ],
                        "terminationMessagePath": "/dev/termination-log",
                        "imagePullPolicy": "Always"
                    }
                ],
                "restartPolicy": "Always",
                "terminationGracePeriodSeconds": 30,
                "dnsPolicy": "ClusterFirst",
                "serviceAccountName": "default",
                "serviceAccount": "default",
                "nodeName": "192.168.12.187",
                "securityContext": {},
                "imagePullSecrets": [
                    {
                        "name": "myregistry"
                    }
                ]
            },
            "status": {
                "phase": "Running",
                "conditions": [
                    {
                        "type": "Initialized",
                        "status": "True",
                        "lastProbeTime": null,
                        "lastTransitionTime": "2017-06-23T03:31:36Z"
                    },
                    {
                        "type": "Ready",
                        "status": "True",
                        "lastProbeTime": null,
                        "lastTransitionTime": "2017-06-28T06:34:51Z"
                    },
                    {
                        "type": "PodScheduled",
                        "status": "True",
                        "lastProbeTime": null,
                        "lastTransitionTime": "2017-06-23T03:31:35Z"
                    }
                ],
                "hostIP": "192.168.12.187",
                "podIP": "172.16.56.4",
                "startTime": "2017-06-23T03:31:36Z",
                "containerStatuses": [
                    {
                        "name": "container01",
                        "state": {
                            "running": {
                                "startedAt": "2017-06-28T06:34:46Z"
                            }
                        },
                        "lastState": {},
                        "ready": true,
                        "restartCount": 0,
                        "image": "10.154.52.159:443/test/apache-php:latest",
                        "imageID": "docker://sha256:2e233ad9329bd7f65572dd6acb1a03e8839c36abfdb1d1f9012d84d13cecf9fc",
                        "containerID": "docker://f3daa802f753d123fe66b2cba2e917725702f8d446c17541822a68f9d2414c6d"
                    }
                ]
            }
        }
    ]
}
```

## 状态码<a name="scce0cbd5b8da4324818e7866150549fa"></a>

[表2](#zh-cn_topic_0079614951_table25728631)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614951_table25728631"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614951_row39779893"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p59589989201918"><a name="p59589989201918"></a><a name="p59589989201918"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p62059838201918"><a name="p62059838201918"></a><a name="p62059838201918"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614951_row32277796"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614951_p64364717"><a name="zh-cn_topic_0079614951_p64364717"></a><a name="zh-cn_topic_0079614951_p64364717"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614951_p46159594"><a name="zh-cn_topic_0079614951_p46159594"></a><a name="zh-cn_topic_0079614951_p46159594"></a>This operation succeeds, and the JSONs of a group of Pod objects are returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

