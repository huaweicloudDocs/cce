# 列出指定的Event<a name="cce_02_0184"></a>

## 功能介绍<a name="section6726992"></a>

This API is used to list all Event resource objects under a specified Namespace.

## URI<a name="section60542934"></a>

GET /api/v1/namespaces/\{namespace\}/events

[表1](#d0e45403)描述该API的参数。

**表 1**  参数解释

<a name="d0e45403"></a>
<table><thead align="left"><tr id="row15382595"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="63.26367363263674%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row14802191"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p58126860"><a name="p58126860"></a><a name="p58126860"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p10655209"><a name="p10655209"></a><a name="p10655209"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p57765582"><a name="p57765582"></a><a name="p57765582"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row50128196"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p33852041"><a name="p33852041"></a><a name="p33852041"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p57660778"><a name="p57660778"></a><a name="p57660778"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p40011473"><a name="p40011473"></a><a name="p40011473"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row24558937"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p43116865"><a name="p43116865"></a><a name="p43116865"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p2805153"><a name="p2805153"></a><a name="p2805153"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p31691062"><a name="p31691062"></a><a name="p31691062"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row16784107"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p17335461"><a name="p17335461"></a><a name="p17335461"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p61995128"><a name="p61995128"></a><a name="p61995128"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p55549451"><a name="p55549451"></a><a name="p55549451"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row30183012"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p28904890"><a name="p28904890"></a><a name="p28904890"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p59594790"><a name="p59594790"></a><a name="p59594790"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p62448653"><a name="p62448653"></a><a name="p62448653"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row25166971"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p25258793"><a name="p25258793"></a><a name="p25258793"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p32696327"><a name="p32696327"></a><a name="p32696327"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p31156797"><a name="p31156797"></a><a name="p31156797"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row11975721"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p30509335"><a name="p30509335"></a><a name="p30509335"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p55337074"><a name="p55337074"></a><a name="p55337074"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p53117985"><a name="p53117985"></a><a name="p53117985"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row8299820"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.4.1.1 "><p id="p1196789"><a name="p1196789"></a><a name="p1196789"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p29831046"><a name="p29831046"></a><a name="p29831046"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="63.26367363263674%" headers="mcps1.2.4.1.3 "><p id="p395656"><a name="p395656"></a><a name="p395656"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section8015500"></a>

N/A

## 响应消息<a name="section5030644"></a>

**响应参数：**

响应参数请参见[表2](#zh-cn_topic_0079614930_table5881294)。

**表 2**  响应参数

<a name="zh-cn_topic_0079614930_table5881294"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614930_row24610089"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614930_p47260226"><a name="zh-cn_topic_0079614930_p47260226"></a><a name="zh-cn_topic_0079614930_p47260226"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p7409181214712"><a name="p7409181214712"></a><a name="p7409181214712"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p441081218475"><a name="p441081218475"></a><a name="p441081218475"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614930_row59951591"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614930_p24240706"><a name="zh-cn_topic_0079614930_p24240706"></a><a name="zh-cn_topic_0079614930_p24240706"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614930_p17340145"><a name="zh-cn_topic_0079614930_p17340145"></a><a name="zh-cn_topic_0079614930_p17340145"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614930_p62374493"><a name="zh-cn_topic_0079614930_p62374493"></a><a name="zh-cn_topic_0079614930_p62374493"></a>A string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614930_row24499525"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614930_p38304470"><a name="zh-cn_topic_0079614930_p38304470"></a><a name="zh-cn_topic_0079614930_p38304470"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614930_p15654360"><a name="zh-cn_topic_0079614930_p15654360"></a><a name="zh-cn_topic_0079614930_p15654360"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614930_p60043634"><a name="zh-cn_topic_0079614930_p60043634"></a><a name="zh-cn_topic_0079614930_p60043634"></a>Versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614930_row3521800"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614930_p16830394"><a name="zh-cn_topic_0079614930_p16830394"></a><a name="zh-cn_topic_0079614930_p16830394"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="ae27c756c3e8c4d7b8b72cbd440b20c9e"><a name="ae27c756c3e8c4d7b8b72cbd440b20c9e"></a><a name="ae27c756c3e8c4d7b8b72cbd440b20c9e"></a><a href="公共响应参数.md#zh-cn_topic_0079614930_table66688435">表15</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614930_p30138892"><a name="zh-cn_topic_0079614930_p30138892"></a><a name="zh-cn_topic_0079614930_p30138892"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614930_row2814577"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614930_p26654174"><a name="zh-cn_topic_0079614930_p26654174"></a><a name="zh-cn_topic_0079614930_p26654174"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="a65502d1935b94750b218e45e0b2d6903"><a name="a65502d1935b94750b218e45e0b2d6903"></a><a name="a65502d1935b94750b218e45e0b2d6903"></a><a href="#cce_02_0184__table10772055194814">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614930_p59446649"><a name="zh-cn_topic_0079614930_p59446649"></a><a name="zh-cn_topic_0079614930_p59446649"></a>List of replication controllers.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  items字段数据结构说明

<a name="table10772055194814"></a>
<table><thead align="left"><tr id="row167885524818"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p78916181114"><a name="p78916181114"></a><a name="p78916181114"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p119191613116"><a name="p119191613116"></a><a name="p119191613116"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p16101716191111"><a name="p16101716191111"></a><a name="p16101716191111"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12781955104810"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p107855517487"><a name="p107855517487"></a><a name="p107855517487"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p117825519482"><a name="p117825519482"></a><a name="p117825519482"></a><a href="获取指定的Service.md#zh-cn_topic_0079614941_ref458764998">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p678955174816"><a name="p678955174816"></a><a name="p678955174816"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="row1878135516485"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p378145584816"><a name="p378145584816"></a><a name="p378145584816"></a>involvedObject</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p167815551483"><a name="p167815551483"></a><a name="p167815551483"></a><a href="#cce_02_0184__table7744122481514">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p979125554813"><a name="p979125554813"></a><a name="p979125554813"></a>The object that this event is about.</p>
</td>
</tr>
<tr id="row328714319511"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p128817315511"><a name="p128817315511"></a><a name="p128817315511"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1288931175113"><a name="p1288931175113"></a><a name="p1288931175113"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p1828873115116"><a name="p1828873115116"></a><a name="p1828873115116"></a>Kind is a string value representing the REST resource this object represents.</p>
</td>
</tr>
<tr id="row17791855124811"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p2079255144817"><a name="p2079255144817"></a><a name="p2079255144817"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p137985515486"><a name="p137985515486"></a><a name="p137985515486"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p147985594816"><a name="p147985594816"></a><a name="p147985594816"></a>This should be a short, machine understandable string that gives the reason for the transition into the object's current status.</p>
</td>
</tr>
<tr id="row5791055114811"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p157965516486"><a name="p157965516486"></a><a name="p157965516486"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p37912559485"><a name="p37912559485"></a><a name="p37912559485"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p1179135534811"><a name="p1179135534811"></a><a name="p1179135534811"></a>A human-readable description of the status of this operation.</p>
</td>
</tr>
<tr id="row579115517489"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p27918554489"><a name="p27918554489"></a><a name="p27918554489"></a>source</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1791552481"><a name="p1791552481"></a><a name="p1791552481"></a><a href="#cce_02_0184__table3940111613552">表5</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p127985584815"><a name="p127985584815"></a><a name="p127985584815"></a>The component reporting this event. Should be a short machine understandable string.</p>
</td>
</tr>
<tr id="row1479555114814"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p18797551488"><a name="p18797551488"></a><a name="p18797551488"></a>firstTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p167965534820"><a name="p167965534820"></a><a name="p167965534820"></a>Time</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p679175504811"><a name="p679175504811"></a><a name="p679175504811"></a>The time at which the event was first recorded. (Time of server receipt is in TypeMeta.)</p>
</td>
</tr>
<tr id="row67945524820"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1279175534816"><a name="p1279175534816"></a><a name="p1279175534816"></a>lastTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p379255154812"><a name="p379255154812"></a><a name="p379255154812"></a>Time</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p1579155511488"><a name="p1579155511488"></a><a name="p1579155511488"></a>The time at which the most recent occurrence of this event was recorded.</p>
</td>
</tr>
<tr id="row15276020181210"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p142772020141210"><a name="p142772020141210"></a><a name="p142772020141210"></a>count</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p02771820131211"><a name="p02771820131211"></a><a name="p02771820131211"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p92771920171212"><a name="p92771920171212"></a><a name="p92771920171212"></a>The number of times this event has occurred.</p>
</td>
</tr>
<tr id="row652592081218"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p185251820141214"><a name="p185251820141214"></a><a name="p185251820141214"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1752572018126"><a name="p1752572018126"></a><a name="p1752572018126"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p6525152061213"><a name="p6525152061213"></a><a name="p6525152061213"></a>Type of this event (Normal, Warning), new types could be added in the future.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  involvedObject字段数据结构说明

<a name="table7744122481514"></a>
<table><thead align="left"><tr id="row6750202431514"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p075122413152"><a name="p075122413152"></a><a name="p075122413152"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p1575312411156"><a name="p1575312411156"></a><a name="p1575312411156"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p375692421513"><a name="p375692421513"></a><a name="p375692421513"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row37584242156"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p174516305155"><a name="p174516305155"></a><a name="p174516305155"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1676212417152"><a name="p1676212417152"></a><a name="p1676212417152"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p207643240152"><a name="p207643240152"></a><a name="p207643240152"></a>Kind of the referent.</p>
</td>
</tr>
<tr id="row207651724191514"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p645053071512"><a name="p645053071512"></a><a name="p645053071512"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1776942421514"><a name="p1776942421514"></a><a name="p1776942421514"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p67714247159"><a name="p67714247159"></a><a name="p67714247159"></a>Namespace of the referent.</p>
</td>
</tr>
<tr id="row9773192481516"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1744919309151"><a name="p1744919309151"></a><a name="p1744919309151"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p17776624111518"><a name="p17776624111518"></a><a name="p17776624111518"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p13777122471520"><a name="p13777122471520"></a><a name="p13777122471520"></a>Name of the referent.</p>
</td>
</tr>
<tr id="row5778124111517"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1944812307158"><a name="p1944812307158"></a><a name="p1944812307158"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p17811424121510"><a name="p17811424121510"></a><a name="p17811424121510"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p14783152451513"><a name="p14783152451513"></a><a name="p14783152451513"></a>UID of the referent.</p>
</td>
</tr>
<tr id="row2784172418154"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p154471630161517"><a name="p154471630161517"></a><a name="p154471630161517"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p8787524111511"><a name="p8787524111511"></a><a name="p8787524111511"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p178912242153"><a name="p178912242153"></a><a name="p178912242153"></a>API version of the referent.</p>
</td>
</tr>
<tr id="row11790142421520"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p14446103031511"><a name="p14446103031511"></a><a name="p14446103031511"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1179672471517"><a name="p1179672471517"></a><a name="p1179672471517"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p10797024121518"><a name="p10797024121518"></a><a name="p10797024121518"></a>Specific resourceVersion to which this reference is made.</p>
</td>
</tr>
<tr id="row16799172412153"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p14445153019150"><a name="p14445153019150"></a><a name="p14445153019150"></a>fieldPath</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p118030243153"><a name="p118030243153"></a><a name="p118030243153"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p14805724121510"><a name="p14805724121510"></a><a name="p14805724121510"></a>If referring to a piece of an object instead of an entire object, this string should contain a valid JSON/Go field access statement, such as desiredState.manifest.containers[2]. For example, if the object reference is to a container within a pod, this would take on a value like: "spec.containers{name}" (where "name" refers to the name of the container that triggered the event) or if no container name is specified "spec.containers[2]" (container with index 2 in this pod). This syntax is chosen only to have some well-defined way of referencing a part of an object.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  source字段数据结构说明

<a name="table3940111613552"></a>
<table><thead align="left"><tr id="row194671675514"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p13949916165512"><a name="p13949916165512"></a><a name="p13949916165512"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p19538161559"><a name="p19538161559"></a><a name="p19538161559"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p13955141614557"><a name="p13955141614557"></a><a name="p13955141614557"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16958916105512"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p6331941135515"><a name="p6331941135515"></a><a name="p6331941135515"></a>component</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p332341115515"><a name="p332341115515"></a><a name="p332341115515"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p3320417556"><a name="p3320417556"></a><a name="p3320417556"></a>Component from which the event is generated.</p>
</td>
</tr>
<tr id="row3966101617559"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p03034135518"><a name="p03034135518"></a><a name="p03034135518"></a>host</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p16292411551"><a name="p16292411551"></a><a name="p16292411551"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p1729441175516"><a name="p1729441175516"></a><a name="p1729441175516"></a>Node name on which the event is generated.</p>
</td>
</tr>
</tbody>
</table>

**响应示例**：

```
{
    "kind": "EventList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/namespaces/default/events",
        "resourceVersion": "6218"
    },
    "items": [
        {
            "metadata": {
                "name": "asdf-554b5dfc44-7mm4f.152b13061a06a7c2",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/events/asdf-554b5dfc44-7mm4f.152b13061a06a7c2",
                "uid": "9e033be0-4ea6-11e8-8c02-fa163e69d0fd",
                "resourceVersion": "6218",
                "creationTimestamp": "2018-05-03T07:50:15Z",
                "enable": true
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "default",
                "name": "asdf-554b5dfc44-7mm4f",
                "uid": "9dff08f2-4ea6-11e8-8c02-fa163e69d0fd",
                "apiVersion": "v1",
                "resourceVersion": "1767656"
            },
            "reason": "FailedScheduling",
            "message": "0/1 nodes are available: 1 Insufficient memory.",
            "source": {
                "component": "default-scheduler"
            },
            "firstTimestamp": "2018-05-03T07:50:15Z",
            "lastTimestamp": "2018-05-03T07:50:22Z",
            "count": 5,
            "type": "Warning",
            "eventTime": null,
            "reportingComponent": "",
            "reportingInstance": ""
        }
    ]
}
```

## 状态码<a name="section45275797"></a>

[表6](#d0e45532)描述API的状态码。

**表 6**  状态码

<a name="d0e45532"></a>
<table><thead align="left"><tr id="row18260744"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p2725313"><a name="p2725313"></a><a name="p2725313"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p19423770"><a name="p19423770"></a><a name="p19423770"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row29821499"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p66731213"><a name="p66731213"></a><a name="p66731213"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p36519159"><a name="p36519159"></a><a name="p36519159"></a>This operation succeeds, and a Event resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

