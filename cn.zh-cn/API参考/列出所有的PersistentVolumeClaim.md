# 列出所有的PersistentVolumeClaim<a name="cce_02_0073"></a>

## 功能介绍<a name="s419b592e6d664d2a9010e11d7827da33"></a>

该API用于列出所有PersistentVolumeClaim资源对象。

## URI<a name="sf7f351f2615e4e6e8b408a05063d02d3"></a>

GET /api/v1/persistentvolumeclaims

[表1](#t6b92864f18d942c89acd1858b2fb3da8)  描述该API的参数。

**表 1**  参数描述

<a name="t6b92864f18d942c89acd1858b2fb3da8"></a>
<table><thead align="left"><tr id="r6b1edf52a0104b4f8b71c51befb02dbd"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="a9906cec577554cb1bbe36718a3317801"><a name="a9906cec577554cb1bbe36718a3317801"></a><a name="a9906cec577554cb1bbe36718a3317801"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.86%" id="mcps1.2.4.1.2"><p id="p61237453201936"><a name="p61237453201936"></a><a name="p61237453201936"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="59.08%" id="mcps1.2.4.1.3"><p id="p61286638201936"><a name="p61286638201936"></a><a name="p61286638201936"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r47acf5fc764b4be3810bcff262dd111b"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a1ec35f9be66b4865a2c0b029c1d31a65"><a name="a1ec35f9be66b4865a2c0b029c1d31a65"></a><a name="a1ec35f9be66b4865a2c0b029c1d31a65"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="ae7de412cd8cf47309c3a036fd34cefce"><a name="ae7de412cd8cf47309c3a036fd34cefce"></a><a name="ae7de412cd8cf47309c3a036fd34cefce"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a36703598d31d46938a53a1c632d3a96e"><a name="a36703598d31d46938a53a1c632d3a96e"></a><a name="a36703598d31d46938a53a1c632d3a96e"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="ra6f05d8566844acca4f099699b9a48cc"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="af5e38663515643ab8f85660e6cca3c7b"><a name="af5e38663515643ab8f85660e6cca3c7b"></a><a name="af5e38663515643ab8f85660e6cca3c7b"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="a98f1d5376e7d48b68d884e908802db5a"><a name="a98f1d5376e7d48b68d884e908802db5a"></a><a name="a98f1d5376e7d48b68d884e908802db5a"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="ad12822b4825947d4b54aeb87466db6d9"><a name="ad12822b4825947d4b54aeb87466db6d9"></a><a name="ad12822b4825947d4b54aeb87466db6d9"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="r45a5b76d80a241e386f5d195fe707ad2"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a735ba7709b58448088448d093801f76e"><a name="a735ba7709b58448088448d093801f76e"></a><a name="a735ba7709b58448088448d093801f76e"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="a1a15d5159b6d4c44a03894fcca58cf2b"><a name="a1a15d5159b6d4c44a03894fcca58cf2b"></a><a name="a1a15d5159b6d4c44a03894fcca58cf2b"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="ac058c5207cb04b7d9ce7385d686f7414"><a name="ac058c5207cb04b7d9ce7385d686f7414"></a><a name="ac058c5207cb04b7d9ce7385d686f7414"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="ra2698a0d3203460295e39ee586bb7e77"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614913_p179965371657"><a name="zh-cn_topic_0079614913_p179965371657"></a><a name="zh-cn_topic_0079614913_p179965371657"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614913_p69969371454"><a name="zh-cn_topic_0079614913_p69969371454"></a><a name="zh-cn_topic_0079614913_p69969371454"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="afca2a8f422154c699d27efaddd699c6a"><a name="afca2a8f422154c699d27efaddd699c6a"></a><a name="afca2a8f422154c699d27efaddd699c6a"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="r38af030b759941ce8897ca4936950d96"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a339734bd9bfe441e8c411543023a6982"><a name="a339734bd9bfe441e8c411543023a6982"></a><a name="a339734bd9bfe441e8c411543023a6982"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="a5a710450a7d44ddfb1794b2df554dd88"><a name="a5a710450a7d44ddfb1794b2df554dd88"></a><a name="a5a710450a7d44ddfb1794b2df554dd88"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a11cd50565cca4ec8a49d4a624e40d9b2"><a name="a11cd50565cca4ec8a49d4a624e40d9b2"></a><a name="a11cd50565cca4ec8a49d4a624e40d9b2"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="r4b2bf7f86f9b4ea4bab7fe8ff18bbbda"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="ac73dd4a4e5e140579dcc7866a7b4a3e2"><a name="ac73dd4a4e5e140579dcc7866a7b4a3e2"></a><a name="ac73dd4a4e5e140579dcc7866a7b4a3e2"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="a7f3e1bbba02646b99502f64728befdf4"><a name="a7f3e1bbba02646b99502f64728befdf4"></a><a name="a7f3e1bbba02646b99502f64728befdf4"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="a439ec24f824049a8a6fc8b6d2ba08281"><a name="a439ec24f824049a8a6fc8b6d2ba08281"></a><a name="a439ec24f824049a8a6fc8b6d2ba08281"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="r33f502ee6d7245d78bc42301ca74b000"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a82a17d68c9794c7eaf07fd3675a22af3"><a name="a82a17d68c9794c7eaf07fd3675a22af3"></a><a name="a82a17d68c9794c7eaf07fd3675a22af3"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.4.1.2 "><p id="a2f3dff2b74f2422c805463d26363bec2"><a name="a2f3dff2b74f2422c805463d26363bec2"></a><a name="a2f3dff2b74f2422c805463d26363bec2"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.08%" headers="mcps1.2.4.1.3 "><p id="ab491f77a059b49e498a5670c6260dcd7"><a name="ab491f77a059b49e498a5670c6260dcd7"></a><a name="ab491f77a059b49e498a5670c6260dcd7"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sac85a222ad14406fae75d886d2a16aa3"></a>

N/A

## 响应消息<a name="s8fc92ce98f764f1299b6c9ced833982a"></a>

**响应参数：**

响应参数的详细描述请参见[表2](列出指定的Namespace下的PersistentVolumeClaim.md#t48c604ca9f9f44e59b88ea85d6d7fd4b).

**响应示例：**

-   1.15及之后集群版本示例

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
                        "everest.io/disk-volume-type":"SATA",
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
            "selfLink": "/api/v1/persistentvolumeclaims",
            "resourceVersion": "4199767"
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
                        "volume.beta.kubernetes.io/storage-class": "sata",
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
                        "volume.beta.kubernetes.io/storage-class": "sata",
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


## 状态码<a name="s835f981137fb4bbd8f86cb5c3e26aa33"></a>

[表2](#t732ea95ebdf44998842e9f9d835eb7ef)描述API的状态码。

**表 2**  状态码

<a name="t732ea95ebdf44998842e9f9d835eb7ef"></a>
<table><thead align="left"><tr id="rbeca8ec7f4fe4298920d4c04907de61f"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p13707436201936"><a name="p13707436201936"></a><a name="p13707436201936"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p36560517201936"><a name="p36560517201936"></a><a name="p36560517201936"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r389885a0f1544af49f9b465ee30f875b"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="a4069a31ee9764037a4a3f56b92809771"><a name="a4069a31ee9764037a4a3f56b92809771"></a><a name="a4069a31ee9764037a4a3f56b92809771"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="a7b02d08e24044db89eb591ba87ca2651"><a name="a7b02d08e24044db89eb591ba87ca2651"></a><a name="a7b02d08e24044db89eb591ba87ca2651"></a>This operation succeeds, and a group of PersistentVolumeClaim resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

