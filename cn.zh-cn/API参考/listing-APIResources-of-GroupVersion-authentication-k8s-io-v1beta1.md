# listing APIResources of GroupVersion authentication.k8s.io/v1beta1<a name="cce_02_0192"></a>

## 功能介绍<a name="section51167169"></a>

This API is used to list APIResources of GroupVersion "authentication.k8s.io/v1beta1".

## URI<a name="section57851338"></a>

GET /apis/authentication.k8s.io/v1beta1

## 请求消息<a name="section50899994"></a>

N/A.

## 响应消息<a name="section55446762"></a>

**响应参数：**

[表1](#d0e47119)  describes the response parameters.

**表 1**  参数解释

<a name="d0e47119"></a>
<table><thead align="left"><tr id="row2846859"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p29269059"><a name="p29269059"></a><a name="p29269059"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p21983563"><a name="p21983563"></a><a name="p21983563"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p35838155"><a name="p35838155"></a><a name="p35838155"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row17209452"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p51788373"><a name="p51788373"></a><a name="p51788373"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p34108719"><a name="p34108719"></a><a name="p34108719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p11342882"><a name="p11342882"></a><a name="p11342882"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row34977076"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p14570878"><a name="p14570878"></a><a name="p14570878"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p39390452"><a name="p39390452"></a><a name="p39390452"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p36510080"><a name="p36510080"></a><a name="p36510080"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row60155264"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p40738245"><a name="p40738245"></a><a name="p40738245"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p11463571"><a name="p11463571"></a><a name="p11463571"></a><a href="#d0e47169">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p35444249"><a name="p35444249"></a><a name="p35444249"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e47169"></a>
<table><thead align="left"><tr id="row51035771"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p40256775"><a name="p40256775"></a><a name="p40256775"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p39573303"><a name="p39573303"></a><a name="p39573303"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p51320947"><a name="p51320947"></a><a name="p51320947"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row63356068"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p31567922"><a name="p31567922"></a><a name="p31567922"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p6864900"><a name="p6864900"></a><a name="p6864900"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p19186051"><a name="p19186051"></a><a name="p19186051"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row38456734"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p27987787"><a name="p27987787"></a><a name="p27987787"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p52418264"><a name="p52418264"></a><a name="p52418264"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p18020973"><a name="p18020973"></a><a name="p18020973"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row27971035"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p51061328"><a name="p51061328"></a><a name="p51061328"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p42326881"><a name="p42326881"></a><a name="p42326881"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p5925368"><a name="p5925368"></a><a name="p5925368"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row53328312"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p24626000"><a name="p24626000"></a><a name="p24626000"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p48548960"><a name="p48548960"></a><a name="p48548960"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p40151697"><a name="p40151697"></a><a name="p40151697"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row25820957"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p11122786"><a name="p11122786"></a><a name="p11122786"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p28530459"><a name="p28530459"></a><a name="p28530459"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p29265841"><a name="p29265841"></a><a name="p29265841"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row62065978"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p61288293"><a name="p61288293"></a><a name="p61288293"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p65404705"><a name="p65404705"></a><a name="p65404705"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p63289749"><a name="p63289749"></a><a name="p63289749"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row32736836"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p34438080"><a name="p34438080"></a><a name="p34438080"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p38021129"><a name="p38021129"></a><a name="p38021129"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p59812614"><a name="p59812614"></a><a name="p59812614"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "authentication.k8s.io/v1beta1",
    "resources": [
        {
            "name": "tokenreviews",
            "singularName": "",
            "namespaced": false,
            "kind": "TokenReview",
            "verbs": [
                "create"
            ]
        }
    ]
}
```

## 状态码<a name="section29258811"></a>

[表3](#d0e47270)描述API的状态码。

**表 3**  状态码

<a name="d0e47270"></a>
<table><thead align="left"><tr id="row54646375"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p64280248"><a name="p64280248"></a><a name="p64280248"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p39317565"><a name="p39317565"></a><a name="p39317565"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row30606174"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p63181061"><a name="p63181061"></a><a name="p63181061"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p17392279"><a name="p17392279"></a><a name="p17392279"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

