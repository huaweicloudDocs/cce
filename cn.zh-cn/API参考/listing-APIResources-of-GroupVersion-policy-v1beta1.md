# listing APIResources of GroupVersion policy/v1beta1<a name="cce_02_0199"></a>

## 功能介绍<a name="section31127152"></a>

This API is used to list APIResources of GroupVersion "policy/v1beta1".

## URI<a name="section11708914"></a>

GET /apis/policy/v1beta1

## 请求消息<a name="section38271369"></a>

N/A.

## 响应消息<a name="section8898005"></a>

**响应参数：**

[表1](#d0e48729)  describes the response parameters.

**表 1**  参数解释

<a name="d0e48729"></a>
<table><thead align="left"><tr id="row51254422"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p57967506"><a name="p57967506"></a><a name="p57967506"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p64856370"><a name="p64856370"></a><a name="p64856370"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p18874590"><a name="p18874590"></a><a name="p18874590"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row52446847"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p20336253"><a name="p20336253"></a><a name="p20336253"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p36623807"><a name="p36623807"></a><a name="p36623807"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p13738414"><a name="p13738414"></a><a name="p13738414"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row56536865"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p16083390"><a name="p16083390"></a><a name="p16083390"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p27686203"><a name="p27686203"></a><a name="p27686203"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p27989952"><a name="p27989952"></a><a name="p27989952"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row50582982"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p3580843"><a name="p3580843"></a><a name="p3580843"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p21612844"><a name="p21612844"></a><a name="p21612844"></a><a href="#d0e48779">resources</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p52289739"><a name="p52289739"></a><a name="p52289739"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e48779"></a>
<table><thead align="left"><tr id="row55892189"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p30973495"><a name="p30973495"></a><a name="p30973495"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p25825194"><a name="p25825194"></a><a name="p25825194"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p11465949"><a name="p11465949"></a><a name="p11465949"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row56326648"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p66164644"><a name="p66164644"></a><a name="p66164644"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p57735944"><a name="p57735944"></a><a name="p57735944"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p46099917"><a name="p46099917"></a><a name="p46099917"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row12246075"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p52408052"><a name="p52408052"></a><a name="p52408052"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p17193825"><a name="p17193825"></a><a name="p17193825"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p50522603"><a name="p50522603"></a><a name="p50522603"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row52050246"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p55320389"><a name="p55320389"></a><a name="p55320389"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p51766549"><a name="p51766549"></a><a name="p51766549"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p32340958"><a name="p32340958"></a><a name="p32340958"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row22633167"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p21347199"><a name="p21347199"></a><a name="p21347199"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p51401531"><a name="p51401531"></a><a name="p51401531"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p2774508"><a name="p2774508"></a><a name="p2774508"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row24970580"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p9351119"><a name="p9351119"></a><a name="p9351119"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p19243187"><a name="p19243187"></a><a name="p19243187"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p15194278"><a name="p15194278"></a><a name="p15194278"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row2530782"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p3666798"><a name="p3666798"></a><a name="p3666798"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p28575202"><a name="p28575202"></a><a name="p28575202"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p32890019"><a name="p32890019"></a><a name="p32890019"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row27574715"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p18959449"><a name="p18959449"></a><a name="p18959449"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p59320440"><a name="p59320440"></a><a name="p59320440"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p40226368"><a name="p40226368"></a><a name="p40226368"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "policy/v1beta1",
    "resources": [
        {
            "name": "poddisruptionbudgets",
            "singularName": "",
            "namespaced": true,
            "kind": "PodDisruptionBudget",
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
                "pdb"
            ]
        },
        {
            "name": "poddisruptionbudgets/status",
            "singularName": "",
            "namespaced": true,
            "kind": "PodDisruptionBudget",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        }
    ]
}
```

## 状态码<a name="section12973183"></a>

[表3](#d0e48880)描述API的状态码。

**表 3**  状态码

<a name="d0e48880"></a>
<table><thead align="left"><tr id="row3439848"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p10192267"><a name="p10192267"></a><a name="p10192267"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p20267307"><a name="p20267307"></a><a name="p20267307"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row31039151"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p31143296"><a name="p31143296"></a><a name="p31143296"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p39579013"><a name="p39579013"></a><a name="p39579013"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

