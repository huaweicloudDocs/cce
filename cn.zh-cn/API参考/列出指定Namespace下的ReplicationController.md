# 列出指定Namespace下的ReplicationController<a name="cce_02_0021"></a>

## 功能介绍<a name="sf67047d8fbb6440aa6c0ee69dbb0ab60"></a>

该API用于列出指定Namespace下的所有ReplicationController。

## URI<a name="s37529ecb6aca4e228e6cf010d6b12623"></a>

GET /api/v1/namespaces/\{namespace\}/replicationcontrollers

[表1](#table77277322065)  描述该API的参数。

**表 1**  参数描述

<a name="table77277322065"></a>
<table><thead align="left"><tr id="row97282324610"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="p67281321665"><a name="p67281321665"></a><a name="p67281321665"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="22%" id="mcps1.2.4.1.2"><p id="p17288321268"><a name="p17288321268"></a><a name="p17288321268"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p17286321068"><a name="p17286321068"></a><a name="p17286321068"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row27281232362"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p11728153218617"><a name="p11728153218617"></a><a name="p11728153218617"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="p127281832268"><a name="p127281832268"></a><a name="p127281832268"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p21257750"><a name="zh-cn_topic_0079615054_p21257750"></a><a name="zh-cn_topic_0079615054_p21257750"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row10728173213617"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p1772817325614"><a name="p1772817325614"></a><a name="p1772817325614"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="p1072815321869"><a name="p1072815321869"></a><a name="p1072815321869"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p64869644"><a name="zh-cn_topic_0079615054_p64869644"></a><a name="zh-cn_topic_0079615054_p64869644"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row1772813320610"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p57281032162"><a name="p57281032162"></a><a name="p57281032162"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="p972812321667"><a name="p972812321667"></a><a name="p972812321667"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615054_p56466209"><a name="zh-cn_topic_0079615054_p56466209"></a><a name="zh-cn_topic_0079615054_p56466209"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row117295320616"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p1729432163"><a name="p1729432163"></a><a name="p1729432163"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="p272917321662"><a name="p272917321662"></a><a name="p272917321662"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="aba3f1dcb1fc04d0b9d8bc6428342c5d1"><a name="aba3f1dcb1fc04d0b9d8bc6428342c5d1"></a><a name="aba3f1dcb1fc04d0b9d8bc6428342c5d1"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row07290321868"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p6729133220619"><a name="p6729133220619"></a><a name="p6729133220619"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="p87299321366"><a name="p87299321366"></a><a name="p87299321366"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p072916324617"><a name="p072916324617"></a><a name="p072916324617"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="row97291232969"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p67298321619"><a name="p67298321619"></a><a name="p67298321619"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="p17295321564"><a name="p17295321564"></a><a name="p17295321564"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p372916324613"><a name="p372916324613"></a><a name="p372916324613"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row9729103214612"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p1372911329617"><a name="p1372911329617"></a><a name="p1372911329617"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="p127298326618"><a name="p127298326618"></a><a name="p127298326618"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p1372943218610"><a name="p1372943218610"></a><a name="p1372943218610"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row1472917321620"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p172918321169"><a name="p172918321169"></a><a name="p172918321169"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.2 "><p id="p972918327616"><a name="p972918327616"></a><a name="p972918327616"></a>Yes</p>
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

响应参数的详细描述请参见[表2](响应数据结构.md#zh-cn_topic_0079614930_table5881294)。

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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p91231312278"><a name="p91231312278"></a><a name="p91231312278"></a>This operation succeeds, and a group of ReplicationController resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

