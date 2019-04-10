# 列出集群下的Secret<a name="cce_02_0048"></a>

## 功能介绍<a name="s9832be8e9a554244a817a938beac98de"></a>

该API用于列出集群中的所有Secret对象。

## URI<a name="s352ffae11a4646bc94188db7e8bfcf91"></a>

GET /api/v1/secrets

[表1](#t9d6c44bf236d4ba8ae211af56abe2ac4)  描述该API的参数。

**表 1**  参数描述

<a name="t9d6c44bf236d4ba8ae211af56abe2ac4"></a>
<table><thead align="left"><tr id="ra01cd44e9248456984c7b05744a542d2"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="a96d6908f2267431abce3d2a7e5d56172"><a name="a96d6908f2267431abce3d2a7e5d56172"></a><a name="a96d6908f2267431abce3d2a7e5d56172"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.1%" id="mcps1.2.4.1.2"><p id="p4741088521041"><a name="p4741088521041"></a><a name="p4741088521041"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="62.839999999999996%" id="mcps1.2.4.1.3"><p id="p1507646821041"><a name="p1507646821041"></a><a name="p1507646821041"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r06cec346727846aa8769b63e84c209aa"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a823020e5b2774684831808755998f5e7"><a name="a823020e5b2774684831808755998f5e7"></a><a name="a823020e5b2774684831808755998f5e7"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="ad8890017a88049cbb0860d5db322cf03"><a name="ad8890017a88049cbb0860d5db322cf03"></a><a name="ad8890017a88049cbb0860d5db322cf03"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p49874218"><a name="p49874218"></a><a name="p49874218"></a>根据资源对象的field字段进行筛选，不设置该参数时默认选择所有资源对象。</p>
</td>
</tr>
<tr id="rc5e5eac50e604dbbac714f1bb81fb3a7"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614976_p72459579277"><a name="zh-cn_topic_0079614976_p72459579277"></a><a name="zh-cn_topic_0079614976_p72459579277"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a704fd3940037413d9a5fb1c10ef71ecd"><a name="a704fd3940037413d9a5fb1c10ef71ecd"></a><a name="a704fd3940037413d9a5fb1c10ef71ecd"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a163adfe9b2884ce09f91ddc74ec8c32a"><a name="a163adfe9b2884ce09f91ddc74ec8c32a"></a><a name="a163adfe9b2884ce09f91ddc74ec8c32a"></a>设置为true后，未初始化完成的资源也会包含在删除列表里。</p>
</td>
</tr>
<tr id="r7bb76dafa3214ee8b0066bb757ceee67"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a4ccfb6aa30a241649698ef9e3368cc36"><a name="a4ccfb6aa30a241649698ef9e3368cc36"></a><a name="a4ccfb6aa30a241649698ef9e3368cc36"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a1f0a86a7482e46979a60ebcd44bd1bd1"><a name="a1f0a86a7482e46979a60ebcd44bd1bd1"></a><a name="a1f0a86a7482e46979a60ebcd44bd1bd1"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p1930564715251"><a name="p1930564715251"></a><a name="p1930564715251"></a>根据资源对象的label字段进行筛选，不设置该参数时默认选择所有资源对象。</p>
</td>
</tr>
<tr id="r2f09d591ec484cf0b9fc9122016bf368"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a161d849263f34836882938f929cf02c5"><a name="a161d849263f34836882938f929cf02c5"></a><a name="a161d849263f34836882938f929cf02c5"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="ad6d37bbcf4c54051af64e95f6affc2a8"><a name="ad6d37bbcf4c54051af64e95f6affc2a8"></a><a name="ad6d37bbcf4c54051af64e95f6affc2a8"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p28675043"><a name="p28675043"></a><a name="p28675043"></a>设置为true后，会打印漂亮的输出结果。</p>
</td>
</tr>
<tr id="rbd6881ebadd34e48b2585f136af20ae6"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a421ca43b53834bc5a0c4ed37f9c9dd0d"><a name="a421ca43b53834bc5a0c4ed37f9c9dd0d"></a><a name="a421ca43b53834bc5a0c4ed37f9c9dd0d"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a87ef05ba3b5d4377916f8f72d96f5d57"><a name="a87ef05ba3b5d4377916f8f72d96f5d57"></a><a name="a87ef05ba3b5d4377916f8f72d96f5d57"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="aec20c0bba55141c0b8e5adba10582195"><a name="aec20c0bba55141c0b8e5adba10582195"></a><a name="aec20c0bba55141c0b8e5adba10582195"></a><span id="ph14746102416396"><a name="ph14746102416396"></a><a name="ph14746102416396"></a>ResourceVersion表示该资源对象内部版本。</span></p>
</td>
</tr>
<tr id="reddd9e93be244077809d70e6d8caaea0"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="ac6bb3e4dc0e547f3abc7c0442816766c"><a name="ac6bb3e4dc0e547f3abc7c0442816766c"></a><a name="ac6bb3e4dc0e547f3abc7c0442816766c"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a0a561bf1af184b5ca0aad59209273646"><a name="a0a561bf1af184b5ca0aad59209273646"></a><a name="a0a561bf1af184b5ca0aad59209273646"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p2133200"><a name="p2133200"></a><a name="p2133200"></a>表示调用list/watch的超时时间。</p>
</td>
</tr>
<tr id="r8ac3f8669aa745c8bb462f8948d15e89"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a85185a67f78f421baf4a7794f0965edd"><a name="a85185a67f78f421baf4a7794f0965edd"></a><a name="a85185a67f78f421baf4a7794f0965edd"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a92aa84d4b2234088824460bc295a3247"><a name="a92aa84d4b2234088824460bc295a3247"></a><a name="a92aa84d4b2234088824460bc295a3247"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a6784a1d0def944f0b380938fa95362d9"><a name="a6784a1d0def944f0b380938fa95362d9"></a><a name="a6784a1d0def944f0b380938fa95362d9"></a><span id="ph10314174718456"><a name="ph10314174718456"></a><a name="ph10314174718456"></a>监视指定资源的更改，并将添加、更新和删除通知的流返回。</span></p>
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
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p6302327521041"><a name="p6302327521041"></a><a name="p6302327521041"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p461161221041"><a name="p461161221041"></a><a name="p461161221041"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r09bc2a71ba2842eea07332a417a05415"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="af1da3c49d5074f65849feccd1b820b08"><a name="af1da3c49d5074f65849feccd1b820b08"></a><a name="af1da3c49d5074f65849feccd1b820b08"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="a3fe2d3a801434d538e7394c3b626d6c7"><a name="a3fe2d3a801434d538e7394c3b626d6c7"></a><a name="a3fe2d3a801434d538e7394c3b626d6c7"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="aa56cd02ff7f54177b717d0f5bb3b3a15"><a name="aa56cd02ff7f54177b717d0f5bb3b3a15"></a><a name="aa56cd02ff7f54177b717d0f5bb3b3a15"></a>表示API版本。</p>
</td>
</tr>
<tr id="r3740d824b5d7426c9d727a9209c819d9"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="a095d27eaa891425b8041e3d1a4d661a2"><a name="a095d27eaa891425b8041e3d1a4d661a2"></a><a name="a095d27eaa891425b8041e3d1a4d661a2"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="acd8daf6d292a406fa265fef7019f20da"><a name="acd8daf6d292a406fa265fef7019f20da"></a><a name="acd8daf6d292a406fa265fef7019f20da"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p30014175"><a name="zh-cn_topic_0079615047_p30014175"></a><a name="zh-cn_topic_0079615047_p30014175"></a>表示API类型。</p>
</td>
</tr>
<tr id="r02f0cc1a6cac4a108b0ef17139973e44"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="a34069eae0183436bbef773db3c40243f"><a name="a34069eae0183436bbef773db3c40243f"></a><a name="a34069eae0183436bbef773db3c40243f"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="a57d16aa7ed944bc58d7b1d5ae2148b46"><a name="a57d16aa7ed944bc58d7b1d5ae2148b46"></a><a name="a57d16aa7ed944bc58d7b1d5ae2148b46"></a><a href="#t6ff895f91da8440685e472dac63f0547">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="addcedf6afc794771a6b4f775844b2b27"><a name="addcedf6afc794771a6b4f775844b2b27"></a><a name="addcedf6afc794771a6b4f775844b2b27"></a><span id="ph128511352184714"><a name="ph128511352184714"></a><a name="ph128511352184714"></a>-</span></p>
</td>
</tr>
<tr id="r25f369b6a3f347c3b3a65563cdd6bb07"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="a07efeb8bbbe24f03b6d9f8bac65dab91"><a name="a07efeb8bbbe24f03b6d9f8bac65dab91"></a><a name="a07efeb8bbbe24f03b6d9f8bac65dab91"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="ada6c495fd25b43428dcb7540584913fa"><a name="ada6c495fd25b43428dcb7540584913fa"></a><a name="ada6c495fd25b43428dcb7540584913fa"></a><a href="创建Secret.md#s08d56e5f4e57452da0a49400212440a4">响应消息</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="ad7d02c90609f4eb0ab27908e5cb543cf"><a name="ad7d02c90609f4eb0ab27908e5cb543cf"></a><a name="ad7d02c90609f4eb0ab27908e5cb543cf"></a><span id="ph17951125418478"><a name="ph17951125418478"></a><a name="ph17951125418478"></a>-</span></p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="t6ff895f91da8440685e472dac63f0547"></a>
<table><thead align="left"><tr id="r86a4582b6de74880895c7e0fdf0d65d8"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="af30c046d5fd845e289825e6a4e7d1995"><a name="af30c046d5fd845e289825e6a4e7d1995"></a><a name="af30c046d5fd845e289825e6a4e7d1995"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.509999999999998%" id="mcps1.2.4.1.2"><p id="p5588517721041"><a name="p5588517721041"></a><a name="p5588517721041"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.43%" id="mcps1.2.4.1.3"><p id="p3040545621041"><a name="p3040545621041"></a><a name="p3040545621041"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r3f97e7c5adb7499b9f8e4153f1cfcff5"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614976_p556806144647"><a name="zh-cn_topic_0079614976_p556806144647"></a><a name="zh-cn_topic_0079614976_p556806144647"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.509999999999998%" headers="mcps1.2.4.1.2 "><p id="a8b64354278c548a4aa8c5d7dc3650953"><a name="a8b64354278c548a4aa8c5d7dc3650953"></a><a name="a8b64354278c548a4aa8c5d7dc3650953"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="a308d721c66be49d380e37fb00f8ef4a4"><a name="a308d721c66be49d380e37fb00f8ef4a4"></a><a name="a308d721c66be49d380e37fb00f8ef4a4"></a>ResourceVersion表示该资源对象内部版本，可以用来优化并发性能和监视资源变化，系统内部使用，只读项。</p>
</td>
</tr>
<tr id="rf66fc13c3eeb4f0685d4958da6461cca"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a4316473a7e624205ae3a451977a4746e"><a name="a4316473a7e624205ae3a451977a4746e"></a><a name="a4316473a7e624205ae3a451977a4746e"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.509999999999998%" headers="mcps1.2.4.1.2 "><p id="a1ad8e2f64d8e41ff9589587ede449b12"><a name="a1ad8e2f64d8e41ff9589587ede449b12"></a><a name="a1ad8e2f64d8e41ff9589587ede449b12"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="a818ff19e70cd4d8c9d4a7acea7bc59fb"><a name="a818ff19e70cd4d8c9d4a7acea7bc59fb"></a><a name="a818ff19e70cd4d8c9d4a7acea7bc59fb"></a>SelfLink 是该资源对象的 URL。 系统内部使用，只读项。</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{ 
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
        "ca.crt": "
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

