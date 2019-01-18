# 替换指定的PersistentVolumeClaim的状态<a name="cce_02_0071"></a>

## 功能介绍<a name="s9ee4fed32e474a519ae93921b3f4771b"></a>

该API用于替换指定的Namespace下指定的PersistentVolumeClaim对象的状态。

其中以下字段支持更新：

-   status.phase

## URI<a name="scb1cc9ec006c4fa6820019f6c4678c13"></a>

PUT /api/v1/namespaces/\{namespace\}/persistentvolumeclaims/\{name\}/status

[表1](#tfbc405768d37450cafff4e7c66273747)  描述该API的参数。

**表 1**  参数描述

<a name="tfbc405768d37450cafff4e7c66273747"></a>
<table><thead align="left"><tr id="rfd08a1af76984296bfe499aa36de2b8a"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="a6b704b428f134421bfc6c9d3d2039103"><a name="a6b704b428f134421bfc6c9d3d2039103"></a><a name="a6b704b428f134421bfc6c9d3d2039103"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p4121007520174"><a name="p4121007520174"></a><a name="p4121007520174"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.77%" id="mcps1.2.4.1.3"><p id="p4968177220174"><a name="p4968177220174"></a><a name="p4968177220174"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r031b4e2567924db18b0c467c4e5bc5c5"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="ad00c229faeff41b5bad6d6468a231e9a"><a name="ad00c229faeff41b5bad6d6468a231e9a"></a><a name="ad00c229faeff41b5bad6d6468a231e9a"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="ab603630cef6a47a8b04e367abeb77826"><a name="ab603630cef6a47a8b04e367abeb77826"></a><a name="ab603630cef6a47a8b04e367abeb77826"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.77%" headers="mcps1.2.4.1.3 "><p id="a1fab66391dd44bd8834369d21d9632bd"><a name="a1fab66391dd44bd8834369d21d9632bd"></a><a name="a1fab66391dd44bd8834369d21d9632bd"></a>Name of the PersistentVolumeClaim.</p>
</td>
</tr>
<tr id="r73c6bc344e1f4b4a9030b0fd3efa78d5"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a8c845645bba64c46a8533e8b797c2f80"><a name="a8c845645bba64c46a8533e8b797c2f80"></a><a name="a8c845645bba64c46a8533e8b797c2f80"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="a6dc5c8ce74ec4a6aa67380e305c8d4a7"><a name="a6dc5c8ce74ec4a6aa67380e305c8d4a7"></a><a name="a6dc5c8ce74ec4a6aa67380e305c8d4a7"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.77%" headers="mcps1.2.4.1.3 "><p id="ab459fc470f694217b4deba4ec493247f"><a name="ab459fc470f694217b4deba4ec493247f"></a><a name="ab459fc470f694217b4deba4ec493247f"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="re0ec2fa4d41a4d539520a6c3359e7a6a"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615028_p529222351166"><a name="zh-cn_topic_0079615028_p529222351166"></a><a name="zh-cn_topic_0079615028_p529222351166"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615028_p588426771166"><a name="zh-cn_topic_0079615028_p588426771166"></a><a name="zh-cn_topic_0079615028_p588426771166"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.77%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615028_p15275601166"><a name="zh-cn_topic_0079615028_p15275601166"></a><a name="zh-cn_topic_0079615028_p15275601166"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="saeed10899040439281108ebe17030278"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建PersistentVolumeClaim-0.md#t8268aeafde034542ab17a36c7fca65c3)。

**请求示例：**

```
{
    "kind": "PersistentVolumeClaim",
    "apiVersion": "v1",
    "metadata": {
        "name": "db-mysql-0",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims/db-mysql-0",
        "uid": "9d070d77-8ce1-11e8-8ee0-fa163e49263c",
        "resourceVersion": "4202107",
        "creationTimestamp": "2018-07-21T12:28:46Z",
        "labels": {
            "failure-domain.beta.kubernetes.io/region": "cn-north-1",
            "failure-domain.beta.kubernetes.io/zone": "cn-north-1a"
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
        "volumeName": "pvc-9d070d77-8ce1-11e8-8ee0-fa163e49263c",
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

## 响应消息<a name="sd4332a274389483d94f3e350fdd2a57f"></a>

**响应参数：**

响应参数的详细描述请参见[14.2-Table2 Request parameters](创建PersistentVolumeClaim-0.md#t8268aeafde034542ab17a36c7fca65c3).

**响应示例：**

```
{
    "kind": "PersistentVolumeClaim",
    "apiVersion": "v1",
    "metadata": {
        "name": "db-mysql-0",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims/db-mysql-0",
        "uid": "9d070d77-8ce1-11e8-8ee0-fa163e49263c",
        "resourceVersion": "4202107",
        "creationTimestamp": "2018-07-21T12:28:46Z",
        "labels": {
            "failure-domain.beta.kubernetes.io/region": "cn-north-1",
            "failure-domain.beta.kubernetes.io/zone": "cn-north-1a"
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
        "volumeName": "pvc-9d070d77-8ce1-11e8-8ee0-fa163e49263c",
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

## 状态码<a name="s0e0c32adabbc42579c19150df2ea5e27"></a>

[表2](#td0de26212f1240f2a44c3c47ff400cb2)描述API的状态码。

**表 2**  状态码

<a name="td0de26212f1240f2a44c3c47ff400cb2"></a>
<table><thead align="left"><tr id="rae4138001e044dbf8d3766b54ea15cf8"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p6423894920174"><a name="p6423894920174"></a><a name="p6423894920174"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p3597239320174"><a name="p3597239320174"></a><a name="p3597239320174"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rd3489a1b889746598b4c27a4bc64ae19"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="a426ab1dd4dcf4bb48a5980b19a9d9d39"><a name="a426ab1dd4dcf4bb48a5980b19a9d9d39"></a><a name="a426ab1dd4dcf4bb48a5980b19a9d9d39"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="a8dfbdb43fdd14714800a66eabfad78e9"><a name="a8dfbdb43fdd14714800a66eabfad78e9"></a><a name="a8dfbdb43fdd14714800a66eabfad78e9"></a>This operation succeeds, and a PersistentVolumeClaim resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

