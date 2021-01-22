# listing APIResources of GroupVersion autoscaling/v1<a name="cce_02_0195"></a>

## 功能介绍<a name="section20847448"></a>

This API is used to list APIResources of GroupVersion "autoscaling/v1".

## URI<a name="section53409307"></a>

GET /apis/autoscaling/v1

## 请求消息<a name="section10921718"></a>

N/A.

## 响应消息<a name="section31186602"></a>

**响应参数：**

[表1](#d0e47809)  describes the response parameters.

**表 1**  参数解释

<a name="d0e47809"></a>
<table><thead align="left"><tr id="row927775"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p8040944"><a name="p8040944"></a><a name="p8040944"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p47336693"><a name="p47336693"></a><a name="p47336693"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p9066902"><a name="p9066902"></a><a name="p9066902"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row63330493"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p29496271"><a name="p29496271"></a><a name="p29496271"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p40387766"><a name="p40387766"></a><a name="p40387766"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p50183642"><a name="p50183642"></a><a name="p50183642"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row48999598"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p9544503"><a name="p9544503"></a><a name="p9544503"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p34907313"><a name="p34907313"></a><a name="p34907313"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p8920132"><a name="p8920132"></a><a name="p8920132"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row13172326"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p60325456"><a name="p60325456"></a><a name="p60325456"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p54523750"><a name="p54523750"></a><a name="p54523750"></a><a href="#d0e47859">resources</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p19366946"><a name="p19366946"></a><a name="p19366946"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e47859"></a>
<table><thead align="left"><tr id="row5692425"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p58433280"><a name="p58433280"></a><a name="p58433280"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p35475231"><a name="p35475231"></a><a name="p35475231"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p54921487"><a name="p54921487"></a><a name="p54921487"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row19455480"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p32390017"><a name="p32390017"></a><a name="p32390017"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p6345682"><a name="p6345682"></a><a name="p6345682"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p44238228"><a name="p44238228"></a><a name="p44238228"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row62599734"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p37413732"><a name="p37413732"></a><a name="p37413732"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p10613462"><a name="p10613462"></a><a name="p10613462"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p54384117"><a name="p54384117"></a><a name="p54384117"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row19695008"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p51791853"><a name="p51791853"></a><a name="p51791853"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p34390554"><a name="p34390554"></a><a name="p34390554"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p34171471"><a name="p34171471"></a><a name="p34171471"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row39107789"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p13614306"><a name="p13614306"></a><a name="p13614306"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p29016979"><a name="p29016979"></a><a name="p29016979"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p1565130"><a name="p1565130"></a><a name="p1565130"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row14086170"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p129106"><a name="p129106"></a><a name="p129106"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p10457602"><a name="p10457602"></a><a name="p10457602"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p41759443"><a name="p41759443"></a><a name="p41759443"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row40290671"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p42318932"><a name="p42318932"></a><a name="p42318932"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p5281453"><a name="p5281453"></a><a name="p5281453"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p25144547"><a name="p25144547"></a><a name="p25144547"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row24974332"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p9654983"><a name="p9654983"></a><a name="p9654983"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p43856163"><a name="p43856163"></a><a name="p43856163"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p62688311"><a name="p62688311"></a><a name="p62688311"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "autoscaling/v1",
    "resources": [
        {
            "name": "horizontalpodautoscalers",
            "singularName": "",
            "namespaced": true,
            "kind": "HorizontalPodAutoscaler",
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
                "hpa"
            ],
            "categories": [
                "all"
            ]
        },
        {
            "name": "horizontalpodautoscalers/status",
            "singularName": "",
            "namespaced": true,
            "kind": "HorizontalPodAutoscaler",
            "verbs": [
                "get",
                "patch",
                "update"
            ]
        }
    ]
}
```

## 状态码<a name="section12243969"></a>

[表3](#d0e47960)描述API的状态码。

**表 3**  状态码

<a name="d0e47960"></a>
<table><thead align="left"><tr id="row26658977"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p11893563"><a name="p11893563"></a><a name="p11893563"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p23854574"><a name="p23854574"></a><a name="p23854574"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row53172321"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11990716"><a name="p11990716"></a><a name="p11990716"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p31723944"><a name="p31723944"></a><a name="p31723944"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

