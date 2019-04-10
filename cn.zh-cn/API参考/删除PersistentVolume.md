# 删除PersistentVolume<a name="cce_02_0255"></a>

## 功能描述<a name="section155195145312"></a>

该API用于删除指定Namespace下的PersistentVolume对象，并可以选择是否保留后端云存储。

## URI<a name="section1975393831219"></a>

DELETE /api/v1/cloudpersistentvolumes/\{name\}

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
<tbody><tr id="row32801312121810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p16285269571"><a name="p16285269571"></a><a name="p16285269571"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.4.1.2 "><p id="p15628162645710"><a name="p15628162645710"></a><a name="p15628162645710"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="68%" headers="mcps1.2.4.1.3 "><p id="p18628172618571"><a name="p18628172618571"></a><a name="p18628172618571"></a>需要删除的PersistentVolume的名称</p>
<p id="p1735311268328"><a name="p1735311268328"></a><a name="p1735311268328"></a>name格式为：Volume名称[?deleteVolume=BOOLEAN&amp;storageType=云存储类型]，中括号内可省略，示例：</p>
<a name="ul1619719362324"></a><a name="ul1619719362324"></a><ul id="ul1619719362324"><li>volume-49f1?deleteVolume=true&amp;storageType=bs</li><li>volume-49f1</li></ul>
<p id="p62371018179"><a name="p62371018179"></a><a name="p62371018179"></a>其中：</p>
<a name="ul0576131593"></a><a name="ul0576131593"></a><ul id="ul0576131593"><li>deleteVolume：删除PersistentVolume后是否保留后端关联的云存储。false表示不删除，ture表示删除，默认为false。（注：当为efs时，不支持删除存储，所以不能设为true）</li></ul>
<a name="ul197198369911"></a><a name="ul197198369911"></a><ul id="ul197198369911"><li>storageType：云存储的类型，和deleteVolume搭配使用。即deleteVolume和storageType必须同时配置。<a name="ul91497416910"></a><a name="ul91497416910"></a><ul id="ul91497416910"><li>bs：EVS云存储</li><li>nfs：SFS弹性文件存储</li><li>obs：OBS对象存储</li><li>efs：SFS Turbo极速文件存储</li></ul>
</li></ul>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section1142842461418"></a>

**请求参数：**

请求参数如[表2](#table1355761351720)所示。

**表 2**  请求Header参数说明

<a name="table1355761351720"></a>
<table><thead align="left"><tr id="cce_02_0253_cce_02_0252_row55001954122614"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="cce_02_0253_cce_02_0252_p115009545264"><a name="cce_02_0253_cce_02_0252_p115009545264"></a><a name="cce_02_0253_cce_02_0252_p115009545264"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.4.1.2"><p id="cce_02_0253_cce_02_0252_p175001547265"><a name="cce_02_0253_cce_02_0252_p175001547265"></a><a name="cce_02_0253_cce_02_0252_p175001547265"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61%" id="mcps1.2.4.1.3"><p id="cce_02_0253_cce_02_0252_p16500154162611"><a name="cce_02_0253_cce_02_0252_p16500154162611"></a><a name="cce_02_0253_cce_02_0252_p16500154162611"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="cce_02_0253_cce_02_0252_row199801811203412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="cce_02_0253_cce_02_0252_p69808112344"><a name="cce_02_0253_cce_02_0252_p69808112344"></a><a name="cce_02_0253_cce_02_0252_p69808112344"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="cce_02_0253_cce_02_0252_p3980111103414"><a name="cce_02_0253_cce_02_0252_p3980111103414"></a><a name="cce_02_0253_cce_02_0252_p3980111103414"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="cce_02_0253_cce_02_0252_p2032514065313"><a name="cce_02_0253_cce_02_0252_p2032514065313"></a><a name="cce_02_0253_cce_02_0252_p2032514065313"></a>消息体的类型（格式），可任选其一使用。</p>
<a name="cce_02_0253_cce_02_0252_ul7385444163617"></a><a name="cce_02_0253_cce_02_0252_ul7385444163617"></a><ul id="cce_02_0253_cce_02_0252_ul7385444163617"><li>application/json;charset=utf-8</li><li>application/json</li></ul>
</td>
</tr>
<tr id="cce_02_0253_cce_02_0252_row3500125412260"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="cce_02_0253_cce_02_0252_p105001654202618"><a name="cce_02_0253_cce_02_0252_p105001654202618"></a><a name="cce_02_0253_cce_02_0252_p105001654202618"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="cce_02_0253_cce_02_0252_p20500954182618"><a name="cce_02_0253_cce_02_0252_p20500954182618"></a><a name="cce_02_0253_cce_02_0252_p20500954182618"></a>使用token认证时必选</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="cce_02_0253_cce_02_0252_p1148116013545"><a name="cce_02_0253_cce_02_0252_p1148116013545"></a><a name="cce_02_0253_cce_02_0252_p1148116013545"></a>调用接口的一种认证方式，使用时需要<a href="获取请求认证.md#section2417768214391">获取token</a>。</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

NA

## 响应消息<a name="section61819725020"></a>

**响应参数：**

响应参数如[表3](#table6458134035814)所示。

**表 3**  参数描述

<a name="table6458134035814"></a>
<table><thead align="left"><tr id="row8825140195819"><th class="cellrowborder" valign="top" width="19.58804119588041%" id="mcps1.2.5.1.1"><p id="p148255401588"><a name="p148255401588"></a><a name="p148255401588"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.55814418558144%" id="mcps1.2.5.1.2"><p id="p14825164011586"><a name="p14825164011586"></a><a name="p14825164011586"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.55814418558144%" id="mcps1.2.5.1.3"><p id="p48258403584"><a name="p48258403584"></a><a name="p48258403584"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.295670432956705%" id="mcps1.2.5.1.4"><p id="p5825540125816"><a name="p5825540125816"></a><a name="p5825540125816"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1182512403583"><td class="cellrowborder" valign="top" width="19.58804119588041%" headers="mcps1.2.5.1.1 "><p id="p1582516409584"><a name="p1582516409584"></a><a name="p1582516409584"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.2 "><p id="p6825114055819"><a name="p6825114055819"></a><a name="p6825114055819"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.3 "><p id="p158251740185814"><a name="p158251740185814"></a><a name="p158251740185814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.295670432956705%" headers="mcps1.2.5.1.4 "><p id="p16825144045815"><a name="p16825144045815"></a><a name="p16825144045815"></a>API版本，固定值＂v1＂</p>
</td>
</tr>
<tr id="row1282564013582"><td class="cellrowborder" valign="top" width="19.58804119588041%" headers="mcps1.2.5.1.1 "><p id="p58250401585"><a name="p58250401585"></a><a name="p58250401585"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.2 "><p id="p128251240185818"><a name="p128251240185818"></a><a name="p128251240185818"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.3 "><p id="p2825114095810"><a name="p2825114095810"></a><a name="p2825114095810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.295670432956705%" headers="mcps1.2.5.1.4 "><p id="p88251640155820"><a name="p88251640155820"></a><a name="p88251640155820"></a>API类型，固定值＂PersistentVolume＂</p>
</td>
</tr>
<tr id="row128251840135810"><td class="cellrowborder" valign="top" width="19.58804119588041%" headers="mcps1.2.5.1.1 "><p id="p7825184015582"><a name="p7825184015582"></a><a name="p7825184015582"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.2 "><p id="p14825124065817"><a name="p14825124065817"></a><a name="p14825124065817"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.3 "><p id="p128252400587"><a name="p128252400587"></a><a name="p128252400587"></a><a href="#table59658333596">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.295670432956705%" headers="mcps1.2.5.1.4 "><p id="p78257406588"><a name="p78257406588"></a><a name="p78257406588"></a>-</p>
</td>
</tr>
<tr id="row1782519409588"><td class="cellrowborder" valign="top" width="19.58804119588041%" headers="mcps1.2.5.1.1 "><p id="p9825194085818"><a name="p9825194085818"></a><a name="p9825194085818"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.2 "><p id="p782534015585"><a name="p782534015585"></a><a name="p782534015585"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.3 "><p id="p10825240135814"><a name="p10825240135814"></a><a name="p10825240135814"></a><a href="#table74541616408">表5</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.295670432956705%" headers="mcps1.2.5.1.4 "><p id="p10825144075818"><a name="p10825144075818"></a><a name="p10825144075818"></a>-</p>
</td>
</tr>
<tr id="row1825154010582"><td class="cellrowborder" valign="top" width="19.58804119588041%" headers="mcps1.2.5.1.1 "><p id="p682574010581"><a name="p682574010581"></a><a name="p682574010581"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.2 "><p id="p18252406585"><a name="p18252406585"></a><a name="p18252406585"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.55814418558144%" headers="mcps1.2.5.1.3 "><p id="p0825240175819"><a name="p0825240175819"></a><a name="p0825240175819"></a><a href="#table1497912571012">表6</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.295670432956705%" headers="mcps1.2.5.1.4 "><p id="p1682594065810"><a name="p1682594065810"></a><a name="p1682594065810"></a>-</p>
</td>
</tr>
</tbody>
</table>

**表 4**  metadata字段数据结构说明

<a name="table59658333596"></a>
<table><thead align="left"><tr id="row182348592"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p09134105913"><a name="p09134105913"></a><a name="p09134105913"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13%" id="mcps1.2.5.1.2"><p id="p139934125915"><a name="p139934125915"></a><a name="p139934125915"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18%" id="mcps1.2.5.1.3"><p id="p5973485918"><a name="p5973485918"></a><a name="p5973485918"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="49%" id="mcps1.2.5.1.4"><p id="p39173411591"><a name="p39173411591"></a><a name="p39173411591"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12913445919"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p15903465918"><a name="p15903465918"></a><a name="p15903465918"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.5.1.2 "><p id="p191534125920"><a name="p191534125920"></a><a name="p191534125920"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.3 "><p id="p119034105917"><a name="p119034105917"></a><a name="p119034105917"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49%" headers="mcps1.2.5.1.4 "><p id="p69234125916"><a name="p69234125916"></a><a name="p69234125916"></a>PersistentVolume名称，可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符，同一namespace下name不能重复。例：my-pv</p>
</td>
</tr>
<tr id="row1598346595"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p09434155916"><a name="p09434155916"></a><a name="p09434155916"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.5.1.2 "><p id="p49834175917"><a name="p49834175917"></a><a name="p49834175917"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.3 "><p id="p1893342599"><a name="p1893342599"></a><a name="p1893342599"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49%" headers="mcps1.2.5.1.4 "><p id="p1891734165913"><a name="p1891734165913"></a><a name="p1891734165913"></a>PersistentVolume标签，key/value对格式。</p>
<a name="ul1736685012"></a><a name="ul1736685012"></a><ul id="ul1736685012"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</li><li>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li></ul>
<p id="p156295249512"><a name="p156295249512"></a><a name="p156295249512"></a>示例："foo": "bar"</p>
</td>
</tr>
</tbody>
</table>

**表 5**  spec字段数据结构说明

<a name="table74541616408"></a>
<table><thead align="left"><tr id="row134931316505"><th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.5.1.1"><p id="p149320165019"><a name="p149320165019"></a><a name="p149320165019"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.18181818181818%" id="mcps1.2.5.1.2"><p id="p24931916207"><a name="p24931916207"></a><a name="p24931916207"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.19191919191919%" id="mcps1.2.5.1.3"><p id="p949315163013"><a name="p949315163013"></a><a name="p949315163013"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.42424242424242%" id="mcps1.2.5.1.4"><p id="p1049317161300"><a name="p1049317161300"></a><a name="p1049317161300"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row20493191611011"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="p1249311161301"><a name="p1249311161301"></a><a name="p1249311161301"></a>volumeName</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="p7493151618015"><a name="p7493151618015"></a><a name="p7493151618015"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.5.1.3 "><p id="p1349311611011"><a name="p1349311611011"></a><a name="p1349311611011"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="p67502719517"><a name="p67502719517"></a><a name="p67502719517"></a>绑定引用的PersistentVolume名称。</p>
<div class="note" id="note11331181334716"><a name="note11331181334716"></a><a name="note11331181334716"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p43313134474"><a name="p43313134474"></a><a name="p43313134474"></a>若“volumeID”配置为“是”，该字段取值无效。</p>
</div></div>
</td>
</tr>
<tr id="row149313161702"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="p5493416904"><a name="p5493416904"></a><a name="p5493416904"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="p749315161203"><a name="p749315161203"></a><a name="p749315161203"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.5.1.3 "><p id="p0493716705"><a name="p0493716705"></a><a name="p0493716705"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="p1449315169018"><a name="p1449315169018"></a><a name="p1449315169018"></a>指定volume应该具有的访问模式，包括：</p>
<a name="ul20281165712148"></a><a name="ul20281165712148"></a><ul id="ul20281165712148"><li>ReadWriteOnce：该卷可以被单个节点以读/写模式挂载</li><li>ReadOnlyMany：该卷可以被多个节点以只读模式挂载</li><li>ReadWriteMany：该卷可以被多个节点以读/写模式挂载</li></ul>
</td>
</tr>
</tbody>
</table>

**表 6**  status字段数据结构说明

<a name="table1497912571012"></a>
<table><thead align="left"><tr id="row10221458901"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.1"><p id="p1922175820018"><a name="p1922175820018"></a><a name="p1922175820018"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.5.1.2"><p id="p22213588014"><a name="p22213588014"></a><a name="p22213588014"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.3"><p id="p142245819016"><a name="p142245819016"></a><a name="p142245819016"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.85571442855714%" id="mcps1.2.5.1.4"><p id="p152265811018"><a name="p152265811018"></a><a name="p152265811018"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row222115810015"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p122158305"><a name="p122158305"></a><a name="p122158305"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p172218581408"><a name="p172218581408"></a><a name="p172218581408"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p16221958407"><a name="p16221958407"></a><a name="p16221958407"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p22216583013"><a name="p22216583013"></a><a name="p22216583013"></a>显示volume实际具有的访问模式</p>
</td>
</tr>
<tr id="row142213581504"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p11225588012"><a name="p11225588012"></a><a name="p11225588012"></a>capacity</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p322135819018"><a name="p322135819018"></a><a name="p322135819018"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p172225812019"><a name="p172225812019"></a><a name="p172225812019"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p112235812020"><a name="p112235812020"></a><a name="p112235812020"></a>底层卷的实际存储空间大小，例：</p>
<a name="ul83971634395"></a><a name="ul83971634395"></a><ul id="ul83971634395"><li>"storage": "1Gi"</li></ul>
</td>
</tr>
<tr id="row822158705"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p122155818015"><a name="p122155818015"></a><a name="p122155818015"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p1322205815010"><a name="p1322205815010"></a><a name="p1322205815010"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p1022958406"><a name="p1022958406"></a><a name="p1022958406"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p12365811013"><a name="p12365811013"></a><a name="p12365811013"></a>PersistentVolume当前所处的状态，包括：</p>
<a name="ul1051916493218"></a><a name="ul1051916493218"></a><ul id="ul1051916493218"><li>Available（可用）：还是空闲资源，没有被任何PVC绑定</li><li>Bound（已绑定）：卷已经被PVC绑定</li><li>Released（已释放）：之前绑定的PVC被删除，但是资源还未被集群重新声明</li><li>Failed（失败）：该卷的自动回收失败</li></ul>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "PersistentVolume",
    "apiVersion": "v1",
    "metadata": {
        "name": "pv-test",
        "selfLink": "/api/v1/persistentvolumes/pv-test",
        "uid": "0d93181d-3628-11e7-9093-fa163e8c373b",
        "resourceVersion": "180886",
        "creationTimestamp": "2017-05-11T08:58:51Z",
        "labels": {
            "app": "test"
        }
    },
    "spec": {
        "flexVolume": {
            "driver": "huawei.com/fuxivol",
            "fsType": "ext4",
            "options": {
                "fsType": "ext4",
                "kubernetes.io/namespace": "default",
                "volumeID": "0781b22f-4d89-4e9c-b026-80e545cea16c"
            }
        },
        "capacity": {
            "storage": "1Gi"
        },
        "accessModes": [
            "ReadWriteMany"
        ],
        "persistentVolumeReclaimPolicy": "Delete"
    },
    "status": {
        "phase": "Available"
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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614900_p44628050"><a name="zh-cn_topic_0079614900_p44628050"></a><a name="zh-cn_topic_0079614900_p44628050"></a>删除指定PersistentVolume作业下发成功。</p>
</td>
</tr>
</tbody>
</table>

