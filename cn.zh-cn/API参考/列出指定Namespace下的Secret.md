# 列出指定Namespace下的Secret<a name="cce_02_0047"></a>

## 功能介绍<a name="s4f273007dbdb496489d59609177ab2ca"></a>

该API用于在指定的Namespace下列出Secret对象。

## URI<a name="s67ffbd94de334af289f07009ba507b57"></a>

GET /api/v1/namespaces/\{namespace\}/secrets

[表1](#t11883f44ee8e465e93615fe19d7d4f59)  描述该API的参数。

**表 1**  参数描述

<a name="t11883f44ee8e465e93615fe19d7d4f59"></a>
<table><thead align="left"><tr id="rad26db413d7d42108494dad8eb868789"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="a43f8f66ef278415a82e2ca2a7084290b"><a name="a43f8f66ef278415a82e2ca2a7084290b"></a><a name="a43f8f66ef278415a82e2ca2a7084290b"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.1%" id="mcps1.2.4.1.2"><p id="p27344536201625"><a name="p27344536201625"></a><a name="p27344536201625"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="62.839999999999996%" id="mcps1.2.4.1.3"><p id="p314980201625"><a name="p314980201625"></a><a name="p314980201625"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rc373bff7df694eaa9a1911f3ee9d056e"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a8e10fa81959d42408405533bbecc2298"><a name="a8e10fa81959d42408405533bbecc2298"></a><a name="a8e10fa81959d42408405533bbecc2298"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="ab3ab30f6f38a44cba2c77f92496078f6"><a name="ab3ab30f6f38a44cba2c77f92496078f6"></a><a name="ab3ab30f6f38a44cba2c77f92496078f6"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p658610593411"><a name="p658610593411"></a><a name="p658610593411"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。</p>
</td>
</tr>
<tr id="r0f899f4f8ea54f2fa893c3e0cf87630c"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a59bb22f28087453ca02324478ffbeacb"><a name="a59bb22f28087453ca02324478ffbeacb"></a><a name="a59bb22f28087453ca02324478ffbeacb"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a2efc413ffd07407c95e92b4e6d9a897e"><a name="a2efc413ffd07407c95e92b4e6d9a897e"></a><a name="a2efc413ffd07407c95e92b4e6d9a897e"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p28675043"><a name="p28675043"></a><a name="p28675043"></a>设置为true后，会打印漂亮的输出结果。</p>
</td>
</tr>
<tr id="r7e813ae72466493da1ae3476c4217a9a"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="aa9c64e4ab78b4acd88c66b1e801ca35a"><a name="aa9c64e4ab78b4acd88c66b1e801ca35a"></a><a name="aa9c64e4ab78b4acd88c66b1e801ca35a"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a0d4037ffde7e416fa83b9299a1a4a87a"><a name="a0d4037ffde7e416fa83b9299a1a4a87a"></a><a name="a0d4037ffde7e416fa83b9299a1a4a87a"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p49874218"><a name="p49874218"></a><a name="p49874218"></a>根据资源对象的field字段进行筛选，不设置该参数时默认选择所有资源对象。</p>
</td>
</tr>
<tr id="r3a7c2bd394cc4b38a62660d120d35a61"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614896_p628523492519"><a name="zh-cn_topic_0079614896_p628523492519"></a><a name="zh-cn_topic_0079614896_p628523492519"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="aab3047b805ad4854aeefd8db47cf4d99"><a name="aab3047b805ad4854aeefd8db47cf4d99"></a><a name="aab3047b805ad4854aeefd8db47cf4d99"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a163adfe9b2884ce09f91ddc74ec8c32a"><a name="a163adfe9b2884ce09f91ddc74ec8c32a"></a><a name="a163adfe9b2884ce09f91ddc74ec8c32a"></a><span id="ph984104618246"><a name="ph984104618246"></a><a name="ph984104618246"></a>设置为true后，未初始化的资源也会包含在删除列表里。</span></p>
</td>
</tr>
<tr id="r3e03b3ed19724be4b39fe666ed7011f5"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a43a73c63fa9546e080760e7e88d5ecf2"><a name="a43a73c63fa9546e080760e7e88d5ecf2"></a><a name="a43a73c63fa9546e080760e7e88d5ecf2"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="abe9b1918c28c44a09ba2c13b3fdfac83"><a name="abe9b1918c28c44a09ba2c13b3fdfac83"></a><a name="abe9b1918c28c44a09ba2c13b3fdfac83"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p1930564715251"><a name="p1930564715251"></a><a name="p1930564715251"></a>根据资源对象的label字段进行筛选，不设置该参数时默认选择所有资源对象。</p>
</td>
</tr>
<tr id="rb24b664f262244d8817205f6426fc18d"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="ab92f7219f16340be9ae9a42c2702afc7"><a name="ab92f7219f16340be9ae9a42c2702afc7"></a><a name="ab92f7219f16340be9ae9a42c2702afc7"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a09235cc3ced749dcbb2940e0d05fb814"><a name="a09235cc3ced749dcbb2940e0d05fb814"></a><a name="a09235cc3ced749dcbb2940e0d05fb814"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="a5267faf2beb54f448afd8d0566d2e815"><a name="a5267faf2beb54f448afd8d0566d2e815"></a><a name="a5267faf2beb54f448afd8d0566d2e815"></a><span id="ph14746102416396"><a name="ph14746102416396"></a><a name="ph14746102416396"></a>ResourceVersion表示该资源对象内部版本。</span></p>
</td>
</tr>
<tr id="r905443bc04e941289138dc2173e87bc7"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="acce97a3e928a45deb3f0d61bcd998746"><a name="acce97a3e928a45deb3f0d61bcd998746"></a><a name="acce97a3e928a45deb3f0d61bcd998746"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a4b9e930dbbf940d297016f43b9858f87"><a name="a4b9e930dbbf940d297016f43b9858f87"></a><a name="a4b9e930dbbf940d297016f43b9858f87"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p2133200"><a name="p2133200"></a><a name="p2133200"></a>表示调用list/watch的超时时间。</p>
</td>
</tr>
<tr id="r76de6a58993848c7953e1d93a68eb6ac"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="ad538da99548e4303a160e21d889620a2"><a name="ad538da99548e4303a160e21d889620a2"></a><a name="ad538da99548e4303a160e21d889620a2"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="15.1%" headers="mcps1.2.4.1.2 "><p id="a064e1d3de451400dbb80b180df98254e"><a name="a064e1d3de451400dbb80b180df98254e"></a><a name="a064e1d3de451400dbb80b180df98254e"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="62.839999999999996%" headers="mcps1.2.4.1.3 "><p id="p176837905310"><a name="p176837905310"></a><a name="p176837905310"></a>监视指定资源的更改，并将添加、更新和删除通知的流返回。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s55df5b092abd4897959f99e7ce493828"></a>

N/A

## 响应消息<a name="scf37ee415d294329ad8442bd193b729e"></a>

**响应参数：**

**表 2**  响应参数

<a name="tc3c49e5e5dee441fb7a7f014a4c81900"></a>
<table><thead align="left"><tr id="re436b46465e04931b74b88d37a1b9677"><th class="cellrowborder" valign="top" width="25.25%" id="mcps1.2.4.1.1"><p id="a28a2f98442b6474da3b695fefeb1cf3d"><a name="a28a2f98442b6474da3b695fefeb1cf3d"></a><a name="a28a2f98442b6474da3b695fefeb1cf3d"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.320000000000004%" id="mcps1.2.4.1.2"><p id="p6199478201625"><a name="p6199478201625"></a><a name="p6199478201625"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.43%" id="mcps1.2.4.1.3"><p id="p32395734201625"><a name="p32395734201625"></a><a name="p32395734201625"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rbba16776ee81419da8a953a80bc7207d"><td class="cellrowborder" valign="top" width="25.25%" headers="mcps1.2.4.1.1 "><p id="af9fabcdd1e8443469be72eb8d614e235"><a name="af9fabcdd1e8443469be72eb8d614e235"></a><a name="af9fabcdd1e8443469be72eb8d614e235"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.320000000000004%" headers="mcps1.2.4.1.2 "><p id="a8602a93578634e13b9187d318ed342ff"><a name="a8602a93578634e13b9187d318ed342ff"></a><a name="a8602a93578634e13b9187d318ed342ff"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="aa56cd02ff7f54177b717d0f5bb3b3a15"><a name="aa56cd02ff7f54177b717d0f5bb3b3a15"></a><a name="aa56cd02ff7f54177b717d0f5bb3b3a15"></a><span id="ph717617234412"><a name="ph717617234412"></a><a name="ph717617234412"></a>表示API版本。</span></p>
</td>
</tr>
<tr id="rfa10b724cdbc4eef815c3d3d64260ede"><td class="cellrowborder" valign="top" width="25.25%" headers="mcps1.2.4.1.1 "><p id="a7192cf844ba34d6b912e4aaf50781fd9"><a name="a7192cf844ba34d6b912e4aaf50781fd9"></a><a name="a7192cf844ba34d6b912e4aaf50781fd9"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.320000000000004%" headers="mcps1.2.4.1.2 "><p id="abf2d542e2a384b5383b8357d555d1bed"><a name="abf2d542e2a384b5383b8357d555d1bed"></a><a name="abf2d542e2a384b5383b8357d555d1bed"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p30014175"><a name="zh-cn_topic_0079615047_p30014175"></a><a name="zh-cn_topic_0079615047_p30014175"></a>表示API类型。</p>
</td>
</tr>
<tr id="r20a89a0b59b24dfc8956b125482f1421"><td class="cellrowborder" valign="top" width="25.25%" headers="mcps1.2.4.1.1 "><p id="af34c3d5c8cfb4eb4890ba46998f81bce"><a name="af34c3d5c8cfb4eb4890ba46998f81bce"></a><a name="af34c3d5c8cfb4eb4890ba46998f81bce"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.320000000000004%" headers="mcps1.2.4.1.2 "><p id="a7af91f6187e54c6ea63970053896337e"><a name="a7af91f6187e54c6ea63970053896337e"></a><a name="a7af91f6187e54c6ea63970053896337e"></a><a href="#tff9df0051888403eb0196353f3feb3b6">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="ad95d3dbaaae4478a8cd5e6242f1a1331"><a name="ad95d3dbaaae4478a8cd5e6242f1a1331"></a><a name="ad95d3dbaaae4478a8cd5e6242f1a1331"></a><span id="ph1432974819413"><a name="ph1432974819413"></a><a name="ph1432974819413"></a>-</span></p>
</td>
</tr>
<tr id="r341420eda4f94280a331ac7a3cfc6215"><td class="cellrowborder" valign="top" width="25.25%" headers="mcps1.2.4.1.1 "><p id="a289ba9b3f09f4b6dbe5490422a339709"><a name="a289ba9b3f09f4b6dbe5490422a339709"></a><a name="a289ba9b3f09f4b6dbe5490422a339709"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30.320000000000004%" headers="mcps1.2.4.1.2 "><p id="abce9149f44ba43009cc66ac939990e96"><a name="abce9149f44ba43009cc66ac939990e96"></a><a name="abce9149f44ba43009cc66ac939990e96"></a><a href="创建Secret.md#zh-cn_topic_0079614900_ref458786458">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="a87a75aac697743dfb099e359013633d9"><a name="a87a75aac697743dfb099e359013633d9"></a><a name="a87a75aac697743dfb099e359013633d9"></a><span id="ph13603175894114"><a name="ph13603175894114"></a><a name="ph13603175894114"></a>-</span></p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="tff9df0051888403eb0196353f3feb3b6"></a>
<table><thead align="left"><tr id="r12daa9f46eeb4a5c83aea6cda1f4e4c5"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="a84714f3753cc47eeb3d1a6df8ce5dc4b"><a name="a84714f3753cc47eeb3d1a6df8ce5dc4b"></a><a name="a84714f3753cc47eeb3d1a6df8ce5dc4b"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.509999999999998%" id="mcps1.2.4.1.2"><p id="p19301202201625"><a name="p19301202201625"></a><a name="p19301202201625"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.43%" id="mcps1.2.4.1.3"><p id="p19893500201625"><a name="p19893500201625"></a><a name="p19893500201625"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r85b01f2c7d1d4a48b955f035e004a0b7"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a3e5016f62da04055871fa7dc628f69c1"><a name="a3e5016f62da04055871fa7dc628f69c1"></a><a name="a3e5016f62da04055871fa7dc628f69c1"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.509999999999998%" headers="mcps1.2.4.1.2 "><p id="a25845db8f0d44529ab7a01fc6d5403be"><a name="a25845db8f0d44529ab7a01fc6d5403be"></a><a name="a25845db8f0d44529ab7a01fc6d5403be"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="a308d721c66be49d380e37fb00f8ef4a4"><a name="a308d721c66be49d380e37fb00f8ef4a4"></a><a name="a308d721c66be49d380e37fb00f8ef4a4"></a><span id="ph516213221259"><a name="ph516213221259"></a><a name="ph516213221259"></a>ResourceVersion表示该资源对象内部版本</span><span id="ph188361713112614"><a name="ph188361713112614"></a><a name="ph188361713112614"></a>，可以用来优化并发性能和监视资源变化，</span><span id="ph173071947202820"><a name="ph173071947202820"></a><a name="ph173071947202820"></a>系统内部使用，只读项</span><span id="ph577585316285"><a name="ph577585316285"></a><a name="ph577585316285"></a>。</span></p>
</td>
</tr>
<tr id="r7353b3d91e5b42338bc6ddbfa8d7f715"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a0b0e25db45a44218be3e42b910afdd08"><a name="a0b0e25db45a44218be3e42b910afdd08"></a><a name="a0b0e25db45a44218be3e42b910afdd08"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.509999999999998%" headers="mcps1.2.4.1.2 "><p id="a4f1ceb0744f04795b0879ccc02fca6a9"><a name="a4f1ceb0744f04795b0879ccc02fca6a9"></a><a name="a4f1ceb0744f04795b0879ccc02fca6a9"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.43%" headers="mcps1.2.4.1.3 "><p id="a818ff19e70cd4d8c9d4a7acea7bc59fb"><a name="a818ff19e70cd4d8c9d4a7acea7bc59fb"></a><a name="a818ff19e70cd4d8c9d4a7acea7bc59fb"></a><span id="ph12354153614421"><a name="ph12354153614421"></a><a name="ph12354153614421"></a>SelfLink 是该资源对象的 URL。 系统内部使用，只读项。.</span></p>
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
        "selfLink": "/api/v1/namespaces/default/secrets",
        "resourceVersion": "1810323"
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
        }
    ]
}

 
```

## 状态码<a name="s91a3be3fa42649b9bc4a65bfa7366093"></a>

[表4](#t6cee8759205747faa51f286e53dbed24)描述API的状态码。

**表 4**  状态码

<a name="t6cee8759205747faa51f286e53dbed24"></a>
<table><thead align="left"><tr id="r4c11b2d5506d46358b44888e0906952a"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p16238293201625"><a name="p16238293201625"></a><a name="p16238293201625"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p40233369201625"><a name="p40233369201625"></a><a name="p40233369201625"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r5ad486edb0db460294cdd49a495f30a6"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="a16bfcc1de96142f6a2f458546b8722ed"><a name="a16bfcc1de96142f6a2f458546b8722ed"></a><a name="a16bfcc1de96142f6a2f458546b8722ed"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614896_p815332217101"><a name="zh-cn_topic_0079614896_p815332217101"></a><a name="zh-cn_topic_0079614896_p815332217101"></a><span id="ph08511419154315"><a name="ph08511419154315"></a><a name="ph08511419154315"></a>操作成功，返回secret资源对象</span><span id="ph76249463430"><a name="ph76249463430"></a><a name="ph76249463430"></a>。</span></p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

