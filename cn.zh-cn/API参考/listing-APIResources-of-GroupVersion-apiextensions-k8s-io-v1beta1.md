# listing APIResources of GroupVersion apiextensions.k8s.io/v1beta1<a name="cce_02_0205"></a>

## 功能介绍<a name="section41993139"></a>

This API is used to list APIResources of GroupVersion "apiextensions.k8s.io/v1beta1".

## URI<a name="section42393933"></a>

GET /apis/apiextensions.k8s.io/v1beta1

## 请求消息<a name="section46001078"></a>

N/A.

## 响应消息<a name="section11356519"></a>

**响应参数：**

[表1](#d0e50109)  describes the response parameters.

**表 1**  参数解释

<a name="d0e50109"></a>
<table><thead align="left"><tr id="row65222624"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p48541153"><a name="p48541153"></a><a name="p48541153"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p39519315"><a name="p39519315"></a><a name="p39519315"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p46947933"><a name="p46947933"></a><a name="p46947933"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row44686248"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p62816348"><a name="p62816348"></a><a name="p62816348"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p54959391"><a name="p54959391"></a><a name="p54959391"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p22525724"><a name="p22525724"></a><a name="p22525724"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row1404927"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p46690243"><a name="p46690243"></a><a name="p46690243"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p23813332"><a name="p23813332"></a><a name="p23813332"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p49831705"><a name="p49831705"></a><a name="p49831705"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row45832162"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p21417681"><a name="p21417681"></a><a name="p21417681"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p57110633"><a name="p57110633"></a><a name="p57110633"></a><a href="#d0e50159">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p26155994"><a name="p26155994"></a><a name="p26155994"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e50159"></a>
<table><thead align="left"><tr id="row42313316"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p4826570"><a name="p4826570"></a><a name="p4826570"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p55407860"><a name="p55407860"></a><a name="p55407860"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p58851658"><a name="p58851658"></a><a name="p58851658"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2255030"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p48439709"><a name="p48439709"></a><a name="p48439709"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p31302377"><a name="p31302377"></a><a name="p31302377"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p52464642"><a name="p52464642"></a><a name="p52464642"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row2419735"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p61780813"><a name="p61780813"></a><a name="p61780813"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p38189956"><a name="p38189956"></a><a name="p38189956"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p6378723"><a name="p6378723"></a><a name="p6378723"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row57408514"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p19578033"><a name="p19578033"></a><a name="p19578033"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p42316829"><a name="p42316829"></a><a name="p42316829"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p5111085"><a name="p5111085"></a><a name="p5111085"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row45999766"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p34993560"><a name="p34993560"></a><a name="p34993560"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p15906098"><a name="p15906098"></a><a name="p15906098"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p13325581"><a name="p13325581"></a><a name="p13325581"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row52821370"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p50672601"><a name="p50672601"></a><a name="p50672601"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p10840012"><a name="p10840012"></a><a name="p10840012"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p5625788"><a name="p5625788"></a><a name="p5625788"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row50632094"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p7558931"><a name="p7558931"></a><a name="p7558931"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p8293689"><a name="p8293689"></a><a name="p8293689"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p700215"><a name="p700215"></a><a name="p700215"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row6301943"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p40695406"><a name="p40695406"></a><a name="p40695406"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p7993552"><a name="p7993552"></a><a name="p7993552"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p43497991"><a name="p43497991"></a><a name="p43497991"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "apiextensions.k8s.io/v1beta1",
    "resources": [
        {
            "name": "customresourcedefinitions",
            "singularName": "",
            "namespaced": false,
            "kind": "CustomResourceDefinition",
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
                "crd"
            ]
        },
        {
            "name": "customresourcedefinitions/status",
            "singularName": "",
            "namespaced": false,
            "kind": "CustomResourceDefinition",
            "verbs": [
                "update"
            ]
        }
    ]
}
```

## 状态码<a name="section35099809"></a>

[表3](#d0e50260)描述API的状态码。

**表 3**  状态码

<a name="d0e50260"></a>
<table><thead align="left"><tr id="row37120553"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p53974854"><a name="p53974854"></a><a name="p53974854"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p9887043"><a name="p9887043"></a><a name="p9887043"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row62653000"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p41728254"><a name="p41728254"></a><a name="p41728254"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p24545420"><a name="p24545420"></a><a name="p24545420"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

