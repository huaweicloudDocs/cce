# 删除所有的Endpoints<a name="cce_02_0117"></a>

## 功能介绍<a name="section42942155"></a>

This API is used to delete collection of Endpoints.

## URI<a name="section50935076"></a>

DELETE /api/v1/namespaces/\{namespace\}/endpoints

[表1](#d0e25539)描述该API的参数。

**表 1**  参数解释

<a name="d0e25539"></a>
<table><thead align="left"><tr id="row58455411"><th class="cellrowborder" valign="top" width="22.45%" id="mcps1.2.4.1.1"><p id="p37267884"><a name="p37267884"></a><a name="p37267884"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.33%" id="mcps1.2.4.1.2"><p id="p65908633"><a name="p65908633"></a><a name="p65908633"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61.22%" id="mcps1.2.4.1.3"><p id="p36999075"><a name="p36999075"></a><a name="p36999075"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row44135089"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p18172460"><a name="p18172460"></a><a name="p18172460"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p62683131"><a name="p62683131"></a><a name="p62683131"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p44168839"><a name="p44168839"></a><a name="p44168839"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row61975231"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p53937776"><a name="p53937776"></a><a name="p53937776"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p6883730"><a name="p6883730"></a><a name="p6883730"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p20711244"><a name="p20711244"></a><a name="p20711244"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row52183474"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p66111876"><a name="p66111876"></a><a name="p66111876"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p53461763"><a name="p53461763"></a><a name="p53461763"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p35435542"><a name="p35435542"></a><a name="p35435542"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row50484427"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p62706776"><a name="p62706776"></a><a name="p62706776"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p46084077"><a name="p46084077"></a><a name="p46084077"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p41822771"><a name="p41822771"></a><a name="p41822771"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row40860624"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p21376225"><a name="p21376225"></a><a name="p21376225"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p53752696"><a name="p53752696"></a><a name="p53752696"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p59001082"><a name="p59001082"></a><a name="p59001082"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row61247696"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p62116320"><a name="p62116320"></a><a name="p62116320"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p65366033"><a name="p65366033"></a><a name="p65366033"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p60157322"><a name="p60157322"></a><a name="p60157322"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row4544994"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p32600219"><a name="p32600219"></a><a name="p32600219"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p23372081"><a name="p23372081"></a><a name="p23372081"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p14090379"><a name="p14090379"></a><a name="p14090379"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row59704549"><td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.1 "><p id="p4230305"><a name="p4230305"></a><a name="p4230305"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.33%" headers="mcps1.2.4.1.2 "><p id="p7110421"><a name="p7110421"></a><a name="p7110421"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p39073258"><a name="p39073258"></a><a name="p39073258"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## Request<a name="section55762507"></a>

N/A

## 响应消息<a name="section32100520"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Endpoints.md#zh-cn_topic_0079614955_ref458759912)

响应示例：

```
{
    "kind": "EndpointsList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/delns-12130306/endpoints",
        "resourceVersion": "419246"
    },
    "items": [
        {
            "metadata": {
                "name": "ep-del-12130306",
                "namespace": "delns-12130306",
                "selfLink": "/api/v1/namespaces/delns-12130306/endpoints/ep-del-12130306",
                "uid": "1480f55c-dfb4-11e7-9c19-fa163e2d897b",
                "resourceVersion": "419246",
                "creationTimestamp": "2017-12-13T03:16:58Z",
                "enable": true
            },
            "subsets": [
                {
                    "addresses": [
                        {
                            "ip": "10.154.75.241"
                        }
                    ],
                    "ports": [
                        {
                            "port": 31043,
                            "protocol": "TCP"
                        }
                    ]
                }
            ]
        }
    ]
}
```

## 状态码<a name="section20469228"></a>

[表2](#d0e25667)描述API的状态码。

**表 2**  状态码

<a name="d0e25667"></a>
<table><thead align="left"><tr id="row32640430"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p26629144"><a name="p26629144"></a><a name="p26629144"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p9477038"><a name="p9477038"></a><a name="p9477038"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row29442650"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p36044417"><a name="p36044417"></a><a name="p36044417"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p33916685"><a name="p33916685"></a><a name="p33916685"></a>Delete an Endpoints resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

