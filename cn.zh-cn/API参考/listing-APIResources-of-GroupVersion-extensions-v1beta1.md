# listing APIResources of GroupVersion extensions/v1beta1<a name="cce_02_0189"></a>

## 功能介绍<a name="section6584238"></a>

This API is used to list APIGroups.

## URI<a name="section59258146"></a>

GET /apis/extensions/v1beta1

## 请求消息<a name="section63561270"></a>

N/A.

## 响应消息<a name="section35180523"></a>

**响应参数：**

[表1](#d0e46429)  describes the response parameters.

**表 1**  参数解释

<a name="d0e46429"></a>
<table><thead align="left"><tr id="row40015383"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p20020594"><a name="p20020594"></a><a name="p20020594"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p11055393"><a name="p11055393"></a><a name="p11055393"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p23071629"><a name="p23071629"></a><a name="p23071629"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row56862621"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p42469561"><a name="p42469561"></a><a name="p42469561"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p17482442"><a name="p17482442"></a><a name="p17482442"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p6791736"><a name="p6791736"></a><a name="p6791736"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row61125629"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p52228929"><a name="p52228929"></a><a name="p52228929"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p2684820"><a name="p2684820"></a><a name="p2684820"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p16143905"><a name="p16143905"></a><a name="p16143905"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row11077420"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p24855808"><a name="p24855808"></a><a name="p24855808"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p54561"><a name="p54561"></a><a name="p54561"></a><a href="#d0e46479">resources</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p39775015"><a name="p39775015"></a><a name="p39775015"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e46479"></a>
<table><thead align="left"><tr id="row1004086"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p14222151"><a name="p14222151"></a><a name="p14222151"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p11143584"><a name="p11143584"></a><a name="p11143584"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p30215146"><a name="p30215146"></a><a name="p30215146"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row31507789"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p1994096"><a name="p1994096"></a><a name="p1994096"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p27304059"><a name="p27304059"></a><a name="p27304059"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p64145175"><a name="p64145175"></a><a name="p64145175"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row40435667"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p54063562"><a name="p54063562"></a><a name="p54063562"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p17072422"><a name="p17072422"></a><a name="p17072422"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p40688975"><a name="p40688975"></a><a name="p40688975"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row30656460"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p145298"><a name="p145298"></a><a name="p145298"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p11769177"><a name="p11769177"></a><a name="p11769177"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p13779272"><a name="p13779272"></a><a name="p13779272"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row56904591"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p45869134"><a name="p45869134"></a><a name="p45869134"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p24412362"><a name="p24412362"></a><a name="p24412362"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p31244266"><a name="p31244266"></a><a name="p31244266"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row12762939"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p27165133"><a name="p27165133"></a><a name="p27165133"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p52892151"><a name="p52892151"></a><a name="p52892151"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p56405858"><a name="p56405858"></a><a name="p56405858"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row37890679"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p49246182"><a name="p49246182"></a><a name="p49246182"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p29517801"><a name="p29517801"></a><a name="p29517801"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p42131689"><a name="p42131689"></a><a name="p42131689"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row43640883"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p45250616"><a name="p45250616"></a><a name="p45250616"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p41421294"><a name="p41421294"></a><a name="p41421294"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p66790524"><a name="p66790524"></a><a name="p66790524"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "groupVersion": "extensions/v1beta1",
    "resources": [
        {
            "name": "daemonsets",
            "singularName": "",
            "namespaced": true,
            "kind": "DaemonSet",
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
                "ds"
            ]
        },
        {
            "name": "daemonsets/status",
            "singularName": "",
            "namespaced": true,
            "kind": "DaemonSet",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "deployments",
            "singularName": "",
            "namespaced": true,
            "kind": "Deployment",
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
                "deploy"
            ],
            "categories": [
                "all"
            ]
        },
        {
            "name": "deployments/rollback",
            "singularName": "",
            "namespaced": true,
            "kind": "DeploymentRollback",
            "verbs": [
                "create"
            ]
        },
        {
            "name": "deployments/scale",
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
            "name": "deployments/status",
            "singularName": "",
            "namespaced": true,
            "kind": "Deployment",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "ingresses",
            "singularName": "",
            "namespaced": true,
            "kind": "Ingress",
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
                "ing"
            ]
        },
        {
            "name": "ingresses/status",
            "singularName": "",
            "namespaced": true,
            "kind": "Ingress",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "networkpolicies",
            "singularName": "",
            "namespaced": true,
            "kind": "NetworkPolicy",
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
            "name": "podsecuritypolicies",
            "singularName": "",
            "namespaced": false,
            "kind": "PodSecurityPolicy",
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
                "psp"
            ]
        },
        {
            "name": "replicasets",
            "singularName": "",
            "namespaced": true,
            "kind": "ReplicaSet",
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
                "rs"
            ],
            "categories": [
                "all"
            ]
        },
        {
            "name": "replicasets/scale",
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
            "name": "replicasets/status",
            "singularName": "",
            "namespaced": true,
            "kind": "ReplicaSet",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        },
        {
            "name": "replicationcontrollers",
            "singularName": "",
            "namespaced": true,
            "kind": "ReplicationControllerDummy",
            "verbs": []
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
            "name": "thirdpartyresources",
            "singularName": "",
            "namespaced": false,
            "kind": "ThirdPartyResource",
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
        }
    ]
}
```

## 状态码<a name="section48189259"></a>

[表3](#d0e46580)描述API的状态码。

**表 3**  状态码

<a name="d0e46580"></a>
<table><thead align="left"><tr id="row39403018"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p37527853"><a name="p37527853"></a><a name="p37527853"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p19857290"><a name="p19857290"></a><a name="p19857290"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row64936647"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p25377036"><a name="p25377036"></a><a name="p25377036"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p42274050"><a name="p42274050"></a><a name="p42274050"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

