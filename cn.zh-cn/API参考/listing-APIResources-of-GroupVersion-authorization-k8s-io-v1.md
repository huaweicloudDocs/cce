# listing APIResources of GroupVersion authorization.k8s.io/v1<a name="cce_02_0193"></a>

## 功能介绍<a name="section62678510"></a>

This API is used to list APIResources of GroupVersion "authorization.k8s.io/v1".

## URI<a name="section27235686"></a>

GET /apis/authorization.k8s.io/v1

## 请求消息<a name="section43794588"></a>

N/A.

## 响应消息<a name="section58606977"></a>

**响应参数：**

[表1](#d0e47349)  describes the response parameters.

**表 1**  参数解释

<a name="d0e47349"></a>
<table><thead align="left"><tr id="row7340367"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p57698855"><a name="p57698855"></a><a name="p57698855"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p43095692"><a name="p43095692"></a><a name="p43095692"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p1090149"><a name="p1090149"></a><a name="p1090149"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row21193243"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p38931093"><a name="p38931093"></a><a name="p38931093"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p66410811"><a name="p66410811"></a><a name="p66410811"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p10566647"><a name="p10566647"></a><a name="p10566647"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row27990959"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p52675236"><a name="p52675236"></a><a name="p52675236"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p38835746"><a name="p38835746"></a><a name="p38835746"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p58687696"><a name="p58687696"></a><a name="p58687696"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row58427216"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p34984074"><a name="p34984074"></a><a name="p34984074"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p15137736"><a name="p15137736"></a><a name="p15137736"></a><a href="#cce_02_0193__d0e47399">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p29556236"><a name="p29556236"></a><a name="p29556236"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e47399"></a>
<table><thead align="left"><tr id="row40744145"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p11941435"><a name="p11941435"></a><a name="p11941435"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p27732198"><a name="p27732198"></a><a name="p27732198"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p31715578"><a name="p31715578"></a><a name="p31715578"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18824989"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p48429178"><a name="p48429178"></a><a name="p48429178"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p30449335"><a name="p30449335"></a><a name="p30449335"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p50477052"><a name="p50477052"></a><a name="p50477052"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row51640290"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p22113927"><a name="p22113927"></a><a name="p22113927"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p46397640"><a name="p46397640"></a><a name="p46397640"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p112527"><a name="p112527"></a><a name="p112527"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row1012743"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p14923343"><a name="p14923343"></a><a name="p14923343"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p831247"><a name="p831247"></a><a name="p831247"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p222192"><a name="p222192"></a><a name="p222192"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row1999732"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p27760617"><a name="p27760617"></a><a name="p27760617"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p34017490"><a name="p34017490"></a><a name="p34017490"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p3953304"><a name="p3953304"></a><a name="p3953304"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row35579737"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p63386420"><a name="p63386420"></a><a name="p63386420"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p34026400"><a name="p34026400"></a><a name="p34026400"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p4675012"><a name="p4675012"></a><a name="p4675012"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row42075115"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p52641175"><a name="p52641175"></a><a name="p52641175"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p36076816"><a name="p36076816"></a><a name="p36076816"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p36540989"><a name="p36540989"></a><a name="p36540989"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row60433451"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p63271362"><a name="p63271362"></a><a name="p63271362"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p24706689"><a name="p24706689"></a><a name="p24706689"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p55084817"><a name="p55084817"></a><a name="p55084817"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "authorization.k8s.io/v1",
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

## 状态码<a name="section57700750"></a>

[表3](#d0e47500)描述API的状态码。

**表 3**  状态码

<a name="d0e47500"></a>
<table><thead align="left"><tr id="row65849641"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p32220709"><a name="p32220709"></a><a name="p32220709"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p59740633"><a name="p59740633"></a><a name="p59740633"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row7153134"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p42533004"><a name="p42533004"></a><a name="p42533004"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p22621274"><a name="p22621274"></a><a name="p22621274"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

F异常状态码请参见[状态码](状态码.md)。

