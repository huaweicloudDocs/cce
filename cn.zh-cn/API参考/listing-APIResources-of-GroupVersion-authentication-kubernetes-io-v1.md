# listing APIResources of GroupVersion authentication.kubernetes.io/v1<a name="cce_02_0191"></a>

## 功能介绍<a name="section24640658"></a>

This API is used to list APIResources of GroupVersion "authentication.kubernetes.io/v1".

## URI<a name="section20439338"></a>

GET /apis/authentication.kubernetes.io/v1

## 请求消息<a name="section49736316"></a>

N/A.

## 响应消息<a name="section44973667"></a>

**响应参数：**

[表1](#d0e46889)  describes the response parameters.

**表 1**  参数解释

<a name="d0e46889"></a>
<table><thead align="left"><tr id="row23309850"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p9049715"><a name="p9049715"></a><a name="p9049715"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p61938284"><a name="p61938284"></a><a name="p61938284"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p50945069"><a name="p50945069"></a><a name="p50945069"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row32909919"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p48457769"><a name="p48457769"></a><a name="p48457769"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p32765236"><a name="p32765236"></a><a name="p32765236"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p36738472"><a name="p36738472"></a><a name="p36738472"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row62210792"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p5909387"><a name="p5909387"></a><a name="p5909387"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p8898347"><a name="p8898347"></a><a name="p8898347"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p49677487"><a name="p49677487"></a><a name="p49677487"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row44444202"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p43210624"><a name="p43210624"></a><a name="p43210624"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p10399662"><a name="p10399662"></a><a name="p10399662"></a><a href="#d0e46939">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p65161549"><a name="p65161549"></a><a name="p65161549"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e46939"></a>
<table><thead align="left"><tr id="row23729842"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p43069063"><a name="p43069063"></a><a name="p43069063"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p66042064"><a name="p66042064"></a><a name="p66042064"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p47806966"><a name="p47806966"></a><a name="p47806966"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row47159008"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p61783286"><a name="p61783286"></a><a name="p61783286"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p38390306"><a name="p38390306"></a><a name="p38390306"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p22607049"><a name="p22607049"></a><a name="p22607049"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row2136855"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p38867589"><a name="p38867589"></a><a name="p38867589"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p61266979"><a name="p61266979"></a><a name="p61266979"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p63678233"><a name="p63678233"></a><a name="p63678233"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row36233189"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p49207187"><a name="p49207187"></a><a name="p49207187"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p26359214"><a name="p26359214"></a><a name="p26359214"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p54721565"><a name="p54721565"></a><a name="p54721565"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row22732040"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p29355921"><a name="p29355921"></a><a name="p29355921"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p29019362"><a name="p29019362"></a><a name="p29019362"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p1758116"><a name="p1758116"></a><a name="p1758116"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row15823046"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p6598388"><a name="p6598388"></a><a name="p6598388"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p64707430"><a name="p64707430"></a><a name="p64707430"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p6810501"><a name="p6810501"></a><a name="p6810501"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row61294512"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p65908477"><a name="p65908477"></a><a name="p65908477"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p36986410"><a name="p36986410"></a><a name="p36986410"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p43109215"><a name="p43109215"></a><a name="p43109215"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row52438621"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p19669874"><a name="p19669874"></a><a name="p19669874"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p49755939"><a name="p49755939"></a><a name="p49755939"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p3699290"><a name="p3699290"></a><a name="p3699290"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "authentication.kubernetes.io/v1",
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

## 状态码<a name="section2109823"></a>

[表3](#d0e47040)描述API的状态码。

**表 3**  状态码

<a name="d0e47040"></a>
<table><thead align="left"><tr id="row4441640"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p24228578"><a name="p24228578"></a><a name="p24228578"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p16357792"><a name="p16357792"></a><a name="p16357792"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49912779"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p16403274"><a name="p16403274"></a><a name="p16403274"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p53596806"><a name="p53596806"></a><a name="p53596806"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

