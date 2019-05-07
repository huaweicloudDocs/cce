# 创建AddonInstance<a name="cce_02_0322"></a>

创建AddonInstance

## 功能介绍<a name="section592712481477"></a>

根据提供的插件模板，安装插件实例。

## URI<a name="section79287481718"></a>

POST /api/v3/addons

## 请求参数<a name="section8930154813719"></a>

**表 1**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row199321948779"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p129387486710"><a name="p129387486710"></a><a name="p129387486710"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p79381481074"><a name="p79381481074"></a><a name="p79381481074"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p1993918481712"><a name="p1993918481712"></a><a name="p1993918481712"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p15942348876"><a name="p15942348876"></a><a name="p15942348876"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row179328481172"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p89441048070"><a name="p89441048070"></a><a name="p89441048070"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1794524819715"><a name="p1794524819715"></a><a name="p1794524819715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1494514819719"><a name="p1494514819719"></a><a name="p1494514819719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1994713481677"><a name="p1994713481677"></a><a name="p1994713481677"></a>消息体的类型（格式），下方类型可任选其一使用：</p>
<p id="p1194719484712"><a name="p1194719484712"></a><a name="p1194719484712"></a>application/json;charset=utf-8</p>
<p id="p19948748875"><a name="p19948748875"></a><a name="p19948748875"></a>application/json</p>
</td>
</tr>
<tr id="row79335489710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1394920485711"><a name="p1394920485711"></a><a name="p1394920485711"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p16951948170"><a name="p16951948170"></a><a name="p16951948170"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1495294820714"><a name="p1495294820714"></a><a name="p1495294820714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p395314810714"><a name="p395314810714"></a><a name="p395314810714"></a>在华为云上调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值</p>
</td>
</tr>
</tbody>
</table>

**表 2**  请求Body参数

<a name="requestParameter"></a>
<table><thead align="left"><tr id="row119542487717"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p6958154810714"><a name="p6958154810714"></a><a name="p6958154810714"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p69592483714"><a name="p69592483714"></a><a name="p69592483714"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p39596485711"><a name="p39596485711"></a><a name="p39596485711"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p179607481978"><a name="p179607481978"></a><a name="p179607481978"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row195534816713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p159613480713"><a name="p159613480713"></a><a name="p159613480713"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p49628487711"><a name="p49628487711"></a><a name="p49628487711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p79641048972"><a name="p79641048972"></a><a name="p79641048972"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p199661648677"><a name="p199661648677"></a><a name="p199661648677"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row59554481671"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p89671048679"><a name="p89671048679"></a><a name="p89671048679"></a>apVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p18969184813710"><a name="p18969184813710"></a><a name="p18969184813710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p169701481712"><a name="p169701481712"></a><a name="p169701481712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p897024815715"><a name="p897024815715"></a><a name="p897024815715"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row99552483717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1097119489714"><a name="p1097119489714"></a><a name="p1097119489714"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p3972448871"><a name="p3972448871"></a><a name="p3972448871"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1297316486713"><a name="p1297316486713"></a><a name="p1297316486713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p7974134814712"><a name="p7974134814712"></a><a name="p7974134814712"></a>安装：固定值为{"addon.install/type":"install"}</p>
<p id="p169745481073"><a name="p169745481073"></a><a name="p169745481073"></a>升级：固定值为{"addon.upgrade/type":"upgrade"}</p>
</td>
</tr>
<tr id="row1395534813720"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p997519485712"><a name="p997519485712"></a><a name="p997519485712"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p4976174810710"><a name="p4976174810710"></a><a name="p4976174810710"></a><a href="#instancerequestspec">instancerequestspec</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p49773480717"><a name="p49773480717"></a><a name="p49773480717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p597713489716"><a name="p597713489716"></a><a name="p597713489716"></a>spec是集合类的元素类型，内容为插件实例安装/升级的具体请求信息</p>
</td>
</tr>
</tbody>
</table>

**表 3**  instancerequestspec

<a name="instancerequestspec"></a>
<table><thead align="left"><tr id="row39791448178"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p09821648578"><a name="p09821648578"></a><a name="p09821648578"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p398317488716"><a name="p398317488716"></a><a name="p398317488716"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p139849481778"><a name="p139849481778"></a><a name="p139849481778"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p09841248377"><a name="p09841248377"></a><a name="p09841248377"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row6979134816713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1698511482716"><a name="p1698511482716"></a><a name="p1698511482716"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p189852481277"><a name="p189852481277"></a><a name="p189852481277"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p49863483711"><a name="p49863483711"></a><a name="p49863483711"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p16987174816719"><a name="p16987174816719"></a><a name="p16987174816719"></a>待安装、升级插件的具体版本版本号，例如1.0.0</p>
</td>
</tr>
<tr id="row59809481715"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1898818487713"><a name="p1898818487713"></a><a name="p1898818487713"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p199888481471"><a name="p199888481471"></a><a name="p199888481471"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p139896481471"><a name="p139896481471"></a><a name="p139896481471"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1198919481710"><a name="p1198919481710"></a><a name="p1198919481710"></a>集群id</p>
</td>
</tr>
<tr id="row298084819719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p699014481574"><a name="p699014481574"></a><a name="p699014481574"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p19990144820711"><a name="p19990144820711"></a><a name="p19990144820711"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p199104819710"><a name="p199104819710"></a><a name="p199104819710"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1299216482716"><a name="p1299216482716"></a><a name="p1299216482716"></a>待安装或升级模板的具体请求参数，一般为配置文件，各插件不同</p>
</td>
</tr>
<tr id="row189802481479"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p9993104815714"><a name="p9993104815714"></a><a name="p9993104815714"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p39933485713"><a name="p39933485713"></a><a name="p39933485713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p599404810712"><a name="p599404810712"></a><a name="p599404810712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1899516487714"><a name="p1899516487714"></a><a name="p1899516487714"></a>待安装插件模板名称，如coredns</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section10996248672"></a>

状态码为 200 时:

**表 4**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row1399914481277"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p151449979"><a name="p151449979"></a><a name="p151449979"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p62049978"><a name="p62049978"></a><a name="p62049978"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p15224914716"><a name="p15224914716"></a><a name="p15224914716"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p939497717"><a name="p939497717"></a><a name="p939497717"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row139995489718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p74549672"><a name="p74549672"></a><a name="p74549672"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1951249076"><a name="p1951249076"></a><a name="p1951249076"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p17584915713"><a name="p17584915713"></a><a name="p17584915713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p864491718"><a name="p864491718"></a><a name="p864491718"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row10549478"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p271249474"><a name="p271249474"></a><a name="p271249474"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2070491873"><a name="p2070491873"></a><a name="p2070491873"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p781549270"><a name="p781549270"></a><a name="p781549270"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p591249673"><a name="p591249673"></a><a name="p591249673"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row1704497713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p191010491071"><a name="p191010491071"></a><a name="p191010491071"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p81117494719"><a name="p81117494719"></a><a name="p81117494719"></a><a href="#response_metadata">metadata</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p612114918710"><a name="p612114918710"></a><a name="p612114918710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p19131949371"><a name="p19131949371"></a><a name="p19131949371"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row30149176"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p7141449474"><a name="p7141449474"></a><a name="p7141449474"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2151049772"><a name="p2151049772"></a><a name="p2151049772"></a><a href="#response_instanceSpec">instanceSpec</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p141614491374"><a name="p141614491374"></a><a name="p141614491374"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p116154914718"><a name="p116154914718"></a><a name="p116154914718"></a>spec是集合类的元素类型，内容为插件实例具体信息，实例的详细描述主体部分都在spec中给出</p>
</td>
</tr>
<tr id="row12014492720"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p71714494710"><a name="p71714494710"></a><a name="p71714494710"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1218349175"><a name="p1218349175"></a><a name="p1218349175"></a><a href="#response_status">status</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p11854913720"><a name="p11854913720"></a><a name="p11854913720"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p21910491473"><a name="p21910491473"></a><a name="p21910491473"></a>插件实例状态</p>
</td>
</tr>
</tbody>
</table>

**表 5**  status

<a name="response_status"></a>
<table><thead align="left"><tr id="row102118492713"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1125194918720"><a name="p1125194918720"></a><a name="p1125194918720"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p92515491073"><a name="p92515491073"></a><a name="p92515491073"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p4265491779"><a name="p4265491779"></a><a name="p4265491779"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p14266491275"><a name="p14266491275"></a><a name="p14266491275"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row152234915711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p172717497719"><a name="p172717497719"></a><a name="p172717497719"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p828104910714"><a name="p828104910714"></a><a name="p828104910714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p2287492714"><a name="p2287492714"></a><a name="p2287492714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p6298492710"><a name="p6298492710"></a><a name="p6298492710"></a>插件实例状态</p>
</td>
</tr>
<tr id="row1622134914718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p123011491678"><a name="p123011491678"></a><a name="p123011491678"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p13044913719"><a name="p13044913719"></a><a name="p13044913719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p123112490713"><a name="p123112490713"></a><a name="p123112490713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p12322491715"><a name="p12322491715"></a><a name="p12322491715"></a>插件安装失败原因</p>
</td>
</tr>
<tr id="row9221049679"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p153214913718"><a name="p153214913718"></a><a name="p153214913718"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p6330491979"><a name="p6330491979"></a><a name="p6330491979"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14341491278"><a name="p14341491278"></a><a name="p14341491278"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p834049673"><a name="p834049673"></a><a name="p834049673"></a>安装错误详情</p>
</td>
</tr>
<tr id="row92213491178"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p0355491714"><a name="p0355491714"></a><a name="p0355491714"></a>targetVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p6363496720"><a name="p6363496720"></a><a name="p6363496720"></a>Array of array</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1136184913717"><a name="p1136184913717"></a><a name="p1136184913717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p93714495711"><a name="p93714495711"></a><a name="p93714495711"></a>此插件版本，支持升级的集群版本</p>
</td>
</tr>
<tr id="row22313493710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p73716491719"><a name="p73716491719"></a><a name="p73716491719"></a>currentVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p13385491275"><a name="p13385491275"></a><a name="p13385491275"></a><a href="#response_versions">versions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p113815491177"><a name="p113815491177"></a><a name="p113815491177"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p239749079"><a name="p239749079"></a><a name="p239749079"></a>当前插件实例使用的具体插件版本信息</p>
</td>
</tr>
</tbody>
</table>

**表 6**  versions

<a name="response_versions"></a>
<table><thead align="left"><tr id="row74013491973"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p13430491971"><a name="p13430491971"></a><a name="p13430491971"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p944134913719"><a name="p944134913719"></a><a name="p944134913719"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p94654917712"><a name="p94654917712"></a><a name="p94654917712"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p15472495713"><a name="p15472495713"></a><a name="p15472495713"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row5406491177"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p44713491971"><a name="p44713491971"></a><a name="p44713491971"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p548154913719"><a name="p548154913719"></a><a name="p548154913719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p9491349171"><a name="p9491349171"></a><a name="p9491349171"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p2507492070"><a name="p2507492070"></a><a name="p2507492070"></a>插件版本号</p>
</td>
</tr>
<tr id="row1541249775"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p19518491176"><a name="p19518491176"></a><a name="p19518491176"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p9517491674"><a name="p9517491674"></a><a name="p9517491674"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1152949773"><a name="p1152949773"></a><a name="p1152949773"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p17551491676"><a name="p17551491676"></a><a name="p17551491676"></a>插件安装参数</p>
</td>
</tr>
<tr id="row1413491777"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1455549171"><a name="p1455549171"></a><a name="p1455549171"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1256194917712"><a name="p1256194917712"></a><a name="p1256194917712"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p15613491371"><a name="p15613491371"></a><a name="p15613491371"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p36210491178"><a name="p36210491178"></a><a name="p36210491178"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row8412049971"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p126214494711"><a name="p126214494711"></a><a name="p126214494711"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p963349876"><a name="p963349876"></a><a name="p963349876"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1364164918714"><a name="p1364164918714"></a><a name="p1364164918714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p19651549477"><a name="p19651549477"></a><a name="p19651549477"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row941049877"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p966154916720"><a name="p966154916720"></a><a name="p966154916720"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p116734915710"><a name="p116734915710"></a><a name="p116734915710"></a>Array of <a href="#response_supportVersions">supportVersions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1269174915719"><a name="p1269174915719"></a><a name="p1269174915719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p107018492071"><a name="p107018492071"></a><a name="p107018492071"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row241449670"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p87112494713"><a name="p87112494713"></a><a name="p87112494713"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p20729496713"><a name="p20729496713"></a><a name="p20729496713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p2732491373"><a name="p2732491373"></a><a name="p2732491373"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p14741492077"><a name="p14741492077"></a><a name="p14741492077"></a>创建时间</p>
</td>
</tr>
<tr id="row34204918717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p175849472"><a name="p175849472"></a><a name="p175849472"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1575249778"><a name="p1575249778"></a><a name="p1575249778"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p6779491776"><a name="p6779491776"></a><a name="p6779491776"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p137813491179"><a name="p137813491179"></a><a name="p137813491179"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 7**  supportVersions

<a name="response_supportVersions"></a>
<table><thead align="left"><tr id="row5793491475"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1081144916715"><a name="p1081144916715"></a><a name="p1081144916715"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p88219499719"><a name="p88219499719"></a><a name="p88219499719"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p12831349771"><a name="p12831349771"></a><a name="p12831349771"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p13832049170"><a name="p13832049170"></a><a name="p13832049170"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row2801449877"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1684104910710"><a name="p1684104910710"></a><a name="p1684104910710"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p38519499716"><a name="p38519499716"></a><a name="p38519499716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p7861249475"><a name="p7861249475"></a><a name="p7861249475"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p12866494716"><a name="p12866494716"></a><a name="p12866494716"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row1180154914716"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p3876495717"><a name="p3876495717"></a><a name="p3876495717"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p10881749775"><a name="p10881749775"></a><a name="p10881749775"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p178914916712"><a name="p178914916712"></a><a name="p178914916712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p890184917715"><a name="p890184917715"></a><a name="p890184917715"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 8**  instanceSpec

<a name="response_instanceSpec"></a>
<table><thead align="left"><tr id="row2934491475"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p2097114915720"><a name="p2097114915720"></a><a name="p2097114915720"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p5986491711"><a name="p5986491711"></a><a name="p5986491711"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p3993492076"><a name="p3993492076"></a><a name="p3993492076"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p69919492720"><a name="p69919492720"></a><a name="p69919492720"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row893104917720"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p9104114914710"><a name="p9104114914710"></a><a name="p9104114914710"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p210512491779"><a name="p210512491779"></a><a name="p210512491779"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p91066497718"><a name="p91066497718"></a><a name="p91066497718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p210719494712"><a name="p210719494712"></a><a name="p210719494712"></a>集群id</p>
</td>
</tr>
<tr id="row6933491572"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p111075491975"><a name="p111075491975"></a><a name="p111075491975"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p10108174914718"><a name="p10108174914718"></a><a name="p10108174914718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1410814491571"><a name="p1410814491571"></a><a name="p1410814491571"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p210917491278"><a name="p210917491278"></a><a name="p210917491278"></a>插件模板版本号，如1.0.0</p>
</td>
</tr>
<tr id="row1194194911719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p141101149675"><a name="p141101149675"></a><a name="p141101149675"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p12110124910716"><a name="p12110124910716"></a><a name="p12110124910716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p7111749774"><a name="p7111749774"></a><a name="p7111749774"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p17112144914711"><a name="p17112144914711"></a><a name="p17112144914711"></a>插件模板名称，如coredns</p>
</td>
</tr>
<tr id="row2944493716"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p911324910719"><a name="p911324910719"></a><a name="p911324910719"></a>addonTemplateType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p15113154911719"><a name="p15113154911719"></a><a name="p15113154911719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p201141949279"><a name="p201141949279"></a><a name="p201141949279"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p201151549179"><a name="p201151549179"></a><a name="p201151549179"></a>插件模板类型</p>
</td>
</tr>
<tr id="row6940499712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p81152493718"><a name="p81152493718"></a><a name="p81152493718"></a>addonTemplateLabels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1711618491372"><a name="p1711618491372"></a><a name="p1711618491372"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p11171049474"><a name="p11171049474"></a><a name="p11171049474"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p2117174912717"><a name="p2117174912717"></a><a name="p2117174912717"></a>插件模板所属类型</p>
</td>
</tr>
<tr id="row129516491176"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p81188499718"><a name="p81188499718"></a><a name="p81188499718"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p171217491179"><a name="p171217491179"></a><a name="p171217491179"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p111211249676"><a name="p111211249676"></a><a name="p111211249676"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p4122164918716"><a name="p4122164918716"></a><a name="p4122164918716"></a>插件模板描述</p>
</td>
</tr>
<tr id="row3951349875"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p161222498716"><a name="p161222498716"></a><a name="p161222498716"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p55333507718"><a name="p55333507718"></a><a name="p55333507718"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1533450775"><a name="p1533450775"></a><a name="p1533450775"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p115348501975"><a name="p115348501975"></a><a name="p115348501975"></a>插件模板安装参数（各插件不同）</p>
</td>
</tr>
</tbody>
</table>

**表 9**  metadata

<a name="response_metadata"></a>
<table><thead align="left"><tr id="row612814920717"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p053412504717"><a name="p053412504717"></a><a name="p053412504717"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1053585017713"><a name="p1053585017713"></a><a name="p1053585017713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p11535115017715"><a name="p11535115017715"></a><a name="p11535115017715"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p10535135014714"><a name="p10535135014714"></a><a name="p10535135014714"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row121299491775"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2053519501774"><a name="p2053519501774"></a><a name="p2053519501774"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p4535650777"><a name="p4535650777"></a><a name="p4535650777"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p253511501076"><a name="p253511501076"></a><a name="p253511501076"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p45355508720"><a name="p45355508720"></a><a name="p45355508720"></a>唯一id标识</p>
</td>
</tr>
<tr id="row19129249876"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p19536155015714"><a name="p19536155015714"></a><a name="p19536155015714"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p115361501479"><a name="p115361501479"></a><a name="p115361501479"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p18536195010718"><a name="p18536195010718"></a><a name="p18536195010718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p453665013717"><a name="p453665013717"></a><a name="p453665013717"></a>插件名称</p>
</td>
</tr>
<tr id="row1312918492718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p8536185014716"><a name="p8536185014716"></a><a name="p8536185014716"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p135364506710"><a name="p135364506710"></a><a name="p135364506710"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p18536185014710"><a name="p18536185014710"></a><a name="p18536185014710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p135361450471"><a name="p135361450471"></a><a name="p135361450471"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row111295491277"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p553710508710"><a name="p553710508710"></a><a name="p553710508710"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14537185014716"><a name="p14537185014716"></a><a name="p14537185014716"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p853713504718"><a name="p853713504718"></a><a name="p853713504718"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1553712501474"><a name="p1553712501474"></a><a name="p1553712501474"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row612974915713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p145376505718"><a name="p145376505718"></a><a name="p145376505718"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p195387504711"><a name="p195387504711"></a><a name="p195387504711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1153817501878"><a name="p1153817501878"></a><a name="p1153817501878"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p35386503719"><a name="p35386503719"></a><a name="p35386503719"></a>更新时间</p>
</td>
</tr>
<tr id="row21303491177"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p85382501573"><a name="p85382501573"></a><a name="p85382501573"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p10538750077"><a name="p10538750077"></a><a name="p10538750077"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p17539125018714"><a name="p17539125018714"></a><a name="p17539125018714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p65392506716"><a name="p65392506716"></a><a name="p65392506716"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section19539145010710"></a>

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

## 响应示例<a name="section95419501776"></a>

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

## 返回值<a name="section55496505712"></a>

<a name="table12"></a>
<table><thead align="left"><tr id="row41741249471"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p1550650078"><a name="p1550650078"></a><a name="p1550650078"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p855025017714"><a name="p855025017714"></a><a name="p855025017714"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row151754492720"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p55508509718"><a name="p55508509718"></a><a name="p55508509718"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p95500508716"><a name="p95500508716"></a><a name="p95500508716"></a>OK</p>
</td>
</tr>
<tr id="row8175134911716"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p1655116502716"><a name="p1655116502716"></a><a name="p1655116502716"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p16551175017718"><a name="p16551175017718"></a><a name="p16551175017718"></a>Internal Server Error</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section65514502720"></a>

<a name="table13"></a>
<table><thead align="left"><tr id="row11811949672"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.5.1.1"><p id="p155511506717"><a name="p155511506717"></a><a name="p155511506717"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.2"><p id="p25511350375"><a name="p25511350375"></a><a name="p25511350375"></a>错误码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.3"><p id="p17551250270"><a name="p17551250270"></a><a name="p17551250270"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="35%" id="mcps1.1.5.1.4"><p id="p1551165017717"><a name="p1551165017717"></a><a name="p1551165017717"></a>解决方案</p>
</th>
</tr>
</thead>
<tbody><tr id="row181821849475"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p1855117501472"><a name="p1855117501472"></a><a name="p1855117501472"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p555145020713"><a name="p555145020713"></a><a name="p555145020713"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1551350573"><a name="p1551350573"></a><a name="p1551350573"></a>bad request</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row171825491375"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p6552195012715"><a name="p6552195012715"></a><a name="p6552195012715"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1755285016711"><a name="p1755285016711"></a><a name="p1755285016711"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p17552850475"><a name="p17552850475"></a><a name="p17552850475"></a>Authenticate failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row14182134915718"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p10552450579"><a name="p10552450579"></a><a name="p10552450579"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p65527506717"><a name="p65527506717"></a><a name="p65527506717"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1555213501976"><a name="p1555213501976"></a><a name="p1555213501976"></a>Authorize failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row1218319491672"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p1553050472"><a name="p1553050472"></a><a name="p1553050472"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p255311501770"><a name="p255311501770"></a><a name="p255311501770"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p455318508719"><a name="p455318508719"></a><a name="p455318508719"></a>addontemplate not exist</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row17183104916713"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p16553115010718"><a name="p16553115010718"></a><a name="p16553115010718"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p185531501271"><a name="p185531501271"></a><a name="p185531501271"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p8553125015715"><a name="p8553125015715"></a><a name="p8553125015715"></a>server internal error</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
</tbody>
</table>

