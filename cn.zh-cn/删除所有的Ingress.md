# 删除所有的Ingress<a name="cce_02_0262"></a>

## 功能介绍<a name="section53754776"></a>

This API is used to delete collection of Ingress.

## URI<a name="section14030938"></a>

DELETE /apis/extensions/v1beta1/namespaces/\{namespace\}/ingresses

[表1](#d0e42906)描述该API的参数。

**表 1**  参数解释

<a name="d0e42906"></a>
<table><thead align="left"><tr id="row10640301"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row19095777"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p3254085"><a name="p3254085"></a><a name="p3254085"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p62254326"><a name="p62254326"></a><a name="p62254326"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p9435611"><a name="p9435611"></a><a name="p9435611"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row20522133618302"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p1522836153011"><a name="p1522836153011"></a><a name="p1522836153011"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p10523163603012"><a name="p10523163603012"></a><a name="p10523163603012"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p1852311367308"><a name="p1852311367308"></a><a name="p1852311367308"></a>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</p>
</td>
</tr>
<tr id="row624413343302"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p13244133414304"><a name="p13244133414304"></a><a name="p13244133414304"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p624483412306"><a name="p624483412306"></a><a name="p624483412306"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p152441344307"><a name="p152441344307"></a><a name="p152441344307"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row17811636"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p33456451"><a name="p33456451"></a><a name="p33456451"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p25618043"><a name="p25618043"></a><a name="p25618043"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p61795587"><a name="p61795587"></a><a name="p61795587"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row1753393453111"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p1653413443116"><a name="p1653413443116"></a><a name="p1653413443116"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p253493417317"><a name="p253493417317"></a><a name="p253493417317"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p1353413347311"><a name="p1353413347311"></a><a name="p1353413347311"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row129823551381"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p498285513380"><a name="p498285513380"></a><a name="p498285513380"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p498215519384"><a name="p498215519384"></a><a name="p498215519384"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p435372743915"><a name="p435372743915"></a><a name="p435372743915"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the continuefield on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.</p>
<p id="p3353192720398"><a name="p3353192720398"></a><a name="p3353192720398"></a>The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row15450128163911"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p1345016883910"><a name="p1345016883910"></a><a name="p1345016883910"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p194502812396"><a name="p194502812396"></a><a name="p194502812396"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p1450282397"><a name="p1450282397"></a><a name="p1450282397"></a>If <em id="i1691161912407"><a name="i1691161912407"></a><a name="i1691161912407"></a>true</em>, then the output is pretty printed.</p>
</td>
</tr>
<tr id="row378595183911"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p117851657391"><a name="p117851657391"></a><a name="p117851657391"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p17785105153911"><a name="p17785105153911"></a><a name="p17785105153911"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p1378511543918"><a name="p1378511543918"></a><a name="p1378511543918"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it’s 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row6157130396"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p1115813323914"><a name="p1115813323914"></a><a name="p1115813323914"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p3158103133912"><a name="p3158103133912"></a><a name="p3158103133912"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p915816317399"><a name="p915816317399"></a><a name="p915816317399"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row16929259103817"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p139294597389"><a name="p139294597389"></a><a name="p139294597389"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p09291859133820"><a name="p09291859133820"></a><a name="p09291859133820"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p14929205910382"><a name="p14929205910382"></a><a name="p14929205910382"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section18662134312520"></a>

N/A

## 响应消息<a name="section9262331134617"></a>

**响应参数：**

响应参数的详细描述请参见[表4](删除Secret.md#zh-cn_topic_0079615047_table30941925)。

**响应示例：**

```
{
    "kind": "IngressList",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "selfLink": "/apis/extensions/v1beta1/namespaces/default/ingresses",
        "resourceVersion": "1494570"
    },
    "items": [
        {
            "metadata": {
                "name": "ingress-test",
                "namespace": "default",
                "selfLink": "/apis/extensions/v1beta1/namespaces/default/ingresses/ingress-test",
                "uid": "0bb1b895-7adb-11e8-a5f8-fa163e458c2a",
                "resourceVersion": "1494559",
                "generation": 1,
                "creationTimestamp": "2018-06-28T13:56:24Z",
                "labels": {
                    "isExternal": "true",
                    "zone": "data"
                },
                "annotations": {
                    "ingress.beta.kubernetes.io/role": "data",
                    "ingress.kubernetes.io/secure-backends": "false",
                    "kubernetes.io/elb.id": "203e27c4-ceaa-4bca-b652-6947f77d1ce0",
                    "kubernetes.io/elb.ip": "10.154.199.81",
                    "kubernetes.io/elb.port": "80",
                    "kubernetes.io/ingress.class": "public-elb",
                    "protocol": "HTTP"
                }
            },
            "spec": {
                "rules": [
                    {
                        "host": "test",
                        "http": {
                            "paths": [
                                {
                                    "path": "/sssss",
                                    "backend": {
                                        "serviceName": "ingress-test",
                                        "servicePort": 8086
                                    },
                                    "property": {
                                        "ingress.beta.kubernetes.io/url-match-mode": "STARTS_WITH"
                                    }
                                }
                            ]
                        }
                    }
                ]
            },
            "status": {
                "loadBalancer": {
                    "ingress": [
                        {
                            "ip": "10.154.199.81",
                            "hostname": "test"
                        }
                    ]
                }
            }
        }
    ]
}
```

## 状态码<a name="section1851444287"></a>

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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16641479525"><a name="p16641479525"></a><a name="p16641479525"></a>success</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

