# 删除AddonInstance<a name="cce_02_0324"></a>

## 功能介绍<a name="section293419499713"></a>

删除插件实例的功能

## URI<a name="section189350497716"></a>

DELETE /api/v3/addons/\{id\}?cluster\_id=\{cluster\_id\}

**表 1**  路径参数

<a name="table493910491373"></a>
<table><thead align="left"><tr id="row1693894920717"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p129401491177"><a name="p129401491177"></a><a name="p129401491177"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p199401491576"><a name="p199401491576"></a><a name="p199401491576"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p11941549372"><a name="p11941549372"></a><a name="p11941549372"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p594211496717"><a name="p594211496717"></a><a name="p594211496717"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row89385497714"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p4943749474"><a name="p4943749474"></a><a name="p4943749474"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p149448492076"><a name="p149448492076"></a><a name="p149448492076"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p169458493711"><a name="p169458493711"></a><a name="p169458493711"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p179456493719"><a name="p179456493719"></a><a name="p179456493719"></a>集群id</p>
</td>
</tr>
<tr id="row18938349479"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1794634912710"><a name="p1794634912710"></a><a name="p1794634912710"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1947104918710"><a name="p1947104918710"></a><a name="p1947104918710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1894718491778"><a name="p1894718491778"></a><a name="p1894718491778"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p159489491773"><a name="p159489491773"></a><a name="p159489491773"></a>插件实例id</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section169491849875"></a>

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row179511549172"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1295316491672"><a name="p1295316491672"></a><a name="p1295316491672"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p149548491978"><a name="p149548491978"></a><a name="p149548491978"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p12955049675"><a name="p12955049675"></a><a name="p12955049675"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p195534910712"><a name="p195534910712"></a><a name="p195534910712"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row795104913711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p995614917718"><a name="p995614917718"></a><a name="p995614917718"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p495717491771"><a name="p495717491771"></a><a name="p495717491771"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p169581491773"><a name="p169581491773"></a><a name="p169581491773"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p895916497712"><a name="p895916497712"></a><a name="p895916497712"></a>消息体的类型（格式），下方类型可任选其一使用</p>
<p id="p209592492075"><a name="p209592492075"></a><a name="p209592492075"></a>application/json;charset=utf-8</p>
<p id="p1496011494710"><a name="p1496011494710"></a><a name="p1496011494710"></a>application/json</p>
</td>
</tr>
<tr id="row095114491716"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18960174911711"><a name="p18960174911711"></a><a name="p18960174911711"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p5961134911717"><a name="p5961134911717"></a><a name="p5961134911717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p396214491979"><a name="p396214491979"></a><a name="p396214491979"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p096234919711"><a name="p096234919711"></a><a name="p096234919711"></a>在华为云上调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填</p>
</td>
</tr>
</tbody>
</table>

**表 3**  请求Body参数

<a name="requestParameter"></a>
<table><thead align="left"><tr id="row39651049970"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p79757491676"><a name="p79757491676"></a><a name="p79757491676"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1297615491679"><a name="p1297615491679"></a><a name="p1297615491679"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p1797714916713"><a name="p1797714916713"></a><a name="p1797714916713"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p49778492717"><a name="p49778492717"></a><a name="p49778492717"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row896517498719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p12978174918710"><a name="p12978174918710"></a><a name="p12978174918710"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1697919491671"><a name="p1697919491671"></a><a name="p1697919491671"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p15980174917717"><a name="p15980174917717"></a><a name="p15980174917717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p09812492719"><a name="p09812492719"></a><a name="p09812492719"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row4965174915720"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p109821949874"><a name="p109821949874"></a><a name="p109821949874"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p59835491375"><a name="p59835491375"></a><a name="p59835491375"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p139841549978"><a name="p139841549978"></a><a name="p139841549978"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p39851949479"><a name="p39851949479"></a><a name="p39851949479"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row159657491173"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p209851249677"><a name="p209851249677"></a><a name="p209851249677"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1698624920716"><a name="p1698624920716"></a><a name="p1698624920716"></a><a href="#metadata">metadata</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p898818497712"><a name="p898818497712"></a><a name="p898818497712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1989164910715"><a name="p1989164910715"></a><a name="p1989164910715"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row1996513491277"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p11990124917718"><a name="p11990124917718"></a><a name="p11990124917718"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1299044915715"><a name="p1299044915715"></a><a name="p1299044915715"></a><a href="#templatespec">templatespec</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p159919491712"><a name="p159919491712"></a><a name="p159919491712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p12992124912711"><a name="p12992124912711"></a><a name="p12992124912711"></a>spec是集合类的元素类型，内容为插件模板具体信息，插件模板的详细描述主体部分都在spec中给出</p>
</td>
</tr>
</tbody>
</table>

**表 4**  templatespec

<a name="templatespec"></a>
<table><thead align="left"><tr id="row899611491575"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1817501375"><a name="p1817501375"></a><a name="p1817501375"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p521250271"><a name="p521250271"></a><a name="p521250271"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p17314501073"><a name="p17314501073"></a><a name="p17314501073"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p6418501179"><a name="p6418501179"></a><a name="p6418501179"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row3996749774"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p114450978"><a name="p114450978"></a><a name="p114450978"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1071150777"><a name="p1071150777"></a><a name="p1071150777"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p08950171"><a name="p08950171"></a><a name="p08950171"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1991750379"><a name="p1991750379"></a><a name="p1991750379"></a>模板类型（helm，static）</p>
</td>
</tr>
<tr id="row199963491079"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1310175018716"><a name="p1310175018716"></a><a name="p1310175018716"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p311250077"><a name="p311250077"></a><a name="p311250077"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p181117505715"><a name="p181117505715"></a><a name="p181117505715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p71218502071"><a name="p71218502071"></a><a name="p71218502071"></a>模板所属分组</p>
</td>
</tr>
<tr id="row899718491471"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p14127505712"><a name="p14127505712"></a><a name="p14127505712"></a>logoURL</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p9132507711"><a name="p9132507711"></a><a name="p9132507711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p101316501678"><a name="p101316501678"></a><a name="p101316501678"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p2014195015713"><a name="p2014195015713"></a><a name="p2014195015713"></a>Logo图片地址</p>
</td>
</tr>
<tr id="row499744912710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p131555016720"><a name="p131555016720"></a><a name="p131555016720"></a>readmeURL</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p61510501678"><a name="p61510501678"></a><a name="p61510501678"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p10167506717"><a name="p10167506717"></a><a name="p10167506717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p121712501378"><a name="p121712501378"></a><a name="p121712501378"></a>Logo图片地址</p>
</td>
</tr>
<tr id="row999714492713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p11717501379"><a name="p11717501379"></a><a name="p11717501379"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p418175016719"><a name="p418175016719"></a><a name="p418175016719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p62216501474"><a name="p62216501474"></a><a name="p62216501474"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p3236502072"><a name="p3236502072"></a><a name="p3236502072"></a>模板描述</p>
</td>
</tr>
<tr id="row2997749577"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p182365016710"><a name="p182365016710"></a><a name="p182365016710"></a>versions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2256501071"><a name="p2256501071"></a><a name="p2256501071"></a>Array of <a href="#versions">versions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p8255502073"><a name="p8255502073"></a><a name="p8255502073"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p22625015715"><a name="p22625015715"></a><a name="p22625015715"></a>模板具体版本详情</p>
</td>
</tr>
<tr id="row89981549778"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1427145015719"><a name="p1427145015719"></a><a name="p1427145015719"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p6278501974"><a name="p6278501974"></a><a name="p6278501974"></a>Array of <a href="#supportVersions">supportVersions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p728135016717"><a name="p728135016717"></a><a name="p728135016717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p32914503720"><a name="p32914503720"></a><a name="p32914503720"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row17999144919711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p113055017717"><a name="p113055017717"></a><a name="p113055017717"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2311509712"><a name="p2311509712"></a><a name="p2311509712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p731115016714"><a name="p731115016714"></a><a name="p731115016714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p832850476"><a name="p832850476"></a><a name="p832850476"></a>创建时间</p>
</td>
</tr>
<tr id="row1699919492072"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p173310501079"><a name="p173310501079"></a><a name="p173310501079"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p123316505715"><a name="p123316505715"></a><a name="p123316505715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p163410501472"><a name="p163410501472"></a><a name="p163410501472"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p133513501073"><a name="p133513501073"></a><a name="p133513501073"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 5**  supportVersions

<a name="supportVersions"></a>
<table><thead align="left"><tr id="row1436050177"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1737150776"><a name="p1737150776"></a><a name="p1737150776"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p163805019711"><a name="p163805019711"></a><a name="p163805019711"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p63810509711"><a name="p63810509711"></a><a name="p63810509711"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p173925012710"><a name="p173925012710"></a><a name="p173925012710"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row13665017715"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p340195019713"><a name="p340195019713"></a><a name="p340195019713"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p84115018716"><a name="p84115018716"></a><a name="p84115018716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p18421250970"><a name="p18421250970"></a><a name="p18421250970"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p124212503711"><a name="p124212503711"></a><a name="p124212503711"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row43617509717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p3431450476"><a name="p3431450476"></a><a name="p3431450476"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p11445501477"><a name="p11445501477"></a><a name="p11445501477"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p3469501375"><a name="p3469501375"></a><a name="p3469501375"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p5461450374"><a name="p5461450374"></a><a name="p5461450374"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 6**  versions

<a name="versions"></a>
<table><thead align="left"><tr id="row144915501874"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p3531250179"><a name="p3531250179"></a><a name="p3531250179"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p55435012713"><a name="p55435012713"></a><a name="p55435012713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p155411501712"><a name="p155411501712"></a><a name="p155411501712"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p255195017716"><a name="p255195017716"></a><a name="p255195017716"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row15491950675"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p955850178"><a name="p955850178"></a><a name="p955850178"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p55612507715"><a name="p55612507715"></a><a name="p55612507715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p4571150678"><a name="p4571150678"></a><a name="p4571150678"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p10572503714"><a name="p10572503714"></a><a name="p10572503714"></a>插件版本号</p>
</td>
</tr>
<tr id="row2501350371"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p7582501375"><a name="p7582501375"></a><a name="p7582501375"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p15599501174"><a name="p15599501174"></a><a name="p15599501174"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p26016503717"><a name="p26016503717"></a><a name="p26016503717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p106116501573"><a name="p106116501573"></a><a name="p106116501573"></a>插件安装参数</p>
</td>
</tr>
<tr id="row4507504714"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p146255018711"><a name="p146255018711"></a><a name="p146255018711"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p206495016712"><a name="p206495016712"></a><a name="p206495016712"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p265650972"><a name="p265650972"></a><a name="p265650972"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1365450377"><a name="p1365450377"></a><a name="p1365450377"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row1150550472"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p106619502710"><a name="p106619502710"></a><a name="p106619502710"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p15678508719"><a name="p15678508719"></a><a name="p15678508719"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1567125020717"><a name="p1567125020717"></a><a name="p1567125020717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p9681507720"><a name="p9681507720"></a><a name="p9681507720"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row55011501272"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1696504714"><a name="p1696504714"></a><a name="p1696504714"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1270150372"><a name="p1270150372"></a><a name="p1270150372"></a>Array of <a href="#supportVersions">supportVersions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p970185020717"><a name="p970185020717"></a><a name="p970185020717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p177120506710"><a name="p177120506710"></a><a name="p177120506710"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row12508509714"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p19724502713"><a name="p19724502713"></a><a name="p19724502713"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p47210503718"><a name="p47210503718"></a><a name="p47210503718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p15731150779"><a name="p15731150779"></a><a name="p15731150779"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p8742504712"><a name="p8742504712"></a><a name="p8742504712"></a>创建时间</p>
</td>
</tr>
<tr id="row35019508710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p27410501271"><a name="p27410501271"></a><a name="p27410501271"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1075195010710"><a name="p1075195010710"></a><a name="p1075195010710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p7768501371"><a name="p7768501371"></a><a name="p7768501371"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p9820500716"><a name="p9820500716"></a><a name="p9820500716"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 7**  supportVersions

<a name="table118365013717"></a>
<table><thead align="left"><tr id="row785850172"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p19896505715"><a name="p19896505715"></a><a name="p19896505715"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p18975017712"><a name="p18975017712"></a><a name="p18975017712"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p199015508720"><a name="p199015508720"></a><a name="p199015508720"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p189175013716"><a name="p189175013716"></a><a name="p189175013716"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row28555010717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p19418506720"><a name="p19418506720"></a><a name="p19418506720"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1996195013717"><a name="p1996195013717"></a><a name="p1996195013717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p199745011713"><a name="p199745011713"></a><a name="p199745011713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p9980501873"><a name="p9980501873"></a><a name="p9980501873"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row4856500714"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p59919507710"><a name="p59919507710"></a><a name="p59919507710"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p131001850071"><a name="p131001850071"></a><a name="p131001850071"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p121017509714"><a name="p121017509714"></a><a name="p121017509714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1110212502070"><a name="p1110212502070"></a><a name="p1110212502070"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 8**  metadata

<a name="metadata"></a>
<table><thead align="left"><tr id="row161054501871"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p811412504712"><a name="p811412504712"></a><a name="p811412504712"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p8115195010716"><a name="p8115195010716"></a><a name="p8115195010716"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p171167501276"><a name="p171167501276"></a><a name="p171167501276"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p41167503718"><a name="p41167503718"></a><a name="p41167503718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row17105150176"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p611765017716"><a name="p611765017716"></a><a name="p611765017716"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p71171509711"><a name="p71171509711"></a><a name="p71171509711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p31183502719"><a name="p31183502719"></a><a name="p31183502719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p191191450778"><a name="p191191450778"></a><a name="p191191450778"></a>唯一id标识</p>
</td>
</tr>
<tr id="row181054507716"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1812065014719"><a name="p1812065014719"></a><a name="p1812065014719"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8121115016714"><a name="p8121115016714"></a><a name="p8121115016714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p11213502071"><a name="p11213502071"></a><a name="p11213502071"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p212275013711"><a name="p212275013711"></a><a name="p212275013711"></a>插件名称</p>
</td>
</tr>
<tr id="row411011501578"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2123650079"><a name="p2123650079"></a><a name="p2123650079"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1712418507716"><a name="p1712418507716"></a><a name="p1712418507716"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p191251350975"><a name="p191251350975"></a><a name="p191251350975"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p161259504719"><a name="p161259504719"></a><a name="p161259504719"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row171112050379"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p15126115015719"><a name="p15126115015719"></a><a name="p15126115015719"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p15126135011716"><a name="p15126135011716"></a><a name="p15126135011716"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p412719508717"><a name="p412719508717"></a><a name="p412719508717"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p181277503716"><a name="p181277503716"></a><a name="p181277503716"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row13111150879"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p01285509718"><a name="p01285509718"></a><a name="p01285509718"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p9128175014711"><a name="p9128175014711"></a><a name="p9128175014711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p613015015711"><a name="p613015015711"></a><a name="p613015015711"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1013119501071"><a name="p1013119501071"></a><a name="p1013119501071"></a>更新时间</p>
</td>
</tr>
<tr id="row1811118505712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2132115012716"><a name="p2132115012716"></a><a name="p2132115012716"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p101335503720"><a name="p101335503720"></a><a name="p101335503720"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p713365020715"><a name="p713365020715"></a><a name="p713365020715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p16134850872"><a name="p16134850872"></a><a name="p16134850872"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section171345501278"></a>

无

## 请求示例<a name="section31356501775"></a>

```
{
	"requesbody" : {
		"kind" : "string",
		"apiVersion" : "string",
		"metadata" : {
			"uid" : "string",
			"name" : "string",
			"labels" : "object",
			"annotations" : "object",
			"updateTimestamp" : "string",
			"creationTimestamp" : "string"
		},
		"spec" : {
			"type" : "string",
			"labels" : [
				 "string",
				"string"
			],
			"logoURL" : "string",
			"readmeURL" : "string",
			"description" : "string",
			"versions" : [
				{
					"version" : "string",
					"input" : 
				},
				"stable" : "boolean",
				"translate" : 
			},
			"supportVersions" : [
				{
					"clusterType" : "string",
					"clusterVersion" : [
						 "string",
						"string"
					]
				}
			],
			"creationTimestamp" : "string",
			"updateTimestamp" : "string"
		}
	],
	"supportVersions" : [
		{
			"clusterType" : "string",
			"clusterVersion" : [
				 "string",
				"string"
			]
		}
	],
	"creationTimestamp" : "string",
	"updateTimestamp" : "string"
},

}
}
```

## 响应示例<a name="section15464185113718"></a>

状态码为 200 时:

```
{
	"string":"string"
}
```

状态码为 500 时:

```
{
	"code":"SVCSTG.CCE-ADDONMGR.500",
	"message":"internal error"
}
```

## 返回值<a name="section194651851070"></a>

<a name="table23"></a>
<table><thead align="left"><tr id="row15164850871"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p174651151772"><a name="p174651151772"></a><a name="p174651151772"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p18465105120712"><a name="p18465105120712"></a><a name="p18465105120712"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row161641250576"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p44659513713"><a name="p44659513713"></a><a name="p44659513713"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p1246518518714"><a name="p1246518518714"></a><a name="p1246518518714"></a>OK</p>
</td>
</tr>
<tr id="row161657501378"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p13466105110712"><a name="p13466105110712"></a><a name="p13466105110712"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p54661511272"><a name="p54661511272"></a><a name="p54661511272"></a>Internal Server Error</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section64661151176"></a>

<a name="table24"></a>
<table><thead align="left"><tr id="row1117512508713"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.5.1.1"><p id="p146619510714"><a name="p146619510714"></a><a name="p146619510714"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.2"><p id="p6466195120711"><a name="p6466195120711"></a><a name="p6466195120711"></a>错误码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.3"><p id="p144664512077"><a name="p144664512077"></a><a name="p144664512077"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="35%" id="mcps1.1.5.1.4"><p id="p1446785117718"><a name="p1446785117718"></a><a name="p1446785117718"></a>解决方案</p>
</th>
</tr>
</thead>
<tbody><tr id="row11751501716"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p1846712516714"><a name="p1846712516714"></a><a name="p1846712516714"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1246718515715"><a name="p1246718515715"></a><a name="p1246718515715"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1346711512079"><a name="p1346711512079"></a><a name="p1346711512079"></a>bad request</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row3175350972"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p18467251378"><a name="p18467251378"></a><a name="p18467251378"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1746712518714"><a name="p1746712518714"></a><a name="p1746712518714"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1467145118714"><a name="p1467145118714"></a><a name="p1467145118714"></a>Authenticate failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row11176165013719"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p14681451878"><a name="p14681451878"></a><a name="p14681451878"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1346812513717"><a name="p1346812513717"></a><a name="p1346812513717"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p546815515712"><a name="p546815515712"></a><a name="p546815515712"></a>Authorize failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row131761508712"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p8468851974"><a name="p8468851974"></a><a name="p8468851974"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p0468115110717"><a name="p0468115110717"></a><a name="p0468115110717"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p114688510718"><a name="p114688510718"></a><a name="p114688510718"></a>addon instance not exist</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row14176165011719"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p16469115118712"><a name="p16469115118712"></a><a name="p16469115118712"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p946916513712"><a name="p946916513712"></a><a name="p946916513712"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p18469451672"><a name="p18469451672"></a><a name="p18469451672"></a>server internal error</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
</tbody>
</table>

