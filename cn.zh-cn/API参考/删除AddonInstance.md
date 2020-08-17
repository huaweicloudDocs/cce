# 删除AddonInstance<a name="cce_02_0324"></a>

## 功能描述<a name="section293419499713"></a>

删除插件实例的功能。

## URI<a name="section189350497716"></a>

DELETE /api/v3/addons/\{id\}?cluster\_id=\{cluster\_id\}

**表 1**  路径参数

<a name="table493910491373"></a>
<table><thead align="left"><tr id="row1693894920717"><th class="cellrowborder" valign="top" width="17.95%" id="mcps1.2.5.1.1"><p id="p129401491177"><a name="p129401491177"></a><a name="p129401491177"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.21%" id="mcps1.2.5.1.2"><p id="p4421354844"><a name="p4421354844"></a><a name="p4421354844"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.88%" id="mcps1.2.5.1.3"><p id="p199401491576"><a name="p199401491576"></a><a name="p199401491576"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.96000000000001%" id="mcps1.2.5.1.4"><p id="p594211496717"><a name="p594211496717"></a><a name="p594211496717"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row89385497714"><td class="cellrowborder" valign="top" width="17.95%" headers="mcps1.2.5.1.1 "><p id="p4943749474"><a name="p4943749474"></a><a name="p4943749474"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="14.21%" headers="mcps1.2.5.1.2 "><p id="p205342313510"><a name="p205342313510"></a><a name="p205342313510"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.88%" headers="mcps1.2.5.1.3 "><p id="p149448492076"><a name="p149448492076"></a><a name="p149448492076"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.96000000000001%" headers="mcps1.2.5.1.4 "><p id="p15106445114416"><a name="p15106445114416"></a><a name="p15106445114416"></a>集群ID，获取方式请参见<a href="如何获取接口URI中参数.md">如何获取接口URI中参数</a>。</p>
</td>
</tr>
<tr id="row18938349479"><td class="cellrowborder" valign="top" width="17.95%" headers="mcps1.2.5.1.1 "><p id="p1794634912710"><a name="p1794634912710"></a><a name="p1794634912710"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="14.21%" headers="mcps1.2.5.1.2 "><p id="p18534193357"><a name="p18534193357"></a><a name="p18534193357"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.88%" headers="mcps1.2.5.1.3 "><p id="p1947104918710"><a name="p1947104918710"></a><a name="p1947104918710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.96000000000001%" headers="mcps1.2.5.1.4 "><p id="p152383501074"><a name="p152383501074"></a><a name="p152383501074"></a>插件实例ID，获取方式请参见<a href="获取AddonInstance列表.md#response_metadata">表9</a>。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section169491849875"></a>

**请求参数：**

请求参数如下所示。

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row179511549172"><th class="cellrowborder" valign="top" width="18.17%" id="mcps1.2.5.1.1"><p id="p1295316491672"><a name="p1295316491672"></a><a name="p1295316491672"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.76%" id="mcps1.2.5.1.2"><p id="p0638101611518"><a name="p0638101611518"></a><a name="p0638101611518"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.120000000000001%" id="mcps1.2.5.1.3"><p id="p149548491978"><a name="p149548491978"></a><a name="p149548491978"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p195534910712"><a name="p195534910712"></a><a name="p195534910712"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row795104913711"><td class="cellrowborder" valign="top" width="18.17%" headers="mcps1.2.5.1.1 "><p id="p995614917718"><a name="p995614917718"></a><a name="p995614917718"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="15.76%" headers="mcps1.2.5.1.2 "><p id="p3595422152"><a name="p3595422152"></a><a name="p3595422152"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p495717491771"><a name="p495717491771"></a><a name="p495717491771"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p895916497712"><a name="p895916497712"></a><a name="p895916497712"></a>消息体的类型（格式），下方类型可任选其一使用</p>
<a name="ul17408183516263"></a><a name="ul17408183516263"></a><ul id="ul17408183516263"><li>application/json;charset=utf-8</li><li>application/json</li></ul>
</td>
</tr>
<tr id="row095114491716"><td class="cellrowborder" valign="top" width="18.17%" headers="mcps1.2.5.1.1 "><p id="p18960174911711"><a name="p18960174911711"></a><a name="p18960174911711"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="15.76%" headers="mcps1.2.5.1.2 "><p id="p459512214517"><a name="p459512214517"></a><a name="p459512214517"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p5961134911717"><a name="p5961134911717"></a><a name="p5961134911717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p34291037192615"><a name="p34291037192615"></a><a name="p34291037192615"></a>调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="认证鉴权.md#section2417768214391">获取token</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  templatespec

<a name="templatespec"></a>
<table><thead align="left"><tr id="row899611491575"><th class="cellrowborder" valign="top" width="16.470000000000002%" id="mcps1.2.5.1.1"><p id="p1817501375"><a name="p1817501375"></a><a name="p1817501375"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.629999999999999%" id="mcps1.2.5.1.2"><p id="p1761103418619"><a name="p1761103418619"></a><a name="p1761103418619"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.950000000000003%" id="mcps1.2.5.1.3"><p id="p521250271"><a name="p521250271"></a><a name="p521250271"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p6418501179"><a name="p6418501179"></a><a name="p6418501179"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row3996749774"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p114450978"><a name="p114450978"></a><a name="p114450978"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p173839511465"><a name="p173839511465"></a><a name="p173839511465"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.950000000000003%" headers="mcps1.2.5.1.3 "><p id="p1071150777"><a name="p1071150777"></a><a name="p1071150777"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1991750379"><a name="p1991750379"></a><a name="p1991750379"></a>模板类型（helm，static）</p>
</td>
</tr>
<tr id="row199963491079"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p1310175018716"><a name="p1310175018716"></a><a name="p1310175018716"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p138416511467"><a name="p138416511467"></a><a name="p138416511467"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.950000000000003%" headers="mcps1.2.5.1.3 "><p id="p311250077"><a name="p311250077"></a><a name="p311250077"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p71218502071"><a name="p71218502071"></a><a name="p71218502071"></a>模板所属分组</p>
</td>
</tr>
<tr id="row899718491471"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p14127505712"><a name="p14127505712"></a><a name="p14127505712"></a>logoURL</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p163844511763"><a name="p163844511763"></a><a name="p163844511763"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.950000000000003%" headers="mcps1.2.5.1.3 "><p id="p9132507711"><a name="p9132507711"></a><a name="p9132507711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p2014195015713"><a name="p2014195015713"></a><a name="p2014195015713"></a>Logo图片地址</p>
</td>
</tr>
<tr id="row499744912710"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p131555016720"><a name="p131555016720"></a><a name="p131555016720"></a>readmeURL</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p15384651468"><a name="p15384651468"></a><a name="p15384651468"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.950000000000003%" headers="mcps1.2.5.1.3 "><p id="p61510501678"><a name="p61510501678"></a><a name="p61510501678"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p121712501378"><a name="p121712501378"></a><a name="p121712501378"></a>Logo图片地址</p>
</td>
</tr>
<tr id="row999714492713"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p11717501379"><a name="p11717501379"></a><a name="p11717501379"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p438418516618"><a name="p438418516618"></a><a name="p438418516618"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.950000000000003%" headers="mcps1.2.5.1.3 "><p id="p418175016719"><a name="p418175016719"></a><a name="p418175016719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p3236502072"><a name="p3236502072"></a><a name="p3236502072"></a>模板描述</p>
</td>
</tr>
<tr id="row2997749577"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p182365016710"><a name="p182365016710"></a><a name="p182365016710"></a>versions</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p73841051165"><a name="p73841051165"></a><a name="p73841051165"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.950000000000003%" headers="mcps1.2.5.1.3 "><p id="p2256501071"><a name="p2256501071"></a><a name="p2256501071"></a>Array of <a href="#versions">versions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p22625015715"><a name="p22625015715"></a><a name="p22625015715"></a>模板具体版本详情</p>
</td>
</tr>
<tr id="row89981549778"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p1427145015719"><a name="p1427145015719"></a><a name="p1427145015719"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p1038405119616"><a name="p1038405119616"></a><a name="p1038405119616"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.950000000000003%" headers="mcps1.2.5.1.3 "><p id="p6278501974"><a name="p6278501974"></a><a name="p6278501974"></a>Array of <a href="#supportVersions">supportVersions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p32914503720"><a name="p32914503720"></a><a name="p32914503720"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row17999144919711"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p113055017717"><a name="p113055017717"></a><a name="p113055017717"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p10384351262"><a name="p10384351262"></a><a name="p10384351262"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.950000000000003%" headers="mcps1.2.5.1.3 "><p id="p2311509712"><a name="p2311509712"></a><a name="p2311509712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p832850476"><a name="p832850476"></a><a name="p832850476"></a>创建时间</p>
</td>
</tr>
<tr id="row1699919492072"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p173310501079"><a name="p173310501079"></a><a name="p173310501079"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p1338413511562"><a name="p1338413511562"></a><a name="p1338413511562"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.950000000000003%" headers="mcps1.2.5.1.3 "><p id="p123316505715"><a name="p123316505715"></a><a name="p123316505715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p133513501073"><a name="p133513501073"></a><a name="p133513501073"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 4**  supportVersions

<a name="supportVersions"></a>
<table><thead align="left"><tr id="row1436050177"><th class="cellrowborder" valign="top" width="13.52%" id="mcps1.2.5.1.1"><p id="p1737150776"><a name="p1737150776"></a><a name="p1737150776"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.64%" id="mcps1.2.5.1.2"><p id="p36941550197"><a name="p36941550197"></a><a name="p36941550197"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.89%" id="mcps1.2.5.1.3"><p id="p163805019711"><a name="p163805019711"></a><a name="p163805019711"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p173925012710"><a name="p173925012710"></a><a name="p173925012710"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13665017715"><td class="cellrowborder" valign="top" width="13.52%" headers="mcps1.2.5.1.1 "><p id="p340195019713"><a name="p340195019713"></a><a name="p340195019713"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="19.64%" headers="mcps1.2.5.1.2 "><p id="p770118571499"><a name="p770118571499"></a><a name="p770118571499"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.89%" headers="mcps1.2.5.1.3 "><p id="p84115018716"><a name="p84115018716"></a><a name="p84115018716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p124212503711"><a name="p124212503711"></a><a name="p124212503711"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row43617509717"><td class="cellrowborder" valign="top" width="13.52%" headers="mcps1.2.5.1.1 "><p id="p3431450476"><a name="p3431450476"></a><a name="p3431450476"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.64%" headers="mcps1.2.5.1.2 "><p id="p20701125718915"><a name="p20701125718915"></a><a name="p20701125718915"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.89%" headers="mcps1.2.5.1.3 "><p id="p11445501477"><a name="p11445501477"></a><a name="p11445501477"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p5461450374"><a name="p5461450374"></a><a name="p5461450374"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 5**  versions

<a name="versions"></a>
<table><thead align="left"><tr id="row144915501874"><th class="cellrowborder" valign="top" width="16.050000000000004%" id="mcps1.2.5.1.1"><p id="p3531250179"><a name="p3531250179"></a><a name="p3531250179"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.44%" id="mcps1.2.5.1.2"><p id="p468017713107"><a name="p468017713107"></a><a name="p468017713107"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.560000000000002%" id="mcps1.2.5.1.3"><p id="p55435012713"><a name="p55435012713"></a><a name="p55435012713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.95%" id="mcps1.2.5.1.4"><p id="p255195017716"><a name="p255195017716"></a><a name="p255195017716"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15491950675"><td class="cellrowborder" valign="top" width="16.050000000000004%" headers="mcps1.2.5.1.1 "><p id="p955850178"><a name="p955850178"></a><a name="p955850178"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.2 "><p id="p6807615121018"><a name="p6807615121018"></a><a name="p6807615121018"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p55612507715"><a name="p55612507715"></a><a name="p55612507715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p10572503714"><a name="p10572503714"></a><a name="p10572503714"></a>插件版本号</p>
</td>
</tr>
<tr id="row2501350371"><td class="cellrowborder" valign="top" width="16.050000000000004%" headers="mcps1.2.5.1.1 "><p id="p7582501375"><a name="p7582501375"></a><a name="p7582501375"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.2 "><p id="p48071415131019"><a name="p48071415131019"></a><a name="p48071415131019"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p15599501174"><a name="p15599501174"></a><a name="p15599501174"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p106116501573"><a name="p106116501573"></a><a name="p106116501573"></a>插件安装参数</p>
</td>
</tr>
<tr id="row4507504714"><td class="cellrowborder" valign="top" width="16.050000000000004%" headers="mcps1.2.5.1.1 "><p id="p146255018711"><a name="p146255018711"></a><a name="p146255018711"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.2 "><p id="p1680751581018"><a name="p1680751581018"></a><a name="p1680751581018"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p206495016712"><a name="p206495016712"></a><a name="p206495016712"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p1365450377"><a name="p1365450377"></a><a name="p1365450377"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row1150550472"><td class="cellrowborder" valign="top" width="16.050000000000004%" headers="mcps1.2.5.1.1 "><p id="p106619502710"><a name="p106619502710"></a><a name="p106619502710"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.2 "><p id="p880719152107"><a name="p880719152107"></a><a name="p880719152107"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p15678508719"><a name="p15678508719"></a><a name="p15678508719"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p9681507720"><a name="p9681507720"></a><a name="p9681507720"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row55011501272"><td class="cellrowborder" valign="top" width="16.050000000000004%" headers="mcps1.2.5.1.1 "><p id="p1696504714"><a name="p1696504714"></a><a name="p1696504714"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.2 "><p id="p17808161512103"><a name="p17808161512103"></a><a name="p17808161512103"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p1270150372"><a name="p1270150372"></a><a name="p1270150372"></a>Array of <a href="#supportVersions">supportVersions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p177120506710"><a name="p177120506710"></a><a name="p177120506710"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row12508509714"><td class="cellrowborder" valign="top" width="16.050000000000004%" headers="mcps1.2.5.1.1 "><p id="p19724502713"><a name="p19724502713"></a><a name="p19724502713"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.2 "><p id="p128085153107"><a name="p128085153107"></a><a name="p128085153107"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p47210503718"><a name="p47210503718"></a><a name="p47210503718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p8742504712"><a name="p8742504712"></a><a name="p8742504712"></a>创建时间</p>
</td>
</tr>
<tr id="row35019508710"><td class="cellrowborder" valign="top" width="16.050000000000004%" headers="mcps1.2.5.1.1 "><p id="p27410501271"><a name="p27410501271"></a><a name="p27410501271"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.2 "><p id="p19808151511104"><a name="p19808151511104"></a><a name="p19808151511104"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p1075195010710"><a name="p1075195010710"></a><a name="p1075195010710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p9820500716"><a name="p9820500716"></a><a name="p9820500716"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 6**  supportVersions

<a name="table118365013717"></a>
<table><thead align="left"><tr id="row785850172"><th class="cellrowborder" valign="top" width="17.46%" id="mcps1.2.5.1.1"><p id="p19896505715"><a name="p19896505715"></a><a name="p19896505715"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.669999999999998%" id="mcps1.2.5.1.2"><p id="p115931101020"><a name="p115931101020"></a><a name="p115931101020"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="14.92%" id="mcps1.2.5.1.3"><p id="p18975017712"><a name="p18975017712"></a><a name="p18975017712"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p189175013716"><a name="p189175013716"></a><a name="p189175013716"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row28555010717"><td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.5.1.1 "><p id="p19418506720"><a name="p19418506720"></a><a name="p19418506720"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="16.669999999999998%" headers="mcps1.2.5.1.2 "><p id="p7157338101016"><a name="p7157338101016"></a><a name="p7157338101016"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.92%" headers="mcps1.2.5.1.3 "><p id="p1996195013717"><a name="p1996195013717"></a><a name="p1996195013717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p9980501873"><a name="p9980501873"></a><a name="p9980501873"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row4856500714"><td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.5.1.1 "><p id="p59919507710"><a name="p59919507710"></a><a name="p59919507710"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.669999999999998%" headers="mcps1.2.5.1.2 "><p id="p4157238141013"><a name="p4157238141013"></a><a name="p4157238141013"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.92%" headers="mcps1.2.5.1.3 "><p id="p131001850071"><a name="p131001850071"></a><a name="p131001850071"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1110212502070"><a name="p1110212502070"></a><a name="p1110212502070"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 7**  metadata

<a name="metadata"></a>
<table><thead align="left"><tr id="row161054501871"><th class="cellrowborder" valign="top" width="17.57%" id="mcps1.2.5.1.1"><p id="p811412504712"><a name="p811412504712"></a><a name="p811412504712"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.41%" id="mcps1.2.5.1.2"><p id="p12514717101"><a name="p12514717101"></a><a name="p12514717101"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.07%" id="mcps1.2.5.1.3"><p id="p8115195010716"><a name="p8115195010716"></a><a name="p8115195010716"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p41167503718"><a name="p41167503718"></a><a name="p41167503718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row17105150176"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p611765017716"><a name="p611765017716"></a><a name="p611765017716"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.2 "><p id="p111517553108"><a name="p111517553108"></a><a name="p111517553108"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.07%" headers="mcps1.2.5.1.3 "><p id="p71171509711"><a name="p71171509711"></a><a name="p71171509711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p191191450778"><a name="p191191450778"></a><a name="p191191450778"></a>唯一id标识</p>
</td>
</tr>
<tr id="row181054507716"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p1812065014719"><a name="p1812065014719"></a><a name="p1812065014719"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.2 "><p id="p8151145517101"><a name="p8151145517101"></a><a name="p8151145517101"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.07%" headers="mcps1.2.5.1.3 "><p id="p8121115016714"><a name="p8121115016714"></a><a name="p8121115016714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p212275013711"><a name="p212275013711"></a><a name="p212275013711"></a>插件名称</p>
</td>
</tr>
<tr id="row411011501578"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p2123650079"><a name="p2123650079"></a><a name="p2123650079"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.2 "><p id="p111511855201011"><a name="p111511855201011"></a><a name="p111511855201011"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.07%" headers="mcps1.2.5.1.3 "><p id="p87953319315"><a name="p87953319315"></a><a name="p87953319315"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p161259504719"><a name="p161259504719"></a><a name="p161259504719"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row171112050379"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p15126115015719"><a name="p15126115015719"></a><a name="p15126115015719"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.2 "><p id="p16151105520100"><a name="p16151105520100"></a><a name="p16151105520100"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.07%" headers="mcps1.2.5.1.3 "><p id="p1780761163116"><a name="p1780761163116"></a><a name="p1780761163116"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p181277503716"><a name="p181277503716"></a><a name="p181277503716"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row13111150879"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p01285509718"><a name="p01285509718"></a><a name="p01285509718"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.2 "><p id="p21511455151013"><a name="p21511455151013"></a><a name="p21511455151013"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.07%" headers="mcps1.2.5.1.3 "><p id="p9128175014711"><a name="p9128175014711"></a><a name="p9128175014711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1013119501071"><a name="p1013119501071"></a><a name="p1013119501071"></a>更新时间</p>
</td>
</tr>
<tr id="row1811118505712"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p2132115012716"><a name="p2132115012716"></a><a name="p2132115012716"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.2 "><p id="p17151105512107"><a name="p17151105512107"></a><a name="p17151105512107"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.07%" headers="mcps1.2.5.1.3 "><p id="p101335503720"><a name="p101335503720"></a><a name="p101335503720"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p16134850872"><a name="p16134850872"></a><a name="p16134850872"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

无

## 响应消息<a name="section171345501278"></a>

**响应参数：**

NA

**响应示例：**

-   状态码为 200 时

    ```
    {
        "string": "string"
    }
    ```


-   状态码为 500 时

    ```
    {
        "code": "SVCSTG.CCE-ADDONMGR.500",
        "message": "internal error"
    }
    ```


## 状态码<a name="section194651851070"></a>

**表 8**  状态码

<a name="zh-cn_topic_0079614900_table46761928"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row33254664"><th class="cellrowborder" valign="top" width="19.96%" id="mcps1.2.3.1.1"><p id="p55616028205955"><a name="p55616028205955"></a><a name="p55616028205955"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="80.04%" id="mcps1.2.3.1.2"><p id="p8604418205955"><a name="p8604418205955"></a><a name="p8604418205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row176274101210"><td class="cellrowborder" valign="top" width="19.96%" headers="mcps1.2.3.1.1 "><p id="p46285101728"><a name="p46285101728"></a><a name="p46285101728"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="80.04%" headers="mcps1.2.3.1.2 "><p id="p126288106215"><a name="p126288106215"></a><a name="p126288106215"></a>OK</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row41084259"><td class="cellrowborder" valign="top" width="19.96%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614900_p39490674"><a name="zh-cn_topic_0079614900_p39490674"></a><a name="zh-cn_topic_0079614900_p39490674"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="80.04%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614900_p44628050"><a name="zh-cn_topic_0079614900_p44628050"></a><a name="zh-cn_topic_0079614900_p44628050"></a>Internal Server Error</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section64661151176"></a>

**表 9**  错误码

<a name="table385715361349"></a>
<table><thead align="left"><tr id="row1185873614413"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p38588361040"><a name="p38588361040"></a><a name="p38588361040"></a>错误码</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p1985811362420"><a name="p1985811362420"></a><a name="p1985811362420"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p10858193619410"><a name="p10858193619410"></a><a name="p10858193619410"></a>解决方法</p>
</th>
</tr>
</thead>
<tbody><tr id="row148582361041"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1365019495711"><a name="p1365019495711"></a><a name="p1365019495711"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p1565094913719"><a name="p1565094913719"></a><a name="p1565094913719"></a>Bad request</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p7650349273"><a name="p7650349273"></a><a name="p7650349273"></a>-</p>
</td>
</tr>
<tr id="row38581736144"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p665014916713"><a name="p665014916713"></a><a name="p665014916713"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p1865118495717"><a name="p1865118495717"></a><a name="p1865118495717"></a>Authenticate failed</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p065118495717"><a name="p065118495717"></a><a name="p065118495717"></a>-</p>
</td>
</tr>
<tr id="row585818368412"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p365184916710"><a name="p365184916710"></a><a name="p365184916710"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p86513495710"><a name="p86513495710"></a><a name="p86513495710"></a>Unauthorized</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p4652124917717"><a name="p4652124917717"></a><a name="p4652124917717"></a>-</p>
</td>
</tr>
<tr id="row1085813618415"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p106521249673"><a name="p106521249673"></a><a name="p106521249673"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p265254911717"><a name="p265254911717"></a><a name="p265254911717"></a>Addon template not exist</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p13652134917713"><a name="p13652134917713"></a><a name="p13652134917713"></a>-</p>
</td>
</tr>
<tr id="row18858536844"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1765216498712"><a name="p1765216498712"></a><a name="p1765216498712"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p1065304912711"><a name="p1065304912711"></a><a name="p1065304912711"></a>Service internal error</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1065311491776"><a name="p1065311491776"></a><a name="p1065311491776"></a>-</p>
</td>
</tr>
</tbody>
</table>

