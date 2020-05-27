# 获取Ingress列表<a name="cce_02_0265"></a>

## 功能介绍<a name="section53754776"></a>

This API is used to list or watch objects of kind Ingress.

## URI<a name="section14030938"></a>

GET /apis/networking.k8s.io/v1beta1/ingresses \(Supports since1.15\)

GET /apis/extensions/v1beta1/ingresses \(Compatible\)

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
<tbody><tr id="row10781191719208"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p19781117112019"><a name="p19781117112019"></a><a name="p19781117112019"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p578231710205"><a name="p578231710205"></a><a name="p578231710205"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p978261710207"><a name="p978261710207"></a><a name="p978261710207"></a><span>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</span></p>
</td>
</tr>
<tr id="row19095777"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p3254085"><a name="p3254085"></a><a name="p3254085"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p62254326"><a name="p62254326"></a><a name="p62254326"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p13311152718012"><a name="p13311152718012"></a><a name="p13311152718012"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row20522133618302"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p1522836153011"><a name="p1522836153011"></a><a name="p1522836153011"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p10523163603012"><a name="p10523163603012"></a><a name="p10523163603012"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p281014399014"><a name="p281014399014"></a><a name="p281014399014"></a><span>If true, partially initialized resources are included in the response.</span></p>
</td>
</tr>
<tr id="row624413343302"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p13244133414304"><a name="p13244133414304"></a><a name="p13244133414304"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p624483412306"><a name="p624483412306"></a><a name="p624483412306"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p152441344307"><a name="p152441344307"></a><a name="p152441344307"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row17811636"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p33456451"><a name="p33456451"></a><a name="p33456451"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p25618043"><a name="p25618043"></a><a name="p25618043"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p1857142219113"><a name="p1857142219113"></a><a name="p1857142219113"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the continuefield on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.</p>
<p id="p17572022410"><a name="p17572022410"></a><a name="p17572022410"></a>The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row4843152517115"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p08431925218"><a name="p08431925218"></a><a name="p08431925218"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p14843125716"><a name="p14843125716"></a><a name="p14843125716"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p384317252013"><a name="p384317252013"></a><a name="p384317252013"></a>If <em id="i549020571119"><a name="i549020571119"></a><a name="i549020571119"></a>true</em>, then the output is pretty printed.</p>
</td>
</tr>
<tr id="row1680214381211"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p14802173813112"><a name="p14802173813112"></a><a name="p14802173813112"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p1280215381514"><a name="p1280215381514"></a><a name="p1280215381514"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p1580220385118"><a name="p1580220385118"></a><a name="p1580220385118"></a><span>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it’s 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</span></p>
</td>
</tr>
<tr id="row693613351015"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p89361435115"><a name="p89361435115"></a><a name="p89361435115"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p59364351716"><a name="p59364351716"></a><a name="p59364351716"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p8936193511110"><a name="p8936193511110"></a><a name="p8936193511110"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row962873311119"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p46281033915"><a name="p46281033915"></a><a name="p46281033915"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p136281335117"><a name="p136281335117"></a><a name="p136281335117"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p136281833912"><a name="p136281833912"></a><a name="p136281833912"></a><span>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</span></p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section18662134312520"></a>

N/A

## 响应消息<a name="section194751211619"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Ingress.md#d0e42951)。

**响应示例：**

```
{
    "kind": "IngressList",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "selfLink": "/apis/extensions/v1beta1/ingresses",
        "resourceVersion": "1495401"
    },
    "items": [
        {
            "metadata": {
                "name": "ingress-test",
                "namespace": "default",
                "selfLink": "/apis/extensions/v1beta1/namespaces/default/ingresses/ingress-test",
                "uid": "29817662-7adb-11e8-a5f8-fa163e458c2a",
                "resourceVersion": "1494672",
                "generation": 1,
                "creationTimestamp": "2018-06-28T13:57:14Z",
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

## 状态码<a name="section9127551153112"></a>

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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p135341732589"><a name="p135341732589"></a><a name="p135341732589"></a>success</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

