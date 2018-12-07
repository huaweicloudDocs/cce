# 创建PersistentVolumeClaim<a name="cce_02_0252"></a>

## 功能描述<a name="section155195145312"></a>

该API用于在指定的Namespace下通过华为云存储服务中的云存储（EVS、SFS、OBS）去创建PersistentVolumeClaim。

## URI<a name="section1975393831219"></a>

POST /api/v1/namespaces/\{namespace\}/cloudpersistentvolumeclaims

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
<tbody><tr id="row32801312121810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1714415589184"><a name="p1714415589184"></a><a name="p1714415589184"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.4.1.2 "><p id="p814518580186"><a name="p814518580186"></a><a name="p814518580186"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="68%" headers="mcps1.2.4.1.3 "><p id="p5145175891811"><a name="p5145175891811"></a><a name="p5145175891811"></a>指定PersistentVolumeClaim所在的命名空间。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section1142842461418"></a>

**请求参数：**

请求参数如[表2](#table165001054142614)、[表3](#table26761425181512)所示。

**表 2**  请求Header参数说明

<a name="table165001054142614"></a>
<table><thead align="left"><tr id="row55001954122614"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p115009545264"><a name="p115009545264"></a><a name="p115009545264"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.4.1.2"><p id="p175001547265"><a name="p175001547265"></a><a name="p175001547265"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61%" id="mcps1.2.4.1.3"><p id="p16500154162611"><a name="p16500154162611"></a><a name="p16500154162611"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row199801811203412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p69808112344"><a name="p69808112344"></a><a name="p69808112344"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="p3980111103414"><a name="p3980111103414"></a><a name="p3980111103414"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p169801011203416"><a name="p169801011203416"></a><a name="p169801011203416"></a>消息体的类型（格式），使用application/json;charset=utf-8或者application/json。</p>
</td>
</tr>
<tr id="row3500125412260"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p105001654202618"><a name="p105001654202618"></a><a name="p105001654202618"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="p20500954182618"><a name="p20500954182618"></a><a name="p20500954182618"></a>使用token认证时必选</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p1250055462618"><a name="p1250055462618"></a><a name="p1250055462618"></a>用户token。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  请求Body参数说明

<a name="table26761425181512"></a>
<table><thead align="left"><tr id="row107441225201515"><th class="cellrowborder" valign="top" width="19.801980198019802%" id="mcps1.2.5.1.1"><p id="p57445253154"><a name="p57445253154"></a><a name="p57445253154"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.81188118811881%" id="mcps1.2.5.1.2"><p id="p11744152514157"><a name="p11744152514157"></a><a name="p11744152514157"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.81188118811881%" id="mcps1.2.5.1.3"><p id="p14744172517156"><a name="p14744172517156"></a><a name="p14744172517156"></a>类型</p>
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
<td class="cellrowborder" valign="top" width="42.57425742574257%" headers="mcps1.2.5.1.4 "><p id="p874542515151"><a name="p874542515151"></a><a name="p874542515151"></a>API类型，固定值＂PersistentVolumeClaim＂</p>
</td>
</tr>
<tr id="row16745125101516"><td class="cellrowborder" valign="top" width="19.801980198019802%" headers="mcps1.2.5.1.1 "><p id="p177451725101517"><a name="p177451725101517"></a><a name="p177451725101517"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.2 "><p id="p1062853354013"><a name="p1062853354013"></a><a name="p1062853354013"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p074532551518"><a name="p074532551518"></a><a name="p074532551518"></a><a href="#cce_02_0252__table6304105819164">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="42.57425742574257%" headers="mcps1.2.5.1.4 "><p id="p2745152519150"><a name="p2745152519150"></a><a name="p2745152519150"></a>-</p>
</td>
</tr>
<tr id="row2745725201512"><td class="cellrowborder" valign="top" width="19.801980198019802%" headers="mcps1.2.5.1.1 "><p id="p8745025151519"><a name="p8745025151519"></a><a name="p8745025151519"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.2 "><p id="p8581153624016"><a name="p8581153624016"></a><a name="p8581153624016"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p1574522520158"><a name="p1574522520158"></a><a name="p1574522520158"></a><a href="#cce_02_0252__table3862152512246">表5</a></p>
</td>
<td class="cellrowborder" valign="top" width="42.57425742574257%" headers="mcps1.2.5.1.4 "><p id="p97458257151"><a name="p97458257151"></a><a name="p97458257151"></a>-</p>
</td>
</tr>
<tr id="row67451925181517"><td class="cellrowborder" valign="top" width="19.801980198019802%" headers="mcps1.2.5.1.1 "><p id="p107451025111518"><a name="p107451025111518"></a><a name="p107451025111518"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.2 "><p id="p1574516258158"><a name="p1574516258158"></a><a name="p1574516258158"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p874562561514"><a name="p874562561514"></a><a name="p874562561514"></a><a href="#cce_02_0252__table478913499397">表6</a></p>
</td>
<td class="cellrowborder" valign="top" width="42.57425742574257%" headers="mcps1.2.5.1.4 "><p id="p8745172518154"><a name="p8745172518154"></a><a name="p8745172518154"></a>-</p>
</td>
</tr>
</tbody>
</table>

**表 4**  metadata字段数据结构说明

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
<td class="cellrowborder" valign="top" width="45.54455445544555%" headers="mcps1.2.5.1.4 "><p id="p17193543245"><a name="p17193543245"></a><a name="p17193543245"></a>PersistentVolumeClaim名称</p>
</td>
</tr>
<tr id="row5304758171616"><td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.1 "><p id="p519318462411"><a name="p519318462411"></a><a name="p519318462411"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="16.831683168316832%" headers="mcps1.2.5.1.2 "><p id="p619364182418"><a name="p619364182418"></a><a name="p619364182418"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.81188118811881%" headers="mcps1.2.5.1.3 "><p id="p1519316412248"><a name="p1519316412248"></a><a name="p1519316412248"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.54455445544555%" headers="mcps1.2.5.1.4 "><p id="p319310432413"><a name="p319310432413"></a><a name="p319310432413"></a>PersistentVolumeClaim标签，key/value对格式</p>
</td>
</tr>
</tbody>
</table>

**表 5**  spec字段数据结构说明

<a name="table3862152512246"></a>
<table><thead align="left"><tr id="row292213259241"><th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.5.1.1"><p id="p892212511240"><a name="p892212511240"></a><a name="p892212511240"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.18181818181818%" id="mcps1.2.5.1.2"><p id="p199221125112412"><a name="p199221125112412"></a><a name="p199221125112412"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.19191919191919%" id="mcps1.2.5.1.3"><p id="p1592252520243"><a name="p1592252520243"></a><a name="p1592252520243"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.42424242424242%" id="mcps1.2.5.1.4"><p id="p19225259247"><a name="p19225259247"></a><a name="p19225259247"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18922102592411"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="p592210259244"><a name="p592210259244"></a><a name="p592210259244"></a>volumeName</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="p89221925162414"><a name="p89221925162414"></a><a name="p89221925162414"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.5.1.3 "><p id="p592210258242"><a name="p592210258242"></a><a name="p592210258242"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="p792512117573"><a name="p792512117573"></a><a name="p792512117573"></a>绑定引用的PersistentVolume名称</p>
<div class="note" id="note1628142395713"><a name="note1628142395713"></a><a name="note1628142395713"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p72820236574"><a name="p72820236574"></a><a name="p72820236574"></a>若“volumeID”被指定，则该字段指定的值无效。</p>
</div></div>
</td>
</tr>
<tr id="row8922225162418"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="p29226252245"><a name="p29226252245"></a><a name="p29226252245"></a>volumeID</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="p1792232552417"><a name="p1792232552417"></a><a name="p1792232552417"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.5.1.3 "><p id="p10922525152419"><a name="p10922525152419"></a><a name="p10922525152419"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="p6922192513245"><a name="p6922192513245"></a><a name="p6922192513245"></a>云存储卷ID</p>
</td>
</tr>
<tr id="row13922112515249"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="p99221625132417"><a name="p99221625132417"></a><a name="p99221625132417"></a>storageType</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="p892213250245"><a name="p892213250245"></a><a name="p892213250245"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.5.1.3 "><p id="p5922162512248"><a name="p5922162512248"></a><a name="p5922162512248"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="p1661119562"><a name="p1661119562"></a><a name="p1661119562"></a>云存储的类型，和volumeID搭配使用。即volumeID和storageType必须同时被配置。</p>
<a name="ul1051832855611"></a><a name="ul1051832855611"></a><ul id="ul1051832855611"><li>bs：EVS云存储</li><li>nfs：SFS弹性文件存储</li><li>obs：OBS对象存储</li><li>efs：SFS Turbo极速文件存储</li></ul>
</td>
</tr>
<tr id="row12922192592410"><td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.1 "><p id="p11922172552413"><a name="p11922172552413"></a><a name="p11922172552413"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="p19635185624011"><a name="p19635185624011"></a><a name="p19635185624011"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.5.1.3 "><p id="p892302519247"><a name="p892302519247"></a><a name="p892302519247"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.2.5.1.4 "><p id="p9923162562416"><a name="p9923162562416"></a><a name="p9923162562416"></a>指定volume应该具有的访问模式</p>
</td>
</tr>
</tbody>
</table>

**表 6**  status字段数据结构说明

<a name="table478913499397"></a>
<table><thead align="left"><tr id="row149491749113917"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.1"><p id="p8949174923910"><a name="p8949174923910"></a><a name="p8949174923910"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.5.1.2"><p id="p14949149203910"><a name="p14949149203910"></a><a name="p14949149203910"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.3"><p id="p18949124916399"><a name="p18949124916399"></a><a name="p18949124916399"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.85571442855714%" id="mcps1.2.5.1.4"><p id="p14949124923919"><a name="p14949124923919"></a><a name="p14949124923919"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row39499497398"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p494914983911"><a name="p494914983911"></a><a name="p494914983911"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p19494490396"><a name="p19494490396"></a><a name="p19494490396"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p494924973913"><a name="p494924973913"></a><a name="p494924973913"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p894919493396"><a name="p894919493396"></a><a name="p894919493396"></a>显示volume实际具有的访问模式</p>
</td>
</tr>
<tr id="row6949114953916"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p895020494399"><a name="p895020494399"></a><a name="p895020494399"></a>capacity</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p795011491393"><a name="p795011491393"></a><a name="p795011491393"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p16950549103917"><a name="p16950549103917"></a><a name="p16950549103917"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p1195074903918"><a name="p1195074903918"></a><a name="p1195074903918"></a>底层卷的实际资源</p>
</td>
</tr>
<tr id="row10950144913397"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p15950144923914"><a name="p15950144923914"></a><a name="p15950144923914"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.5.1.2 "><p id="p13950949133913"><a name="p13950949133913"></a><a name="p13950949133913"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p1895044933913"><a name="p1895044933913"></a><a name="p1895044933913"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p159501649173914"><a name="p159501649173914"></a><a name="p159501649173914"></a>PersistentVolumeClaim当前所处的状态</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

-   指定EVS云硬盘ID创建PersistentVolumeClaim

    ```
    {
        "apiVersion": "v1",
        "kind": "PersistentVolumeClaim",
        "metadata": {
            "name": "csms-dev-create",
            "namespace": "default"
        },
        "spec": {
            "volumeID": "86b29e16-23db-11e7-9c83-fa163ec08232",
            "storageType": "bs",
            "accessModes": [
                "ReadWriteMany"
            ]
        }
    }
    ```

-   指定SFS文件存储ID创建PersistentVolumeClaim

    ```
    {
        "apiVersion": "v1",
        "kind": "PersistentVolumeClaim",
        "metadata": {
            "name": "csms-dev-create",
            "namespace": "default"
        },
        "spec": {
            "volumeID": "86b29e16-23db-11e7-9c83-fa163ec08232",
            "storageType": "nfs",
            "accessModes": [
                "ReadWriteMany"
            ]
        }
    }
    ```

-   指定OBS对象存储ID创建PersistentVolumeClaim

    ```
    { 
        "apiVersion": "v1", 
        "kind": "PersistentVolumeClaim", 
        "metadata": { 
            "name": "csms-dev-create", 
            "namespace": "default" 
        }, 
        "spec": {
            "volumeID": "obs-storage-id",
            "storageType": "obs",
            "accessModes": [ 
                "ReadWriteMany" 
            ]
    }
    ```


-   指定SFS Turbo极速文件存储ID创建PersistentVolumeClaim

    ```
    {  
        "apiVersion": "v1",  
        "kind": "PersistentVolumeClaim",  
        "metadata": {  
            "name": "csms-dev-create",  
            "namespace": "default"  
        },  
        "spec": { 
            "volumeID": "86b29e16-23db-11e7-9c83-fa163ec08232", 
            "storageType": "efs", 
            "accessModes": [  
                "ReadWriteMany"  
            ] 
    }
    ```


## 响应消息<a name="section61819725020"></a>

**响应参数：**

响应参数如[表3](#table26761425181512)所示。

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
<tbody><tr id="zh-cn_topic_0079614900_row41084259"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614900_p39490674"><a name="zh-cn_topic_0079614900_p39490674"></a><a name="zh-cn_topic_0079614900_p39490674"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614900_p44628050"><a name="zh-cn_topic_0079614900_p44628050"></a><a name="zh-cn_topic_0079614900_p44628050"></a>创建PersistentVolumeClaim作业下发成功。</p>
</td>
</tr>
</tbody>
</table>

