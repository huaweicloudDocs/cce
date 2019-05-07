# 获取AddonInstance列表<a name="cce_02_0326"></a>

## 功能介绍<a name="section108927501774"></a>

获取集群所有已安装插件实例

## URI<a name="section68937501179"></a>

GET /api/v3/addons?cluster\_id=\{cluster\_id\}

**表 1**  路径参数

<a name="table489613501374"></a>
<table><thead align="left"><tr id="row198955507711"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p289718501577"><a name="p289718501577"></a><a name="p289718501577"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1489725017716"><a name="p1489725017716"></a><a name="p1489725017716"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p28971250079"><a name="p28971250079"></a><a name="p28971250079"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p4898185014715"><a name="p4898185014715"></a><a name="p4898185014715"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row108951650475"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1389812506713"><a name="p1389812506713"></a><a name="p1389812506713"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1789915507711"><a name="p1789915507711"></a><a name="p1789915507711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p989975014712"><a name="p989975014712"></a><a name="p989975014712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1090517501279"><a name="p1090517501279"></a><a name="p1090517501279"></a>集群id</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section89068508720"></a>

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row5908145011714"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1191015014713"><a name="p1191015014713"></a><a name="p1191015014713"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p189107501272"><a name="p189107501272"></a><a name="p189107501272"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p491117506717"><a name="p491117506717"></a><a name="p491117506717"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p10912135017710"><a name="p10912135017710"></a><a name="p10912135017710"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row0908105018717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p15913165019712"><a name="p15913165019712"></a><a name="p15913165019712"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1391314504716"><a name="p1391314504716"></a><a name="p1391314504716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1191414506719"><a name="p1191414506719"></a><a name="p1191414506719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p149140501872"><a name="p149140501872"></a><a name="p149140501872"></a>消息体的类型（格式），下方类型可任选其一使用</p>
<p id="p1991518502710"><a name="p1991518502710"></a><a name="p1991518502710"></a>application/json;charset=utf-8</p>
<p id="p1991520501719"><a name="p1991520501719"></a><a name="p1991520501719"></a>application/json</p>
</td>
</tr>
<tr id="row090835018716"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p149163501971"><a name="p149163501971"></a><a name="p149163501971"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p18916050978"><a name="p18916050978"></a><a name="p18916050978"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1091710509716"><a name="p1091710509716"></a><a name="p1091710509716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p199186505712"><a name="p199186505712"></a><a name="p199186505712"></a>在华为云上调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section691935020713"></a>

状态码为 200 时:

**表 3**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row392414502719"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1992816501972"><a name="p1992816501972"></a><a name="p1992816501972"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p09289506713"><a name="p09289506713"></a><a name="p09289506713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p119281250878"><a name="p119281250878"></a><a name="p119281250878"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p092910501876"><a name="p092910501876"></a><a name="p092910501876"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row3924185012719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1692919501377"><a name="p1692919501377"></a><a name="p1692919501377"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1793014504716"><a name="p1793014504716"></a><a name="p1793014504716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p15930750478"><a name="p15930750478"></a><a name="p15930750478"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p109308501873"><a name="p109308501873"></a><a name="p109308501873"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row139243501972"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p993110507710"><a name="p993110507710"></a><a name="p993110507710"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p6931185016711"><a name="p6931185016711"></a><a name="p6931185016711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p2932135011719"><a name="p2932135011719"></a><a name="p2932135011719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p493319504719"><a name="p493319504719"></a><a name="p493319504719"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row139252050570"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p293315501374"><a name="p293315501374"></a><a name="p293315501374"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p199345504710"><a name="p199345504710"></a><a name="p199345504710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1993520504714"><a name="p1993520504714"></a><a name="p1993520504714"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p16935135010714"><a name="p16935135010714"></a><a name="p16935135010714"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row892595010713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p109382509720"><a name="p109382509720"></a><a name="p109382509720"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p4938350474"><a name="p4938350474"></a><a name="p4938350474"></a>Array of <a href="#response_addoninstance">addoninstance</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p119396501373"><a name="p119396501373"></a><a name="p119396501373"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1593918501575"><a name="p1593918501575"></a><a name="p1593918501575"></a>插件实例列表</p>
</td>
</tr>
</tbody>
</table>

**表 4**  addoninstance

<a name="response_addoninstance"></a>
<table><thead align="left"><tr id="row169413501271"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p894314505715"><a name="p894314505715"></a><a name="p894314505715"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1594410501672"><a name="p1594410501672"></a><a name="p1594410501672"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p594411509717"><a name="p594411509717"></a><a name="p594411509717"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p79451050773"><a name="p79451050773"></a><a name="p79451050773"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row79411850572"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p794612501372"><a name="p794612501372"></a><a name="p794612501372"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p139472503714"><a name="p139472503714"></a><a name="p139472503714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1494719505720"><a name="p1494719505720"></a><a name="p1494719505720"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p109481350971"><a name="p109481350971"></a><a name="p109481350971"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row18942125015719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p179489503713"><a name="p179489503713"></a><a name="p179489503713"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1994910501272"><a name="p1994910501272"></a><a name="p1994910501272"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p294911501274"><a name="p294911501274"></a><a name="p294911501274"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p189503505717"><a name="p189503505717"></a><a name="p189503505717"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row139424501712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p195011501173"><a name="p195011501173"></a><a name="p195011501173"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1295111501278"><a name="p1295111501278"></a><a name="p1295111501278"></a><a href="#response_metadata">metadata</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p2953185017711"><a name="p2953185017711"></a><a name="p2953185017711"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p129542504720"><a name="p129542504720"></a><a name="p129542504720"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row14942650077"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p16955145011712"><a name="p16955145011712"></a><a name="p16955145011712"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1495665020710"><a name="p1495665020710"></a><a name="p1495665020710"></a><a href="#response_instanceSpec">instanceSpec</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p995713501971"><a name="p995713501971"></a><a name="p995713501971"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p7958650573"><a name="p7958650573"></a><a name="p7958650573"></a>spec是集合类的元素类型，内容为插件实例具体信息，实例的详细描述主体部分都在spec中给出</p>
</td>
</tr>
<tr id="row894219508714"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p69597507715"><a name="p69597507715"></a><a name="p69597507715"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p29609508716"><a name="p29609508716"></a><a name="p29609508716"></a><a href="#response_status">status</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p496220503717"><a name="p496220503717"></a><a name="p496220503717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1296317501873"><a name="p1296317501873"></a><a name="p1296317501873"></a>插件实例状态</p>
</td>
</tr>
</tbody>
</table>

**表 5**  status

<a name="response_status"></a>
<table><thead align="left"><tr id="row1496719506712"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p69711850179"><a name="p69711850179"></a><a name="p69711850179"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p6972145015718"><a name="p6972145015718"></a><a name="p6972145015718"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p209721506718"><a name="p209721506718"></a><a name="p209721506718"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1397325019718"><a name="p1397325019718"></a><a name="p1397325019718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row496720500713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p99741750479"><a name="p99741750479"></a><a name="p99741750479"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1197505019718"><a name="p1197505019718"></a><a name="p1197505019718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p139761750370"><a name="p139761750370"></a><a name="p139761750370"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p19778501676"><a name="p19778501676"></a><a name="p19778501676"></a>插件实例状态</p>
</td>
</tr>
<tr id="row149679501871"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p15978450279"><a name="p15978450279"></a><a name="p15978450279"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p119785502077"><a name="p119785502077"></a><a name="p119785502077"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1197913501173"><a name="p1197913501173"></a><a name="p1197913501173"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p09794501176"><a name="p09794501176"></a><a name="p09794501176"></a>插件安装失败原因</p>
</td>
</tr>
<tr id="row199684501470"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p99809501072"><a name="p99809501072"></a><a name="p99809501072"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8981250176"><a name="p8981250176"></a><a name="p8981250176"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p10982850171"><a name="p10982850171"></a><a name="p10982850171"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p129831501471"><a name="p129831501471"></a><a name="p129831501471"></a>安装错误详情</p>
</td>
</tr>
<tr id="row99683501876"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p998413501977"><a name="p998413501977"></a><a name="p998413501977"></a>targetVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p12985150273"><a name="p12985150273"></a><a name="p12985150273"></a>Array of array</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p159866502712"><a name="p159866502712"></a><a name="p159866502712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p29877502710"><a name="p29877502710"></a><a name="p29877502710"></a>此插件版本，支持升级的集群版本</p>
</td>
</tr>
<tr id="row896835010719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p498785016717"><a name="p498785016717"></a><a name="p498785016717"></a>currentVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p189886501570"><a name="p189886501570"></a><a name="p189886501570"></a><a href="#response_versions">versions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14989175017714"><a name="p14989175017714"></a><a name="p14989175017714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p4990135016715"><a name="p4990135016715"></a><a name="p4990135016715"></a>当前插件实例使用的具体插件版本信息</p>
</td>
</tr>
</tbody>
</table>

**表 6**  versions

<a name="response_versions"></a>
<table><thead align="left"><tr id="row199931450577"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p109972501473"><a name="p109972501473"></a><a name="p109972501473"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p159985509718"><a name="p159985509718"></a><a name="p159985509718"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p209995502075"><a name="p209995502075"></a><a name="p209995502075"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p101195114718"><a name="p101195114718"></a><a name="p101195114718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1899317501677"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p0285116716"><a name="p0285116716"></a><a name="p0285116716"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p131511270"><a name="p131511270"></a><a name="p131511270"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p9420511376"><a name="p9420511376"></a><a name="p9420511376"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p85125116717"><a name="p85125116717"></a><a name="p85125116717"></a>插件版本号</p>
</td>
</tr>
<tr id="row13993450777"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p19615514719"><a name="p19615514719"></a><a name="p19615514719"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1677512070"><a name="p1677512070"></a><a name="p1677512070"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p13820511479"><a name="p13820511479"></a><a name="p13820511479"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p39115120710"><a name="p39115120710"></a><a name="p39115120710"></a>插件安装参数</p>
</td>
</tr>
<tr id="row129932050276"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p71012512711"><a name="p71012512711"></a><a name="p71012512711"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1611451177"><a name="p1611451177"></a><a name="p1611451177"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p12126515716"><a name="p12126515716"></a><a name="p12126515716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p71310511711"><a name="p71310511711"></a><a name="p71310511711"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row15994250971"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p17143511479"><a name="p17143511479"></a><a name="p17143511479"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p131585111714"><a name="p131585111714"></a><a name="p131585111714"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p191625118714"><a name="p191625118714"></a><a name="p191625118714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p14173511779"><a name="p14173511779"></a><a name="p14173511779"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row4994135020715"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p41819511710"><a name="p41819511710"></a><a name="p41819511710"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p41835112715"><a name="p41835112715"></a><a name="p41835112715"></a>Array of <a href="#response_supportVersions">supportVersions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p18191851673"><a name="p18191851673"></a><a name="p18191851673"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p62019518712"><a name="p62019518712"></a><a name="p62019518712"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row99941250170"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p921651074"><a name="p921651074"></a><a name="p921651074"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p822115112715"><a name="p822115112715"></a><a name="p822115112715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p22217514720"><a name="p22217514720"></a><a name="p22217514720"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p172316512713"><a name="p172316512713"></a><a name="p172316512713"></a>创建时间</p>
</td>
</tr>
<tr id="row189953501573"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18242511270"><a name="p18242511270"></a><a name="p18242511270"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p62415110712"><a name="p62415110712"></a><a name="p62415110712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p202525112718"><a name="p202525112718"></a><a name="p202525112718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1926185116711"><a name="p1926185116711"></a><a name="p1926185116711"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 7**  supportVersions

<a name="response_supportVersions"></a>
<table><thead align="left"><tr id="row3278514710"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p3312511379"><a name="p3312511379"></a><a name="p3312511379"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p53235111720"><a name="p53235111720"></a><a name="p53235111720"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p333155120718"><a name="p333155120718"></a><a name="p333155120718"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p0331511274"><a name="p0331511274"></a><a name="p0331511274"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row7281651376"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p13416518713"><a name="p13416518713"></a><a name="p13416518713"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p193412511720"><a name="p193412511720"></a><a name="p193412511720"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p193511511972"><a name="p193511511972"></a><a name="p193511511972"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p15368511674"><a name="p15368511674"></a><a name="p15368511674"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row9285519712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p103612510712"><a name="p103612510712"></a><a name="p103612510712"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p83745111715"><a name="p83745111715"></a><a name="p83745111715"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p0384511672"><a name="p0384511672"></a><a name="p0384511672"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p11391151577"><a name="p11391151577"></a><a name="p11391151577"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 8**  instanceSpec

<a name="response_instanceSpec"></a>
<table><thead align="left"><tr id="row74125116711"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p54617513717"><a name="p54617513717"></a><a name="p54617513717"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p647185120710"><a name="p647185120710"></a><a name="p647185120710"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p124875118714"><a name="p124875118714"></a><a name="p124875118714"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p34955113718"><a name="p34955113718"></a><a name="p34955113718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row13422511472"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p7501511779"><a name="p7501511779"></a><a name="p7501511779"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p55015118712"><a name="p55015118712"></a><a name="p55015118712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p165116514720"><a name="p165116514720"></a><a name="p165116514720"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p15516511713"><a name="p15516511713"></a><a name="p15516511713"></a>集群id</p>
</td>
</tr>
<tr id="row10423511072"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p11520515717"><a name="p11520515717"></a><a name="p11520515717"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p253135115717"><a name="p253135115717"></a><a name="p253135115717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14531051776"><a name="p14531051776"></a><a name="p14531051776"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p125435114714"><a name="p125435114714"></a><a name="p125435114714"></a>插件模板版本号，如1.0.0</p>
</td>
</tr>
<tr id="row742251170"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p35575112718"><a name="p35575112718"></a><a name="p35575112718"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1056125118713"><a name="p1056125118713"></a><a name="p1056125118713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p65711511715"><a name="p65711511715"></a><a name="p65711511715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p125710514710"><a name="p125710514710"></a><a name="p125710514710"></a>插件模板名称，如coredns</p>
</td>
</tr>
<tr id="row1042185111710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p558155112717"><a name="p558155112717"></a><a name="p558155112717"></a>addonTemplateType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p4591751379"><a name="p4591751379"></a><a name="p4591751379"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p360155116712"><a name="p360155116712"></a><a name="p360155116712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p660951672"><a name="p660951672"></a><a name="p660951672"></a>插件模板类型</p>
</td>
</tr>
<tr id="row2043195114710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p86117511174"><a name="p86117511174"></a><a name="p86117511174"></a>addonTemplateLabels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p962651371"><a name="p962651371"></a><a name="p962651371"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p186225112717"><a name="p186225112717"></a><a name="p186225112717"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p663451374"><a name="p663451374"></a><a name="p663451374"></a>插件模板所属类型</p>
</td>
</tr>
<tr id="row4431051477"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p96435116719"><a name="p96435116719"></a><a name="p96435116719"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p765551677"><a name="p765551677"></a><a name="p765551677"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p12651651173"><a name="p12651651173"></a><a name="p12651651173"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p206695110714"><a name="p206695110714"></a><a name="p206695110714"></a>插件模板描述</p>
</td>
</tr>
<tr id="row5449511979"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p11663518714"><a name="p11663518714"></a><a name="p11663518714"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p166714514718"><a name="p166714514718"></a><a name="p166714514718"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p66718512713"><a name="p66718512713"></a><a name="p66718512713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p18685511374"><a name="p18685511374"></a><a name="p18685511374"></a>插件模板安装参数（各插件不同）</p>
</td>
</tr>
</tbody>
</table>

**表 9**  metadata

<a name="response_metadata"></a>
<table><thead align="left"><tr id="row107017516717"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1751851877"><a name="p1751851877"></a><a name="p1751851877"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p975165119719"><a name="p975165119719"></a><a name="p975165119719"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p147775111712"><a name="p147775111712"></a><a name="p147775111712"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1178105116711"><a name="p1178105116711"></a><a name="p1178105116711"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row107135111717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18794519717"><a name="p18794519717"></a><a name="p18794519717"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p128011518712"><a name="p128011518712"></a><a name="p128011518712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p128110511676"><a name="p128110511676"></a><a name="p128110511676"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p2081165117710"><a name="p2081165117710"></a><a name="p2081165117710"></a>唯一id标识</p>
</td>
</tr>
<tr id="row20712511171"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1668510511377"><a name="p1668510511377"></a><a name="p1668510511377"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p86856511373"><a name="p86856511373"></a><a name="p86856511373"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p206850511873"><a name="p206850511873"></a><a name="p206850511873"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1568545119720"><a name="p1568545119720"></a><a name="p1568545119720"></a>插件名称</p>
</td>
</tr>
<tr id="row127119514717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p668519519713"><a name="p668519519713"></a><a name="p668519519713"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p96859511070"><a name="p96859511070"></a><a name="p96859511070"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p2068515511779"><a name="p2068515511779"></a><a name="p2068515511779"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p268617512718"><a name="p268617512718"></a><a name="p268617512718"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row8727511675"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p106861651975"><a name="p106861651975"></a><a name="p106861651975"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p176861151678"><a name="p176861151678"></a><a name="p176861151678"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p068611519717"><a name="p068611519717"></a><a name="p068611519717"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1168665111711"><a name="p1168665111711"></a><a name="p1168665111711"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row1972135120712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p4686551974"><a name="p4686551974"></a><a name="p4686551974"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p66869516716"><a name="p66869516716"></a><a name="p66869516716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p8686951370"><a name="p8686951370"></a><a name="p8686951370"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1568635112719"><a name="p1568635112719"></a><a name="p1568635112719"></a>更新时间</p>
</td>
</tr>
<tr id="row10728511678"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p368711518711"><a name="p368711518711"></a><a name="p368711518711"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p768715116714"><a name="p768715116714"></a><a name="p768715116714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1468775110713"><a name="p1468775110713"></a><a name="p1468775110713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p15687135118719"><a name="p15687135118719"></a><a name="p15687135118719"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section1568717511777"></a>

无

## 响应示例<a name="section1668711512079"></a>

状态码为 200 时:

```
{
	"apiVersion":"v3",
	"kind":"Addon",
	"items":[
		{
			"metadata":{
				"uid":"8ca259cc-553b-11e9-926f-0255ac101a31",
				"name":"storage-driver",
				"creationTimestamp":"2019-04-02T11:36:26Z",
				"updateTimestamp":"2019-04-02T11:36:26Z"
			},
			"apiVersion":"v3",
			"kind":"Addon",
			"spec":{
				"addonTemplateName":"storage-driver",
				"addonTemplateLogo":"https://192.149.48.66/cce-addon-southchina-aw1hz2u/storage-driverlogo.svg",
				"addonTemplateType":"helm",
				"values":{
					"flavor":{
						"replicas":1
					},
					"basic":{
						"obs_url":"obs.cn-north-1.myhuaweicloud.com",
						"swr_user":"hwofficial",
						"euleros_version":"2.2.5",
						"addon_version":"1.0.10",
						"platform":"linux-amd64",
						"swr_addr":"100.125.6.246:20202"
					},
					"parameters":{
						
					}
				},
				"description":"A kubernetes FlexVolume Driver used to support cloud storage",
				"addonTemplateLabels":[
					"Storage"
				],
				"clusterID":"0c0e4a63-5539-11e9-95f7-0255ac10177e",
				"version":"1.0.10"
			},
			"status":{
				"message":"",
				"Reason":"Install complete",
				"currentVersion":{
					"input":{
						"basic":{
							"obs_url":"obs.cn-north-1.myhuaweicloud.com",
							"swr_user":"hwofficial",
							"euleros_version":"2.2.5",
							"swr_addr":"100.125.6.246:20202"
						},
						"parameters":{
							
						}
					},
					"stable":true,
					"creationTimestamp":"2019-03-29T13:45:37Z",
					"version":"1.0.10",
					"translate":{
						"en_US":{
							"addon":{
								"changeLog":"The plug-in is upgraded to enhance the storage plug-in function.",
								"description":"A kubernetes FlexVolume Driver used to support cloud storage"
							}
						},
						"zh_CN":{
							"addon":{
								"changeLog":"升级插件，增强存储插件功能.",
								"description":"用于对接云存储服务的FlexVolume驱动"
							}
						}
					},
					"updateTimestamp":"2019-03-29T13:45:37Z"
				},
				"status":"running"
			}
		}
	]
}
```

状态码为 500 时:

```
{
	"code":"SVCSTG.CCE-ADDONMGR.500",
	"message":"internal error"
}
```

## 返回值<a name="section3694185113715"></a>

<a name="table33"></a>
<table><thead align="left"><tr id="row21356512713"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p176957511574"><a name="p176957511574"></a><a name="p176957511574"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p86951651477"><a name="p86951651477"></a><a name="p86951651477"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row5135851376"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p1569511511374"><a name="p1569511511374"></a><a name="p1569511511374"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row713545115715"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p1669525112716"><a name="p1669525112716"></a><a name="p1669525112716"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p769555118719"><a name="p769555118719"></a><a name="p769555118719"></a>Internal Server Error</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section7695105115718"></a>

<a name="table34"></a>
<table><thead align="left"><tr id="row214217511674"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.5.1.1"><p id="p106951251279"><a name="p106951251279"></a><a name="p106951251279"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.2"><p id="p5696145110710"><a name="p5696145110710"></a><a name="p5696145110710"></a>错误码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.3"><p id="p8696851572"><a name="p8696851572"></a><a name="p8696851572"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="35%" id="mcps1.1.5.1.4"><p id="p16963510713"><a name="p16963510713"></a><a name="p16963510713"></a>解决方案</p>
</th>
</tr>
</thead>
<tbody><tr id="row1514218511379"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p1669616519716"><a name="p1669616519716"></a><a name="p1669616519716"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p196960516711"><a name="p196960516711"></a><a name="p196960516711"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p156961851379"><a name="p156961851379"></a><a name="p156961851379"></a>bad request</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row13143851173"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p469611511276"><a name="p469611511276"></a><a name="p469611511276"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p46965515716"><a name="p46965515716"></a><a name="p46965515716"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p136963518711"><a name="p136963518711"></a><a name="p136963518711"></a>Authenticate error</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row2014410512075"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p36966511719"><a name="p36966511719"></a><a name="p36966511719"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p96971451570"><a name="p96971451570"></a><a name="p96971451570"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p11697551577"><a name="p11697551577"></a><a name="p11697551577"></a>Authorize failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row0144165119713"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p1069712513720"><a name="p1069712513720"></a><a name="p1069712513720"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1469716510715"><a name="p1469716510715"></a><a name="p1469716510715"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p17697851370"><a name="p17697851370"></a><a name="p17697851370"></a>server internal error</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
</tbody>
</table>

