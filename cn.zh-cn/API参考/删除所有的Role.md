# 删除所有的Role<a name="ZH-CN_TOPIC_0140918319"></a>

## 功能介绍<a name="section38641523111810"></a>

This API is used to delete collection of Role

## URL<a name="section6988203810188"></a>

DELETE /apis/rbac.authorization.k8s.io/v1/namespaces/\{namespace\}/roles

[参数解释](#d0e42906)描述该API的参数。

**表 1**  参数解释

<a name="d0e42906"></a>
<table><thead align="left"><tr id="row10640301"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.61%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row999013125918"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p19990203111596"><a name="p19990203111596"></a><a name="p19990203111596"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p17990331175913"><a name="p17990331175913"></a><a name="p17990331175913"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p9990123165911"><a name="p9990123165911"></a><a name="p9990123165911"></a>object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row17811636"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p33456451"><a name="p33456451"></a><a name="p33456451"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p25618043"><a name="p25618043"></a><a name="p25618043"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p61795587"><a name="p61795587"></a><a name="p61795587"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row324054917610"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p1124024920612"><a name="p1124024920612"></a><a name="p1124024920612"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 ">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p12411249269"><a name="p12411249269"></a><a name="p12411249269"></a>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</p>
</td>
</tr>
<tr id="row8371453863"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p203719531862"><a name="p203719531862"></a><a name="p203719531862"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p337185317611"><a name="p337185317611"></a><a name="p337185317611"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p03815531069"><a name="p03815531069"></a><a name="p03815531069"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row95502597616"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p10550165911618"><a name="p10550165911618"></a><a name="p10550165911618"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p5550859960"><a name="p5550859960"></a><a name="p5550859960"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p1926516398711"><a name="p1926516398711"></a><a name="p1926516398711"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row18246153971216"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p1324716394129"><a name="p1324716394129"></a><a name="p1324716394129"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p9247203913129"><a name="p9247203913129"></a><a name="p9247203913129"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p1324717397129"><a name="p1324717397129"></a><a name="p1324717397129"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row198884817818"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p08881481880"><a name="p08881481880"></a><a name="p08881481880"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p14888481680"><a name="p14888481680"></a><a name="p14888481680"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p4889148188"><a name="p4889148188"></a><a name="p4889148188"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the continue field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true. The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row16889138585"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p388912812820"><a name="p388912812820"></a><a name="p388912812820"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p1888915810820"><a name="p1888915810820"></a><a name="p1888915810820"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p13889484813"><a name="p13889484813"></a><a name="p13889484813"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row0889481784"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p11889148586"><a name="p11889148586"></a><a name="p11889148586"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p198891987812"><a name="p198891987812"></a><a name="p198891987812"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p364910501388"><a name="p364910501388"></a><a name="p364910501388"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row488916815820"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p178891816811"><a name="p178891816811"></a><a name="p178891816811"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p988968282"><a name="p988968282"></a><a name="p988968282"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p7889118385"><a name="p7889118385"></a><a name="p7889118385"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section18662134312520"></a>

N/A

## 响应消息<a name="section726119112252"></a>

**响应参数：**

响应参数的详细描述请参见[请求参数](创建Role.md#d0e42951)。

**响应示例：**

```
{
    "kind" : "RoleList",
    "apiVersion" : "rbac.authorization.k8s.io/v1",
    "metadata" : {
        "selfLink" : "/apis/rbac.authorization.k8s.io/v1/namespaces/default/roles",
        "resourceVersion" : "4629"
    },
    "items" : [ {
        "metadata" : {
            "name" : "pod-reader",
            "namespace" : "default",
            "selfLink" : "/apis/rbac.authorization.k8s.io/v1/namespaces/default/roles/secret-reader",
            "uid" : "8e7afa24-f1e7-11e8-b449-fa163ec24e06",
            "resourceVersion" : "4627",
            "creationTimestamp" : "2018-11-27T01:55:46Z"
        },
        "rules" : [ {
            "verbs" : [ "get", "watch", "list" ],
            "apiGroups" : [ "" ],
            "resources" : [ "pods" ]
        } ]
    } ]
}
```

## 状态码<a name="section534515230266"></a>

[状态码](#d0e43055)描述API的状态码。

**表 2**  状态码

<a name="d0e43055"></a>
<table><thead align="left"><tr id="row20813512"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p8172937"><a name="p8172937"></a><a name="p8172937"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p58028199"><a name="p58028199"></a><a name="p58028199"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2663689"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p14432280"><a name="p14432280"></a><a name="p14432280"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p0978454104816"><a name="p0978454104816"></a><a name="p0978454104816"></a>success</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

