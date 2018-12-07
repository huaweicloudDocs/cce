# 删除所有的ConfigMap<a name="cce_02_0171"></a>

## 功能介绍<a name="section13890442"></a>

This API is used to delete collection of ConfigMap.

## URI<a name="section57905122"></a>

DELETE /api/v1/namespaces/\{namespace\}/configmaps

[表1](#d0e43464)描述该API的参数。

**表 1**  参数解释

<a name="d0e43464"></a>
<table><thead align="left"><tr id="row32529038"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.15%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="62.629999999999995%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row45647968"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p6497962"><a name="p6497962"></a><a name="p6497962"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p56572941"><a name="p56572941"></a><a name="p56572941"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p19005488"><a name="p19005488"></a><a name="p19005488"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row36831665"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p30574871"><a name="p30574871"></a><a name="p30574871"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p60645523"><a name="p60645523"></a><a name="p60645523"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p13340298"><a name="p13340298"></a><a name="p13340298"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row52953824"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p61401374"><a name="p61401374"></a><a name="p61401374"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p7455372"><a name="p7455372"></a><a name="p7455372"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p67014226"><a name="p67014226"></a><a name="p67014226"></a>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</p>
</td>
</tr>
<tr id="row66257126"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p65226980"><a name="p65226980"></a><a name="p65226980"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p48894031"><a name="p48894031"></a><a name="p48894031"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p993550"><a name="p993550"></a><a name="p993550"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row8941953"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p53209562"><a name="p53209562"></a><a name="p53209562"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p15007227"><a name="p15007227"></a><a name="p15007227"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p7625869"><a name="p7625869"></a><a name="p7625869"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row1523959"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p56331893"><a name="p56331893"></a><a name="p56331893"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p66589495"><a name="p66589495"></a><a name="p66589495"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p25040038"><a name="p25040038"></a><a name="p25040038"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row24033753"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p577014"><a name="p577014"></a><a name="p577014"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p46738163"><a name="p46738163"></a><a name="p46738163"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p27694840"><a name="p27694840"></a><a name="p27694840"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the continue field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true. The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row47926974"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p56879651"><a name="p56879651"></a><a name="p56879651"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p43848996"><a name="p43848996"></a><a name="p43848996"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p62107819"><a name="p62107819"></a><a name="p62107819"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row22099459"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p45225739"><a name="p45225739"></a><a name="p45225739"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p39406219"><a name="p39406219"></a><a name="p39406219"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p37787180"><a name="p37787180"></a><a name="p37787180"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row4540304"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p32220357"><a name="p32220357"></a><a name="p32220357"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.2 "><p id="p59712110"><a name="p59712110"></a><a name="p59712110"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.629999999999995%" headers="mcps1.2.4.1.3 "><p id="p4842740"><a name="p4842740"></a><a name="p4842740"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section51384056"></a>

N/A

## 响应消息<a name="section59803325"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建ConfigMap.md#d0e42951)。

**响应示例：**

```
{
    "kind": "ConfigMapList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/ns-12130306-s/configmaps",
        "resourceVersion": "419144"
    },
    "items": []
}
```

## 状态码<a name="section1359018"></a>

[表2](#d0e43612)描述API的状态码。

**表 2**  状态码

<a name="d0e43612"></a>
<table><thead align="left"><tr id="row12283955"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p55476324"><a name="p55476324"></a><a name="p55476324"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p64397298"><a name="p64397298"></a><a name="p64397298"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row48798660"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p60377411"><a name="p60377411"></a><a name="p60377411"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p58732118"><a name="p58732118"></a><a name="p58732118"></a>Delete a ConfigMap resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

