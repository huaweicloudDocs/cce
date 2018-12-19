# 列出指定Namespaces下的所有Pod<a name="cce_02_0039"></a>

## 功能介绍<a name="sa15e1880c5594fc48219b954fe0ba73f"></a>

该API用于列出指定Namespaces下面的所有Pod资源对象。

## URI<a name="s2816ee648d7a424dadd23e140e22ab10"></a>

GET /api/v1/namespaces/\{namespace\}/pods

[表1](#zh-cn_topic_0079615024_table39288210)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615024_table39288210"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615024_row57365620"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615024_p16103609"><a name="zh-cn_topic_0079615024_p16103609"></a><a name="zh-cn_topic_0079615024_p16103609"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="26%" id="mcps1.2.4.1.2"><p id="p2877885220168"><a name="p2877885220168"></a><a name="p2877885220168"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="41%" id="mcps1.2.4.1.3"><p id="p4938564320168"><a name="p4938564320168"></a><a name="p4938564320168"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615024_row60306259"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615024_p52968826"><a name="zh-cn_topic_0079615024_p52968826"></a><a name="zh-cn_topic_0079615024_p52968826"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615024_p62616542"><a name="zh-cn_topic_0079615024_p62616542"></a><a name="zh-cn_topic_0079615024_p62616542"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615024_p38775142"><a name="zh-cn_topic_0079615024_p38775142"></a><a name="zh-cn_topic_0079615024_p38775142"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615024_row13431963"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615024_p14247253"><a name="zh-cn_topic_0079615024_p14247253"></a><a name="zh-cn_topic_0079615024_p14247253"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615024_p13176872"><a name="zh-cn_topic_0079615024_p13176872"></a><a name="zh-cn_topic_0079615024_p13176872"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615024_p60693691"><a name="zh-cn_topic_0079615024_p60693691"></a><a name="zh-cn_topic_0079615024_p60693691"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615024_row9372308"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615024_p20959466"><a name="zh-cn_topic_0079615024_p20959466"></a><a name="zh-cn_topic_0079615024_p20959466"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615024_p19995222"><a name="zh-cn_topic_0079615024_p19995222"></a><a name="zh-cn_topic_0079615024_p19995222"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615024_p9000253"><a name="zh-cn_topic_0079615024_p9000253"></a><a name="zh-cn_topic_0079615024_p9000253"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="r48a23247a4514d3895552219d0bf1d7f"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615024_p268425212266"><a name="zh-cn_topic_0079615024_p268425212266"></a><a name="zh-cn_topic_0079615024_p268425212266"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="ab0682c66f2294f69bb2a7d10b9e29068"><a name="ab0682c66f2294f69bb2a7d10b9e29068"></a><a name="ab0682c66f2294f69bb2a7d10b9e29068"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="a101aec385acb47ff8569f2105ffa4e76"><a name="a101aec385acb47ff8569f2105ffa4e76"></a><a name="a101aec385acb47ff8569f2105ffa4e76"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615024_row13893419"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615024_p51625177"><a name="zh-cn_topic_0079615024_p51625177"></a><a name="zh-cn_topic_0079615024_p51625177"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615024_p20889783"><a name="zh-cn_topic_0079615024_p20889783"></a><a name="zh-cn_topic_0079615024_p20889783"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615024_p14350829"><a name="zh-cn_topic_0079615024_p14350829"></a><a name="zh-cn_topic_0079615024_p14350829"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615024_row62048601"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615024_p59880775"><a name="zh-cn_topic_0079615024_p59880775"></a><a name="zh-cn_topic_0079615024_p59880775"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615024_p18504610"><a name="zh-cn_topic_0079615024_p18504610"></a><a name="zh-cn_topic_0079615024_p18504610"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615024_p22478417"><a name="zh-cn_topic_0079615024_p22478417"></a><a name="zh-cn_topic_0079615024_p22478417"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615024_row979164"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615024_p12203429"><a name="zh-cn_topic_0079615024_p12203429"></a><a name="zh-cn_topic_0079615024_p12203429"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615024_p48953654"><a name="zh-cn_topic_0079615024_p48953654"></a><a name="zh-cn_topic_0079615024_p48953654"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615024_p5823032"><a name="zh-cn_topic_0079615024_p5823032"></a><a name="zh-cn_topic_0079615024_p5823032"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615024_row52407290"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615024_p17132136"><a name="zh-cn_topic_0079615024_p17132136"></a><a name="zh-cn_topic_0079615024_p17132136"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615024_p45525786"><a name="zh-cn_topic_0079615024_p45525786"></a><a name="zh-cn_topic_0079615024_p45525786"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615024_p63710073"><a name="zh-cn_topic_0079615024_p63710073"></a><a name="zh-cn_topic_0079615024_p63710073"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s417ddc31a4054521aee75e523ec75dc7"></a>

N/A

## 响应消息<a name="sf3b21eb28dd042b6860622b69c5fcf92"></a>

**响应参数：**

响应参数的详细描述请参见[表4](公共响应参数.md#zh-cn_topic_0079614930_table6622802)。

**响应示例：**

```
{
    "kind": "PodList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/default/pods",
        "resourceVersion": "1550921"
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

## 状态码<a name="sbc30358c7d094cf7b28929f12a616f3c"></a>

[表2](#zh-cn_topic_0079615024_table18049573)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615024_table18049573"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615024_row33487713"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p3844484120168"><a name="p3844484120168"></a><a name="p3844484120168"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p2702441120168"><a name="p2702441120168"></a><a name="p2702441120168"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615024_row10105911"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615024_p13272423"><a name="zh-cn_topic_0079615024_p13272423"></a><a name="zh-cn_topic_0079615024_p13272423"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615024_p1324451"><a name="zh-cn_topic_0079615024_p1324451"></a><a name="zh-cn_topic_0079615024_p1324451"></a>This operation succeeds, and a group of Pod resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

