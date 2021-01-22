# 列出指定Namespace下的Secret<a name="cce_02_0047"></a>

## 功能介绍<a name="s4f273007dbdb496489d59609177ab2ca"></a>

该API用于在指定的Namespace下列出Secret对象。

## URI<a name="s67ffbd94de334af289f07009ba507b57"></a>

GET /api/v1/namespaces/\{namespace\}/secrets

[表1](#table18879133105311)  描述该API的参数。

**表 1**  参数描述

<a name="table18879133105311"></a>
<table><thead align="left"><tr id="row118791033195317"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="p58794331533"><a name="p58794331533"></a><a name="p58794331533"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.1%" id="mcps1.2.4.1.2"><p id="p10879163355311"><a name="p10879163355311"></a><a name="p10879163355311"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="62.839999999999996%" id="mcps1.2.4.1.3"><p id="p08791733185317"><a name="p08791733185317"></a><a name="p08791733185317"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1879193375310"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p7879633155316"><a name="p7879633155316"></a><a name="p7879633155316"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p88791833195317"><a name="p88791833195317"></a><a name="p88791833195317"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="aff28fe9aebcf437cba4de7a9ead856e9"><a name="aff28fe9aebcf437cba4de7a9ead856e9"></a><a name="aff28fe9aebcf437cba4de7a9ead856e9"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row20879113316534"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p4879433115313"><a name="p4879433115313"></a><a name="p4879433115313"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p1387923345314"><a name="p1387923345314"></a><a name="p1387923345314"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a0a7b2841e1c7435eb425115739a1ce01"><a name="a0a7b2841e1c7435eb425115739a1ce01"></a><a name="a0a7b2841e1c7435eb425115739a1ce01"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row118791233185320"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p9879123365318"><a name="p9879123365318"></a><a name="p9879123365318"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p2879933175312"><a name="p2879933175312"></a><a name="p2879933175312"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a276f514c7e054fe594be37cb743f5173"><a name="a276f514c7e054fe594be37cb743f5173"></a><a name="a276f514c7e054fe594be37cb743f5173"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row98791533185313"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p188799336537"><a name="p188799336537"></a><a name="p188799336537"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p0879133316539"><a name="p0879133316539"></a><a name="p0879133316539"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p887911338531"><a name="p887911338531"></a><a name="p887911338531"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row1587923315319"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p3880333145318"><a name="p3880333145318"></a><a name="p3880333145318"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p1188033319536"><a name="p1188033319536"></a><a name="p1188033319536"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="ac0386b9e9729419d808bfc1e4da82d9c"><a name="ac0386b9e9729419d808bfc1e4da82d9c"></a><a name="ac0386b9e9729419d808bfc1e4da82d9c"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row138801333205316"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p9880203385312"><a name="p9880203385312"></a><a name="p9880203385312"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p1088093335315"><a name="p1088093335315"></a><a name="p1088093335315"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p18880113318539"><a name="p18880113318539"></a><a name="p18880113318539"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row5880113312536"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p1388011337534"><a name="p1388011337534"></a><a name="p1388011337534"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p1880193313532"><a name="p1880193313532"></a><a name="p1880193313532"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a8e45bcc0a7704befb090dc6e70c7c134"><a name="a8e45bcc0a7704befb090dc6e70c7c134"></a><a name="a8e45bcc0a7704befb090dc6e70c7c134"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row988083395314"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p1088017337539"><a name="p1088017337539"></a><a name="p1088017337539"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p78808339539"><a name="p78808339539"></a><a name="p78808339539"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="ab64449bf39f74dfc8a50ec513c46f5bf"><a name="ab64449bf39f74dfc8a50ec513c46f5bf"></a><a name="ab64449bf39f74dfc8a50ec513c46f5bf"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s55df5b092abd4897959f99e7ce493828"></a>

N/A

## 响应消息<a name="scf37ee415d294329ad8442bd193b729e"></a>

**响应参数：**

**表 2**  响应参数

<a name="tc3c49e5e5dee441fb7a7f014a4c81900"></a>
<table><thead align="left"><tr id="re436b46465e04931b74b88d37a1b9677"><th class="cellrowborder" valign="top" width="25.25%" id="mcps1.2.4.1.1"><p id="a28a2f98442b6474da3b695fefeb1cf3d"><a name="a28a2f98442b6474da3b695fefeb1cf3d"></a><a name="a28a2f98442b6474da3b695fefeb1cf3d"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.320000000000004%" id="mcps1.2.4.1.2"><p id="p6199478201625"><a name="p6199478201625"></a><a name="p6199478201625"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.43%" id="mcps1.2.4.1.3"><p id="p32395734201625"><a name="p32395734201625"></a><a name="p32395734201625"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rbba16776ee81419da8a953a80bc7207d"><td class="cellrowborder" valign="top" width="25.25%" headers="mcps1.2.4.1.1 "><p id="af9fabcdd1e8443469be72eb8d614e235"><a name="af9fabcdd1e8443469be72eb8d614e235"></a><a name="af9fabcdd1e8443469be72eb8d614e235"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.320000000000004%" headers="mcps1.2.4.1.2 "><p id="a8602a93578634e13b9187d318ed342ff"><a name="a8602a93578634e13b9187d318ed342ff"></a><a name="a8602a93578634e13b9187d318ed342ff"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="p114739177545"><a name="p114739177545"></a><a name="p114739177545"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="rfa10b724cdbc4eef815c3d3d64260ede"><td class="cellrowborder" valign="top" width="25.25%" headers="mcps1.2.4.1.1 "><p id="a7192cf844ba34d6b912e4aaf50781fd9"><a name="a7192cf844ba34d6b912e4aaf50781fd9"></a><a name="a7192cf844ba34d6b912e4aaf50781fd9"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.320000000000004%" headers="mcps1.2.4.1.2 "><p id="abf2d542e2a384b5383b8357d555d1bed"><a name="abf2d542e2a384b5383b8357d555d1bed"></a><a name="abf2d542e2a384b5383b8357d555d1bed"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="a0bd2ec87801c43058b892f11b50d0f07"><a name="a0bd2ec87801c43058b892f11b50d0f07"></a><a name="a0bd2ec87801c43058b892f11b50d0f07"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="r20a89a0b59b24dfc8956b125482f1421"><td class="cellrowborder" valign="top" width="25.25%" headers="mcps1.2.4.1.1 "><p id="af34c3d5c8cfb4eb4890ba46998f81bce"><a name="af34c3d5c8cfb4eb4890ba46998f81bce"></a><a name="af34c3d5c8cfb4eb4890ba46998f81bce"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.320000000000004%" headers="mcps1.2.4.1.2 "><p id="a7af91f6187e54c6ea63970053896337e"><a name="a7af91f6187e54c6ea63970053896337e"></a><a name="a7af91f6187e54c6ea63970053896337e"></a><a href="#tff9df0051888403eb0196353f3feb3b6">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="p16201547125414"><a name="p16201547125414"></a><a name="p16201547125414"></a>Standard list metadata.</p>
</td>
</tr>
<tr id="r341420eda4f94280a331ac7a3cfc6215"><td class="cellrowborder" valign="top" width="25.25%" headers="mcps1.2.4.1.1 "><p id="a289ba9b3f09f4b6dbe5490422a339709"><a name="a289ba9b3f09f4b6dbe5490422a339709"></a><a name="a289ba9b3f09f4b6dbe5490422a339709"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30.320000000000004%" headers="mcps1.2.4.1.2 "><p id="p616612559218"><a name="p616612559218"></a><a name="p616612559218"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="p0900115610545"><a name="p0900115610545"></a><a name="p0900115610545"></a>List of services.具体请参见<a href="创建Secret.md#zh-cn_topic_0079614900_ref458786458">表2</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="tff9df0051888403eb0196353f3feb3b6"></a>
<table><thead align="left"><tr id="r12daa9f46eeb4a5c83aea6cda1f4e4c5"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="a84714f3753cc47eeb3d1a6df8ce5dc4b"><a name="a84714f3753cc47eeb3d1a6df8ce5dc4b"></a><a name="a84714f3753cc47eeb3d1a6df8ce5dc4b"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.509999999999998%" id="mcps1.2.4.1.2"><p id="p19301202201625"><a name="p19301202201625"></a><a name="p19301202201625"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.43%" id="mcps1.2.4.1.3"><p id="p19893500201625"><a name="p19893500201625"></a><a name="p19893500201625"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r85b01f2c7d1d4a48b955f035e004a0b7"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a3e5016f62da04055871fa7dc628f69c1"><a name="a3e5016f62da04055871fa7dc628f69c1"></a><a name="a3e5016f62da04055871fa7dc628f69c1"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.509999999999998%" headers="mcps1.2.4.1.2 "><p id="a25845db8f0d44529ab7a01fc6d5403be"><a name="a25845db8f0d44529ab7a01fc6d5403be"></a><a name="a25845db8f0d44529ab7a01fc6d5403be"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="p196130199554"><a name="p196130199554"></a><a name="p196130199554"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="r7353b3d91e5b42338bc6ddbfa8d7f715"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a0b0e25db45a44218be3e42b910afdd08"><a name="a0b0e25db45a44218be3e42b910afdd08"></a><a name="a0b0e25db45a44218be3e42b910afdd08"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.509999999999998%" headers="mcps1.2.4.1.2 "><p id="a4f1ceb0744f04795b0879ccc02fca6a9"><a name="a4f1ceb0744f04795b0879ccc02fca6a9"></a><a name="a4f1ceb0744f04795b0879ccc02fca6a9"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="p215613323556"><a name="p215613323556"></a><a name="p215613323556"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "SecretList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/default/secrets",
        "resourceVersion": "1810323"
    },
    "items": [
        {
            "metadata": {
                "name": "default-token-nlckn",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/secrets/default-token-nlckn",
                "uid": "23070e11-1425-11e7-96c7-fa163ec08232",
                "resourceVersion": "30",
                "creationTimestamp": "2017-03-29T02:12:19Z",
                "annotations": {
                    "kubernetes.io/service-account.name": "default",
                    "kubernetes.io/service-account.uid": "2303e59b-1425-11e7-96c7-fa163ec08232"
                }
            },
            "data": {
                "ca.crt": "",
                "namespace": "ZGVmYXVsdA==",
                "token": ""
            },
            "type": "kubernetes.io/service-account-token"
        },
        {
            "metadata": {
                "name": "myregistry",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/secrets/myregistry",
                "uid": "a34ed5e4-1427-11e7-96c7-fa163ec08232",
                "resourceVersion": "1243",
                "creationTimestamp": "2017-03-29T02:30:13Z"
            },
            "data": {
                ".dockercfg": ""
            },
            "type": "kubernetes.io/hwdockercfg"
        },
        {
            "metadata": {
                "name": "paas.elb",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/secrets/paas.elb",
                "uid": "a34df6f3-1427-11e7-96c7-fa163ec08232",
                "resourceVersion": "1242",
                "creationTimestamp": "2017-03-29T02:30:13Z"
            },
            "data": {
                "access.key": "",
                "secret.key": ""
            },
            "type": "Opaque"
        }
    ]
}

 
```

## 状态码<a name="s91a3be3fa42649b9bc4a65bfa7366093"></a>

[表4](#t6cee8759205747faa51f286e53dbed24)描述API的状态码。

**表 4**  状态码

<a name="t6cee8759205747faa51f286e53dbed24"></a>
<table><thead align="left"><tr id="r4c11b2d5506d46358b44888e0906952a"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p16238293201625"><a name="p16238293201625"></a><a name="p16238293201625"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p40233369201625"><a name="p40233369201625"></a><a name="p40233369201625"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r5ad486edb0db460294cdd49a495f30a6"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="a16bfcc1de96142f6a2f458546b8722ed"><a name="a16bfcc1de96142f6a2f458546b8722ed"></a><a name="a16bfcc1de96142f6a2f458546b8722ed"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614896_p815332217101"><a name="zh-cn_topic_0079614896_p815332217101"></a><a name="zh-cn_topic_0079614896_p815332217101"></a>This operation succeeds, and a secret resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

