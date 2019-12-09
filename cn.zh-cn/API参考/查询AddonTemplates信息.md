# 查询AddonTemplates信息<a name="cce_02_0321"></a>

## 功能描述<a name="section1534344818715"></a>

插件模板查询接口，查询插件信息。

## URI<a name="section183455486713"></a>

GET /api/v3/addontemplates

**表 1**  Query参数

<a name="table737034819716"></a>
<table><thead align="left"><tr id="row103656481670"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p133745480717"><a name="p133745480717"></a><a name="p133745480717"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.51%" id="mcps1.2.5.1.2"><p id="p616414954511"><a name="p616414954511"></a><a name="p616414954511"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.160000000000002%" id="mcps1.2.5.1.3"><p id="p15377144811715"><a name="p15377144811715"></a><a name="p15377144811715"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p123801048676"><a name="p123801048676"></a><a name="p123801048676"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1836618488717"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p1538114813711"><a name="p1538114813711"></a><a name="p1538114813711"></a>addon_template_name</p>
</td>
<td class="cellrowborder" valign="top" width="13.51%" headers="mcps1.2.5.1.2 "><p id="p4164991452"><a name="p4164991452"></a><a name="p4164991452"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.160000000000002%" headers="mcps1.2.5.1.3 "><p id="p1538213482712"><a name="p1538213482712"></a><a name="p1538213482712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p438454820719"><a name="p438454820719"></a><a name="p438454820719"></a>模板名称。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section93858481877"></a>

**请求参数：**

请求参数如[表2](#HeaderParameter)所示。

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row17387194814717"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p139015484714"><a name="p139015484714"></a><a name="p139015484714"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.370000000000001%" id="mcps1.2.5.1.2"><p id="p16982202524515"><a name="p16982202524515"></a><a name="p16982202524515"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.3%" id="mcps1.2.5.1.3"><p id="p239154815711"><a name="p239154815711"></a><a name="p239154815711"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p2039412481576"><a name="p2039412481576"></a><a name="p2039412481576"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13889481075"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p13953487714"><a name="p13953487714"></a><a name="p13953487714"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="15.370000000000001%" headers="mcps1.2.5.1.2 "><p id="p169938481458"><a name="p169938481458"></a><a name="p169938481458"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.3%" headers="mcps1.2.5.1.3 "><p id="p4395174816712"><a name="p4395174816712"></a><a name="p4395174816712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p939684816716"><a name="p939684816716"></a><a name="p939684816716"></a>消息体的类型（格式），下方类型可任选其一使用：</p>
<a name="ul8269121814261"></a><a name="ul8269121814261"></a><ul id="ul8269121814261"><li>application/json;charset=utf-8</li><li>application/json</li></ul>
</td>
</tr>
<tr id="row1938810483710"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p1739716481277"><a name="p1739716481277"></a><a name="p1739716481277"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="15.370000000000001%" headers="mcps1.2.5.1.2 "><p id="p1799374854514"><a name="p1799374854514"></a><a name="p1799374854514"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.3%" headers="mcps1.2.5.1.3 "><p id="p2039874819715"><a name="p2039874819715"></a><a name="p2039874819715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1679410113266"><a name="p1679410113266"></a><a name="p1679410113266"></a>调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="认证鉴权.md#section2417768214391">获取token</a>。</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

无

## 响应消息<a name="section040116481479"></a>

响应参数如[表3](#responseParameter)所示。

**表 3**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row1340515482711"><th class="cellrowborder" valign="top" width="20.03%" id="mcps1.2.5.1.1"><p id="p11408174812712"><a name="p11408174812712"></a><a name="p11408174812712"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.340000000000002%" id="mcps1.2.5.1.2"><p id="p16704155604520"><a name="p16704155604520"></a><a name="p16704155604520"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.68%" id="mcps1.2.5.1.3"><p id="p2040917481573"><a name="p2040917481573"></a><a name="p2040917481573"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p1410184814714"><a name="p1410184814714"></a><a name="p1410184814714"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row040511487711"><td class="cellrowborder" valign="top" width="20.03%" headers="mcps1.2.5.1.1 "><p id="p241110481374"><a name="p241110481374"></a><a name="p241110481374"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="15.340000000000002%" headers="mcps1.2.5.1.2 "><p id="p107041956104510"><a name="p107041956104510"></a><a name="p107041956104510"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.68%" headers="mcps1.2.5.1.3 "><p id="p5411144816717"><a name="p5411144816717"></a><a name="p5411144816717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1841216488711"><a name="p1841216488711"></a><a name="p1841216488711"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row154053481470"><td class="cellrowborder" valign="top" width="20.03%" headers="mcps1.2.5.1.1 "><p id="p1641313485710"><a name="p1641313485710"></a><a name="p1641313485710"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.340000000000002%" headers="mcps1.2.5.1.2 "><p id="p47043569455"><a name="p47043569455"></a><a name="p47043569455"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.68%" headers="mcps1.2.5.1.3 "><p id="p64135482718"><a name="p64135482718"></a><a name="p64135482718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p10416848774"><a name="p10416848774"></a><a name="p10416848774"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row1840612480712"><td class="cellrowborder" valign="top" width="20.03%" headers="mcps1.2.5.1.1 "><p id="p341718481978"><a name="p341718481978"></a><a name="p341718481978"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="15.340000000000002%" headers="mcps1.2.5.1.2 "><p id="p13704165614455"><a name="p13704165614455"></a><a name="p13704165614455"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.68%" headers="mcps1.2.5.1.3 "><p id="p104191481879"><a name="p104191481879"></a><a name="p104191481879"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1642115481775"><a name="p1642115481775"></a><a name="p1642115481775"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row84065482073"><td class="cellrowborder" valign="top" width="20.03%" headers="mcps1.2.5.1.1 "><p id="p542218481571"><a name="p542218481571"></a><a name="p542218481571"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="15.340000000000002%" headers="mcps1.2.5.1.2 "><p id="p2070435614511"><a name="p2070435614511"></a><a name="p2070435614511"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.68%" headers="mcps1.2.5.1.3 "><p id="p695232717465"><a name="p695232717465"></a><a name="p695232717465"></a>Array of <a href="#response_addontemplate">addontemplate</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p10425104817719"><a name="p10425104817719"></a><a name="p10425104817719"></a>插件模板列表</p>
</td>
</tr>
</tbody>
</table>

**表 4**  addontemplate

<a name="response_addontemplate"></a>
<table><thead align="left"><tr id="row44291348170"><th class="cellrowborder" valign="top" width="17.051705170517053%" id="mcps1.2.5.1.1"><p id="p543310484712"><a name="p543310484712"></a><a name="p543310484712"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.391539153915392%" id="mcps1.2.5.1.2"><p id="p15337121294718"><a name="p15337121294718"></a><a name="p15337121294718"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.6016601660166%" id="mcps1.2.5.1.3"><p id="p13434448376"><a name="p13434448376"></a><a name="p13434448376"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.95509550955095%" id="mcps1.2.5.1.4"><p id="p124368489711"><a name="p124368489711"></a><a name="p124368489711"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row643064813711"><td class="cellrowborder" valign="top" width="17.051705170517053%" headers="mcps1.2.5.1.1 "><p id="p2043764815713"><a name="p2043764815713"></a><a name="p2043764815713"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="15.391539153915392%" headers="mcps1.2.5.1.2 "><p id="p1338171284713"><a name="p1338171284713"></a><a name="p1338171284713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.6016601660166%" headers="mcps1.2.5.1.3 "><p id="p1437748272"><a name="p1437748272"></a><a name="p1437748272"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95509550955095%" headers="mcps1.2.5.1.4 "><p id="p164384486720"><a name="p164384486720"></a><a name="p164384486720"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row1243018486713"><td class="cellrowborder" valign="top" width="17.051705170517053%" headers="mcps1.2.5.1.1 "><p id="p114391048472"><a name="p114391048472"></a><a name="p114391048472"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.391539153915392%" headers="mcps1.2.5.1.2 "><p id="p6338191204719"><a name="p6338191204719"></a><a name="p6338191204719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.6016601660166%" headers="mcps1.2.5.1.3 "><p id="p1843917489718"><a name="p1843917489718"></a><a name="p1843917489718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95509550955095%" headers="mcps1.2.5.1.4 "><p id="p1744110482718"><a name="p1744110482718"></a><a name="p1744110482718"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row164301848678"><td class="cellrowborder" valign="top" width="17.051705170517053%" headers="mcps1.2.5.1.1 "><p id="p244214489711"><a name="p244214489711"></a><a name="p244214489711"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="15.391539153915392%" headers="mcps1.2.5.1.2 "><p id="p12338812104714"><a name="p12338812104714"></a><a name="p12338812104714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.6016601660166%" headers="mcps1.2.5.1.3 "><p id="p14436484714"><a name="p14436484714"></a><a name="p14436484714"></a><a href="#response_metadata">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.95509550955095%" headers="mcps1.2.5.1.4 "><p id="p8445548477"><a name="p8445548477"></a><a name="p8445548477"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性。</p>
</td>
</tr>
<tr id="row154311848276"><td class="cellrowborder" valign="top" width="17.051705170517053%" headers="mcps1.2.5.1.1 "><p id="p444620481772"><a name="p444620481772"></a><a name="p444620481772"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="15.391539153915392%" headers="mcps1.2.5.1.2 "><p id="p733841214472"><a name="p733841214472"></a><a name="p733841214472"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.6016601660166%" headers="mcps1.2.5.1.3 "><p id="p174465481719"><a name="p174465481719"></a><a name="p174465481719"></a><a href="#response_templatespec">templatespec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.95509550955095%" headers="mcps1.2.5.1.4 "><p id="p94487481076"><a name="p94487481076"></a><a name="p94487481076"></a>spec是集合类的元素类型，内容为插件模板具体信息，插件模板的详细描述主体部分都在spec中给出。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  templatespec

<a name="response_templatespec"></a>
<table><thead align="left"><tr id="row154538481711"><th class="cellrowborder" valign="top" width="17.18%" id="mcps1.2.5.1.1"><p id="p2459194811717"><a name="p2459194811717"></a><a name="p2459194811717"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.83%" id="mcps1.2.5.1.2"><p id="p830007105012"><a name="p830007105012"></a><a name="p830007105012"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.04%" id="mcps1.2.5.1.3"><p id="p14600486720"><a name="p14600486720"></a><a name="p14600486720"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p1246211481575"><a name="p1246211481575"></a><a name="p1246211481575"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row20453104810711"><td class="cellrowborder" valign="top" width="17.18%" headers="mcps1.2.5.1.1 "><p id="p746315482070"><a name="p746315482070"></a><a name="p746315482070"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.2.5.1.2 "><p id="p530015714505"><a name="p530015714505"></a><a name="p530015714505"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.5.1.3 "><p id="p124656481975"><a name="p124656481975"></a><a name="p124656481975"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p14466184816713"><a name="p14466184816713"></a><a name="p14466184816713"></a>模板类型（helm，static）</p>
</td>
</tr>
<tr id="row6454848176"><td class="cellrowborder" valign="top" width="17.18%" headers="mcps1.2.5.1.1 "><p id="p7467548678"><a name="p7467548678"></a><a name="p7467548678"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.2.5.1.2 "><p id="p11300147155020"><a name="p11300147155020"></a><a name="p11300147155020"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.5.1.3 "><p id="p84680481171"><a name="p84680481171"></a><a name="p84680481171"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p846914481377"><a name="p846914481377"></a><a name="p846914481377"></a>模板所属分组</p>
</td>
</tr>
<tr id="row34546481171"><td class="cellrowborder" valign="top" width="17.18%" headers="mcps1.2.5.1.1 "><p id="p94701448379"><a name="p94701448379"></a><a name="p94701448379"></a>logoURL</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.2.5.1.2 "><p id="p1830027145017"><a name="p1830027145017"></a><a name="p1830027145017"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.5.1.3 "><p id="p114701248473"><a name="p114701248473"></a><a name="p114701248473"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p847224819712"><a name="p847224819712"></a><a name="p847224819712"></a>Logo图片地址</p>
</td>
</tr>
<tr id="row194551748672"><td class="cellrowborder" valign="top" width="17.18%" headers="mcps1.2.5.1.1 "><p id="p047314481714"><a name="p047314481714"></a><a name="p047314481714"></a>readmeURL</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.2.5.1.2 "><p id="p1630014718504"><a name="p1630014718504"></a><a name="p1630014718504"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.5.1.3 "><p id="p154733481274"><a name="p154733481274"></a><a name="p154733481274"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p44741488717"><a name="p44741488717"></a><a name="p44741488717"></a>Logo图片地址</p>
</td>
</tr>
<tr id="row11455134819720"><td class="cellrowborder" valign="top" width="17.18%" headers="mcps1.2.5.1.1 "><p id="p18475174810717"><a name="p18475174810717"></a><a name="p18475174810717"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.2.5.1.2 "><p id="p530015711504"><a name="p530015711504"></a><a name="p530015711504"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.5.1.3 "><p id="p12476748575"><a name="p12476748575"></a><a name="p12476748575"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p44772487718"><a name="p44772487718"></a><a name="p44772487718"></a>模板描述</p>
</td>
</tr>
<tr id="row154554485719"><td class="cellrowborder" valign="top" width="17.18%" headers="mcps1.2.5.1.1 "><p id="p847834811720"><a name="p847834811720"></a><a name="p847834811720"></a>versions</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.2.5.1.2 "><p id="p1130015735016"><a name="p1130015735016"></a><a name="p1130015735016"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.5.1.3 "><p id="p447815488717"><a name="p447815488717"></a><a name="p447815488717"></a>Array of <a href="#response_versions">versions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p104802481873"><a name="p104802481873"></a><a name="p104802481873"></a>模板具体版本详情</p>
</td>
</tr>
<tr id="row1145518487710"><td class="cellrowborder" valign="top" width="17.18%" headers="mcps1.2.5.1.1 "><p id="p548384811711"><a name="p548384811711"></a><a name="p548384811711"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.2.5.1.2 "><p id="p73001676502"><a name="p73001676502"></a><a name="p73001676502"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.5.1.3 "><p id="p1148420483714"><a name="p1148420483714"></a><a name="p1148420483714"></a>Array of <a href="#response_supportVersions">supportVersions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p848514487719"><a name="p848514487719"></a><a name="p848514487719"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row3456114813713"><td class="cellrowborder" valign="top" width="17.18%" headers="mcps1.2.5.1.1 "><p id="p5485134814710"><a name="p5485134814710"></a><a name="p5485134814710"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.2.5.1.2 "><p id="p2030017725014"><a name="p2030017725014"></a><a name="p2030017725014"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.5.1.3 "><p id="p1448616481679"><a name="p1448616481679"></a><a name="p1448616481679"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1348713481374"><a name="p1348713481374"></a><a name="p1348713481374"></a>模板创建时间</p>
</td>
</tr>
<tr id="row9456948475"><td class="cellrowborder" valign="top" width="17.18%" headers="mcps1.2.5.1.1 "><p id="p18488164818711"><a name="p18488164818711"></a><a name="p18488164818711"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.2.5.1.2 "><p id="p330018713503"><a name="p330018713503"></a><a name="p330018713503"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.5.1.3 "><p id="p54891648370"><a name="p54891648370"></a><a name="p54891648370"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p8490114812717"><a name="p8490114812717"></a><a name="p8490114812717"></a>模板更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 6**  supportVersions

<a name="response_supportVersions"></a>
<table><thead align="left"><tr id="row2492144815716"><th class="cellrowborder" valign="top" width="17.05%" id="mcps1.2.5.1.1"><p id="p349574812720"><a name="p349574812720"></a><a name="p349574812720"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.57%" id="mcps1.2.5.1.2"><p id="p2654614115011"><a name="p2654614115011"></a><a name="p2654614115011"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.43%" id="mcps1.2.5.1.3"><p id="p164951482713"><a name="p164951482713"></a><a name="p164951482713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p249620488715"><a name="p249620488715"></a><a name="p249620488715"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row154934480713"><td class="cellrowborder" valign="top" width="17.05%" headers="mcps1.2.5.1.1 "><p id="p1849715481715"><a name="p1849715481715"></a><a name="p1849715481715"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="14.57%" headers="mcps1.2.5.1.2 "><p id="p4119152585011"><a name="p4119152585011"></a><a name="p4119152585011"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.43%" headers="mcps1.2.5.1.3 "><p id="p104971448375"><a name="p104971448375"></a><a name="p104971448375"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p104991481572"><a name="p104991481572"></a><a name="p104991481572"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row1849315487718"><td class="cellrowborder" valign="top" width="17.05%" headers="mcps1.2.5.1.1 "><p id="p164991648477"><a name="p164991648477"></a><a name="p164991648477"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.57%" headers="mcps1.2.5.1.2 "><p id="p11119182510503"><a name="p11119182510503"></a><a name="p11119182510503"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.43%" headers="mcps1.2.5.1.3 "><p id="p125001448476"><a name="p125001448476"></a><a name="p125001448476"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p15017487716"><a name="p15017487716"></a><a name="p15017487716"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 7**  versions

<a name="response_versions"></a>
<table><thead align="left"><tr id="row25033482076"><th class="cellrowborder" valign="top" width="17.44%" id="mcps1.2.5.1.1"><p id="p1751394812714"><a name="p1751394812714"></a><a name="p1751394812714"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.2%" id="mcps1.2.5.1.2"><p id="p345523212504"><a name="p345523212504"></a><a name="p345523212504"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.6%" id="mcps1.2.5.1.3"><p id="p1251315481471"><a name="p1251315481471"></a><a name="p1251315481471"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.76%" id="mcps1.2.5.1.4"><p id="p651524811718"><a name="p651524811718"></a><a name="p651524811718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1950510481713"><td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.1 "><p id="p15151481575"><a name="p15151481575"></a><a name="p15151481575"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="19.2%" headers="mcps1.2.5.1.2 "><p id="p452065215013"><a name="p452065215013"></a><a name="p452065215013"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.6%" headers="mcps1.2.5.1.3 "><p id="p1516164814715"><a name="p1516164814715"></a><a name="p1516164814715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.76%" headers="mcps1.2.5.1.4 "><p id="p16517648271"><a name="p16517648271"></a><a name="p16517648271"></a>插件版本号</p>
</td>
</tr>
<tr id="row17505114811710"><td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.1 "><p id="p85188481370"><a name="p85188481370"></a><a name="p85188481370"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="19.2%" headers="mcps1.2.5.1.2 "><p id="p15216525507"><a name="p15216525507"></a><a name="p15216525507"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.6%" headers="mcps1.2.5.1.3 "><p id="p45194481574"><a name="p45194481574"></a><a name="p45194481574"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="43.76%" headers="mcps1.2.5.1.4 "><p id="p13520548179"><a name="p13520548179"></a><a name="p13520548179"></a>插件安装参数</p>
</td>
</tr>
<tr id="row1050614483713"><td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.1 "><p id="p14522124819716"><a name="p14522124819716"></a><a name="p14522124819716"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="19.2%" headers="mcps1.2.5.1.2 "><p id="p9521105215012"><a name="p9521105215012"></a><a name="p9521105215012"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.6%" headers="mcps1.2.5.1.3 "><p id="p1523448979"><a name="p1523448979"></a><a name="p1523448979"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="43.76%" headers="mcps1.2.5.1.4 "><p id="p105241848370"><a name="p105241848370"></a><a name="p105241848370"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row1950654811719"><td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.1 "><p id="p35250481077"><a name="p35250481077"></a><a name="p35250481077"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="19.2%" headers="mcps1.2.5.1.2 "><p id="p11521115245011"><a name="p11521115245011"></a><a name="p11521115245011"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.6%" headers="mcps1.2.5.1.3 "><p id="p1652712481373"><a name="p1652712481373"></a><a name="p1652712481373"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="43.76%" headers="mcps1.2.5.1.4 "><p id="p1852824812712"><a name="p1852824812712"></a><a name="p1852824812712"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row1250712481677"><td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.1 "><p id="p1852912482716"><a name="p1852912482716"></a><a name="p1852912482716"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="19.2%" headers="mcps1.2.5.1.2 "><p id="p7521952145010"><a name="p7521952145010"></a><a name="p7521952145010"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.6%" headers="mcps1.2.5.1.3 "><p id="p175294482715"><a name="p175294482715"></a><a name="p175294482715"></a>Array of <a href="#response_supportVersions">supportVersions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="43.76%" headers="mcps1.2.5.1.4 "><p id="p553115485720"><a name="p553115485720"></a><a name="p553115485720"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row1950716485719"><td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.1 "><p id="p1153115483716"><a name="p1153115483716"></a><a name="p1153115483716"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="19.2%" headers="mcps1.2.5.1.2 "><p id="p13521175265010"><a name="p13521175265010"></a><a name="p13521175265010"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="19.6%" headers="mcps1.2.5.1.3 "><p id="p85323486713"><a name="p85323486713"></a><a name="p85323486713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.76%" headers="mcps1.2.5.1.4 "><p id="p1553416484710"><a name="p1553416484710"></a><a name="p1553416484710"></a>插件创建时间</p>
</td>
</tr>
<tr id="row105081481473"><td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.1 "><p id="p55352048275"><a name="p55352048275"></a><a name="p55352048275"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="19.2%" headers="mcps1.2.5.1.2 "><p id="p1521115255016"><a name="p1521115255016"></a><a name="p1521115255016"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.6%" headers="mcps1.2.5.1.3 "><p id="p15536184820711"><a name="p15536184820711"></a><a name="p15536184820711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.76%" headers="mcps1.2.5.1.4 "><p id="p1953717481674"><a name="p1953717481674"></a><a name="p1953717481674"></a>插件更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 8**  supportVersions

<a name="table1253774812710"></a>
<table><thead align="left"><tr id="row1653917481177"><th class="cellrowborder" valign="top" width="15.89%" id="mcps1.2.5.1.1"><p id="p125421348677"><a name="p125421348677"></a><a name="p125421348677"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.580000000000002%" id="mcps1.2.5.1.2"><p id="p135510294516"><a name="p135510294516"></a><a name="p135510294516"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.85%" id="mcps1.2.5.1.3"><p id="p1954414814715"><a name="p1954414814715"></a><a name="p1954414814715"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="46.68%" id="mcps1.2.5.1.4"><p id="p154634819713"><a name="p154634819713"></a><a name="p154634819713"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row45403483711"><td class="cellrowborder" valign="top" width="15.89%" headers="mcps1.2.5.1.1 "><p id="p3547248473"><a name="p3547248473"></a><a name="p3547248473"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="17.580000000000002%" headers="mcps1.2.5.1.2 "><p id="p10677153775120"><a name="p10677153775120"></a><a name="p10677153775120"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.85%" headers="mcps1.2.5.1.3 "><p id="p1354884814713"><a name="p1354884814713"></a><a name="p1354884814713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="46.68%" headers="mcps1.2.5.1.4 "><p id="p125511648172"><a name="p125511648172"></a><a name="p125511648172"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row6540164820717"><td class="cellrowborder" valign="top" width="15.89%" headers="mcps1.2.5.1.1 "><p id="p1955316485710"><a name="p1955316485710"></a><a name="p1955316485710"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17.580000000000002%" headers="mcps1.2.5.1.2 "><p id="p19677133715119"><a name="p19677133715119"></a><a name="p19677133715119"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.85%" headers="mcps1.2.5.1.3 "><p id="p655412480719"><a name="p655412480719"></a><a name="p655412480719"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="46.68%" headers="mcps1.2.5.1.4 "><p id="p85557481775"><a name="p85557481775"></a><a name="p85557481775"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 9**  metadata

<a name="response_metadata"></a>
<table><thead align="left"><tr id="row125591948576"><th class="cellrowborder" valign="top" width="13.05%" id="mcps1.2.5.1.1"><p id="p1356364810718"><a name="p1356364810718"></a><a name="p1356364810718"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.620000000000001%" id="mcps1.2.5.1.2"><p id="p4961346105113"><a name="p4961346105113"></a><a name="p4961346105113"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.3"><p id="p115643481176"><a name="p115643481176"></a><a name="p115643481176"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p135656484714"><a name="p135656484714"></a><a name="p135656484714"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1556074816713"><td class="cellrowborder" valign="top" width="13.05%" headers="mcps1.2.5.1.1 "><p id="p135661748372"><a name="p135661748372"></a><a name="p135661748372"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="15.620000000000001%" headers="mcps1.2.5.1.2 "><p id="p125995511516"><a name="p125995511516"></a><a name="p125995511516"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p105671148576"><a name="p105671148576"></a><a name="p105671148576"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p165681148774"><a name="p165681148774"></a><a name="p165681148774"></a>插件唯一id标识</p>
</td>
</tr>
<tr id="row456014481711"><td class="cellrowborder" valign="top" width="13.05%" headers="mcps1.2.5.1.1 "><p id="p25691248577"><a name="p25691248577"></a><a name="p25691248577"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="15.620000000000001%" headers="mcps1.2.5.1.2 "><p id="p1595555512"><a name="p1595555512"></a><a name="p1595555512"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p957014811716"><a name="p957014811716"></a><a name="p957014811716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1357118481978"><a name="p1357118481978"></a><a name="p1357118481978"></a>插件名称</p>
</td>
</tr>
<tr id="row156016481373"><td class="cellrowborder" valign="top" width="13.05%" headers="mcps1.2.5.1.1 "><p id="p25711348772"><a name="p25711348772"></a><a name="p25711348772"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="15.620000000000001%" headers="mcps1.2.5.1.2 "><p id="p360135545117"><a name="p360135545117"></a><a name="p360135545117"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p957220481473"><a name="p957220481473"></a><a name="p957220481473"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p7574184815711"><a name="p7574184815711"></a><a name="p7574184815711"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row1556017486718"><td class="cellrowborder" valign="top" width="13.05%" headers="mcps1.2.5.1.1 "><p id="p1627174919717"><a name="p1627174919717"></a><a name="p1627174919717"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="15.620000000000001%" headers="mcps1.2.5.1.2 "><p id="p176065515111"><a name="p176065515111"></a><a name="p176065515111"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p1452116273317"><a name="p1452116273317"></a><a name="p1452116273317"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p16281449173"><a name="p16281449173"></a><a name="p16281449173"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row1561184817713"><td class="cellrowborder" valign="top" width="13.05%" headers="mcps1.2.5.1.1 "><p id="p662854913714"><a name="p662854913714"></a><a name="p662854913714"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="15.620000000000001%" headers="mcps1.2.5.1.2 "><p id="p1160175515116"><a name="p1160175515116"></a><a name="p1160175515116"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p46281949777"><a name="p46281949777"></a><a name="p46281949777"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p46283491473"><a name="p46283491473"></a><a name="p46283491473"></a>插件更新时间</p>
</td>
</tr>
<tr id="row145611748972"><td class="cellrowborder" valign="top" width="13.05%" headers="mcps1.2.5.1.1 "><p id="p36281249771"><a name="p36281249771"></a><a name="p36281249771"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="15.620000000000001%" headers="mcps1.2.5.1.2 "><p id="p660955135111"><a name="p660955135111"></a><a name="p660955135111"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p562814919715"><a name="p562814919715"></a><a name="p562814919715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p106291491677"><a name="p106291491677"></a><a name="p106291491677"></a>插件创建时间</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

-   状态码为 200 时：

    ```
    {
        "apiVersion": "v3",
        "kind": "Addon",
        "items": [
            {
                "metadata": {
                    "uid": "web-terminal",
                    "name": "web-terminal",
                    "creationTimestamp": "2019-01-07T13:22:48Z",
                    "updateTimestamp": "2019-03-28T06:52:58Z"
                },
                "apiVersion": "v3",
                "kind": "Addon",
                "spec": {
                    "readmeURL": "https://192.168.48.66/cce-addon-y24tcmvhzg1l/web-terminalcn-readme.md##https://192.168.48.66/cce-addon-zw4tcmvhzg1l/web-terminalen-readme.md",
                    "versions": [
                        {
                            "input": {
                                "basic": {
                                    "swr_user": "hwofficial",
                                    "euleros_version": "2.2.5",
                                    "swr_addr": "10.125.6.246:20202"
                                },
                                "parameters": {
                                    "flavor1": {
                                        "replicas": 1,
                                        "name": "Single",
                                        "description": "Has only one instance",
                                        "resources": [
                                            {
                                                "limitsCpu": "200m",
                                                "name": "web-terminal",
                                                "limitsMem": "512Mi",
                                                "requestsMem": "256Mi",
                                                "requestsCpu": "100m"
                                            }
                                        ]
                                    },
                                    "custom": {
                                        "password": "hwcloud_cce"
                                    }
                                }
                            },
                            "stable": true,
                            "supportVersions": [
                                {
                                    "clusterType": "VirtualMachine",
                                    "clusterVersion": [
                                        "v1.(9|11).*"
                                    ]
                                },
                                {
                                    "clusterType": "BareMetal",
                                    "clusterVersion": [
                                        "v1.(9|11).*"
                                    ]
                                }
                            ],
                            "creationTimestamp": "2019-01-07T13:22:48Z",
                            "version": "1.0.0",
                            "translate": {
                                "en_US": {
                                    "addon": {
                                        "changeLog": "none",
                                        "description": "A plug-in that allows users to run kubectl commands using a web browser."
                                    },
                                    "description": {
                                        "Parameters.flavor1.name": "Single",
                                        "Parameters.flavor1.description": "Deploy with one instance"
                                    },
                                    "key": {
                                        "Parameters.custom.password": "password"
                                    }
                                },
                                "zh_CN": {
                                    "addon": {
                                        "changeLog": "",
                                        "description": ""
                                    },
                                    "description": {
                                        "Parameters.flavor1.name": "",
                                        "Parameters.flavor1.description": ""
                                    },
                                    "key": {
                                        "Parameters.custom.password": ""
                                    }
                                }
                            },
                            "updateTimestamp": "2019-02-22T07:01:16Z"
                        },
                        {
                            "input": {
                                "basic": {
                                    "rbac_enabled": true,
                                    "swr_user": "hwofficial",
                                    "euleros_version": "2.2.5",
                                    "swr_addr": "10.125.6.246:20202"
                                },
                                "parameters": {
                                    "flavor1": {
                                        "replicas": 1,
                                        "name": "Single",
                                        "description": "Has only one instance",
                                        "resources": [
                                            {
                                                "limitsCpu": "200m",
                                                "name": "web-terminal",
                                                "limitsMem": "512Mi",
                                                "requestsMem": "256Mi",
                                                "requestsCpu": "100m"
                                            }
                                        ]
                                    },
                                    "custom": {
                                        "serviceType": "NodePort",
                                        "password": "hwcloud_cce",
                                        "loadBalancerIP": "127.0.0.1",
                                        "port": 3000,
                                        "elbID": 0,
                                        "elbClass": "union",
                                        "targetPort": 3000
                                    }
                                }
                            },
                            "stable": true,
                            "supportVersions": [
                                {
                                    "clusterType": "VirtualMachine",
                                    "clusterVersion": [
                                        "v1.(9|11).*"
                                    ]
                                },
                                {
                                    "clusterType": "BareMetal",
                                    "clusterVersion": [
                                        "v1.(9|11).*"
                                    ]
                                }
                            ],
                            "creationTimestamp": "2019-03-28T06:52:57Z",
                            "version": "1.0.1",
                            "translate": {
                                "en_US": {
                                    "addon": {
                                        "changeLog": "1.include service creation  2.simplify operation  3.support access via elb",
                                        "description": "A plug-in that allows users to run kubectl commands using a web browser."
                                    },
                                    "description": {
                                        "Parameters.custom.serviceType": "Service type for accessing web-terminal",
                                        "Parameters.flavor1.name": "Single",
                                        "Parameters.flavor1.description": "Deploy with one instance"
                                    },
                                    "key": {
                                        "Parameters.custom.serviceType": "Access type"
                                    }
                                },
                                "zh_CN": {
                                    "addon": {
                                        "changeLog": "",
                                        "description": ""
                                    },
                                    "description": {
                                        "Parameters.custom.serviceType": "",
                                        "Parameters.flavor1.name": "",
                                        "Parameters.flavor1.description": ""
                                    },
                                    "key": {
                                        "Parameters.custom.serviceType": ""
                                    }
                                }
                            },
                            "updateTimestamp": "2019-03-28T06:52:57Z"
                        }
                    ],
                    "description": "A plug-in that allows users to run kubectl commands using a web browser.",
                    "type": "helm",
                    "logoURL": "https://192.168.48.66/cce-addon-southchina-aw1hz2u/web-terminallogo.svg",
                    "labels": [
                        "Maintenance"
                    ]
                }
            }
        ]
    ```


-   状态码为 500 时：

    ```
    {
    	"code":"SVCSTG.CCE-ADDONMGR.500",
    	"message":"Internal error"
    }
    ```


## 状态码<a name="section764810491714"></a>

[表10](#zh-cn_topic_0079614900_table46761928)描述API的状态码。

**表 10**  状态码

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

## 错误码<a name="section36491499714"></a>

**表 11**  错误码

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

