# 替换指定的PersistentVolumeClaim<a name="cce_02_0070"></a>

## 功能介绍<a name="sa5928b0d99984d7081f2c931c933d69d"></a>

该API用于替换指定Namespace下的PersistentVolumeClaim对象。

其中以下字段支持更新：

-   metadata.labels
-   metadata.generateName

## URI<a name="s87b8218f53d444f49f38d904a12edb17"></a>

PUT /api/v1/namespaces/\{namespace\}/persistentvolumeclaims/\{name\}

[表1](#tb472e3e9893d440e8123378d55bae83f)  描述该API的参数。

**表 1**  参数描述

<a name="tb472e3e9893d440e8123378d55bae83f"></a>
<table><thead align="left"><tr id="r9d44a43a0e2b4c249a00d113fb83ec02"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="a5b306c85a6024e728db73ca561e2601d"><a name="a5b306c85a6024e728db73ca561e2601d"></a><a name="a5b306c85a6024e728db73ca561e2601d"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p2047943620171"><a name="p2047943620171"></a><a name="p2047943620171"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.77%" id="mcps1.2.4.1.3"><p id="p4822159920171"><a name="p4822159920171"></a><a name="p4822159920171"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r8973bf87127645c6b482a034f8581e04"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a1c5b00e82749496b9a5ce76266641a8e"><a name="a1c5b00e82749496b9a5ce76266641a8e"></a><a name="a1c5b00e82749496b9a5ce76266641a8e"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="ab83a23bf0acc4db0be0aba137dc173a5"><a name="ab83a23bf0acc4db0be0aba137dc173a5"></a><a name="ab83a23bf0acc4db0be0aba137dc173a5"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.77%" headers="mcps1.2.4.1.3 "><p id="af90d022586e74e73b19fe1d7d78f5ea2"><a name="af90d022586e74e73b19fe1d7d78f5ea2"></a><a name="af90d022586e74e73b19fe1d7d78f5ea2"></a>Name of the PersistentVolumeClaim.</p>
</td>
</tr>
<tr id="r4cd4f7f44d374e1ab56368e02debfd56"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a7dd414a86f704898a67131ed07f488cd"><a name="a7dd414a86f704898a67131ed07f488cd"></a><a name="a7dd414a86f704898a67131ed07f488cd"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="a26b256f4f4f74a119a2460832bf7cf3f"><a name="a26b256f4f4f74a119a2460832bf7cf3f"></a><a name="a26b256f4f4f74a119a2460832bf7cf3f"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.77%" headers="mcps1.2.4.1.3 "><p id="adc067b71f30f407e85b8926683814f39"><a name="adc067b71f30f407e85b8926683814f39"></a><a name="adc067b71f30f407e85b8926683814f39"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="r947f59587e6e4d3bbcc63201427d90f6"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a2510fcb356b3400ab1a04f5c6c82a1e8"><a name="a2510fcb356b3400ab1a04f5c6c82a1e8"></a><a name="a2510fcb356b3400ab1a04f5c6c82a1e8"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="af00a18f9ab564e7088ab67cd2df9c4ac"><a name="af00a18f9ab564e7088ab67cd2df9c4ac"></a><a name="af00a18f9ab564e7088ab67cd2df9c4ac"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.77%" headers="mcps1.2.4.1.3 "><p id="a47770adf1d3c45af8939d3d07fd6aa5d"><a name="a47770adf1d3c45af8939d3d07fd6aa5d"></a><a name="a47770adf1d3c45af8939d3d07fd6aa5d"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sea7dee5d358f49a39d539b20e6aaa64a"></a>

**响应参数：**

请求参数的详细描述请参见[表2](创建PersistentVolumeClaim.md#t8268aeafde034542ab17a36c7fca65c3)

**请求示例：**

-   1.15及以上版本集群，示例如下：

    ```
    {
        "kind":"PersistentVolumeClaim",
        "apiVersion":"v1",
        "metadata":{
            "name":"cce-evs-k6m131jj-i1px",
            "namespace":"default",
            "selfLink":"/api/v1/namespaces/default/persistentvolumeclaims/cce-evs-k6m131jj-i1px",
            "uid":"d34f6a93-9eba-4a33-9320-8fa4addd3753",
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
        }
    }
    ```

-   1.13及之前集群版本yaml示例：

    ```
    {
        "kind": "PersistentVolumeClaim",
        "apiVersion": "v1",
        "metadata": {
            "name": "db-mysql-0",
            "namespace": "default",
            "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims/db-mysql-0",
            "uid": "f6585eb2-8cdd-11e8-a538-fa163e082286",
            "resourceVersion": "4198033",
            "creationTimestamp": "2018-07-21T12:02:38Z",
            "labels": {
                "failure-domain.beta.kubernetes.io/region": "cn-north-4",
                "failure-domain.beta.kubernetes.io/zone": "cn-north-4a",
                "app":"mysql"
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
    ```


## 响应消息<a name="sa1c46b09ebf345e6bb23a1502709a639"></a>

**响应参数：**

响应参数的详细描述请参见[14.2-Table2 Request parameters](创建PersistentVolumeClaim.md#t8268aeafde034542ab17a36c7fca65c3).

**响应示例：**

-   1.15及以上版本集群，示例如下：

    ```
    {
        "kind":"PersistentVolumeClaim",
        "apiVersion":"v1",
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
    ```

-   1.13及之前版本示例：

    ```
    {
        "kind": "PersistentVolumeClaim",
        "apiVersion": "v1",
        "metadata": {
            "name": "db-mysql-0",
            "namespace": "default",
            "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims/db-mysql-0",
            "uid": "f6585eb2-8cdd-11e8-a538-fa163e082286",
            "resourceVersion": "4201550",
            "creationTimestamp": "2018-07-21T12:02:38Z",
            "labels": {
                "app": "mysql",
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
    ```


## 状态码<a name="sfa20934b9ee24b2fa016b29e7345d356"></a>

[表2](#t668f7dd3090a42978732e583cc84d7c0)描述API的状态码。

**表 2**  状态码

<a name="t668f7dd3090a42978732e583cc84d7c0"></a>
<table><thead align="left"><tr id="rf6bc622186054c718b25b71fd3b36d83"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p408989920171"><a name="p408989920171"></a><a name="p408989920171"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p6284643120171"><a name="p6284643120171"></a><a name="p6284643120171"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rb0025aac94e44cd181e28eea627b03c5"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="af7dba24c4dda4252bbbe016cee1a28e6"><a name="af7dba24c4dda4252bbbe016cee1a28e6"></a><a name="af7dba24c4dda4252bbbe016cee1a28e6"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="a9318460675b44b2085529a621c4b985a"><a name="a9318460675b44b2085529a621c4b985a"></a><a name="a9318460675b44b2085529a621c4b985a"></a>This operation succeeds, and a PersistentVolumeClaim resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

