# 获取指定的Service<a name="cce_02_0027"></a>

## 功能介绍<a name="s6b63abeb0a574a7a9c13de5369a91cd8"></a>

该API用于获取指定的Service对象。

## URI<a name="s2a208d531ff9407b93924d7c313193b8"></a>

GET /api/v1/namespaces/\{namespace\}/services/\{name\}

[表1](#zh-cn_topic_0079614941_table43974095)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614941_table43974095"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614941_row47185870"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614941_p63959112"><a name="zh-cn_topic_0079614941_p63959112"></a><a name="zh-cn_topic_0079614941_p63959112"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.2"><p id="p54432917195332"><a name="p54432917195332"></a><a name="p54432917195332"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="42%" id="mcps1.2.4.1.3"><p id="p46990176195332"><a name="p46990176195332"></a><a name="p46990176195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614941_row56542298"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p16523463"><a name="zh-cn_topic_0079614941_p16523463"></a><a name="zh-cn_topic_0079614941_p16523463"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p63332116"><a name="zh-cn_topic_0079614941_p63332116"></a><a name="zh-cn_topic_0079614941_p63332116"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p29627753"><a name="zh-cn_topic_0079614941_p29627753"></a><a name="zh-cn_topic_0079614941_p29627753"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row65323191"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p56687084"><a name="zh-cn_topic_0079614941_p56687084"></a><a name="zh-cn_topic_0079614941_p56687084"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p28251069"><a name="zh-cn_topic_0079614941_p28251069"></a><a name="zh-cn_topic_0079614941_p28251069"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p6635284"><a name="zh-cn_topic_0079614941_p6635284"></a><a name="zh-cn_topic_0079614941_p6635284"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row59717556"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p5283852"><a name="zh-cn_topic_0079614941_p5283852"></a><a name="zh-cn_topic_0079614941_p5283852"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p25338844"><a name="zh-cn_topic_0079614941_p25338844"></a><a name="zh-cn_topic_0079614941_p25338844"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p39180493"><a name="zh-cn_topic_0079614941_p39180493"></a><a name="zh-cn_topic_0079614941_p39180493"></a>Name of the Service.</p>
</td>
</tr>
<tr id="r0af24e6998b447a7b420c9ba8d740997"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="a90c1431310924496a5cc65d5b4246e84"><a name="a90c1431310924496a5cc65d5b4246e84"></a><a name="a90c1431310924496a5cc65d5b4246e84"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="a5209f92e2e0a4d0cbd92d02f2828855c"><a name="a5209f92e2e0a4d0cbd92d02f2828855c"></a><a name="a5209f92e2e0a4d0cbd92d02f2828855c"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="a69e76f9c221f4f5aad657379aae91d95"><a name="a69e76f9c221f4f5aad657379aae91d95"></a><a name="a69e76f9c221f4f5aad657379aae91d95"></a>Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="r96bb6bf9ae1440009077fa844f28a88e"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p151474572434"><a name="zh-cn_topic_0079614941_p151474572434"></a><a name="zh-cn_topic_0079614941_p151474572434"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="a0aa4cab1194c44d2b2658f322b9fd0fc"><a name="a0aa4cab1194c44d2b2658f322b9fd0fc"></a><a name="a0aa4cab1194c44d2b2658f322b9fd0fc"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p114755710438"><a name="zh-cn_topic_0079614941_p114755710438"></a><a name="zh-cn_topic_0079614941_p114755710438"></a>Should this value be exported. Export strips fields that a user can not specify.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s24d2fb0a92bc4481b97f1980a208a6ec"></a>

N/A

## 响应消息<a name="s058feaad90fa4e52a6d698f3cd609786"></a>

**响应参数：**

响应参数如[表2](#zh-cn_topic_0079614941_ref458765062)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079614941_ref458765062"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614941_row38964390"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614941_p1999044"><a name="zh-cn_topic_0079614941_p1999044"></a><a name="zh-cn_topic_0079614941_p1999044"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p60550309195332"><a name="p60550309195332"></a><a name="p60550309195332"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p5627969195332"><a name="p5627969195332"></a><a name="p5627969195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614941_row40717663"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p9796398"><a name="zh-cn_topic_0079614941_p9796398"></a><a name="zh-cn_topic_0079614941_p9796398"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p55310798"><a name="zh-cn_topic_0079614941_p55310798"></a><a name="zh-cn_topic_0079614941_p55310798"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p50989671"><a name="zh-cn_topic_0079614941_p50989671"></a><a name="zh-cn_topic_0079614941_p50989671"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row56253856"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p60268448"><a name="zh-cn_topic_0079614941_p60268448"></a><a name="zh-cn_topic_0079614941_p60268448"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p49906092"><a name="zh-cn_topic_0079614941_p49906092"></a><a name="zh-cn_topic_0079614941_p49906092"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p15861677"><a name="zh-cn_topic_0079614941_p15861677"></a><a name="zh-cn_topic_0079614941_p15861677"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row8537373"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p20438632"><a name="zh-cn_topic_0079614941_p20438632"></a><a name="zh-cn_topic_0079614941_p20438632"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p44916508"><a name="zh-cn_topic_0079614941_p44916508"></a><a name="zh-cn_topic_0079614941_p44916508"></a><a href="#zh-cn_topic_0079614941_ref458764998">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p62117599"><a name="zh-cn_topic_0079614941_p62117599"></a><a name="zh-cn_topic_0079614941_p62117599"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row22187484"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p52355769"><a name="zh-cn_topic_0079614941_p52355769"></a><a name="zh-cn_topic_0079614941_p52355769"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p12958878"><a name="zh-cn_topic_0079614941_p12958878"></a><a name="zh-cn_topic_0079614941_p12958878"></a><a href="#zh-cn_topic_0079614941_table60222542">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p51781593"><a name="zh-cn_topic_0079614941_p51781593"></a><a name="zh-cn_topic_0079614941_p51781593"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row63381154"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p33599889"><a name="zh-cn_topic_0079614941_p33599889"></a><a name="zh-cn_topic_0079614941_p33599889"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p37236521"><a name="zh-cn_topic_0079614941_p37236521"></a><a name="zh-cn_topic_0079614941_p37236521"></a><a href="#zh-cn_topic_0079614941_table5131967">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p33442970"><a name="zh-cn_topic_0079614941_p33442970"></a><a name="zh-cn_topic_0079614941_p33442970"></a>-</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="zh-cn_topic_0079614941_ref458764998"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614941_row38043720"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614941_p61642459"><a name="zh-cn_topic_0079614941_p61642459"></a><a name="zh-cn_topic_0079614941_p61642459"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p3061210195332"><a name="p3061210195332"></a><a name="p3061210195332"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p46631457195332"><a name="p46631457195332"></a><a name="p46631457195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614941_row3949862"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p51503435"><a name="zh-cn_topic_0079614941_p51503435"></a><a name="zh-cn_topic_0079614941_p51503435"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p11028729"><a name="zh-cn_topic_0079614941_p11028729"></a><a name="zh-cn_topic_0079614941_p11028729"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p20911831"><a name="zh-cn_topic_0079614941_p20911831"></a><a name="zh-cn_topic_0079614941_p20911831"></a>Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated.</p>
</td>
</tr>
<tr id="r23e41c48101b42d4ba6c17522f707dff"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p125271586440"><a name="zh-cn_topic_0079614941_p125271586440"></a><a name="zh-cn_topic_0079614941_p125271586440"></a>clusterName</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p552765813443"><a name="zh-cn_topic_0079614941_p552765813443"></a><a name="zh-cn_topic_0079614941_p552765813443"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p85276589448"><a name="zh-cn_topic_0079614941_p85276589448"></a><a name="zh-cn_topic_0079614941_p85276589448"></a>The name of the cluster which the object belongs to. This is used to distinguish resources with same name and namespace in different clusters. This field is not set anywhere right now and apiserver is going to ignore it if set in create or update request.</p>
</td>
</tr>
<tr id="r3854f4b6d14c4d528607b630afccb48f"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a0ae58910b8da4a0297e9a6ae4c066679"><a name="a0ae58910b8da4a0297e9a6ae4c066679"></a><a name="a0ae58910b8da4a0297e9a6ae4c066679"></a>initializers</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="a199187bb15a94798be9ceff3e50a1701"><a name="a199187bb15a94798be9ceff3e50a1701"></a><a name="a199187bb15a94798be9ceff3e50a1701"></a><a href="响应数据结构.md#t050e77dc2b1644c895d89f389e46d859">initializers</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a0ce09cd1010e405aa6363e10cdc6908c"><a name="a0ce09cd1010e405aa6363e10cdc6908c"></a><a name="a0ce09cd1010e405aa6363e10cdc6908c"></a>An initializer is a controller which enforces some system invariant at object creation time. This field is a list of initializers that have not yet acted on this object. If nil or empty, this object has been completely initialized. Otherwise, the object is considered uninitialized and is hidden (in list/watch and get calls) from clients that haven't explicitly asked to observe uninitialized objects. When an object is created, the system will populate this list with the current set of initializers. Only privileged users may set or modify this list. Once it is empty, it may not be modified further by any user.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row53988751"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p11012729"><a name="zh-cn_topic_0079614941_p11012729"></a><a name="zh-cn_topic_0079614941_p11012729"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p19615847"><a name="zh-cn_topic_0079614941_p19615847"></a><a name="zh-cn_topic_0079614941_p19615847"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p45379778"><a name="zh-cn_topic_0079614941_p45379778"></a><a name="zh-cn_topic_0079614941_p45379778"></a>GenerateName is an optional prefix, used by the server, to generate a unique name ONLY IF the Name field has not been provided. If this field is used, the name returned to the client will be different than the name passed. This value will also be combined with a unique suffix. The provided value has the same validation rules as the Name field, and may be truncated by the length of the suffix required to make the value unique on the server.</p>
<p id="zh-cn_topic_0079614941_p5764819"><a name="zh-cn_topic_0079614941_p5764819"></a><a name="zh-cn_topic_0079614941_p5764819"></a>If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header).</p>
<p id="zh-cn_topic_0079614941_p51883377"><a name="zh-cn_topic_0079614941_p51883377"></a><a name="zh-cn_topic_0079614941_p51883377"></a>Applied only if Name is not specified.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row64297212"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p40691653"><a name="zh-cn_topic_0079614941_p40691653"></a><a name="zh-cn_topic_0079614941_p40691653"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p7689558"><a name="zh-cn_topic_0079614941_p7689558"></a><a name="zh-cn_topic_0079614941_p7689558"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p18874456"><a name="zh-cn_topic_0079614941_p18874456"></a><a name="zh-cn_topic_0079614941_p18874456"></a>Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty. Must be a DNS_LABEL. Cannot be updated.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row35652378"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p2161544"><a name="zh-cn_topic_0079614941_p2161544"></a><a name="zh-cn_topic_0079614941_p2161544"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p40867386"><a name="zh-cn_topic_0079614941_p40867386"></a><a name="zh-cn_topic_0079614941_p40867386"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p21923993"><a name="zh-cn_topic_0079614941_p21923993"></a><a name="zh-cn_topic_0079614941_p21923993"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row63098212"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p10681585"><a name="zh-cn_topic_0079614941_p10681585"></a><a name="zh-cn_topic_0079614941_p10681585"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p59902046"><a name="zh-cn_topic_0079614941_p59902046"></a><a name="zh-cn_topic_0079614941_p59902046"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p20227539"><a name="zh-cn_topic_0079614941_p20227539"></a><a name="zh-cn_topic_0079614941_p20227539"></a>UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row47830129"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p49035206"><a name="zh-cn_topic_0079614941_p49035206"></a><a name="zh-cn_topic_0079614941_p49035206"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p12428727"><a name="zh-cn_topic_0079614941_p12428727"></a><a name="zh-cn_topic_0079614941_p12428727"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p93998"><a name="zh-cn_topic_0079614941_p93998"></a><a name="zh-cn_topic_0079614941_p93998"></a>An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources. Populated by the system. Read-only. Value must be treated as opaque by clients.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row845982"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p1415702"><a name="zh-cn_topic_0079614941_p1415702"></a><a name="zh-cn_topic_0079614941_p1415702"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p47563014"><a name="zh-cn_topic_0079614941_p47563014"></a><a name="zh-cn_topic_0079614941_p47563014"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p27398935"><a name="zh-cn_topic_0079614941_p27398935"></a><a name="zh-cn_topic_0079614941_p27398935"></a>A sequence number representing a specific generation of the desired state. Currently only implemented by replication controllers. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row45263827"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p42491384"><a name="zh-cn_topic_0079614941_p42491384"></a><a name="zh-cn_topic_0079614941_p42491384"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p19250065"><a name="zh-cn_topic_0079614941_p19250065"></a><a name="zh-cn_topic_0079614941_p19250065"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p15751431"><a name="zh-cn_topic_0079614941_p15751431"></a><a name="zh-cn_topic_0079614941_p15751431"></a>CreationTimestamp is a timestamp representing the server time when this object was created. It is not guaranteed to be set in happens-before order across separate operations. Clients may not set this value. It is represented in RFC3339 form and is in UTC. Populated by the system. Read-only. Null for lists.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row7545152"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p7177547"><a name="zh-cn_topic_0079614941_p7177547"></a><a name="zh-cn_topic_0079614941_p7177547"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p44510439"><a name="zh-cn_topic_0079614941_p44510439"></a><a name="zh-cn_topic_0079614941_p44510439"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p48575803"><a name="zh-cn_topic_0079614941_p48575803"></a><a name="zh-cn_topic_0079614941_p48575803"></a>DeletionTimestamp is RFC 3339 date and time at which this resource will be deleted. This field is set by the server when a graceful deletion is requested by the user, and is not directly settable by a client. The resource will be deleted (no longer visible from resource lists, and not reachable by name) after the time in this field. Once set, this value may not be unset or be set further into the future, although it may be shortened or the resource may be deleted prior to this time. For example, a user may request that a pod is deleted in 30 seconds. The Kubelet will react by sending a graceful termination signal to the containers in the pod. Once the resource is deleted in the API, the Kubelet will send a hard termination signal to the container. If not set, graceful deletion of the object has not been requested. Populated by the system when a graceful deletion is requested. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row34529050"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p45389686"><a name="zh-cn_topic_0079614941_p45389686"></a><a name="zh-cn_topic_0079614941_p45389686"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p52685983"><a name="zh-cn_topic_0079614941_p52685983"></a><a name="zh-cn_topic_0079614941_p52685983"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p39706236"><a name="zh-cn_topic_0079614941_p39706236"></a><a name="zh-cn_topic_0079614941_p39706236"></a>Number of seconds allowed for this object to gracefully terminate before it will be removed from the system. Only set when deletionTimestamp is also set. May only be shortened. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row21811810"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p21926185"><a name="zh-cn_topic_0079614941_p21926185"></a><a name="zh-cn_topic_0079614941_p21926185"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p31190552"><a name="zh-cn_topic_0079614941_p31190552"></a><a name="zh-cn_topic_0079614941_p31190552"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p43406808"><a name="zh-cn_topic_0079614941_p43406808"></a><a name="zh-cn_topic_0079614941_p43406808"></a>Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row55116958"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p35288602"><a name="zh-cn_topic_0079614941_p35288602"></a><a name="zh-cn_topic_0079614941_p35288602"></a>Annotations</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p39804474"><a name="zh-cn_topic_0079614941_p39804474"></a><a name="zh-cn_topic_0079614941_p39804474"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p2936934"><a name="zh-cn_topic_0079614941_p2936934"></a><a name="zh-cn_topic_0079614941_p2936934"></a>Annotations is an unstructured key value map stored with a resource that may be set by external tools to store and retrieve arbitrary metadata. They are not queryable and should be preserved when modifying objects.</p>
</td>
</tr>
<tr id="r2feaee3b298b45c5bf6d2c10a248a241"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p555409218048"><a name="zh-cn_topic_0079614941_p555409218048"></a><a name="zh-cn_topic_0079614941_p555409218048"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="aa9fd857ab00a48298e3fe2e5afab75be"><a name="aa9fd857ab00a48298e3fe2e5afab75be"></a><a name="aa9fd857ab00a48298e3fe2e5afab75be"></a><a href="#ta7d3233a62ea4c8a98f6ade04f4fb53b">ownerReferences</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="aba65636a2bce42bd9745719f9cf6ed9a"><a name="aba65636a2bce42bd9745719f9cf6ed9a"></a><a name="aba65636a2bce42bd9745719f9cf6ed9a"></a>List of objects depended by this object. If ALL objects in the list have been deleted, this object will be garbage collected. If this object is managed by a controller, then an entry in this list will point to this controller, with the controller field set to true. There cannot be more than one managing controller.</p>
</td>
</tr>
<tr id="r6fcc72de7a7942ab85a1b97640bd7fde"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p734471418048"><a name="zh-cn_topic_0079614941_p734471418048"></a><a name="zh-cn_topic_0079614941_p734471418048"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="aa8dd99bd7f2841bb88425a9813c1b885"><a name="aa8dd99bd7f2841bb88425a9813c1b885"></a><a name="aa8dd99bd7f2841bb88425a9813c1b885"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a37178eacb11e4c7e9ea8539ab3bbfe1d"><a name="a37178eacb11e4c7e9ea8539ab3bbfe1d"></a><a name="a37178eacb11e4c7e9ea8539ab3bbfe1d"></a>Must be empty before the object is deleted from the registry. Each entry is an identifier for the responsible component that will remove the entry from the list. If the deletionTimestamp of the object is non-nil, entries in this list can only be removed.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  spec字段数据结构说明

<a name="zh-cn_topic_0079614941_table60222542"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614941_row13231337"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614941_p65105414"><a name="zh-cn_topic_0079614941_p65105414"></a><a name="zh-cn_topic_0079614941_p65105414"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p63399386195332"><a name="p63399386195332"></a><a name="p63399386195332"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p35076659195332"><a name="p35076659195332"></a><a name="p35076659195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614941_row33956798"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p66146124"><a name="zh-cn_topic_0079614941_p66146124"></a><a name="zh-cn_topic_0079614941_p66146124"></a>ports</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p56235867"><a name="zh-cn_topic_0079614941_p56235867"></a><a name="zh-cn_topic_0079614941_p56235867"></a><a href="#zh-cn_topic_0079614941_table46187709">ports</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p59540653"><a name="zh-cn_topic_0079614941_p59540653"></a><a name="zh-cn_topic_0079614941_p59540653"></a>The list of ports that are exposed by this service.</p>
</td>
</tr>
<tr id="rf9bb0f53ddd64b69893f584c49961967"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a1fdcd0a30a8e4010abdc099c4e1ca6c8"><a name="a1fdcd0a30a8e4010abdc099c4e1ca6c8"></a><a name="a1fdcd0a30a8e4010abdc099c4e1ca6c8"></a>selector</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="a2d433ce106114e4fb2d58e1159bf202e"><a name="a2d433ce106114e4fb2d58e1159bf202e"></a><a name="a2d433ce106114e4fb2d58e1159bf202e"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a8f8b6e4437244e8a9e082f0937bf9015"><a name="a8f8b6e4437244e8a9e082f0937bf9015"></a><a name="a8f8b6e4437244e8a9e082f0937bf9015"></a>This service will route traffic to pods having labels matching this selector. Label keys and values that must match in order to receive traffic for this service. If empty, all pods are selected, if not specified, endpoints must be manually specified.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row66103835"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p52810395"><a name="zh-cn_topic_0079614941_p52810395"></a><a name="zh-cn_topic_0079614941_p52810395"></a>clusterIP</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p49783612"><a name="zh-cn_topic_0079614941_p49783612"></a><a name="zh-cn_topic_0079614941_p49783612"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p5940773"><a name="zh-cn_topic_0079614941_p5940773"></a><a name="zh-cn_topic_0079614941_p5940773"></a>ClusterIP is usually assigned by the master and is the IP address of the service. If specified, it will be allocated to the service if it is unused or else creation of the service will fail. Valid values are None, empty string (""), or a valid IP address. 'None' can be specified for a headless service when proxying is not required. Cannot be updated.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row53466965"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p35856894"><a name="zh-cn_topic_0079614941_p35856894"></a><a name="zh-cn_topic_0079614941_p35856894"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p18727300"><a name="zh-cn_topic_0079614941_p18727300"></a><a name="zh-cn_topic_0079614941_p18727300"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p40516302"><a name="zh-cn_topic_0079614941_p40516302"></a><a name="zh-cn_topic_0079614941_p40516302"></a>Type of exposed service. Must be ClusterIP, NodePort, or LoadBalancer. Defaults to ClusterIP.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row29102400"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p8484204"><a name="zh-cn_topic_0079614941_p8484204"></a><a name="zh-cn_topic_0079614941_p8484204"></a>externalIPs</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p16131920"><a name="zh-cn_topic_0079614941_p16131920"></a><a name="zh-cn_topic_0079614941_p16131920"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p31617173"><a name="zh-cn_topic_0079614941_p31617173"></a><a name="zh-cn_topic_0079614941_p31617173"></a>externalIPs is a list of IP addresses for which nodes in the cluster will also accept traffic for this service. These IPs are not managed by Kubernetes. The user is responsible for ensuring that traffic arrives at a node with this IP. A common example is external load-balancers that are not part of the Kubernetes system. A previous form of this functionality exists as the deprecatedPublicIPs field. When using this field, callers should also clear the deprecatedPublicIPs field.</p>
</td>
</tr>
<tr id="r5f8aebacc89f494bb183b5e5b17bda7a"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p37641971469"><a name="zh-cn_topic_0079614941_p37641971469"></a><a name="zh-cn_topic_0079614941_p37641971469"></a>healthCheckNodePort</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p876419714611"><a name="zh-cn_topic_0079614941_p876419714611"></a><a name="zh-cn_topic_0079614941_p876419714611"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a37b4242ed2aa472681d9fc65e14e3bad"><a name="a37b4242ed2aa472681d9fc65e14e3bad"></a><a name="a37b4242ed2aa472681d9fc65e14e3bad"></a>healthCheckNodePort specifies the healthcheck nodePort for the service. If not specified, HealthCheckNodePort is created by the service api backend with the allocated nodePort. Will use user-specified nodePort value if specified by the client. Only effects when Type is set to LoadBalancer and ExternalTrafficPolicy is set to Local.</p>
</td>
</tr>
<tr id="rf079e1b02a394209a2ee54522967f6e2"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p581113313462"><a name="zh-cn_topic_0079614941_p581113313462"></a><a name="zh-cn_topic_0079614941_p581113313462"></a>loadBalancerSourceRanges</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="a99c1692ff1e2455ebb84aad24f2696a2"><a name="a99c1692ff1e2455ebb84aad24f2696a2"></a><a name="a99c1692ff1e2455ebb84aad24f2696a2"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a8b4988d66da84be79c2bf73d1b7e9fc4"><a name="a8b4988d66da84be79c2bf73d1b7e9fc4"></a><a name="a8b4988d66da84be79c2bf73d1b7e9fc4"></a>If specified and supported by the platform, this will restrict traffic through the cloud-provider load-balancer will be restricted to the specified client IPs. This field will be ignored if the cloud-provider does not support the feature.</p>
</td>
</tr>
<tr id="r8a7fe1bbe6d44a59b89f76ec2f339daf"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a8dee5f1a26024a6eb5d0be05f8c8a1be"><a name="a8dee5f1a26024a6eb5d0be05f8c8a1be"></a><a name="a8dee5f1a26024a6eb5d0be05f8c8a1be"></a>externalName</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="a47d50fbcb33249f9a80a507d4a139ba5"><a name="a47d50fbcb33249f9a80a507d4a139ba5"></a><a name="a47d50fbcb33249f9a80a507d4a139ba5"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a228bda9a0f4345b5a67369cd15fa31fb"><a name="a228bda9a0f4345b5a67369cd15fa31fb"></a><a name="a228bda9a0f4345b5a67369cd15fa31fb"></a>externalName is the external reference that kubedns or equivalent will return as a CNAME record for this service. No proxying will be involved. Must be a valid DNS name and requires Type to be ExternalName.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row16119107"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p30579324"><a name="zh-cn_topic_0079614941_p30579324"></a><a name="zh-cn_topic_0079614941_p30579324"></a>deprecatedPublicIPs</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p61006185"><a name="zh-cn_topic_0079614941_p61006185"></a><a name="zh-cn_topic_0079614941_p61006185"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p42553971"><a name="zh-cn_topic_0079614941_p42553971"></a><a name="zh-cn_topic_0079614941_p42553971"></a>deprecatedPublicIPs is deprecated and replaced by the externalIPs field with almost the exact same semantics. This field is retained in the v1 API for compatibility until at least 8/20/2016. It will be removed from any new API revisions. If both deprecatedPublicIPs and externalIPs are set, deprecatedPublicIPs is used.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row47441422"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p17549965"><a name="zh-cn_topic_0079614941_p17549965"></a><a name="zh-cn_topic_0079614941_p17549965"></a>sessionAffinity</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p12261085"><a name="zh-cn_topic_0079614941_p12261085"></a><a name="zh-cn_topic_0079614941_p12261085"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p53623846"><a name="zh-cn_topic_0079614941_p53623846"></a><a name="zh-cn_topic_0079614941_p53623846"></a>Supports "ClientIP" and "None". Used to maintain session affinity. Enable client IP based session affinity. Must be ClientIP or None. Defaults to None.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row12852567"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p34424967"><a name="zh-cn_topic_0079614941_p34424967"></a><a name="zh-cn_topic_0079614941_p34424967"></a>loadBalancerIP</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p36958915"><a name="zh-cn_topic_0079614941_p36958915"></a><a name="zh-cn_topic_0079614941_p36958915"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p40882164"><a name="zh-cn_topic_0079614941_p40882164"></a><a name="zh-cn_topic_0079614941_p40882164"></a>Only applies to Service Type: LoadBalancer LoadBalancer will get created with the IP specified in this field. This feature depends on whether the underlying cloud-provider supports specifying the loadBalancerIP when a load balancer is created. This field will be ignored if the cloud-provider does not support the feature.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  status字段数据结构说明

<a name="zh-cn_topic_0079614941_table5131967"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614941_row123163"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614941_p9976232"><a name="zh-cn_topic_0079614941_p9976232"></a><a name="zh-cn_topic_0079614941_p9976232"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p31169058195332"><a name="p31169058195332"></a><a name="p31169058195332"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p41665746195332"><a name="p41665746195332"></a><a name="p41665746195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614941_row44378785"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p37911872"><a name="zh-cn_topic_0079614941_p37911872"></a><a name="zh-cn_topic_0079614941_p37911872"></a>loadBalancer</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p50962824"><a name="zh-cn_topic_0079614941_p50962824"></a><a name="zh-cn_topic_0079614941_p50962824"></a><a href="#zh-cn_topic_0079614941_table13036200">loadBalancer</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p40697121"><a name="zh-cn_topic_0079614941_p40697121"></a><a name="zh-cn_topic_0079614941_p40697121"></a>-</p>
</td>
</tr>
</tbody>
</table>

**表 6**  ownerReferences字段数据结构说明

<a name="ta7d3233a62ea4c8a98f6ade04f4fb53b"></a>
<table><thead align="left"><tr id="r1615626fe7364f95828ccaca388dfcc1"><th class="cellrowborder" valign="top" width="24%" id="mcps1.2.4.1.1"><p id="a40471e2c1e5546f6b0b1c3d0447f81bf"><a name="a40471e2c1e5546f6b0b1c3d0447f81bf"></a><a name="a40471e2c1e5546f6b0b1c3d0447f81bf"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="31%" id="mcps1.2.4.1.2"><p id="p17445963195332"><a name="p17445963195332"></a><a name="p17445963195332"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p3836904195332"><a name="p3836904195332"></a><a name="p3836904195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r2a2bb87e1eae44e69cec9408439db939"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.1 "><p id="a0049648c303d457593c9d98311db236d"><a name="a0049648c303d457593c9d98311db236d"></a><a name="a0049648c303d457593c9d98311db236d"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="31%" headers="mcps1.2.4.1.2 "><p id="a27368c93aa87439cb687de6fbbedf1bf"><a name="a27368c93aa87439cb687de6fbbedf1bf"></a><a name="a27368c93aa87439cb687de6fbbedf1bf"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="a59e6707a6d874d81bf2ad93afc49e9c2"><a name="a59e6707a6d874d81bf2ad93afc49e9c2"></a><a name="a59e6707a6d874d81bf2ad93afc49e9c2"></a>API version of the referent.</p>
</td>
</tr>
<tr id="radf556694b374586ae554ba0d4dc858b"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.1 "><p id="a6a8a9bf7c0ff4b37828863b7a1351762"><a name="a6a8a9bf7c0ff4b37828863b7a1351762"></a><a name="a6a8a9bf7c0ff4b37828863b7a1351762"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="31%" headers="mcps1.2.4.1.2 "><p id="a2e1552ec3fdc433ca5db3879cb619dee"><a name="a2e1552ec3fdc433ca5db3879cb619dee"></a><a name="a2e1552ec3fdc433ca5db3879cb619dee"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="a8bf43cd75ac74b3eae8103fba349378d"><a name="a8bf43cd75ac74b3eae8103fba349378d"></a><a name="a8bf43cd75ac74b3eae8103fba349378d"></a>Kind of the referent.</p>
</td>
</tr>
<tr id="rf91c449b45f1443ab9e24aab574a9131"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.1 "><p id="a79c433be11b8432a86260a70110b182b"><a name="a79c433be11b8432a86260a70110b182b"></a><a name="a79c433be11b8432a86260a70110b182b"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="31%" headers="mcps1.2.4.1.2 "><p id="ac8dd2459a88c4ee88add294f219e1a6f"><a name="ac8dd2459a88c4ee88add294f219e1a6f"></a><a name="ac8dd2459a88c4ee88add294f219e1a6f"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="a122863c903fd423b94e250629ec5e3e8"><a name="a122863c903fd423b94e250629ec5e3e8"></a><a name="a122863c903fd423b94e250629ec5e3e8"></a>Name of the referent.</p>
</td>
</tr>
<tr id="r5c9c2282d6334aea8384937b67612c64"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.1 "><p id="ac4a717598ee74867891890a5fae06129"><a name="ac4a717598ee74867891890a5fae06129"></a><a name="ac4a717598ee74867891890a5fae06129"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="31%" headers="mcps1.2.4.1.2 "><p id="ac02bd81cf21b41a888c2e7da7effd4b9"><a name="ac02bd81cf21b41a888c2e7da7effd4b9"></a><a name="ac02bd81cf21b41a888c2e7da7effd4b9"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="aa7e379fc1fa44a3e9e34916a7fc0d559"><a name="aa7e379fc1fa44a3e9e34916a7fc0d559"></a><a name="aa7e379fc1fa44a3e9e34916a7fc0d559"></a>UID of the referent.</p>
</td>
</tr>
<tr id="r93929f6f249d4e99a16e475563057c59"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.1 "><p id="ac019f98f28b343489328b62a2e7633af"><a name="ac019f98f28b343489328b62a2e7633af"></a><a name="ac019f98f28b343489328b62a2e7633af"></a>controller</p>
</td>
<td class="cellrowborder" valign="top" width="31%" headers="mcps1.2.4.1.2 "><p id="ad4e3d7e1f49b44a291673e313ee0645f"><a name="ad4e3d7e1f49b44a291673e313ee0645f"></a><a name="ad4e3d7e1f49b44a291673e313ee0645f"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="a4dd2936c914749e18a62f5885eb0064a"><a name="a4dd2936c914749e18a62f5885eb0064a"></a><a name="a4dd2936c914749e18a62f5885eb0064a"></a>If true, this reference points to the managing controller.</p>
</td>
</tr>
<tr id="rf638e77a844a4fdc81490b86e9e595cc"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.1 "><p id="abcbb1e4382ab42b8989619bb6181d40d"><a name="abcbb1e4382ab42b8989619bb6181d40d"></a><a name="abcbb1e4382ab42b8989619bb6181d40d"></a>blockOwnerDeletion</p>
</td>
<td class="cellrowborder" valign="top" width="31%" headers="mcps1.2.4.1.2 "><p id="aeb6ca19d8ad445c6bd79d916013ebec6"><a name="aeb6ca19d8ad445c6bd79d916013ebec6"></a><a name="aeb6ca19d8ad445c6bd79d916013ebec6"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="a84738067e6364928b545653916f79321"><a name="a84738067e6364928b545653916f79321"></a><a name="a84738067e6364928b545653916f79321"></a>If true, AND if the owner has the "foregroundDeletion" finalizer, then the owner cannot be deleted from the key-value store until this reference is removed. Defaults to false. To set this field, a user needs "delete" permission of the owner, otherwise 422 (Unprocessable Entity) will be returned.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  ports字段数据结构说明

<a name="zh-cn_topic_0079614941_table46187709"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614941_row15879623"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614941_p11181066"><a name="zh-cn_topic_0079614941_p11181066"></a><a name="zh-cn_topic_0079614941_p11181066"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p40842415195332"><a name="p40842415195332"></a><a name="p40842415195332"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p19901293195332"><a name="p19901293195332"></a><a name="p19901293195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614941_row56826725"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p39562042"><a name="zh-cn_topic_0079614941_p39562042"></a><a name="zh-cn_topic_0079614941_p39562042"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p50408856"><a name="zh-cn_topic_0079614941_p50408856"></a><a name="zh-cn_topic_0079614941_p50408856"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p56585510"><a name="zh-cn_topic_0079614941_p56585510"></a><a name="zh-cn_topic_0079614941_p56585510"></a>The name of this port within the service. This must be a DNS_LABEL. All ports within a ServiceSpec must have unique names. This maps to the 'Name' field in EndpointPort objects. Optional if only one ServicePort is defined on this service.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row39507542"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p45994352"><a name="zh-cn_topic_0079614941_p45994352"></a><a name="zh-cn_topic_0079614941_p45994352"></a>protocol</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p34555022"><a name="zh-cn_topic_0079614941_p34555022"></a><a name="zh-cn_topic_0079614941_p34555022"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p47493401"><a name="zh-cn_topic_0079614941_p47493401"></a><a name="zh-cn_topic_0079614941_p47493401"></a>The IP protocol for this port. Supports "TCP" and "UDP". Default is TCP.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row24787426"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p61624507"><a name="zh-cn_topic_0079614941_p61624507"></a><a name="zh-cn_topic_0079614941_p61624507"></a>port</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p25529140"><a name="zh-cn_topic_0079614941_p25529140"></a><a name="zh-cn_topic_0079614941_p25529140"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p54594421"><a name="zh-cn_topic_0079614941_p54594421"></a><a name="zh-cn_topic_0079614941_p54594421"></a>The port that will be exposed by this service.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row21587744"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p3776865"><a name="zh-cn_topic_0079614941_p3776865"></a><a name="zh-cn_topic_0079614941_p3776865"></a>targetPort</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p37490687"><a name="zh-cn_topic_0079614941_p37490687"></a><a name="zh-cn_topic_0079614941_p37490687"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p16846817"><a name="zh-cn_topic_0079614941_p16846817"></a><a name="zh-cn_topic_0079614941_p16846817"></a>Number or name of the port to access on the pods targeted by the service. Number must be in the range 1 to 65535. Name must be an IANA_SVC_NAME. If this is a string, it will be looked up as a named port in the target Pod's container ports. If this is not specified, the value of Port is used (an identity map). Defaults to the service port.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row17403632"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p408051"><a name="zh-cn_topic_0079614941_p408051"></a><a name="zh-cn_topic_0079614941_p408051"></a>nodePort</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p33052208"><a name="zh-cn_topic_0079614941_p33052208"></a><a name="zh-cn_topic_0079614941_p33052208"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p59983181"><a name="zh-cn_topic_0079614941_p59983181"></a><a name="zh-cn_topic_0079614941_p59983181"></a>The port on each node on which this service is exposed when type=NodePort or LoadBalancer. Usually assigned by the system. If specified, it will be allocated to the service if unused or else creation of the service will fail. Default is to auto-allocate a port if the ServiceType of this Service requires one.</p>
</td>
</tr>
</tbody>
</table>

**表 8**  loadBalancer字段数据结构说明

<a name="zh-cn_topic_0079614941_table13036200"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614941_row39333461"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614941_p31893735"><a name="zh-cn_topic_0079614941_p31893735"></a><a name="zh-cn_topic_0079614941_p31893735"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p58736464195332"><a name="p58736464195332"></a><a name="p58736464195332"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p60033171195332"><a name="p60033171195332"></a><a name="p60033171195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614941_row20116922"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p18857999"><a name="zh-cn_topic_0079614941_p18857999"></a><a name="zh-cn_topic_0079614941_p18857999"></a>ingress</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p51102936"><a name="zh-cn_topic_0079614941_p51102936"></a><a name="zh-cn_topic_0079614941_p51102936"></a><a href="#zh-cn_topic_0079614941_table50216937">ingress</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p8621167"><a name="zh-cn_topic_0079614941_p8621167"></a><a name="zh-cn_topic_0079614941_p8621167"></a>Ingress is a list containing ingress points for the load-balancer. Traffic intended for the service should be sent to these ingress points.</p>
</td>
</tr>
</tbody>
</table>

**表 9**  ingress字段数据结构说明

<a name="zh-cn_topic_0079614941_table50216937"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614941_row38913757"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614941_p65006646"><a name="zh-cn_topic_0079614941_p65006646"></a><a name="zh-cn_topic_0079614941_p65006646"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p5916613195332"><a name="p5916613195332"></a><a name="p5916613195332"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p9483620195332"><a name="p9483620195332"></a><a name="p9483620195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614941_row23831707"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p51320118"><a name="zh-cn_topic_0079614941_p51320118"></a><a name="zh-cn_topic_0079614941_p51320118"></a>ip</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p63288869"><a name="zh-cn_topic_0079614941_p63288869"></a><a name="zh-cn_topic_0079614941_p63288869"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p26124753"><a name="zh-cn_topic_0079614941_p26124753"></a><a name="zh-cn_topic_0079614941_p26124753"></a>IP is set for load-balancer ingress points that are IP based</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614941_row33796185"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614941_p53136426"><a name="zh-cn_topic_0079614941_p53136426"></a><a name="zh-cn_topic_0079614941_p53136426"></a>hostname</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614941_p9083244"><a name="zh-cn_topic_0079614941_p9083244"></a><a name="zh-cn_topic_0079614941_p9083244"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614941_p64654150"><a name="zh-cn_topic_0079614941_p64654150"></a><a name="zh-cn_topic_0079614941_p64654150"></a>Hostname is set for load-balancer ingress points that are DNS based</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{ 
   "kind": "Service", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "myapp", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/services/myapp", 
     "uid": "58b5ca7c-5d12-11e6-aeb9-286ed488fafe", 
     "resourceVersion": "683", 
     "creationTimestamp": "2016-08-08T02:46:46Z" 
   }, 
   "spec": { 
     "ports": [ 
       { 
         "protocol": "TCP", 
         "port": 8765, 
         "targetPort": 9376 
       } 
     ], 
     "selector": { 
       "app": "example" 
     }, 
     "clusterIP": "10.0.0.139", 
     "type": "ClusterIP", 
     "sessionAffinity": "None" 
   }, 
   "status": { 
     "loadBalancer": {} 
   } 
 }
```

## 状态码<a name="sd2fb196246a241cea5cbced82b71a7c0"></a>

[表10](#zh-cn_topic_0079614941_table49299249)描述API的状态码。

**表 10**  状态码

<a name="zh-cn_topic_0079614941_table49299249"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614941_row51657386"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p47913009195332"><a name="p47913009195332"></a><a name="p47913009195332"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p55748497195332"><a name="p55748497195332"></a><a name="p55748497195332"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614941_row26379626"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614941_p56374952"><a name="zh-cn_topic_0079614941_p56374952"></a><a name="zh-cn_topic_0079614941_p56374952"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614941_p2968403"><a name="zh-cn_topic_0079614941_p2968403"></a><a name="zh-cn_topic_0079614941_p2968403"></a>This operation succeeds, and a Service resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

