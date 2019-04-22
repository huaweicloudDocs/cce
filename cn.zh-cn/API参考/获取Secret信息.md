# 获取Secret信息<a name="cce_02_0045"></a>

## 功能介绍<a name="sd604b64334b14bda8ab791b18976a40a"></a>

该API用于获取指定Secret的详细信息。

## URI<a name="s2da0803c5eaf4d60a9765de92e374e84"></a>

GET /api/v1/namespaces/\{namespace\}/secrets/\{name\}

[表1](#zh-cn_topic_0079614927_table17106298)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614927_table17106298"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614927_row33442533"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614927_p24490648"><a name="zh-cn_topic_0079614927_p24490648"></a><a name="zh-cn_topic_0079614927_p24490648"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="26%" id="mcps1.2.4.1.2"><p id="p3588391203114"><a name="p3588391203114"></a><a name="p3588391203114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="41%" id="mcps1.2.4.1.3"><p id="p22224249203114"><a name="p22224249203114"></a><a name="p22224249203114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614927_row40369597"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p48711890"><a name="zh-cn_topic_0079614927_p48711890"></a><a name="zh-cn_topic_0079614927_p48711890"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p53348995"><a name="zh-cn_topic_0079614927_p53348995"></a><a name="zh-cn_topic_0079614927_p53348995"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="p28675043"><a name="p28675043"></a><a name="p28675043"></a>设置为true后，会打印漂亮的输出结果。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row35385738"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p47672514"><a name="zh-cn_topic_0079614927_p47672514"></a><a name="zh-cn_topic_0079614927_p47672514"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p36268402"><a name="zh-cn_topic_0079614927_p36268402"></a><a name="zh-cn_topic_0079614927_p36268402"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p52059459"><a name="zh-cn_topic_0079614927_p52059459"></a><a name="zh-cn_topic_0079614927_p52059459"></a></p>
<p id="p658610593411"><a name="p658610593411"></a><a name="p658610593411"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。可以任选其一使用：</p>
<a name="ul75828215461"></a><a name="ul75828215461"></a><ul id="ul75828215461"><li>用户自定义的namespace，使用前必须先<a href="创建Namespace.md">创建Namespace</a></li><li>系统自带的namespace：default或kube-system</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row65881951"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p34837828"><a name="zh-cn_topic_0079614927_p34837828"></a><a name="zh-cn_topic_0079614927_p34837828"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p3291805"><a name="zh-cn_topic_0079614927_p3291805"></a><a name="zh-cn_topic_0079614927_p3291805"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p35684724"><a name="zh-cn_topic_0079615047_p35684724"></a><a name="zh-cn_topic_0079615047_p35684724"></a>指定查看的secret的名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row8895702167"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p19896202160"><a name="zh-cn_topic_0079614927_p19896202160"></a><a name="zh-cn_topic_0079614927_p19896202160"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="a688fa776ec494137a4dc4d62383a2dc3"><a name="a688fa776ec494137a4dc4d62383a2dc3"></a><a name="a688fa776ec494137a4dc4d62383a2dc3"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p28969051618"><a name="zh-cn_topic_0079614927_p28969051618"></a><a name="zh-cn_topic_0079614927_p28969051618"></a>表示查看的信息是否要精准导出，设置后导出信息会保持集群专属的字段，比如"Namespace"。</p>
</td>
</tr>
<tr id="rd0a38f8b45ce43d4b33530c1fb363adb"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="acf120ad7b3464dd3afd59acac130d10a"><a name="acf120ad7b3464dd3afd59acac130d10a"></a><a name="acf120ad7b3464dd3afd59acac130d10a"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p275914191162"><a name="zh-cn_topic_0079614927_p275914191162"></a><a name="zh-cn_topic_0079614927_p275914191162"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="a743d354f3c564a71bea87c0e96598b2d"><a name="a743d354f3c564a71bea87c0e96598b2d"></a><a name="a743d354f3c564a71bea87c0e96598b2d"></a>设置value值是否要导出，导出时会忽略用户无法指定的字段。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s238431defdf9448ab788b8b65625dbd0"></a>

N/A

## 响应消息<a name="s195ff6098f0d47c6bf0449fd249cac30"></a>

**响应参数：**

响应参数如[表2](#zh-cn_topic_0079614927_table19738956)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079614927_table19738956"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614927_row9250766"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614927_p11114581"><a name="zh-cn_topic_0079614927_p11114581"></a><a name="zh-cn_topic_0079614927_p11114581"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p20130695203114"><a name="p20130695203114"></a><a name="p20130695203114"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p19973587203114"><a name="p19973587203114"></a><a name="p19973587203114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614927_row23367165"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p13692182"><a name="zh-cn_topic_0079614927_p13692182"></a><a name="zh-cn_topic_0079614927_p13692182"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p35324919"><a name="zh-cn_topic_0079614927_p35324919"></a><a name="zh-cn_topic_0079614927_p35324919"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p30014175"><a name="zh-cn_topic_0079615047_p30014175"></a><a name="zh-cn_topic_0079615047_p30014175"></a>表示API类型。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row49171347"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p23456209"><a name="zh-cn_topic_0079614927_p23456209"></a><a name="zh-cn_topic_0079614927_p23456209"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p20904787"><a name="zh-cn_topic_0079614927_p20904787"></a><a name="zh-cn_topic_0079614927_p20904787"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p44485484"><a name="zh-cn_topic_0079615047_p44485484"></a><a name="zh-cn_topic_0079615047_p44485484"></a>表示API版本。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row5878165"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p6369394"><a name="zh-cn_topic_0079614927_p6369394"></a><a name="zh-cn_topic_0079614927_p6369394"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p46158895"><a name="zh-cn_topic_0079614927_p46158895"></a><a name="zh-cn_topic_0079614927_p46158895"></a><a href="#zh-cn_topic_0079614927_table43432884">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p47882996"><a name="zh-cn_topic_0079614927_p47882996"></a><a name="zh-cn_topic_0079614927_p47882996"></a>-</p>
</td>
</tr>
<tr id="ra0f5eda0265f4fcfa3f19b07e037934b"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="a967096c804ef402aab0fc2136cc27626"><a name="a967096c804ef402aab0fc2136cc27626"></a><a name="a967096c804ef402aab0fc2136cc27626"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="a22ac63c8187b498d89bf40f317c194a4"><a name="a22ac63c8187b498d89bf40f317c194a4"></a><a name="a22ac63c8187b498d89bf40f317c194a4"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="aa3f29c40161141a9bc895a80c070e251"><a name="aa3f29c40161141a9bc895a80c070e251"></a><a name="aa3f29c40161141a9bc895a80c070e251"></a>Data表示secret的数据，是key/value对的格式。secret的数据是base64加密格式的字符串类型。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row28293786"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p10095295"><a name="zh-cn_topic_0079614927_p10095295"></a><a name="zh-cn_topic_0079614927_p10095295"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p12412544"><a name="zh-cn_topic_0079614927_p12412544"></a><a name="zh-cn_topic_0079614927_p12412544"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p65892039"><a name="zh-cn_topic_0079614927_p65892039"></a><a name="zh-cn_topic_0079614927_p65892039"></a>Type表示secret的类型</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="zh-cn_topic_0079614927_table43432884"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614927_row22548652"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614927_p14501537"><a name="zh-cn_topic_0079614927_p14501537"></a><a name="zh-cn_topic_0079614927_p14501537"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p17824150203114"><a name="p17824150203114"></a><a name="p17824150203114"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p34470068203114"><a name="p34470068203114"></a><a name="p34470068203114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614927_row63767898"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p64926096"><a name="zh-cn_topic_0079614927_p64926096"></a><a name="zh-cn_topic_0079614927_p64926096"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p24522460"><a name="zh-cn_topic_0079614927_p24522460"></a><a name="zh-cn_topic_0079614927_p24522460"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p168024282424"><a name="zh-cn_topic_0079614900_p168024282424"></a><a name="zh-cn_topic_0079614900_p168024282424"></a>Secret名称，同一namespace下name不能重复，无法被更新</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row25915585"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p18787663"><a name="zh-cn_topic_0079614927_p18787663"></a><a name="zh-cn_topic_0079614927_p18787663"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p45405709"><a name="zh-cn_topic_0079614927_p45405709"></a><a name="zh-cn_topic_0079614927_p45405709"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p16098318"><a name="zh-cn_topic_0079614900_p16098318"></a><a name="zh-cn_topic_0079614900_p16098318"></a>GenerateName 是一个可选项，表示名字的前缀，当Name字段为空时，会自动使用该前缀生成一个集群内唯一存在的Name。只有当Name字段为空时才需要配置generateName，generateName可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row28380941"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p17154888"><a name="zh-cn_topic_0079614927_p17154888"></a><a name="zh-cn_topic_0079614927_p17154888"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p47368663"><a name="zh-cn_topic_0079614927_p47368663"></a><a name="zh-cn_topic_0079614927_p47368663"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p1561207153512"><a name="p1561207153512"></a><a name="p1561207153512"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。可以任选其一使用：</p>
<a name="ul2786250175914"></a><a name="ul2786250175914"></a><ul id="ul2786250175914"><li>用户自定义的namespace，使用前必须先<a href="创建Namespace.md">创建Namespace</a></li><li>系统自带的namespace：default或kube-system</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row37799483"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p41859244"><a name="zh-cn_topic_0079614927_p41859244"></a><a name="zh-cn_topic_0079614927_p41859244"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p35155598"><a name="zh-cn_topic_0079614927_p35155598"></a><a name="zh-cn_topic_0079614927_p35155598"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p14471838"><a name="zh-cn_topic_0079614900_p14471838"></a><a name="zh-cn_topic_0079614900_p14471838"></a>SelfLink 是该资源对象的 URL。 系统内部使用，只读项。.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row59953998"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p24435680"><a name="zh-cn_topic_0079614927_p24435680"></a><a name="zh-cn_topic_0079614927_p24435680"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p33133087"><a name="zh-cn_topic_0079614927_p33133087"></a><a name="zh-cn_topic_0079614927_p33133087"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p39122574"><a name="zh-cn_topic_0079614900_p39122574"></a><a name="zh-cn_topic_0079614900_p39122574"></a>UID 是赋值给该资源对象全局唯一的ID. 系统自动生成以及提供系统内部使用，只读项。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row61938567"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p50968020"><a name="zh-cn_topic_0079614927_p50968020"></a><a name="zh-cn_topic_0079614927_p50968020"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p34768937"><a name="zh-cn_topic_0079614927_p34768937"></a><a name="zh-cn_topic_0079614927_p34768937"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p64820527"><a name="zh-cn_topic_0079614927_p64820527"></a><a name="zh-cn_topic_0079614927_p64820527"></a>ResourceVersion表示该资源对象内部版本，可以用来优化并发性能和监视资源变化，系统内部使用，只读项。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row46513836"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p9524349"><a name="zh-cn_topic_0079614927_p9524349"></a><a name="zh-cn_topic_0079614927_p9524349"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p33274836"><a name="zh-cn_topic_0079614927_p33274836"></a><a name="zh-cn_topic_0079614927_p33274836"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p19792958"><a name="zh-cn_topic_0079614900_p19792958"></a><a name="zh-cn_topic_0079614900_p19792958"></a>Generation是根据资源对象预期状态生成的一串序列，由replication controllers生成， 系统内部使用，只读项。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row31055564"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p32472732"><a name="zh-cn_topic_0079614927_p32472732"></a><a name="zh-cn_topic_0079614927_p32472732"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p13045645"><a name="zh-cn_topic_0079614927_p13045645"></a><a name="zh-cn_topic_0079614927_p13045645"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p60119179"><a name="zh-cn_topic_0079614900_p60119179"></a><a name="zh-cn_topic_0079614900_p60119179"></a>CreationTimestamp是该资源对象创建的时间戳，UTC时间，使用RFC3339格式。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row47925758"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p56781175"><a name="zh-cn_topic_0079614927_p56781175"></a><a name="zh-cn_topic_0079614927_p56781175"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p35872461"><a name="zh-cn_topic_0079614927_p35872461"></a><a name="zh-cn_topic_0079614927_p35872461"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p19988199"><a name="zh-cn_topic_0079614927_p19988199"></a><a name="zh-cn_topic_0079614927_p19988199"></a>DeletionTimestamp是该资源对象即将被删除的时间戳，使用RFC3339格式。 只有当客户端请求优雅删除资源对象的时候，该参数才会被系统赋值，客户端无法直接设置该参数，资源对象会在该时间之后被删除（list无法看到以及通过名字无法查询到），该参数值设置后无法修改，只读项。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row45676065"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p8773789"><a name="zh-cn_topic_0079614927_p8773789"></a><a name="zh-cn_topic_0079614927_p8773789"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p39588305"><a name="zh-cn_topic_0079614927_p39588305"></a><a name="zh-cn_topic_0079614927_p39588305"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p63073541"><a name="zh-cn_topic_0079614900_p63073541"></a><a name="zh-cn_topic_0079614900_p63073541"></a>设置允许资源对象被优雅删除的最长时间，该参数会和deletionTimestamp一起被设置，只读项。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row3063452"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p46813093"><a name="zh-cn_topic_0079614927_p46813093"></a><a name="zh-cn_topic_0079614927_p46813093"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p33764194"><a name="zh-cn_topic_0079614927_p33764194"></a><a name="zh-cn_topic_0079614927_p33764194"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p1891734165913"><a name="p1891734165913"></a><a name="p1891734165913"></a>Secret标签，key/value对格式。</p>
<a name="ul1736685012"></a><a name="ul1736685012"></a><ul id="ul1736685012"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</li><li>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li></ul>
<p id="p156295249512"><a name="p156295249512"></a><a name="p156295249512"></a>示例：</p>
<a name="ul184411422183314"></a><a name="ul184411422183314"></a><ul id="ul184411422183314"><li>"foo": "bar"</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row52253727"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p4693486"><a name="zh-cn_topic_0079614927_p4693486"></a><a name="zh-cn_topic_0079614927_p4693486"></a>Annotations</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p44628110"><a name="zh-cn_topic_0079614927_p44628110"></a><a name="zh-cn_topic_0079614927_p44628110"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p58107175"><a name="zh-cn_topic_0079614927_p58107175"></a><a name="zh-cn_topic_0079614927_p58107175"></a>Annotations是非结构化的键值对，通常用来保存任意外部定义的元数据。</p>
</td>
</tr>
<tr id="r9f8905c2e7b441419117d2bc6f46baea"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a8a1e39bea6d94f2692a45140018e13b9"><a name="a8a1e39bea6d94f2692a45140018e13b9"></a><a name="a8a1e39bea6d94f2692a45140018e13b9"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="a2fad25498b674e40937f6e88b4e8099c"><a name="a2fad25498b674e40937f6e88b4e8099c"></a><a name="a2fad25498b674e40937f6e88b4e8099c"></a><a href="#tcba7b62965f94a85b2111568e64bf277">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a47143b35d469419b80303ee850b0642e"><a name="a47143b35d469419b80303ee850b0642e"></a><a name="a47143b35d469419b80303ee850b0642e"></a>OwnerReferences是所有依赖当前资源对象的其他资源对象列表，如果列表里资源都已经被删除，则当前资源会被垃圾回收。如果当前资源被controller管理，则列表中有一项指向该controller，该项中controller字段被设置为true，controller不会超过一个。</p>
</td>
</tr>
<tr id="r8b930028b27043558a2e43034bbf289a"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p9160517169"><a name="zh-cn_topic_0079614927_p9160517169"></a><a name="zh-cn_topic_0079614927_p9160517169"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p742001917169"><a name="zh-cn_topic_0079614927_p742001917169"></a><a name="zh-cn_topic_0079614927_p742001917169"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a69e1b2402dce4f358aeab4184e6cf280"><a name="a69e1b2402dce4f358aeab4184e6cf280"></a><a name="a69e1b2402dce4f358aeab4184e6cf280"></a>在从注册表中删除对象之前，该参数必须为空。</p>
</td>
</tr>
</tbody>
</table>

**表 4**  ownerReferences字段数据结构说明

<a name="tcba7b62965f94a85b2111568e64bf277"></a>
<table><thead align="left"><tr id="rd0051a4123424215a4ab3acda7febb55"><th class="cellrowborder" valign="top" width="24.0975902409759%" id="mcps1.2.4.1.1"><p id="a9a7db9964ad04363b4b86ce6700d57cc"><a name="a9a7db9964ad04363b4b86ce6700d57cc"></a><a name="a9a7db9964ad04363b4b86ce6700d57cc"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="26.507349265073493%" id="mcps1.2.4.1.2"><p id="p56237581203114"><a name="p56237581203114"></a><a name="p56237581203114"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="49.3950604939506%" id="mcps1.2.4.1.3"><p id="p58950192203114"><a name="p58950192203114"></a><a name="p58950192203114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r0913647179604279841715f37ff6105c"><td class="cellrowborder" valign="top" width="24.0975902409759%" headers="mcps1.2.4.1.1 "><p id="ac18fd4b4b202428abafd3fcf91df0fbe"><a name="ac18fd4b4b202428abafd3fcf91df0fbe"></a><a name="ac18fd4b4b202428abafd3fcf91df0fbe"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="26.507349265073493%" headers="mcps1.2.4.1.2 "><p id="a20483d3be3e64055af5d7f12dfbbca12"><a name="a20483d3be3e64055af5d7f12dfbbca12"></a><a name="a20483d3be3e64055af5d7f12dfbbca12"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="ac964351ba76e4233b5f31aa5309de4b4"><a name="ac964351ba76e4233b5f31aa5309de4b4"></a><a name="ac964351ba76e4233b5f31aa5309de4b4"></a>资源对象的API版本。</p>
</td>
</tr>
<tr id="r9f429c7df9e446efbffca38d4fca1ca7"><td class="cellrowborder" valign="top" width="24.0975902409759%" headers="mcps1.2.4.1.1 "><p id="a02456892c5454c84bd3fd3caa55d0489"><a name="a02456892c5454c84bd3fd3caa55d0489"></a><a name="a02456892c5454c84bd3fd3caa55d0489"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="26.507349265073493%" headers="mcps1.2.4.1.2 "><p id="a0ed2bd4b0d59460c9e74c3251ea3cd8f"><a name="a0ed2bd4b0d59460c9e74c3251ea3cd8f"></a><a name="a0ed2bd4b0d59460c9e74c3251ea3cd8f"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="a4d2494c2f65b402db38a21a347dbb2ff"><a name="a4d2494c2f65b402db38a21a347dbb2ff"></a><a name="a4d2494c2f65b402db38a21a347dbb2ff"></a>资源对象的类型。</p>
</td>
</tr>
<tr id="r380a9238b04440a2b9e5eee6cb77e03f"><td class="cellrowborder" valign="top" width="24.0975902409759%" headers="mcps1.2.4.1.1 "><p id="a36b1525ce4eb4b4a902894499694c872"><a name="a36b1525ce4eb4b4a902894499694c872"></a><a name="a36b1525ce4eb4b4a902894499694c872"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="26.507349265073493%" headers="mcps1.2.4.1.2 "><p id="a437e19270d3c45a9ba6bb2d0dd3818ca"><a name="a437e19270d3c45a9ba6bb2d0dd3818ca"></a><a name="a437e19270d3c45a9ba6bb2d0dd3818ca"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="a2484d62071634d99981015986f3c8faf"><a name="a2484d62071634d99981015986f3c8faf"></a><a name="a2484d62071634d99981015986f3c8faf"></a>资源对象的名称。</p>
</td>
</tr>
<tr id="r70d0edae05714a5ea61275024721373b"><td class="cellrowborder" valign="top" width="24.0975902409759%" headers="mcps1.2.4.1.1 "><p id="ae4adf2e5f3bf4620937b827e45e66682"><a name="ae4adf2e5f3bf4620937b827e45e66682"></a><a name="ae4adf2e5f3bf4620937b827e45e66682"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="26.507349265073493%" headers="mcps1.2.4.1.2 "><p id="af80ffaeca49c45c4bebe2232602f1839"><a name="af80ffaeca49c45c4bebe2232602f1839"></a><a name="af80ffaeca49c45c4bebe2232602f1839"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="adf363898799a47238dca0df0d77a34a9"><a name="adf363898799a47238dca0df0d77a34a9"></a><a name="adf363898799a47238dca0df0d77a34a9"></a>资源对象的ID。</p>
</td>
</tr>
<tr id="r5214e1f4f2e94d978714c841785db021"><td class="cellrowborder" valign="top" width="24.0975902409759%" headers="mcps1.2.4.1.1 "><p id="a0fb4b24dfe864a43aa57576a47b62d6b"><a name="a0fb4b24dfe864a43aa57576a47b62d6b"></a><a name="a0fb4b24dfe864a43aa57576a47b62d6b"></a>controller</p>
</td>
<td class="cellrowborder" valign="top" width="26.507349265073493%" headers="mcps1.2.4.1.2 "><p id="a88772f0c557f4e3c9326a539c9aea94f"><a name="a88772f0c557f4e3c9326a539c9aea94f"></a><a name="a88772f0c557f4e3c9326a539c9aea94f"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="a7001fc303bc94b8fab380110d692be60"><a name="a7001fc303bc94b8fab380110d692be60"></a><a name="a7001fc303bc94b8fab380110d692be60"></a>如果是true，则表示该资源对象被controller管理。</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{ 
   "kind": "Secret", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "mysecret", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/secrets/mysecret", 
     "uid": "597c306b-594e-11e6-b444-286ed488fafe", 
     "resourceVersion": "10742", 
     "creationTimestamp": "2016-08-03T07:46:12Z" 
   }, 
   "data": { 
    "password": "******",
    "username": "*****" 
   }, 
   "type": "Opaque" 
 }
```

## 状态码<a name="sff598d4e22514a58b84cd8ada7bf81ef"></a>

[表5](#zh-cn_topic_0079614927_table55351642)描述API的状态码。

**表 5**  状态码

<a name="zh-cn_topic_0079614927_table55351642"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614927_row10658099"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p23353744203114"><a name="p23353744203114"></a><a name="p23353744203114"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p12605125203114"><a name="p12605125203114"></a><a name="p12605125203114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614927_row28817734"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614927_p52535131"><a name="zh-cn_topic_0079614927_p52535131"></a><a name="zh-cn_topic_0079614927_p52535131"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614900_p44628050"><a name="zh-cn_topic_0079614900_p44628050"></a><a name="zh-cn_topic_0079614900_p44628050"></a>接口调用成功，返回查询的secret资源对象。</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

