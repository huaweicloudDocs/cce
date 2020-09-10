# 创建DaemonSet<a name="cce_02_0133"></a>

## 功能介绍<a name="section4885644"></a>

This API is used to create a DaemonSet resource object.

## URI<a name="section43970798"></a>

POST /apis/apps/v1/namespaces/\{namespace\}/daemonsets \(Supports 1.9 and 1.9+\)

POST /apis/extensions/v1beta1/namespaces/\{namespace\}/daemonsets \(Compatible\)

[表1](#d0e31331)描述该API的参数。

**表 1**  参数描述

<a name="d0e31331"></a>
<table><thead align="left"><tr id="row54051220"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row59085450"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p21192165"><a name="p21192165"></a><a name="p21192165"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p38843817"><a name="p38843817"></a><a name="p38843817"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p59341436"><a name="p59341436"></a><a name="p59341436"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row64310884"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.4.1.1 "><p id="p41799124"><a name="p41799124"></a><a name="p41799124"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.4.1.2 "><p id="p30285864"><a name="p30285864"></a><a name="p30285864"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p37235913"><a name="p37235913"></a><a name="p37235913"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section60192866"></a>

**请求参数：**

请求参数如[表2](#d0e31376)所示。

**表 2**  请求参数

<a name="d0e31376"></a>
<table><thead align="left"><tr id="row9350803"><th class="cellrowborder" valign="top" width="22.447755224477554%" id="mcps1.2.5.1.1"><p id="ae656fc68d4c647108a0d683bf8d51906"><a name="ae656fc68d4c647108a0d683bf8d51906"></a><a name="ae656fc68d4c647108a0d683bf8d51906"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.5.1.2"><p id="p1194511281367"><a name="p1194511281367"></a><a name="p1194511281367"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.36816318368163%" id="mcps1.2.5.1.3"><p id="p15946172811365"><a name="p15946172811365"></a><a name="p15946172811365"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.85571442855714%" id="mcps1.2.5.1.4"><p id="a02ec96a8fd6a472b99e398797499857f"><a name="a02ec96a8fd6a472b99e398797499857f"></a><a name="a02ec96a8fd6a472b99e398797499857f"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row4741657"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p48529919"><a name="p48529919"></a><a name="p48529919"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p38609403"><a name="p38609403"></a><a name="p38609403"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.5.1.3 "><p id="p40353906"><a name="p40353906"></a><a name="p40353906"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p47440974"><a name="p47440974"></a><a name="p47440974"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row24315590"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p23405748"><a name="p23405748"></a><a name="p23405748"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p16817402"><a name="p16817402"></a><a name="p16817402"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.5.1.3 "><p id="p20032321"><a name="p20032321"></a><a name="p20032321"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p12005296"><a name="p12005296"></a><a name="p12005296"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="row40938807"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p27709046"><a name="p27709046"></a><a name="p27709046"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p29840242"><a name="p29840242"></a><a name="p29840242"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.5.1.3 "><p id="p1140498"><a name="p1140498"></a><a name="p1140498"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table47756489">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p26116789"><a name="p26116789"></a><a name="p26116789"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="row33724511"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p47330909"><a name="p47330909"></a><a name="p47330909"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p8598431"><a name="p8598431"></a><a name="p8598431"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.5.1.3 "><p id="p25384334"><a name="p25384334"></a><a name="p25384334"></a><a href="#table109924514514">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p50242206"><a name="p50242206"></a><a name="p50242206"></a>The desired behavior of this daemon set.</p>
</td>
</tr>
<tr id="row49526673"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p52237557"><a name="p52237557"></a><a name="p52237557"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p3383718"><a name="p3383718"></a><a name="p3383718"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.5.1.3 "><p id="p5645707"><a name="p5645707"></a><a name="p5645707"></a><a href="#table423617231387">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p22079859"><a name="p22079859"></a><a name="p22079859"></a>The current status of this daemon set. This data may be out of date by some window of time. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  spec字段数据结构说明

<a name="table109924514514"></a>
<table><thead align="left"><tr id="row54410744"><th class="cellrowborder" valign="top" width="22.68%" id="mcps1.2.5.1.1"><p id="p195961586362"><a name="p195961586362"></a><a name="p195961586362"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.49%" id="mcps1.2.5.1.2"><p id="p659875817369"><a name="p659875817369"></a><a name="p659875817369"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.56%" id="mcps1.2.5.1.3"><p id="p19599858183612"><a name="p19599858183612"></a><a name="p19599858183612"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.27%" id="mcps1.2.5.1.4"><p id="p126028584368"><a name="p126028584368"></a><a name="p126028584368"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16080284"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p27434664"><a name="p27434664"></a><a name="p27434664"></a>minReadySeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p7615279"><a name="p7615279"></a><a name="p7615279"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p12857883"><a name="p12857883"></a><a name="p12857883"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p34855636"><a name="p34855636"></a><a name="p34855636"></a>The minimum number of seconds for which a newly created DaemonSet pod should be ready without any of its container crashing, for it to be considered available. Defaults to 0 (pod will be considered available as soon as it is ready).</p>
</td>
</tr>
<tr id="row45265273"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p42608463"><a name="p42608463"></a><a name="p42608463"></a>revisionHistoryLimit</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p28733478"><a name="p28733478"></a><a name="p28733478"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p45710373"><a name="p45710373"></a><a name="p45710373"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p36865955"><a name="p36865955"></a><a name="p36865955"></a>The number of old history to retain to allow rollback. This is a pointer to distinguish between explicit zero and not specified. Defaults to 10.</p>
</td>
</tr>
<tr id="row63358142"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p31735847"><a name="p31735847"></a><a name="p31735847"></a>selector</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p20466776"><a name="p20466776"></a><a name="p20466776"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p47196154"><a name="p47196154"></a><a name="p47196154"></a><a href="创建PersistentVolumeClaim.md#t87a0b25af7d2428182ec8bb2b4416a12">selector</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p46258138"><a name="p46258138"></a><a name="p46258138"></a>A label query over pods that are managed by the daemon set. Must match in order to be controlled. If empty, defaulted to labels on Pod template.</p>
</td>
</tr>
<tr id="row13670063"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p33533331"><a name="p33533331"></a><a name="p33533331"></a>template</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p31845254"><a name="p31845254"></a><a name="p31845254"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p29328819"><a name="p29328819"></a><a name="p29328819"></a><a href="#table82651956102317">template</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p40090562"><a name="p40090562"></a><a name="p40090562"></a>An object that describes the pod that will be created. The DaemonSet will create exactly one copy of this pod on every node that matches the template's node selector (or on every node if no node selector is specified).</p>
</td>
</tr>
<tr id="row25270741"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p33664155"><a name="p33664155"></a><a name="p33664155"></a>templateGeneration</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p42442041"><a name="p42442041"></a><a name="p42442041"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p15253336"><a name="p15253336"></a><a name="p15253336"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p27560736"><a name="p27560736"></a><a name="p27560736"></a>DEPRECATED. A sequence number representing a specific generation of the template. Populated by the system. It can be set only during the creation.</p>
</td>
</tr>
<tr id="row46720034"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p26226425"><a name="p26226425"></a><a name="p26226425"></a>updateStrategy</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p43965709"><a name="p43965709"></a><a name="p43965709"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p4452677"><a name="p4452677"></a><a name="p4452677"></a><a href="#table2082584572918">updateStrategy</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p24776540"><a name="p24776540"></a><a name="p24776540"></a>An update strategy to replace existing DaemonSet pods with new pods.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  status字段数据结构说明

<a name="table423617231387"></a>
<table><thead align="left"><tr id="row49319253"><th class="cellrowborder" valign="top" width="22.68%" id="mcps1.2.5.1.1"><p id="p641302113716"><a name="p641302113716"></a><a name="p641302113716"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.49%" id="mcps1.2.5.1.2"><p id="p204151420379"><a name="p204151420379"></a><a name="p204151420379"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.56%" id="mcps1.2.5.1.3"><p id="p341710253710"><a name="p341710253710"></a><a name="p341710253710"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.27%" id="mcps1.2.5.1.4"><p id="p1442142113714"><a name="p1442142113714"></a><a name="p1442142113714"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row40882376"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p23138150"><a name="p23138150"></a><a name="p23138150"></a>collisionCount</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p62250865"><a name="p62250865"></a><a name="p62250865"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p9155280"><a name="p9155280"></a><a name="p9155280"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p3380204"><a name="p3380204"></a><a name="p3380204"></a>Count of hash collisions for the DaemonSet. The DaemonSet controller uses this field as a collision avoidance mechanism when it needs to create the name for the newest ControllerRevision.</p>
</td>
</tr>
<tr id="row30421836"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p48249613"><a name="p48249613"></a><a name="p48249613"></a>currentNumberScheduled</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p15904575"><a name="p15904575"></a><a name="p15904575"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p13202185"><a name="p13202185"></a><a name="p13202185"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p62744084"><a name="p62744084"></a><a name="p62744084"></a>The number of nodes that are running at least 1 daemon pod and are supposed to run the daemon pod.</p>
</td>
</tr>
<tr id="row27825849"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p39301320"><a name="p39301320"></a><a name="p39301320"></a>desiredNumberScheduled</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p29290347"><a name="p29290347"></a><a name="p29290347"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p23707915"><a name="p23707915"></a><a name="p23707915"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p41292943"><a name="p41292943"></a><a name="p41292943"></a>The total number of nodes that should be running the daemon pod (including nodes correctly running the daemon pod).</p>
</td>
</tr>
<tr id="row36092170"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p37784672"><a name="p37784672"></a><a name="p37784672"></a>numberAvailable</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p40659598"><a name="p40659598"></a><a name="p40659598"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p5093181"><a name="p5093181"></a><a name="p5093181"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p9894549"><a name="p9894549"></a><a name="p9894549"></a>The number of nodes that should be running the daemon pod and have one or more of the daemon pod running and available (ready for at least spec.minReadySeconds)</p>
</td>
</tr>
<tr id="row21942079"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p32477990"><a name="p32477990"></a><a name="p32477990"></a>numberMisscheduled</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p13471562"><a name="p13471562"></a><a name="p13471562"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p17454738"><a name="p17454738"></a><a name="p17454738"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p4547687"><a name="p4547687"></a><a name="p4547687"></a>The number of nodes that are running the daemon pod, but are not supposed to run the daemon pod.</p>
</td>
</tr>
<tr id="row40929185"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p26929716"><a name="p26929716"></a><a name="p26929716"></a>numberReady</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p33823367"><a name="p33823367"></a><a name="p33823367"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p55338178"><a name="p55338178"></a><a name="p55338178"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p53207438"><a name="p53207438"></a><a name="p53207438"></a>The number of nodes that should be running the daemon pod and have one or more of the daemon pod running and ready.</p>
</td>
</tr>
<tr id="row9104898"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p66408105"><a name="p66408105"></a><a name="p66408105"></a>numberUnavailable</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p10347445"><a name="p10347445"></a><a name="p10347445"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p32836750"><a name="p32836750"></a><a name="p32836750"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p42531099"><a name="p42531099"></a><a name="p42531099"></a>The number of nodes that should be running the daemon pod and have none of the daemon pod running and available (ready for at least spec.minReadySeconds)</p>
</td>
</tr>
<tr id="row47235577"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p876528"><a name="p876528"></a><a name="p876528"></a>observedGeneration</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p3889935"><a name="p3889935"></a><a name="p3889935"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p46649343"><a name="p46649343"></a><a name="p46649343"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p20500456"><a name="p20500456"></a><a name="p20500456"></a>The most recent generation observed by the daemon set controller.</p>
</td>
</tr>
<tr id="row50286377"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p46664697"><a name="p46664697"></a><a name="p46664697"></a>updatedNumberScheduled</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p21744085"><a name="p21744085"></a><a name="p21744085"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p16440486"><a name="p16440486"></a><a name="p16440486"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p56611028"><a name="p56611028"></a><a name="p56611028"></a>The total number of nodes that are running updated daemon pod</p>
</td>
</tr>
</tbody>
</table>

**表 5**  template字段数据结构说明

<a name="table82651956102317"></a>
<table><thead align="left"><tr id="row18933514"><th class="cellrowborder" valign="top" width="22.68%" id="mcps1.2.5.1.1"><p id="p1394012513376"><a name="p1394012513376"></a><a name="p1394012513376"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.49%" id="mcps1.2.5.1.2"><p id="p1994225173711"><a name="p1994225173711"></a><a name="p1994225173711"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.56%" id="mcps1.2.5.1.3"><p id="p094415163719"><a name="p094415163719"></a><a name="p094415163719"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.27%" id="mcps1.2.5.1.4"><p id="p14947105103712"><a name="p14947105103712"></a><a name="p14947105103712"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row31796234"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p25358146"><a name="p25358146"></a><a name="p25358146"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p40743922"><a name="p40743922"></a><a name="p40743922"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p11923395"><a name="p11923395"></a><a name="p11923395"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table47756489">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p35111876"><a name="p35111876"></a><a name="p35111876"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="row47571430"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p28080649"><a name="p28080649"></a><a name="p28080649"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="16.49%" headers="mcps1.2.5.1.2 "><p id="p59940076"><a name="p59940076"></a><a name="p59940076"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.56%" headers="mcps1.2.5.1.3 "><p id="p23307959"><a name="p23307959"></a><a name="p23307959"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42.27%" headers="mcps1.2.5.1.4 "><p id="p8896531"><a name="p8896531"></a><a name="p8896531"></a>Specification of the desired behavior of the pod.</p>
</td>
</tr>
</tbody>
</table>

**表 6**  updateStrategy字段数据结构说明

<a name="table2082584572918"></a>
<table><thead align="left"><tr id="row62374408"><th class="cellrowborder" valign="top" width="22.447755224477554%" id="mcps1.2.5.1.1"><p id="p69736803717"><a name="p69736803717"></a><a name="p69736803717"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.5.1.2"><p id="p2974384376"><a name="p2974384376"></a><a name="p2974384376"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.36816318368163%" id="mcps1.2.5.1.3"><p id="p14976782378"><a name="p14976782378"></a><a name="p14976782378"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.835816418358164%" id="mcps1.2.5.1.4"><p id="p69781811374"><a name="p69781811374"></a><a name="p69781811374"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15998054"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p20773958"><a name="p20773958"></a><a name="p20773958"></a>rollingUpdate</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p4969010"><a name="p4969010"></a><a name="p4969010"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.5.1.3 "><p id="p98640246501"><a name="p98640246501"></a><a name="p98640246501"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="41.835816418358164%" headers="mcps1.2.5.1.4 "><p id="p53880913"><a name="p53880913"></a><a name="p53880913"></a>Rolling update config params. Present only if type = "RollingUpdate".</p>
</td>
</tr>
<tr id="row15166174"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p20500594"><a name="p20500594"></a><a name="p20500594"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p49935381"><a name="p49935381"></a><a name="p49935381"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.5.1.3 "><p id="p18234098"><a name="p18234098"></a><a name="p18234098"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.835816418358164%" headers="mcps1.2.5.1.4 "><p id="p5102633"><a name="p5102633"></a><a name="p5102633"></a>Type of daemon set update. Can be "RollingUpdate" or "OnDelete". Default is OnDelete.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
    "kind": "DaemonSet",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "name": "daemonset-test",
        "labels": {
            "name": "daemonset-test"
        },
        "enable": true
    },
    "spec": {
        "selector": {
            "matchLabels": {
                "name": "daemonset-test"
            }
        },
        "template": {
            "metadata": {
                "labels": {
                    "name": "daemonset-test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "daemonset-test",
                        "image": "172.16.5.235:20202/test/nginx",
                        "imagePullPolicy": "IfNotPresent"
                    }
                ],
                "imagePullSecrets": [{
                    "name": "default-secret"
                }]            
            }
        }
    }
}
```

## 响应消息<a name="section4864890"></a>

**响应参数：**

响应参数的详细描述请参见[表2](#d0e31376)

**响应示例：**

```
{
    "kind": "DaemonSet",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "name": "daemonset-test",
        "namespace": "default",
        "selfLink": "/apis/extensions/v1beta1/namespaces/default/daemonsets/daemonset-test",
        "uid": "f9808766-fc23-11e7-9c3c-fa163eb8ad1a",
        "resourceVersion": "487764",
        "generation": 1,
        "creationTimestamp": "2018-01-18T07:48:29Z",
        "labels": {
            "name": "daemonset-test"
        },
        "enable": true
    },
    "spec": {
        "selector": {
            "matchLabels": {
                "name": "daemonset-test"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "name": "daemonset-test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "daemonset-test",
                        "image": "172.16.5.235:20202/test/nginx",
                        "resources": {},
                        "terminationMessagePath": "/dev/termination-log",
                        "terminationMessagePolicy": "File",
                        "imagePullPolicy": "IfNotPresent"
                    }
                ],
                "restartPolicy": "Always",
                "terminationGracePeriodSeconds": 30,
                "dnsPolicy": "ClusterFirst",
                "securityContext": {},
                "imagePullSecrets": [
                    {
                        "name": "default-secret"
                    }
                ],
                "schedulerName": "default-scheduler"
            }
        },
        "updateStrategy": {
            "type": "OnDelete"
        },
        "templateGeneration": 1,
        "revisionHistoryLimit": 10
    },
    "status": {
        "currentNumberScheduled": 0,
        "numberMisscheduled": 0,
        "desiredNumberScheduled": 0,
        "numberReady": 0
    }
}
```

## 状态码<a name="section43784014"></a>

[表7](#d0e31841)描述API的状态码。

**表 7**  状态码

<a name="d0e31841"></a>
<table><thead align="left"><tr id="row17467873"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p5611603"><a name="p5611603"></a><a name="p5611603"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p51886685"><a name="p51886685"></a><a name="p51886685"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row42071976"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p52386908"><a name="p52386908"></a><a name="p52386908"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p15481119"><a name="p15481119"></a><a name="p15481119"></a>The request has been fulfilled, resulting in the creation of a new resource.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

