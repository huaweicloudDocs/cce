# 删除Ingress<a name="cce_02_0261"></a>

## 功能介绍<a name="section53754776"></a>

This API is used to delete an Ingress.

## URI<a name="section14030938"></a>

DELETE /apis/networking.k8s.io/v1beta1/namespaces/\{namespace\}/ingresses/\{name\} \(Supports 1.15 and 1.15+\)

DELETE /apis/extensions/v1beta1/namespaces/\{namespace\}/ingresses/\{name\} \(Supports 1.15-\)

[表1](#d0e42906)描述该API的参数。

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
<tbody><tr id="row10781191719208"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p19781117112019"><a name="p19781117112019"></a><a name="p19781117112019"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p578231710205"><a name="p578231710205"></a><a name="p578231710205"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p978261710207"><a name="p978261710207"></a><a name="p978261710207"></a><span>Name of the Ingress.</span></p>
</td>
</tr>
<tr id="row19095777"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p3254085"><a name="p3254085"></a><a name="p3254085"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p62254326"><a name="p62254326"></a><a name="p62254326"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p9435611"><a name="p9435611"></a><a name="p9435611"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row20522133618302"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p1522836153011"><a name="p1522836153011"></a><a name="p1522836153011"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p10523163603012"><a name="p10523163603012"></a><a name="p10523163603012"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p1852311367308"><a name="p1852311367308"></a><a name="p1852311367308"></a><span>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</span></p>
</td>
</tr>
<tr id="row624413343302"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p13244133414304"><a name="p13244133414304"></a><a name="p13244133414304"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p624483412306"><a name="p624483412306"></a><a name="p624483412306"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p152441344307"><a name="p152441344307"></a><a name="p152441344307"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object’s finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="row17811636"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p33456451"><a name="p33456451"></a><a name="p33456451"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p25618043"><a name="p25618043"></a><a name="p25618043"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p61795587"><a name="p61795587"></a><a name="p61795587"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row1753393453111"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p1653413443116"><a name="p1653413443116"></a><a name="p1653413443116"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p253493417317"><a name="p253493417317"></a><a name="p253493417317"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p1353413347311"><a name="p1353413347311"></a><a name="p1353413347311"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: <em id="i3248135110313"><a name="i3248135110313"></a><a name="i3248135110313"></a>Orphan</em> - orphan the dependents; <em id="i102485513314"><a name="i102485513314"></a><a name="i102485513314"></a>Background</em> - allow the garbage collector to delete the dependents in the background; <em id="i62481751103110"><a name="i62481751103110"></a><a name="i62481751103110"></a>Foreground</em> - a cascading policy that deletes all dependents in the foreground.</p>
</td>
</tr>
<tr id="row26391471649"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p14640471145"><a name="p14640471145"></a><a name="p14640471145"></a>body</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p064011716413"><a name="p064011716413"></a><a name="p064011716413"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p46408710414"><a name="p46408710414"></a><a name="p46408710414"></a>-</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section18662134312520"></a>

N/A

## 响应消息<a name="section726119112252"></a>

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
        "name": "ingress-test",
        "group": "extensions",
        "kind": "ingresses",
        "uid": "138af621-7ad3-11e8-a5f8-fa163e458c2a"
    },
    "code": 200
}
```

## 状态码<a name="section534515230266"></a>

[表2](#d0e43055)描述API的状态码。

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

