# 创建Secret<a name="cce_02_0043"></a>

## 功能介绍<a name="s4e0a1c9701464caaa087bfb241e8faeb"></a>

该API用于创建Secret资源类型，Kubernetes提供了Secret来处理敏感信息。

## URI<a name="s3cae00f6e7914695ba88e44aa7a2a633"></a>

POST /api/v1/namespaces/\{namespace\}/secrets

[表1](#zh-cn_topic_0079614900_table43659541)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614900_table43659541"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row65791910"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614900_p27544487"><a name="zh-cn_topic_0079614900_p27544487"></a><a name="zh-cn_topic_0079614900_p27544487"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p4973534205955"><a name="p4973534205955"></a><a name="p4973534205955"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p203075205955"><a name="p203075205955"></a><a name="p203075205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row14572292"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614900_p39504966"><a name="zh-cn_topic_0079614900_p39504966"></a><a name="zh-cn_topic_0079614900_p39504966"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614900_p45785693"><a name="zh-cn_topic_0079614900_p45785693"></a><a name="zh-cn_topic_0079614900_p45785693"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p17653681"><a name="zh-cn_topic_0079614900_p17653681"></a><a name="zh-cn_topic_0079614900_p17653681"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row43820797"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614900_p59823639"><a name="zh-cn_topic_0079614900_p59823639"></a><a name="zh-cn_topic_0079614900_p59823639"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614900_p13876573"><a name="zh-cn_topic_0079614900_p13876573"></a><a name="zh-cn_topic_0079614900_p13876573"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p50260665"><a name="zh-cn_topic_0079614900_p50260665"></a><a name="zh-cn_topic_0079614900_p50260665"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079614900_d0e9414"></a>

请求参数：

请求参数如[表2](#zh-cn_topic_0079614900_ref458786458)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079614900_ref458786458"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row23223189"><th class="cellrowborder" valign="top" width="22.189999999999998%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614900_p2030132"><a name="zh-cn_topic_0079614900_p2030132"></a><a name="zh-cn_topic_0079614900_p2030132"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.849999999999998%" id="mcps1.2.5.1.2"><p id="p1331399205955"><a name="p1331399205955"></a><a name="p1331399205955"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.3%" id="mcps1.2.5.1.3"><p id="p40734494205955"><a name="p40734494205955"></a><a name="p40734494205955"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.660000000000004%" id="mcps1.2.5.1.4"><p id="p11159709205955"><a name="p11159709205955"></a><a name="p11159709205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row35800477"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p14157563"><a name="zh-cn_topic_0079614900_p14157563"></a><a name="zh-cn_topic_0079614900_p14157563"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p5911965"><a name="zh-cn_topic_0079614900_p5911965"></a><a name="zh-cn_topic_0079614900_p5911965"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p9107180"><a name="zh-cn_topic_0079614900_p9107180"></a><a name="zh-cn_topic_0079614900_p9107180"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p66592975"><a name="zh-cn_topic_0079614900_p66592975"></a><a name="zh-cn_topic_0079614900_p66592975"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="zh-cn_topic_0079614900_p62465868"><a name="zh-cn_topic_0079614900_p62465868"></a><a name="zh-cn_topic_0079614900_p62465868"></a>The value of this parameter is <strong id="zh-cn_topic_0079614900_b25321903"><a name="zh-cn_topic_0079614900_b25321903"></a><a name="zh-cn_topic_0079614900_b25321903"></a>Secret</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row26570537"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p4729870"><a name="zh-cn_topic_0079614900_p4729870"></a><a name="zh-cn_topic_0079614900_p4729870"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p47575204"><a name="zh-cn_topic_0079614900_p47575204"></a><a name="zh-cn_topic_0079614900_p47575204"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p28386322"><a name="zh-cn_topic_0079614900_p28386322"></a><a name="zh-cn_topic_0079614900_p28386322"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p17590785"><a name="zh-cn_topic_0079614900_p17590785"></a><a name="zh-cn_topic_0079614900_p17590785"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="zh-cn_topic_0079614900_p24099345"><a name="zh-cn_topic_0079614900_p24099345"></a><a name="zh-cn_topic_0079614900_p24099345"></a>The value of this parameter is <strong id="zh-cn_topic_0079614900_b15567513"><a name="zh-cn_topic_0079614900_b15567513"></a><a name="zh-cn_topic_0079614900_b15567513"></a>v1</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row5889891"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p7319178"><a name="zh-cn_topic_0079614900_p7319178"></a><a name="zh-cn_topic_0079614900_p7319178"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p55982574"><a name="zh-cn_topic_0079614900_p55982574"></a><a name="zh-cn_topic_0079614900_p55982574"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p38294646"><a name="zh-cn_topic_0079614900_p38294646"></a><a name="zh-cn_topic_0079614900_p38294646"></a><a href="#cce_02_0043__zh-cn_topic_0079614900_table57391552">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p14858635"><a name="zh-cn_topic_0079614900_p14858635"></a><a name="zh-cn_topic_0079614900_p14858635"></a>-</p>
</td>
</tr>
<tr id="r4da44c1005dc4397ab1b1ccf464484c7"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="a0409150518b342c1aa173b44cb238e6a"><a name="a0409150518b342c1aa173b44cb238e6a"></a><a name="a0409150518b342c1aa173b44cb238e6a"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="aa1c1da83ee97430f9257ae829978892e"><a name="aa1c1da83ee97430f9257ae829978892e"></a><a name="aa1c1da83ee97430f9257ae829978892e"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="a146c165b312544a28557e9eeb74b2edc"><a name="a146c165b312544a28557e9eeb74b2edc"></a><a name="a146c165b312544a28557e9eeb74b2edc"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="a2039915c6faf4e959fd294043cc9fce5"><a name="a2039915c6faf4e959fd294043cc9fce5"></a><a name="a2039915c6faf4e959fd294043cc9fce5"></a>Data contains the secret data. Each key must be a valid DNS_SUBDOMAIN or leading dot followed by valid DNS_SUBDOMAIN. The serialized form of the secret data is a base64 encoded string, representing the arbitrary (possibly non-string) data value here.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row66618853"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p27418040"><a name="zh-cn_topic_0079614900_p27418040"></a><a name="zh-cn_topic_0079614900_p27418040"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p6268747"><a name="zh-cn_topic_0079614900_p6268747"></a><a name="zh-cn_topic_0079614900_p6268747"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p38006470"><a name="zh-cn_topic_0079614900_p38006470"></a><a name="zh-cn_topic_0079614900_p38006470"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p58625234"><a name="zh-cn_topic_0079614900_p58625234"></a><a name="zh-cn_topic_0079614900_p58625234"></a>Used to facilitate programmatic handling of secret data.</p>
<p id="zh-cn_topic_0079614900_p57865062"><a name="zh-cn_topic_0079614900_p57865062"></a><a name="zh-cn_topic_0079614900_p57865062"></a>The primitive k8s supports the following secret types:</p>
<a name="zh-cn_topic_0079614900_ul51023510"></a><a name="zh-cn_topic_0079614900_ul51023510"></a><ul id="zh-cn_topic_0079614900_ul51023510"><li>kubernetes.io/service-account-token</li><li>kubernetes.io/.dockercfg</li><li>kubernetes.io/.dockerconfigjson</li><li>kubernetes.io/basic-auth</li><li>kubernetes.io/ssh-auth</li><li>kubernetes.io/tls</li></ul>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="zh-cn_topic_0079614900_table57391552"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row49758049"><th class="cellrowborder" valign="top" width="22.22222222222222%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614900_p3870157"><a name="zh-cn_topic_0079614900_p3870157"></a><a name="zh-cn_topic_0079614900_p3870157"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.18181818181818%" id="mcps1.2.5.1.2"><p id="p1711493205955"><a name="p1711493205955"></a><a name="p1711493205955"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.2020202020202%" id="mcps1.2.5.1.3"><p id="p4413239205955"><a name="p4413239205955"></a><a name="p4413239205955"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.39393939393939%" id="mcps1.2.5.1.4"><p id="p21928065205955"><a name="p21928065205955"></a><a name="p21928065205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row15135864"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p18045482"><a name="zh-cn_topic_0079614900_p18045482"></a><a name="zh-cn_topic_0079614900_p18045482"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p52397961"><a name="zh-cn_topic_0079614900_p52397961"></a><a name="zh-cn_topic_0079614900_p52397961"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p16376444"><a name="zh-cn_topic_0079614900_p16376444"></a><a name="zh-cn_topic_0079614900_p16376444"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p41049265420"><a name="zh-cn_topic_0079614900_p41049265420"></a><a name="zh-cn_topic_0079614900_p41049265420"></a>Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition.</p>
<p id="zh-cn_topic_0079614900_p168024282424"><a name="zh-cn_topic_0079614900_p168024282424"></a><a name="zh-cn_topic_0079614900_p168024282424"></a>The name must be 0 to 253 characters in length.</p>
<p id="zh-cn_topic_0079614900_p51423596"><a name="zh-cn_topic_0079614900_p51423596"></a><a name="zh-cn_topic_0079614900_p51423596"></a>The string must comply with regular expression [a-z0-9]([-a-z0-9]*[a-z0-9])?.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row41055555"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p37165673"><a name="zh-cn_topic_0079614900_p37165673"></a><a name="zh-cn_topic_0079614900_p37165673"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p57629543"><a name="zh-cn_topic_0079614900_p57629543"></a><a name="zh-cn_topic_0079614900_p57629543"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p37481446"><a name="zh-cn_topic_0079614900_p37481446"></a><a name="zh-cn_topic_0079614900_p37481446"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p16098318"><a name="zh-cn_topic_0079614900_p16098318"></a><a name="zh-cn_topic_0079614900_p16098318"></a>GenerateName is an optional prefix, used by the server, to generate a unique name ONLY IF the Name field has not been provided. If this field is used, the name returned to the client will be different than the name passed. This value will also be combined with a unique suffix. The provided value has the same validation rules as the Name field, and may be truncated by the length of the suffix required to make the value unique on the server.</p>
<p id="zh-cn_topic_0079614900_p10667136"><a name="zh-cn_topic_0079614900_p10667136"></a><a name="zh-cn_topic_0079614900_p10667136"></a>If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header).</p>
<p id="zh-cn_topic_0079614900_p28895366"><a name="zh-cn_topic_0079614900_p28895366"></a><a name="zh-cn_topic_0079614900_p28895366"></a>Applied only if Name is not specified.</p>
<p id="zh-cn_topic_0079614900_p58731703"><a name="zh-cn_topic_0079614900_p58731703"></a><a name="zh-cn_topic_0079614900_p58731703"></a>Value length: 0 character &lt; String length ≤ 253 characters.</p>
<p id="zh-cn_topic_0079614900_p58823286"><a name="zh-cn_topic_0079614900_p58823286"></a><a name="zh-cn_topic_0079614900_p58823286"></a>The string must comply with regular expression [a-z0-9]([-a-z0-9]*[a-z0-9])?.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row59647531"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p66720707"><a name="zh-cn_topic_0079614900_p66720707"></a><a name="zh-cn_topic_0079614900_p66720707"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p35668200"><a name="zh-cn_topic_0079614900_p35668200"></a><a name="zh-cn_topic_0079614900_p35668200"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p3443073"><a name="zh-cn_topic_0079614900_p3443073"></a><a name="zh-cn_topic_0079614900_p3443073"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p10453495"><a name="zh-cn_topic_0079614900_p10453495"></a><a name="zh-cn_topic_0079614900_p10453495"></a>Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty. Must be a DNS_LABEL. Cannot be updated.</p>
<p id="zh-cn_topic_0079614900_p26972592"><a name="zh-cn_topic_0079614900_p26972592"></a><a name="zh-cn_topic_0079614900_p26972592"></a>Value length: 0 character &lt; String length ≤ 253 characters.</p>
<p id="zh-cn_topic_0079614900_p41426737"><a name="zh-cn_topic_0079614900_p41426737"></a><a name="zh-cn_topic_0079614900_p41426737"></a>The string must comply with regular expression [a-z0-9]([-a-z0-9]*[a-z0-9])?.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row37296315"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p1102679"><a name="zh-cn_topic_0079614900_p1102679"></a><a name="zh-cn_topic_0079614900_p1102679"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p22208171"><a name="zh-cn_topic_0079614900_p22208171"></a><a name="zh-cn_topic_0079614900_p22208171"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p54031456"><a name="zh-cn_topic_0079614900_p54031456"></a><a name="zh-cn_topic_0079614900_p54031456"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p14471838"><a name="zh-cn_topic_0079614900_p14471838"></a><a name="zh-cn_topic_0079614900_p14471838"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
<div class="note" id="zh-cn_topic_0079614900_note63137679"><a name="zh-cn_topic_0079614900_note63137679"></a><a name="zh-cn_topic_0079614900_note63137679"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079614900_p31368204"><a name="zh-cn_topic_0079614900_p31368204"></a><a name="zh-cn_topic_0079614900_p31368204"></a>This parameter is automatically generated. Do not assign values to this parameter. Otherwise, the API fails to be called.</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row13878380"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p50407014"><a name="zh-cn_topic_0079614900_p50407014"></a><a name="zh-cn_topic_0079614900_p50407014"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p56436324"><a name="zh-cn_topic_0079614900_p56436324"></a><a name="zh-cn_topic_0079614900_p56436324"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p7939535"><a name="zh-cn_topic_0079614900_p7939535"></a><a name="zh-cn_topic_0079614900_p7939535"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p39122574"><a name="zh-cn_topic_0079614900_p39122574"></a><a name="zh-cn_topic_0079614900_p39122574"></a>UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations. Populated by the system. Read-only.</p>
<div class="note" id="zh-cn_topic_0079614900_note16558849"><a name="zh-cn_topic_0079614900_note16558849"></a><a name="zh-cn_topic_0079614900_note16558849"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079614900_p14811914"><a name="zh-cn_topic_0079614900_p14811914"></a><a name="zh-cn_topic_0079614900_p14811914"></a>This parameter is automatically generated. Do not assign values to this parameter. Otherwise, the API fails to be called.</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row66198362"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p60467067"><a name="zh-cn_topic_0079614900_p60467067"></a><a name="zh-cn_topic_0079614900_p60467067"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p65994253"><a name="zh-cn_topic_0079614900_p65994253"></a><a name="zh-cn_topic_0079614900_p65994253"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p43934263"><a name="zh-cn_topic_0079614900_p43934263"></a><a name="zh-cn_topic_0079614900_p43934263"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p1905570"><a name="zh-cn_topic_0079614900_p1905570"></a><a name="zh-cn_topic_0079614900_p1905570"></a>An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources. Populated by the system. Read-only. Value must be treated as opaque by clients.</p>
<div class="note" id="zh-cn_topic_0079614900_note17150135"><a name="zh-cn_topic_0079614900_note17150135"></a><a name="zh-cn_topic_0079614900_note17150135"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079614900_p20133494"><a name="zh-cn_topic_0079614900_p20133494"></a><a name="zh-cn_topic_0079614900_p20133494"></a>This parameter is automatically generated. Do not assign values to this parameter. Otherwise, the API fails to be called.</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row46983718"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p47584809"><a name="zh-cn_topic_0079614900_p47584809"></a><a name="zh-cn_topic_0079614900_p47584809"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p29164329"><a name="zh-cn_topic_0079614900_p29164329"></a><a name="zh-cn_topic_0079614900_p29164329"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p13500429"><a name="zh-cn_topic_0079614900_p13500429"></a><a name="zh-cn_topic_0079614900_p13500429"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p19792958"><a name="zh-cn_topic_0079614900_p19792958"></a><a name="zh-cn_topic_0079614900_p19792958"></a>A sequence number representing a specific generation of the desired state. Currently only implemented by replication controllers. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row43918894"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p660668"><a name="zh-cn_topic_0079614900_p660668"></a><a name="zh-cn_topic_0079614900_p660668"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p53514187"><a name="zh-cn_topic_0079614900_p53514187"></a><a name="zh-cn_topic_0079614900_p53514187"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p39681923"><a name="zh-cn_topic_0079614900_p39681923"></a><a name="zh-cn_topic_0079614900_p39681923"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p60119179"><a name="zh-cn_topic_0079614900_p60119179"></a><a name="zh-cn_topic_0079614900_p60119179"></a>CreationTimestamp is a timestamp representing the server time when this object was created. It is not guaranteed to be set in happens-before order across separate operations. Clients may not set this value. It is represented in RFC3339 form and is in UTC. Populated by the system. Read-only. Null for lists.</p>
<div class="note" id="zh-cn_topic_0079614900_note4201700"><a name="zh-cn_topic_0079614900_note4201700"></a><a name="zh-cn_topic_0079614900_note4201700"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079614900_p37815307"><a name="zh-cn_topic_0079614900_p37815307"></a><a name="zh-cn_topic_0079614900_p37815307"></a>This parameter is automatically generated. Do not assign values to this parameter. Otherwise, the API fails to be called.</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row4793448"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p52725008"><a name="zh-cn_topic_0079614900_p52725008"></a><a name="zh-cn_topic_0079614900_p52725008"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p42867269"><a name="zh-cn_topic_0079614900_p42867269"></a><a name="zh-cn_topic_0079614900_p42867269"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p49696750"><a name="zh-cn_topic_0079614900_p49696750"></a><a name="zh-cn_topic_0079614900_p49696750"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p66013812"><a name="zh-cn_topic_0079614900_p66013812"></a><a name="zh-cn_topic_0079614900_p66013812"></a>DeletionTimestamp is RFC 3339 date and time at which this resource will be deleted. This field is set by the server when a graceful deletion is requested by the user, and is not directly settable by a client. The resource will be deleted (no longer visible from resource lists, and not reachable by name) after the time in this field. Once set, this value may not be unset or be set further into the future, although it may be shortened or the resource may be deleted prior to this time. For example, a user may request that a pod is deleted in 30 seconds. The Kubelet will react by sending a graceful termination signal to the containers in the pod. Once the resource is deleted in the API, the Kubelet will send a hard termination signal to the container. If not set, graceful deletion of the object has not been requested. Populated by the system when a graceful deletion is requested. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row57253397"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p7013552"><a name="zh-cn_topic_0079614900_p7013552"></a><a name="zh-cn_topic_0079614900_p7013552"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p31226844"><a name="zh-cn_topic_0079614900_p31226844"></a><a name="zh-cn_topic_0079614900_p31226844"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p46346432"><a name="zh-cn_topic_0079614900_p46346432"></a><a name="zh-cn_topic_0079614900_p46346432"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p63073541"><a name="zh-cn_topic_0079614900_p63073541"></a><a name="zh-cn_topic_0079614900_p63073541"></a>Number of seconds allowed for this object to gracefully terminate before it will be removed from the system. Only set when deletionTimestamp is also set. May only be shortened. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row30790963"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p11040108"><a name="zh-cn_topic_0079614900_p11040108"></a><a name="zh-cn_topic_0079614900_p11040108"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p21833561"><a name="zh-cn_topic_0079614900_p21833561"></a><a name="zh-cn_topic_0079614900_p21833561"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p23688035"><a name="zh-cn_topic_0079614900_p23688035"></a><a name="zh-cn_topic_0079614900_p23688035"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p39682673"><a name="zh-cn_topic_0079614900_p39682673"></a><a name="zh-cn_topic_0079614900_p39682673"></a>Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row21599741"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p4748621"><a name="zh-cn_topic_0079614900_p4748621"></a><a name="zh-cn_topic_0079614900_p4748621"></a>Annotations</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p49094038"><a name="zh-cn_topic_0079614900_p49094038"></a><a name="zh-cn_topic_0079614900_p49094038"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p17194111"><a name="zh-cn_topic_0079614900_p17194111"></a><a name="zh-cn_topic_0079614900_p17194111"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p50545712"><a name="zh-cn_topic_0079614900_p50545712"></a><a name="zh-cn_topic_0079614900_p50545712"></a>Annotations is an unstructured key value map stored with a resource that may be set by external tools to store and retrieve arbitrary metadata. They are not queryable and should be preserved when modifying objects.</p>
</td>
</tr>
<tr id="rd6cf3435589e4112b5e54dd5fecc7795"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="a5e699b787f7c456bb897a571b2bd303b"><a name="a5e699b787f7c456bb897a571b2bd303b"></a><a name="a5e699b787f7c456bb897a571b2bd303b"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="a9499098f0a904fb1979e0f9292b6b87c"><a name="a9499098f0a904fb1979e0f9292b6b87c"></a><a name="a9499098f0a904fb1979e0f9292b6b87c"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="a1857e4ea59ee46e78931c80b1ce4d570"><a name="a1857e4ea59ee46e78931c80b1ce4d570"></a><a name="a1857e4ea59ee46e78931c80b1ce4d570"></a><a href="#cce_02_0043__t56c9527f988e4c2c8b0d5a53ba538176">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="a47143b35d469419b80303ee850b0642e"><a name="a47143b35d469419b80303ee850b0642e"></a><a name="a47143b35d469419b80303ee850b0642e"></a>List of objects depended by this object. If ALL objects in the list have been deleted, this object will be garbage collected. If this object is managed by a controller, then an entry in this list will point to this controller, with the controller field set to true. There cannot be more than one managing controller.</p>
</td>
</tr>
<tr id="r0f3d6bfcf1384a60b96dabf065d3a0fa"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="a3a092d3ef0d54cb7924ec4020823383e"><a name="a3a092d3ef0d54cb7924ec4020823383e"></a><a name="a3a092d3ef0d54cb7924ec4020823383e"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="a3c70cffc92484e66862d2bc20d079601"><a name="a3c70cffc92484e66862d2bc20d079601"></a><a name="a3c70cffc92484e66862d2bc20d079601"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="ac6b4f707b1244254b143828a5f097ded"><a name="ac6b4f707b1244254b143828a5f097ded"></a><a name="ac6b4f707b1244254b143828a5f097ded"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="ae688fa6dbc27407897a7d62d292d7cf1"><a name="ae688fa6dbc27407897a7d62d292d7cf1"></a><a name="ae688fa6dbc27407897a7d62d292d7cf1"></a>Must be empty before the object is deleted from the registry. Each entry is an identifier for the responsible component that will remove the entry from the list. If the deletionTimestamp of the object is non-nil, entries in this list can only be removed.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  ownerReferences字段数据结构说明

<a name="t56c9527f988e4c2c8b0d5a53ba538176"></a>
<table><thead align="left"><tr id="r550b08f0ee964525be70ec96f41d8475"><th class="cellrowborder" valign="top" width="22.37%" id="mcps1.2.5.1.1"><p id="a3f6c00cbf4d44f82906917be33495c96"><a name="a3f6c00cbf4d44f82906917be33495c96"></a><a name="a3f6c00cbf4d44f82906917be33495c96"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.86%" id="mcps1.2.5.1.2"><p id="p16985922205955"><a name="p16985922205955"></a><a name="p16985922205955"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.49%" id="mcps1.2.5.1.3"><p id="p33682440205955"><a name="p33682440205955"></a><a name="p33682440205955"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28%" id="mcps1.2.5.1.4"><p id="p43923090205955"><a name="p43923090205955"></a><a name="p43923090205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rc77662aed67a428eb415a6a70e2f2cc0"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="a94c8a8baf1d347a0927d0db9a98b0edd"><a name="a94c8a8baf1d347a0927d0db9a98b0edd"></a><a name="a94c8a8baf1d347a0927d0db9a98b0edd"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="aa8414eb11e6d4d219a843224790cecf4"><a name="aa8414eb11e6d4d219a843224790cecf4"></a><a name="aa8414eb11e6d4d219a843224790cecf4"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="a2689014b700340c3b7a06423e8ea47a8"><a name="a2689014b700340c3b7a06423e8ea47a8"></a><a name="a2689014b700340c3b7a06423e8ea47a8"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="ac964351ba76e4233b5f31aa5309de4b4"><a name="ac964351ba76e4233b5f31aa5309de4b4"></a><a name="ac964351ba76e4233b5f31aa5309de4b4"></a>API version of the referent.</p>
</td>
</tr>
<tr id="r97f9bda38ecc4049b7df9d01b3628b45"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="a940e95193ce44e44afc20dcdf0b24958"><a name="a940e95193ce44e44afc20dcdf0b24958"></a><a name="a940e95193ce44e44afc20dcdf0b24958"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="abac88577765d4a25b4fe1873aca0b729"><a name="abac88577765d4a25b4fe1873aca0b729"></a><a name="abac88577765d4a25b4fe1873aca0b729"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="a485b075ba5e848a684f32c68f2f49bdd"><a name="a485b075ba5e848a684f32c68f2f49bdd"></a><a name="a485b075ba5e848a684f32c68f2f49bdd"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a4d2494c2f65b402db38a21a347dbb2ff"><a name="a4d2494c2f65b402db38a21a347dbb2ff"></a><a name="a4d2494c2f65b402db38a21a347dbb2ff"></a>Kind of the referent.</p>
</td>
</tr>
<tr id="r0ae02b5d933345829dd94dbe697b10d5"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="a681a134085fc422fa901f57984edbab9"><a name="a681a134085fc422fa901f57984edbab9"></a><a name="a681a134085fc422fa901f57984edbab9"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="ab5fe6157b1dc4ff3b50c69bb185ab420"><a name="ab5fe6157b1dc4ff3b50c69bb185ab420"></a><a name="ab5fe6157b1dc4ff3b50c69bb185ab420"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="a9e7d6ca2ef7b41d79fc3bb0328b224b2"><a name="a9e7d6ca2ef7b41d79fc3bb0328b224b2"></a><a name="a9e7d6ca2ef7b41d79fc3bb0328b224b2"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a2484d62071634d99981015986f3c8faf"><a name="a2484d62071634d99981015986f3c8faf"></a><a name="a2484d62071634d99981015986f3c8faf"></a>Name of the referent.</p>
</td>
</tr>
<tr id="r23e2627b1b114d4b926db2721d59c1eb"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="a7646e7d4535d4afcb99e819c66b88cbe"><a name="a7646e7d4535d4afcb99e819c66b88cbe"></a><a name="a7646e7d4535d4afcb99e819c66b88cbe"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p570124172656"><a name="zh-cn_topic_0079614900_p570124172656"></a><a name="zh-cn_topic_0079614900_p570124172656"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="adcd3ed14ebaf4b5f9ac15e48cfc06d22"><a name="adcd3ed14ebaf4b5f9ac15e48cfc06d22"></a><a name="adcd3ed14ebaf4b5f9ac15e48cfc06d22"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a17f25dca1d6a472b950aa60856c4912d"><a name="a17f25dca1d6a472b950aa60856c4912d"></a><a name="a17f25dca1d6a472b950aa60856c4912d"></a>UID of the referent.</p>
</td>
</tr>
<tr id="r23569e934f4c435bafdd343d76a240ba"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="abe8fbcc645e34aa5b63e4877951cf16f"><a name="abe8fbcc645e34aa5b63e4877951cf16f"></a><a name="abe8fbcc645e34aa5b63e4877951cf16f"></a>controller</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="a6c3e93d72df44415b9c26a8047ee5945"><a name="a6c3e93d72df44415b9c26a8047ee5945"></a><a name="a6c3e93d72df44415b9c26a8047ee5945"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="ad3e358d29eb54e5987b16b12933c7378"><a name="ad3e358d29eb54e5987b16b12933c7378"></a><a name="ad3e358d29eb54e5987b16b12933c7378"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a8c96e54ca8e34c58806c4ff79c8ec8b9"><a name="a8c96e54ca8e34c58806c4ff79c8ec8b9"></a><a name="a8c96e54ca8e34c58806c4ff79c8ec8b9"></a>If true, this reference points to the managing controller.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
  "apiVersion": "v1",
  "kind": "Secret",
  "metadata": {
    "name": "mysecret"
  },
  "type": "Opaque",
  "data": {
    "password": "******", #需要用Base64编码，方法：echo -n "待编码内容" | base64
    "username": "*****" #需要用Base64编码，方法：echo -n "待编码内容" | base64
  }
}
```

## 响应消息<a name="s08d56e5f4e57452da0a49400212440a4"></a>

**响应参数：**

响应参数的详细描述请参见[表2](#zh-cn_topic_0079614900_ref458786458)。

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

## 状态码<a name="s50f1049a6a4d404c895cf636eb8f3bf1"></a>

[表5](#zh-cn_topic_0079614900_table46761928)描述API的状态码。

**表 5**  状态码

<a name="zh-cn_topic_0079614900_table46761928"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row33254664"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p55616028205955"><a name="p55616028205955"></a><a name="p55616028205955"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p8604418205955"><a name="p8604418205955"></a><a name="p8604418205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row41084259"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614900_p39490674"><a name="zh-cn_topic_0079614900_p39490674"></a><a name="zh-cn_topic_0079614900_p39490674"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614900_p44628050"><a name="zh-cn_topic_0079614900_p44628050"></a><a name="zh-cn_topic_0079614900_p44628050"></a>This operation succeeds, and a secret resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

