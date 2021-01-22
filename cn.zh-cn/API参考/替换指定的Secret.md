# 替换指定的Secret<a name="cce_02_0046"></a>

## 功能介绍<a name="s2fa7c6b09ad0449ebce13163ee876960"></a>

该API用于替换指定Namespace下的Secret对象。

其中以下字段支持更新：

-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.generation
-   metadata.creationTimestamp
-   metadata.deletionTimestamp
-   metadata.labels
-   metadata.clusterName
-   metadata.generateName
-   metadata.annotations

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   当“type“的值为“Opaque“时，“data“的“key“和“value“都可以更新。
>-   当“type“的值不为“Opaque“时，“data“的“value“可以更新。

## URI<a name="se7a801b22ec44205a03503a15151ba92"></a>

PUT /api/v1/namespaces/\{namespace\}/secrets/\{name\}

[表1](#table195518420539)  描述该API的参数。

**表 1**  参数描述

<a name="table195518420539"></a>
<table><thead align="left"><tr id="row1895516485313"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p49558415538"><a name="p49558415538"></a><a name="p49558415538"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p495518435314"><a name="p495518435314"></a><a name="p495518435314"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p395615465319"><a name="p395615465319"></a><a name="p395615465319"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row159562040536"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p395612415535"><a name="p395612415535"></a><a name="p395612415535"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p119561495319"><a name="p119561495319"></a><a name="p119561495319"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615031_p61052759"><a name="zh-cn_topic_0079615031_p61052759"></a><a name="zh-cn_topic_0079615031_p61052759"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row1795634105314"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1195619465319"><a name="p1195619465319"></a><a name="p1195619465319"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p169561249530"><a name="p169561249530"></a><a name="p169561249530"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615031_p11408737"><a name="zh-cn_topic_0079615031_p11408737"></a><a name="zh-cn_topic_0079615031_p11408737"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row195616417532"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p9956104155314"><a name="p9956104155314"></a><a name="p9956104155314"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p795619475316"><a name="p795619475316"></a><a name="p795619475316"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615031_p13513185"><a name="zh-cn_topic_0079615031_p13513185"></a><a name="zh-cn_topic_0079615031_p13513185"></a>Name of the Secret.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079615031_ref458786529"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建Secret.md#zh-cn_topic_0079614900_ref458786458)。

**请求示例：**

```
{ 
   "apiVersion": "v1", 
   "kind": "Secret", 
   "metadata": { 
     "name": "mysecret" 
   }, 
   "type": "Opaque", 
   "data": { 
     "password": "******", #需要用Base64编码，方法：echo -n "待编码内容" | base64
     "username": "*****" #需要用Base64编码，方法：echo -n "待编码内容" | base64
   } 
 }
```

## 响应消息<a name="s62e9d00c756e4ae99025f3a29117287f"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Secret.md#zh-cn_topic_0079614900_ref458786458)。

**响应示例：**

```
{
    "kind": "Secret",
    "apiVersion": "v1",
    "metadata": {
        "name": "mysecret",
        "namespace": "ns-12130306-s",
        "selfLink": "/api/v1/namespaces/ns-12130306-s/secrets/mysecret",
        "uid": "0bbfb314-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "418375",
        "creationTimestamp": "2017-12-13T03:09:34Z",
        "enable": true
    },
    "data": {
        "password": "******",
        "username": "*****" 
    },
    "type": "Opaque",
    "httpcode": 200,
    "header": {
        "X-Frame-Options": "SAMEORIGIN",
        "Strict-Transport-Security": "max-age=31536000; includeSubdomains;",
        "Server": "Web Server",
        "X-Router-Status": "fresh,upstream return 200",
        "X-Content-Type-Options": "nosniff",
        "Connection": "keep-alive",
        "X-Download-Options": "noopen",
        "Set-Cookie": "******; Expires=Thu, 14-Dec-17 03:09:34 GMT; Domain=192.168.50.250; Path=/; Secure; HttpOnly",
        "Content-Length": "364",
        "X-XSS-Protection": "1; mode=block;",
        "Date": "Wed, 13 Dec 2017 03:09:34 GMT",
        "Content-Type": "application/json"
    }
}
```

## 状态码<a name="s0cae25a23bb14c80b7b9465f8da69cd7"></a>

[表2](#zh-cn_topic_0079615031_table64060950)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615031_table64060950"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615031_row64282674"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p57631252201621"><a name="p57631252201621"></a><a name="p57631252201621"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0079615031_p46527158"><a name="zh-cn_topic_0079615031_p46527158"></a><a name="zh-cn_topic_0079615031_p46527158"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615031_row10603493"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615031_p53576637"><a name="zh-cn_topic_0079615031_p53576637"></a><a name="zh-cn_topic_0079615031_p53576637"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615031_p44740325"><a name="zh-cn_topic_0079615031_p44740325"></a><a name="zh-cn_topic_0079615031_p44740325"></a>操作成功，返回更新后的secret资源对象</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

