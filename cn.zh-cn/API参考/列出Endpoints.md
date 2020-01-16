# 列出Endpoints<a name="cce_02_0063"></a>

## 功能介绍<a name="se41b5214217c46878f61206c07596eb4"></a>

该API用于列出所有的Endpoints资源对象。

## URI<a name="sf91bd4390d4c4830b1b787e9885cb9f4"></a>

GET /api/v1/endpoints

[表1](#zh-cn_topic_0079614910_table37859935)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614910_table37859935"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614910_row9677327"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614910_p45666040"><a name="zh-cn_topic_0079614910_p45666040"></a><a name="zh-cn_topic_0079614910_p45666040"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="26%" id="mcps1.2.4.1.2"><p id="p41491268201925"><a name="p41491268201925"></a><a name="p41491268201925"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="41%" id="mcps1.2.4.1.3"><p id="p5349547201925"><a name="p5349547201925"></a><a name="p5349547201925"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614910_row26207892"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p42464494"><a name="zh-cn_topic_0079614910_p42464494"></a><a name="zh-cn_topic_0079614910_p42464494"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p17072009"><a name="zh-cn_topic_0079614910_p17072009"></a><a name="zh-cn_topic_0079614910_p17072009"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p40655501"><a name="zh-cn_topic_0079614910_p40655501"></a><a name="zh-cn_topic_0079614910_p40655501"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row30355189"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p42851240"><a name="zh-cn_topic_0079614910_p42851240"></a><a name="zh-cn_topic_0079614910_p42851240"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p48398424"><a name="zh-cn_topic_0079614910_p48398424"></a><a name="zh-cn_topic_0079614910_p48398424"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p27958252"><a name="zh-cn_topic_0079614910_p27958252"></a><a name="zh-cn_topic_0079614910_p27958252"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row3425452468"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a1d0ca559244f465a9fc5c5ff1ad01726"><a name="a1d0ca559244f465a9fc5c5ff1ad01726"></a><a name="a1d0ca559244f465a9fc5c5ff1ad01726"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p642515164618"><a name="zh-cn_topic_0079614910_p642515164618"></a><a name="zh-cn_topic_0079614910_p642515164618"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p442515184611"><a name="zh-cn_topic_0079614910_p442515184611"></a><a name="zh-cn_topic_0079614910_p442515184611"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row50297679"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p47580213"><a name="zh-cn_topic_0079614910_p47580213"></a><a name="zh-cn_topic_0079614910_p47580213"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p28792051"><a name="zh-cn_topic_0079614910_p28792051"></a><a name="zh-cn_topic_0079614910_p28792051"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p50454834"><a name="zh-cn_topic_0079614910_p50454834"></a><a name="zh-cn_topic_0079614910_p50454834"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row51440330"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p5917164"><a name="zh-cn_topic_0079614910_p5917164"></a><a name="zh-cn_topic_0079614910_p5917164"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p9528291"><a name="zh-cn_topic_0079614910_p9528291"></a><a name="zh-cn_topic_0079614910_p9528291"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p33594135"><a name="zh-cn_topic_0079614910_p33594135"></a><a name="zh-cn_topic_0079614910_p33594135"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row33911763"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p62498284"><a name="zh-cn_topic_0079614910_p62498284"></a><a name="zh-cn_topic_0079614910_p62498284"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p29196278"><a name="zh-cn_topic_0079614910_p29196278"></a><a name="zh-cn_topic_0079614910_p29196278"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p16088345"><a name="zh-cn_topic_0079614910_p16088345"></a><a name="zh-cn_topic_0079614910_p16088345"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row10577379"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p51461341"><a name="zh-cn_topic_0079614910_p51461341"></a><a name="zh-cn_topic_0079614910_p51461341"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p7619075"><a name="zh-cn_topic_0079614910_p7619075"></a><a name="zh-cn_topic_0079614910_p7619075"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p13165375"><a name="zh-cn_topic_0079614910_p13165375"></a><a name="zh-cn_topic_0079614910_p13165375"></a>Timeout for the list/watch call.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sf6d69235d514410b9df31b1c107977cc"></a>

N/A

## 响应消息<a name="s871d296e934a4a0596c01c189ad05eb7"></a>

**响应参数：**

响应参数如[表2](#zh-cn_topic_0079614910_ref458760085)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079614910_ref458760085"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614910_row61120788"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614910_p51836813"><a name="zh-cn_topic_0079614910_p51836813"></a><a name="zh-cn_topic_0079614910_p51836813"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p53156369201925"><a name="p53156369201925"></a><a name="p53156369201925"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p10698594201925"><a name="p10698594201925"></a><a name="p10698594201925"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614910_row19124697"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p5596611"><a name="zh-cn_topic_0079614910_p5596611"></a><a name="zh-cn_topic_0079614910_p5596611"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p50672366"><a name="zh-cn_topic_0079614910_p50672366"></a><a name="zh-cn_topic_0079614910_p50672366"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p10820994"><a name="zh-cn_topic_0079614910_p10820994"></a><a name="zh-cn_topic_0079614910_p10820994"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row30280082"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p36767573"><a name="zh-cn_topic_0079614910_p36767573"></a><a name="zh-cn_topic_0079614910_p36767573"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p25383445"><a name="zh-cn_topic_0079614910_p25383445"></a><a name="zh-cn_topic_0079614910_p25383445"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p42793145"><a name="zh-cn_topic_0079614910_p42793145"></a><a name="zh-cn_topic_0079614910_p42793145"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row49593988"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p57690106"><a name="zh-cn_topic_0079614910_p57690106"></a><a name="zh-cn_topic_0079614910_p57690106"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p42387016"><a name="zh-cn_topic_0079614910_p42387016"></a><a name="zh-cn_topic_0079614910_p42387016"></a><a href="#zh-cn_topic_0079614910_table5195099">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p10796311"><a name="zh-cn_topic_0079614910_p10796311"></a><a name="zh-cn_topic_0079614910_p10796311"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row30057943"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p18774281"><a name="zh-cn_topic_0079614910_p18774281"></a><a name="zh-cn_topic_0079614910_p18774281"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p44321808"><a name="zh-cn_topic_0079614910_p44321808"></a><a name="zh-cn_topic_0079614910_p44321808"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p141911584228"><a name="p141911584228"></a><a name="p141911584228"></a>List of endpoints.</p>
<p id="zh-cn_topic_0079614910_p31235064"><a name="zh-cn_topic_0079614910_p31235064"></a><a name="zh-cn_topic_0079614910_p31235064"></a>具体请参见<a href="创建Endpoints.md#zh-cn_topic_0079614955_ref458759912">表2</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="zh-cn_topic_0079614910_table5195099"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614910_row13949281"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614910_p56149948"><a name="zh-cn_topic_0079614910_p56149948"></a><a name="zh-cn_topic_0079614910_p56149948"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p35621711201925"><a name="p35621711201925"></a><a name="p35621711201925"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p66786310201925"><a name="p66786310201925"></a><a name="p66786310201925"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614910_row25775953"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p7477471"><a name="zh-cn_topic_0079614910_p7477471"></a><a name="zh-cn_topic_0079614910_p7477471"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p1695389"><a name="zh-cn_topic_0079614910_p1695389"></a><a name="zh-cn_topic_0079614910_p1695389"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p3108787"><a name="zh-cn_topic_0079614910_p3108787"></a><a name="zh-cn_topic_0079614910_p3108787"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614910_row27979087"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614910_p51713565"><a name="zh-cn_topic_0079614910_p51713565"></a><a name="zh-cn_topic_0079614910_p51713565"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614910_p28049240"><a name="zh-cn_topic_0079614910_p28049240"></a><a name="zh-cn_topic_0079614910_p28049240"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614910_p57395943"><a name="zh-cn_topic_0079614910_p57395943"></a><a name="zh-cn_topic_0079614910_p57395943"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "EndpointsList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/endpoints",
        "resourceVersion": "599259"
    },
    "items": [
        {
            "metadata": {
                "name": "kubernetes",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/endpoints/kubernetes",
                "uid": "64593b5d-f83d-11e7-9c3c-fa163eb8ad1a",
                "resourceVersion": "49",
                "creationTimestamp": "2018-01-13T08:40:21Z",
                "enable": true
            },
            "subsets": [
                {
                    "addresses": [
                        {
                            "ip": "192.168.0.64"
                        }
                    ],
                    "ports": [
                        {
                            "name": "https",
                            "port": 5444,
                            "protocol": "TCP"
                        }
                    ]
                }
            ]
        },
        {
            "metadata": {
                "name": "kube-controller-manager",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/endpoints/kube-controller-manager",
                "uid": "654e158d-f83d-11e7-9c3c-fa163eb8ad1a",
                "resourceVersion": "599259",
                "creationTimestamp": "2018-01-13T08:40:23Z",
                "annotations": {
                    "control-plane.alpha.kubernetes.io/leader": "{\"holderIdentity\":\"192-168-0-64\",\"leaseDurationSeconds\":15,\"acquireTime\":\"2018-01-13T08:40:23Z\",\"renewTime\":\"2018-01-19T09:31:56Z\",\"leaderTransitions\":0}"
                },
                "enable": true
            },
            "subsets": null
        },
        {
            "metadata": {
                "name": "kube-dns",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/endpoints/kube-dns",
                "uid": "6cfc9958-f83d-11e7-9c3c-fa163eb8ad1a",
                "resourceVersion": "506984",
                "creationTimestamp": "2018-01-13T08:40:36Z",
                "labels": {
                    "addonmanager.kubernetes.io/mode": "Reconcile",
                    "kubernetes-app": "kube-dns",
                    "kubernetes.io/cluster-service": "true",
                    "kubernetes.io/name": "KubeDNS"
                },
                "enable": true
            },
            "subsets": [
                {
                    "addresses": [
                        {
                            "ip": "172.31.0.10",
                            "nodeName": "192.168.0.228",
                            "targetRef": {
                                "kind": "Pod",
                                "namespace": "kube-system",
                                "name": "kube-dns-139966378-crrqm",
                                "uid": "c46cfbf9-fc4b-11e7-9c3c-fa163eb8ad1a",
                                "resourceVersion": "506982"
                            }
                        }
                    ],
                    "ports": [
                        {
                            "name": "dns-tcp",
                            "port": 5353,
                            "protocol": "TCP"
                        },
                        {
                            "name": "dns",
                            "port": 5353,
                            "protocol": "UDP"
                        }
                    ]
                }
            ]
        },
        {
            "metadata": {
                "name": "kube-scheduler",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/endpoints/kube-scheduler",
                "uid": "64d35553-f83d-11e7-9c3c-fa163eb8ad1a",
                "resourceVersion": "599258",
                "creationTimestamp": "2018-01-13T08:40:22Z",
                "annotations": {
                    "control-plane.alpha.kubernetes.io/leader": "{\"holderIdentity\":\"192-168-0-64\",\"leaseDurationSeconds\":15,\"acquireTime\":\"2018-01-13T08:40:22Z\",\"renewTime\":\"2018-01-19T09:31:56Z\",\"leaderTransitions\":0}"
                },
                "enable": true
            },
            "subsets": null
        }
    ]
}
```

## 状态码<a name="s679ed498decc4f6fb82e49698eb47fb8"></a>

[表4](#zh-cn_topic_0079614910_table46755894)描述API的状态码。

**表 4**  状态码

<a name="zh-cn_topic_0079614910_table46755894"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614910_row9860484"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p22510226201925"><a name="p22510226201925"></a><a name="p22510226201925"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p11389007201925"><a name="p11389007201925"></a><a name="p11389007201925"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614910_row3031417"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614910_p44218209"><a name="zh-cn_topic_0079614910_p44218209"></a><a name="zh-cn_topic_0079614910_p44218209"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614910_p24905153"><a name="zh-cn_topic_0079614910_p24905153"></a><a name="zh-cn_topic_0079614910_p24905153"></a>This operation succeeds, and a group of Endpoint resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

