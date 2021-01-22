# 列出所有的PersistentVolume<a name="cce_02_0081"></a>

## 功能介绍<a name="sf7e61042b8f443ffaba2eede91eb90a2"></a>

该API用于列出所有PersistentVolume资源对象。

## URI<a name="s400c42cac85c4b71a31cc649b53f17d7"></a>

GET /api/v1/persistentvolumes

[表1](#tbf6cfcabd5e94f8bbbf94427987ba7b4)描述该API的参数。

**表 1**  参数描述

<a name="tbf6cfcabd5e94f8bbbf94427987ba7b4"></a>
<table><thead align="left"><tr id="r6af560f2f36b4afc9de828d2ab6c0224"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="ad8ed9453c46247148343cf801966069e"><a name="ad8ed9453c46247148343cf801966069e"></a><a name="ad8ed9453c46247148343cf801966069e"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.99%" id="mcps1.2.4.1.2"><p id="p28684502201939"><a name="p28684502201939"></a><a name="p28684502201939"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="57.95%" id="mcps1.2.4.1.3"><p id="p41743360201939"><a name="p41743360201939"></a><a name="p41743360201939"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r16669450f0ab41df8933a056448202e8"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="abab60d7ebc4348ceaec1b212d62c0e12"><a name="abab60d7ebc4348ceaec1b212d62c0e12"></a><a name="abab60d7ebc4348ceaec1b212d62c0e12"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="19.99%" headers="mcps1.2.4.1.2 "><p id="af4d487b0928b4c91b85447452feb2cd4"><a name="af4d487b0928b4c91b85447452feb2cd4"></a><a name="af4d487b0928b4c91b85447452feb2cd4"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="57.95%" headers="mcps1.2.4.1.3 "><p id="a93b84444ef8a417bb4630276039de34e"><a name="a93b84444ef8a417bb4630276039de34e"></a><a name="a93b84444ef8a417bb4630276039de34e"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="r921e79f46d3d48ac8899e06ae90f87f4"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="aaf3a19b7f0454befbbe9b488b9a7122e"><a name="aaf3a19b7f0454befbbe9b488b9a7122e"></a><a name="aaf3a19b7f0454befbbe9b488b9a7122e"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="19.99%" headers="mcps1.2.4.1.2 "><p id="a7b0007971d2a469c9b7c509a8d2d7168"><a name="a7b0007971d2a469c9b7c509a8d2d7168"></a><a name="a7b0007971d2a469c9b7c509a8d2d7168"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="57.95%" headers="mcps1.2.4.1.3 "><p id="a8ec2ca7b087a48c19a937e43f63fb847"><a name="a8ec2ca7b087a48c19a937e43f63fb847"></a><a name="a8ec2ca7b087a48c19a937e43f63fb847"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="rb915548bc3764378b919ff04924009c1"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="ae1dd8dfc18314ccb9d369830a9165a3c"><a name="ae1dd8dfc18314ccb9d369830a9165a3c"></a><a name="ae1dd8dfc18314ccb9d369830a9165a3c"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="19.99%" headers="mcps1.2.4.1.2 "><p id="afe5ddffdd20a4a5182e516caf7542a05"><a name="afe5ddffdd20a4a5182e516caf7542a05"></a><a name="afe5ddffdd20a4a5182e516caf7542a05"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="57.95%" headers="mcps1.2.4.1.3 "><p id="ab72bc3ae9cc944e3b929f3a59da5c68a"><a name="ab72bc3ae9cc944e3b929f3a59da5c68a"></a><a name="ab72bc3ae9cc944e3b929f3a59da5c68a"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="r3534cb2328464748ac4ebfc74600705d"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="af991179441b9405b8c432af4e4ef7007"><a name="af991179441b9405b8c432af4e4ef7007"></a><a name="af991179441b9405b8c432af4e4ef7007"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="19.99%" headers="mcps1.2.4.1.2 "><p id="a8acd212117cd4f20a6f4f7e494317af2"><a name="a8acd212117cd4f20a6f4f7e494317af2"></a><a name="a8acd212117cd4f20a6f4f7e494317af2"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="57.95%" headers="mcps1.2.4.1.3 "><p id="a7b3cd02ad20c4862a165b5911e72e5ab"><a name="a7b3cd02ad20c4862a165b5911e72e5ab"></a><a name="a7b3cd02ad20c4862a165b5911e72e5ab"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="r301923f3838d459eb1d67b564857f7fb"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615014_p252141194858"><a name="zh-cn_topic_0079615014_p252141194858"></a><a name="zh-cn_topic_0079615014_p252141194858"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.99%" headers="mcps1.2.4.1.2 "><p id="aa3a7909553dc495bb5de644fe3dd8139"><a name="aa3a7909553dc495bb5de644fe3dd8139"></a><a name="aa3a7909553dc495bb5de644fe3dd8139"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="57.95%" headers="mcps1.2.4.1.3 "><p id="a1a8b9824958546b6960819b8b46185e5"><a name="a1a8b9824958546b6960819b8b46185e5"></a><a name="a1a8b9824958546b6960819b8b46185e5"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="r430b3cf656354984a9c00f2ae6b2f39c"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a3e0e853a80f749bdabde27857790df80"><a name="a3e0e853a80f749bdabde27857790df80"></a><a name="a3e0e853a80f749bdabde27857790df80"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.99%" headers="mcps1.2.4.1.2 "><p id="a4f0494d334f24f5ba645dd79d7d5af15"><a name="a4f0494d334f24f5ba645dd79d7d5af15"></a><a name="a4f0494d334f24f5ba645dd79d7d5af15"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="57.95%" headers="mcps1.2.4.1.3 "><p id="afdc203f80c7748cf947f9724e04063dd"><a name="afdc203f80c7748cf947f9724e04063dd"></a><a name="afdc203f80c7748cf947f9724e04063dd"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="rae45e71ecfba48bd86b86c7a3f3de003"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="adb16543fb0d54b98b587516041b8744b"><a name="adb16543fb0d54b98b587516041b8744b"></a><a name="adb16543fb0d54b98b587516041b8744b"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="19.99%" headers="mcps1.2.4.1.2 "><p id="ada85fd295cb2478db6c4de13886fca39"><a name="ada85fd295cb2478db6c4de13886fca39"></a><a name="ada85fd295cb2478db6c4de13886fca39"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="57.95%" headers="mcps1.2.4.1.3 "><p id="afc29214a680c4f2b9af39af8e6ca1fd9"><a name="afc29214a680c4f2b9af39af8e6ca1fd9"></a><a name="afc29214a680c4f2b9af39af8e6ca1fd9"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sfe2a0ff9b685403e99828e084231f0c5"></a>

N/A

## 响应消息<a name="s26637b3073a54198a524722022ff5ab4"></a>

**响应参数：**

**表 2**  响应参数

<a name="t96eb17162dc541b0ac14da07f10d4a59"></a>
<table><thead align="left"><tr id="r9b876eed979f4d8d95cc73130bdcef0c"><th class="cellrowborder" valign="top" width="25.069999999999997%" id="mcps1.2.4.1.1"><p id="a25728619ecab48b6953dc2a9d523978f"><a name="a25728619ecab48b6953dc2a9d523978f"></a><a name="a25728619ecab48b6953dc2a9d523978f"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.130000000000003%" id="mcps1.2.4.1.2"><p id="p9344806201939"><a name="p9344806201939"></a><a name="p9344806201939"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p18731826201939"><a name="p18731826201939"></a><a name="p18731826201939"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r81ae86da92b843d4892e839345bb9ba2"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="a5c610a6a9cb94585a3c8dc123407bbdc"><a name="a5c610a6a9cb94585a3c8dc123407bbdc"></a><a name="a5c610a6a9cb94585a3c8dc123407bbdc"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.130000000000003%" headers="mcps1.2.4.1.2 "><p id="acf1f5b6b90874a97bb1235462e636c19"><a name="acf1f5b6b90874a97bb1235462e636c19"></a><a name="acf1f5b6b90874a97bb1235462e636c19"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a84a7688aa18c44328dff13e3b4ae7a1b"><a name="a84a7688aa18c44328dff13e3b4ae7a1b"></a><a name="a84a7688aa18c44328dff13e3b4ae7a1b"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="ra3b61a1c18234ae5895fce21580fa7cf"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="ae197de9e4fdd41a5bb2b36da2741624f"><a name="ae197de9e4fdd41a5bb2b36da2741624f"></a><a name="ae197de9e4fdd41a5bb2b36da2741624f"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30.130000000000003%" headers="mcps1.2.4.1.2 "><p id="aeed7e4fc9cb046bb8a31f51a08a01ba3"><a name="aeed7e4fc9cb046bb8a31f51a08a01ba3"></a><a name="aeed7e4fc9cb046bb8a31f51a08a01ba3"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a6f1336d639b14f52aefdbed32248f795"><a name="a6f1336d639b14f52aefdbed32248f795"></a><a name="a6f1336d639b14f52aefdbed32248f795"></a>List of persistent volumes.</p>
<p id="p43239512330"><a name="p43239512330"></a><a name="p43239512330"></a>具体请参见<a href="创建PersistentVolume.md#tfdb73431f39846d4a56ec4eb558e1617">表2</a>。</p>
</td>
</tr>
<tr id="r1eae1b232e4a40a282f48a6c5dcfd2de"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="a7a01181f00f44f6ab8f5a7308e2962bf"><a name="a7a01181f00f44f6ab8f5a7308e2962bf"></a><a name="a7a01181f00f44f6ab8f5a7308e2962bf"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.130000000000003%" headers="mcps1.2.4.1.2 "><p id="a6f22d7ee594448ac9671530b2409b5cf"><a name="a6f22d7ee594448ac9671530b2409b5cf"></a><a name="a6f22d7ee594448ac9671530b2409b5cf"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="ab30461c3d24c4fb09f0f123ef11464e8"><a name="ab30461c3d24c4fb09f0f123ef11464e8"></a><a name="ab30461c3d24c4fb09f0f123ef11464e8"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="rf8a0ebda4114493e87e8ed92cdb6f07b"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="aca8ab7d645b34ec883c36ed5ce5a61f9"><a name="aca8ab7d645b34ec883c36ed5ce5a61f9"></a><a name="aca8ab7d645b34ec883c36ed5ce5a61f9"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.130000000000003%" headers="mcps1.2.4.1.2 "><p id="a431bb762c443456daa7cbcbc93a1b21e"><a name="a431bb762c443456daa7cbcbc93a1b21e"></a><a name="a431bb762c443456daa7cbcbc93a1b21e"></a><a href="#t0259714600444a569592dde7d2f11c77">ListMeta</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a22186cc4bee94b23aa645545743ffbd1"><a name="a22186cc4bee94b23aa645545743ffbd1"></a><a name="a22186cc4bee94b23aa645545743ffbd1"></a>Standard list metadata.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  ListMeta字段数据结构说明

<a name="t0259714600444a569592dde7d2f11c77"></a>
<table><thead align="left"><tr id="r62083060c9ac4d788389dfaff36156f6"><th class="cellrowborder" valign="top" width="25.069999999999997%" id="mcps1.2.4.1.1"><p id="a17fd4491bed6482ca1cb9a83c977e093"><a name="a17fd4491bed6482ca1cb9a83c977e093"></a><a name="a17fd4491bed6482ca1cb9a83c977e093"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.130000000000003%" id="mcps1.2.4.1.2"><p id="p55506439201939"><a name="p55506439201939"></a><a name="p55506439201939"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p66836606201939"><a name="p66836606201939"></a><a name="p66836606201939"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r9ef9105ba37d463f9c89317699d38d03"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="a22e75999705045ddb98446ba0a906555"><a name="a22e75999705045ddb98446ba0a906555"></a><a name="a22e75999705045ddb98446ba0a906555"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.130000000000003%" headers="mcps1.2.4.1.2 "><p id="ad0f806bec88d4b60b5019cb693021627"><a name="ad0f806bec88d4b60b5019cb693021627"></a><a name="ad0f806bec88d4b60b5019cb693021627"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a0558a3612ad24ef28973afa11def0bbd"><a name="a0558a3612ad24ef28973afa11def0bbd"></a><a name="a0558a3612ad24ef28973afa11def0bbd"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="r7ed17774e0cc459da534582eb6d532e3"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="abdcb80924b704166a4b0302e10283595"><a name="abdcb80924b704166a4b0302e10283595"></a><a name="abdcb80924b704166a4b0302e10283595"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.130000000000003%" headers="mcps1.2.4.1.2 "><p id="af39bf7dc4ce94309912cf5f6f5e18e2b"><a name="af39bf7dc4ce94309912cf5f6f5e18e2b"></a><a name="af39bf7dc4ce94309912cf5f6f5e18e2b"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a14f08edb188142508c0b28b2dbb90274"><a name="a14f08edb188142508c0b28b2dbb90274"></a><a name="a14f08edb188142508c0b28b2dbb90274"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "PersistentVolumeList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/persistentvolumes",
        "resourceVersion": "5672912"
    },
    "items": [
        {
            "metadata": {
                "name": "pv-test-02",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/persistentvolumes/pv-test-02",
                "uid": "98efd6aa-920a-11e8-81cc-fa163e49263c",
                "resourceVersion": "5672676",
                "creationTimestamp": "2018-07-28T02:04:44Z",
                "labels": {
                    "failure-domain.beta.kubernetes.io/region": "cn-north-4",
                    "failure-domain.beta.kubernetes.io/zone": "cn-north-4a",
                    "name": "pv-test-02"
                },
                "annotations": {
                    "volume.beta.kubernetes.io/storage-class": "sata",
                    "volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
                }
            },
            "spec": {
                "capacity": {
                    "storage": "10Gi"
                },
                "hostPath": {
                    "path": "/home",
                    "type": ""
                },
                "accessModes": [
                    "ReadWriteMany"
                ],
                "persistentVolumeReclaimPolicy": "Delete"
            },
            "status": {
                "phase": "Available"
            }
        }
    ]
}
```

## 状态码<a name="s65e32268b5f54d8b8a04518fb9f0779c"></a>

[表4](#t9fcf45e15dd94c479fec1cde9e04f2eb)描述API的状态码。

**表 4**  状态码

<a name="t9fcf45e15dd94c479fec1cde9e04f2eb"></a>
<table><thead align="left"><tr id="ra7e381a3ead0489aa3757438ec867d17"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p23983097201939"><a name="p23983097201939"></a><a name="p23983097201939"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p63582696201939"><a name="p63582696201939"></a><a name="p63582696201939"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r209c90b9d3fe4264aa12faf61b5464f3"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="a948dca46ff954c04935f4addc90d3399"><a name="a948dca46ff954c04935f4addc90d3399"></a><a name="a948dca46ff954c04935f4addc90d3399"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="ab8d8465a2531440989b1b0d21c28d85b"><a name="ab8d8465a2531440989b1b0d21c28d85b"></a><a name="ab8d8465a2531440989b1b0d21c28d85b"></a>This operation succeeds, and a group of PersistentVolume resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

