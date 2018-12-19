# 列出指定Namespace下的ReplicationController<a name="cce_02_0021"></a>

## 功能介绍<a name="sf67047d8fbb6440aa6c0ee69dbb0ab60"></a>

该API用于列出指定Namespace下的所有ReplicationController。

## URI<a name="s37529ecb6aca4e228e6cf010d6b12623"></a>

GET /api/v1/namespaces/\{namespace\}/replicationcontrollers

[表1](#zh-cn_topic_0079615054_table43644936)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615054_table43644936"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615054_row23652783"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615054_p36827296"><a name="zh-cn_topic_0079615054_p36827296"></a><a name="zh-cn_topic_0079615054_p36827296"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="22%" id="mcps1.2.4.1.2"><p id="p60596924194718"><a name="p60596924194718"></a><a name="p60596924194718"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p9403811194718"><a name="p9403811194718"></a><a name="p9403811194718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615054_row40650175"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615054_p4329874"><a name="zh-cn_topic_0079615054_p4329874"></a><a name="zh-cn_topic_0079615054_p4329874"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615054_p15175522"><a name="zh-cn_topic_0079615054_p15175522"></a><a name="zh-cn_topic_0079615054_p15175522"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p21257750"><a name="zh-cn_topic_0079615054_p21257750"></a><a name="zh-cn_topic_0079615054_p21257750"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615054_row57102025"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615054_p61861327"><a name="zh-cn_topic_0079615054_p61861327"></a><a name="zh-cn_topic_0079615054_p61861327"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615054_p44711597"><a name="zh-cn_topic_0079615054_p44711597"></a><a name="zh-cn_topic_0079615054_p44711597"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p64869644"><a name="zh-cn_topic_0079615054_p64869644"></a><a name="zh-cn_topic_0079615054_p64869644"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615054_row46955892"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615054_p45330870"><a name="zh-cn_topic_0079615054_p45330870"></a><a name="zh-cn_topic_0079615054_p45330870"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615054_p47921869"><a name="zh-cn_topic_0079615054_p47921869"></a><a name="zh-cn_topic_0079615054_p47921869"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p56466209"><a name="zh-cn_topic_0079615054_p56466209"></a><a name="zh-cn_topic_0079615054_p56466209"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="r2db43af1a5cc4b9aa0dbca7d708e30d5"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a18e375bd668a48008cad678f18f6a747"><a name="a18e375bd668a48008cad678f18f6a747"></a><a name="a18e375bd668a48008cad678f18f6a747"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="ade2c3b7bd21e47bfaaec460717e532a1"><a name="ade2c3b7bd21e47bfaaec460717e532a1"></a><a name="ade2c3b7bd21e47bfaaec460717e532a1"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="aba3f1dcb1fc04d0b9d8bc6428342c5d1"><a name="aba3f1dcb1fc04d0b9d8bc6428342c5d1"></a><a name="aba3f1dcb1fc04d0b9d8bc6428342c5d1"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615054_row38433837"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615054_p26133094"><a name="zh-cn_topic_0079615054_p26133094"></a><a name="zh-cn_topic_0079615054_p26133094"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615054_p36405904"><a name="zh-cn_topic_0079615054_p36405904"></a><a name="zh-cn_topic_0079615054_p36405904"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p63197139"><a name="zh-cn_topic_0079615054_p63197139"></a><a name="zh-cn_topic_0079615054_p63197139"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615054_row31903341"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615054_p34033799"><a name="zh-cn_topic_0079615054_p34033799"></a><a name="zh-cn_topic_0079615054_p34033799"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615054_p5274317"><a name="zh-cn_topic_0079615054_p5274317"></a><a name="zh-cn_topic_0079615054_p5274317"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p24566569"><a name="zh-cn_topic_0079615054_p24566569"></a><a name="zh-cn_topic_0079615054_p24566569"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615054_row19772529"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615054_p58071046"><a name="zh-cn_topic_0079615054_p58071046"></a><a name="zh-cn_topic_0079615054_p58071046"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615054_p6134308"><a name="zh-cn_topic_0079615054_p6134308"></a><a name="zh-cn_topic_0079615054_p6134308"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p27116914"><a name="zh-cn_topic_0079615054_p27116914"></a><a name="zh-cn_topic_0079615054_p27116914"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615054_row42725634"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615054_p38224348"><a name="zh-cn_topic_0079615054_p38224348"></a><a name="zh-cn_topic_0079615054_p38224348"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615054_p9164474"><a name="zh-cn_topic_0079615054_p9164474"></a><a name="zh-cn_topic_0079615054_p9164474"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p4124933"><a name="zh-cn_topic_0079615054_p4124933"></a><a name="zh-cn_topic_0079615054_p4124933"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s150fa7f516814ff4ad39c60c6e55b3b9"></a>

N/A

## 响应消息<a name="s00fead6e7b3148c58421f54f9b14f808"></a>

**响应参数：**

响应参数的详细描述请参见[表2](公共响应参数.md#zh-cn_topic_0079614930_table5881294)。

**响应示例：**

```
{
    "kind": "ReplicationControllerList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/default/replicationcontrollers",
        "resourceVersion": "591585"
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

## 状态码<a name="sf1c91f0d19274e1fafc6cab7ada11fbd"></a>

[表2](#zh-cn_topic_0079615054_table57260105)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615054_table57260105"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615054_row357754"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p48540733194718"><a name="p48540733194718"></a><a name="p48540733194718"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p39485296194718"><a name="p39485296194718"></a><a name="p39485296194718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615054_row6247673"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615054_p36299500"><a name="zh-cn_topic_0079615054_p36299500"></a><a name="zh-cn_topic_0079615054_p36299500"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615054_p54578396"><a name="zh-cn_topic_0079615054_p54578396"></a><a name="zh-cn_topic_0079615054_p54578396"></a>This operation succeeds, and a group of ReplicationController resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

