# 替换指定的Role<a name="cce_02_0304"></a>

## 功能介绍<a name="section15607442151714"></a>

This API is used to replace the specified Role

## URL<a name="section212810541176"></a>

PUT /apis/rbac.authorization.kubernetes.io/v1/namespaces/\{namespace\}/roles/\{name\}

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
<tbody><tr id="row84161156145910"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p141645620590"><a name="p141645620590"></a><a name="p141645620590"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p1141614564595"><a name="p1141614564595"></a><a name="p1141614564595"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p19416125617595"><a name="p19416125617595"></a><a name="p19416125617595"></a>name of the Role.</p>
</td>
</tr>
<tr id="row53721532135214"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p337383220520"><a name="p337383220520"></a><a name="p337383220520"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p6373113213528"><a name="p6373113213528"></a><a name="p6373113213528"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p1937333235214"><a name="p1937333235214"></a><a name="p1937333235214"></a>object name and auth scope, such as for teams and projects.</p>
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
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p18759135485719"><a name="p18759135485719"></a><a name="p18759135485719"></a>-</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section1097017235815"></a>

**请求参数：**

请求参数的详细描述请参见[请求参数](创建Role.md#d0e42951)。

“Content-Type“的详细描述请参见 [PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
{
	"metadata": {
		"name": "pod-reader",
		"namespace": "default",
		"selfLink": "/apis/rbac.authorization.kubernetes.io/v1/namespaces/default/roles/secret-reader",
		"uid": "6320bedb-f220-11e8-b449-fa163ec24e06",
		"resourceVersion": "56532",
		"creationTimestamp": "2018-11-27T08:42:35Z"
	},
	"rules": [{
		"verbs": ["get","watch"],
		"apiGroups": [""],
		"resources": ["pods"]
	}]
}
```

## 响应消息<a name="section13598181712916"></a>

**响应参数：**

响应参数的详细描述请参见[请求参数](创建Role.md#d0e42951)。

**响应示例：**

```
{
	"kind": "Role",
	"apiVersion": "rbac.authorization.kubernetes.io/v1",
	"metadata": {
		"name": "pod-reader",
		"namespace": "default",
		"selfLink": "/apis/rbac.authorization.kubernetes.io/v1/namespaces/default/roles/secret-reader",
		"uid": "6320bedb-f220-11e8-b449-fa163ec24e06",
		"resourceVersion": "56532",
		"creationTimestamp": "2018-11-27T08:42:35Z"
	},
	"rules": [{
		"verbs": ["get",watch"],
		"apiGroups": [""],
		"resources": ["pods"]
	}]
}
```

## 状态码<a name="section14947131610112"></a>

[状态码](#d0e43055)描述API的状态码。

**表 2**  状态码

<a name="d0e43055"></a>
<table><thead align="left"><tr id="row20813512"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p53137435195352"><a name="p53137435195352"></a><a name="p53137435195352"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0079615066_p19540130"><a name="zh-cn_topic_0079615066_p19540130"></a><a name="zh-cn_topic_0079615066_p19540130"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2663689"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615066_p24863727"><a name="zh-cn_topic_0079615066_p24863727"></a><a name="zh-cn_topic_0079615066_p24863727"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615066_p696045"><a name="zh-cn_topic_0079615066_p696045"></a><a name="zh-cn_topic_0079615066_p696045"></a>OK</p>
</td>
</tr>
<tr id="row826601219502"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p157531052144911"><a name="p157531052144911"></a><a name="p157531052144911"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p137534522491"><a name="p137534522491"></a><a name="p137534522491"></a>Created</p>
</td>
</tr>
</tbody>
</table>

