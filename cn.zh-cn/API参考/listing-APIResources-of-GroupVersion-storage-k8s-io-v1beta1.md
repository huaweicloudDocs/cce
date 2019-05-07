# listing APIResources of GroupVersion storage.k8s.io/v1beta1<a name="cce_02_0204"></a>

## 功能介绍<a name="section12592885"></a>

This API is used to list APIResources of GroupVersion "storage.k8s.io/v1beta1".

## URI<a name="section46227102"></a>

GET /apis/storage.k8s.io/v1beta1

## 请求消息<a name="section13390742"></a>

N/A.

## 响应消息<a name="section53407821"></a>

**响应参数：**

[表1](#d0e49879)  describes the response parameters.

**表 1**  参数解释

<a name="d0e49879"></a>
<table><thead align="left"><tr id="row14884665"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p64807237"><a name="p64807237"></a><a name="p64807237"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p14894878"><a name="p14894878"></a><a name="p14894878"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p65634475"><a name="p65634475"></a><a name="p65634475"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row14792277"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p57323779"><a name="p57323779"></a><a name="p57323779"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p12714526"><a name="p12714526"></a><a name="p12714526"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p23243661"><a name="p23243661"></a><a name="p23243661"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row7866360"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p33195393"><a name="p33195393"></a><a name="p33195393"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p4472274"><a name="p4472274"></a><a name="p4472274"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p26709908"><a name="p26709908"></a><a name="p26709908"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row39062582"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p9952612"><a name="p9952612"></a><a name="p9952612"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p855254"><a name="p855254"></a><a name="p855254"></a><a href="#d0e49929">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p19500960"><a name="p19500960"></a><a name="p19500960"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e49929"></a>
<table><thead align="left"><tr id="row60828981"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p28200435"><a name="p28200435"></a><a name="p28200435"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p2533938"><a name="p2533938"></a><a name="p2533938"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p3922458"><a name="p3922458"></a><a name="p3922458"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49283666"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p32553986"><a name="p32553986"></a><a name="p32553986"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p19627219"><a name="p19627219"></a><a name="p19627219"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p46300908"><a name="p46300908"></a><a name="p46300908"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row14054996"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p64712877"><a name="p64712877"></a><a name="p64712877"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p7251683"><a name="p7251683"></a><a name="p7251683"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p50515421"><a name="p50515421"></a><a name="p50515421"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row51985607"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p50084643"><a name="p50084643"></a><a name="p50084643"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p30324279"><a name="p30324279"></a><a name="p30324279"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p40347564"><a name="p40347564"></a><a name="p40347564"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row27583762"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p19692283"><a name="p19692283"></a><a name="p19692283"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p51571096"><a name="p51571096"></a><a name="p51571096"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p16509266"><a name="p16509266"></a><a name="p16509266"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row14365669"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p22768532"><a name="p22768532"></a><a name="p22768532"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p32311828"><a name="p32311828"></a><a name="p32311828"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p12429"><a name="p12429"></a><a name="p12429"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row111862"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p9060822"><a name="p9060822"></a><a name="p9060822"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p62837954"><a name="p62837954"></a><a name="p62837954"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p56709539"><a name="p56709539"></a><a name="p56709539"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row40623811"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p2194414"><a name="p2194414"></a><a name="p2194414"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p43529858"><a name="p43529858"></a><a name="p43529858"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p36257573"><a name="p36257573"></a><a name="p36257573"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "storage.k8s.io/v1beta1",
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

## 状态码<a name="section10908349"></a>

[表3](#d0e50030)描述API的状态码。

**表 3**  状态码

<a name="d0e50030"></a>
<table><thead align="left"><tr id="row14643679"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p45287325"><a name="p45287325"></a><a name="p45287325"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p44394675"><a name="p44394675"></a><a name="p44394675"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row39198922"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p20996105"><a name="p20996105"></a><a name="p20996105"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p22962969"><a name="p22962969"></a><a name="p22962969"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

