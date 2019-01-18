# 替换指定的PersistentVolume的状态<a name="cce_02_0080"></a>

## 功能介绍<a name="sadbc5fb215c04f0e8e8325e0e16d275e"></a>

该API用于替换指定的PersistentVolume对象的状态。

其中以下字段支持更新：

-   status.phase

## URI<a name="s276514e02b864c299d30dd77b707d0be"></a>

PUT /api/v1/persistentvolumes/\{name\}/status

[表1](#t1d4ac034b0f34bc9a38abebc870fee84)  描述该API的参数。

**表 1**  参数描述

<a name="t1d4ac034b0f34bc9a38abebc870fee84"></a>
<table><thead align="left"><tr id="r84db55a6144949aeb38e1c20651dd578"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="aae3c90f76e324d3ea1ca0e7560e43a6c"><a name="aae3c90f76e324d3ea1ca0e7560e43a6c"></a><a name="aae3c90f76e324d3ea1ca0e7560e43a6c"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.93%" id="mcps1.2.4.1.2"><p id="p65757568201724"><a name="p65757568201724"></a><a name="p65757568201724"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="57.010000000000005%" id="mcps1.2.4.1.3"><p id="p24762778201724"><a name="p24762778201724"></a><a name="p24762778201724"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r759589bf4bcb4d6aacef56fccb2f8b4a"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a0eda225d96144a95923c44de68bf69b7"><a name="a0eda225d96144a95923c44de68bf69b7"></a><a name="a0eda225d96144a95923c44de68bf69b7"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20.93%" headers="mcps1.2.4.1.2 "><p id="a7fb371139cde44658394f60358d3f3b5"><a name="a7fb371139cde44658394f60358d3f3b5"></a><a name="a7fb371139cde44658394f60358d3f3b5"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="57.010000000000005%" headers="mcps1.2.4.1.3 "><p id="a0f0c2a348f564bab9987c69a2a71bc88"><a name="a0f0c2a348f564bab9987c69a2a71bc88"></a><a name="a0f0c2a348f564bab9987c69a2a71bc88"></a>Name of the PersistentVolume.</p>
</td>
</tr>
<tr id="r7b8c1ffaace540a88791c438f6a67980"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a3e04b47b57c4407f86396eac4c142ad0"><a name="a3e04b47b57c4407f86396eac4c142ad0"></a><a name="a3e04b47b57c4407f86396eac4c142ad0"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="20.93%" headers="mcps1.2.4.1.2 "><p id="a3afa288b7f7a443fa2fc2368127a2511"><a name="a3afa288b7f7a443fa2fc2368127a2511"></a><a name="a3afa288b7f7a443fa2fc2368127a2511"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="57.010000000000005%" headers="mcps1.2.4.1.3 "><p id="a2c337b82f88b44febc14cd78ea318bad"><a name="a2c337b82f88b44febc14cd78ea318bad"></a><a name="a2c337b82f88b44febc14cd78ea318bad"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s23adef582fb84e6b9f45ba207fa67dd2"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建PersistentVolume-1.md#tfdb73431f39846d4a56ec4eb558e1617)

**请求示例：**

```
{
    "kind": "PersistentVolume",
    "apiVersion": "v1",
    "metadata": {
        "name": "pv-test",
        "selfLink": "/api/v1/persistentvolumes/pv-test",
        "uid": "e0b9c5e3-fcfc-11e7-9c3c-fa163eb8ad1a",
        "resourceVersion": "189565",
        "creationTimestamp": "2018-01-19T09:41:09Z",
        "labels": {
            "app": "test"
        }
    },
    "spec": {
        "capacity": {
            "storage": "1Gi"
        },
        "hostPath": {
            "path": "/home"
        },
        "accessModes": [
            "ReadWriteMany"
        ],
        "persistentVolumeReclaimPolicy": "Delete"
    },
    "status": {
        "phase": "Bound"
    }
}
```

## 响应消息<a name="s46e96924872f4ca48961d0390b35ebd3"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建PersistentVolume-1.md#tfdb73431f39846d4a56ec4eb558e1617).

**响应示例：**

```
{
    "kind": "PersistentVolume",
    "apiVersion": "v1",
    "metadata": {
        "name": "pv-test",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/persistentvolumes/pv-test",
        "uid": "e0b9c5e3-fcfc-11e7-9c3c-fa163eb8ad1a",
        "resourceVersion": "599899",
        "creationTimestamp": "2018-01-19T09:41:09Z",
        "labels": {
            "name": "pv-test"
        },
        "enable": true
    },
    "spec": {
        "capacity": {
            "storage": "1Gi"
        },
        "hostPath": {
            "path": "/home"
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

## 状态码<a name="sffab7031cb3846df9aa60c6651b70917"></a>

[表2](#te7c513b49efa42a396c41c76eb531fa8)描述API的状态码。

**表 2**  状态码

<a name="te7c513b49efa42a396c41c76eb531fa8"></a>
<table><thead align="left"><tr id="r9e5f1045ee6a40979ca32b130c94288d"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p60128964201724"><a name="p60128964201724"></a><a name="p60128964201724"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p38607882201724"><a name="p38607882201724"></a><a name="p38607882201724"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r7d12cef7f06e457a8415a962a663f626"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="ac8d6e53b1399420b916671b8aab03459"><a name="ac8d6e53b1399420b916671b8aab03459"></a><a name="ac8d6e53b1399420b916671b8aab03459"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="ab6fddf3ce68c450ab08d0a56b7104760"><a name="ab6fddf3ce68c450ab08d0a56b7104760"></a><a name="ab6fddf3ce68c450ab08d0a56b7104760"></a>This operation succeeds, and a PersistentVolume resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

