# 创建PersistentVolume（已废弃）<a name="cce_02_0256"></a>

## 功能描述<a name="section155195145312"></a>

该API用于通过指定云存储服务中的云存储（如EVS、SFS、OBS）去创建PersistentVolume。

## URI<a name="section1975393831219"></a>

POST /api/v1/cloudpersistentvolumes

## 请求消息<a name="section1142842461418"></a>

**请求参数：**

请求参数如[表1](#table31885335210)、[表2](#table26761425181512)所示。

**表 1**  请求Header参数说明

<a name="table31885335210"></a>
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

**表 2**  请求body参数说明

<a name="table26761425181512"></a>
<table><thead align="left"><tr id="row107441225201515"><th class="cellrowborder" valign="top" width="19.801980198019802%" id="mcps1.2.5.1.1"><p id="p57445253154"><a name="p57445253154"></a><a name="p57445253154"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.81188118811881%" id="mcps1.2.5.1.2"><p id="p11744152514157"><a name="p11744152514157"></a><a name="p11744152514157"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.81188118811881%" id="mcps1.2.5.1.3"><p id="p14744172517156"><a name="p14744172517156"></a><a name="p14744172517156"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.57425742574257%" id="mcps1.2.5.1.4"><p id="p1474411256156"><a name="p1474411256156"></a><a name="p1474411256156"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1574452581519"><td class="cellrowborder" valign="top" width="19.801980198019802%" headers="mcps1.2.5.1.1 "><p id="p16744192510159"><a name="p16744192510159"></a><a name="p16744192510159"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.2 "><p id="p6883728134011"><a name="p6883728134011"></a><a name="p6883728134011"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p97441825111518"><a name="p97441825111518"></a><a name="p97441825111518"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.57425742574257%" headers="mcps1.2.5.1.4 "><p id="p9745152531519"><a name="p9745152531519"></a><a name="p9745152531519"></a>API版本，固定值＂v1＂</p>
</td>
</tr>
<tr id="row87455255158"><td class="cellrowborder" valign="top" width="19.801980198019802%" headers="mcps1.2.5.1.1 "><p id="p117456259153"><a name="p117456259153"></a><a name="p117456259153"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.2 "><p id="p102721431204019"><a name="p102721431204019"></a><a name="p102721431204019"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p157451525111516"><a name="p157451525111516"></a><a name="p157451525111516"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.57425742574257%" headers="mcps1.2.5.1.4 "><p id="p874542515151"><a name="p874542515151"></a><a name="p874542515151"></a>API类型，固定值＂PersistentVolume＂</p>
</td>
</tr>
<tr id="row16745125101516"><td class="cellrowborder" valign="top" width="19.801980198019802%" headers="mcps1.2.5.1.1 "><p id="p177451725101517"><a name="p177451725101517"></a><a name="p177451725101517"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.2 "><p id="p1062853354013"><a name="p1062853354013"></a><a name="p1062853354013"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p074532551518"><a name="p074532551518"></a><a name="p074532551518"></a><a href="#table6304105819164">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.57425742574257%" headers="mcps1.2.5.1.4 "><p id="p2745152519150"><a name="p2745152519150"></a><a name="p2745152519150"></a>-</p>
</td>
</tr>
<tr id="row2745725201512"><td class="cellrowborder" valign="top" width="19.801980198019802%" headers="mcps1.2.5.1.1 "><p id="p8745025151519"><a name="p8745025151519"></a><a name="p8745025151519"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.2 "><p id="p8581153624016"><a name="p8581153624016"></a><a name="p8581153624016"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p1574522520158"><a name="p1574522520158"></a><a name="p1574522520158"></a><a href="#table3862152512246">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.57425742574257%" headers="mcps1.2.5.1.4 "><p id="p97458257151"><a name="p97458257151"></a><a name="p97458257151"></a>-</p>
</td>
</tr>
<tr id="row67451925181517"><td class="cellrowborder" valign="top" width="19.801980198019802%" headers="mcps1.2.5.1.1 "><p id="p107451025111518"><a name="p107451025111518"></a><a name="p107451025111518"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.2 "><p id="p1574516258158"><a name="p1574516258158"></a><a name="p1574516258158"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p874562561514"><a name="p874562561514"></a><a name="p874562561514"></a><a href="#table478913499397">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.57425742574257%" headers="mcps1.2.5.1.4 "><p id="p8745172518154"><a name="p8745172518154"></a><a name="p8745172518154"></a>-</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="table6304105819164"></a>
<table><thead align="left"><tr id="row630412582164"><th class="cellrowborder" valign="top" width="18.81188118811881%" id="mcps1.2.5.1.1"><p id="p55461758152314"><a name="p55461758152314"></a><a name="p55461758152314"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.831683168316832%" id="mcps1.2.5.1.2"><p id="p754645816237"><a name="p754645816237"></a><a name="p754645816237"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.81188118811881%" id="mcps1.2.5.1.3"><p id="p354612586239"><a name="p354612586239"></a><a name="p354612586239"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45.54455445544555%" id="mcps1.2.5.1.4"><p id="p754625882316"><a name="p754625882316"></a><a name="p754625882316"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row4304175891615"><td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.1 "><p id="p81931402411"><a name="p81931402411"></a><a name="p81931402411"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.831683168316832%" headers="mcps1.2.5.1.2 "><p id="p21931847246"><a name="p21931847246"></a><a name="p21931847246"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p15193194192418"><a name="p15193194192418"></a><a name="p15193194192418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.54455445544555%" headers="mcps1.2.5.1.4 "><p id="p17193543245"><a name="p17193543245"></a><a name="p17193543245"></a>PersistentVolume名称，可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符，同一namespace下name不能重复。</p>
</td>
</tr>
<tr id="row5304758171616"><td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.1 "><p id="p519318462411"><a name="p519318462411"></a><a name="p519318462411"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="16.831683168316832%" headers="mcps1.2.5.1.2 "><p id="p619364182418"><a name="p619364182418"></a><a name="p619364182418"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p1519316412248"><a name="p1519316412248"></a><a name="p1519316412248"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.54455445544555%" headers="mcps1.2.5.1.4 "><p id="p319310432413"><a name="p319310432413"></a><a name="p319310432413"></a>PersistentVolume标签，key/value对格式。</p>
<a name="ul1736685012"></a><a name="ul1736685012"></a><ul id="ul1736685012"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</li><li>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li></ul>
<p id="p156295249512"><a name="p156295249512"></a><a name="p156295249512"></a>示例："foo": "bar"</p>
</td>
</tr>
</tbody>
</table>

**表 4**  spec字段数据结构说明

<a name="table3862152512246"></a>
<table><thead align="left"><tr id="row292213259241"><th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.5.1.1"><p id="p892212511240"><a name="p892212511240"></a><a name="p892212511240"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.18181818181818%" id="mcps1.2.5.1.2"><p id="p199221125112412"><a name="p199221125112412"></a><a name="p199221125112412"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.19191919191919%" id="mcps1.2.5.1.3"><p id="p1592252520243"><a name="p1592252520243"></a><a name="p1592252520243"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.42424242424242%" id="mcps1.2.5.1.4"><p id="p19225259247"><a name="p19225259247"></a><a name="p19225259247"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18922102592411"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="p113621337112413"><a name="p113621337112413"></a><a name="p113621337112413"></a>flexVolume</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="p18362173742410"><a name="p18362173742410"></a><a name="p18362173742410"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.5.1.3 "><p id="p163629375243"><a name="p163629375243"></a><a name="p163629375243"></a><a href="#table11677121919263">flexVolume</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="p636233719244"><a name="p636233719244"></a><a name="p636233719244"></a>Kubernetes的flexvolume存储插件</p>
</td>
</tr>
<tr id="row8922225162418"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="p10362153713248"><a name="p10362153713248"></a><a name="p10362153713248"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="p5362337112412"><a name="p5362337112412"></a><a name="p5362337112412"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.5.1.3 "><p id="p136213375242"><a name="p136213375242"></a><a name="p136213375242"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="p12362837142418"><a name="p12362837142418"></a><a name="p12362837142418"></a>指定volume应该具有的访问模式。</p>
<a name="ul20281165712148"></a><a name="ul20281165712148"></a><ul id="ul20281165712148"><li>ReadWriteOnce：该卷可以被单个节点以读/写模式挂载<div class="note" id="note1348319103139"><a name="note1348319103139"></a><a name="note1348319103139"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p19484810151313"><a name="p19484810151313"></a><a name="p19484810151313"></a>集群版本为v1.13.10且storage-driver版本为1.0.19时，才支持此功能。</p>
</div></div>
</li><li>ReadOnlyMany：该卷可以被多个节点以只读模式挂载</li><li>ReadWriteMany：该卷可以被多个节点以读/写模式挂载</li></ul>
</td>
</tr>
<tr id="row13922112515249"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="p143621137182416"><a name="p143621137182416"></a><a name="p143621137182416"></a>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="p1536214371246"><a name="p1536214371246"></a><a name="p1536214371246"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.5.1.3 "><p id="p036214370243"><a name="p036214370243"></a><a name="p036214370243"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="p83621637192411"><a name="p83621637192411"></a><a name="p83621637192411"></a>PersistentVolume的回收策略，包括：</p>
<a name="ul6449173941614"></a><a name="ul6449173941614"></a><ul id="ul6449173941614"><li>Retain：保留策略允许手动回收资源。当 PersistentVolumeClaim 被删除时，PersistentVolume 仍然存在，volume 被视为“已释放”。</li><li>Recycle：回收策略会在 volume上执行基本擦除（rm -rf / thevolume / *），可被再次声明使用。</li><li>Delete：对于支持删除回收策略的卷插件，删除操作将从 Kubernetes 中删除 PersistentVolume 对象，并删除外部基础架构中的关联存储资产。动态配置的卷继承其 StorageClass，默认为 Delete。</li></ul>
</td>
</tr>
</tbody>
</table>

**表 5**  status字段数据结构说明

<a name="table478913499397"></a>
<table><thead align="left"><tr id="row149491749113917"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.1"><p id="p8949174923910"><a name="p8949174923910"></a><a name="p8949174923910"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.5.1.2"><p id="p14949149203910"><a name="p14949149203910"></a><a name="p14949149203910"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.3"><p id="p18949124916399"><a name="p18949124916399"></a><a name="p18949124916399"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.85571442855714%" id="mcps1.2.5.1.4"><p id="p14949124923919"><a name="p14949124923919"></a><a name="p14949124923919"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row39499497398"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p494914983911"><a name="p494914983911"></a><a name="p494914983911"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p19494490396"><a name="p19494490396"></a><a name="p19494490396"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p494924973913"><a name="p494924973913"></a><a name="p494924973913"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p894919493396"><a name="p894919493396"></a><a name="p894919493396"></a>显示volume实际具有的访问模式</p>
</td>
</tr>
<tr id="row10950144913397"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p15950144923914"><a name="p15950144923914"></a><a name="p15950144923914"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p13950949133913"><a name="p13950949133913"></a><a name="p13950949133913"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p1895044933913"><a name="p1895044933913"></a><a name="p1895044933913"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p159501649173914"><a name="p159501649173914"></a><a name="p159501649173914"></a>PersistentVolume当前所处的状态，包括：</p>
<a name="ul1051916493218"></a><a name="ul1051916493218"></a><ul id="ul1051916493218"><li>Available（可用）：还是空闲资源，没有被任何PVC绑定</li><li>Bound（已绑定）：卷已经被PVC绑定</li><li>Released（已释放）：之前绑定的PVC被删除，但是资源还未被集群重新声明</li><li>Failed（失败）：该卷的自动回收失败</li></ul>
</td>
</tr>
</tbody>
</table>

**表 6**  flexVolume字段数据结构说明

<a name="table11677121919263"></a>
<table><thead align="left"><tr id="row56771019202620"><th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.1"><p id="p1180044072613"><a name="p1180044072613"></a><a name="p1180044072613"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p3800134052614"><a name="p3800134052614"></a><a name="p3800134052614"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="22%" id="mcps1.2.5.1.3"><p id="p12800144010269"><a name="p12800144010269"></a><a name="p12800144010269"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47%" id="mcps1.2.5.1.4"><p id="p1480064015266"><a name="p1480064015266"></a><a name="p1480064015266"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1367741972615"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p823584616263"><a name="p823584616263"></a><a name="p823584616263"></a>driver</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1235134672611"><a name="p1235134672611"></a><a name="p1235134672611"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p1023513468266"><a name="p1023513468266"></a><a name="p1023513468266"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.5.1.4 "><p id="p1723544616263"><a name="p1723544616263"></a><a name="p1723544616263"></a>Flexvolume插件名称，请根据使用的存储类型填写：</p>
<a name="ul16335122794614"></a><a name="ul16335122794614"></a><ul id="ul16335122794614"><li>huawei.com/fuxivol (EVS)</li><li>huawei.com/fuxinfs (SFS)</li><li>huawei.com/fuxiobs (OBS)</li><li>huawei.com/fuxiefs (SFS Turbo)</li></ul>
</td>
</tr>
<tr id="row15677181962610"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p32351546112611"><a name="p32351546112611"></a><a name="p32351546112611"></a>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1523554618260"><a name="p1523554618260"></a><a name="p1523554618260"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p1023584614266"><a name="p1023584614266"></a><a name="p1023584614266"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.5.1.4 "><p id="p1123584642618"><a name="p1123584642618"></a><a name="p1123584642618"></a>文件系统类型，请根据使用的存储类型填写：</p>
<a name="ul17722202534718"></a><a name="ul17722202534718"></a><ul id="ul17722202534718"><li>ext4： EVS云硬盘存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0044.html" target="_blank" rel="noopener noreferrer">使用云硬盘存储卷</a> 。</li><li>nfs：SFS弹性文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0111.html" target="_blank" rel="noopener noreferrer">使用文件存储卷</a> 。</li><li>obs：OBS对象存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0160.html" target="_blank" rel="noopener noreferrer">使用对象存储卷</a> 。</li><li>efs：SFS Turbo极速文件存储，详情可参见<a href="https://support.huaweicloud.com/usermanual-cce/cce_01_0125.html" target="_blank" rel="noopener noreferrer">使用极速文件存储卷</a>。</li></ul>
</td>
</tr>
<tr id="row2678121972620"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p42353464268"><a name="p42353464268"></a><a name="p42353464268"></a>options</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1723518464266"><a name="p1723518464266"></a><a name="p1723518464266"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p223574612612"><a name="p223574612612"></a><a name="p223574612612"></a><a href="#table311414269276">options</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.5.1.4 "><p id="p323524616269"><a name="p323524616269"></a><a name="p323524616269"></a>-</p>
</td>
</tr>
</tbody>
</table>

**表 7**  options字段数据结构说明

<a name="table311414269276"></a>
<table><thead align="left"><tr id="row211582652717"><th class="cellrowborder" valign="top" width="13.861386138613863%" id="mcps1.2.5.1.1"><p id="p21681624202220"><a name="p21681624202220"></a><a name="p21681624202220"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.861386138613863%" id="mcps1.2.5.1.2"><p id="p17168162412227"><a name="p17168162412227"></a><a name="p17168162412227"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.841584158415841%" id="mcps1.2.5.1.3"><p id="p1168624112210"><a name="p1168624112210"></a><a name="p1168624112210"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="56.43564356435643%" id="mcps1.2.5.1.4"><p id="p141691324182211"><a name="p141691324182211"></a><a name="p141691324182211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1115826152715"><td class="cellrowborder" valign="top" width="13.861386138613863%" headers="mcps1.2.5.1.1 "><p id="p125557151227"><a name="p125557151227"></a><a name="p125557151227"></a>fsType</p>
</td>
<td class="cellrowborder" valign="top" width="13.861386138613863%" headers="mcps1.2.5.1.2 "><p id="p19555141562216"><a name="p19555141562216"></a><a name="p19555141562216"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.841584158415841%" headers="mcps1.2.5.1.3 "><p id="p1555511514222"><a name="p1555511514222"></a><a name="p1555511514222"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="56.43564356435643%" headers="mcps1.2.5.1.4 "><p id="p6555161522210"><a name="p6555161522210"></a><a name="p6555161522210"></a>文件系统类型，请根据使用的存储类型填写：</p>
<a name="ul91631136124611"></a><a name="ul91631136124611"></a><ul id="ul91631136124611"><li>ext4 (EVS)</li><li>nfs (SFS)</li><li>obs (OBS)</li><li>efs (SFS Turbo)</li></ul>
</td>
</tr>
<tr id="row1611562682718"><td class="cellrowborder" valign="top" width="13.861386138613863%" headers="mcps1.2.5.1.1 "><p id="p1755518156223"><a name="p1755518156223"></a><a name="p1755518156223"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="13.861386138613863%" headers="mcps1.2.5.1.2 "><p id="p1955510154226"><a name="p1955510154226"></a><a name="p1955510154226"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.841584158415841%" headers="mcps1.2.5.1.3 "><p id="p1055591514222"><a name="p1055591514222"></a><a name="p1055591514222"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="56.43564356435643%" headers="mcps1.2.5.1.4 "><p id="p18555315122215"><a name="p18555315122215"></a><a name="p18555315122215"></a>云存储所在的region。</p>
</td>
</tr>
<tr id="row11156268277"><td class="cellrowborder" valign="top" width="13.861386138613863%" headers="mcps1.2.5.1.1 "><p id="p175551115182210"><a name="p175551115182210"></a><a name="p175551115182210"></a>volumeID</p>
</td>
<td class="cellrowborder" valign="top" width="13.861386138613863%" headers="mcps1.2.5.1.2 "><p id="p8555915192216"><a name="p8555915192216"></a><a name="p8555915192216"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.841584158415841%" headers="mcps1.2.5.1.3 "><p id="p9556415182215"><a name="p9556415182215"></a><a name="p9556415182215"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="56.43564356435643%" headers="mcps1.2.5.1.4 "><p id="p185569154223"><a name="p185569154223"></a><a name="p185569154223"></a>云存储的UUID，如果是OBS-bucket则填入名称</p>
</td>
</tr>
<tr id="row17115192616279"><td class="cellrowborder" valign="top" width="13.861386138613863%" headers="mcps1.2.5.1.1 "><p id="p255615153226"><a name="p255615153226"></a><a name="p255615153226"></a>storageType</p>
</td>
<td class="cellrowborder" valign="top" width="13.861386138613863%" headers="mcps1.2.5.1.2 "><p id="p11559615192218"><a name="p11559615192218"></a><a name="p11559615192218"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.841584158415841%" headers="mcps1.2.5.1.3 "><p id="p18559315162216"><a name="p18559315162216"></a><a name="p18559315162216"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="56.43564356435643%" headers="mcps1.2.5.1.4 "><p id="p95591315182219"><a name="p95591315182219"></a><a name="p95591315182219"></a>指定云存储的类型。</p>
<a name="ul1396918418499"></a><a name="ul1396918418499"></a><ul id="ul1396918418499"><li>bs (EVS)</li><li>nfs (SFS)</li><li>obs (OBS)</li><li>efs (SFS Turbo)</li></ul>
</td>
</tr>
</tbody>
</table>

**请求示例：**

-   指定EVS云硬盘ID创建PersistentVolume

    1.9版本的集群样例：

    ```
    { 
        "apiVersion": "v1", 
        "kind": "PersistentVolume", 
        "metadata": { 
            "labels": { 
                "name": "pv-test" 
            }, 
            "name": "pv-test" 
        }, 
        "spec": { 
            "accessModes": [ 
                "ReadWriteMany" 
            ], 
            "flexVolume": { 
                "driver": "huawei.com/fuxivol", 
                "fsType": "ext4", 
                "options": { 
                    "fsType": "ext4", 
                    "kubernetes.io/namespace": "default", 
                    "region": "southchina", 
                    "volumeID": "76e01b29-08b9-11e8-9ca5-1051722006ec", 
                    "storageType": "bs" 
                } 
            }, 
            "persistentVolumeReclaimPolicy": "Delete" 
        } 
    }
    ```

    1.11及以上版本集群样例：

    ```
    { 
        "apiVersion": "v1", 
        "kind": "PersistentVolume", 
        "metadata": { 
            "labels": { 
                "name": "pv-test" 
            }, 
            "name": "pv-test" 
        }, 
        "spec": { 
            "accessModes": [ 
                "ReadWriteMany" 
            ], 
            "flexVolume": { 
                "driver": "huawei.com/fuxivol", 
                "fsType": "ext4", 
                "options": { 
                    "fsType": "ext4", 
                    "region": "southchina", 
                    "volumeID": "76e01b29-08b9-11e8-9ca5-1051722006ec", 
                    "storageType": "bs" 
                } 
            }, 
            "persistentVolumeReclaimPolicy": "Delete" 
        } 
    }
    ```

-   指定SFS文件存储ID创建PersistentVolume

    1.9版本的集群样例：

    ```
    { 
        "apiVersion": "v1", 
        "kind": "PersistentVolume", 
        "metadata": { 
            "labels": { 
                "name": "pv-test" 
            }, 
            "name": "pv-test" 
        }, 
        "spec": { 
            "accessModes": [ 
                "ReadWriteMany" 
            ], 
            "flexVolume": { 
                "driver": "huawei.com/fuxinfs", 
                "fsType": "nfs", 
                "options": { 
                    "fsType": "nfs ", 
                    "kubernetes.io/namespace": "default", 
                    "region": "southchina", 
                    "volumeID": "56e01b29-02b9-128-9ca5-1051722006ec", 
                    "storageType": "nfs" 
                } 
            }, 
            "persistentVolumeReclaimPolicy": "Delete" 
        } 
    }
    ```

    1.11及以上版本集群样例：

    ```
    { 
        "apiVersion": "v1", 
        "kind": "PersistentVolume", 
        "metadata": { 
            "labels": { 
                "name": "pv-test" 
            }, 
            "name": "pv-test" 
        }, 
        "spec": { 
            "accessModes": [ 
                "ReadWriteMany" 
            ], 
            "flexVolume": { 
                "driver": "huawei.com/fuxinfs", 
                "fsType": "nfs", 
                "options": { 
                    "fsType": "nfs ", 
                    "region": "southchina", 
                    "volumeID": "56e01b29-02b9-128-9ca5-1051722006ec", 
                    "storageType": "nfs" 
                } 
            }, 
            "persistentVolumeReclaimPolicy": "Delete" 
        } 
    }
    ```

-   指定OBS对象存储ID创建PersistentVolume

    1.9版本的集群样例：

    ```
    { 
        "apiVersion": "v1", 
        "kind": "PersistentVolume", 
        "metadata": { 
            "labels": { 
                "name": "pv-test" 
            }, 
            "name": "pv-test" 
        }, 
        "spec": { 
            "accessModes": [ 
                "ReadWriteMany" 
            ], 
            "flexVolume": { 
                "driver": "huawei.com/fuxiobs", 
                "fsType": "obs", 
                "options": { 
                    "fsType": "obs", 
                    "kubernetes.io/namespace": "default", 
                    "region": "southchina", 
                    "volumeID": "76e01b29-08b9-11e8-9ca5-1051722006ec", 
                    "storageType": "obs" 
                } 
            }, 
            "persistentVolumeReclaimPolicy": "Delete" 
        } 
    }
    ```

    1.11及以上版本集群样例：

    ```
    { 
        "apiVersion": "v1", 
        "kind": "PersistentVolume", 
        "metadata": { 
            "labels": { 
                "name": "pv-test" 
            }, 
            "name": "pv-test" 
        }, 
        "spec": { 
            "accessModes": [ 
                "ReadWriteMany" 
            ], 
            "flexVolume": { 
                "driver": "huawei.com/fuxiobs", 
                "fsType": "obs", 
                "options": { 
                    "fsType": "obs", 
                    "region": "southchina", 
                    "volumeID": "76e01b29-08b9-11e8-9ca5-1051722006ec", 
                    "storageType": "obs" 
                } 
            }, 
            "persistentVolumeReclaimPolicy": "Delete" 
        } 
    }
    ```

-   指定SFS Turbo极速文件存储ID创建PersistentVolume（不支持1.11版本之前的集群）

    ```
    { 
        "apiVersion": "v1", 
        "kind": "PersistentVolume", 
        "metadata": { 
            "labels": { 
                "name": "pv-test" 
            }, 
            "name": "pv-test" 
        }, 
        "spec": { 
            "accessModes": [ 
                "ReadWriteMany" 
            ], 
            "flexVolume": { 
                "driver": "huawei.com/fuxiefs", 
                "fsType": "efs", 
                "options": { 
                    "fsType": "efs", 
                    "region": "southchina", 
                    "volumeID": "76e01b29-08b9-11e8-9ca5-1051722006ec", 
                    "storageType": "efs" 
                } 
            }, 
            "persistentVolumeReclaimPolicy": "Delete" 
        } 
    }
    ```


## 响应消息<a name="section61819725020"></a>

**响应参数：**

响应参数如[表2](#table26761425181512)所示。

**响应示例：**

```
{
    "kind": "PersistentVolume",
    "apiVersion": "v1",
    "metadata": {
        "name": "pv-test",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/persistentvolumes/pv-test",
        "uid": "e174188f-ff21-11e7-855b-fa163eaf5675",
        "resourceVersion": "174229",
        "creationTimestamp": "2018-01-22T03:11:03Z",
        "labels": {
            "name": "pv-test"
        },
        "enable": true
    },
    "spec": {
        "capacity": {
            "storage": "1Gi"
        },
        "accessModes": [
            "ReadWriteMany"
        ],
        "flexVolume": {
            "driver": "huawei.com/fuxivol",
            "fsType": "ext4",
            "options": {
                "fsType": "ext4",
                "kubernetes.io/namespace": "default",
                "volumeID": "0781b22f-4d89-4e9c-b026-80e545cea16c"
            }
        },
        "persistentVolumeReclaimPolicy": "Delete"
    },
    "status": {
        "phase": "Pending"
    }
}
```

## 状态码<a name="s50f1049a6a4d404c895cf636eb8f3bf1"></a>

[表 3 状态码](#zh-cn_topic_0079614900_table46761928)描述API的状态码。

**表 8**  状态码

<a name="zh-cn_topic_0079614900_table46761928"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row33254664"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p55616028205955"><a name="p55616028205955"></a><a name="p55616028205955"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p8604418205955"><a name="p8604418205955"></a><a name="p8604418205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row41084259"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614900_p39490674"><a name="zh-cn_topic_0079614900_p39490674"></a><a name="zh-cn_topic_0079614900_p39490674"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614900_p44628050"><a name="zh-cn_topic_0079614900_p44628050"></a><a name="zh-cn_topic_0079614900_p44628050"></a>创建PersistentVolume作业下发成功。</p>
</td>
</tr>
</tbody>
</table>

