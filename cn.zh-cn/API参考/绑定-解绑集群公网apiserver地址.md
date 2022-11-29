# 绑定、解绑集群公网apiserver地址<a name="UpdateClusterEip"></a>

## 功能介绍<a name="section2210161565"></a>

该API用于通过集群ID绑定、解绑集群公网apiserver地址

>![](public_sys-resources/icon-note.gif) **说明：** 
>集群管理的URL格式为：https://Endpoint/uri。其中uri为资源路径，也即API访问的路径。

## 调试<a name="section32119113610"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?product=CCE&api=UpdateClusterEip)中调试该接口，支持自动认证鉴权。API Explorer可以自动生成SDK代码示例，并提供SDK代码示例调试功能。

## URI<a name="section92121510612"></a>

PUT /api/v3/projects/\{project\_id\}/clusters/\{cluster\_id\}/mastereip

**表 1**  路径参数

<a name="table6213414612"></a>
<table><thead align="left"><tr id="row1421215120615"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p921311117611"><a name="p921311117611"></a><a name="p921311117611"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p92131213614"><a name="p92131213614"></a><a name="p92131213614"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p172131118619"><a name="p172131118619"></a><a name="p172131118619"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p102141511616"><a name="p102141511616"></a><a name="p102141511616"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row921210113617"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1621461563"><a name="p1621461563"></a><a name="p1621461563"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p112141912061"><a name="p112141912061"></a><a name="p112141912061"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p22141211869"><a name="p22141211869"></a><a name="p22141211869"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p122141418614"><a name="p122141418614"></a><a name="p122141418614"></a>项目ID，获取方式请参见<a href="如何获取接口URI中参数.md">如何获取接口URI中参数</a>。</p>
</td>
</tr>
<tr id="row4213141061"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p142141015612"><a name="p142141015612"></a><a name="p142141015612"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p5214715617"><a name="p5214715617"></a><a name="p5214715617"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p42148116618"><a name="p42148116618"></a><a name="p42148116618"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p62151511766"><a name="p62151511766"></a><a name="p62151511766"></a>集群 ID，获取方式请参见<a href="如何获取接口URI中参数.md">如何获取接口URI中参数</a>。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section021511666"></a>

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row14215121469"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p19216191966"><a name="p19216191966"></a><a name="p19216191966"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p152162119611"><a name="p152162119611"></a><a name="p152162119611"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p62161116616"><a name="p62161116616"></a><a name="p62161116616"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p202162115619"><a name="p202162115619"></a><a name="p202162115619"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row8215611063"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p821610117620"><a name="p821610117620"></a><a name="p821610117620"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p11216911067"><a name="p11216911067"></a><a name="p11216911067"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p42161013617"><a name="p42161013617"></a><a name="p42161013617"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p2217131362"><a name="p2217131362"></a><a name="p2217131362"></a>消息体的类型（格式）</p>
</td>
</tr>
<tr id="row1221510112619"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p5217714618"><a name="p5217714618"></a><a name="p5217714618"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p132171117616"><a name="p132171117616"></a><a name="p132171117616"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p8217819617"><a name="p8217819617"></a><a name="p8217819617"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p192171011767"><a name="p192171011767"></a><a name="p192171011767"></a>调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="认证鉴权.md">获取token</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  请求Body参数

<a name="request_MasterEIPRequest"></a>
<table><thead align="left"><tr id="row14217911661"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p62182110613"><a name="p62182110613"></a><a name="p62182110613"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p121818111617"><a name="p121818111617"></a><a name="p121818111617"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p17218817616"><a name="p17218817616"></a><a name="p17218817616"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p17219161564"><a name="p17219161564"></a><a name="p17219161564"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row122181711365"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1321913119616"><a name="p1321913119616"></a><a name="p1321913119616"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p13219912069"><a name="p13219912069"></a><a name="p13219912069"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p14220112613"><a name="p14220112613"></a><a name="p14220112613"></a><a href="#request_spec">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p52207116615"><a name="p52207116615"></a><a name="p52207116615"></a>spec信息</p>
</td>
</tr>
</tbody>
</table>

**表 4**  spec

<a name="request_spec"></a>
<table><thead align="left"><tr id="row1221191269"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p152221711865"><a name="p152221711865"></a><a name="p152221711865"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p162221311162"><a name="p162221311162"></a><a name="p162221311162"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1122251466"><a name="p1122251466"></a><a name="p1122251466"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p522217112618"><a name="p522217112618"></a><a name="p522217112618"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row152211011463"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p12231511362"><a name="p12231511362"></a><a name="p12231511362"></a>action</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p522331664"><a name="p522331664"></a><a name="p522331664"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p42239119618"><a name="p42239119618"></a><a name="p42239119618"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1522319120619"><a name="p1522319120619"></a><a name="p1522319120619"></a>绑定或解绑动作</p>
</td>
</tr>
<tr id="row17221191168"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p15223111463"><a name="p15223111463"></a><a name="p15223111463"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1223611466"><a name="p1223611466"></a><a name="p1223611466"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p522417113620"><a name="p522417113620"></a><a name="p522417113620"></a><a href="#request_spec">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p422412117610"><a name="p422412117610"></a><a name="p422412117610"></a>API Server地址信息</p>
</td>
</tr>
<tr id="row132211311612"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p12224121660"><a name="p12224121660"></a><a name="p12224121660"></a>bandwidth</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p6224611764"><a name="p6224611764"></a><a name="p6224611764"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p112241311613"><a name="p112241311613"></a><a name="p112241311613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p6224917616"><a name="p6224917616"></a><a name="p6224917616"></a>带宽</p>
</td>
</tr>
<tr id="row15221611960"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p11224141869"><a name="p11224141869"></a><a name="p11224141869"></a>elasticIp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p142251316611"><a name="p142251316611"></a><a name="p142251316611"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1022520118613"><a name="p1022520118613"></a><a name="p1022520118613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1522551067"><a name="p1522551067"></a><a name="p1522551067"></a>弹性网卡IP</p>
</td>
</tr>
</tbody>
</table>

**表 5**  spec

<a name="table42253118616"></a>
<table><thead align="left"><tr id="row22251918619"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p722615114612"><a name="p722615114612"></a><a name="p722615114612"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p2022620117619"><a name="p2022620117619"></a><a name="p2022620117619"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1722671763"><a name="p1722671763"></a><a name="p1722671763"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p162261111611"><a name="p162261111611"></a><a name="p162261111611"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6225151567"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2226616611"><a name="p2226616611"></a><a name="p2226616611"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p122271711566"><a name="p122271711566"></a><a name="p122271711566"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p15227151268"><a name="p15227151268"></a><a name="p15227151268"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p9227211668"><a name="p9227211668"></a><a name="p9227211668"></a>弹性网卡ID</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section422714114614"></a>

**状态码： 200**

**表 6**  响应Body参数

<a name="response_MasterEIPResponse"></a>
<table><thead align="left"><tr id="row142282112611"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p62283118613"><a name="p62283118613"></a><a name="p62283118613"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p22293114614"><a name="p22293114614"></a><a name="p22293114614"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p20229191169"><a name="p20229191169"></a><a name="p20229191169"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row322815114614"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1122914110616"><a name="p1122914110616"></a><a name="p1122914110616"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p62295113613"><a name="p62295113613"></a><a name="p62295113613"></a><a href="#response_Metadata">Metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1322961868"><a name="p1322961868"></a><a name="p1322961868"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row8228917619"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p82291314611"><a name="p82291314611"></a><a name="p82291314611"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p162292016618"><a name="p162292016618"></a><a name="p162292016618"></a><a href="#response_spec">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p11855471202"><a name="p11855471202"></a><a name="p11855471202"></a>spec信息</p>
</td>
</tr>
<tr id="row122817115614"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p142301919612"><a name="p142301919612"></a><a name="p142301919612"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p8230913612"><a name="p8230913612"></a><a name="p8230913612"></a><a href="#response_status">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p385620710208"><a name="p385620710208"></a><a name="p385620710208"></a>状态信息</p>
</td>
</tr>
</tbody>
</table>

**表 7**  Metadata

<a name="response_Metadata"></a>
<table><thead align="left"><tr id="row223117114615"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p52324111610"><a name="p52324111610"></a><a name="p52324111610"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p182327119618"><a name="p182327119618"></a><a name="p182327119618"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p132331211964"><a name="p132331211964"></a><a name="p132331211964"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2231011060"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1123316113612"><a name="p1123316113612"></a><a name="p1123316113612"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p17233511467"><a name="p17233511467"></a><a name="p17233511467"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p172331911766"><a name="p172331911766"></a><a name="p172331911766"></a>唯一id标识</p>
</td>
</tr>
<tr id="row12231211617"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p12234411365"><a name="p12234411365"></a><a name="p12234411365"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p4234181562"><a name="p4234181562"></a><a name="p4234181562"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p72341011066"><a name="p72341011066"></a><a name="p72341011066"></a>插件名称</p>
</td>
</tr>
<tr id="row92318112613"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p152347117610"><a name="p152347117610"></a><a name="p152347117610"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p112340116612"><a name="p112340116612"></a><a name="p112340116612"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1923412114610"><a name="p1923412114610"></a><a name="p1923412114610"></a>插件标签，key/value对格式，接口保留字段，填写不会生效</p>
</td>
</tr>
<tr id="row4231121962"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p72344113618"><a name="p72344113618"></a><a name="p72344113618"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p9235151264"><a name="p9235151264"></a><a name="p9235151264"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p82351019613"><a name="p82351019613"></a><a name="p82351019613"></a>插件注解，由key/value组成</p>
<a name="ul72351518617"></a><a name="ul72351518617"></a><ul id="ul72351518617"><li>安装：固定值为{"addon.install/type":"install"}</li><li>升级：固定值为{"addon.upgrade/type":"upgrade"}</li></ul>
</td>
</tr>
<tr id="row11231171361"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p4235611369"><a name="p4235611369"></a><a name="p4235611369"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p0235311567"><a name="p0235311567"></a><a name="p0235311567"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p823612110617"><a name="p823612110617"></a><a name="p823612110617"></a>更新时间</p>
</td>
</tr>
<tr id="row122311913619"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p10236711968"><a name="p10236711968"></a><a name="p10236711968"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p82360116616"><a name="p82360116616"></a><a name="p82360116616"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p82361716611"><a name="p82361716611"></a><a name="p82361716611"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

**表 8**  spec

<a name="response_spec"></a>
<table><thead align="left"><tr id="row92372110614"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p2239217616"><a name="p2239217616"></a><a name="p2239217616"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p10239012612"><a name="p10239012612"></a><a name="p10239012612"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p2239014614"><a name="p2239014614"></a><a name="p2239014614"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row62371511664"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p024011167"><a name="p024011167"></a><a name="p024011167"></a>action</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p82401411360"><a name="p82401411360"></a><a name="p82401411360"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p62403110614"><a name="p62403110614"></a><a name="p62403110614"></a>绑定动作</p>
</td>
</tr>
<tr id="row16238111467"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18240111568"><a name="p18240111568"></a><a name="p18240111568"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p5241818617"><a name="p5241818617"></a><a name="p5241818617"></a><a href="#response_spec">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p102411211616"><a name="p102411211616"></a><a name="p102411211616"></a>API Server地址信息</p>
</td>
</tr>
<tr id="row8238013614"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p924117117614"><a name="p924117117614"></a><a name="p924117117614"></a>elasticIp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p12422011561"><a name="p12422011561"></a><a name="p12422011561"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p15242117615"><a name="p15242117615"></a><a name="p15242117615"></a>弹性公网IP</p>
</td>
</tr>
</tbody>
</table>

**表 9**  spec

<a name="table1624218120619"></a>
<table><thead align="left"><tr id="row14242718618"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p62431311614"><a name="p62431311614"></a><a name="p62431311614"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p8243511563"><a name="p8243511563"></a><a name="p8243511563"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p2024341269"><a name="p2024341269"></a><a name="p2024341269"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1324213115611"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p42438115612"><a name="p42438115612"></a><a name="p42438115612"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p18243111267"><a name="p18243111267"></a><a name="p18243111267"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1224441766"><a name="p1224441766"></a><a name="p1224441766"></a>弹性网卡ID</p>
</td>
</tr>
<tr id="row172421314617"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p22441717611"><a name="p22441717611"></a><a name="p22441717611"></a>eip</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p12244219615"><a name="p12244219615"></a><a name="p12244219615"></a><a href="#response_EipSpec">EipSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p16244171269"><a name="p16244171269"></a><a name="p16244171269"></a>EIP的详细信息</p>
</td>
</tr>
<tr id="row15242111062"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p72441011164"><a name="p72441011164"></a><a name="p72441011164"></a>IsDynamic</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p32441611763"><a name="p32441611763"></a><a name="p32441611763"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17244201168"><a name="p17244201168"></a><a name="p17244201168"></a>是否动态创建</p>
</td>
</tr>
</tbody>
</table>

**表 10**  EipSpec

<a name="response_EipSpec"></a>
<table><thead align="left"><tr id="row10245911964"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p424519113615"><a name="p424519113615"></a><a name="p424519113615"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p524581660"><a name="p524581660"></a><a name="p524581660"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p42451211663"><a name="p42451211663"></a><a name="p42451211663"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row92451811966"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p0246611614"><a name="p0246611614"></a><a name="p0246611614"></a>bandwidth</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p2246411268"><a name="p2246411268"></a><a name="p2246411268"></a><a href="#response_bandwidth">bandwidth</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p448595863610"><a name="p448595863610"></a><a name="p448595863610"></a>带宽信息</p>
</td>
</tr>
</tbody>
</table>

**表 11**  bandwidth

<a name="response_bandwidth"></a>
<table><thead align="left"><tr id="row8246416611"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p152473116612"><a name="p152473116612"></a><a name="p152473116612"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p10247131068"><a name="p10247131068"></a><a name="p10247131068"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p52471311064"><a name="p52471311064"></a><a name="p52471311064"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row182461915611"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p112477119619"><a name="p112477119619"></a><a name="p112477119619"></a>size</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p32473117617"><a name="p32473117617"></a><a name="p32473117617"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p52473112619"><a name="p52473112619"></a><a name="p52473112619"></a>带宽大小</p>
</td>
</tr>
<tr id="row2246141164"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p124715112617"><a name="p124715112617"></a><a name="p124715112617"></a>sharetype</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p32481118615"><a name="p32481118615"></a><a name="p32481118615"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p152485113620"><a name="p152485113620"></a><a name="p152485113620"></a>带宽类型</p>
</td>
</tr>
</tbody>
</table>

**表 12**  status

<a name="response_status"></a>
<table><thead align="left"><tr id="row13248812060"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p18248112067"><a name="p18248112067"></a><a name="p18248112067"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p12499117611"><a name="p12499117611"></a><a name="p12499117611"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p192492118613"><a name="p192492118613"></a><a name="p192492118613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row0248915619"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18249716613"><a name="p18249716613"></a><a name="p18249716613"></a>privateEndpoint</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p524914120613"><a name="p524914120613"></a><a name="p524914120613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p182499113611"><a name="p182499113611"></a><a name="p182499113611"></a>集群访问的PrivateIP(HA集群返回VIP)</p>
</td>
</tr>
<tr id="row132481211666"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1725001269"><a name="p1725001269"></a><a name="p1725001269"></a>publicEndpoint</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p202501211460"><a name="p202501211460"></a><a name="p202501211460"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p525014114614"><a name="p525014114614"></a><a name="p525014114614"></a>集群访问的PublicIP</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section52501116611"></a>

```
{
  "metadata" : { },
  "spec" : {
    "action" : "bind",
    "spec" : {
      "id" : "a757a69e-f920-455a-b1ba-d7a22db0fd50",
      "eip" : {
        "bandwidth" : {
          "size" : 5,
          "sharetype" : "PER"
        }
      },
      "IsDynamic" : false
    },
    "elasticIp" : "8.8.8.8"
  },
  "status" : {
    "privateEndpoint" : "https://192.168.3.238:5443",
    "publicEndpoint" : "https://8.8.8.8:5443"
  }
}
```

## 响应示例<a name="section164941711760"></a>

**状态码： 200**

表示绑定集群公网apiserver地址成功，解绑成功无响应体。

```
{
  "metadata" : { },
  "spec" : {
    "action" : "bind",
    "spec" : {
      "id" : "a757a69e-f920-455a-b1ba-d7a22db0fd50",
      "eip" : {
        "bandwidth" : {
          "size" : 5,
          "sharetype" : "PER"
        }
      },
      "IsDynamic" : false
    },
    "elasticIp" : "8.8.8.8"
  },
  "status" : {
    "privateEndpoint" : "https://192.168.3.238:5443",
    "publicEndpoint" : "https://8.8.8.8:5443"
  }
}
```

## 状态码<a name="section13495611568"></a>

<a name="status_code"></a>
<table><thead align="left"><tr id="row16258101569"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p174958116612"><a name="p174958116612"></a><a name="p174958116612"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p174957119610"><a name="p174957119610"></a><a name="p174957119610"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row182581711367"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p18495151864"><a name="p18495151864"></a><a name="p18495151864"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p154951111467"><a name="p154951111467"></a><a name="p154951111467"></a>表示绑定集群公网apiserver地址成功，解绑成功无响应体。</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section84951113610"></a>

请参见[错误码](错误码.md)。

