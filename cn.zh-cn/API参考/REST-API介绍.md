# REST API介绍<a name="cce_02_0102"></a>

公有云API符合RESTful API的设计理论。

REST从资源的角度观察整个网络，分布在各处的资源由URI（Uniform Resource Identifier）确定，客户端的应用通过URL（Unified Resource Locator）获取资源。

-   CCE接口（[集群管理](集群管理.md)）的URL格式为：**https://Endpoint/uri**。其中uri为资源路径，也即API访问的路径。
-   Kubernetes原生接口、[存储管理](存储管理.md)的URL格式为：**https://\{clusterid\}.Endpoint/uri**。其中\{clusterid\}为集群ID，uri为资源路径，也即API访问的路径。

**表 1**  URL中的参数说明

<a name="te8003eec96f14d04bba49f077d8255c4"></a>
<table><thead align="left"><tr id="r003377fae265496abae667620fefa2cd"><th class="cellrowborder" valign="top" width="24.529999999999998%" id="mcps1.2.3.1.1"><p id="a0a4bf16b1e234537a1dfcf1b16d21681"><a name="a0a4bf16b1e234537a1dfcf1b16d21681"></a><a name="a0a4bf16b1e234537a1dfcf1b16d21681"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="75.47%" id="mcps1.2.3.1.2"><p id="a42f4efa6728b4c73ac5b8460767e4217"><a name="a42f4efa6728b4c73ac5b8460767e4217"></a><a name="a42f4efa6728b4c73ac5b8460767e4217"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row76071946195619"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="p10608114665617"><a name="p10608114665617"></a><a name="p10608114665617"></a>{clusterid}</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="p357191914513"><a name="p357191914513"></a><a name="p357191914513"></a>集群ID，创建集群后，调用<a href="获取指定项目下的集群.md">获取指定项目下的集群</a>接口获取。</p>
</td>
</tr>
<tr id="rfcf00bdb43074ab9bf75d834e4a7487e"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="p8404174418467"><a name="p8404174418467"></a><a name="p8404174418467"></a>Endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="a605696dad25c4828959fc00e6097c1b1"><a name="a605696dad25c4828959fc00e6097c1b1"></a><a name="a605696dad25c4828959fc00e6097c1b1"></a>Web服务入口点的URL，从<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>中获取从。</p>
</td>
</tr>
<tr id="r1ca9595858924fc984a2d0319152599f"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035614179_p150234219554"><a name="zh-cn_topic_0035614179_p150234219554"></a><a name="zh-cn_topic_0035614179_p150234219554"></a>uri</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="p1054711916519"><a name="p1054711916519"></a><a name="p1054711916519"></a>资源路径，也即API访问路径。从具体接口的URI模块获取，例如“v3/auth/tokens”。</p>
</td>
</tr>
</tbody>
</table>

REST API请求/响应对可以分为如下几部分：

-   请求URI
-   请求方法
-   请求消息头
-   请求消息体
-   响应消息头
-   响应消息体

## 请求URI<a name="section1849899574"></a>

请求URI由如下部分组成。

**\{URI-scheme\} :// \{**Endpoint**\} / \{resource-path\} ? \{query-string\}**

尽管请求URI包含在请求消息头中，但大多数语言或框架都要求您从请求消息中单独传递它，所有我们在此单独拿出来强调。

**表 2**  URI中的参数说明

<a name="t1797260c744a4e1a85d354f259cae55a"></a>
<table><thead align="left"><tr id="r6dceed05bcc649d2b032accbb2980a31"><th class="cellrowborder" valign="top" width="24.529999999999998%" id="mcps1.2.3.1.1"><p id="a3446b6b785cb432bae9f45aef9177041"><a name="a3446b6b785cb432bae9f45aef9177041"></a><a name="a3446b6b785cb432bae9f45aef9177041"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="75.47%" id="mcps1.2.3.1.2"><p id="abe71244a12ac45308e99d4bbf975a9f8"><a name="abe71244a12ac45308e99d4bbf975a9f8"></a><a name="abe71244a12ac45308e99d4bbf975a9f8"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row106982018513"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="p136991001517"><a name="p136991001517"></a><a name="p136991001517"></a>URI-scheme</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="p56992017520"><a name="p56992017520"></a><a name="p56992017520"></a>表示用于传输请求的协议。CCE的API都必须采用https。</p>
</td>
</tr>
<tr id="rb217758afff146a1b40b0dcbb28a4ae1"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035614179_p480227019422"><a name="zh-cn_topic_0035614179_p480227019422"></a><a name="zh-cn_topic_0035614179_p480227019422"></a>Endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="ad82b3484a1be43ddadf436efbe15285e"><a name="ad82b3484a1be43ddadf436efbe15285e"></a><a name="ad82b3484a1be43ddadf436efbe15285e"></a>指定承载REST服务端点的服务器域名或IP，从<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>中获取。</p>
</td>
</tr>
<tr id="refeed61892004ea682639be281a1a707"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="p1797614317513"><a name="p1797614317513"></a><a name="p1797614317513"></a>resource-path</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="a90409cbb8b1c49c4ad4d3cfee16f475e"><a name="a90409cbb8b1c49c4ad4d3cfee16f475e"></a><a name="a90409cbb8b1c49c4ad4d3cfee16f475e"></a>资源路径，也即API访问路径。从具体接口的URI模块获取，例如“v3/auth/tokens”。</p>
</td>
</tr>
<tr id="row19939365518"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="p393966455"><a name="p393966455"></a><a name="p393966455"></a>Query string</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="p159401867517"><a name="p159401867517"></a><a name="p159401867517"></a>可选参数，例如API版本或资源选择标准。</p>
</td>
</tr>
</tbody>
</table>

## 请求方法<a name="section10555351105412"></a>

HTTP方法（也称为操作或动词），它告诉服务你正在请求什么类型的操作。

**表 3**  HTTP方法

<a name="table6784213556"></a>
<table><thead align="left"><tr id="row158516220552"><th class="cellrowborder" valign="top" width="18%" id="mcps1.2.3.1.1"><p id="p19871923550"><a name="p19871923550"></a><a name="p19871923550"></a>方法</p>
</th>
<th class="cellrowborder" valign="top" width="82%" id="mcps1.2.3.1.2"><p id="p199019211551"><a name="p199019211551"></a><a name="p199019211551"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row893182175513"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p89718219557"><a name="p89718219557"></a><a name="p89718219557"></a>GET</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p181009218551"><a name="p181009218551"></a><a name="p181009218551"></a>请求服务器返回指定资源。</p>
</td>
</tr>
<tr id="row710113255515"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p1210618218558"><a name="p1210618218558"></a><a name="p1210618218558"></a>PUT</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p810915255511"><a name="p810915255511"></a><a name="p810915255511"></a>请求服务器更新指定资源。</p>
</td>
</tr>
<tr id="row6110226555"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p1911262175512"><a name="p1911262175512"></a><a name="p1911262175512"></a>POST</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p711411255514"><a name="p711411255514"></a><a name="p711411255514"></a>请求服务器新增资源或执行特殊操作。</p>
</td>
</tr>
<tr id="row81151920557"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p91178235510"><a name="p91178235510"></a><a name="p91178235510"></a>DELETE</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p21203215557"><a name="p21203215557"></a><a name="p21203215557"></a>请求服务器删除指定资源，如删除对象等。</p>
</td>
</tr>
<tr id="row5120725559"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p412212220551"><a name="p412212220551"></a><a name="p412212220551"></a>HEAD</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p181242265518"><a name="p181242265518"></a><a name="p181242265518"></a>请求服务器资源头部。</p>
</td>
</tr>
<tr id="row1712672145515"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p20127202175518"><a name="p20127202175518"></a><a name="p20127202175518"></a>PATCH</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p71296215510"><a name="p71296215510"></a><a name="p71296215510"></a>请求服务器更新资源的部分内容。</p>
<p id="p2129326557"><a name="p2129326557"></a><a name="p2129326557"></a>当资源不存在的时候，PATCH可能会去创建一个新的资源。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息头<a name="section1454211155819"></a>

可选的附加请求头字段，如指定的URI和HTTP方法所要求的字段。详细的公共请求消息头字段请参见[表4](#table070418235551)，其中请求认证信息请参见[获取请求认证](获取请求认证.md)。

**表 4**  公共请求消息头

<a name="table070418235551"></a>
<table><thead align="left"><tr id="row1371232314555"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p17161923125519"><a name="p17161923125519"></a><a name="p17161923125519"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="26%" id="mcps1.2.5.1.2"><p id="p12719623105520"><a name="p12719623105520"></a><a name="p12719623105520"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p87227238550"><a name="p87227238550"></a><a name="p87227238550"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="34%" id="mcps1.2.5.1.4"><p id="p27252023175518"><a name="p27252023175518"></a><a name="p27252023175518"></a>示例</p>
</th>
</tr>
</thead>
<tbody><tr id="row1872718238557"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1973015234551"><a name="p1973015234551"></a><a name="p1973015234551"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.5.1.2 "><p id="p973242310559"><a name="p973242310559"></a><a name="p973242310559"></a>用户Token。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1773410238550"><a name="p1773410238550"></a><a name="p1773410238550"></a>使用Token认证时必选</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="p573716236557"><a name="p573716236557"></a><a name="p573716236557"></a>-</p>
</td>
</tr>
<tr id="row1073818236558"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1974132315555"><a name="p1974132315555"></a><a name="p1974132315555"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.5.1.2 "><p id="p1774362318558"><a name="p1774362318558"></a><a name="p1774362318558"></a>消息体的类型（格式）。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1174722311553"><a name="p1174722311553"></a><a name="p1174722311553"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="p0749192314550"><a name="p0749192314550"></a><a name="p0749192314550"></a>application/json;charset=utf-8或者application/json</p>
</td>
</tr>
<tr id="row87515232557"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p16752112318550"><a name="p16752112318550"></a><a name="p16752112318550"></a>X-Sdk-Date</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.5.1.2 "><p id="p187551423185510"><a name="p187551423185510"></a><a name="p187551423185510"></a>请求的发生时间</p>
<p id="p67561123205516"><a name="p67561123205516"></a><a name="p67561123205516"></a>格式为(YYYYMMDD'T'HHMMSS'Z')。取值为当前系统的GMT时间</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p12758823105515"><a name="p12758823105515"></a><a name="p12758823105515"></a>使用AK/SK认证时必选</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="p177601123155512"><a name="p177601123155512"></a><a name="p177601123155512"></a>-</p>
</td>
</tr>
<tr id="row2761112345510"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p6764202317558"><a name="p6764202317558"></a><a name="p6764202317558"></a>Authorization</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.5.1.2 "><p id="p2766123165511"><a name="p2766123165511"></a><a name="p2766123165511"></a>签名认证信息，该值来源于请求签名结果。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1276922311551"><a name="p1276922311551"></a><a name="p1276922311551"></a>使用AK/SK认证时必选</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="p529152714225"><a name="p529152714225"></a><a name="p529152714225"></a>-</p>
</td>
</tr>
<tr id="row8773122315515"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p777532335512"><a name="p777532335512"></a><a name="p777532335512"></a>Host</p>
</td>
<td class="cellrowborder" valign="top" width="26%" headers="mcps1.2.5.1.2 "><p id="p19777142317555"><a name="p19777142317555"></a><a name="p19777142317555"></a>请求的服务器信息，从服务API的URL中获取。值为hostname[:port]。端口缺省时使用默认的端口，https的默认端口为443</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p877922318558"><a name="p877922318558"></a><a name="p877922318558"></a>使用AK/SK认证时必选</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="p478110236553"><a name="p478110236553"></a><a name="p478110236553"></a>-</p>
</td>
</tr>
</tbody>
</table>

## 请求消息体（可选）<a name="section14612192315587"></a>

请求消息体通常以结构化格式（如JSON或XML）发出，与请求消息头中Content-type对应，传递除请求消息头之外的内容。

## 响应消息头<a name="section7804143005810"></a>

响应消息头包含如下两部分。

-   一个HTTP状态代码，从2xx成功代码到4xx或5xx错误代码。 或者，可以返回服务定义的状态码，如API文档中所示。
-   附加响应头字段，如支持请求的响应所需，如Content-type响应消息头。详细的公共响应消息头字段请参见[表5](#zh-cn_topic_0035614305_table431633395935)。

    **表 5**  响应消息头

    <a name="zh-cn_topic_0035614305_table431633395935"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0035614305_row5838132395935"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0035614305_p2208706210115"><a name="zh-cn_topic_0035614305_p2208706210115"></a><a name="zh-cn_topic_0035614305_p2208706210115"></a>名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="44%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0035614305_p4259252810115"><a name="zh-cn_topic_0035614305_p4259252810115"></a><a name="zh-cn_topic_0035614305_p4259252810115"></a>描述</p>
    </th>
    <th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0035614305_p4178727010115"><a name="zh-cn_topic_0035614305_p4178727010115"></a><a name="zh-cn_topic_0035614305_p4178727010115"></a>示例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0035614305_row1643024095935"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.1 "><p id="p59963253104610"><a name="p59963253104610"></a><a name="p59963253104610"></a>Date</p>
    </td>
    <td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.2 "><p id="p25185323104610"><a name="p25185323104610"></a><a name="p25185323104610"></a>HTTP协议标准报头。表示消息发送的时间，时间的描述格式由rfc822定义。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.3 "><p id="p26745253104610"><a name="p26745253104610"></a><a name="p26745253104610"></a>Mon，12 Nov 2007 15:55:01 GMT</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035614305_row6136471495935"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.1 "><p id="p35719083104610"><a name="p35719083104610"></a><a name="p35719083104610"></a>Server</p>
    </td>
    <td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.2 "><p id="p7564607104610"><a name="p7564607104610"></a><a name="p7564607104610"></a>HTTP协议标准报头。包含了服务器用来处理请求的软件信息。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.3 "><p id="p8753460104610"><a name="p8753460104610"></a><a name="p8753460104610"></a>Apache</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035614305_row5278388395935"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.1 "><p id="p5930819104610"><a name="p5930819104610"></a><a name="p5930819104610"></a>Content-Length</p>
    </td>
    <td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.2 "><p id="p10634336104610"><a name="p10634336104610"></a><a name="p10634336104610"></a>HTTP协议标准报头。用于指明实体正文的长度，以字节方式存储的十进制数字来表示。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.3 "><p id="p56074906104610"><a name="p56074906104610"></a><a name="p56074906104610"></a>xxx</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035614305_row6263177095935"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.1 "><p id="p9308572104610"><a name="p9308572104610"></a><a name="p9308572104610"></a>Content-Type</p>
    </td>
    <td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.2 "><p id="p15796892104610"><a name="p15796892104610"></a><a name="p15796892104610"></a>HTTP协议标准报头。用于指明发送给接收者的实体正文的媒体类型。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.3 "><p id="p4479893104610"><a name="p4479893104610"></a><a name="p4479893104610"></a>application/json</p>
    </td>
    </tr>
    </tbody>
    </table>


## 响应消息体（可选）<a name="section034615592583"></a>

响应消息体通常以结构化格式（如JSON或XML）返回，与响应消息头中Content-type对应，传递除响应消息头之外的内容。

## 发起请求<a name="section140743661613"></a>

共有三种方式可以基于已构建好的请求消息发起请求，分别为：

-   cURL

    cURL是一个命令行工具，用来执行各种URL操作和信息传输。cURL充当的是HTTP客户端，可以发送HTTP请求给服务端，并接收响应消息。cURL适用于接口调试。关于cURL详细信息请参见[https://curl.haxx.se/](https://curl.haxx.se/)。

-   编码

    通过编码调用接口，组装请求消息，并发送处理请求消息。

-   REST客户端

    Mozilla、Google都为REST提供了图形化的浏览器插件，发送处理请求消息。针对Firefox，请参见[Firefox REST Client](https://addons.mozilla.org/en-US/firefox/addon/restclient/)。针对Chrome，请参见[Postman](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop)。


