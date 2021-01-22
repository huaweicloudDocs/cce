# 创建ConfigMap<a name="cce_02_0169"></a>

## 功能介绍<a name="section65969046"></a>

This API is used to create a Node Node resource object.

## URI<a name="section56850503"></a>

POST /api/v1/namespaces/\{namespace\}/configmaps

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
<tbody><tr id="row19095777"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p3254085"><a name="p3254085"></a><a name="p3254085"></a>namespace</p>
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
</tbody>
</table>

## 请求消息<a name="section41892484"></a>

**请求参数：**

请求参数如[表2](#d0e42951)所示。

**表 2**  请求参数

<a name="d0e42951"></a>
<table><thead align="left"><tr id="row29055885"><th class="cellrowborder" valign="top" width="22.447755224477554%" id="mcps1.2.5.1.1"><p id="p4716456"><a name="p4716456"></a><a name="p4716456"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.288571142885711%" id="mcps1.2.5.1.2"><p id="p46488660"><a name="p46488660"></a><a name="p46488660"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.3"><p id="p7485112"><a name="p7485112"></a><a name="p7485112"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.85571442855714%" id="mcps1.2.5.1.4"><p id="p2314365"><a name="p2314365"></a><a name="p2314365"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row53245899"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p17950537"><a name="p17950537"></a><a name="p17950537"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p44707359"><a name="p44707359"></a><a name="p44707359"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p64526326"><a name="p64526326"></a><a name="p64526326"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p59249909"><a name="p59249909"></a><a name="p59249909"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row63487140"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p42184691"><a name="p42184691"></a><a name="p42184691"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p61516799"><a name="p61516799"></a><a name="p61516799"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p16804783"><a name="p16804783"></a><a name="p16804783"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p19010155"><a name="p19010155"></a><a name="p19010155"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row36873674"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p33977604"><a name="p33977604"></a><a name="p33977604"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p722559"><a name="p722559"></a><a name="p722559"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p58527331"><a name="p58527331"></a><a name="p58527331"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table47756489">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p52295694"><a name="p52295694"></a><a name="p52295694"></a>Standard list metadata.</p>
</td>
</tr>
<tr id="row899203"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p5726608"><a name="p5726608"></a><a name="p5726608"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p61202085"><a name="p61202085"></a><a name="p61202085"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p58421867"><a name="p58421867"></a><a name="p58421867"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p34550793"><a name="p34550793"></a><a name="p34550793"></a>Data contains the configuration data. Each key must consist of alphanumeric characters, '-', '_' or '.'.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
    "apiVersion": "v1",
    "data": {
        "property_1": "test"
    },
    "kind": "ConfigMap",
    "metadata": {
        "name": "test-12130306"
    }
}
```

## 响应消息<a name="section41488036"></a>

**响应参数：**

响应参数的详细描述请参见[表2](#d0e42951)。

**响应示例：**

```
{
    "kind": "ConfigMap",
    "apiVersion": "v1",
    "metadata": {
        "name": "test-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/api/v1/namespaces/ns-12130306-s/configmaps/test-12130306",
        "uid": "efd6d9e0-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "419081",
        "creationTimestamp": "2017-12-13T03:15:57Z",
        "enable": true
    },
    "data": {
        "property_1": "test"
    }
}
```

## 状态码<a name="section37848010"></a>

[表3](#d0e43055)描述API的状态码。

**表 3**  状态码

<a name="d0e43055"></a>
<table><thead align="left"><tr id="row20813512"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p8172937"><a name="p8172937"></a><a name="p8172937"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p58028199"><a name="p58028199"></a><a name="p58028199"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2663689"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p14432280"><a name="p14432280"></a><a name="p14432280"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p28164027"><a name="p28164027"></a><a name="p28164027"></a>The request has been fulfilled, resulting in the creation of a new resource.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

