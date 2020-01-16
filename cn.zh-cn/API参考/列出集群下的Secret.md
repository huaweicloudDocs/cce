# 列出集群下的Secret<a name="cce_02_0048"></a>

## 功能介绍<a name="s9832be8e9a554244a817a938beac98de"></a>

该API用于列出集群中的所有Secret对象。

## URI<a name="s352ffae11a4646bc94188db7e8bfcf91"></a>

GET /api/v1/secrets

[表1](#table195206720562)  描述该API的参数。

**表 1**  参数描述

<a name="table195206720562"></a>
<table><thead align="left"><tr id="row95209765615"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="p352015711566"><a name="p352015711566"></a><a name="p352015711566"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.1%" id="mcps1.2.4.1.2"><p id="p1852010795618"><a name="p1852010795618"></a><a name="p1852010795618"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="62.839999999999996%" id="mcps1.2.4.1.3"><p id="p7520197175615"><a name="p7520197175615"></a><a name="p7520197175615"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row852014710568"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p205206720564"><a name="p205206720564"></a><a name="p205206720564"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p14520147185617"><a name="p14520147185617"></a><a name="p14520147185617"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="ad14cb7d2b618440380eb4bf942dd2c50"><a name="ad14cb7d2b618440380eb4bf942dd2c50"></a><a name="ad14cb7d2b618440380eb4bf942dd2c50"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row1052014775616"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p1752047135619"><a name="p1752047135619"></a><a name="p1752047135619"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p17520275566"><a name="p17520275566"></a><a name="p17520275566"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a44911256aebf49a7b5ae3ad8453a8937"><a name="a44911256aebf49a7b5ae3ad8453a8937"></a><a name="a44911256aebf49a7b5ae3ad8453a8937"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row185201712569"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p205202713568"><a name="p205202713568"></a><a name="p205202713568"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p185208755619"><a name="p185208755619"></a><a name="p185208755619"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a3c382597bf134507b3b553ee74b099da"><a name="a3c382597bf134507b3b553ee74b099da"></a><a name="a3c382597bf134507b3b553ee74b099da"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row15520171560"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p752097155615"><a name="p752097155615"></a><a name="p752097155615"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p145200765610"><a name="p145200765610"></a><a name="p145200765610"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a333cbdd5981847fcbaf1caaaa4d28221"><a name="a333cbdd5981847fcbaf1caaaa4d28221"></a><a name="a333cbdd5981847fcbaf1caaaa4d28221"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row35211719561"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p165211173568"><a name="p165211173568"></a><a name="p165211173568"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p105217775619"><a name="p105217775619"></a><a name="p105217775619"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p1521177195619"><a name="p1521177195619"></a><a name="p1521177195619"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row55215725611"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p1752117718568"><a name="p1752117718568"></a><a name="p1752117718568"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p45219795614"><a name="p45219795614"></a><a name="p45219795614"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="acb733f8ca00f4d00adf87badaa30d91d"><a name="acb733f8ca00f4d00adf87badaa30d91d"></a><a name="acb733f8ca00f4d00adf87badaa30d91d"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row17521177155610"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="p25212712569"><a name="p25212712569"></a><a name="p25212712569"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="p5521076569"><a name="p5521076569"></a><a name="p5521076569"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p1352187155610"><a name="p1352187155610"></a><a name="p1352187155610"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s0609e98f717b4da28f1da14e6f4c3341"></a>

N/A

## 响应消息<a name="s5a3ecee096c64650b96840664d84c0a3"></a>

**响应参数：**

**表 2**  响应参数

<a name="t0379bd97a8684d7eadf07afc388a3bb3"></a>
<table><thead align="left"><tr id="rf21a5b5429fb47caa652894d57b6deb1"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="a3a029ede9e9345d98849c9379dd2339f"><a name="a3a029ede9e9345d98849c9379dd2339f"></a><a name="a3a029ede9e9345d98849c9379dd2339f"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p6302327521041"><a name="p6302327521041"></a><a name="p6302327521041"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p461161221041"><a name="p461161221041"></a><a name="p461161221041"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r09bc2a71ba2842eea07332a417a05415"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="af1da3c49d5074f65849feccd1b820b08"><a name="af1da3c49d5074f65849feccd1b820b08"></a><a name="af1da3c49d5074f65849feccd1b820b08"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="a3fe2d3a801434d538e7394c3b626d6c7"><a name="a3fe2d3a801434d538e7394c3b626d6c7"></a><a name="a3fe2d3a801434d538e7394c3b626d6c7"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="a93336fc478f0490eb7206ee078750e4b"><a name="a93336fc478f0490eb7206ee078750e4b"></a><a name="a93336fc478f0490eb7206ee078750e4b"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="r3740d824b5d7426c9d727a9209c819d9"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="a095d27eaa891425b8041e3d1a4d661a2"><a name="a095d27eaa891425b8041e3d1a4d661a2"></a><a name="a095d27eaa891425b8041e3d1a4d661a2"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="acd8daf6d292a406fa265fef7019f20da"><a name="acd8daf6d292a406fa265fef7019f20da"></a><a name="acd8daf6d292a406fa265fef7019f20da"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="a38f8950176544380bb468d87e0ddbb63"><a name="a38f8950176544380bb468d87e0ddbb63"></a><a name="a38f8950176544380bb468d87e0ddbb63"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="r02f0cc1a6cac4a108b0ef17139973e44"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="a34069eae0183436bbef773db3c40243f"><a name="a34069eae0183436bbef773db3c40243f"></a><a name="a34069eae0183436bbef773db3c40243f"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="a57d16aa7ed944bc58d7b1d5ae2148b46"><a name="a57d16aa7ed944bc58d7b1d5ae2148b46"></a><a name="a57d16aa7ed944bc58d7b1d5ae2148b46"></a><a href="#t6ff895f91da8440685e472dac63f0547">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="addcedf6afc794771a6b4f775844b2b27"><a name="addcedf6afc794771a6b4f775844b2b27"></a><a name="addcedf6afc794771a6b4f775844b2b27"></a>Standard list metadata.</p>
</td>
</tr>
<tr id="r25f369b6a3f347c3b3a65563cdd6bb07"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="a07efeb8bbbe24f03b6d9f8bac65dab91"><a name="a07efeb8bbbe24f03b6d9f8bac65dab91"></a><a name="a07efeb8bbbe24f03b6d9f8bac65dab91"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="ada6c495fd25b43428dcb7540584913fa"><a name="ada6c495fd25b43428dcb7540584913fa"></a><a name="ada6c495fd25b43428dcb7540584913fa"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p128013175711"><a name="p128013175711"></a><a name="p128013175711"></a>List of services.具体请参见<a href="创建Secret.md#s08d56e5f4e57452da0a49400212440a4">响应消息</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="t6ff895f91da8440685e472dac63f0547"></a>
<table><thead align="left"><tr id="r86a4582b6de74880895c7e0fdf0d65d8"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="af30c046d5fd845e289825e6a4e7d1995"><a name="af30c046d5fd845e289825e6a4e7d1995"></a><a name="af30c046d5fd845e289825e6a4e7d1995"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.509999999999998%" id="mcps1.2.4.1.2"><p id="p5588517721041"><a name="p5588517721041"></a><a name="p5588517721041"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.43%" id="mcps1.2.4.1.3"><p id="p3040545621041"><a name="p3040545621041"></a><a name="p3040545621041"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r3f97e7c5adb7499b9f8e4153f1cfcff5"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614976_p556806144647"><a name="zh-cn_topic_0079614976_p556806144647"></a><a name="zh-cn_topic_0079614976_p556806144647"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.509999999999998%" headers="mcps1.2.4.1.2 "><p id="a8b64354278c548a4aa8c5d7dc3650953"><a name="a8b64354278c548a4aa8c5d7dc3650953"></a><a name="a8b64354278c548a4aa8c5d7dc3650953"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="ad21f3b5f3aa6479ea682c231dcd5a008"><a name="ad21f3b5f3aa6479ea682c231dcd5a008"></a><a name="ad21f3b5f3aa6479ea682c231dcd5a008"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="rf66fc13c3eeb4f0685d4958da6461cca"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a4316473a7e624205ae3a451977a4746e"><a name="a4316473a7e624205ae3a451977a4746e"></a><a name="a4316473a7e624205ae3a451977a4746e"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.509999999999998%" headers="mcps1.2.4.1.2 "><p id="a1ad8e2f64d8e41ff9589587ede449b12"><a name="a1ad8e2f64d8e41ff9589587ede449b12"></a><a name="a1ad8e2f64d8e41ff9589587ede449b12"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="a8c49f739a5894becb12789cc49db934f"><a name="a8c49f739a5894becb12789cc49db934f"></a><a name="a8c49f739a5894becb12789cc49db934f"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{ 

  "kind": "SecretList",
  "apiVersion": "v1",
  "metadata": {
    "selfLink": "/api/v1/secrets",
    "resourceVersion": "1810858"
  },
  "items": [
    {
      "metadata": {
        "name": "default-token-nlckn",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/secrets/default-token-nlckn",
        "uid": "23070e11-1425-11e7-96c7-fa163ec08232",
        "resourceVersion": "30",
        "creationTimestamp": "2017-03-29T02:12:19Z",
        "annotations": {
          "kubernetes.io/service-account.name": "default",
          "kubernetes.io/service-account.uid": "2303e59b-1425-11e7-96c7-fa163ec08232"
        }
      },
      "data": {
        "ca.crt": "",
        "namespace": "ZGVmYXVsdA==",
        "token": ""
      },
      "type": "kubernetes.io/service-account-token"
    },
    {
      "metadata": {
        "name": "myregistry",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/secrets/myregistry",
        "uid": "a34ed5e4-1427-11e7-96c7-fa163ec08232",
        "resourceVersion": "1243",
        "creationTimestamp": "2017-03-29T02:30:13Z"
      },
      "data": {
        ".dockercfg": ""
      },
      "type": "kubernetes.io/hwdockercfg"
    },
    {
      "metadata": {
        "name": "paas.elb",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/secrets/paas.elb",
        "uid": "a34df6f3-1427-11e7-96c7-fa163ec08232",
        "resourceVersion": "1242",
        "creationTimestamp": "2017-03-29T02:30:13Z"
      },
      "data": {
        "access.key": "",
        "secret.key": ""
      },
      "type": "Opaque"
    },
    {
      "metadata": {
        "name": "default-token-cptf1",
        "namespace": "kube-system",
        "selfLink": "/api/v1/namespaces/kube-system/secrets/default-token-cptf1",
        "uid": "23090a90-1425-11e7-96c7-fa163ec08232",
        "resourceVersion": "32",
        "creationTimestamp": "2017-03-29T02:12:19Z",
        "annotations": {
          "kubernetes.io/service-account.name": "default",
          "kubernetes.io/service-account.uid": "23046012-1425-11e7-96c7-fa163ec08232"
        }
      },
      "data": {
        "ca.crt": "",
        "namespace": "a3ViZS1zeXN0ZW0=",
        "token": ""
      },
      "type": "kubernetes.io/service-account-token"
    },
    {
      "metadata": {
        "name": "token-kube-proxy",
        "namespace": "kube-system",
        "selfLink": "/api/v1/namespaces/kube-system/secrets/token-kube-proxy",
        "uid": "23a5f659-1425-11e7-96c7-fa163ec08232",
        "resourceVersion": "34",
        "creationTimestamp": "2017-03-29T02:12:20Z"
      },
      "data": {
        "kubeconfig": "YXBpVmVyc2lvbjogdjEKa2luZDoK"
      },
      "type": "Opaque"
    },
    {
      "metadata": {
        "name": "token-kubelet",
        "namespace": "kube-system",
        "selfLink": "/api/v1/namespaces/kube-system/secrets/token-kubelet",
        "uid": "23b9cf39-1425-11e7-96c7-fa163ec08232",
        "resourceVersion": "36",
        "creationTimestamp": "2017-03-29T02:12:20Z"
      },
      "data": {
        "kubeconfig": ""
      },
      "type": "Opaque"
    },
    {
      "metadata": {
        "name": "token-system-controller-manager",
        "namespace": "kube-system",
        "selfLink": "/api/v1/namespaces/kube-system/secrets/token-system-controller-manager",
        "uid": "23dc783d-1425-11e7-96c7-fa163ec08232",
        "resourceVersion": "39",
        "creationTimestamp": "2017-03-29T02:12:20Z"
      },
      "data": {
        "kubeconfig": ""
      },
      "type": "Opaque"
    },
    {
      "metadata": {
        "name": "token-system-dns",
        "namespace": "kube-system",
        "selfLink": "/api/v1/namespaces/kube-system/secrets/token-system-dns",
        "uid": "23d31dfb-1425-11e7-96c7-fa163ec08232",
        "resourceVersion": "38",
        "creationTimestamp": "2017-03-29T02:12:20Z"
      },
      "data": {
        "kubeconfig": ""
      },
      "type": "Opaque"
    },
    {
      "metadata": {
        "name": "token-system-scheduler",
        "namespace": "kube-system",
        "selfLink": "/api/v1/namespaces/kube-system/secrets/token-system-scheduler",
        "uid": "23c18f3e-1425-11e7-96c7-fa163ec08232",
        "resourceVersion": "37",
        "creationTimestamp": "2017-03-29T02:12:20Z"
      },
      "data": {
        "kubeconfig": ""
      },
      "type": "Opaque"
    }
  ]
 }
```

## 状态码<a name="s73fc339f63a04c6dbf30ccc63e253dc1"></a>

[表4](#tc533cff3bbcf4a7294abd207ad6f1bd9)描述API的状态码。

**表 4**  状态码

<a name="tc533cff3bbcf4a7294abd207ad6f1bd9"></a>
<table><thead align="left"><tr id="r56fe0dd762374f10ad96fcbf2c46fb47"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p4320871621041"><a name="p4320871621041"></a><a name="p4320871621041"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1024509721041"><a name="p1024509721041"></a><a name="p1024509721041"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rbc196dfda0394a6aa9cece8f2ba51036"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="adfb77bdfe1cd4d169fbc3328b808e52f"><a name="adfb77bdfe1cd4d169fbc3328b808e52f"></a><a name="adfb77bdfe1cd4d169fbc3328b808e52f"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614896_p815332217101"><a name="zh-cn_topic_0079614896_p815332217101"></a><a name="zh-cn_topic_0079614896_p815332217101"></a>操作成功，返回一组secret资源对象。</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

