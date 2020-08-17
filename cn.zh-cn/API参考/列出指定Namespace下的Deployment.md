# 列出指定Namespace下的Deployment<a name="cce_02_0127"></a>

## 功能介绍<a name="section51078739"></a>

This API is used to list all Deployment resource objects under a specified Namespace.

## URI<a name="section57055467"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/deployments \(Supports 1.9 and 1.9+\)

GET /apis/apps/v1beta1/namespaces/\{namespace\}/deployments \(Supports only1.7\)

GET /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments \(Compatible\)

[表1](#d0e36539)描述该API的参数。

**表 1**  参数解释

<a name="d0e36539"></a>
<table><thead align="left"><tr id="row2135501"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.16%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61.62%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row59065999"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p19616629"><a name="p19616629"></a><a name="p19616629"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p45443123"><a name="p45443123"></a><a name="p45443123"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p57014386"><a name="p57014386"></a><a name="p57014386"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row43367434"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p23101228"><a name="p23101228"></a><a name="p23101228"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p59260195"><a name="p59260195"></a><a name="p59260195"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p35346519"><a name="p35346519"></a><a name="p35346519"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row49683219"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p64917804"><a name="p64917804"></a><a name="p64917804"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p23850806"><a name="p23850806"></a><a name="p23850806"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p6042403"><a name="p6042403"></a><a name="p6042403"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row54381628"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p42835719"><a name="p42835719"></a><a name="p42835719"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p47141219"><a name="p47141219"></a><a name="p47141219"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p60342391"><a name="p60342391"></a><a name="p60342391"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row6210614"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p33297746"><a name="p33297746"></a><a name="p33297746"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p12762939"><a name="p12762939"></a><a name="p12762939"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p27165144"><a name="p27165144"></a><a name="p27165144"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row43159710"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p6275621"><a name="p6275621"></a><a name="p6275621"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p38563284"><a name="p38563284"></a><a name="p38563284"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p36618324"><a name="p36618324"></a><a name="p36618324"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row61129466"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p52539702"><a name="p52539702"></a><a name="p52539702"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p27857430"><a name="p27857430"></a><a name="p27857430"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p41859330"><a name="p41859330"></a><a name="p41859330"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row41189657"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p48027907"><a name="p48027907"></a><a name="p48027907"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p65055278"><a name="p65055278"></a><a name="p65055278"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p34986178"><a name="p34986178"></a><a name="p34986178"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section43737161"></a>

N/A

## 响应消息<a name="section58090133"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Deployment.md#table12862324102610)。

**响应示例**：

```
{
    "kind": "DeploymentList",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "selfLink": "/apis/apps/v1beta1/namespaces/ns-12130306-s/deployments",
        "resourceVersion": "418745"
    },
    "items": []
}
```

## 状态码<a name="section53049152"></a>

[表2](#d0e36668)描述API的状态码。

**表 2**  状态码

<a name="d0e36668"></a>
<table><thead align="left"><tr id="row17031726"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p37392545"><a name="p37392545"></a><a name="p37392545"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p8897276"><a name="p8897276"></a><a name="p8897276"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49590760"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p57428620"><a name="p57428620"></a><a name="p57428620"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p21206673"><a name="p21206673"></a><a name="p21206673"></a>This operation succeeds, and a Deployment resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

