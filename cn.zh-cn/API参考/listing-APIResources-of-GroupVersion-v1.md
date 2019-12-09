# listing APIResources of GroupVersion v1<a name="cce_02_0206"></a>

## 功能介绍<a name="section38722623"></a>

This API is used to list APIResources of GroupVersion "v1".

## URI<a name="section12959287"></a>

GET /api/v1

## 请求消息<a name="section49524720"></a>

N/A.

## 响应消息<a name="section43069299"></a>

**响应参数：**

[表1](#d0e50339)  describes the response parameters.

**表 1**  参数解释

<a name="d0e50339"></a>
<table><thead align="left"><tr id="row53024952"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p53840"><a name="p53840"></a><a name="p53840"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p4361056"><a name="p4361056"></a><a name="p4361056"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p17701265"><a name="p17701265"></a><a name="p17701265"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row24516362"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p39668340"><a name="p39668340"></a><a name="p39668340"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p59018999"><a name="p59018999"></a><a name="p59018999"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p15809594"><a name="p15809594"></a><a name="p15809594"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row8068619"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p49578385"><a name="p49578385"></a><a name="p49578385"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p56426285"><a name="p56426285"></a><a name="p56426285"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p7126340"><a name="p7126340"></a><a name="p7126340"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row64137066"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p27719880"><a name="p27719880"></a><a name="p27719880"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p30717782"><a name="p30717782"></a><a name="p30717782"></a><a href="#d0e50389">resources</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p46011424"><a name="p46011424"></a><a name="p46011424"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e50389"></a>
<table><thead align="left"><tr id="row2200900"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p44055172"><a name="p44055172"></a><a name="p44055172"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p11699152"><a name="p11699152"></a><a name="p11699152"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p8107281"><a name="p8107281"></a><a name="p8107281"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row52710063"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p41656721"><a name="p41656721"></a><a name="p41656721"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p18751264"><a name="p18751264"></a><a name="p18751264"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p42457411"><a name="p42457411"></a><a name="p42457411"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row46572384"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p14266749"><a name="p14266749"></a><a name="p14266749"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p14756002"><a name="p14756002"></a><a name="p14756002"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p54385528"><a name="p54385528"></a><a name="p54385528"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row19707709"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p52820574"><a name="p52820574"></a><a name="p52820574"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p50608133"><a name="p50608133"></a><a name="p50608133"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p5618071"><a name="p5618071"></a><a name="p5618071"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row50562645"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p1933557"><a name="p1933557"></a><a name="p1933557"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p22400438"><a name="p22400438"></a><a name="p22400438"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p2496191"><a name="p2496191"></a><a name="p2496191"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row22465727"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p7784584"><a name="p7784584"></a><a name="p7784584"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p26571566"><a name="p26571566"></a><a name="p26571566"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p4813208"><a name="p4813208"></a><a name="p4813208"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row43318874"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p19167910"><a name="p19167910"></a><a name="p19167910"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p9096874"><a name="p9096874"></a><a name="p9096874"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p65758223"><a name="p65758223"></a><a name="p65758223"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row54953101"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p22016230"><a name="p22016230"></a><a name="p22016230"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p38484211"><a name="p38484211"></a><a name="p38484211"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p30213405"><a name="p30213405"></a><a name="p30213405"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "groupVersion": "v1",
    "resources": [
        {
            "name": "bindings",
            "singularName": "",
            "namespaced": true,
            "kind": "Binding",
            "verbs": [
                "create"
            ]
        },
        {
            "name": "componentstatuses",
            "singularName": "",
            "namespaced": false,
            "kind": "ComponentStatus",
            "verbs": [
                "get",
                "list"
            ],
            "shortNames": [
                "cs"
            ]
        },
        {
            "name": "configmaps",
            "singularName": "",
            "namespaced": true,
            "kind": "ConfigMap",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "cm"
            ]
        },
        {
            "name": "endpoints",
            "singularName": "",
            "namespaced": true,
            "kind": "Endpoints",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "ep"
            ]
        },
        {
            "name": "events",
            "singularName": "",
            "namespaced": true,
            "kind": "Event",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "ev"
            ]
        },
        {
            "name": "limitranges",
            "singularName": "",
            "namespaced": true,
            "kind": "LimitRange",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "limits"
            ]
        },
        {
            "name": "namespaces",
            "singularName": "",
            "namespaced": false,
            "kind": "Namespace",
            "verbs": [
                "create",
                "delete",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "ns"
            ]
        },
        {
            "name": "namespaces/finalize",
            "singularName": "",
            "namespaced": false,
            "kind": "Namespace",
            "verbs": [
                "update"
            ]
        },
        {
            "name": "namespaces/status",
            "singularName": "",
            "namespaced": false,
            "kind": "Namespace",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "nodes",
            "singularName": "",
            "namespaced": false,
            "kind": "Node",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "proxy",
                "update",
                "watch"
            ],
            "shortNames": [
                "no"
            ]
        },
        {
            "name": "nodes/proxy",
            "singularName": "",
            "namespaced": false,
            "kind": "Node",
            "verbs": []
        },
        {
            "name": "nodes/status",
            "singularName": "",
            "namespaced": false,
            "kind": "Node",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "persistentvolumeclaims",
            "singularName": "",
            "namespaced": true,
            "kind": "PersistentVolumeClaim",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "pvc"
            ]
        },
        {
            "name": "persistentvolumeclaims/status",
            "singularName": "",
            "namespaced": true,
            "kind": "PersistentVolumeClaim",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "persistentvolumes",
            "singularName": "",
            "namespaced": false,
            "kind": "PersistentVolume",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "pv"
            ]
        },
        {
            "name": "persistentvolumes/status",
            "singularName": "",
            "namespaced": false,
            "kind": "PersistentVolume",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "pods",
            "singularName": "",
            "namespaced": true,
            "kind": "Pod",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "proxy",
                "update",
                "watch"
            ],
            "shortNames": [
                "po"
            ],
            "categories": [
                "all"
            ]
        },
        {
            "name": "pods/attach",
            "singularName": "",
            "namespaced": true,
            "kind": "Pod",
            "verbs": []
        },
        {
            "name": "pods/binding",
            "singularName": "",
            "namespaced": true,
            "kind": "Binding",
            "verbs": [
                "create"
            ]
        },
        {
            "name": "pods/eviction",
            "singularName": "",
            "namespaced": true,
            "kind": "Eviction",
            "verbs": [
                "create"
            ]
        },
        {
            "name": "pods/exec",
            "singularName": "",
            "namespaced": true,
            "kind": "Pod",
            "verbs": []
        },
        {
            "name": "pods/log",
            "singularName": "",
            "namespaced": true,
            "kind": "Pod",
            "verbs": [
                "get"
            ]
        },
        {
            "name": "pods/portforward",
            "singularName": "",
            "namespaced": true,
            "kind": "Pod",
            "verbs": []
        },
        {
            "name": "pods/proxy",
            "singularName": "",
            "namespaced": true,
            "kind": "Pod",
            "verbs": []
        },
        {
            "name": "pods/status",
            "singularName": "",
            "namespaced": true,
            "kind": "Pod",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "podtemplates",
            "singularName": "",
            "namespaced": true,
            "kind": "PodTemplate",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ]
        },
        {
            "name": "replicationcontrollers",
            "singularName": "",
            "namespaced": true,
            "kind": "ReplicationController",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "rc"
            ],
            "categories": [
                "all"
            ]
        },
        {
            "name": "replicationcontrollers/scale",
            "singularName": "",
            "namespaced": true,
            "kind": "Scale",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "replicationcontrollers/status",
            "singularName": "",
            "namespaced": true,
            "kind": "ReplicationController",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "resourcequotas",
            "singularName": "",
            "namespaced": true,
            "kind": "ResourceQuota",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "quota"
            ]
        },
        {
            "name": "resourcequotas/status",
            "singularName": "",
            "namespaced": true,
            "kind": "ResourceQuota",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "secrets",
            "singularName": "",
            "namespaced": true,
            "kind": "Secret",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ]
        },
        {
            "name": "serviceaccounts",
            "singularName": "",
            "namespaced": true,
            "kind": "ServiceAccount",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "sa"
            ]
        },
        {
            "name": "services",
            "singularName": "",
            "namespaced": true,
            "kind": "Service",
            "verbs": [
                "create",
                "delete",
                "get",
                "list",
                "patch",
                "proxy",
                "update",
                "watch"
            ]
        },
        {
            "name": "services/proxy",
            "singularName": "",
            "namespaced": true,
            "kind": "Service",
            "verbs": []
        },
        {
            "name": "services/status",
            "singularName": "",
            "namespaced": true,
            "kind": "Service",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        }
    ]
}
```

## 状态码<a name="section52079378"></a>

[表3](#d0e50490)描述API的状态码。

**表 3**  状态码

<a name="d0e50490"></a>
<table><thead align="left"><tr id="row23459350"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p21159234"><a name="p21159234"></a><a name="p21159234"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p36176361"><a name="p36176361"></a><a name="p36176361"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row44604149"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p56166350"><a name="p56166350"></a><a name="p56166350"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p53180507"><a name="p53180507"></a><a name="p53180507"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

