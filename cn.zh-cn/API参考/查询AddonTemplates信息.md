# 查询AddonTemplates信息<a name="cce_02_0321"></a>

## 功能介绍<a name="section1534344818715"></a>

插件模板查询接口，查询插件信息。

## URI<a name="section183455486713"></a>

GET /api/v3/addontemplates

**表 1**  Query参数

<a name="table737034819716"></a>
<table><thead align="left"><tr id="row103656481670"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p133745480717"><a name="p133745480717"></a><a name="p133745480717"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p15377144811715"><a name="p15377144811715"></a><a name="p15377144811715"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p63799489712"><a name="p63799489712"></a><a name="p63799489712"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p123801048676"><a name="p123801048676"></a><a name="p123801048676"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1836618488717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1538114813711"><a name="p1538114813711"></a><a name="p1538114813711"></a>addon_template_name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1538213482712"><a name="p1538213482712"></a><a name="p1538213482712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14383104818715"><a name="p14383104818715"></a><a name="p14383104818715"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p438454820719"><a name="p438454820719"></a><a name="p438454820719"></a>模板名称(不填：查询列表)。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section93858481877"></a>

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row17387194814717"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p139015484714"><a name="p139015484714"></a><a name="p139015484714"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p239154815711"><a name="p239154815711"></a><a name="p239154815711"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p13934486714"><a name="p13934486714"></a><a name="p13934486714"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p2039412481576"><a name="p2039412481576"></a><a name="p2039412481576"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row13889481075"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p13953487714"><a name="p13953487714"></a><a name="p13953487714"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p4395174816712"><a name="p4395174816712"></a><a name="p4395174816712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p183969486713"><a name="p183969486713"></a><a name="p183969486713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p939684816716"><a name="p939684816716"></a><a name="p939684816716"></a>消息体的类型（格式），下方类型可任选其一使用：</p>
<p id="p1239654812717"><a name="p1239654812717"></a><a name="p1239654812717"></a>application/json;charset=utf-8</p>
<p id="p1839715481977"><a name="p1839715481977"></a><a name="p1839715481977"></a>application/json</p>
</td>
</tr>
<tr id="row1938810483710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1739716481277"><a name="p1739716481277"></a><a name="p1739716481277"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2039874819715"><a name="p2039874819715"></a><a name="p2039874819715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p9399194813713"><a name="p9399194813713"></a><a name="p9399194813713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p11400144812715"><a name="p11400144812715"></a><a name="p11400144812715"></a>在华为云上调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section040116481479"></a>

状态码为 200 时:

**表 3**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row1340515482711"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p11408174812712"><a name="p11408174812712"></a><a name="p11408174812712"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p2040917481573"><a name="p2040917481573"></a><a name="p2040917481573"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p10409174813715"><a name="p10409174813715"></a><a name="p10409174813715"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1410184814714"><a name="p1410184814714"></a><a name="p1410184814714"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row040511487711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p241110481374"><a name="p241110481374"></a><a name="p241110481374"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p5411144816717"><a name="p5411144816717"></a><a name="p5411144816717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p134121648871"><a name="p134121648871"></a><a name="p134121648871"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1841216488711"><a name="p1841216488711"></a><a name="p1841216488711"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row154053481470"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1641313485710"><a name="p1641313485710"></a><a name="p1641313485710"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p64135482718"><a name="p64135482718"></a><a name="p64135482718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1041420483716"><a name="p1041420483716"></a><a name="p1041420483716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p10416848774"><a name="p10416848774"></a><a name="p10416848774"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row1840612480712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p341718481978"><a name="p341718481978"></a><a name="p341718481978"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p104191481879"><a name="p104191481879"></a><a name="p104191481879"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p114202048271"><a name="p114202048271"></a><a name="p114202048271"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1642115481775"><a name="p1642115481775"></a><a name="p1642115481775"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row84065482073"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p542218481571"><a name="p542218481571"></a><a name="p542218481571"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p74239481874"><a name="p74239481874"></a><a name="p74239481874"></a>Array of <a href="#response_addontemplate">addontemplate</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1642410481074"><a name="p1642410481074"></a><a name="p1642410481074"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p10425104817719"><a name="p10425104817719"></a><a name="p10425104817719"></a>插件模板列表</p>
</td>
</tr>
</tbody>
</table>

**表 4**  addontemplate

<a name="response_addontemplate"></a>
<table><thead align="left"><tr id="row44291348170"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p543310484712"><a name="p543310484712"></a><a name="p543310484712"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p13434448376"><a name="p13434448376"></a><a name="p13434448376"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p184351848671"><a name="p184351848671"></a><a name="p184351848671"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p124368489711"><a name="p124368489711"></a><a name="p124368489711"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row643064813711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2043764815713"><a name="p2043764815713"></a><a name="p2043764815713"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1437748272"><a name="p1437748272"></a><a name="p1437748272"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p84386481971"><a name="p84386481971"></a><a name="p84386481971"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p164384486720"><a name="p164384486720"></a><a name="p164384486720"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row1243018486713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p114391048472"><a name="p114391048472"></a><a name="p114391048472"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1843917489718"><a name="p1843917489718"></a><a name="p1843917489718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14402483715"><a name="p14402483715"></a><a name="p14402483715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1744110482718"><a name="p1744110482718"></a><a name="p1744110482718"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row164301848678"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p244214489711"><a name="p244214489711"></a><a name="p244214489711"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14436484714"><a name="p14436484714"></a><a name="p14436484714"></a><a href="#response_metadata">metadata</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p2044424812717"><a name="p2044424812717"></a><a name="p2044424812717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p8445548477"><a name="p8445548477"></a><a name="p8445548477"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row154311848276"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p444620481772"><a name="p444620481772"></a><a name="p444620481772"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p174465481719"><a name="p174465481719"></a><a name="p174465481719"></a><a href="#response_templatespec">templatespec</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p64470486718"><a name="p64470486718"></a><a name="p64470486718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p94487481076"><a name="p94487481076"></a><a name="p94487481076"></a>spec是集合类的元素类型，内容为插件模板具体信息，插件模板的详细描述主体部分都在spec中给出</p>
</td>
</tr>
</tbody>
</table>

**表 5**  templatespec

<a name="response_templatespec"></a>
<table><thead align="left"><tr id="row154538481711"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p2459194811717"><a name="p2459194811717"></a><a name="p2459194811717"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p14600486720"><a name="p14600486720"></a><a name="p14600486720"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p4461114813715"><a name="p4461114813715"></a><a name="p4461114813715"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1246211481575"><a name="p1246211481575"></a><a name="p1246211481575"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row20453104810711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p746315482070"><a name="p746315482070"></a><a name="p746315482070"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p124656481975"><a name="p124656481975"></a><a name="p124656481975"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p174653481711"><a name="p174653481711"></a><a name="p174653481711"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p14466184816713"><a name="p14466184816713"></a><a name="p14466184816713"></a>模板类型（helm，static）</p>
</td>
</tr>
<tr id="row6454848176"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p7467548678"><a name="p7467548678"></a><a name="p7467548678"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p84680481171"><a name="p84680481171"></a><a name="p84680481171"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p18469134817717"><a name="p18469134817717"></a><a name="p18469134817717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p846914481377"><a name="p846914481377"></a><a name="p846914481377"></a>模板所属分组</p>
</td>
</tr>
<tr id="row34546481171"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p94701448379"><a name="p94701448379"></a><a name="p94701448379"></a>logoURL</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p114701248473"><a name="p114701248473"></a><a name="p114701248473"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14471154815710"><a name="p14471154815710"></a><a name="p14471154815710"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p847224819712"><a name="p847224819712"></a><a name="p847224819712"></a>Logo图片地址</p>
</td>
</tr>
<tr id="row194551748672"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p047314481714"><a name="p047314481714"></a><a name="p047314481714"></a>readmeURL</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p154733481274"><a name="p154733481274"></a><a name="p154733481274"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p8474348573"><a name="p8474348573"></a><a name="p8474348573"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p44741488717"><a name="p44741488717"></a><a name="p44741488717"></a>Logo图片地址</p>
</td>
</tr>
<tr id="row11455134819720"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18475174810717"><a name="p18475174810717"></a><a name="p18475174810717"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p12476748575"><a name="p12476748575"></a><a name="p12476748575"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p2476204818720"><a name="p2476204818720"></a><a name="p2476204818720"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p44772487718"><a name="p44772487718"></a><a name="p44772487718"></a>模板描述</p>
</td>
</tr>
<tr id="row154554485719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p847834811720"><a name="p847834811720"></a><a name="p847834811720"></a>versions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p447815488717"><a name="p447815488717"></a><a name="p447815488717"></a>Array of <a href="#response_versions">versions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p247916488719"><a name="p247916488719"></a><a name="p247916488719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p104802481873"><a name="p104802481873"></a><a name="p104802481873"></a>模板具体版本详情</p>
</td>
</tr>
<tr id="row1145518487710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p548384811711"><a name="p548384811711"></a><a name="p548384811711"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1148420483714"><a name="p1148420483714"></a><a name="p1148420483714"></a>Array of <a href="#response_supportVersions">supportVersions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1548415486717"><a name="p1548415486717"></a><a name="p1548415486717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p848514487719"><a name="p848514487719"></a><a name="p848514487719"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row3456114813713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p5485134814710"><a name="p5485134814710"></a><a name="p5485134814710"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1448616481679"><a name="p1448616481679"></a><a name="p1448616481679"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p24868481978"><a name="p24868481978"></a><a name="p24868481978"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1348713481374"><a name="p1348713481374"></a><a name="p1348713481374"></a>创建时间</p>
</td>
</tr>
<tr id="row9456948475"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18488164818711"><a name="p18488164818711"></a><a name="p18488164818711"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p54891648370"><a name="p54891648370"></a><a name="p54891648370"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p048915482716"><a name="p048915482716"></a><a name="p048915482716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p8490114812717"><a name="p8490114812717"></a><a name="p8490114812717"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 6**  supportVersions

<a name="response_supportVersions"></a>
<table><thead align="left"><tr id="row2492144815716"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p349574812720"><a name="p349574812720"></a><a name="p349574812720"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p164951482713"><a name="p164951482713"></a><a name="p164951482713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p749615485720"><a name="p749615485720"></a><a name="p749615485720"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p249620488715"><a name="p249620488715"></a><a name="p249620488715"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row154934480713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1849715481715"><a name="p1849715481715"></a><a name="p1849715481715"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p104971448375"><a name="p104971448375"></a><a name="p104971448375"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p94988481576"><a name="p94988481576"></a><a name="p94988481576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p104991481572"><a name="p104991481572"></a><a name="p104991481572"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row1849315487718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p164991648477"><a name="p164991648477"></a><a name="p164991648477"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p125001448476"><a name="p125001448476"></a><a name="p125001448476"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p115002486714"><a name="p115002486714"></a><a name="p115002486714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p15017487716"><a name="p15017487716"></a><a name="p15017487716"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 7**  versions

<a name="response_versions"></a>
<table><thead align="left"><tr id="row25033482076"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1751394812714"><a name="p1751394812714"></a><a name="p1751394812714"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1251315481471"><a name="p1251315481471"></a><a name="p1251315481471"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p8514348575"><a name="p8514348575"></a><a name="p8514348575"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p651524811718"><a name="p651524811718"></a><a name="p651524811718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1950510481713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p15151481575"><a name="p15151481575"></a><a name="p15151481575"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1516164814715"><a name="p1516164814715"></a><a name="p1516164814715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p115161148377"><a name="p115161148377"></a><a name="p115161148377"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p16517648271"><a name="p16517648271"></a><a name="p16517648271"></a>插件版本号</p>
</td>
</tr>
<tr id="row17505114811710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p85188481370"><a name="p85188481370"></a><a name="p85188481370"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p45194481574"><a name="p45194481574"></a><a name="p45194481574"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p13520134820714"><a name="p13520134820714"></a><a name="p13520134820714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p13520548179"><a name="p13520548179"></a><a name="p13520548179"></a>插件安装参数</p>
</td>
</tr>
<tr id="row1050614483713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p14522124819716"><a name="p14522124819716"></a><a name="p14522124819716"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1523448979"><a name="p1523448979"></a><a name="p1523448979"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p752414817719"><a name="p752414817719"></a><a name="p752414817719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p105241848370"><a name="p105241848370"></a><a name="p105241848370"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row1950654811719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p35250481077"><a name="p35250481077"></a><a name="p35250481077"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1652712481373"><a name="p1652712481373"></a><a name="p1652712481373"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p175281348674"><a name="p175281348674"></a><a name="p175281348674"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1852824812712"><a name="p1852824812712"></a><a name="p1852824812712"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row1250712481677"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1852912482716"><a name="p1852912482716"></a><a name="p1852912482716"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p175294482715"><a name="p175294482715"></a><a name="p175294482715"></a>Array of <a href="#response_supportVersions">supportVersions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p19530104817713"><a name="p19530104817713"></a><a name="p19530104817713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p553115485720"><a name="p553115485720"></a><a name="p553115485720"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row1950716485719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1153115483716"><a name="p1153115483716"></a><a name="p1153115483716"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p85323486713"><a name="p85323486713"></a><a name="p85323486713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p5533148279"><a name="p5533148279"></a><a name="p5533148279"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1553416484710"><a name="p1553416484710"></a><a name="p1553416484710"></a>创建时间</p>
</td>
</tr>
<tr id="row105081481473"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p55352048275"><a name="p55352048275"></a><a name="p55352048275"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p15536184820711"><a name="p15536184820711"></a><a name="p15536184820711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p653618481273"><a name="p653618481273"></a><a name="p653618481273"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1953717481674"><a name="p1953717481674"></a><a name="p1953717481674"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 8**  supportVersions

<a name="table1253774812710"></a>
<table><thead align="left"><tr id="row1653917481177"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p125421348677"><a name="p125421348677"></a><a name="p125421348677"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1954414814715"><a name="p1954414814715"></a><a name="p1954414814715"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p105453487716"><a name="p105453487716"></a><a name="p105453487716"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p154634819713"><a name="p154634819713"></a><a name="p154634819713"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row45403483711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p3547248473"><a name="p3547248473"></a><a name="p3547248473"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1354884814713"><a name="p1354884814713"></a><a name="p1354884814713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p155508484715"><a name="p155508484715"></a><a name="p155508484715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p125511648172"><a name="p125511648172"></a><a name="p125511648172"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row6540164820717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1955316485710"><a name="p1955316485710"></a><a name="p1955316485710"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p655412480719"><a name="p655412480719"></a><a name="p655412480719"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p45558489718"><a name="p45558489718"></a><a name="p45558489718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p85557481775"><a name="p85557481775"></a><a name="p85557481775"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 9**  metadata

<a name="response_metadata"></a>
<table><thead align="left"><tr id="row125591948576"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1356364810718"><a name="p1356364810718"></a><a name="p1356364810718"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p115643481176"><a name="p115643481176"></a><a name="p115643481176"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p25656481711"><a name="p25656481711"></a><a name="p25656481711"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p135656484714"><a name="p135656484714"></a><a name="p135656484714"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1556074816713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p135661748372"><a name="p135661748372"></a><a name="p135661748372"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p105671148576"><a name="p105671148576"></a><a name="p105671148576"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1756874817720"><a name="p1756874817720"></a><a name="p1756874817720"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p165681148774"><a name="p165681148774"></a><a name="p165681148774"></a>唯一id标识</p>
</td>
</tr>
<tr id="row456014481711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p25691248577"><a name="p25691248577"></a><a name="p25691248577"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p957014811716"><a name="p957014811716"></a><a name="p957014811716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p657019489717"><a name="p657019489717"></a><a name="p657019489717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1357118481978"><a name="p1357118481978"></a><a name="p1357118481978"></a>插件名称</p>
</td>
</tr>
<tr id="row156016481373"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p25711348772"><a name="p25711348772"></a><a name="p25711348772"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p957220481473"><a name="p957220481473"></a><a name="p957220481473"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p19573194820718"><a name="p19573194820718"></a><a name="p19573194820718"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p7574184815711"><a name="p7574184815711"></a><a name="p7574184815711"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row1556017486718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1627174919717"><a name="p1627174919717"></a><a name="p1627174919717"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p862812498713"><a name="p862812498713"></a><a name="p862812498713"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p7628104911715"><a name="p7628104911715"></a><a name="p7628104911715"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p16281449173"><a name="p16281449173"></a><a name="p16281449173"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row1561184817713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p662854913714"><a name="p662854913714"></a><a name="p662854913714"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p46281949777"><a name="p46281949777"></a><a name="p46281949777"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p16281549975"><a name="p16281549975"></a><a name="p16281549975"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p46283491473"><a name="p46283491473"></a><a name="p46283491473"></a>更新时间</p>
</td>
</tr>
<tr id="row145611748972"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p36281249771"><a name="p36281249771"></a><a name="p36281249771"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p562814919715"><a name="p562814919715"></a><a name="p562814919715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1629154912712"><a name="p1629154912712"></a><a name="p1629154912712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p106291491677"><a name="p106291491677"></a><a name="p106291491677"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section46293491976"></a>

无

## 响应示例<a name="section763044910717"></a>

状态码为 200 时:

```
{
	"apiVersion":"v3",
	"kind":"Addon",
	"items":[
		{
			"metadata":{
				"uid":"web-terminal",
				"name":"web-terminal",
				"creationTimestamp":"2019-01-07T13:22:48Z",
				"updateTimestamp":"2019-03-28T06:52:58Z"
			},
			"apiVersion":"v3",
			"kind":"Addon",
			"spec":{
				"readmeURL":"https://192.149.48.66/cce-addon-southchina-y24tcmvhzg1l/web-terminalcn-readme.md##https://192.149.48.66/cce-addon-southchina-zw4tcmvhzg1l/web-terminalen-readme.md",
				"versions":[
					{
						"input":{
							"basic":{
								"swr_user":"hwofficial",
								"euleros_version":"2.2.5",
								"swr_addr":"100.125.6.246:20202"
							},
							"parameters":{
								"flavor1":{
									"replicas":1,
									"name":"Single",
									"description":"Has only one instance",
									"resources":[
										{
											"limitsCpu":"200m",
											"name":"web-terminal",
											"limitsMem":"512Mi",
											"requestsMem":"256Mi",
											"requestsCpu":"100m"
										}
									]
								},
								"custom":{
									"password":"hwcloud_cce"
								}
							}
						},
						"stable":true,
						"supportVersions":[
							{
								"clusterType":"VirtualMachine",
								"clusterVersion":[
									"v1.(9|11).*"
								]
							},
							{
								"clusterType":"BareMetal",
								"clusterVersion":[
									"v1.(9|11).*"
								]
							}
						],
						"creationTimestamp":"2019-01-07T13:22:48Z",
						"version":"1.0.0",
						"translate":{
							"en_US":{
								"addon":{
									"changeLog":"none",
									"description":"A plug-in that allows users to run kubectl commands using a web browser."
								},
								"description":{
									"Parameters.flavor1.name":"Single",
									"Parameters.flavor1.description":"Deploy with one instance"
								},
								"key":{
									"Parameters.custom.password":"password"
								}
							},
							"zh_CN":{
								"addon":{
									"changeLog":"无",
									"description":"一款支持在web界面上使用kubectl的插件。"
								},
								"description":{
									"Parameters.flavor1.name":"单实例",
									"Parameters.flavor1.description":"单实例部署"
								},
								"key":{
									"Parameters.custom.password":"密码"
								}
							}
						},
						"updateTimestamp":"2019-02-22T07:01:16Z"
					},
					{
						"input":{
							"basic":{
								"rbac_enabled":true,
								"swr_user":"hwofficial",
								"euleros_version":"2.2.5",
								"swr_addr":"100.125.6.246:20202"
							},
							"parameters":{
								"flavor1":{
									"replicas":1,
									"name":"Single",
									"description":"Has only one instance",
									"resources":[
										{
											"limitsCpu":"200m",
											"name":"web-terminal",
											"limitsMem":"512Mi",
											"requestsMem":"256Mi",
											"requestsCpu":"100m"
										}
									]
								},
								"custom":{
									"serviceType":"NodePort",
									"password":"hwcloud_cce",
									"loadBalancerIP":"127.0.0.1",
									"port":3000,
									"elbID":0,
									"elbClass":"union",
									"targetPort":3000
								}
							}
						},
						"stable":true,
						"supportVersions":[
							{
								"clusterType":"VirtualMachine",
								"clusterVersion":[
									"v1.(9|11).*"
								]
							},
							{
								"clusterType":"BareMetal",
								"clusterVersion":[
									"v1.(9|11).*"
								]
							}
						],
						"creationTimestamp":"2019-03-28T06:52:57Z",
						"version":"1.0.1",
						"translate":{
							"en_US":{
								"addon":{
									"changeLog":"1.include service creation  2.simplify operation  3.support access via elb",
									"description":"A plug-in that allows users to run kubectl commands using a web browser."
								},
								"description":{
									"Parameters.custom.serviceType":"Service type for accessing web-terminal",
									"Parameters.flavor1.name":"Single",
									"Parameters.flavor1.description":"Deploy with one instance"
								},
								"key":{
									"Parameters.custom.serviceType":"Access type"
								}
							},
							"zh_CN":{
								"addon":{
									"changeLog":"1.包含service创建  2.操作简化  3.支持通过elb访问",
									"description":"一款支持在web界面上使用kubectl的插件。"
								},
								"description":{
									"Parameters.custom.serviceType":"访问web-terminal的service类型",
									"Parameters.flavor1.name":"单实例",
									"Parameters.flavor1.description":"单实例部署"
								},
								"key":{
									"Parameters.custom.serviceType":"访问类型"
								}
							}
						},
						"updateTimestamp":"2019-03-28T06:52:57Z"
					}
				],
				"description":"A plug-in that allows users to run kubectl commands using a web browser.",
				"type":"helm",
				"logoURL":"https://192.149.48.66/cce-addon-southchina-aw1hz2u/web-terminallogo.svg",
				"labels":[
					"Maintenance"
				]
			}
		}
	]
}
```

状态码为 500 时:

```
{
	"code":"SVCSTG.CCE-ADDONMGR.500",
	"message":"Internal error"
}
```

## 返回值<a name="section764810491714"></a>

<a name="table5"></a>
<table><thead align="left"><tr id="row1865713481370"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p0648649173"><a name="p0648649173"></a><a name="p0648649173"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p156484491171"><a name="p156484491171"></a><a name="p156484491171"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row0657748076"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p146480497718"><a name="p146480497718"></a><a name="p146480497718"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p106481493716"><a name="p106481493716"></a><a name="p106481493716"></a>OK</p>
</td>
</tr>
<tr id="row36575481376"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p364914916715"><a name="p364914916715"></a><a name="p364914916715"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p126491949271"><a name="p126491949271"></a><a name="p126491949271"></a>Internal Server Error</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section36491499714"></a>

<a name="table6"></a>
<table><thead align="left"><tr id="row1666416481772"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.5.1.1"><p id="p136491549970"><a name="p136491549970"></a><a name="p136491549970"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.2"><p id="p11649134912716"><a name="p11649134912716"></a><a name="p11649134912716"></a>错误码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.3"><p id="p36491449679"><a name="p36491449679"></a><a name="p36491449679"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="35%" id="mcps1.1.5.1.4"><p id="p165018493711"><a name="p165018493711"></a><a name="p165018493711"></a>解决方案</p>
</th>
</tr>
</thead>
<tbody><tr id="row176641481372"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p166505495715"><a name="p166505495715"></a><a name="p166505495715"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1365019495711"><a name="p1365019495711"></a><a name="p1365019495711"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1565094913719"><a name="p1565094913719"></a><a name="p1565094913719"></a>Bad request</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row10664114817719"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p176507493712"><a name="p176507493712"></a><a name="p176507493712"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p665014916713"><a name="p665014916713"></a><a name="p665014916713"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1865118495717"><a name="p1865118495717"></a><a name="p1865118495717"></a>Authenticate failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row96659481979"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p86511249472"><a name="p86511249472"></a><a name="p86511249472"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p365184916710"><a name="p365184916710"></a><a name="p365184916710"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p86513495710"><a name="p86513495710"></a><a name="p86513495710"></a>Unauthorized</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row866514487715"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p365216494711"><a name="p365216494711"></a><a name="p365216494711"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p106521249673"><a name="p106521249673"></a><a name="p106521249673"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p265254911717"><a name="p265254911717"></a><a name="p265254911717"></a>Addon template not exist</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row12665048271"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p15652949676"><a name="p15652949676"></a><a name="p15652949676"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1765216498712"><a name="p1765216498712"></a><a name="p1765216498712"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1065304912711"><a name="p1065304912711"></a><a name="p1065304912711"></a>Service internal error</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
</tbody>
</table>

