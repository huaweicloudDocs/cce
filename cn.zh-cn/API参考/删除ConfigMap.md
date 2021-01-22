# 删除ConfigMap<a name="cce_02_0170"></a>

## 功能介绍<a name="section4992645"></a>

This API is used to delete a ConfigMap.

## URI<a name="section44933808"></a>

DELETE /api/v1/namespaces/\{namespace\}/configmaps/\{name\}

[表1](#d0e43122)描述该API的参数。

**表 1**  参数解释

<a name="d0e43122"></a>
<table><thead align="left"><tr id="row4620112"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="23%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="44%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row38131941"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p1679523"><a name="p1679523"></a><a name="p1679523"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p1823714"><a name="p1823714"></a><a name="p1823714"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p13503178"><a name="p13503178"></a><a name="p13503178"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row54419740"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p45922835"><a name="p45922835"></a><a name="p45922835"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p28762183"><a name="p28762183"></a><a name="p28762183"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p48035487"><a name="p48035487"></a><a name="p48035487"></a>name of the ConfigMap</p>
</td>
</tr>
<tr id="row29666204"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p54152358"><a name="p54152358"></a><a name="p54152358"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p24264905"><a name="p24264905"></a><a name="p24264905"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p19300268"><a name="p19300268"></a><a name="p19300268"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row39484685"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p44142899"><a name="p44142899"></a><a name="p44142899"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p18805103"><a name="p18805103"></a><a name="p18805103"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p46818342"><a name="p46818342"></a><a name="p46818342"></a>The duration in seconds before the object should be deleted. Value must be a non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="row18711900"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p39268954"><a name="p39268954"></a><a name="p39268954"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p26668680"><a name="p26668680"></a><a name="p26668680"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p12679438"><a name="p12679438"></a><a name="p12679438"></a>Deprecated: Use the PropagationPolicy. This field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="row47006082"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p49396288"><a name="p49396288"></a><a name="p49396288"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p41676395"><a name="p41676395"></a><a name="p41676395"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p48885565"><a name="p48885565"></a><a name="p48885565"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section1751091"></a>

**请求参数：**

请求参数如[表2](#d0e43214)所示。

**表 2**  参数解释

<a name="d0e43214"></a>
<table><thead align="left"><tr id="row27266773"><th class="cellrowborder" valign="top" width="21.42785721427857%" id="mcps1.2.5.1.1"><p id="p61125042"><a name="p61125042"></a><a name="p61125042"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.2"><p id="p52181359"><a name="p52181359"></a><a name="p52181359"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.3"><p id="p65940532"><a name="p65940532"></a><a name="p65940532"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.796020397960206%" id="mcps1.2.5.1.4"><p id="p39582890"><a name="p39582890"></a><a name="p39582890"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row52097528"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p59150279"><a name="p59150279"></a><a name="p59150279"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p26443327"><a name="p26443327"></a><a name="p26443327"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p61534727"><a name="p61534727"></a><a name="p61534727"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p18256967"><a name="p18256967"></a><a name="p18256967"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="p30094980"><a name="p30094980"></a><a name="p30094980"></a>The value of this parameter is <strong id="b136611544243"><a name="b136611544243"></a><a name="b136611544243"></a>DeleteOptions</strong>.</p>
</td>
</tr>
<tr id="row21774316"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p18889185"><a name="p18889185"></a><a name="p18889185"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p53629002"><a name="p53629002"></a><a name="p53629002"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p48981904"><a name="p48981904"></a><a name="p48981904"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p8111258"><a name="p8111258"></a><a name="p8111258"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="p5892460"><a name="p5892460"></a><a name="p5892460"></a>The value of this parameter is <strong id="b53032144"><a name="b53032144"></a><a name="b53032144"></a>v1</strong>.</p>
</td>
</tr>
<tr id="row7527256"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p5727996"><a name="p5727996"></a><a name="p5727996"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p61314561"><a name="p61314561"></a><a name="p61314561"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p423567"><a name="p423567"></a><a name="p423567"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p34308941"><a name="p34308941"></a><a name="p34308941"></a>The duration in seconds before the object should be deleted. Value must be a non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
<p id="p40345013"><a name="p40345013"></a><a name="p40345013"></a>Value range of this parameter: &gt; 0.</p>
</td>
</tr>
<tr id="row27560803"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p17832570"><a name="p17832570"></a><a name="p17832570"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p35152057"><a name="p35152057"></a><a name="p35152057"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p28744393"><a name="p28744393"></a><a name="p28744393"></a><a href="#d0e43330">preconditions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p16697443"><a name="p16697443"></a><a name="p16697443"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="row16059259"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p25731564"><a name="p25731564"></a><a name="p25731564"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p3881934"><a name="p3881934"></a><a name="p3881934"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p46001224"><a name="p46001224"></a><a name="p46001224"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p35111683"><a name="p35111683"></a><a name="p35111683"></a>Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list.</p>
</td>
</tr>
<tr id="row47569696"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p27940191"><a name="p27940191"></a><a name="p27940191"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p48562994"><a name="p48562994"></a><a name="p48562994"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p41288450"><a name="p41288450"></a><a name="p41288450"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p34509161"><a name="p34509161"></a><a name="p34509161"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  preconditions字段数据结构说明

<a name="d0e43330"></a>
<table><thead align="left"><tr id="row25317718"><th class="cellrowborder" valign="top" width="21.42785721427857%" id="mcps1.2.5.1.1"><p id="p37469293"><a name="p37469293"></a><a name="p37469293"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.2"><p id="p15113921"><a name="p15113921"></a><a name="p15113921"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.3"><p id="p16268089"><a name="p16268089"></a><a name="p16268089"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.796020397960206%" id="mcps1.2.5.1.4"><p id="p42646846"><a name="p42646846"></a><a name="p42646846"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row31842487"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p29104653"><a name="p29104653"></a><a name="p29104653"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p8666663"><a name="p8666663"></a><a name="p8666663"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p30911085"><a name="p30911085"></a><a name="p30911085"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p20769993"><a name="p20769993"></a><a name="p20769993"></a>Specifies the target UID.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
    "kind": "DeleteOptions",
    "apiVersion": "v1",
    "gracePeriodSeconds": 0
}
```

## 响应消息<a name="section15759823"></a>

**响应参数：**

响应参数的详细描述请参见[表2](删除Secret.md#table13766144711235)。

**响应示例：**

```
{
    "kind": "Status",
    "apiVersion": "v1",
    "metadata": {},
    "status": "Success",
    "details": {
        "name": "test-12130306",
        "kind": "configmaps",
        "uid": "efd6d9e0-dfb3-11e7-9c19-fa163e2d897b"
    },
    "code": 200
}
```

## 状态码<a name="section7620686"></a>

[表4](#d0e43397)描述API的状态码。

**表 4**  状态码

<a name="d0e43397"></a>
<table><thead align="left"><tr id="row30119043"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p23723412"><a name="p23723412"></a><a name="p23723412"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p42548185"><a name="p42548185"></a><a name="p42548185"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row23850938"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p52877857"><a name="p52877857"></a><a name="p52877857"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p55247987"><a name="p55247987"></a><a name="p55247987"></a>Delete a ConfigMap resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

