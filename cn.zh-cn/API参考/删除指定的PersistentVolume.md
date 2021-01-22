# 删除指定的PersistentVolume<a name="cce_02_0077"></a>

## 功能介绍<a name="s8901ba9fbe9e41598ca810c8c4ad6bc1"></a>

该API用于删除指定的PersistentVolume对象。

## URI<a name="s6ca51de79b434b5588410e3a5127373f"></a>

DELETE /api/v1/persistentvolumes/\{name\}

[表1](#tb28ffaf3c906456da48c0127534b7818)  描述该API的参数。

**表 1**  参数描述

<a name="tb28ffaf3c906456da48c0127534b7818"></a>
<table><thead align="left"><tr id="r617d4bc7c4ac43fe898c44ba988d2619"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="a4a0a77c892d74d0a9ef81d4be1fc0142"><a name="a4a0a77c892d74d0a9ef81d4be1fc0142"></a><a name="a4a0a77c892d74d0a9ef81d4be1fc0142"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.67%" id="mcps1.2.4.1.2"><p id="p91114513387"><a name="p91114513387"></a><a name="p91114513387"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="59.27%" id="mcps1.2.4.1.3"><p id="p181294515385"><a name="p181294515385"></a><a name="p181294515385"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r0e5983ceb4c246c9b81eb8f681fb00fa"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a131f9d2b10bb4860869b81bd299a4345"><a name="a131f9d2b10bb4860869b81bd299a4345"></a><a name="a131f9d2b10bb4860869b81bd299a4345"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="18.67%" headers="mcps1.2.4.1.2 "><p id="a8b9d2fc66a754eb4b9f51ea13f66d63c"><a name="a8b9d2fc66a754eb4b9f51ea13f66d63c"></a><a name="a8b9d2fc66a754eb4b9f51ea13f66d63c"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="59.27%" headers="mcps1.2.4.1.3 "><p id="a5354d4725fce4f06856e212a48badfb1"><a name="a5354d4725fce4f06856e212a48badfb1"></a><a name="a5354d4725fce4f06856e212a48badfb1"></a>Name of the PersistentVolume.</p>
</td>
</tr>
<tr id="rb5992764701b442b880a1abfa3dd28b4"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a3667d5d86a974ab8ab3fc577d70140b7"><a name="a3667d5d86a974ab8ab3fc577d70140b7"></a><a name="a3667d5d86a974ab8ab3fc577d70140b7"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="18.67%" headers="mcps1.2.4.1.2 "><p id="a743bf16483d948ad9f0bada5866c88de"><a name="a743bf16483d948ad9f0bada5866c88de"></a><a name="a743bf16483d948ad9f0bada5866c88de"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.27%" headers="mcps1.2.4.1.3 "><p id="a043c6e66828d412a830429550a403dcb"><a name="a043c6e66828d412a830429550a403dcb"></a><a name="a043c6e66828d412a830429550a403dcb"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="r7d99cfb353b14391b609779d0247c267"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a25762ee8783644678b59c04f53d51e92"><a name="a25762ee8783644678b59c04f53d51e92"></a><a name="a25762ee8783644678b59c04f53d51e92"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="18.67%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614956_p851141115490"><a name="zh-cn_topic_0079614956_p851141115490"></a><a name="zh-cn_topic_0079614956_p851141115490"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.27%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614956_p45151134915"><a name="zh-cn_topic_0079614956_p45151134915"></a><a name="zh-cn_topic_0079614956_p45151134915"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="r3b02d3e16592403ca21b02198c7bfb29"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="ac88d31bfbb5645baad4494bb1211dd6c"><a name="ac88d31bfbb5645baad4494bb1211dd6c"></a><a name="ac88d31bfbb5645baad4494bb1211dd6c"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="18.67%" headers="mcps1.2.4.1.2 "><p id="a55d293bb4b484074926227a80b6a4ffb"><a name="a55d293bb4b484074926227a80b6a4ffb"></a><a name="a55d293bb4b484074926227a80b6a4ffb"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.27%" headers="mcps1.2.4.1.3 "><p id="a62c1db6abe1f4d9c9f31d778ce58c67e"><a name="a62c1db6abe1f4d9c9f31d778ce58c67e"></a><a name="a62c1db6abe1f4d9c9f31d778ce58c67e"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="r7844c163da00465b82086557c4a35620"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614956_p816811514914"><a name="zh-cn_topic_0079614956_p816811514914"></a><a name="zh-cn_topic_0079614956_p816811514914"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="18.67%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614956_p416820151499"><a name="zh-cn_topic_0079614956_p416820151499"></a><a name="zh-cn_topic_0079614956_p416820151499"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="59.27%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614956_p71686159494"><a name="zh-cn_topic_0079614956_p71686159494"></a><a name="zh-cn_topic_0079614956_p71686159494"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s0683e5617b64436ba3eea347c7d07363"></a>

**请求参数：**

请求参数的详细描述请参见[表2](删除Endpoints.md#zh-cn_topic_0079614926_table29580916).

**请求示例：**

```
{ 
   "kind": "DeleteOptions", 
   "apiVersion": "v1", 
   "gracePeriodSeconds": 0 
 }
```

## 响应消息<a name="s16d87f79b1ad451984bd98bcd091493b"></a>

**响应参数：**

响应参数的详细描述请参见[表2](删除Secret.md#table13766144711235)。

**响应示例：**

1.15及以上版本集群，示例如下：

```
{
    "apiVersion": "v1",
    "kind": "PersistentVolume",
    "metadata": {
        "annotations": {
            "pv.kubernetes.io/provisioned-by": "everest-csi-provisioner"
        },
        "creationTimestamp": "2020-01-08T02:00:31Z",
        "deletionGracePeriodSeconds": 0,
        "deletionTimestamp": "2020-01-13T02:04:12Z",
        "finalizers": [
            "everest-csi-attacher/disk-csi-everest-io"
        ],
        "labels": {
            "failure-domain.beta.kubernetes.io/region": "cn-north-7",
            "failure-domain.beta.kubernetes.io/zone": "cn-north-7b"
        },
        "name": "pvc-efe92ec5-fb39-4e17-bb26-c5d336ce5c14",
        "resourceVersion": "5025500",
        "selfLink": "/api/v1/persistentvolumes/pvc-efe92ec5-fb39-4e17-bb26-c5d336ce5c14",
        "uid": "b14a40bc-8be7-4b26-90e5-975261d470a2"
    },
    "spec": {
        "accessModes": [
            "ReadWriteOnce"
        ],
        "capacity": {
            "storage": "20Gi"
        },
        "claimRef": {
            "apiVersion": "v1",
            "kind": "PersistentVolumeClaim",
            "name": "cce-evs-k54nobs9-ljhc",
            "namespace": "default",
            "resourceVersion": "3578282",
            "uid": "efe92ec5-fb39-4e17-bb26-c5d336ce5c14"
        },
        "csi": {
            "driver": "disk.csi.everest.io",
            "fsType": "ext4",
            "volumeAttributes": {
                "everest.io/disk-mode": "SCSI",
                "everest.io/disk-volume-type": "SATA",
                "storage.kubernetes.io/csiProvisionerIdentity": "everest-csi-provisioner"
            },
            "volumeHandle": "9c44d068-42ab-4fcf-bb8f-1609823da5bb"
        },
        "persistentVolumeReclaimPolicy": "Delete",
        "storageClassName": "csi-disk",
        "volumeMode": "Filesystem"
    },
    "status": {
        "phase": "Released"
    }
}
```

1.13及之前集群版本示例：

```
{
    "kind": "PersistentVolume",
    "apiVersion": "v1",
    "metadata": {
        "name": "pv-test-02",
        "generateName": "pv-demo",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/persistentvolumes/pv-test-02",
        "uid": "98efd6aa-920a-11e8-81cc-fa163e49263c",
        "resourceVersion": "5674455",
        "creationTimestamp": "2018-07-28T02:04:44Z",
        "labels": {
            "failure-domain.beta.kubernetes.io/region": "cn-north-4",
            "failure-domain.beta.kubernetes.io/zone": "cn-north-4a",
            "name": "pv-test-03"
        },
        "annotations": {
            "pv.kubernetes.io/bound-by-controller": "yes",
            "volume.beta.kubernetes.io/storage-class": "sata",
            "volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
        }
    },
    "spec": {
        "capacity": {
            "storage": "11Gi"
        },
        "hostPath": {
            "path": "/home",
            "type": ""
        },
        "accessModes": [
            "ReadWriteMany"
        ],
        "claimRef": {
            "kind": "PersistentVolumeClaim",
            "namespace": "default",
            "name": "db-mysql",
            "uid": "638e26ac-9148-11e8-8cd0-fa163e082286",
            "apiVersion": "v1",
            "resourceVersion": "5456583"
        },
        "persistentVolumeReclaimPolicy": "Delete"
    },
    "status": {
        "phase": "Bound"
    }
}
```

## 状态码<a name="sd1ea4eba5a624e07ba90fcd23319bd4e"></a>

[表2](#tafa4ae9910f84780a85f7b111bdafea6)描述API的状态码。

**表 2**  状态码

<a name="tafa4ae9910f84780a85f7b111bdafea6"></a>
<table><thead align="left"><tr id="r33076ffa4db14dd78ee7ce04e2eecf58"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p81111145113814"><a name="p81111145113814"></a><a name="p81111145113814"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p91132454381"><a name="p91132454381"></a><a name="p91132454381"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r188ec9cc97ca4259847bb8f3f3226b4b"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="a2fa6153697ab4cf0bfecd0ac700546d4"><a name="a2fa6153697ab4cf0bfecd0ac700546d4"></a><a name="a2fa6153697ab4cf0bfecd0ac700546d4"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614956_p633951365615"><a name="zh-cn_topic_0079614956_p633951365615"></a><a name="zh-cn_topic_0079614956_p633951365615"></a>Delete a specified PersistentVolume resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

