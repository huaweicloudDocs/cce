# 删除所有的PersistentVolume<a name="cce_02_0119"></a>

## Function<a name="section3340011"></a>

This API is used to delete collection of PersistentVolume.

## URI<a name="section30060106"></a>

DELETE /api/v1/persistentvolumes

[表1](#d0e30162)描述该API的参数。

**表 1**  参数解释

<a name="d0e30162"></a>
<table><thead align="left"><tr id="row47452932"><th class="cellrowborder" valign="top" width="22.45%" id="mcps1.2.4.1.1"><p id="p18482264"><a name="p18482264"></a><a name="p18482264"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.33%" id="mcps1.2.4.1.2"><p id="p20668409"><a name="p20668409"></a><a name="p20668409"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61.22%" id="mcps1.2.4.1.3"><p id="p63528398"><a name="p63528398"></a><a name="p63528398"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row45526591"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p63775286"><a name="p63775286"></a><a name="p63775286"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p65524504"><a name="p65524504"></a><a name="p65524504"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p5884623"><a name="p5884623"></a><a name="p5884623"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row52961614"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p62032351"><a name="p62032351"></a><a name="p62032351"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p58564536"><a name="p58564536"></a><a name="p58564536"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p46107010"><a name="p46107010"></a><a name="p46107010"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row12309913"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p57578895"><a name="p57578895"></a><a name="p57578895"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p33378889"><a name="p33378889"></a><a name="p33378889"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p19335471"><a name="p19335471"></a><a name="p19335471"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row39801519"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p2697603"><a name="p2697603"></a><a name="p2697603"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p17179320"><a name="p17179320"></a><a name="p17179320"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p49347702"><a name="p49347702"></a><a name="p49347702"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row41476135"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p4123780"><a name="p4123780"></a><a name="p4123780"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p65590782"><a name="p65590782"></a><a name="p65590782"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p11253116"><a name="p11253116"></a><a name="p11253116"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row34169184"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p16240544"><a name="p16240544"></a><a name="p16240544"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p40415705"><a name="p40415705"></a><a name="p40415705"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p52446642"><a name="p52446642"></a><a name="p52446642"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row2257730"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p48658414"><a name="p48658414"></a><a name="p48658414"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p49017487"><a name="p49017487"></a><a name="p49017487"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p10993549"><a name="p10993549"></a><a name="p10993549"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row31833082"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p28342862"><a name="p28342862"></a><a name="p28342862"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p14070449"><a name="p14070449"></a><a name="p14070449"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p65964622"><a name="p65964622"></a><a name="p65964622"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## Request<a name="section2105499"></a>

N/A

## Response<a name="section18949497"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建PersistentVolume-0.md#tfdb73431f39846d4a56ec4eb558e1617)。

响应示例：

```
{
    "kind": "PersistentVolumeList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/persistentvolumes",
        "resourceVersion": "5679025"
    },
    "items": [
        {
            "metadata": {
                "name": "pv-test-02",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/persistentvolumes/pv-test-02",
                "uid": "b1e175a8-920c-11e8-8cd0-fa163e082286",
                "resourceVersion": "5675029",
                "creationTimestamp": "2018-07-28T02:19:45Z",
                "labels": {
                    "failure-domain.beta.kubernetes.io/region": "cn-north-1",
                    "failure-domain.beta.kubernetes.io/zone": "cn-north-1a",
                    "name": "pv-test-02"
                },
                "annotations": {
                    "pv.kubernetes.io/bound-by-controller": "yes",
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
                "claimRef": {
                    "kind": "PersistentVolumeClaim",
                    "namespace": "default",
                    "name": "db-mysql",
                    "uid": "638e26ac-9148-11e8-8cd0-fa163e082286",
                    "apiVersion": "v1",
                    "resourceVersion": "5674792"
                },
                "persistentVolumeReclaimPolicy": "Delete"
            },
            "status": {
                "phase": "Bound"
            }
        },
        {
            "metadata": {
                "name": "pv-test-03",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/persistentvolumes/pv-test-03",
                "uid": "e4e15446-920c-11e8-81cc-fa163e49263c",
                "resourceVersion": "5675754",
                "creationTimestamp": "2018-07-28T02:21:11Z",
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
                    "storage": "3Gi"
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

## 状态码<a name="section36327748"></a>

[表2](#d0e30290)  describes the status code of this API.

**表 2**  状态码

<a name="d0e30290"></a>
<table><thead align="left"><tr id="row5612028"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p51921162"><a name="p51921162"></a><a name="p51921162"></a>Status Code</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p44864604"><a name="p44864604"></a><a name="p44864604"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row10154331"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p17194478"><a name="p17194478"></a><a name="p17194478"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p50575486"><a name="p50575486"></a><a name="p50575486"></a>Delete a DaemonSet resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

