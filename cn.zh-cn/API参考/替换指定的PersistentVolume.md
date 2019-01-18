# 替换指定的PersistentVolume<a name="cce_02_0079"></a>

## 功能介绍<a name="see0a611522774fda83054d4db7583d2e"></a>

该API用于替换指定的PersistentVolume对象。

其中以下字段支持更新：

-   metadata.labels
-   metadata.generateName
-   spec.accessModes
-   spec.capacity
-   spec.persistentVolumeReclaimPolicy

## URI<a name="sae9200e2419646fa9c2892da2426f173"></a>

PUT /api/v1/persistentvolumes/\{name\}

[表1](#tef189c476e174ba0b34a0ce1e3ee2cc9)  描述该API的参数。

**表 1**  参数描述

<a name="tef189c476e174ba0b34a0ce1e3ee2cc9"></a>
<table><thead align="left"><tr id="r84d29e2c03f64f8ab98fa3e981da6fb5"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="a063c22b1a3304a7aa169e0d0050be3d8"><a name="a063c22b1a3304a7aa169e0d0050be3d8"></a><a name="a063c22b1a3304a7aa169e0d0050be3d8"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.05%" id="mcps1.2.4.1.2"><p id="p37916570201720"><a name="p37916570201720"></a><a name="p37916570201720"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="58.89%" id="mcps1.2.4.1.3"><p id="p51343366201720"><a name="p51343366201720"></a><a name="p51343366201720"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r78c58e7564404f1f9c250b4e8fd34223"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a9c432d5188dc4eafaabab03fdbd94dec"><a name="a9c432d5188dc4eafaabab03fdbd94dec"></a><a name="a9c432d5188dc4eafaabab03fdbd94dec"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.05%" headers="mcps1.2.4.1.2 "><p id="ad0227f6a0e3a4358991be1c5696d3212"><a name="ad0227f6a0e3a4358991be1c5696d3212"></a><a name="ad0227f6a0e3a4358991be1c5696d3212"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="58.89%" headers="mcps1.2.4.1.3 "><p id="af1e34546985945889bb73f641130cd86"><a name="af1e34546985945889bb73f641130cd86"></a><a name="af1e34546985945889bb73f641130cd86"></a>Name of the PersistentVolume.</p>
</td>
</tr>
<tr id="r39b1197edb204bc489cef97822e0fa8e"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="aa5e6df89a303450ebb72f9d07c5ce203"><a name="aa5e6df89a303450ebb72f9d07c5ce203"></a><a name="aa5e6df89a303450ebb72f9d07c5ce203"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="19.05%" headers="mcps1.2.4.1.2 "><p id="a7737d1d5bb80449e83898d5de2d5a7a2"><a name="a7737d1d5bb80449e83898d5de2d5a7a2"></a><a name="a7737d1d5bb80449e83898d5de2d5a7a2"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="58.89%" headers="mcps1.2.4.1.3 "><p id="ad9adc52700fe4126bb1db09bfdadbc3e"><a name="ad9adc52700fe4126bb1db09bfdadbc3e"></a><a name="ad9adc52700fe4126bb1db09bfdadbc3e"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s0b715f8af10643e98668ac57049da327"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建PersistentVolume-1.md#tfdb73431f39846d4a56ec4eb558e1617)。

**请求示例：**

```
{ 
    "apiVersion": "v1", 
    "kind": "PersistentVolume", 
    "metadata": { 
        "labels": { 
	"failure-domain.beta.kubernetes.io/region": "cn-north-1",
	"failure-domain.beta.kubernetes.io/zone": "cn-north-1a",
            "name": "pv-test-03" 
        }, 
        "name": "pv-test-02",
        "annotations": {
	"volume.beta.kubernetes.io/storage-class": "sata",
	"volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
        },
        "generateName": "pv-demo"
    }, 
    "spec": { 
        "accessModes": [ 
            "ReadWriteMany" 
        ], 
        "capacity": { 
            "storage": "11Gi" 
        }, 
        "hostPath": { 
            "path": "/home" 
        }, 
        "persistentVolumeReclaimPolicy": "Delete" 
    } 
}
```

## 响应消息<a name="s5455488dd62741c1b14674b7148b38cd"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建PersistentVolume-1.md#tfdb73431f39846d4a56ec4eb558e1617).

**响应示例：**

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
        "resourceVersion": "5673741",
        "creationTimestamp": "2018-07-28T02:04:44Z",
        "labels": {
            "failure-domain.beta.kubernetes.io/region": "cn-north-1",
            "failure-domain.beta.kubernetes.io/zone": "cn-north-1a",
            "name": "pv-test-03"
        },
        "annotations": {
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
        "persistentVolumeReclaimPolicy": "Delete"
    },
    "status": {
        "phase": "Available"
    }
}
```

## 状态码<a name="s71097d457bd14572b91eee0509e05e21"></a>

[表2](#tf9990cd5591b439ca16fd00faec02a0e)描述API的状态码。

**表 2**  状态码

<a name="tf9990cd5591b439ca16fd00faec02a0e"></a>
<table><thead align="left"><tr id="recf3f3bcb6b14d5e808694ea29056eec"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p36839200201720"><a name="p36839200201720"></a><a name="p36839200201720"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p31185239201720"><a name="p31185239201720"></a><a name="p31185239201720"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rdd5dfd85ac324160af9d515272d07736"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="ab969ada844774771a35b8e9b25f43dee"><a name="ab969ada844774771a35b8e9b25f43dee"></a><a name="ab969ada844774771a35b8e9b25f43dee"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="ae4b41d1e2e824f32b7ba461190ca8acf"><a name="ae4b41d1e2e824f32b7ba461190ca8acf"></a><a name="ae4b41d1e2e824f32b7ba461190ca8acf"></a>This operation succeeds, and a PersistentVolume resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

