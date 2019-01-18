# 删除所有的Secret<a name="cce_02_0114"></a>

## 功能介绍<a name="section44856736"></a>

This API is used to delete collection of Secret.

## URI<a name="section1057444"></a>

DELETE /api/v1/namespaces/\{namespace\}/secrets

[表1](#d0e14442)描述该API的参数。

**表 1**  参数解释

<a name="d0e14442"></a>
<table><thead align="left"><tr id="row49778871"><th class="cellrowborder" valign="top" width="22.45%" id="mcps1.2.4.1.1"><p id="p5556711"><a name="p5556711"></a><a name="p5556711"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.33%" id="mcps1.2.4.1.2"><p id="p47440419"><a name="p47440419"></a><a name="p47440419"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61.22%" id="mcps1.2.4.1.3"><p id="p17468756"><a name="p17468756"></a><a name="p17468756"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row5683170"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p57683636"><a name="p57683636"></a><a name="p57683636"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p41862963"><a name="p41862963"></a><a name="p41862963"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p35456838"><a name="p35456838"></a><a name="p35456838"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row50676091"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p11122696"><a name="p11122696"></a><a name="p11122696"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p28523165"><a name="p28523165"></a><a name="p28523165"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p28675043"><a name="p28675043"></a><a name="p28675043"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row56748800"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p33250065"><a name="p33250065"></a><a name="p33250065"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p8900776"><a name="p8900776"></a><a name="p8900776"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p49874218"><a name="p49874218"></a><a name="p49874218"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row46214784"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p52410000"><a name="p52410000"></a><a name="p52410000"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p17351617"><a name="p17351617"></a><a name="p17351617"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p63303738"><a name="p63303738"></a><a name="p63303738"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row32862738"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p44636107"><a name="p44636107"></a><a name="p44636107"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p58754913"><a name="p58754913"></a><a name="p58754913"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p61527483"><a name="p61527483"></a><a name="p61527483"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row16876437"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p24814161"><a name="p24814161"></a><a name="p24814161"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p63790021"><a name="p63790021"></a><a name="p63790021"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p66718106"><a name="p66718106"></a><a name="p66718106"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row63592048"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p50682297"><a name="p50682297"></a><a name="p50682297"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p11625398"><a name="p11625398"></a><a name="p11625398"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p2133200"><a name="p2133200"></a><a name="p2133200"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row19198803"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p11599202"><a name="p11599202"></a><a name="p11599202"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p11330"><a name="p11330"></a><a name="p11330"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p917787"><a name="p917787"></a><a name="p917787"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## Request<a name="section9517004"></a>

N/A

## 响应消息<a name="section18544176"></a>

**Response parameters:**

响应参数的详细描述请参见[表2](创建Secret.md#zh-cn_topic_0079614900_ref458786458)

**Example response**:

```
{
    "kind": "SecretList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/delns-12130306/secrets",
        "resourceVersion": "419248"
    },
    "items": [
        {
            "metadata": {
                "name": "default-token-zx6gk",
                "namespace": "delns-12130306",
                "selfLink": "/api/v1/namespaces/delns-12130306/secrets/default-token-zx6gk",
                "uid": "025df020-dfb4-11e7-9c19-fa163e2d897b",
                "resourceVersion": "419149",
                "creationTimestamp": "2017-12-13T03:16:28Z",
                "annotations": {
                    "generator": "JWT",
                    "kubernetes.io/service-account.name": "default",
                    "kubernetes.io/service-account.uid": "025c1f6e-dfb4-11e7-9c19-fa163e2d897b"
                },
                "enable": true
            },
            "data": {
                "ca.crt": "",
                "namespace": "ZGVsbnMtMTIxMzAzMDY=",
                "token": ""
            },
            "type": "kubernetes.io/service-account-token"
        },
        {
            "metadata": {
                "name": "st-del-12130306",
                "namespace": "delns-12130306",
                "selfLink": "/api/v1/namespaces/delns-12130306/secrets/st-del-12130306",
                "uid": "14975399-dfb4-11e7-9c19-fa163e2d897b",
                "resourceVersion": "419248",
                "creationTimestamp": "2017-12-13T03:16:59Z",
                "enable": true
            },
            "data": {
                ".dockerconfigjson": ""
            },
            "type": "kubernetes.io/dockerconfigjson"
        }
    ]
}
```

## 状态码<a name="section32679856"></a>

[表2](#d0e14569)描述API的状态码。

**表 2**  状态码

<a name="d0e14569"></a>
<table><thead align="left"><tr id="row25575097"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p58316938"><a name="p58316938"></a><a name="p58316938"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p26051532"><a name="p26051532"></a><a name="p26051532"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row29799334"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p64935873"><a name="p64935873"></a><a name="p64935873"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p25314373"><a name="p25314373"></a><a name="p25314373"></a>Delete a DaemonSet resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

