# listing APIResources of GroupVersion storage.k8s.io/v1<a name="cce_02_0203"></a>

## 功能介绍<a name="section49039760"></a>

This API is used to list APIResources of GroupVersion "storage.k8s.io/v1".

## URI<a name="section38704658"></a>

GET /apis/storage.k8s.io/v1

## 请求消息<a name="section12797610"></a>

N/A.

## 响应消息<a name="section48069632"></a>

**响应参数：**

[表1](#d0e49649)  describes the response parameters.

**表 1**  参数解释

<a name="d0e49649"></a>
<table><thead align="left"><tr id="row30477758"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p52779343"><a name="p52779343"></a><a name="p52779343"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p47268392"><a name="p47268392"></a><a name="p47268392"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p3534578"><a name="p3534578"></a><a name="p3534578"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row17865429"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p37813624"><a name="p37813624"></a><a name="p37813624"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p43004675"><a name="p43004675"></a><a name="p43004675"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p60826655"><a name="p60826655"></a><a name="p60826655"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row10568987"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p50781586"><a name="p50781586"></a><a name="p50781586"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p19667822"><a name="p19667822"></a><a name="p19667822"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p49589783"><a name="p49589783"></a><a name="p49589783"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row43654868"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p46383386"><a name="p46383386"></a><a name="p46383386"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p66066785"><a name="p66066785"></a><a name="p66066785"></a><a href="#d0e49699">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p45631063"><a name="p45631063"></a><a name="p45631063"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e49699"></a>
<table><thead align="left"><tr id="row55139806"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p37139327"><a name="p37139327"></a><a name="p37139327"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p55495549"><a name="p55495549"></a><a name="p55495549"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p65954495"><a name="p65954495"></a><a name="p65954495"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row40713902"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p9491761"><a name="p9491761"></a><a name="p9491761"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p30635185"><a name="p30635185"></a><a name="p30635185"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p65530901"><a name="p65530901"></a><a name="p65530901"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row52907200"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p57624822"><a name="p57624822"></a><a name="p57624822"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p37099012"><a name="p37099012"></a><a name="p37099012"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p52230035"><a name="p52230035"></a><a name="p52230035"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row308275"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p24970277"><a name="p24970277"></a><a name="p24970277"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p9326572"><a name="p9326572"></a><a name="p9326572"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p17254896"><a name="p17254896"></a><a name="p17254896"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row21076340"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p29461981"><a name="p29461981"></a><a name="p29461981"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p37610295"><a name="p37610295"></a><a name="p37610295"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p26535082"><a name="p26535082"></a><a name="p26535082"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row37489148"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p16722118"><a name="p16722118"></a><a name="p16722118"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p12314300"><a name="p12314300"></a><a name="p12314300"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p57934280"><a name="p57934280"></a><a name="p57934280"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row51646472"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p22614733"><a name="p22614733"></a><a name="p22614733"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p19854107"><a name="p19854107"></a><a name="p19854107"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p64678809"><a name="p64678809"></a><a name="p64678809"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row45238369"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p40429291"><a name="p40429291"></a><a name="p40429291"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p53547129"><a name="p53547129"></a><a name="p53547129"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p42350196"><a name="p42350196"></a><a name="p42350196"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "storage.k8s.io/v1",
    "resources": [
        {
            "name": "storageclasses",
            "singularName": "",
            "namespaced": false,
            "kind": "StorageClass",
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
                "sc"
            ]
        }
    ]
}
```

## 状态码<a name="section29973509"></a>

[表3](#d0e49800)描述API的状态码。

**表 3**  状态码

<a name="d0e49800"></a>
<table><thead align="left"><tr id="row28924005"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p61143082"><a name="p61143082"></a><a name="p61143082"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p53642595"><a name="p53642595"></a><a name="p53642595"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row50082937"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p30186067"><a name="p30186067"></a><a name="p30186067"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p29152345"><a name="p29152345"></a><a name="p29152345"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

