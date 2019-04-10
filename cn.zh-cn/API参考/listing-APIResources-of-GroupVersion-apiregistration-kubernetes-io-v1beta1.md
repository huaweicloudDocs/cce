# listing APIResources of GroupVersion apiregistration.kubernetes.io/v1beta1<a name="cce_02_0188"></a>

## 功能介绍<a name="section42248057"></a>

This API is used to list APIGroups.

## URI<a name="section44688198"></a>

GET /apis/apiregistration.kubernetes.io/v1beta1

## 请求消息<a name="section66649469"></a>

N/A.

## 响应消息<a name="section62974309"></a>

**响应参数：**

[表1](#d0e46199)  describes the response parameters.

**表 1**  参数解释

<a name="d0e46199"></a>
<table><thead align="left"><tr id="row12332252"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p59388390"><a name="p59388390"></a><a name="p59388390"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p45730313"><a name="p45730313"></a><a name="p45730313"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p13167852"><a name="p13167852"></a><a name="p13167852"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row59963063"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p25169939"><a name="p25169939"></a><a name="p25169939"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p25499175"><a name="p25499175"></a><a name="p25499175"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p52167324"><a name="p52167324"></a><a name="p52167324"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row66852738"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p46362731"><a name="p46362731"></a><a name="p46362731"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p64393736"><a name="p64393736"></a><a name="p64393736"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p48510146"><a name="p48510146"></a><a name="p48510146"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row33938133"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p64634244"><a name="p64634244"></a><a name="p64634244"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p882436"><a name="p882436"></a><a name="p882436"></a><a href="#d0e46249">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p39316582"><a name="p39316582"></a><a name="p39316582"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e46249"></a>
<table><thead align="left"><tr id="row20838481"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p10195411"><a name="p10195411"></a><a name="p10195411"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p20521986"><a name="p20521986"></a><a name="p20521986"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p51668165"><a name="p51668165"></a><a name="p51668165"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row24371845"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p27962409"><a name="p27962409"></a><a name="p27962409"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p50362650"><a name="p50362650"></a><a name="p50362650"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p52842815"><a name="p52842815"></a><a name="p52842815"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row5823288"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p1924359"><a name="p1924359"></a><a name="p1924359"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p21655423"><a name="p21655423"></a><a name="p21655423"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p9258823"><a name="p9258823"></a><a name="p9258823"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row16220544"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p38795716"><a name="p38795716"></a><a name="p38795716"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p55445292"><a name="p55445292"></a><a name="p55445292"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p61883681"><a name="p61883681"></a><a name="p61883681"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row20082219"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p16047070"><a name="p16047070"></a><a name="p16047070"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p24744273"><a name="p24744273"></a><a name="p24744273"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p58129068"><a name="p58129068"></a><a name="p58129068"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row53399568"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p30397788"><a name="p30397788"></a><a name="p30397788"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p46301731"><a name="p46301731"></a><a name="p46301731"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p59452751"><a name="p59452751"></a><a name="p59452751"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row65312719"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p55838861"><a name="p55838861"></a><a name="p55838861"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p26653859"><a name="p26653859"></a><a name="p26653859"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p11478970"><a name="p11478970"></a><a name="p11478970"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row36201869"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p46670280"><a name="p46670280"></a><a name="p46670280"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p22196311"><a name="p22196311"></a><a name="p22196311"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p53070755"><a name="p53070755"></a><a name="p53070755"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "apiregistration.kubernetes.io/v1beta1",
    "resources": [
        {
            "name": "apiservices",
            "singularName": "",
            "namespaced": false,
            "kind": "APIService",
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
            "name": "apiservices/status",
            "singularName": "",
            "namespaced": false,
            "kind": "APIService",
            "verbs": [
                "update"
            ]
        }
    ]
}
```

## 状态码<a name="section29897872"></a>

[表3](#d0e46350)描述API的状态码。

**表 3**  状态码

<a name="d0e46350"></a>
<table><thead align="left"><tr id="row22660525"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p23563273"><a name="p23563273"></a><a name="p23563273"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p29576928"><a name="p29576928"></a><a name="p29576928"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row46920988"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p42503717"><a name="p42503717"></a><a name="p42503717"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p20249058"><a name="p20249058"></a><a name="p20249058"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

