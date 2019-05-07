# 更新AddonInstance<a name="cce_02_0323"></a>

## 功能介绍<a name="section1221654910714"></a>

更新插件实例的功能

## URI<a name="section1021716494713"></a>

PUT /api/v3/addons/\{id\}

**表 1**  路径参数

<a name="table422018491378"></a>
<table><thead align="left"><tr id="row1121918490718"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p722054916719"><a name="p722054916719"></a><a name="p722054916719"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p42217491771"><a name="p42217491771"></a><a name="p42217491771"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p11222204915716"><a name="p11222204915716"></a><a name="p11222204915716"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1022214495718"><a name="p1022214495718"></a><a name="p1022214495718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row62196499718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p122233491170"><a name="p122233491170"></a><a name="p122233491170"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p192241049376"><a name="p192241049376"></a><a name="p192241049376"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1224124912712"><a name="p1224124912712"></a><a name="p1224124912712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p12225134914717"><a name="p12225134914717"></a><a name="p12225134914717"></a>插件实例id</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section1022684910719"></a>

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row12228449678"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p423018491370"><a name="p423018491370"></a><a name="p423018491370"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p0231184915710"><a name="p0231184915710"></a><a name="p0231184915710"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p1323184912716"><a name="p1323184912716"></a><a name="p1323184912716"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p42327491079"><a name="p42327491079"></a><a name="p42327491079"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row6228124918717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p0232449176"><a name="p0232449176"></a><a name="p0232449176"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1623316493715"><a name="p1623316493715"></a><a name="p1623316493715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p182332491471"><a name="p182332491471"></a><a name="p182332491471"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p162341349670"><a name="p162341349670"></a><a name="p162341349670"></a>消息体的类型（格式），下方类型可任选其一使用：</p>
<p id="p423424917710"><a name="p423424917710"></a><a name="p423424917710"></a>application/json;charset=utf-8</p>
<p id="p22353491076"><a name="p22353491076"></a><a name="p22353491076"></a>application/json</p>
</td>
</tr>
<tr id="row122813491477"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1423584915713"><a name="p1423584915713"></a><a name="p1423584915713"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p11236349477"><a name="p11236349477"></a><a name="p11236349477"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p92368491674"><a name="p92368491674"></a><a name="p92368491674"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p123774914719"><a name="p123774914719"></a><a name="p123774914719"></a>在华为云上调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填</p>
</td>
</tr>
</tbody>
</table>

**表 3**  请求Body参数

<a name="requestParameter"></a>
<table><thead align="left"><tr id="row52384491472"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p124220492716"><a name="p124220492716"></a><a name="p124220492716"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p2243134917713"><a name="p2243134917713"></a><a name="p2243134917713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p1024411494715"><a name="p1024411494715"></a><a name="p1024411494715"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p19244204918712"><a name="p19244204918712"></a><a name="p19244204918712"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row12395498718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p15245849373"><a name="p15245849373"></a><a name="p15245849373"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p16245349274"><a name="p16245349274"></a><a name="p16245349274"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p924613491776"><a name="p924613491776"></a><a name="p924613491776"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p924716493719"><a name="p924716493719"></a><a name="p924716493719"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row132391649371"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2024710496712"><a name="p2024710496712"></a><a name="p2024710496712"></a>apVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p112488491671"><a name="p112488491671"></a><a name="p112488491671"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p112491949478"><a name="p112491949478"></a><a name="p112491949478"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p202501249170"><a name="p202501249170"></a><a name="p202501249170"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row324014920719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p225017494714"><a name="p225017494714"></a><a name="p225017494714"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p82517499715"><a name="p82517499715"></a><a name="p82517499715"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p4251249673"><a name="p4251249673"></a><a name="p4251249673"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1525284910711"><a name="p1525284910711"></a><a name="p1525284910711"></a>安装：固定值为{"addon.install/type":"install"}</p>
<p id="p11252184914711"><a name="p11252184914711"></a><a name="p11252184914711"></a>升级：固定值为{"addon.upgrade/type":"upgrade"}</p>
</td>
</tr>
<tr id="row162406492710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p3252134910711"><a name="p3252134910711"></a><a name="p3252134910711"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p725313491379"><a name="p725313491379"></a><a name="p725313491379"></a><a href="#instancerequestspec">instancerequestspec</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1925320491179"><a name="p1925320491179"></a><a name="p1925320491179"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p102545491174"><a name="p102545491174"></a><a name="p102545491174"></a>spec是集合类的元素类型，内容为插件实例安装/升级的具体请求信息</p>
</td>
</tr>
</tbody>
</table>

**表 4**  instancerequestspec

<a name="instancerequestspec"></a>
<table><thead align="left"><tr id="row112566495713"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p02608493719"><a name="p02608493719"></a><a name="p02608493719"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1260249476"><a name="p1260249476"></a><a name="p1260249476"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p122618491178"><a name="p122618491178"></a><a name="p122618491178"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1026110498719"><a name="p1026110498719"></a><a name="p1026110498719"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row52573499710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1426254917713"><a name="p1426254917713"></a><a name="p1426254917713"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p112637490713"><a name="p112637490713"></a><a name="p112637490713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p026424915710"><a name="p026424915710"></a><a name="p026424915710"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1626524918718"><a name="p1626524918718"></a><a name="p1626524918718"></a>待安装、升级插件的具体版本版本号，例如1.0.0</p>
</td>
</tr>
<tr id="row82574492720"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p14265124915713"><a name="p14265124915713"></a><a name="p14265124915713"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p826624919714"><a name="p826624919714"></a><a name="p826624919714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14266249475"><a name="p14266249475"></a><a name="p14266249475"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p52679497719"><a name="p52679497719"></a><a name="p52679497719"></a>集群id</p>
</td>
</tr>
<tr id="row172574495718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p16268449574"><a name="p16268449574"></a><a name="p16268449574"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p17269164912715"><a name="p17269164912715"></a><a name="p17269164912715"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p192692490715"><a name="p192692490715"></a><a name="p192692490715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p3270049177"><a name="p3270049177"></a><a name="p3270049177"></a>待安装或升级模板的具体请求参数，一般为配置文件，各插件不同</p>
</td>
</tr>
<tr id="row92581849472"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p527104910720"><a name="p527104910720"></a><a name="p527104910720"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8272104912717"><a name="p8272104912717"></a><a name="p8272104912717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p527218491472"><a name="p527218491472"></a><a name="p527218491472"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p13273164916714"><a name="p13273164916714"></a><a name="p13273164916714"></a>待安装插件模板名称，如coredns</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section12739492071"></a>

状态码为 200 时:

**表 5**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row5275249277"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p42792491076"><a name="p42792491076"></a><a name="p42792491076"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p428084911714"><a name="p428084911714"></a><a name="p428084911714"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p1628014912712"><a name="p1628014912712"></a><a name="p1628014912712"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p52814495718"><a name="p52814495718"></a><a name="p52814495718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row182761449276"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p228118491376"><a name="p228118491376"></a><a name="p228118491376"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p142823496712"><a name="p142823496712"></a><a name="p142823496712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1028319494713"><a name="p1028319494713"></a><a name="p1028319494713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p428312491676"><a name="p428312491676"></a><a name="p428312491676"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row19276749873"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p122845491712"><a name="p122845491712"></a><a name="p122845491712"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p202862491478"><a name="p202862491478"></a><a name="p202862491478"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p82871749477"><a name="p82871749477"></a><a name="p82871749477"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p152886497713"><a name="p152886497713"></a><a name="p152886497713"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row18276149577"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18288144910711"><a name="p18288144910711"></a><a name="p18288144910711"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p20289104912718"><a name="p20289104912718"></a><a name="p20289104912718"></a><a href="#response_metadata">metadata</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p17289154913718"><a name="p17289154913718"></a><a name="p17289154913718"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1729014491674"><a name="p1729014491674"></a><a name="p1729014491674"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row1427611491279"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p12291849172"><a name="p12291849172"></a><a name="p12291849172"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1629110491273"><a name="p1629110491273"></a><a name="p1629110491273"></a><a href="#response_instanceSpec">instanceSpec</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p15312749877"><a name="p15312749877"></a><a name="p15312749877"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p031324916712"><a name="p031324916712"></a><a name="p031324916712"></a>spec是集合类的元素类型，内容为插件实例具体信息，实例的详细描述主体部分都在spec中给出</p>
</td>
</tr>
<tr id="row72773491471"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1231418491871"><a name="p1231418491871"></a><a name="p1231418491871"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p53151749875"><a name="p53151749875"></a><a name="p53151749875"></a><a href="#response_status">status</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p331574918713"><a name="p331574918713"></a><a name="p331574918713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1631614491178"><a name="p1631614491178"></a><a name="p1631614491178"></a>插件实例状态</p>
</td>
</tr>
</tbody>
</table>

**表 6**  status

<a name="response_status"></a>
<table><thead align="left"><tr id="row73181049771"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p133217499713"><a name="p133217499713"></a><a name="p133217499713"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p173223495711"><a name="p173223495711"></a><a name="p173223495711"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p032244916711"><a name="p032244916711"></a><a name="p032244916711"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p732334912711"><a name="p732334912711"></a><a name="p732334912711"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row631812491770"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p183231549877"><a name="p183231549877"></a><a name="p183231549877"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p103244498714"><a name="p103244498714"></a><a name="p103244498714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p123249495716"><a name="p123249495716"></a><a name="p123249495716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p732417491878"><a name="p732417491878"></a><a name="p732417491878"></a>插件实例状态</p>
</td>
</tr>
<tr id="row731920491277"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p232516494715"><a name="p232516494715"></a><a name="p232516494715"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p173261349277"><a name="p173261349277"></a><a name="p173261349277"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1732714492720"><a name="p1732714492720"></a><a name="p1732714492720"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1328549278"><a name="p1328549278"></a><a name="p1328549278"></a>插件安装失败原因</p>
</td>
</tr>
<tr id="row93196496718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p632815492079"><a name="p632815492079"></a><a name="p632815492079"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14329154915714"><a name="p14329154915714"></a><a name="p14329154915714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p03301249774"><a name="p03301249774"></a><a name="p03301249774"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1533114499715"><a name="p1533114499715"></a><a name="p1533114499715"></a>安装错误详情</p>
</td>
</tr>
<tr id="row031915493711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1633213493715"><a name="p1633213493715"></a><a name="p1633213493715"></a>targetVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p53334494717"><a name="p53334494717"></a><a name="p53334494717"></a>Array of array</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p53336491971"><a name="p53336491971"></a><a name="p53336491971"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p18334144914716"><a name="p18334144914716"></a><a name="p18334144914716"></a>此插件版本，支持升级的集群版本</p>
</td>
</tr>
<tr id="row13191949976"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p53356491574"><a name="p53356491574"></a><a name="p53356491574"></a>currentVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p113369498718"><a name="p113369498718"></a><a name="p113369498718"></a><a href="#response_versions">versions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1333634918714"><a name="p1333634918714"></a><a name="p1333634918714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p0337134913713"><a name="p0337134913713"></a><a name="p0337134913713"></a>当前插件实例使用的具体插件版本信息</p>
</td>
</tr>
</tbody>
</table>

**表 7**  versions

<a name="response_versions"></a>
<table><thead align="left"><tr id="row13391491973"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1534374910716"><a name="p1534374910716"></a><a name="p1534374910716"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p234313491712"><a name="p234313491712"></a><a name="p234313491712"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p3344849279"><a name="p3344849279"></a><a name="p3344849279"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p834554912719"><a name="p834554912719"></a><a name="p834554912719"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row133913492711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p123461649975"><a name="p123461649975"></a><a name="p123461649975"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p63462492075"><a name="p63462492075"></a><a name="p63462492075"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p2034719491713"><a name="p2034719491713"></a><a name="p2034719491713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p16347549773"><a name="p16347549773"></a><a name="p16347549773"></a>插件版本号</p>
</td>
</tr>
<tr id="row933914914719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p10348164920714"><a name="p10348164920714"></a><a name="p10348164920714"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p634818493716"><a name="p634818493716"></a><a name="p634818493716"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p834913491877"><a name="p834913491877"></a><a name="p834913491877"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p93508491572"><a name="p93508491572"></a><a name="p93508491572"></a>插件安装参数</p>
</td>
</tr>
<tr id="row83392049879"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p7350114919719"><a name="p7350114919719"></a><a name="p7350114919719"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p4351154919712"><a name="p4351154919712"></a><a name="p4351154919712"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p93524490717"><a name="p93524490717"></a><a name="p93524490717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p93521491717"><a name="p93521491717"></a><a name="p93521491717"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row133401649572"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1235315491574"><a name="p1235315491574"></a><a name="p1235315491574"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p43545491777"><a name="p43545491777"></a><a name="p43545491777"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p635444912714"><a name="p635444912714"></a><a name="p635444912714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p93551749470"><a name="p93551749470"></a><a name="p93551749470"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row18340144910718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1435510498712"><a name="p1435510498712"></a><a name="p1435510498712"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p63565491871"><a name="p63565491871"></a><a name="p63565491871"></a>Array of <a href="#response_supportVersions">supportVersions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1835718494714"><a name="p1835718494714"></a><a name="p1835718494714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p11358649875"><a name="p11358649875"></a><a name="p11358649875"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row334020491074"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1435944914710"><a name="p1435944914710"></a><a name="p1435944914710"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p193602496716"><a name="p193602496716"></a><a name="p193602496716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p8360124919710"><a name="p8360124919710"></a><a name="p8360124919710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p536194917713"><a name="p536194917713"></a><a name="p536194917713"></a>创建时间</p>
</td>
</tr>
<tr id="row1034010491472"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p436213492711"><a name="p436213492711"></a><a name="p436213492711"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2036274912716"><a name="p2036274912716"></a><a name="p2036274912716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p336394914718"><a name="p336394914718"></a><a name="p336394914718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p036414491712"><a name="p036414491712"></a><a name="p036414491712"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 8**  supportVersions

<a name="response_supportVersions"></a>
<table><thead align="left"><tr id="row13365449277"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p83678498710"><a name="p83678498710"></a><a name="p83678498710"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p5368149078"><a name="p5368149078"></a><a name="p5368149078"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p23688492716"><a name="p23688492716"></a><a name="p23688492716"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p123691849179"><a name="p123691849179"></a><a name="p123691849179"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1636520491077"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p193708499713"><a name="p193708499713"></a><a name="p193708499713"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p203701849178"><a name="p203701849178"></a><a name="p203701849178"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1737113497712"><a name="p1737113497712"></a><a name="p1737113497712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p9372849379"><a name="p9372849379"></a><a name="p9372849379"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row1736613495710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p203739491577"><a name="p203739491577"></a><a name="p203739491577"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p13373164919715"><a name="p13373164919715"></a><a name="p13373164919715"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14374124918719"><a name="p14374124918719"></a><a name="p14374124918719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p73754494714"><a name="p73754494714"></a><a name="p73754494714"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 9**  instanceSpec

<a name="response_instanceSpec"></a>
<table><thead align="left"><tr id="row13772497714"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p12381174917715"><a name="p12381174917715"></a><a name="p12381174917715"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1338210497716"><a name="p1338210497716"></a><a name="p1338210497716"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p3383949174"><a name="p3383949174"></a><a name="p3383949174"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1438312495714"><a name="p1438312495714"></a><a name="p1438312495714"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row737715493710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p13846491474"><a name="p13846491474"></a><a name="p13846491474"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1538418493717"><a name="p1538418493717"></a><a name="p1538418493717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p19385849672"><a name="p19385849672"></a><a name="p19385849672"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1238617491379"><a name="p1238617491379"></a><a name="p1238617491379"></a>集群id</p>
</td>
</tr>
<tr id="row103775491773"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18386149778"><a name="p18386149778"></a><a name="p18386149778"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p183873499719"><a name="p183873499719"></a><a name="p183873499719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p12388549172"><a name="p12388549172"></a><a name="p12388549172"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p18388144911716"><a name="p18388144911716"></a><a name="p18388144911716"></a>插件模板版本号，如1.0.0</p>
</td>
</tr>
<tr id="row1037715491572"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p15389124911718"><a name="p15389124911718"></a><a name="p15389124911718"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p93899497713"><a name="p93899497713"></a><a name="p93899497713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1539084916710"><a name="p1539084916710"></a><a name="p1539084916710"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p239116491272"><a name="p239116491272"></a><a name="p239116491272"></a>插件模板名称，如coredns</p>
</td>
</tr>
<tr id="row73771549276"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1239113491973"><a name="p1239113491973"></a><a name="p1239113491973"></a>addonTemplateType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8392154914718"><a name="p8392154914718"></a><a name="p8392154914718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1139311494716"><a name="p1139311494716"></a><a name="p1139311494716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p15748850877"><a name="p15748850877"></a><a name="p15748850877"></a>插件模板类型</p>
</td>
</tr>
<tr id="row1037820497710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p177493506718"><a name="p177493506718"></a><a name="p177493506718"></a>addonTemplateLabels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p774914509717"><a name="p774914509717"></a><a name="p774914509717"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1474925017710"><a name="p1474925017710"></a><a name="p1474925017710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p12749145017711"><a name="p12749145017711"></a><a name="p12749145017711"></a>插件模板所属类型</p>
</td>
</tr>
<tr id="row737874913710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p77491504711"><a name="p77491504711"></a><a name="p77491504711"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p19750350770"><a name="p19750350770"></a><a name="p19750350770"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p167501850476"><a name="p167501850476"></a><a name="p167501850476"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p4750450777"><a name="p4750450777"></a><a name="p4750450777"></a>插件模板描述</p>
</td>
</tr>
<tr id="row173788491271"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p177505501377"><a name="p177505501377"></a><a name="p177505501377"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p775011501975"><a name="p775011501975"></a><a name="p775011501975"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p17500501471"><a name="p17500501471"></a><a name="p17500501471"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1475014507719"><a name="p1475014507719"></a><a name="p1475014507719"></a>插件模板安装参数（各插件不同）</p>
</td>
</tr>
</tbody>
</table>

**表 10**  metadata

<a name="response_metadata"></a>
<table><thead align="left"><tr id="row1940510491679"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p57511150870"><a name="p57511150870"></a><a name="p57511150870"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p15751145014718"><a name="p15751145014718"></a><a name="p15751145014718"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p175195013718"><a name="p175195013718"></a><a name="p175195013718"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1675219506718"><a name="p1675219506718"></a><a name="p1675219506718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row840511491576"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p8752175019717"><a name="p8752175019717"></a><a name="p8752175019717"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1175225013710"><a name="p1175225013710"></a><a name="p1175225013710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1075219502717"><a name="p1075219502717"></a><a name="p1075219502717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p14752150971"><a name="p14752150971"></a><a name="p14752150971"></a>唯一id标识</p>
</td>
</tr>
<tr id="row13405184915712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1675295013715"><a name="p1675295013715"></a><a name="p1675295013715"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p27531850270"><a name="p27531850270"></a><a name="p27531850270"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1753185018712"><a name="p1753185018712"></a><a name="p1753185018712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p67531250973"><a name="p67531250973"></a><a name="p67531250973"></a>插件名称</p>
</td>
</tr>
<tr id="row1940510498716"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p8753145019711"><a name="p8753145019711"></a><a name="p8753145019711"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p9754165016711"><a name="p9754165016711"></a><a name="p9754165016711"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p4754115019714"><a name="p4754115019714"></a><a name="p4754115019714"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p147546507712"><a name="p147546507712"></a><a name="p147546507712"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row204055494714"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p37542050170"><a name="p37542050170"></a><a name="p37542050170"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p77541150579"><a name="p77541150579"></a><a name="p77541150579"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p475425018711"><a name="p475425018711"></a><a name="p475425018711"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p107547501077"><a name="p107547501077"></a><a name="p107547501077"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row440614495710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1575513501374"><a name="p1575513501374"></a><a name="p1575513501374"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p77558508715"><a name="p77558508715"></a><a name="p77558508715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p107551650772"><a name="p107551650772"></a><a name="p107551650772"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p147558501871"><a name="p147558501871"></a><a name="p147558501871"></a>更新时间</p>
</td>
</tr>
<tr id="row14062491978"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2075519508718"><a name="p2075519508718"></a><a name="p2075519508718"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p107556509712"><a name="p107556509712"></a><a name="p107556509712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1275555010716"><a name="p1275555010716"></a><a name="p1275555010716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1755195017719"><a name="p1755195017719"></a><a name="p1755195017719"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section1075618501872"></a>

```
{
	"kind" : "string",
	"apVersion" : "string",
	"metadata" : 
},
"spec" : {
	"version" : "string",
	"clusterID" : "string",
	"values" : 
},
"addonTemplateName" : "string"
}
}
```

## 响应示例<a name="section3757165016719"></a>

状态码为 200 时:

```
{
	"metadata":{
		"uid":"24b23108-55c0-11e9-926f-0255ac101a31",
		"name":"gpu-beta",
		"creationTimestamp":"2019-04-03T03:25:34Z",
		"updateTimestamp":"2019-04-03T03:25:34Z"
	},
	"apiVersion":"v3",
	"kind":"Addon",
	"spec":{
		"addonTemplateName":"gpu-beta",
		"addonTemplateLogo":"",
		"addonTemplateType":"helm",
		"values":{
			"basic":{
				"rbac_enabled":true,
				"swr_user":"hwofficial",
				"swr_addr":"100.125.6.246:20202"
			}
		},
		"description":"A device plugin for nvidia.com/gpu resource on nvidia driver",
		"addonTemplateLabels":[
			"Accelerator"
		],
		"clusterID":"0c0e4a63-5539-11e9-95f7-0255ac10177e",
		"version":"1.0.0"
	},
	"status":{
		"message":"",
		"Reason":"",
		"currentVersion":{
			"input":{
				"basic":{
					"swr_user":"hwofficial",
					"swr_addr":"100.125.6.246:20202"
				},
				"parameters":{
					
				}
			},
			"stable":true,
			"creationTimestamp":"2018-10-23T13:14:55Z",
			"version":"1.0.0",
			"translate":{
				"en_US":{
					"addon":{
						"changeLog":"A device plugin for nvidia.com/gpu resource on nvidia driver",
						"description":"A device plugin for nvidia.com/gpu resource on nvidia driver"
					}
				},
				"zh_CN":{
					"addon":{
						"changeLog":"支持容器里使用GPU显卡的设备管理插件，仅支持nvidia驱动",
						"description":"支持容器里使用GPU显卡的设备管理插件，仅支持nvidia驱动"
					}
				}
			},
			"updateTimestamp":"2018-12-07T09:40:24Z"
		},
		"status":"installing"
	}
}
```

状态码为 500 时:

```
{
	"code":"SVCSTG.CCE-ADDONMGR.500",
	"message":"internal error"
}
```

## 返回值<a name="section117635504719"></a>

<a name="table19"></a>
<table><thead align="left"><tr id="row13459104918718"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p1576415015719"><a name="p1576415015719"></a><a name="p1576415015719"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p1676415501713"><a name="p1676415501713"></a><a name="p1676415501713"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row0459134916719"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p107641950777"><a name="p107641950777"></a><a name="p107641950777"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p976415508716"><a name="p976415508716"></a><a name="p976415508716"></a>OK</p>
</td>
</tr>
<tr id="row1646013499711"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p7764185012718"><a name="p7764185012718"></a><a name="p7764185012718"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p776412501277"><a name="p776412501277"></a><a name="p776412501277"></a>Internal Server Error</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section7765250774"></a>

<a name="table20"></a>
<table><thead align="left"><tr id="row1846517491079"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.5.1.1"><p id="p87658501879"><a name="p87658501879"></a><a name="p87658501879"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.2"><p id="p127651850576"><a name="p127651850576"></a><a name="p127651850576"></a>错误码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.3"><p id="p476515502716"><a name="p476515502716"></a><a name="p476515502716"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="35%" id="mcps1.1.5.1.4"><p id="p1876619501179"><a name="p1876619501179"></a><a name="p1876619501179"></a>解决方案</p>
</th>
</tr>
</thead>
<tbody><tr id="row11465164920710"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p5766145019710"><a name="p5766145019710"></a><a name="p5766145019710"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p197661550975"><a name="p197661550975"></a><a name="p197661550975"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1076610506717"><a name="p1076610506717"></a><a name="p1076610506717"></a>bad request</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row154651649975"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p576685012714"><a name="p576685012714"></a><a name="p576685012714"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p18766450371"><a name="p18766450371"></a><a name="p18766450371"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p137663500711"><a name="p137663500711"></a><a name="p137663500711"></a>Authenticate failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row14651492073"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p876616501570"><a name="p876616501570"></a><a name="p876616501570"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p157669500715"><a name="p157669500715"></a><a name="p157669500715"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p97661150275"><a name="p97661150275"></a><a name="p97661150275"></a>Authorize failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row18465249372"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p1376716506719"><a name="p1376716506719"></a><a name="p1376716506719"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p076715501274"><a name="p076715501274"></a><a name="p076715501274"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p17767145018717"><a name="p17767145018717"></a><a name="p17767145018717"></a>addontemplate not exist</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row24657495711"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p127671450975"><a name="p127671450975"></a><a name="p127671450975"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p167678508713"><a name="p167678508713"></a><a name="p167678508713"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p12767165016715"><a name="p12767165016715"></a><a name="p12767165016715"></a>server internal error</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
</tbody>
</table>

