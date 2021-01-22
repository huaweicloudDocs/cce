# 替换指定Namespace下的某个Ingress对象的状态<a name="cce_02_0267"></a>

## 功能介绍<a name="section53754776"></a>

This API is used to replace status of the specified Ingress.

其中以下字段支持更新：

status.loadBalancer

## URI<a name="section14030938"></a>

PUT /apis/networking.k8s.io/v1beta1/namespaces/\{namespace\}/ingresses/\{name\}/status \(Supports 1.15 and 1.15+\)

PUT /apis/extensions/v1beta1/namespaces/\{namespace\}/ingresses/\{name\}/status \(Supports 1.15-\)

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
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p978261710207"><a name="p978261710207"></a><a name="p978261710207"></a><span>name of the Ingress.</span></p>
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
<tr id="row18814556171017"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p58142056131018"><a name="p58142056131018"></a><a name="p58142056131018"></a>body</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p19814195601016"><a name="p19814195601016"></a><a name="p19814195601016"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p4814185620106"><a name="p4814185620106"></a><a name="p4814185620106"></a>-</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section18662134312520"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建Ingress.md#d0e42951)。

**请求示例：**

```
{
    "apiVersion": "extensions/v1beta1",
    "kind": "Ingress",
    "metadata": {
        "labels": {
            "zone": "data",
            "isExternal": "true"
        },
        "name": "ingress-test",
        "annotations": {
            "kubernetes.io/ingress.class": "public-elb",
            "ingress.kubernetes.io/secure-backends": "false",
            "ingress.beta.kubernetes.io/role": "data",
            "protocol": "HTTP",
            "kubernetes.io/elb.ip": "10.154.199.81",
            "kubernetes.io/elb.port": "80",
            "kubernetes.io/elb.id": "203e27c4-ceaa-4bca-b652-6947f77d1ce0"
        }
    },
    "spec": {
        "rules": [
            {
                "http": {
                    "paths": [
                        {
                            "backend": {
                                "serviceName": "ingress-test",
                                "servicePort": 8087
                            },
                            "path": "/sssss",
                            "property": {
                                "ingress.beta.kubernetes.io/url-match-mode": "STARTS_WITH"
                            }
                        }
                    ]
                },
                "host": "test"
            }
        ]
    }
}
```

## 响应消息<a name="section1071812962118"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Ingress.md#d0e42951)。

**响应示例：**

```
{
    "kind": "Ingress",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "name": "ingress-test",
        "namespace": "default",
        "selfLink": "/apis/extensions/v1beta1/namespaces/default/ingresses/ingress-test/status",
        "uid": "29817662-7adb-11e8-a5f8-fa163e458c2a",
        "resourceVersion": "1499417",
        "generation": 3,
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
                "host": "agaaaa",
                "http": {
                    "paths": [
                        {
                            "path": "/sssss",
                            "backend": {
                                "serviceName": "test",
                                "servicePort": 8080
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
        "loadBalancer": {}
    }
}
```

## 状态码<a name="section10771131813717"></a>

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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1159883516594"><a name="p1159883516594"></a><a name="p1159883516594"></a>success</p>
</td>
</tr>
<tr id="row388218015333"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p08829053311"><a name="p08829053311"></a><a name="p08829053311"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1588200153314"><a name="p1588200153314"></a><a name="p1588200153314"></a>created</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

