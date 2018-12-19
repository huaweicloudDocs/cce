# listing APIResources of GroupVersion rbac.authorization.k8s.io/v1beta1<a name="cce_02_0200"></a>

## 功能介绍<a name="section39062201"></a>

This API is used to list APIResources of GroupVersion "rbac.authorization.k8s.io/v1beta1".

## URI<a name="section16015489"></a>

GET /apis/rbac.authorization.k8s.io/v1beta1

## 请求消息<a name="section9921673"></a>

N/A.

## 响应消息<a name="section22186194"></a>

**响应参数：**

[表1](#d0e48959)  describes the response parameters.

**表 1**  参数解释

<a name="d0e48959"></a>
<table><thead align="left"><tr id="row62516938"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p30707180"><a name="p30707180"></a><a name="p30707180"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p4253667"><a name="p4253667"></a><a name="p4253667"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p9002775"><a name="p9002775"></a><a name="p9002775"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row58136175"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p11409748"><a name="p11409748"></a><a name="p11409748"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p51774381"><a name="p51774381"></a><a name="p51774381"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p32975331"><a name="p32975331"></a><a name="p32975331"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row28342524"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p14043079"><a name="p14043079"></a><a name="p14043079"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p63747619"><a name="p63747619"></a><a name="p63747619"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p63283511"><a name="p63283511"></a><a name="p63283511"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row32680694"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p29890578"><a name="p29890578"></a><a name="p29890578"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p5217787"><a name="p5217787"></a><a name="p5217787"></a><a href="#d0e49009">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p45670750"><a name="p45670750"></a><a name="p45670750"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e49009"></a>
<table><thead align="left"><tr id="row5675917"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p57096102"><a name="p57096102"></a><a name="p57096102"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p61381511"><a name="p61381511"></a><a name="p61381511"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p5846489"><a name="p5846489"></a><a name="p5846489"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row3803587"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p39655150"><a name="p39655150"></a><a name="p39655150"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p57950594"><a name="p57950594"></a><a name="p57950594"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p63486501"><a name="p63486501"></a><a name="p63486501"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row34507605"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p43652629"><a name="p43652629"></a><a name="p43652629"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p46202041"><a name="p46202041"></a><a name="p46202041"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p51377834"><a name="p51377834"></a><a name="p51377834"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row59747322"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p7694920"><a name="p7694920"></a><a name="p7694920"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p19308823"><a name="p19308823"></a><a name="p19308823"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p20510863"><a name="p20510863"></a><a name="p20510863"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row50380041"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p54251536"><a name="p54251536"></a><a name="p54251536"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p32298324"><a name="p32298324"></a><a name="p32298324"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p66027452"><a name="p66027452"></a><a name="p66027452"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row57376161"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p16957499"><a name="p16957499"></a><a name="p16957499"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p31380206"><a name="p31380206"></a><a name="p31380206"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p58768737"><a name="p58768737"></a><a name="p58768737"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row59156586"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p26954144"><a name="p26954144"></a><a name="p26954144"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p35802092"><a name="p35802092"></a><a name="p35802092"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p14288307"><a name="p14288307"></a><a name="p14288307"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row61485905"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p14302431"><a name="p14302431"></a><a name="p14302431"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p17646237"><a name="p17646237"></a><a name="p17646237"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p20059059"><a name="p20059059"></a><a name="p20059059"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "rbac.authorization.k8s.io/v1beta1",
    "resources": [
        {
            "name": "clusterrolebindings",
            "singularName": "",
            "namespaced": false,
            "kind": "ClusterRoleBinding",
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
            "name": "clusterroles",
            "singularName": "",
            "namespaced": false,
            "kind": "ClusterRole",
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
            "name": "rolebindings",
            "singularName": "",
            "namespaced": true,
            "kind": "RoleBinding",
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
            "name": "roles",
            "singularName": "",
            "namespaced": true,
            "kind": "Role",
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

## 状态码<a name="section65458021"></a>

[表3](#d0e49110)描述API的状态码。

**表 3**  状态码

<a name="d0e49110"></a>
<table><thead align="left"><tr id="row44958077"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p17725644"><a name="p17725644"></a><a name="p17725644"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p26491055"><a name="p26491055"></a><a name="p26491055"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row65400719"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p62966867"><a name="p62966867"></a><a name="p62966867"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p42596"><a name="p42596"></a><a name="p42596"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

