# listing APIResources of GroupVersion authorization.kubernetes.io/v1beta1<a name="cce_02_0194"></a>

## 功能介绍<a name="section24060969"></a>

This API is used to list APIResources of GroupVersion "authorization.kubernetes.io/v1beta1".

## URI<a name="section15222134"></a>

GET /apis/authorization.kubernetes.io/v1beta1

## 请求消息<a name="section2781482"></a>

N/A.

## 响应消息<a name="section25033342"></a>

**响应参数：**

[表1](#d0e47579)  describes the response parameters.

**表 1**  参数解释

<a name="d0e47579"></a>
<table><thead align="left"><tr id="row25914492"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p18699099"><a name="p18699099"></a><a name="p18699099"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p38232075"><a name="p38232075"></a><a name="p38232075"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p9790388"><a name="p9790388"></a><a name="p9790388"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row54823933"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p11553550"><a name="p11553550"></a><a name="p11553550"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p63422352"><a name="p63422352"></a><a name="p63422352"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p36936874"><a name="p36936874"></a><a name="p36936874"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row63996416"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p16327218"><a name="p16327218"></a><a name="p16327218"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p47436305"><a name="p47436305"></a><a name="p47436305"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p17135492"><a name="p17135492"></a><a name="p17135492"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row20001705"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p9525398"><a name="p9525398"></a><a name="p9525398"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p33359755"><a name="p33359755"></a><a name="p33359755"></a><a href="#d0e47629">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p25853118"><a name="p25853118"></a><a name="p25853118"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e47629"></a>
<table><thead align="left"><tr id="row39728575"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p63898035"><a name="p63898035"></a><a name="p63898035"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p8358347"><a name="p8358347"></a><a name="p8358347"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p5937520"><a name="p5937520"></a><a name="p5937520"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row11177097"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p32929663"><a name="p32929663"></a><a name="p32929663"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p50057017"><a name="p50057017"></a><a name="p50057017"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p28086559"><a name="p28086559"></a><a name="p28086559"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row51452447"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p6898675"><a name="p6898675"></a><a name="p6898675"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p21921832"><a name="p21921832"></a><a name="p21921832"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p30837990"><a name="p30837990"></a><a name="p30837990"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row9106455"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p66534260"><a name="p66534260"></a><a name="p66534260"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p20565998"><a name="p20565998"></a><a name="p20565998"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p55233132"><a name="p55233132"></a><a name="p55233132"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row27336144"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p66744080"><a name="p66744080"></a><a name="p66744080"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p37561417"><a name="p37561417"></a><a name="p37561417"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p22575906"><a name="p22575906"></a><a name="p22575906"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row1856562"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p16163806"><a name="p16163806"></a><a name="p16163806"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p34199935"><a name="p34199935"></a><a name="p34199935"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p18731389"><a name="p18731389"></a><a name="p18731389"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row34364778"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p32083646"><a name="p32083646"></a><a name="p32083646"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p48638497"><a name="p48638497"></a><a name="p48638497"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p47404222"><a name="p47404222"></a><a name="p47404222"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row23984817"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p63722005"><a name="p63722005"></a><a name="p63722005"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p61208774"><a name="p61208774"></a><a name="p61208774"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p58963627"><a name="p58963627"></a><a name="p58963627"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "authorization.kubernetes.io/v1beta1",
    "resources": [
        {
            "name": "localsubjectaccessreviews",
            "singularName": "",
            "namespaced": true,
            "kind": "LocalSubjectAccessReview",
            "verbs": [
                "create"
            ]
        },
        {
            "name": "selfsubjectaccessreviews",
            "singularName": "",
            "namespaced": false,
            "kind": "SelfSubjectAccessReview",
            "verbs": [
                "create"
            ]
        },
        {
            "name": "subjectaccessreviews",
            "singularName": "",
            "namespaced": false,
            "kind": "SubjectAccessReview",
            "verbs": [
                "create"
            ]
        }
    ]
}
```

## 状态码<a name="section23973491"></a>

[表3](#d0e47730)描述API的状态码。

**表 3**  状态码

<a name="d0e47730"></a>
<table><thead align="left"><tr id="row43316795"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p18999532"><a name="p18999532"></a><a name="p18999532"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p62567162"><a name="p62567162"></a><a name="p62567162"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row34775372"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p65341771"><a name="p65341771"></a><a name="p65341771"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p58192094"><a name="p58192094"></a><a name="p58192094"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

