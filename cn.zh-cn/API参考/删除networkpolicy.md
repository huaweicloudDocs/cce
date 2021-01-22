# 删除networkpolicy<a name="cce_02_0279"></a>

## 功能介绍<a name="section474171885320"></a>

This API is used to delete a NetworkPolicy.

## URL<a name="section219412719263"></a>

DELETE /apis/networking.k8s.io/v1/namespaces/\{namespace\}/networkpolicies/\{name\}

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
<tbody><tr id="row10781191719208"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p19781117112019"><a name="p19781117112019"></a><a name="p19781117112019"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p578231710205"><a name="p578231710205"></a><a name="p578231710205"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p978261710207"><a name="p978261710207"></a><a name="p978261710207"></a><span>Name of the NetworkPolicy</span>.</p>
</td>
</tr>
<tr id="row19095777"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p3254085"><a name="p3254085"></a><a name="p3254085"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p62254326"><a name="p62254326"></a><a name="p62254326"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p9435611"><a name="p9435611"></a><a name="p9435611"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row17811636"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p33456451"><a name="p33456451"></a><a name="p33456451"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p25618043"><a name="p25618043"></a><a name="p25618043"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p61795587"><a name="p61795587"></a><a name="p61795587"></a>If 'true', then the output is pretty printed.</p>
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

## 请求消息<a name="section1097017235815"></a>

N/A

## 响应消息<a name="section13598181712916"></a>

**响应参数：**

响应参数的详细描述请参见[请求参数](创建networkpolicy.md#d0e42951)。

**响应示例：**

```
{
    "apiVersion": "v1",
	"code": 200,	
	"details": {
	    "name": "aqws", 
	    "group": "networking.k8s.io", 
	    "kind": "networkpolicies",
            "uid" : "0eea113a-ebb6-11e8-889b-fa163ecbd381"
	},
    "kind": "Status",
    "metadata" : {},
    "status": "Success"	
}
```

## 状态码<a name="section14947131610112"></a>

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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p13489144118012"><a name="p13489144118012"></a><a name="p13489144118012"></a>OK</p>
</td>
</tr>
</tbody>
</table>

