# 创建PersistentVolumeClaim<a name="cce_02_0067"></a>

## 功能介绍<a name="s0a28adc85c784085a2d82fe65fbfc112"></a>

该API用于在指定的Namespace下创建PersistentVolumeClaim。

>![](public_sys-resources/icon-note.gif) **说明：**   
>使用已有的EVS创建PVC时，请参照CCE用户指南中使用云硬盘存储章节的[使用已有的EVS创建PVC](https://support.huaweicloud.com/usermanual-cce/cce_01_0044.html#section8)中**步骤5**为集群增加关联的metadata，以确保在删除节点或集群时避免删除已挂载的静态PV关联的EVS盘。若不执行上述操作或创建静态PV/PVC时没有执行过上述操作，请务必确保删除节点前，提前将静态PV关联的云硬盘从节点上卸载。  

## URI<a name="sdad79289da6f40bfb1b0726f426f9f1f"></a>

POST /api/v1/namespaces/\{namespace\}/persistentvolumeclaims

[表1](#tbb39505880dd47b7952941b52626bf77)  描述该API的参数。

**表 1**  参数描述

<a name="tbb39505880dd47b7952941b52626bf77"></a>
<table><thead align="left"><tr id="rf1f3422b7e214676bd6220a3089a0b6c"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="a301ecfa05ce3484b872abcfe0f9a0bd9"><a name="a301ecfa05ce3484b872abcfe0f9a0bd9"></a><a name="a301ecfa05ce3484b872abcfe0f9a0bd9"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.36%" id="mcps1.2.4.1.2"><p id="p1135171915172"><a name="p1135171915172"></a><a name="p1135171915172"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.58%" id="mcps1.2.4.1.3"><p id="p2136191911171"><a name="p2136191911171"></a><a name="p2136191911171"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="reaebe094596f4e358be751cc58bfbc85"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="a3a05d303c85e40d58e46a1b7663edd92"><a name="a3a05d303c85e40d58e46a1b7663edd92"></a><a name="a3a05d303c85e40d58e46a1b7663edd92"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.36%" headers="mcps1.2.4.1.2 "><p id="ac987d6ec8853486398964e4759c35f02"><a name="ac987d6ec8853486398964e4759c35f02"></a><a name="ac987d6ec8853486398964e4759c35f02"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.58%" headers="mcps1.2.4.1.3 "><p id="a19a056d9e1c94f59a442258ba4fbd575"><a name="a19a056d9e1c94f59a442258ba4fbd575"></a><a name="a19a056d9e1c94f59a442258ba4fbd575"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="rdf1dc9140a3b4b3c92cc8f904603ea5b"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="ab1a2800ea10145d7bbb8d4a1d91b26c3"><a name="ab1a2800ea10145d7bbb8d4a1d91b26c3"></a><a name="ab1a2800ea10145d7bbb8d4a1d91b26c3"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.36%" headers="mcps1.2.4.1.2 "><p id="affc15999723c44ecabaa9a50d861b5bb"><a name="affc15999723c44ecabaa9a50d861b5bb"></a><a name="affc15999723c44ecabaa9a50d861b5bb"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.58%" headers="mcps1.2.4.1.3 "><p id="ad893e4b8017643c4b53c96cdf6e47507"><a name="ad893e4b8017643c4b53c96cdf6e47507"></a><a name="ad893e4b8017643c4b53c96cdf6e47507"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sa85d89666a35466388180b7b77d8c772"></a>

**请求参数：**

**表 2**  请求参数

<a name="t8268aeafde034542ab17a36c7fca65c3"></a>
<table><thead align="left"><tr id="r599834d119144e0c86c3923a3a2398b9"><th class="cellrowborder" valign="top" width="19.92%" id="mcps1.2.5.1.1"><p id="a52fb3ae7f42e4fdeb05163f9445c1270"><a name="a52fb3ae7f42e4fdeb05163f9445c1270"></a><a name="a52fb3ae7f42e4fdeb05163f9445c1270"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.42%" id="mcps1.2.5.1.2"><p id="p1215011901714"><a name="p1215011901714"></a><a name="p1215011901714"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.800000000000004%" id="mcps1.2.5.1.3"><p id="p515141913179"><a name="p515141913179"></a><a name="p515141913179"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.86000000000001%" id="mcps1.2.5.1.4"><p id="p2015211193174"><a name="p2015211193174"></a><a name="p2015211193174"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r3a5b68ec0f6e4beab8243a4ffd20f6b4"><td class="cellrowborder" valign="top" width="19.92%" headers="mcps1.2.5.1.1 "><p id="a983142d00f134aa99903dca33a51485e"><a name="a983142d00f134aa99903dca33a51485e"></a><a name="a983142d00f134aa99903dca33a51485e"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="18.42%" headers="mcps1.2.5.1.2 "><p id="a298da45e279f44ce9b0756789d705cd2"><a name="a298da45e279f44ce9b0756789d705cd2"></a><a name="a298da45e279f44ce9b0756789d705cd2"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.800000000000004%" headers="mcps1.2.5.1.3 "><p id="aa3045fc4cd2e41628d4b71fcb5c0cd5b"><a name="aa3045fc4cd2e41628d4b71fcb5c0cd5b"></a><a name="aa3045fc4cd2e41628d4b71fcb5c0cd5b"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.86000000000001%" headers="mcps1.2.5.1.4 "><p id="a471b7a48977643fea09acc6cb7343a43"><a name="a471b7a48977643fea09acc6cb7343a43"></a><a name="a471b7a48977643fea09acc6cb7343a43"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="r36f3532e5dfe42009ef6f54f94fa206f"><td class="cellrowborder" valign="top" width="19.92%" headers="mcps1.2.5.1.1 "><p id="aad2063ba2fa54066abe33d84ad236fe9"><a name="aad2063ba2fa54066abe33d84ad236fe9"></a><a name="aad2063ba2fa54066abe33d84ad236fe9"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="18.42%" headers="mcps1.2.5.1.2 "><p id="af36627fefdbd41f88d1693fb84c94add"><a name="af36627fefdbd41f88d1693fb84c94add"></a><a name="af36627fefdbd41f88d1693fb84c94add"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.800000000000004%" headers="mcps1.2.5.1.3 "><p id="aef4460a21022474680220bba0abfdd70"><a name="aef4460a21022474680220bba0abfdd70"></a><a name="aef4460a21022474680220bba0abfdd70"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.86000000000001%" headers="mcps1.2.5.1.4 "><p id="a8de0fd10023f4d69a1c118c0ef439c0f"><a name="a8de0fd10023f4d69a1c118c0ef439c0f"></a><a name="a8de0fd10023f4d69a1c118c0ef439c0f"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="re4d41fbe88c04c9a97dec36d8e445e21"><td class="cellrowborder" valign="top" width="19.92%" headers="mcps1.2.5.1.1 "><p id="ae6c1123494d4499bbc24638bacbaca41"><a name="ae6c1123494d4499bbc24638bacbaca41"></a><a name="ae6c1123494d4499bbc24638bacbaca41"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="18.42%" headers="mcps1.2.5.1.2 "><p id="a331c5c23b9ac4d32aa0e594ed1580da8"><a name="a331c5c23b9ac4d32aa0e594ed1580da8"></a><a name="a331c5c23b9ac4d32aa0e594ed1580da8"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.800000000000004%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615029_p87768102015"><a name="zh-cn_topic_0079615029_p87768102015"></a><a name="zh-cn_topic_0079615029_p87768102015"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table47756489">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.86000000000001%" headers="mcps1.2.5.1.4 "><p id="a81b26054aa0f42f989c255e33d8d1839"><a name="a81b26054aa0f42f989c255e33d8d1839"></a><a name="a81b26054aa0f42f989c255e33d8d1839"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="r7dc3c368e52045cfb1c55fa4ae3b1eb8"><td class="cellrowborder" valign="top" width="19.92%" headers="mcps1.2.5.1.1 "><p id="aa9bd2f43a5a24fbabdcd1449a0b579a9"><a name="aa9bd2f43a5a24fbabdcd1449a0b579a9"></a><a name="aa9bd2f43a5a24fbabdcd1449a0b579a9"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="18.42%" headers="mcps1.2.5.1.2 "><p id="a3c23a0c1bad64a7aaa06d8b5cf59702c"><a name="a3c23a0c1bad64a7aaa06d8b5cf59702c"></a><a name="a3c23a0c1bad64a7aaa06d8b5cf59702c"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.800000000000004%" headers="mcps1.2.5.1.3 "><p id="a68dc55caf2854cef9dc9d4807e7dfa34"><a name="a68dc55caf2854cef9dc9d4807e7dfa34"></a><a name="a68dc55caf2854cef9dc9d4807e7dfa34"></a><a href="#te8aab4b8a25d48e3b3866c6c72239343">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.86000000000001%" headers="mcps1.2.5.1.4 "><p id="a342a0000645c480e9c82b88d608a9f50"><a name="a342a0000645c480e9c82b88d608a9f50"></a><a name="a342a0000645c480e9c82b88d608a9f50"></a>Spec defines the desired characteristics of a volume requested by a pod author.</p>
</td>
</tr>
<tr id="rcab0eff652cf4877a426a94b96ce9a35"><td class="cellrowborder" valign="top" width="19.92%" headers="mcps1.2.5.1.1 "><p id="a551f06b23e00410a9296c1abbd31bcab"><a name="a551f06b23e00410a9296c1abbd31bcab"></a><a name="a551f06b23e00410a9296c1abbd31bcab"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="18.42%" headers="mcps1.2.5.1.2 "><p id="a3f758c10769e416dbb0525ca05b8c73f"><a name="a3f758c10769e416dbb0525ca05b8c73f"></a><a name="a3f758c10769e416dbb0525ca05b8c73f"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.800000000000004%" headers="mcps1.2.5.1.3 "><p id="a1ed4070c0a1946b3b9c85113c8a484b2"><a name="a1ed4070c0a1946b3b9c85113c8a484b2"></a><a name="a1ed4070c0a1946b3b9c85113c8a484b2"></a><a href="#t6d0caee8f6ff4e19882bd42052d54287">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.86000000000001%" headers="mcps1.2.5.1.4 "><p id="a860de33cd8ff458491e26f1d1942c661"><a name="a860de33cd8ff458491e26f1d1942c661"></a><a name="a860de33cd8ff458491e26f1d1942c661"></a>Status represents the current information/status of a persistent volume claim. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  status字段数据结构说明

<a name="t6d0caee8f6ff4e19882bd42052d54287"></a>
<table><thead align="left"><tr id="r1039787b08fc447499e07ba06d5dc4f1"><th class="cellrowborder" valign="top" width="20.3020302030203%" id="mcps1.2.5.1.1"><p id="a0a6c65cf28864c2982e6007e2df4fe88"><a name="a0a6c65cf28864c2982e6007e2df4fe88"></a><a name="a0a6c65cf28864c2982e6007e2df4fe88"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.85178517851785%" id="mcps1.2.5.1.2"><p id="p19178141913173"><a name="p19178141913173"></a><a name="p19178141913173"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.731973197319732%" id="mcps1.2.5.1.3"><p id="p16179191919176"><a name="p16179191919176"></a><a name="p16179191919176"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.11421142114211%" id="mcps1.2.5.1.4"><p id="p418081971717"><a name="p418081971717"></a><a name="p418081971717"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r22049c56a96c45c5a601cfbc02be6660"><td class="cellrowborder" valign="top" width="20.3020302030203%" headers="mcps1.2.5.1.1 "><p id="a8e9b888448e64c96b2438c7a6dd7206d"><a name="a8e9b888448e64c96b2438c7a6dd7206d"></a><a name="a8e9b888448e64c96b2438c7a6dd7206d"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="17.85178517851785%" headers="mcps1.2.5.1.2 "><p id="aab7a0c5931934d50afa42cbd6453b8fd"><a name="aab7a0c5931934d50afa42cbd6453b8fd"></a><a name="aab7a0c5931934d50afa42cbd6453b8fd"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.731973197319732%" headers="mcps1.2.5.1.3 "><p id="a5c899f160ca240feacb14c6a3d94891c"><a name="a5c899f160ca240feacb14c6a3d94891c"></a><a name="a5c899f160ca240feacb14c6a3d94891c"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="42.11421142114211%" headers="mcps1.2.5.1.4 "><p id="a97cb0bc9eddc4610ade9dfff34189d75"><a name="a97cb0bc9eddc4610ade9dfff34189d75"></a><a name="a97cb0bc9eddc4610ade9dfff34189d75"></a>AccessModes contains the actual access modes the volume backing the PVC has.</p>
</td>
</tr>
<tr id="rb36b4b63c61c4b8bbfa417d3cd671c65"><td class="cellrowborder" valign="top" width="20.3020302030203%" headers="mcps1.2.5.1.1 "><p id="a083502d559ae4ae5982745f11d581767"><a name="a083502d559ae4ae5982745f11d581767"></a><a name="a083502d559ae4ae5982745f11d581767"></a>capacity</p>
</td>
<td class="cellrowborder" valign="top" width="17.85178517851785%" headers="mcps1.2.5.1.2 "><p id="aa9db836ee711403681c6f92b2b7cf5e6"><a name="aa9db836ee711403681c6f92b2b7cf5e6"></a><a name="aa9db836ee711403681c6f92b2b7cf5e6"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.731973197319732%" headers="mcps1.2.5.1.3 "><p id="a92f40e5b37ea4b12ac653d0a7155a1e5"><a name="a92f40e5b37ea4b12ac653d0a7155a1e5"></a><a name="a92f40e5b37ea4b12ac653d0a7155a1e5"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42.11421142114211%" headers="mcps1.2.5.1.4 "><p id="abf2c9e5432d34f8e9a748ab9654f7f7e"><a name="abf2c9e5432d34f8e9a748ab9654f7f7e"></a><a name="abf2c9e5432d34f8e9a748ab9654f7f7e"></a>Represents the actual resources of the underlying volume.</p>
</td>
</tr>
<tr id="r10ce1a1a516646b491d4ac077e72fb9d"><td class="cellrowborder" valign="top" width="20.3020302030203%" headers="mcps1.2.5.1.1 "><p id="a7cc0bd3cd0a54323bf21e2ac1e149cb2"><a name="a7cc0bd3cd0a54323bf21e2ac1e149cb2"></a><a name="a7cc0bd3cd0a54323bf21e2ac1e149cb2"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="17.85178517851785%" headers="mcps1.2.5.1.2 "><p id="a672cacf269794f17b672f2037e82c27f"><a name="a672cacf269794f17b672f2037e82c27f"></a><a name="a672cacf269794f17b672f2037e82c27f"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.731973197319732%" headers="mcps1.2.5.1.3 "><p id="a81001b8fef7848f09e59855bd96889a8"><a name="a81001b8fef7848f09e59855bd96889a8"></a><a name="a81001b8fef7848f09e59855bd96889a8"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11421142114211%" headers="mcps1.2.5.1.4 "><p id="a18f7cacd46024b05b7c1155055355dfe"><a name="a18f7cacd46024b05b7c1155055355dfe"></a><a name="a18f7cacd46024b05b7c1155055355dfe"></a>Phase represents the current phase of PersistentVolumeClaim.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  spec字段数据结构说明

<a name="te8aab4b8a25d48e3b3866c6c72239343"></a>
<table><thead align="left"><tr id="rf6e12204227f4fd3b84c216a0b860e68"><th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.5.1.1"><p id="a32620b87599745a9befdfa0869b98359"><a name="a32620b87599745a9befdfa0869b98359"></a><a name="a32620b87599745a9befdfa0869b98359"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.181818181818183%" id="mcps1.2.5.1.2"><p id="p61961119121715"><a name="p61961119121715"></a><a name="p61961119121715"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.5.1.3"><p id="p1119731910170"><a name="p1119731910170"></a><a name="p1119731910170"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.42424242424242%" id="mcps1.2.5.1.4"><p id="p18198819191716"><a name="p18198819191716"></a><a name="p18198819191716"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r53f2370142cb40788a32217eb4381ea5"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="a6409cced66134299be5e1d72b3513740"><a name="a6409cced66134299be5e1d72b3513740"></a><a name="a6409cced66134299be5e1d72b3513740"></a>volumeName</p>
</td>
<td class="cellrowborder" valign="top" width="18.181818181818183%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615029_p99829116436"><a name="zh-cn_topic_0079615029_p99829116436"></a><a name="zh-cn_topic_0079615029_p99829116436"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.5.1.3 "><p id="a1847fe8ee9fb4eb2baea898aa62e305a"><a name="a1847fe8ee9fb4eb2baea898aa62e305a"></a><a name="a1847fe8ee9fb4eb2baea898aa62e305a"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="ae8ab35042c524764a22854770e47011e"><a name="ae8ab35042c524764a22854770e47011e"></a><a name="ae8ab35042c524764a22854770e47011e"></a>VolumeName is the binding reference to the PersistentVolume backing this claim.</p>
</td>
</tr>
<tr id="r95177e5fc4774418800a458bfdec2be4"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="a8a53626737324427898ca58743e22120"><a name="a8a53626737324427898ca58743e22120"></a><a name="a8a53626737324427898ca58743e22120"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="18.181818181818183%" headers="mcps1.2.5.1.2 "><p id="ace8608fc2dad4fd4a23530b7bdf8fe56"><a name="ace8608fc2dad4fd4a23530b7bdf8fe56"></a><a name="ace8608fc2dad4fd4a23530b7bdf8fe56"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.5.1.3 "><p id="adb5d08279e8c487d94b76c25dbc9f2e1"><a name="adb5d08279e8c487d94b76c25dbc9f2e1"></a><a name="adb5d08279e8c487d94b76c25dbc9f2e1"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="a418458bd90ba478b8313723a7d57caf6"><a name="a418458bd90ba478b8313723a7d57caf6"></a><a name="a418458bd90ba478b8313723a7d57caf6"></a>AccessModes contains the desired access modes the volume should have. A volume can only be mounted using one access mode at a time, even if it supports many.</p>
</td>
</tr>
<tr id="r80c1d9db5bd34ec595e0346d0da690d3"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="a0e84d842139c48fc980c25160c38e10a"><a name="a0e84d842139c48fc980c25160c38e10a"></a><a name="a0e84d842139c48fc980c25160c38e10a"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="18.181818181818183%" headers="mcps1.2.5.1.2 "><p id="a6fc295b5732c49a6a3a11ad1381ae022"><a name="a6fc295b5732c49a6a3a11ad1381ae022"></a><a name="a6fc295b5732c49a6a3a11ad1381ae022"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.5.1.3 "><p id="a5f8f86b21e804fa0a5607657d0445f4e"><a name="a5f8f86b21e804fa0a5607657d0445f4e"></a><a name="a5f8f86b21e804fa0a5607657d0445f4e"></a><a href="#tb72f1d98d76d4130a04d98b73e0cce23">resources</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="a1dfe411351ca4e2494866ccd7c945431"><a name="a1dfe411351ca4e2494866ccd7c945431"></a><a name="a1dfe411351ca4e2494866ccd7c945431"></a>Resources represents the minimum resources the volume should have.</p>
</td>
</tr>
<tr id="rd80c2c948df44fc2a024d9fc3b8796e5"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="a8f955cfd78094329b1896a2beeaf5e10"><a name="a8f955cfd78094329b1896a2beeaf5e10"></a><a name="a8f955cfd78094329b1896a2beeaf5e10"></a>selector</p>
</td>
<td class="cellrowborder" valign="top" width="18.181818181818183%" headers="mcps1.2.5.1.2 "><p id="a65073be011424b618a9760a26b3a4b24"><a name="a65073be011424b618a9760a26b3a4b24"></a><a name="a65073be011424b618a9760a26b3a4b24"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.5.1.3 "><p id="a9ea12189100445e08e5a781d5fbb5aa0"><a name="a9ea12189100445e08e5a781d5fbb5aa0"></a><a name="a9ea12189100445e08e5a781d5fbb5aa0"></a><a href="#t87a0b25af7d2428182ec8bb2b4416a12">selector</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="a6794297065b6424e8da1fc310265ae69"><a name="a6794297065b6424e8da1fc310265ae69"></a><a name="a6794297065b6424e8da1fc310265ae69"></a>A label query over volumes to consider for binding.</p>
</td>
</tr>
<tr id="rf273f427ed004e31976ac3bd84136015"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="ad5c8b4d55586473dac47e4338dc8934c"><a name="ad5c8b4d55586473dac47e4338dc8934c"></a><a name="ad5c8b4d55586473dac47e4338dc8934c"></a>storageClassName</p>
</td>
<td class="cellrowborder" valign="top" width="18.181818181818183%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615029_p593313415714"><a name="zh-cn_topic_0079615029_p593313415714"></a><a name="zh-cn_topic_0079615029_p593313415714"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615029_p13933641377"><a name="zh-cn_topic_0079615029_p13933641377"></a><a name="zh-cn_topic_0079615029_p13933641377"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="abe92fbe03e704d03bd4ba5eef9f22f87"><a name="abe92fbe03e704d03bd4ba5eef9f22f87"></a><a name="abe92fbe03e704d03bd4ba5eef9f22f87"></a>Name of the StorageClass required by the claim.</p>
<p id="p1114925710147"><a name="p1114925710147"></a><a name="p1114925710147"></a>The cluster of v1.15 or later which use CCE SCI everest should fill in this filed. For EVS, set "csi-disk". For SFS, set "csi-nas". For OBS, set "csi-obs". For SFS-Turbo, set "csi-sfsturbo".</p>
</td>
</tr>
</tbody>
</table>

**表 5**  resources字段数据结构说明

<a name="tb72f1d98d76d4130a04d98b73e0cce23"></a>
<table><thead align="left"><tr id="r4317a7e84ae3468e8237aebe9de26de1"><th class="cellrowborder" valign="top" width="20.3%" id="mcps1.2.5.1.1"><p id="a38466d42e574446e97c43631a1ffd2ed"><a name="a38466d42e574446e97c43631a1ffd2ed"></a><a name="a38466d42e574446e97c43631a1ffd2ed"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.05%" id="mcps1.2.5.1.2"><p id="p13232819181720"><a name="p13232819181720"></a><a name="p13232819181720"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.11%" id="mcps1.2.5.1.3"><p id="p17235131914172"><a name="p17235131914172"></a><a name="p17235131914172"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.54%" id="mcps1.2.5.1.4"><p id="p18236171991718"><a name="p18236171991718"></a><a name="p18236171991718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r759308a1cad5445b9c7a7cc27887b234"><td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.1 "><p id="a6ef53902e1ae476aa4b8693ef275fb69"><a name="a6ef53902e1ae476aa4b8693ef275fb69"></a><a name="a6ef53902e1ae476aa4b8693ef275fb69"></a>limits</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="a691154d3d85b4080a11fa540473f4e9e"><a name="a691154d3d85b4080a11fa540473f4e9e"></a><a name="a691154d3d85b4080a11fa540473f4e9e"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.11%" headers="mcps1.2.5.1.3 "><p id="ae772f3c3a4d14ce8a7534e8486b4f453"><a name="ae772f3c3a4d14ce8a7534e8486b4f453"></a><a name="ae772f3c3a4d14ce8a7534e8486b4f453"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="41.54%" headers="mcps1.2.5.1.4 "><p id="a9ced3fae3c854142b30bbad123deeb50"><a name="a9ced3fae3c854142b30bbad123deeb50"></a><a name="a9ced3fae3c854142b30bbad123deeb50"></a>Limits describes the maximum amount of compute resources allowed.</p>
<div class="note" id="n771faf0818134d609e3ec4a29d247a1d"><a name="n771faf0818134d609e3ec4a29d247a1d"></a><a name="n771faf0818134d609e3ec4a29d247a1d"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a603f9ab664e947028e28f4a7508d17e7"><a name="a603f9ab664e947028e28f4a7508d17e7"></a><a name="a603f9ab664e947028e28f4a7508d17e7"></a>Parameter <strong id="zh-cn_topic_0079615029_b01199562566"><a name="zh-cn_topic_0079615029_b01199562566"></a><a name="zh-cn_topic_0079615029_b01199562566"></a>limits </strong>is invalid.</p>
</div></div>
</td>
</tr>
<tr id="r32f31618aeca4ac28acbca4823447bcc"><td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615029_p968607103038"><a name="zh-cn_topic_0079615029_p968607103038"></a><a name="zh-cn_topic_0079615029_p968607103038"></a>requests</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="a81ab9d3a8d5f46b7838981b6b1d1c56f"><a name="a81ab9d3a8d5f46b7838981b6b1d1c56f"></a><a name="a81ab9d3a8d5f46b7838981b6b1d1c56f"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.11%" headers="mcps1.2.5.1.3 "><p id="aade34b5b833e4978a51255ef6cb5a034"><a name="aade34b5b833e4978a51255ef6cb5a034"></a><a name="aade34b5b833e4978a51255ef6cb5a034"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="41.54%" headers="mcps1.2.5.1.4 "><p id="a8be2de751b264efb8f7e98e864ca08aa"><a name="a8be2de751b264efb8f7e98e864ca08aa"></a><a name="a8be2de751b264efb8f7e98e864ca08aa"></a>Requests describes the minimum amount of compute resources required. If Requests is omitted for a container, it defaults to Limits if that is explicitly specified, otherwise to an implementation-defined value.</p>
<div class="note" id="nb404d0c681ec402582456381b115edaf"><a name="nb404d0c681ec402582456381b115edaf"></a><a name="nb404d0c681ec402582456381b115edaf"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a7d6ef3ae08434217a89fb8ee46a76621"><a name="a7d6ef3ae08434217a89fb8ee46a76621"></a><a name="a7d6ef3ae08434217a89fb8ee46a76621"></a>Except parameter <strong id="a5d928ed0ad0c401eaf0de4522dd44864"><a name="a5d928ed0ad0c401eaf0de4522dd44864"></a><a name="a5d928ed0ad0c401eaf0de4522dd44864"></a>storage</strong>, the other parameters (such as&nbsp;<strong id="zh-cn_topic_0079615029_b380914172598"><a name="zh-cn_topic_0079615029_b380914172598"></a><a name="zh-cn_topic_0079615029_b380914172598"></a>CPU</strong>&nbsp;and&nbsp;<strong id="ac0085b622ee548e1bcdebc5a5d9dced8"><a name="ac0085b622ee548e1bcdebc5a5d9dced8"></a><a name="ac0085b622ee548e1bcdebc5a5d9dced8"></a>memory</strong>) are invalid.</p>
</div></div>
</td>
</tr>
</tbody>
</table>

**表 6**  selector字段数据结构说明

<a name="t87a0b25af7d2428182ec8bb2b4416a12"></a>
<table><thead align="left"><tr id="r2a5829fcfed94e4198396b80fd7d3c70"><th class="cellrowborder" valign="top" width="20.49%" id="mcps1.2.5.1.1"><p id="a49b6dadc30874be28e28b3db6d329171"><a name="a49b6dadc30874be28e28b3db6d329171"></a><a name="a49b6dadc30874be28e28b3db6d329171"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.86%" id="mcps1.2.5.1.2"><p id="p82575192174"><a name="p82575192174"></a><a name="p82575192174"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.3%" id="mcps1.2.5.1.3"><p id="p1525817199171"><a name="p1525817199171"></a><a name="p1525817199171"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.349999999999994%" id="mcps1.2.5.1.4"><p id="p14259219121716"><a name="p14259219121716"></a><a name="p14259219121716"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r1a6d727676e34d3fa181c0bcd3ee48b0"><td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.1 "><p id="a728d8aedf14946dfa98022dfebc3aa4e"><a name="a728d8aedf14946dfa98022dfebc3aa4e"></a><a name="a728d8aedf14946dfa98022dfebc3aa4e"></a>matchExpressions</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="aca2c67f0f6874158a6505ac0a585647f"><a name="aca2c67f0f6874158a6505ac0a585647f"></a><a name="aca2c67f0f6874158a6505ac0a585647f"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="a7233b96002a541818ad7e1a1ddb1e469"><a name="a7233b96002a541818ad7e1a1ddb1e469"></a><a name="a7233b96002a541818ad7e1a1ddb1e469"></a><a href="#t8ff36c0b2ec24d7caf0c726319d7bb73">matchExpressions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="41.349999999999994%" headers="mcps1.2.5.1.4 "><p id="a089ce9db9ab04f20aad32d21c5ea14c7"><a name="a089ce9db9ab04f20aad32d21c5ea14c7"></a><a name="a089ce9db9ab04f20aad32d21c5ea14c7"></a>MatchExpressions is a list of label selector requirements. The requirements are ANDed.</p>
</td>
</tr>
<tr id="rf2aa597e0e994495a58e29c028e0d37a"><td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.1 "><p id="a2f5e0427a45d4fd796b549030bc43f5e"><a name="a2f5e0427a45d4fd796b549030bc43f5e"></a><a name="a2f5e0427a45d4fd796b549030bc43f5e"></a>matchLabels</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="af4e7fb004dab4ebda86cc06b52ebae6c"><a name="af4e7fb004dab4ebda86cc06b52ebae6c"></a><a name="af4e7fb004dab4ebda86cc06b52ebae6c"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="a0e6c5bd704084c28a2b07e8459ab2f65"><a name="a0e6c5bd704084c28a2b07e8459ab2f65"></a><a name="a0e6c5bd704084c28a2b07e8459ab2f65"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="41.349999999999994%" headers="mcps1.2.5.1.4 "><p id="ac44ce0da1cd54bba925effa1af55dc20"><a name="ac44ce0da1cd54bba925effa1af55dc20"></a><a name="ac44ce0da1cd54bba925effa1af55dc20"></a>MatchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  matchExpressions字段数据结构说明

<a name="t8ff36c0b2ec24d7caf0c726319d7bb73"></a>
<table><thead align="left"><tr id="rd49cd0acdad64dc88133cc81665bd516"><th class="cellrowborder" valign="top" width="20.49%" id="mcps1.2.5.1.1"><p id="a8c097e38653545d18c60d02cc3f47f7d"><a name="a8c097e38653545d18c60d02cc3f47f7d"></a><a name="a8c097e38653545d18c60d02cc3f47f7d"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.669999999999998%" id="mcps1.2.5.1.2"><p id="p1027521914175"><a name="p1027521914175"></a><a name="p1027521914175"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.49%" id="mcps1.2.5.1.3"><p id="p427610192179"><a name="p427610192179"></a><a name="p427610192179"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.349999999999994%" id="mcps1.2.5.1.4"><p id="p11277419131719"><a name="p11277419131719"></a><a name="p11277419131719"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rc0f7baf4628a4efb9354048b9a231187"><td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.1 "><p id="a1b655fff259b4075b0c05684edadf447"><a name="a1b655fff259b4075b0c05684edadf447"></a><a name="a1b655fff259b4075b0c05684edadf447"></a>key</p>
</td>
<td class="cellrowborder" valign="top" width="17.669999999999998%" headers="mcps1.2.5.1.2 "><p id="a62a5e7d054d74083865c303d4f1fd1a4"><a name="a62a5e7d054d74083865c303d4f1fd1a4"></a><a name="a62a5e7d054d74083865c303d4f1fd1a4"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="ab4746cbb41b5467bbbed18c1e0ecc71c"><a name="ab4746cbb41b5467bbbed18c1e0ecc71c"></a><a name="ab4746cbb41b5467bbbed18c1e0ecc71c"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.349999999999994%" headers="mcps1.2.5.1.4 "><p id="ae985fe8957dc4890bbc1b769b9d1b1ca"><a name="ae985fe8957dc4890bbc1b769b9d1b1ca"></a><a name="ae985fe8957dc4890bbc1b769b9d1b1ca"></a>Key is the label key that the selector applies to.</p>
</td>
</tr>
<tr id="r3f95161df496421baf7fa0d6079489a0"><td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.1 "><p id="aa5270327f17a46ed85c14bd91defb103"><a name="aa5270327f17a46ed85c14bd91defb103"></a><a name="aa5270327f17a46ed85c14bd91defb103"></a>operator</p>
</td>
<td class="cellrowborder" valign="top" width="17.669999999999998%" headers="mcps1.2.5.1.2 "><p id="a7c0665a700c14671901b8e91d2911412"><a name="a7c0665a700c14671901b8e91d2911412"></a><a name="a7c0665a700c14671901b8e91d2911412"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="a756afe203dae4d0caf0526cc04e0caf2"><a name="a756afe203dae4d0caf0526cc04e0caf2"></a><a name="a756afe203dae4d0caf0526cc04e0caf2"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.349999999999994%" headers="mcps1.2.5.1.4 "><p id="af5f15638ee2d4576974d4ebbe7109240"><a name="af5f15638ee2d4576974d4ebbe7109240"></a><a name="af5f15638ee2d4576974d4ebbe7109240"></a>Operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</p>
</td>
</tr>
<tr id="r76d6bdbf9d3647e7a7632aa9157f3419"><td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.1 "><p id="a73c0e5a1e1bc4442a9ba429271e11452"><a name="a73c0e5a1e1bc4442a9ba429271e11452"></a><a name="a73c0e5a1e1bc4442a9ba429271e11452"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="17.669999999999998%" headers="mcps1.2.5.1.2 "><p id="a0d8837a9d71b4d0b8dbac5ca2be7a048"><a name="a0d8837a9d71b4d0b8dbac5ca2be7a048"></a><a name="a0d8837a9d71b4d0b8dbac5ca2be7a048"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="adeaae4564fde4f92b97fd8da81eb6669"><a name="adeaae4564fde4f92b97fd8da81eb6669"></a><a name="adeaae4564fde4f92b97fd8da81eb6669"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="41.349999999999994%" headers="mcps1.2.5.1.4 "><p id="a030ebef722294e85a182b65b2562e932"><a name="a030ebef722294e85a182b65b2562e932"></a><a name="a030ebef722294e85a182b65b2562e932"></a>Values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</p>
</td>
</tr>
</tbody>
</table>

**云硬盘存储卷请求示例**：

-   1.15及之后集群版本请求示例：

    ```
    {
        "kind":"PersistentVolumeClaim",
        "apiVersion":"v1",
        "metadata":{
            "name":"cce-evs-k6m16atm-3ays",
            "namespace":"default",
            "selfLink":"/api/v1/namespaces/default/persistentvolumeclaims/cce-evs-k6m16atm-3ays",
            "uid":"80f111e7-7d7e-4841-bd73-7ef97df0ee51",
            "resourceVersion":"2287083",
            "creationTimestamp":"2020-02-14T10:30:20Z",
            "labels":{
                "failure-domain.beta.kubernetes.io/region":"cn-north-5",
                "failure-domain.beta.kubernetes.io/zone":"cn-north-5a"
            },
            "annotations":{
                "everest.io/crypt-key-id":"527cbece-428d-463b-a92c-936a11077b5d", //创建加密卷必需，若无或不全，则不加密；
                "everest.io/disk-volume-type":"SATA"
            },
            "finalizers":[
                "kubernetes.io/pvc-protection"
            ]
        },
        "spec":{
            "accessModes":[
                "ReadWriteOnce"
            ],
            "resources":{
                "requests":{
                    "storage":"10Gi"
                }
            },
            "storageClassName":"csi-disk",
            "volumeMode":"Filesystem"
        }
    }
    ```

-   1.13及之前版本示例：

    ```
    {
        "apiVersion": "v1",
        "kind": "PersistentVolumeClaim",
        "metadata": {
            "name": "db-mysql",
            "namespace": "default",
            "annotations": {
            "paas.storage.io/cryptKeyId": "1ed68cb7-b09b-423c-8d66-fdd2e063769d",     //此annotation表明是否加密，若无，则不加密；
    	"volume.beta.kubernetes.io/storage-class": "sata",
    	"volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
            },
            "labels": {
    	"failure-domain.beta.kubernetes.io/region": "cn-north-1",
    	"failure-domain.beta.kubernetes.io/zone": "cn-north-1a"
            }
        },
        "spec": {
            "accessModes": [
                "ReadWriteMany"
            ],
            "resources": {
                "requests": {
                    "storage": "10Gi"
                }
            }
        }
    }
    ```


**文件存储卷请求示例**：

-   1.15及之后集群版本示例

    ```
    {
        "apiVersion": "v1",
        "kind": "PersistentVolumeClaim",
        "metadata": {
            "annotations": {
                "everest.io/crypt-key-id": "3cfaea47-eb9b-4c68-b108-86fe399aebaf",
    	    "everest.io/crypt-domain-id": "fff357e41a3a4a0d88e821f35194d110",
    	    "everest.io/crypt-alias": "sfs/default"
            },
            "name": "pvc-158167040158916159-test-sfs-0",
            "namespace": "default",
        },
        "spec": {
            "accessModes": [
                "ReadWriteMany"
            ],
            "resources": {
                "requests": {
                    "storage": "10Gi"
                }
            },
            "storageClassName": "csi-nas",
            "volumeMode": "Filesystem",
            "volumeName": "pvc-1c933c44-1f47-41a4-9353-3800a21cab6b"
        }
    }
    ```

-   1.13及之前集群版本示例：

    ```
    {
        "apiVersion": "v1",
        "kind": "PersistentVolumeClaim",
        "metadata": {
            "name": "sfs-pvc",
            "namespace": "default",
            "annotations": {   
            "paas.storage.io/cryptAlias": "sfs/default" ,           //红色字体部分三个annotation是创建加密卷必需，若无或不全，则不加密；
            "paas.storage.io/cryptDomainId": "fff357e41a3a4a0d88e821f35194d110",
            "paas.storage.io/cryptKeyId": "3cfaea47-eb9b-4c68-b108-86fe399aebaf",
    	"volume.beta.kubernetes.io/storage-class": "nfs-rw",
    	"volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxinfs"
            }
        },
        "spec": {
            "accessModes": [
                "ReadWriteMany"
            ],
            "resources": {
                "requests": {
                    "storage": "10Gi"
                }
            }
        }
    }
    ```


## 响应消息<a name="sfea287b75ddb40569f61ea90875869cb"></a>

**响应参数：**

响应参数的详细描述请参见[14.2 Table2 Request parameters](#t8268aeafde034542ab17a36c7fca65c3).

**云硬盘存储卷响应示例：**

-   1.15及之后集群版本yaml示例

    ```
    {
        "kind":"PersistentVolumeClaim",
        "apiVersion":"v1",
        "metadata":{
            "name":"cce-evs-k6m16atm-3ays",
            "namespace":"default",
            "selfLink":"/api/v1/namespaces/default/persistentvolumeclaims/cce-evs-k6m16atm-3ays",
            "uid":"80f111e7-7d7e-4841-bd73-7ef97df0ee51",
            "resourceVersion":"2287083",
            "creationTimestamp":"2020-02-14T10:30:20Z",
            "labels":{
                "failure-domain.beta.kubernetes.io/region":"cn-north-5",
                "failure-domain.beta.kubernetes.io/zone":"cn-north-5a"
            },
            "annotations":{
                "everest.io/crypt-key-id":"527cbece-428d-463b-a92c-936a11077b5d",//若为加密卷，则存在
                "everest.io/disk-volume-type":"SATA"
            },
            "finalizers":[
                "kubernetes.io/pvc-protection"
            ]
        },
        "spec":{
            "accessModes":[
                "ReadWriteOnce"
            ],
            "resources":{
                "requests":{
                    "storage":"10Gi"
                }
            },
            "storageClassName":"csi-disk",
            "volumeName": "pvc-d34f6a93-9eba-4a33-9320-8fa4addd3753",
            "volumeMode":"Filesystem"
        },
        "status":{
            "phase":"Pending"
        }
    }
    ```


-   1.13及之前版本yaml示例：

    ```
    {
        "kind": "PersistentVolumeClaim",
        "apiVersion": "v1",
        "metadata": {
            "name": "db-mysql",
            "namespace": "default",
            "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims/db-mysql",
            "uid": "ac34af93-8cdd-11e8-8ee0-fa163e49263c",
            "resourceVersion": "4197709",
            "creationTimestamp": "2018-07-21T12:00:33Z",
            "labels": {
                "failure-domain.beta.kubernetes.io/region": "cn-north-1",
                "failure-domain.beta.kubernetes.io/zone": "cn-north-1a"
            },
            "annotations": {
                "paas.storage.io/cryptKeyId": "1ed68cb7-b09b-423c-8d66-fdd2e063769d"   //若为加密卷，则存在
                "pv.kubernetes.io/bind-completed": "yes",
                "pv.kubernetes.io/bound-by-controller": "yes",
                "volume.beta.kubernetes.io/storage-class": "sata",
                "volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
            }
        },
        "spec": {
            "accessModes": [
                "ReadWriteMany"
            ],
            "resources": {
                "requests": {
                    "storage": "10Gi"
                }
            },
            "volumeName": "pvc-ac34af93-8cdd-11e8-8ee0-fa163e49263c",
            "volumeNamespace": "default"
        },
        "status": {
            "phase": "Bound",
            "accessModes": [
                "ReadWriteMany"
            ],
            "capacity": {
                "storage": "10Gi"
            }
        }
    }
    ```


## 状态码<a name="s83847071f8aa4217be1335b90a09a193"></a>

[表8](#t395400749a4a48bdaa2c2d6467f593cd)描述API的状态码。

**表 8**  状态码

<a name="t395400749a4a48bdaa2c2d6467f593cd"></a>
<table><thead align="left"><tr id="rbe30eb05eac64354acc6ebc34daf65dc"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p10977619181711"><a name="p10977619181711"></a><a name="p10977619181711"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1997761919172"><a name="p1997761919172"></a><a name="p1997761919172"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r16588ef0f9eb42a78267e1bfe3ffde07"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="a714d32bf07ab434b9b247aafadab0e41"><a name="a714d32bf07ab434b9b247aafadab0e41"></a><a name="a714d32bf07ab434b9b247aafadab0e41"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="a5d57d5cda4e144c9a9688f3ed7abf5f0"><a name="a5d57d5cda4e144c9a9688f3ed7abf5f0"></a><a name="a5d57d5cda4e144c9a9688f3ed7abf5f0"></a>The request has been fulfilled, resulting in the creation of a new resource.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

