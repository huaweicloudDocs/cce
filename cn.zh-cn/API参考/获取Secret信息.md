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
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p26301370"><a name="zh-cn_topic_0079614927_p26301370"></a><a name="zh-cn_topic_0079614927_p26301370"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row35385738"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p47672514"><a name="zh-cn_topic_0079614927_p47672514"></a><a name="zh-cn_topic_0079614927_p47672514"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p36268402"><a name="zh-cn_topic_0079614927_p36268402"></a><a name="zh-cn_topic_0079614927_p36268402"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p52059459"><a name="zh-cn_topic_0079614927_p52059459"></a><a name="zh-cn_topic_0079614927_p52059459"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row65881951"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p34837828"><a name="zh-cn_topic_0079614927_p34837828"></a><a name="zh-cn_topic_0079614927_p34837828"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p3291805"><a name="zh-cn_topic_0079614927_p3291805"></a><a name="zh-cn_topic_0079614927_p3291805"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p65309651"><a name="zh-cn_topic_0079614927_p65309651"></a><a name="zh-cn_topic_0079614927_p65309651"></a>Name of the Secret.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row8895702167"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p19896202160"><a name="zh-cn_topic_0079614927_p19896202160"></a><a name="zh-cn_topic_0079614927_p19896202160"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="a688fa776ec494137a4dc4d62383a2dc3"><a name="a688fa776ec494137a4dc4d62383a2dc3"></a><a name="a688fa776ec494137a4dc4d62383a2dc3"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p28969051618"><a name="zh-cn_topic_0079614927_p28969051618"></a><a name="zh-cn_topic_0079614927_p28969051618"></a>Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="rd0a38f8b45ce43d4b33530c1fb363adb"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="acf120ad7b3464dd3afd59acac130d10a"><a name="acf120ad7b3464dd3afd59acac130d10a"></a><a name="acf120ad7b3464dd3afd59acac130d10a"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p275914191162"><a name="zh-cn_topic_0079614927_p275914191162"></a><a name="zh-cn_topic_0079614927_p275914191162"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="41%" headers="mcps1.2.4.1.3 "><p id="a743d354f3c564a71bea87c0e96598b2d"><a name="a743d354f3c564a71bea87c0e96598b2d"></a><a name="a743d354f3c564a71bea87c0e96598b2d"></a>Should this value be exported. Export strips fields that a user can not specify.</p>
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
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p42746185"><a name="zh-cn_topic_0079614927_p42746185"></a><a name="zh-cn_topic_0079614927_p42746185"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row49171347"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p23456209"><a name="zh-cn_topic_0079614927_p23456209"></a><a name="zh-cn_topic_0079614927_p23456209"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p20904787"><a name="zh-cn_topic_0079614927_p20904787"></a><a name="zh-cn_topic_0079614927_p20904787"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p15566210"><a name="zh-cn_topic_0079614927_p15566210"></a><a name="zh-cn_topic_0079614927_p15566210"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
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
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="aa3f29c40161141a9bc895a80c070e251"><a name="aa3f29c40161141a9bc895a80c070e251"></a><a name="aa3f29c40161141a9bc895a80c070e251"></a>ata contains the secret data. Each key must be a valid DNS_SUBDOMAIN or leading dot followed by valid DNS_SUBDOMAIN. The serialized form of the secret data is a base64 encoded string, representing the arbitrary (possibly non-string) data value here.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row28293786"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p10095295"><a name="zh-cn_topic_0079614927_p10095295"></a><a name="zh-cn_topic_0079614927_p10095295"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p12412544"><a name="zh-cn_topic_0079614927_p12412544"></a><a name="zh-cn_topic_0079614927_p12412544"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p65892039"><a name="zh-cn_topic_0079614927_p65892039"></a><a name="zh-cn_topic_0079614927_p65892039"></a>Used to facilitate programmatic handling of secret data.</p>
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
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p40162211"><a name="zh-cn_topic_0079614927_p40162211"></a><a name="zh-cn_topic_0079614927_p40162211"></a>Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row25915585"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p18787663"><a name="zh-cn_topic_0079614927_p18787663"></a><a name="zh-cn_topic_0079614927_p18787663"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p45405709"><a name="zh-cn_topic_0079614927_p45405709"></a><a name="zh-cn_topic_0079614927_p45405709"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p53983779"><a name="zh-cn_topic_0079614927_p53983779"></a><a name="zh-cn_topic_0079614927_p53983779"></a>GenerateName is an optional prefix, used by the server, to generate a unique name ONLY IF the Name field has not been provided. If this field is used, the name returned to the client will be different than the name passed. This value will also be combined with a unique suffix. The provided value has the same validation rules as the Name field, and may be truncated by the length of the suffix required to make the value unique on the server.</p>
<p id="zh-cn_topic_0079614927_p16091967"><a name="zh-cn_topic_0079614927_p16091967"></a><a name="zh-cn_topic_0079614927_p16091967"></a>If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header).</p>
<p id="zh-cn_topic_0079614927_p10609978"><a name="zh-cn_topic_0079614927_p10609978"></a><a name="zh-cn_topic_0079614927_p10609978"></a>Applied only if Name is not specified.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row28380941"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p17154888"><a name="zh-cn_topic_0079614927_p17154888"></a><a name="zh-cn_topic_0079614927_p17154888"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p47368663"><a name="zh-cn_topic_0079614927_p47368663"></a><a name="zh-cn_topic_0079614927_p47368663"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p11656483"><a name="zh-cn_topic_0079614927_p11656483"></a><a name="zh-cn_topic_0079614927_p11656483"></a>Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty. Must be a DNS_LABEL. Cannot be updated.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row37799483"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p41859244"><a name="zh-cn_topic_0079614927_p41859244"></a><a name="zh-cn_topic_0079614927_p41859244"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p35155598"><a name="zh-cn_topic_0079614927_p35155598"></a><a name="zh-cn_topic_0079614927_p35155598"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p29031176"><a name="zh-cn_topic_0079614927_p29031176"></a><a name="zh-cn_topic_0079614927_p29031176"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row59953998"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p24435680"><a name="zh-cn_topic_0079614927_p24435680"></a><a name="zh-cn_topic_0079614927_p24435680"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p33133087"><a name="zh-cn_topic_0079614927_p33133087"></a><a name="zh-cn_topic_0079614927_p33133087"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p66534386"><a name="zh-cn_topic_0079614927_p66534386"></a><a name="zh-cn_topic_0079614927_p66534386"></a>UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row61938567"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p50968020"><a name="zh-cn_topic_0079614927_p50968020"></a><a name="zh-cn_topic_0079614927_p50968020"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p34768937"><a name="zh-cn_topic_0079614927_p34768937"></a><a name="zh-cn_topic_0079614927_p34768937"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p64820527"><a name="zh-cn_topic_0079614927_p64820527"></a><a name="zh-cn_topic_0079614927_p64820527"></a>An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources. Populated by the system. Read-only. Value must be treated as opaque by clients.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row46513836"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p9524349"><a name="zh-cn_topic_0079614927_p9524349"></a><a name="zh-cn_topic_0079614927_p9524349"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p33274836"><a name="zh-cn_topic_0079614927_p33274836"></a><a name="zh-cn_topic_0079614927_p33274836"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p10907158"><a name="zh-cn_topic_0079614927_p10907158"></a><a name="zh-cn_topic_0079614927_p10907158"></a>A sequence number representing a specific generation of the desired state. Currently only implemented by replication controllers. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row31055564"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p32472732"><a name="zh-cn_topic_0079614927_p32472732"></a><a name="zh-cn_topic_0079614927_p32472732"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p13045645"><a name="zh-cn_topic_0079614927_p13045645"></a><a name="zh-cn_topic_0079614927_p13045645"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p50064326"><a name="zh-cn_topic_0079614927_p50064326"></a><a name="zh-cn_topic_0079614927_p50064326"></a>CreationTimestamp is a timestamp representing the server time when this object was created. It is not guaranteed to be set in happens-before order across separate operations. Clients may not set this value. It is represented in RFC3339 form and is in UTC. Populated by the system. Read-only. Null for lists.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row47925758"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p56781175"><a name="zh-cn_topic_0079614927_p56781175"></a><a name="zh-cn_topic_0079614927_p56781175"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p35872461"><a name="zh-cn_topic_0079614927_p35872461"></a><a name="zh-cn_topic_0079614927_p35872461"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p19988199"><a name="zh-cn_topic_0079614927_p19988199"></a><a name="zh-cn_topic_0079614927_p19988199"></a>DeletionTimestamp is RFC 3339 date and time at which this resource will be deleted. This field is set by the server when a graceful deletion is requested by the user, and is not directly settable by a client. The resource will be deleted (no longer visible from resource lists, and not reachable by name) after the time in this field. Once set, this value may not be unset or be set further into the future, although it may be shortened or the resource may be deleted prior to this time. For example, a user may request that a pod is deleted in 30 seconds. The Kubelet will react by sending a graceful termination signal to the containers in the pod. Once the resource is deleted in the API, the Kubelet will send a hard termination signal to the container. If not set, graceful deletion of the object has not been requested. Populated by the system when a graceful deletion is requested. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row45676065"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p8773789"><a name="zh-cn_topic_0079614927_p8773789"></a><a name="zh-cn_topic_0079614927_p8773789"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p39588305"><a name="zh-cn_topic_0079614927_p39588305"></a><a name="zh-cn_topic_0079614927_p39588305"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p52536166"><a name="zh-cn_topic_0079614927_p52536166"></a><a name="zh-cn_topic_0079614927_p52536166"></a>Number of seconds allowed for this object to gracefully terminate before it will be removed from the system. Only set when deletionTimestamp is also set. May only be shortened. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row3063452"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p46813093"><a name="zh-cn_topic_0079614927_p46813093"></a><a name="zh-cn_topic_0079614927_p46813093"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p33764194"><a name="zh-cn_topic_0079614927_p33764194"></a><a name="zh-cn_topic_0079614927_p33764194"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p50545212"><a name="zh-cn_topic_0079614927_p50545212"></a><a name="zh-cn_topic_0079614927_p50545212"></a>Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614927_row52253727"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p4693486"><a name="zh-cn_topic_0079614927_p4693486"></a><a name="zh-cn_topic_0079614927_p4693486"></a>Annotations</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p44628110"><a name="zh-cn_topic_0079614927_p44628110"></a><a name="zh-cn_topic_0079614927_p44628110"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614927_p58107175"><a name="zh-cn_topic_0079614927_p58107175"></a><a name="zh-cn_topic_0079614927_p58107175"></a>Annotations is an unstructured key value map stored with a resource that may be set by external tools to store and retrieve arbitrary metadata. They are not queryable and should be preserved when modifying objects.</p>
</td>
</tr>
<tr id="r9f8905c2e7b441419117d2bc6f46baea"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a8a1e39bea6d94f2692a45140018e13b9"><a name="a8a1e39bea6d94f2692a45140018e13b9"></a><a name="a8a1e39bea6d94f2692a45140018e13b9"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="a2fad25498b674e40937f6e88b4e8099c"><a name="a2fad25498b674e40937f6e88b4e8099c"></a><a name="a2fad25498b674e40937f6e88b4e8099c"></a><a href="#tcba7b62965f94a85b2111568e64bf277">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a5f93733c20a6487cb7b69526885e4298"><a name="a5f93733c20a6487cb7b69526885e4298"></a><a name="a5f93733c20a6487cb7b69526885e4298"></a>List of objects depended by this object. If ALL objects in the list have been deleted, this object will be garbage collected. If this object is managed by a controller, then an entry in this list will point to this controller, with the controller field set to true. There cannot be more than one managing controller.</p>
</td>
</tr>
<tr id="r8b930028b27043558a2e43034bbf289a"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614927_p9160517169"><a name="zh-cn_topic_0079614927_p9160517169"></a><a name="zh-cn_topic_0079614927_p9160517169"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614927_p742001917169"><a name="zh-cn_topic_0079614927_p742001917169"></a><a name="zh-cn_topic_0079614927_p742001917169"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a69e1b2402dce4f358aeab4184e6cf280"><a name="a69e1b2402dce4f358aeab4184e6cf280"></a><a name="a69e1b2402dce4f358aeab4184e6cf280"></a>Must be empty before the object is deleted from the registry. Each entry is an identifier for the responsible component that will remove the entry from the list. If the deletionTimestamp of the object is non-nil, entries in this list can only be removed.</p>
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
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="a0d4a6430678e474d84b2acbec3a632e5"><a name="a0d4a6430678e474d84b2acbec3a632e5"></a><a name="a0d4a6430678e474d84b2acbec3a632e5"></a>API version of the referent.</p>
</td>
</tr>
<tr id="r9f429c7df9e446efbffca38d4fca1ca7"><td class="cellrowborder" valign="top" width="24.0975902409759%" headers="mcps1.2.4.1.1 "><p id="a02456892c5454c84bd3fd3caa55d0489"><a name="a02456892c5454c84bd3fd3caa55d0489"></a><a name="a02456892c5454c84bd3fd3caa55d0489"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="26.507349265073493%" headers="mcps1.2.4.1.2 "><p id="a0ed2bd4b0d59460c9e74c3251ea3cd8f"><a name="a0ed2bd4b0d59460c9e74c3251ea3cd8f"></a><a name="a0ed2bd4b0d59460c9e74c3251ea3cd8f"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="acc5561b1b0054836af0acb63debebd2e"><a name="acc5561b1b0054836af0acb63debebd2e"></a><a name="acc5561b1b0054836af0acb63debebd2e"></a>Kind of the referent.</p>
</td>
</tr>
<tr id="r380a9238b04440a2b9e5eee6cb77e03f"><td class="cellrowborder" valign="top" width="24.0975902409759%" headers="mcps1.2.4.1.1 "><p id="a36b1525ce4eb4b4a902894499694c872"><a name="a36b1525ce4eb4b4a902894499694c872"></a><a name="a36b1525ce4eb4b4a902894499694c872"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="26.507349265073493%" headers="mcps1.2.4.1.2 "><p id="a437e19270d3c45a9ba6bb2d0dd3818ca"><a name="a437e19270d3c45a9ba6bb2d0dd3818ca"></a><a name="a437e19270d3c45a9ba6bb2d0dd3818ca"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="a9577aa5a10a343ac933a257fc36963d7"><a name="a9577aa5a10a343ac933a257fc36963d7"></a><a name="a9577aa5a10a343ac933a257fc36963d7"></a>Name of the referent.</p>
</td>
</tr>
<tr id="r70d0edae05714a5ea61275024721373b"><td class="cellrowborder" valign="top" width="24.0975902409759%" headers="mcps1.2.4.1.1 "><p id="ae4adf2e5f3bf4620937b827e45e66682"><a name="ae4adf2e5f3bf4620937b827e45e66682"></a><a name="ae4adf2e5f3bf4620937b827e45e66682"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="26.507349265073493%" headers="mcps1.2.4.1.2 "><p id="af80ffaeca49c45c4bebe2232602f1839"><a name="af80ffaeca49c45c4bebe2232602f1839"></a><a name="af80ffaeca49c45c4bebe2232602f1839"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="adf363898799a47238dca0df0d77a34a9"><a name="adf363898799a47238dca0df0d77a34a9"></a><a name="adf363898799a47238dca0df0d77a34a9"></a>UID of the referent.</p>
</td>
</tr>
<tr id="r5214e1f4f2e94d978714c841785db021"><td class="cellrowborder" valign="top" width="24.0975902409759%" headers="mcps1.2.4.1.1 "><p id="a0fb4b24dfe864a43aa57576a47b62d6b"><a name="a0fb4b24dfe864a43aa57576a47b62d6b"></a><a name="a0fb4b24dfe864a43aa57576a47b62d6b"></a>controller</p>
</td>
<td class="cellrowborder" valign="top" width="26.507349265073493%" headers="mcps1.2.4.1.2 "><p id="a88772f0c557f4e3c9326a539c9aea94f"><a name="a88772f0c557f4e3c9326a539c9aea94f"></a><a name="a88772f0c557f4e3c9326a539c9aea94f"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="49.3950604939506%" headers="mcps1.2.4.1.3 "><p id="a7001fc303bc94b8fab380110d692be60"><a name="a7001fc303bc94b8fab380110d692be60"></a><a name="a7001fc303bc94b8fab380110d692be60"></a>If true, this reference points to the managing controller.</p>
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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614927_p27487204"><a name="zh-cn_topic_0079614927_p27487204"></a><a name="zh-cn_topic_0079614927_p27487204"></a>This operation succeeds, and a secret resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

