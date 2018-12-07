# 删除DaemonSet<a name="cce_02_0134"></a>

## 功能介绍<a name="section27094845"></a>

This API is used to delete a DaemonSet resource object.

## URI<a name="section42527017"></a>

DELETE /apis/apps/v1/namespaces/\{namespace\}/daemonsets/\{name\} \(Supports only1.9\)

DELETE /apis/extensions/v1beta1/namespaces/\{namespace\}/daemonsets/\{name\} \(Compatible\)

[表1](#table137278403473)描述该API的参数。

**表 1**  参数解释

<a name="table137278403473"></a>
<table><thead align="left"><tr id="row6995273"><th class="cellrowborder" valign="top" width="21.43%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.37%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.199999999999996%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row4392225"><td class="cellrowborder" valign="top" width="21.43%" headers="mcps1.2.4.1.1 "><p id="p20225910"><a name="p20225910"></a><a name="p20225910"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p27685991"><a name="p27685991"></a><a name="p27685991"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.199999999999996%" headers="mcps1.2.4.1.3 "><p id="p27972830"><a name="p27972830"></a><a name="p27972830"></a>name of the DaemonSet</p>
</td>
</tr>
<tr id="row50428878"><td class="cellrowborder" valign="top" width="21.43%" headers="mcps1.2.4.1.1 "><p id="p58207302"><a name="p58207302"></a><a name="p58207302"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p17170998"><a name="p17170998"></a><a name="p17170998"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.199999999999996%" headers="mcps1.2.4.1.3 "><p id="p48673607"><a name="p48673607"></a><a name="p48673607"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row35409283"><td class="cellrowborder" valign="top" width="21.43%" headers="mcps1.2.4.1.1 "><p id="p49579688"><a name="p49579688"></a><a name="p49579688"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p56531777"><a name="p56531777"></a><a name="p56531777"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.199999999999996%" headers="mcps1.2.4.1.3 "><p id="p15671223"><a name="p15671223"></a><a name="p15671223"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row6823280"><td class="cellrowborder" valign="top" width="21.43%" headers="mcps1.2.4.1.1 "><p id="p15814779"><a name="p15814779"></a><a name="p15814779"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p5928727"><a name="p5928727"></a><a name="p5928727"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.199999999999996%" headers="mcps1.2.4.1.3 "><p id="p10464875"><a name="p10464875"></a><a name="p10464875"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="row27075018"><td class="cellrowborder" valign="top" width="21.43%" headers="mcps1.2.4.1.1 "><p id="p45592870"><a name="p45592870"></a><a name="p45592870"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p2035023"><a name="p2035023"></a><a name="p2035023"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.199999999999996%" headers="mcps1.2.4.1.3 "><p id="p30619180"><a name="p30619180"></a><a name="p30619180"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="row7137170"><td class="cellrowborder" valign="top" width="21.43%" headers="mcps1.2.4.1.1 "><p id="p41239897"><a name="p41239897"></a><a name="p41239897"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p52097352"><a name="p52097352"></a><a name="p52097352"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.199999999999996%" headers="mcps1.2.4.1.3 "><p id="p7671193934118"><a name="p7671193934118"></a><a name="p7671193934118"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: 'Orphan' - orphan the dependents; 'Background' - allow the garbage collector to delete the dependents in the background; 'Foreground' - a cascading policy that deletes all dependents in the foreground.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section47198836"></a>

**请求参数：**

请求参数如[表2](#table191461259175715)所示。

**表 2**  请求参数

<a name="table191461259175715"></a>
<table><thead align="left"><tr id="row55138935"><th class="cellrowborder" valign="top" width="18.18181818181818%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0083857388_zh-cn_topic_0079615000_p19784972"><a name="zh-cn_topic_0083857388_zh-cn_topic_0079615000_p19784972"></a><a name="zh-cn_topic_0083857388_zh-cn_topic_0079615000_p19784972"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.151515151515152%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0083857388_p62904453205444"><a name="zh-cn_topic_0083857388_p62904453205444"></a><a name="zh-cn_topic_0083857388_p62904453205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0083857388_p62095922205444"><a name="zh-cn_topic_0083857388_p62095922205444"></a><a name="zh-cn_topic_0083857388_p62095922205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="46.464646464646464%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0083857388_p63713767205444"><a name="zh-cn_topic_0083857388_p63713767205444"></a><a name="zh-cn_topic_0083857388_p63713767205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row57174526"><td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.1 "><p id="p624995"><a name="p624995"></a><a name="p624995"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.2.5.1.2 "><p id="p50624612"><a name="p50624612"></a><a name="p50624612"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p6952939"><a name="p6952939"></a><a name="p6952939"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.5.1.4 "><p id="p26317149"><a name="p26317149"></a><a name="p26317149"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row35527755"><td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.1 "><p id="p59175883"><a name="p59175883"></a><a name="p59175883"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.2.5.1.2 "><p id="p28517228"><a name="p28517228"></a><a name="p28517228"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p28194133"><a name="p28194133"></a><a name="p28194133"></a>integer</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.5.1.4 "><p id="p2023471"><a name="p2023471"></a><a name="p2023471"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="row18211246"><td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.1 "><p id="p65824820"><a name="p65824820"></a><a name="p65824820"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.2.5.1.2 "><p id="p30210174"><a name="p30210174"></a><a name="p30210174"></a>Ye</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p31105012"><a name="p31105012"></a><a name="p31105012"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.5.1.4 "><p id="p36478080"><a name="p36478080"></a><a name="p36478080"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="row59867264"><td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.1 "><p id="p17410245"><a name="p17410245"></a><a name="p17410245"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.2.5.1.2 "><p id="p943763"><a name="p943763"></a><a name="p943763"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p9335953"><a name="p9335953"></a><a name="p9335953"></a>boolean</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.5.1.4 "><p id="p18014695"><a name="p18014695"></a><a name="p18014695"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="row27914531"><td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.1 "><p id="p46484529"><a name="p46484529"></a><a name="p46484529"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.2.5.1.2 "><p id="p7150508"><a name="p7150508"></a><a name="p7150508"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p42320251"><a name="p42320251"></a><a name="p42320251"></a><a href="#cce_02_0134__table27213123546">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.5.1.4 "><p id="p48494655"><a name="p48494655"></a><a name="p48494655"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="row33798711"><td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.1 "><p id="p53341043"><a name="p53341043"></a><a name="p53341043"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.2.5.1.2 "><p id="p25657252"><a name="p25657252"></a><a name="p25657252"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p64971570"><a name="p64971570"></a><a name="p64971570"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="46.464646464646464%" headers="mcps1.2.5.1.4 "><p id="p36716510426"><a name="p36716510426"></a><a name="p36716510426"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: 'Orphan' - orphan the dependents; 'Background' - allow the garbage collector to delete the dependents in the background; 'Foreground' - a cascading policy that deletes all dependents in the foreground.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  preconditions字段数据结构说明

<a name="table27213123546"></a>
<table><thead align="left"><tr id="row38609115"><th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.5.1.1"><p id="p177362043416"><a name="p177362043416"></a><a name="p177362043416"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.308469153084694%" id="mcps1.2.5.1.2"><p id="p2741420163416"><a name="p2741420163416"></a><a name="p2741420163416"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.3"><p id="p197662010344"><a name="p197662010344"></a><a name="p197662010344"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="46.93530646935306%" id="mcps1.2.5.1.4"><p id="p1578162011343"><a name="p1578162011343"></a><a name="p1578162011343"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row65528017"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.1 "><p id="p6169189"><a name="p6169189"></a><a name="p6169189"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084694%" headers="mcps1.2.5.1.2 "><p id="p29942301"><a name="p29942301"></a><a name="p29942301"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p9407330"><a name="p9407330"></a><a name="p9407330"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="46.93530646935306%" headers="mcps1.2.5.1.4 "><p id="p23796251"><a name="p23796251"></a><a name="p23796251"></a>Specifies the target UID.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

-   只删除DaemonSet（对应Pod不删除）

    ```
    {
        "Kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Orphan"
    }
    ```

-   前台级联删除（按照Pod-\>DaemonSet的顺序进行删除）

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Foreground"
    }
    ```

-   后台级联删除（按照DaemonSet-\>Pod的顺序进行删除）

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Background"
    }
    ```


## 响应消息<a name="section22136343"></a>

**响应参数：**

响应参数的详细描述请参见[Table 5-9](删除Secret.md#zh-cn_topic_0079615047_table30941925)。

**响应示例：**

```
{
    "kind": "DaemonSet",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "name": "ds-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/daemonsets/ds-12130306",
        "uid": "dc72a82b-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "419055",
        "generation": 2,
        "creationTimestamp": "2017-12-13T03:15:24Z",
        "deletionTimestamp": "2017-12-13T03:15:55Z",
        "deletionGracePeriodSeconds": 0,
        "labels": {
            "name": "daemonset-test"
        },
        "finalizers": [
            "orphan"
        ],
        "enable": true
    },
    "spec": {
        "selector": {
            "matchLabels": {
                "name": "daemonset-test"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "name": "daemonset-test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "dscon-12130306",
                        "image": "172.16.5.235:20202/test/redis:latest",
                        "resources": {},
                        "terminationMessagePath": "/dev/termination-log",
                        "terminationMessagePolicy": "File",
                        "imagePullPolicy": "IfNotPresent"
                    }
                ],
                "restartPolicy": "Always",
                "terminationGracePeriodSeconds": 30,
                "dnsPolicy": "ClusterFirst",
                "securityContext": {},
                "schedulerName": "default-scheduler"
            }
        },
        "updateStrategy": {
            "type": "OnDelete"
        },
        "templateGeneration": 1,
        "revisionHistoryLimit": 10
    },
    "status": {
        "currentNumberScheduled": 1,
        "numberMisscheduled": 0,
        "desiredNumberScheduled": 1,
        "numberReady": 1,
        "observedGeneration": 1,
        "updatedNumberScheduled": 1,
        "numberAvailable": 1
    }
}
```

## 状态码<a name="section65009363"></a>

[表4](#d0e32165)描述API的状态码。

**表 4**  状态码

<a name="d0e32165"></a>
<table><thead align="left"><tr id="row51284826"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p60430236"><a name="p60430236"></a><a name="p60430236"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p63010934"><a name="p63010934"></a><a name="p63010934"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row3612049"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p24140565"><a name="p24140565"></a><a name="p24140565"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9228712"><a name="p9228712"></a><a name="p9228712"></a>Delete a DeamonSet resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

