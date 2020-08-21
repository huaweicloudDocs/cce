# 删除PersistentVolumeClaim<a name="cce_02_0253"></a>

## 功能描述<a name="section155195145312"></a>

该API用于删除指定Namespace下的PersistentVolumeClaim对象，并可以选择保留后端的云存储。

>![](public_sys-resources/icon-note.gif) **说明：** 
>URL格式为：**https://\{clusterid\}.Endpoint/uri**。其中\{clusterid\}为集群ID，uri为资源路径，也即API访问的路径。

## URI<a name="section1975393831219"></a>

DELETE /api/v1/namespaces/\{namespace\}/cloudpersistentvolumeclaims/\{name\}

[表1](#table2027961241820)描述该API的参数。

**表 1**  参数解释

<a name="table2027961241820"></a>
<table><thead align="left"><tr id="row122809120186"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p91421758131813"><a name="p91421758131813"></a><a name="p91421758131813"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12%" id="mcps1.2.4.1.2"><p id="p101421758131816"><a name="p101421758131816"></a><a name="p101421758131816"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="68%" id="mcps1.2.4.1.3"><p id="p19143115818187"><a name="p19143115818187"></a><a name="p19143115818187"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row32801312121810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p174971953101213"><a name="p174971953101213"></a><a name="p174971953101213"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.4.1.2 "><p id="p1849715318121"><a name="p1849715318121"></a><a name="p1849715318121"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="68%" headers="mcps1.2.4.1.3 "><p id="p44971053101215"><a name="p44971053101215"></a><a name="p44971053101215"></a>指定PersistentVolumeClaim所在的命名空间。</p>
</td>
</tr>
<tr id="row8285134691214"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p54971553111215"><a name="p54971553111215"></a><a name="p54971553111215"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.4.1.2 "><p id="p44971153181211"><a name="p44971153181211"></a><a name="p44971153181211"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="68%" headers="mcps1.2.4.1.3 "><p id="p24971753111210"><a name="p24971753111210"></a><a name="p24971753111210"></a>需要删除的PersistentVolumClaim的名称。</p>
<p id="p1735311268328"><a name="p1735311268328"></a><a name="p1735311268328"></a>name格式为：Volume名称[?deleteVolume=BOOLEAN&amp;storageType=云存储类型]，中括号内可省略，示例：</p>
<a name="ul1619719362324"></a><a name="ul1619719362324"></a><ul id="ul1619719362324"><li>volume-49f1?deleteVolume=true&amp;storageType=bs</li><li>volume-49f1</li></ul>
<p id="p9192451581"><a name="p9192451581"></a><a name="p9192451581"></a>其中：</p>
<a name="ul0576131593"></a><a name="ul0576131593"></a><ul id="ul0576131593"><li>deleteVolume：删除PersistentVolumeClaim后是否保留后端关联的云存储。false表示不删除，ture表示删除，默认为false。<div class="note" id="note9546141043213"><a name="note9546141043213"></a><a name="note9546141043213"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p65461410133217"><a name="p65461410133217"></a><a name="p65461410133217"></a>当为efs时，不支持删除存储，所以不能设为true。</p>
</div></div>
</li></ul>
<a name="ul197198369911"></a><a name="ul197198369911"></a><ul id="ul197198369911"><li>storageType：云存储的类型，和deleteVolume搭配使用。即deleteVolume和storageType必须同时配置。<a name="ul91497416910"></a><a name="ul91497416910"></a><ul id="ul91497416910"><li>bs：EVS云存储</li><li>nfs：SFS弹性文件存储</li><li>obs：OBS对象存储</li><li>efs：SFS Turbo极速文件存储</li></ul>
</li></ul>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section1142842461418"></a>

**请求参数**：

请求参数如[表2](#table117921043305)所示。

**表 2**  请求Header参数说明

<a name="table117921043305"></a>
<table><thead align="left"><tr id="cce_02_0252_row55001954122614"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="cce_02_0252_p115009545264"><a name="cce_02_0252_p115009545264"></a><a name="cce_02_0252_p115009545264"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.4.1.2"><p id="cce_02_0252_p175001547265"><a name="cce_02_0252_p175001547265"></a><a name="cce_02_0252_p175001547265"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61%" id="mcps1.2.4.1.3"><p id="cce_02_0252_p16500154162611"><a name="cce_02_0252_p16500154162611"></a><a name="cce_02_0252_p16500154162611"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="cce_02_0252_row199801811203412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="cce_02_0252_p69808112344"><a name="cce_02_0252_p69808112344"></a><a name="cce_02_0252_p69808112344"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="cce_02_0252_p3980111103414"><a name="cce_02_0252_p3980111103414"></a><a name="cce_02_0252_p3980111103414"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="cce_02_0252_p2032514065313"><a name="cce_02_0252_p2032514065313"></a><a name="cce_02_0252_p2032514065313"></a>消息体的类型（格式），可任选其一使用。</p>
<a name="cce_02_0252_ul7385444163617"></a><a name="cce_02_0252_ul7385444163617"></a><ul id="cce_02_0252_ul7385444163617"><li>application/json;charset=utf-8</li><li>application/json</li></ul>
</td>
</tr>
<tr id="cce_02_0252_row3500125412260"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="cce_02_0252_p105001654202618"><a name="cce_02_0252_p105001654202618"></a><a name="cce_02_0252_p105001654202618"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="cce_02_0252_p20500954182618"><a name="cce_02_0252_p20500954182618"></a><a name="cce_02_0252_p20500954182618"></a>使用token认证时必选</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="cce_02_0252_p1148116013545"><a name="cce_02_0252_p1148116013545"></a><a name="cce_02_0252_p1148116013545"></a>调用接口的一种认证方式，使用时需要<a href="认证鉴权.md#section2417768214391">获取token</a>.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

NA

## 响应消息<a name="section61819725020"></a>

**响应参数：**

响应参数如[表3](#table146621347181415)所示。

**表 3**  参数描述

<a name="table146621347181415"></a>
<table><thead align="left"><tr id="row12662154712149"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p1679411287150"><a name="p1679411287150"></a><a name="p1679411287150"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.2"><p id="p4796728141514"><a name="p4796728141514"></a><a name="p4796728141514"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.3"><p id="p579802813152"><a name="p579802813152"></a><a name="p579802813152"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="p1799172821519"><a name="p1799172821519"></a><a name="p1799172821519"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row966224741418"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1711565711146"><a name="p1711565711146"></a><a name="p1711565711146"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p611775741413"><a name="p611775741413"></a><a name="p611775741413"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p61215578148"><a name="p61215578148"></a><a name="p61215578148"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p1112325714147"><a name="p1112325714147"></a><a name="p1112325714147"></a>API版本，固定值＂v1＂</p>
</td>
</tr>
<tr id="row56621547141412"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p612513579149"><a name="p612513579149"></a><a name="p612513579149"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p2012725751410"><a name="p2012725751410"></a><a name="p2012725751410"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p1129105713148"><a name="p1129105713148"></a><a name="p1129105713148"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p8131175711147"><a name="p8131175711147"></a><a name="p8131175711147"></a>API类型，固定值＂PersistentVolumeClaim＂</p>
</td>
</tr>
<tr id="row366204715144"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p19132105713147"><a name="p19132105713147"></a><a name="p19132105713147"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p15134357161414"><a name="p15134357161414"></a><a name="p15134357161414"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p1913585701410"><a name="p1913585701410"></a><a name="p1913585701410"></a><a href="#table1945363971613">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p17136135781419"><a name="p17136135781419"></a><a name="p17136135781419"></a>-</p>
</td>
</tr>
<tr id="row866215472144"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p16801171311162"><a name="p16801171311162"></a><a name="p16801171311162"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p11801111318165"><a name="p11801111318165"></a><a name="p11801111318165"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p167731241144016"><a name="p167731241144016"></a><a name="p167731241144016"></a><a href="#table19793181719183">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p15801713171610"><a name="p15801713171610"></a><a name="p15801713171610"></a>-</p>
</td>
</tr>
<tr id="row1155885214159"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1524125981516"><a name="p1524125981516"></a><a name="p1524125981516"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p452455971510"><a name="p452455971510"></a><a name="p452455971510"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p2524459171518"><a name="p2524459171518"></a><a name="p2524459171518"></a><a href="#table6872113611911">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p955819520155"><a name="p955819520155"></a><a name="p955819520155"></a>-</p>
</td>
</tr>
</tbody>
</table>

**表 4**  metadata字段数据结构说明

<a name="table1945363971613"></a>
<table><thead align="left"><tr id="row449323981614"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p24934390169"><a name="p24934390169"></a><a name="p24934390169"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13%" id="mcps1.2.5.1.2"><p id="p1049333913167"><a name="p1049333913167"></a><a name="p1049333913167"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18%" id="mcps1.2.5.1.3"><p id="p2493939141611"><a name="p2493939141611"></a><a name="p2493939141611"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="49%" id="mcps1.2.5.1.4"><p id="p6493239191614"><a name="p6493239191614"></a><a name="p6493239191614"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row144931839131615"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1493153961618"><a name="p1493153961618"></a><a name="p1493153961618"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.5.1.2 "><p id="p17493739191613"><a name="p17493739191613"></a><a name="p17493739191613"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.3 "><p id="p049343914165"><a name="p049343914165"></a><a name="p049343914165"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49%" headers="mcps1.2.5.1.4 "><p id="p5181301009"><a name="p5181301009"></a><a name="p5181301009"></a>PersistentVolumeClaim名称，可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符，同一namespace下name不能重复。</p>
</td>
</tr>
<tr id="row949303931617"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p549453918167"><a name="p549453918167"></a><a name="p549453918167"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.5.1.2 "><p id="p149412395169"><a name="p149412395169"></a><a name="p149412395169"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.3 "><p id="p19494183919169"><a name="p19494183919169"></a><a name="p19494183919169"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49%" headers="mcps1.2.5.1.4 "><p id="p418368504"><a name="p418368504"></a><a name="p418368504"></a>PersistentVolumeClaim标签，key/value对格式。</p>
<a name="ul1736685012"></a><a name="ul1736685012"></a><ul id="ul1736685012"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</li><li>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li></ul>
<p id="p156295249512"><a name="p156295249512"></a><a name="p156295249512"></a>示例："foo": "bar"</p>
</td>
</tr>
</tbody>
</table>

**表 5**  spec字段数据结构说明

<a name="table19793181719183"></a>
<table><thead align="left"><tr id="row1979411177180"><th class="cellrowborder" valign="top" width="14.59%" id="mcps1.2.5.1.1"><p id="p19814255187"><a name="p19814255187"></a><a name="p19814255187"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.57%" id="mcps1.2.5.1.2"><p id="p983122519186"><a name="p983122519186"></a><a name="p983122519186"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.990000000000002%" id="mcps1.2.5.1.3"><p id="p1484132511814"><a name="p1484132511814"></a><a name="p1484132511814"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="51.849999999999994%" id="mcps1.2.5.1.4"><p id="p11882025141817"><a name="p11882025141817"></a><a name="p11882025141817"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row979411713185"><td class="cellrowborder" valign="top" width="14.59%" headers="mcps1.2.5.1.1 "><p id="p13921425191812"><a name="p13921425191812"></a><a name="p13921425191812"></a>volumeName</p>
</td>
<td class="cellrowborder" valign="top" width="12.57%" headers="mcps1.2.5.1.2 "><p id="p194102521818"><a name="p194102521818"></a><a name="p194102521818"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20.990000000000002%" headers="mcps1.2.5.1.3 "><p id="p9952254189"><a name="p9952254189"></a><a name="p9952254189"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.849999999999994%" headers="mcps1.2.5.1.4 "><p id="p298182531811"><a name="p298182531811"></a><a name="p298182531811"></a>绑定引用的PersistentVolume名称</p>
</td>
</tr>
<tr id="row47941117101813"><td class="cellrowborder" valign="top" width="14.59%" headers="mcps1.2.5.1.1 "><p id="p10102162571819"><a name="p10102162571819"></a><a name="p10102162571819"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="12.57%" headers="mcps1.2.5.1.2 "><p id="p81041025171810"><a name="p81041025171810"></a><a name="p81041025171810"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.990000000000002%" headers="mcps1.2.5.1.3 "><p id="p11106525181819"><a name="p11106525181819"></a><a name="p11106525181819"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="51.849999999999994%" headers="mcps1.2.5.1.4 "><p id="p9923162562416"><a name="p9923162562416"></a><a name="p9923162562416"></a>指定volume应该具有的访问模式。</p>
<a name="ul8320115773216"></a><a name="ul8320115773216"></a><ul id="ul8320115773216"><li>ReadWriteOnce：该卷可以被单个节点以读/写模式挂载<div class="note" id="note1348319103139"><a name="note1348319103139"></a><a name="note1348319103139"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p19484810151313"><a name="p19484810151313"></a><a name="p19484810151313"></a>集群版本为v1.13.10且storage-driver版本为1.0.19时，才支持此功能。</p>
</div></div>
</li><li>ReadOnlyMany：该卷可以被多个节点以只读模式挂载</li><li>ReadWriteMany：该卷可以被多个节点以读/写模式挂载</li></ul>
</td>
</tr>
</tbody>
</table>

**表 6**  status字段数据结构说明

<a name="table6872113611911"></a>
<table><thead align="left"><tr id="row1872336191918"><th class="cellrowborder" valign="top" width="21.782178217821777%" id="mcps1.2.5.1.1"><p id="p4287411132016"><a name="p4287411132016"></a><a name="p4287411132016"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.8019801980198%" id="mcps1.2.5.1.2"><p id="p1428991112203"><a name="p1428991112203"></a><a name="p1428991112203"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.81188118811881%" id="mcps1.2.5.1.3"><p id="p16292711162010"><a name="p16292711162010"></a><a name="p16292711162010"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.6039603960396%" id="mcps1.2.5.1.4"><p id="p102941111192018"><a name="p102941111192018"></a><a name="p102941111192018"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row7872203631913"><td class="cellrowborder" valign="top" width="21.782178217821777%" headers="mcps1.2.5.1.1 "><p id="p3299151142013"><a name="p3299151142013"></a><a name="p3299151142013"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="19.8019801980198%" headers="mcps1.2.5.1.2 "><p id="p6302121114201"><a name="p6302121114201"></a><a name="p6302121114201"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p73047117200"><a name="p73047117200"></a><a name="p73047117200"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="39.6039603960396%" headers="mcps1.2.5.1.4 "><p id="p133061711162014"><a name="p133061711162014"></a><a name="p133061711162014"></a>显示volume实际具有的访问模式</p>
</td>
</tr>
<tr id="row168721836171912"><td class="cellrowborder" valign="top" width="21.782178217821777%" headers="mcps1.2.5.1.1 "><p id="p1130901117208"><a name="p1130901117208"></a><a name="p1130901117208"></a>capacity</p>
</td>
<td class="cellrowborder" valign="top" width="19.8019801980198%" headers="mcps1.2.5.1.2 "><p id="p16311171142017"><a name="p16311171142017"></a><a name="p16311171142017"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p931311112202"><a name="p931311112202"></a><a name="p931311112202"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="39.6039603960396%" headers="mcps1.2.5.1.4 "><p id="p105861929133913"><a name="p105861929133913"></a><a name="p105861929133913"></a>底层卷的实际存储空间大小，例："storage": "1Gi"</p>
</td>
</tr>
<tr id="row1873113618196"><td class="cellrowborder" valign="top" width="21.782178217821777%" headers="mcps1.2.5.1.1 "><p id="p6318411102016"><a name="p6318411102016"></a><a name="p6318411102016"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="19.8019801980198%" headers="mcps1.2.5.1.2 "><p id="p5320811102019"><a name="p5320811102019"></a><a name="p5320811102019"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p133221911192018"><a name="p133221911192018"></a><a name="p133221911192018"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.6039603960396%" headers="mcps1.2.5.1.4 "><p id="p16324111115200"><a name="p16324111115200"></a><a name="p16324111115200"></a>PersistentVolumeClaim当前所处的状态</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "PersistentVolumeClaim",
    "apiVersion": "v1",
    "metadata": {
        "name": " csms-dev-create ",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims/db-mysql-0",
        "uid": "86b29e16-23db-11e7-9c83-fa163ec08232",
        "resourceVersion": "1793115",
        "creationTimestamp": "2017-04-18T02:05:42Z"
    },
    "spec": {
        "volumeName": "csms-dev-create ",
        "accessModes": [
            "ReadWriteMany"
        ],
        "resources": {
            "requests": {
                "storage": "1Gi"
            }
        }
    },
    "status": {
        "phase": "Pending",
        "accessModes": [
            "ReadWriteMany"
        ]
    }
}
```

## 状态码<a name="s50f1049a6a4d404c895cf636eb8f3bf1"></a>

[表 3 状态码](#zh-cn_topic_0079614900_table46761928)描述API的状态码。

**表 7**  状态码

<a name="zh-cn_topic_0079614900_table46761928"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row33254664"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p55616028205955"><a name="p55616028205955"></a><a name="p55616028205955"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p8604418205955"><a name="p8604418205955"></a><a name="p8604418205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row41084259"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614900_p39490674"><a name="zh-cn_topic_0079614900_p39490674"></a><a name="zh-cn_topic_0079614900_p39490674"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614900_p44628050"><a name="zh-cn_topic_0079614900_p44628050"></a><a name="zh-cn_topic_0079614900_p44628050"></a>删除指定PersistentVolumeClaim作业下发成功。</p>
</td>
</tr>
</tbody>
</table>

