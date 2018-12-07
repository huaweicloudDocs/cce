# listing APIResources of GroupVersion apps/v1beta1<a name="cce_02_0190"></a>

## 功能介绍<a name="section1517466"></a>

This API is used to list APIResources of Group Version "apps/v1beta1".

## URI<a name="section13657195"></a>

GET /apis/apps/v1beta1

## 请求消息<a name="section55805891"></a>

N/A.

## 响应消息<a name="section32490971"></a>

**响应参数：**

[表1](#d0e46659)  describes the response parameters.

**表 1**  参数解释

<a name="d0e46659"></a>
<table><thead align="left"><tr id="row36767732"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p25396348"><a name="p25396348"></a><a name="p25396348"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p43838292"><a name="p43838292"></a><a name="p43838292"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p61240740"><a name="p61240740"></a><a name="p61240740"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row61552917"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p19730382"><a name="p19730382"></a><a name="p19730382"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p54657144"><a name="p54657144"></a><a name="p54657144"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p65152571"><a name="p65152571"></a><a name="p65152571"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row49502229"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p50257583"><a name="p50257583"></a><a name="p50257583"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p44332405"><a name="p44332405"></a><a name="p44332405"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p34155089"><a name="p34155089"></a><a name="p34155089"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row38960345"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1671406"><a name="p1671406"></a><a name="p1671406"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1166220"><a name="p1166220"></a><a name="p1166220"></a><a href="#cce_02_0190__d0e46709">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p44868138"><a name="p44868138"></a><a name="p44868138"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e46709"></a>
<table><thead align="left"><tr id="row58709452"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p57845160"><a name="p57845160"></a><a name="p57845160"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p54946344"><a name="p54946344"></a><a name="p54946344"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p21468852"><a name="p21468852"></a><a name="p21468852"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row61255477"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p62746643"><a name="p62746643"></a><a name="p62746643"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p49313333"><a name="p49313333"></a><a name="p49313333"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p34957060"><a name="p34957060"></a><a name="p34957060"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row46178087"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p49437604"><a name="p49437604"></a><a name="p49437604"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p45022977"><a name="p45022977"></a><a name="p45022977"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p22982502"><a name="p22982502"></a><a name="p22982502"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row5515932"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p44137313"><a name="p44137313"></a><a name="p44137313"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p18352578"><a name="p18352578"></a><a name="p18352578"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p10163881"><a name="p10163881"></a><a name="p10163881"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row24366065"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p27494233"><a name="p27494233"></a><a name="p27494233"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p12440377"><a name="p12440377"></a><a name="p12440377"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p1037626"><a name="p1037626"></a><a name="p1037626"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row9338638"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p18232227"><a name="p18232227"></a><a name="p18232227"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p415404"><a name="p415404"></a><a name="p415404"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p33647762"><a name="p33647762"></a><a name="p33647762"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row34394403"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p34483230"><a name="p34483230"></a><a name="p34483230"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p41678250"><a name="p41678250"></a><a name="p41678250"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p20495086"><a name="p20495086"></a><a name="p20495086"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row50238053"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p42750513"><a name="p42750513"></a><a name="p42750513"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p40239562"><a name="p40239562"></a><a name="p40239562"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p38179095"><a name="p38179095"></a><a name="p38179095"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "apps/v1beta1",
    "resources": [
        {
            "name": "controllerrevisions",
            "singularName": "",
            "namespaced": true,
            "kind": "ControllerRevision",
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
            "name": "statefulsets",
            "singularName": "",
            "namespaced": true,
            "kind": "StatefulSet",
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
                "sts"
            ],
            "categories": [
                "all"
            ]
        },
        {
            "name": "statefulsets/status",
            "singularName": "",
            "namespaced": true,
            "kind": "StatefulSet",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        }
    ]
}
```

## 状态码<a name="section23983284"></a>

[表3](#d0e46810)描述API的状态码。

**表 3**  状态码

<a name="d0e46810"></a>
<table><thead align="left"><tr id="row62209304"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p5788893"><a name="p5788893"></a><a name="p5788893"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p66247211"><a name="p66247211"></a><a name="p66247211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row64423849"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p50949247"><a name="p50949247"></a><a name="p50949247"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p33248342"><a name="p33248342"></a><a name="p33248342"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

