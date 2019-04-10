# listing APIResources of GroupVersion networking.kubernetes.io/v1<a name="cce_02_0198"></a>

## 功能介绍<a name="section14441351"></a>

This API is used to list APIResources of GroupVersion "networking.kubernetes.io/v1".

## URI<a name="section62863296"></a>

GET /apis/networking.kubernetes.io/v1

## 请求消息<a name="section28898760"></a>

N/A.

## 响应消息<a name="section58762255"></a>

**响应参数：**

[表1](#d0e48499)  describes the response parameters.

**表 1**  参数解释

<a name="d0e48499"></a>
<table><thead align="left"><tr id="row26591467"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p6425239"><a name="p6425239"></a><a name="p6425239"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p50682384"><a name="p50682384"></a><a name="p50682384"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p11632445"><a name="p11632445"></a><a name="p11632445"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2704007"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p17698005"><a name="p17698005"></a><a name="p17698005"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p24252304"><a name="p24252304"></a><a name="p24252304"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p18279583"><a name="p18279583"></a><a name="p18279583"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row30298522"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p38261187"><a name="p38261187"></a><a name="p38261187"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p12148404"><a name="p12148404"></a><a name="p12148404"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p44496662"><a name="p44496662"></a><a name="p44496662"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row64925640"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p24485526"><a name="p24485526"></a><a name="p24485526"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p37170600"><a name="p37170600"></a><a name="p37170600"></a><a href="#d0e48549">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p52495778"><a name="p52495778"></a><a name="p52495778"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e48549"></a>
<table><thead align="left"><tr id="row11588023"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p66214677"><a name="p66214677"></a><a name="p66214677"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p61788660"><a name="p61788660"></a><a name="p61788660"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p38825596"><a name="p38825596"></a><a name="p38825596"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row57865556"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p56598436"><a name="p56598436"></a><a name="p56598436"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p21070613"><a name="p21070613"></a><a name="p21070613"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p28998094"><a name="p28998094"></a><a name="p28998094"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row59656262"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p319039"><a name="p319039"></a><a name="p319039"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p25842197"><a name="p25842197"></a><a name="p25842197"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p12843183"><a name="p12843183"></a><a name="p12843183"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row48479785"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p34548517"><a name="p34548517"></a><a name="p34548517"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p46966489"><a name="p46966489"></a><a name="p46966489"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p46189294"><a name="p46189294"></a><a name="p46189294"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row13050468"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p50455021"><a name="p50455021"></a><a name="p50455021"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p60324906"><a name="p60324906"></a><a name="p60324906"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p54479236"><a name="p54479236"></a><a name="p54479236"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row20551079"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p54024694"><a name="p54024694"></a><a name="p54024694"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p13924118"><a name="p13924118"></a><a name="p13924118"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p54111791"><a name="p54111791"></a><a name="p54111791"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row17244072"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p54592552"><a name="p54592552"></a><a name="p54592552"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p59920564"><a name="p59920564"></a><a name="p59920564"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p21727541"><a name="p21727541"></a><a name="p21727541"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row61330149"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p1686192"><a name="p1686192"></a><a name="p1686192"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p2363876"><a name="p2363876"></a><a name="p2363876"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p57256231"><a name="p57256231"></a><a name="p57256231"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "networking.kubernetes.io/v1",
    "resources": [
        {
            "name": "networkpolicies",
            "singularName": "",
            "namespaced": true,
            "kind": "NetworkPolicy",
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

## 状态码<a name="section59098255"></a>

[表3](#d0e48650)描述API的状态码。

**表 3**  状态码

<a name="d0e48650"></a>
<table><thead align="left"><tr id="row57543781"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p30534705"><a name="p30534705"></a><a name="p30534705"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p57392074"><a name="p57392074"></a><a name="p57392074"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18246423"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1565313"><a name="p1565313"></a><a name="p1565313"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p59681519"><a name="p59681519"></a><a name="p59681519"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

