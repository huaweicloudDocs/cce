# 列出指定的Namespace下的PersistentVolumeClaim<a name="cce_02_0072"></a>

## 功能介绍<a name="s56cf46cd1088494ba3345c1672a9b59a"></a>

该API用于列出指定Namespace下的所有PersistentVolumeClaim资源对象。

## URI<a name="s31d720a41bf84b65b5d3417e08ffcadb"></a>

GET /api/v1/namespaces/\{namespace\}/persistentvolumeclaims

[表1](#tf27da786f0794f6eba4e51fcf287b04d)  描述该API的参数。

**表 1**  参数描述

<a name="tf27da786f0794f6eba4e51fcf287b04d"></a>
<table><thead align="left"><tr id="r780cad841a0f42c6ac0d6751b45201bc"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="afd18f336b4d846c08f40381b274a8897"><a name="afd18f336b4d846c08f40381b274a8897"></a><a name="afd18f336b4d846c08f40381b274a8897"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.86%" id="mcps1.2.4.1.2"><p id="p1639850420177"><a name="p1639850420177"></a><a name="p1639850420177"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="59.08%" id="mcps1.2.4.1.3"><p id="p5321047720177"><a name="p5321047720177"></a><a name="p5321047720177"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r1b54c86c26a64776a80a484e335385af"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a597808b10ebf4f92880302a98f58e1d7"><a name="a597808b10ebf4f92880302a98f58e1d7"></a><a name="a597808b10ebf4f92880302a98f58e1d7"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="aedb98a7375d441b8a8ec2914954a8520"><a name="aedb98a7375d441b8a8ec2914954a8520"></a><a name="aedb98a7375d441b8a8ec2914954a8520"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a1a4e6c2d59304f449b2f2a6d6de7b0b6"><a name="a1a4e6c2d59304f449b2f2a6d6de7b0b6"></a><a name="a1a4e6c2d59304f449b2f2a6d6de7b0b6"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="r72a077f3cde9477db1924e6cb517656b"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a47f936542ae449f5956c22ced235872a"><a name="a47f936542ae449f5956c22ced235872a"></a><a name="a47f936542ae449f5956c22ced235872a"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="a65cb02b0c22c4d38b2cecd60b7ba32d1"><a name="a65cb02b0c22c4d38b2cecd60b7ba32d1"></a><a name="a65cb02b0c22c4d38b2cecd60b7ba32d1"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="af70410f32f45415c96e1c617e629c3d9"><a name="af70410f32f45415c96e1c617e629c3d9"></a><a name="af70410f32f45415c96e1c617e629c3d9"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="raed9402a1c78445da9ed8490a68db562"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a9684ee28e2f745cc94ea97e78f0fd6a2"><a name="a9684ee28e2f745cc94ea97e78f0fd6a2"></a><a name="a9684ee28e2f745cc94ea97e78f0fd6a2"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="ad7d41fac848b497192a8d4c4d1db5111"><a name="ad7d41fac848b497192a8d4c4d1db5111"></a><a name="ad7d41fac848b497192a8d4c4d1db5111"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a6208a0dbf69c42f69fdfc6d7b2d029e9"><a name="a6208a0dbf69c42f69fdfc6d7b2d029e9"></a><a name="a6208a0dbf69c42f69fdfc6d7b2d029e9"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="rc37c871b94344e86a1a6c172ec12d00f"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="ae4ea9dbd389340a798552cc70c490133"><a name="ae4ea9dbd389340a798552cc70c490133"></a><a name="ae4ea9dbd389340a798552cc70c490133"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="a9bfe38430cff4e54ad58607cf30cf81f"><a name="a9bfe38430cff4e54ad58607cf30cf81f"></a><a name="a9bfe38430cff4e54ad58607cf30cf81f"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a937063dd2cc84d6ea673e63ff1f4b21b"><a name="a937063dd2cc84d6ea673e63ff1f4b21b"></a><a name="a937063dd2cc84d6ea673e63ff1f4b21b"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="r77fef211aee04eb8accff8d15db8d987"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a7ae70a1a54b94d8a8a96e3a3dae01dd2"><a name="a7ae70a1a54b94d8a8a96e3a3dae01dd2"></a><a name="a7ae70a1a54b94d8a8a96e3a3dae01dd2"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="ad5b3d9a606d8415a9861e2edf83d4ce7"><a name="ad5b3d9a606d8415a9861e2edf83d4ce7"></a><a name="ad5b3d9a606d8415a9861e2edf83d4ce7"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a2bf33982996b47c99a515fc8016164e8"><a name="a2bf33982996b47c99a515fc8016164e8"></a><a name="a2bf33982996b47c99a515fc8016164e8"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="re5aeab2d41d34489a98b535524db1649"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a3d9ba6912f174c9bb3dea45b320fbb8b"><a name="a3d9ba6912f174c9bb3dea45b320fbb8b"></a><a name="a3d9ba6912f174c9bb3dea45b320fbb8b"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="a170e694c132c4a86bac2e6dbf3f6725f"><a name="a170e694c132c4a86bac2e6dbf3f6725f"></a><a name="a170e694c132c4a86bac2e6dbf3f6725f"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a8c964fca76c344e0a09ec6457ee0cb71"><a name="a8c964fca76c344e0a09ec6457ee0cb71"></a><a name="a8c964fca76c344e0a09ec6457ee0cb71"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="r11334e66cada44adb312e169a3ea462c"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a2641d6a3294c41aeb524bd0cda02ed4a"><a name="a2641d6a3294c41aeb524bd0cda02ed4a"></a><a name="a2641d6a3294c41aeb524bd0cda02ed4a"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615077_p880733710130"><a name="zh-cn_topic_0079615077_p880733710130"></a><a name="zh-cn_topic_0079615077_p880733710130"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a2986bf94c6ad41b4bc09e295bf4be90f"><a name="a2986bf94c6ad41b4bc09e295bf4be90f"></a><a name="a2986bf94c6ad41b4bc09e295bf4be90f"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="ra450fd84fd6a4ee5a2053cbf89bd65ed"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a1d680086c57c4a29a7ca1ded242b1600"><a name="a1d680086c57c4a29a7ca1ded242b1600"></a><a name="a1d680086c57c4a29a7ca1ded242b1600"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="a8c0f0077b37c481dac8c7255c7b1ede4"><a name="a8c0f0077b37c481dac8c7255c7b1ede4"></a><a name="a8c0f0077b37c481dac8c7255c7b1ede4"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a27a55e3491bc4f8eb10ca73c1599808e"><a name="a27a55e3491bc4f8eb10ca73c1599808e"></a><a name="a27a55e3491bc4f8eb10ca73c1599808e"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s1aaade19a5f2449c8f90fc400cb59e0a"></a>

N/A

## 响应消息<a name="se1ddbf9e5de0401e83a36b0530ef7b5d"></a>

**响应参数：**

**表 2**  响应参数

<a name="t48c604ca9f9f44e59b88ea85d6d7fd4b"></a>
<table><thead align="left"><tr id="raeae77d8f5b948b88cf7180aa835e76b"><th class="cellrowborder" valign="top" width="25.06250625062506%" id="mcps1.2.4.1.1"><p id="aa639e5fdbd7348ec99ace53fd3f7c7fe"><a name="aa639e5fdbd7348ec99ace53fd3f7c7fe"></a><a name="aa639e5fdbd7348ec99ace53fd3f7c7fe"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.133013301330138%" id="mcps1.2.4.1.2"><p id="p1613864020177"><a name="p1613864020177"></a><a name="p1613864020177"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.80448044804481%" id="mcps1.2.4.1.3"><p id="p3216145220177"><a name="p3216145220177"></a><a name="p3216145220177"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r2b4dd214f0544472b7625477a01045f9"><td class="cellrowborder" valign="top" width="25.06250625062506%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615077_p177982811595"><a name="zh-cn_topic_0079615077_p177982811595"></a><a name="zh-cn_topic_0079615077_p177982811595"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.133013301330138%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615077_p67799281595"><a name="zh-cn_topic_0079615077_p67799281595"></a><a name="zh-cn_topic_0079615077_p67799281595"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.80448044804481%" headers="mcps1.2.4.1.3 "><p id="a7689ae74b4544aadbcb7258528f0468d"><a name="a7689ae74b4544aadbcb7258528f0468d"></a><a name="a7689ae74b4544aadbcb7258528f0468d"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="rc58b8c615b0f4f7383a700da7fd20ca8"><td class="cellrowborder" valign="top" width="25.06250625062506%" headers="mcps1.2.4.1.1 "><p id="a24007e1bf96c4976871920b20bfc745e"><a name="a24007e1bf96c4976871920b20bfc745e"></a><a name="a24007e1bf96c4976871920b20bfc745e"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.133013301330138%" headers="mcps1.2.4.1.2 "><p id="a5ab61ab4b11c441b9104b737061f3a75"><a name="a5ab61ab4b11c441b9104b737061f3a75"></a><a name="a5ab61ab4b11c441b9104b737061f3a75"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.80448044804481%" headers="mcps1.2.4.1.3 "><p id="aa6853b8f941540b9a9d451ce15670447"><a name="aa6853b8f941540b9a9d451ce15670447"></a><a name="aa6853b8f941540b9a9d451ce15670447"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="rbf2743dcae9b4bdb8c6456574bd392e2"><td class="cellrowborder" valign="top" width="25.06250625062506%" headers="mcps1.2.4.1.1 "><p id="a761cefa8d3f841ed99e30e8e50f2d6b6"><a name="a761cefa8d3f841ed99e30e8e50f2d6b6"></a><a name="a761cefa8d3f841ed99e30e8e50f2d6b6"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.133013301330138%" headers="mcps1.2.4.1.2 "><p id="af180fe2686704ca09b7c7c19780efcfa"><a name="af180fe2686704ca09b7c7c19780efcfa"></a><a name="af180fe2686704ca09b7c7c19780efcfa"></a><a href="#ta2fc9dc3f1d44679823d5c4a9c14722c">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.80448044804481%" headers="mcps1.2.4.1.3 "><p id="adec13d3c70784e1bbc784b93d0db2270"><a name="adec13d3c70784e1bbc784b93d0db2270"></a><a name="adec13d3c70784e1bbc784b93d0db2270"></a>Standard list metadata.</p>
</td>
</tr>
<tr id="r0da1d356e44d4363ad1b8d8bc4748c13"><td class="cellrowborder" valign="top" width="25.06250625062506%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615077_p26077174593"><a name="zh-cn_topic_0079615077_p26077174593"></a><a name="zh-cn_topic_0079615077_p26077174593"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30.133013301330138%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615077_p960791745920"><a name="zh-cn_topic_0079615077_p960791745920"></a><a name="zh-cn_topic_0079615077_p960791745920"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.80448044804481%" headers="mcps1.2.4.1.3 "><p id="ac1b99f17181549ae885fa9e19b91b2d2"><a name="ac1b99f17181549ae885fa9e19b91b2d2"></a><a name="ac1b99f17181549ae885fa9e19b91b2d2"></a>A list of persistent volume claims.</p>
<p id="p13804044296"><a name="p13804044296"></a><a name="p13804044296"></a>具体请参见<a href="创建PersistentVolumeClaim.md#t8268aeafde034542ab17a36c7fca65c3">14.2-Table2 Request parameters</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="ta2fc9dc3f1d44679823d5c4a9c14722c"></a>
<table><thead align="left"><tr id="r9823dbc490e54bc388b43d154dd7583c"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="a746ea03ac38e40b78670ff7222482e26"><a name="a746ea03ac38e40b78670ff7222482e26"></a><a name="a746ea03ac38e40b78670ff7222482e26"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p5264627420177"><a name="p5264627420177"></a><a name="p5264627420177"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p3648980620177"><a name="p3648980620177"></a><a name="p3648980620177"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rfc07824cd6f74ee493bb2de0271ba79e"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="a17937f10d414416188d55a7c76e8e125"><a name="a17937f10d414416188d55a7c76e8e125"></a><a name="a17937f10d414416188d55a7c76e8e125"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="a7c606b1aaf5c4fb78b9941126deb8c2e"><a name="a7c606b1aaf5c4fb78b9941126deb8c2e"></a><a name="a7c606b1aaf5c4fb78b9941126deb8c2e"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="a3230eb2bdc574173b17e5a3789c474a8"><a name="a3230eb2bdc574173b17e5a3789c474a8"></a><a name="a3230eb2bdc574173b17e5a3789c474a8"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="r6a4af3ce05a940fcb4794559ce47cb45"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="a7d7750b075a642eca6fbc55870b04a64"><a name="a7d7750b075a642eca6fbc55870b04a64"></a><a name="a7d7750b075a642eca6fbc55870b04a64"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="a66eb5b8266e444a0890db93c9608fd55"><a name="a66eb5b8266e444a0890db93c9608fd55"></a><a name="a66eb5b8266e444a0890db93c9608fd55"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="a46d894aae9c54a94b0ea0d1e1fc7c785"><a name="a46d894aae9c54a94b0ea0d1e1fc7c785"></a><a name="a46d894aae9c54a94b0ea0d1e1fc7c785"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

-   1.15及以上版本集群，示例如下：

    ```
    {
        "kind":"PersistentVolumeClaimList",
        "apiVersion":"v1",
        "metadata":{
            "selfLink":"/api/v1/persistentvolumeclaims",
            "resourceVersion":"2306215"
        },
        "items":[
            {
                "metadata":{
                    "name":"cce-evs-k6m131jj-i1px",
                    "namespace":"default",
                    "selfLink":"/api/v1/namespaces/default/persistentvolumeclaims/cce-evs-k6m131jj-i1px",
                    "uid":"d34f6a93-9eba-4a33-9320-8fa4addd3753",
                    "resourceVersion":"2286592",
                    "creationTimestamp":"2020-02-14T10:27:43Z",
                    "labels":{
                        "failure-domain.beta.kubernetes.io/region":"cn-north-5",
                        "failure-domain.beta.kubernetes.io/zone":"cn-north-5a"
                    },
                    "annotations":{
                        "everest.io/disk-volume-type":"SAS",
                        "pv.kubernetes.io/bind-completed":"yes",
                        "pv.kubernetes.io/bound-by-controller":"yes",
                        "volume.beta.kubernetes.io/storage-provisioner":"everest-csi-provisioner"
                    },
                    "finalizers":[
                        "kubernetes.io/pvc-protection"
                    ]
                },
                "spec":{
                    "accessModes":[
                        "ReadWriteOnce"
                    ],
                    "resources":{
                        "requests":{
                            "storage":"10Gi"
                        }
                    },
                    "volumeName":"pvc-d34f6a93-9eba-4a33-9320-8fa4addd3753",
                    "storageClassName":"csi-disk",
                    "volumeMode":"Filesystem"
                },
                "status":{
                    "phase":"Bound",
                    "accessModes":[
                        "ReadWriteOnce"
                    ],
                    "capacity":{
                        "storage":"10Gi"
                    }
                }
            }
        ]
    }
    ```

-   1.13及之前集群版本示例：

    ```
    {
        "kind": "PersistentVolumeClaimList",
        "apiVersion": "v1",
        "metadata": {
            "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims",
            "resourceVersion": "4198037"
        },
        "items": [
            {
                "metadata": {
                    "name": "db-mysql",
                    "namespace": "default",
                    "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims/db-mysql",
                    "uid": "ac34af93-8cdd-11e8-8ee0-fa163e49263c",
                    "resourceVersion": "4197709",
                    "creationTimestamp": "2018-07-21T12:00:33Z",
                    "labels": {
                        "failure-domain.beta.kubernetes.io/region": "cn-north-4",
                        "failure-domain.beta.kubernetes.io/zone": "cn-north-4a"
                    },
                    "annotations": {
                        "pv.kubernetes.io/bind-completed": "yes",
                        "pv.kubernetes.io/bound-by-controller": "yes",
                        "volume.beta.kubernetes.io/storage-class": "SAS",
                        "volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
                    }
                },
                "spec": {
                    "accessModes": [
                        "ReadWriteMany"
                    ],
                    "resources": {
                        "requests": {
                            "storage": "10Gi"
                        }
                    },
                    "volumeName": "pvc-ac34af93-8cdd-11e8-8ee0-fa163e49263c",
                    "volumeNamespace": "default"
                },
                "status": {
                    "phase": "Bound",
                    "accessModes": [
                        "ReadWriteMany"
                    ],
                    "capacity": {
                        "storage": "10Gi"
                    }
                }
            },
            {
                "metadata": {
                    "name": "db-mysql-0",
                    "namespace": "default",
                    "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims/db-mysql-0",
                    "uid": "f6585eb2-8cdd-11e8-a538-fa163e082286",
                    "resourceVersion": "4198033",
                    "creationTimestamp": "2018-07-21T12:02:38Z",
                    "labels": {
                        "failure-domain.beta.kubernetes.io/region": "cn-north-4",
                        "failure-domain.beta.kubernetes.io/zone": "cn-north-4a"
                    },
                    "annotations": {
                        "pv.kubernetes.io/bind-completed": "yes",
                        "pv.kubernetes.io/bound-by-controller": "yes",
                        "volume.beta.kubernetes.io/storage-class": "SAS",
                        "volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
                    }
                },
                "spec": {
                    "accessModes": [
                        "ReadWriteMany"
                    ],
                    "resources": {
                        "requests": {
                            "storage": "5Gi"
                        }
                    },
                    "volumeName": "pvc-f6585eb2-8cdd-11e8-a538-fa163e082286",
                    "volumeNamespace": "default"
                },
                "status": {
                    "phase": "Bound",
                    "accessModes": [
                        "ReadWriteMany"
                    ],
                    "capacity": {
                        "storage": "5Gi"
                    }
                }
            }
        ]
    }
    ```


