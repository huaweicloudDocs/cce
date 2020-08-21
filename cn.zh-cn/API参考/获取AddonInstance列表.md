# 获取AddonInstance列表<a name="cce_02_0326"></a>

## 功能描述<a name="section108927501774"></a>

获取集群所有已安装插件实例。

>![](public_sys-resources/icon-note.gif) **说明：** 
>URL格式为：**https://\{clusterid\}.Endpoint/uri**。其中\{clusterid\}为集群ID，uri为资源路径，也即API访问的路径。

## URI<a name="section68937501179"></a>

GET /api/v3/addons?cluster\_id=\{cluster\_id\}

**表 1**  路径参数

<a name="table489613501374"></a>
<table><thead align="left"><tr id="row198955507711"><th class="cellrowborder" valign="top" width="16.509999999999998%" id="mcps1.2.5.1.1"><p id="p289718501577"><a name="p289718501577"></a><a name="p289718501577"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.16%" id="mcps1.2.5.1.2"><p id="p629412918011"><a name="p629412918011"></a><a name="p629412918011"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.3"><p id="p1489725017716"><a name="p1489725017716"></a><a name="p1489725017716"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p4898185014715"><a name="p4898185014715"></a><a name="p4898185014715"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row108951650475"><td class="cellrowborder" valign="top" width="16.509999999999998%" headers="mcps1.2.5.1.1 "><p id="p1389812506713"><a name="p1389812506713"></a><a name="p1389812506713"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="12.16%" headers="mcps1.2.5.1.2 "><p id="p82942910016"><a name="p82942910016"></a><a name="p82942910016"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p1789915507711"><a name="p1789915507711"></a><a name="p1789915507711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p15106445114416"><a name="p15106445114416"></a><a name="p15106445114416"></a>集群ID，获取方式请参见<a href="如何获取接口URI中参数.md">如何获取接口URI中参数</a>。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section89068508720"></a>

**请求参数：**

请求参数如[表2](#HeaderParameter)所示。

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row5908145011714"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p1191015014713"><a name="p1191015014713"></a><a name="p1191015014713"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.310000000000002%" id="mcps1.2.5.1.2"><p id="p1090919451205"><a name="p1090919451205"></a><a name="p1090919451205"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.360000000000001%" id="mcps1.2.5.1.3"><p id="p189107501272"><a name="p189107501272"></a><a name="p189107501272"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.95%" id="mcps1.2.5.1.4"><p id="p10912135017710"><a name="p10912135017710"></a><a name="p10912135017710"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row0908105018717"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p15913165019712"><a name="p15913165019712"></a><a name="p15913165019712"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="13.310000000000002%" headers="mcps1.2.5.1.2 "><p id="p772812576018"><a name="p772812576018"></a><a name="p772812576018"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.360000000000001%" headers="mcps1.2.5.1.3 "><p id="p1391314504716"><a name="p1391314504716"></a><a name="p1391314504716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p149140501872"><a name="p149140501872"></a><a name="p149140501872"></a>消息体的类型（格式），下方类型可任选其一使用</p>
<a name="ul17123954274"></a><a name="ul17123954274"></a><ul id="ul17123954274"><li>application/json;charset=utf-8</li><li>application/json</li></ul>
</td>
</tr>
<tr id="row090835018716"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p149163501971"><a name="p149163501971"></a><a name="p149163501971"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="13.310000000000002%" headers="mcps1.2.5.1.2 "><p id="p9728357905"><a name="p9728357905"></a><a name="p9728357905"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.360000000000001%" headers="mcps1.2.5.1.3 "><p id="p18916050978"><a name="p18916050978"></a><a name="p18916050978"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p6931115842613"><a name="p6931115842613"></a><a name="p6931115842613"></a>调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="认证鉴权.md#section2417768214391">获取token</a>。</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

无

## 响应消息<a name="section691935020713"></a>

**响应参数：**

响应参数如[表3](#responseParameter)所示。

**表 3**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row392414502719"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p1992816501972"><a name="p1992816501972"></a><a name="p1992816501972"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.75%" id="mcps1.2.5.1.2"><p id="p58181177117"><a name="p58181177117"></a><a name="p58181177117"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.919999999999998%" id="mcps1.2.5.1.3"><p id="p09289506713"><a name="p09289506713"></a><a name="p09289506713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p092910501876"><a name="p092910501876"></a><a name="p092910501876"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row3924185012719"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p1692919501377"><a name="p1692919501377"></a><a name="p1692919501377"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="14.75%" headers="mcps1.2.5.1.2 "><p id="p829511161219"><a name="p829511161219"></a><a name="p829511161219"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p1793014504716"><a name="p1793014504716"></a><a name="p1793014504716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p109308501873"><a name="p109308501873"></a><a name="p109308501873"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row139243501972"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p993110507710"><a name="p993110507710"></a><a name="p993110507710"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.75%" headers="mcps1.2.5.1.2 "><p id="p829571610117"><a name="p829571610117"></a><a name="p829571610117"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p6931185016711"><a name="p6931185016711"></a><a name="p6931185016711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p493319504719"><a name="p493319504719"></a><a name="p493319504719"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row139252050570"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p293315501374"><a name="p293315501374"></a><a name="p293315501374"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="14.75%" headers="mcps1.2.5.1.2 "><p id="p18295516814"><a name="p18295516814"></a><a name="p18295516814"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p199345504710"><a name="p199345504710"></a><a name="p199345504710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p16935135010714"><a name="p16935135010714"></a><a name="p16935135010714"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row892595010713"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p109382509720"><a name="p109382509720"></a><a name="p109382509720"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="14.75%" headers="mcps1.2.5.1.2 "><p id="p1629517168110"><a name="p1629517168110"></a><a name="p1629517168110"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p4938350474"><a name="p4938350474"></a><a name="p4938350474"></a>Array of <a href="#response_addoninstance">addoninstance</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1593918501575"><a name="p1593918501575"></a><a name="p1593918501575"></a>插件实例列表</p>
</td>
</tr>
</tbody>
</table>

**表 4**  addoninstance

<a name="response_addoninstance"></a>
<table><thead align="left"><tr id="row169413501271"><th class="cellrowborder" valign="top" width="18.16%" id="mcps1.2.5.1.1"><p id="p894314505715"><a name="p894314505715"></a><a name="p894314505715"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.920000000000002%" id="mcps1.2.5.1.2"><p id="p753694911119"><a name="p753694911119"></a><a name="p753694911119"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.97%" id="mcps1.2.5.1.3"><p id="p1594410501672"><a name="p1594410501672"></a><a name="p1594410501672"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p79451050773"><a name="p79451050773"></a><a name="p79451050773"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row79411850572"><td class="cellrowborder" valign="top" width="18.16%" headers="mcps1.2.5.1.1 "><p id="p794612501372"><a name="p794612501372"></a><a name="p794612501372"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="12.920000000000002%" headers="mcps1.2.5.1.2 "><p id="p02155913110"><a name="p02155913110"></a><a name="p02155913110"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.97%" headers="mcps1.2.5.1.3 "><p id="p139472503714"><a name="p139472503714"></a><a name="p139472503714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p109481350971"><a name="p109481350971"></a><a name="p109481350971"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row18942125015719"><td class="cellrowborder" valign="top" width="18.16%" headers="mcps1.2.5.1.1 "><p id="p179489503713"><a name="p179489503713"></a><a name="p179489503713"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="12.920000000000002%" headers="mcps1.2.5.1.2 "><p id="p1924591118"><a name="p1924591118"></a><a name="p1924591118"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.97%" headers="mcps1.2.5.1.3 "><p id="p1994910501272"><a name="p1994910501272"></a><a name="p1994910501272"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p189503505717"><a name="p189503505717"></a><a name="p189503505717"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row139424501712"><td class="cellrowborder" valign="top" width="18.16%" headers="mcps1.2.5.1.1 "><p id="p195011501173"><a name="p195011501173"></a><a name="p195011501173"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="12.920000000000002%" headers="mcps1.2.5.1.2 "><p id="p326591111"><a name="p326591111"></a><a name="p326591111"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.97%" headers="mcps1.2.5.1.3 "><p id="p1295111501278"><a name="p1295111501278"></a><a name="p1295111501278"></a><a href="#response_metadata">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p129542504720"><a name="p129542504720"></a><a name="p129542504720"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性。</p>
</td>
</tr>
<tr id="row14942650077"><td class="cellrowborder" valign="top" width="18.16%" headers="mcps1.2.5.1.1 "><p id="p16955145011712"><a name="p16955145011712"></a><a name="p16955145011712"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="12.920000000000002%" headers="mcps1.2.5.1.2 "><p id="p1223599118"><a name="p1223599118"></a><a name="p1223599118"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.97%" headers="mcps1.2.5.1.3 "><p id="p1495665020710"><a name="p1495665020710"></a><a name="p1495665020710"></a><a href="#response_instanceSpec">instanceSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p7958650573"><a name="p7958650573"></a><a name="p7958650573"></a>spec是集合类的元素类型，内容为插件实例具体信息，实例的详细描述主体部分都在spec中给出。</p>
</td>
</tr>
<tr id="row894219508714"><td class="cellrowborder" valign="top" width="18.16%" headers="mcps1.2.5.1.1 "><p id="p69597507715"><a name="p69597507715"></a><a name="p69597507715"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="12.920000000000002%" headers="mcps1.2.5.1.2 "><p id="p72759310"><a name="p72759310"></a><a name="p72759310"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.97%" headers="mcps1.2.5.1.3 "><p id="p29609508716"><a name="p29609508716"></a><a name="p29609508716"></a><a href="#response_status">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1296317501873"><a name="p1296317501873"></a><a name="p1296317501873"></a>插件实例状态。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  status

<a name="response_status"></a>
<table><thead align="left"><tr id="row1496719506712"><th class="cellrowborder" valign="top" width="20.387961203879613%" id="mcps1.2.5.1.1"><p id="p69711850179"><a name="p69711850179"></a><a name="p69711850179"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.808619138086192%" id="mcps1.2.5.1.2"><p id="p62612818214"><a name="p62612818214"></a><a name="p62612818214"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="14.84851514848515%" id="mcps1.2.5.1.3"><p id="p6972145015718"><a name="p6972145015718"></a><a name="p6972145015718"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.954904509549046%" id="mcps1.2.5.1.4"><p id="p1397325019718"><a name="p1397325019718"></a><a name="p1397325019718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row496720500713"><td class="cellrowborder" valign="top" width="20.387961203879613%" headers="mcps1.2.5.1.1 "><p id="p99741750479"><a name="p99741750479"></a><a name="p99741750479"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="13.808619138086192%" headers="mcps1.2.5.1.2 "><p id="p19318919525"><a name="p19318919525"></a><a name="p19318919525"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.84851514848515%" headers="mcps1.2.5.1.3 "><p id="p1197505019718"><a name="p1197505019718"></a><a name="p1197505019718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.954904509549046%" headers="mcps1.2.5.1.4 "><p id="p19778501676"><a name="p19778501676"></a><a name="p19778501676"></a>插件实例状态</p>
</td>
</tr>
<tr id="row149679501871"><td class="cellrowborder" valign="top" width="20.387961203879613%" headers="mcps1.2.5.1.1 "><p id="p15978450279"><a name="p15978450279"></a><a name="p15978450279"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="13.808619138086192%" headers="mcps1.2.5.1.2 "><p id="p1631971911214"><a name="p1631971911214"></a><a name="p1631971911214"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.84851514848515%" headers="mcps1.2.5.1.3 "><p id="p119785502077"><a name="p119785502077"></a><a name="p119785502077"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.954904509549046%" headers="mcps1.2.5.1.4 "><p id="p09794501176"><a name="p09794501176"></a><a name="p09794501176"></a>插件安装失败原因</p>
</td>
</tr>
<tr id="row199684501470"><td class="cellrowborder" valign="top" width="20.387961203879613%" headers="mcps1.2.5.1.1 "><p id="p99809501072"><a name="p99809501072"></a><a name="p99809501072"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="13.808619138086192%" headers="mcps1.2.5.1.2 "><p id="p331912191729"><a name="p331912191729"></a><a name="p331912191729"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.84851514848515%" headers="mcps1.2.5.1.3 "><p id="p8981250176"><a name="p8981250176"></a><a name="p8981250176"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.954904509549046%" headers="mcps1.2.5.1.4 "><p id="p129831501471"><a name="p129831501471"></a><a name="p129831501471"></a>安装错误详情</p>
</td>
</tr>
<tr id="row99683501876"><td class="cellrowborder" valign="top" width="20.387961203879613%" headers="mcps1.2.5.1.1 "><p id="p998413501977"><a name="p998413501977"></a><a name="p998413501977"></a>targetVersions</p>
</td>
<td class="cellrowborder" valign="top" width="13.808619138086192%" headers="mcps1.2.5.1.2 "><p id="p831911917220"><a name="p831911917220"></a><a name="p831911917220"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.84851514848515%" headers="mcps1.2.5.1.3 "><p id="p12985150273"><a name="p12985150273"></a><a name="p12985150273"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.954904509549046%" headers="mcps1.2.5.1.4 "><p id="p29877502710"><a name="p29877502710"></a><a name="p29877502710"></a>此插件版本，支持升级的集群版本</p>
</td>
</tr>
<tr id="row896835010719"><td class="cellrowborder" valign="top" width="20.387961203879613%" headers="mcps1.2.5.1.1 "><p id="p498785016717"><a name="p498785016717"></a><a name="p498785016717"></a>currentVersion</p>
</td>
<td class="cellrowborder" valign="top" width="13.808619138086192%" headers="mcps1.2.5.1.2 "><p id="p173195191219"><a name="p173195191219"></a><a name="p173195191219"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.84851514848515%" headers="mcps1.2.5.1.3 "><p id="p189886501570"><a name="p189886501570"></a><a name="p189886501570"></a><a href="#response_versions">versions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.954904509549046%" headers="mcps1.2.5.1.4 "><p id="p4990135016715"><a name="p4990135016715"></a><a name="p4990135016715"></a>当前插件实例使用的具体插件版本信息</p>
</td>
</tr>
</tbody>
</table>

**表 6**  versions

<a name="response_versions"></a>
<table><thead align="left"><tr id="row199931450577"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p109972501473"><a name="p109972501473"></a><a name="p109972501473"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.98%" id="mcps1.2.5.1.2"><p id="p7122631127"><a name="p7122631127"></a><a name="p7122631127"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.690000000000001%" id="mcps1.2.5.1.3"><p id="p159985509718"><a name="p159985509718"></a><a name="p159985509718"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p101195114718"><a name="p101195114718"></a><a name="p101195114718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1899317501677"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p0285116716"><a name="p0285116716"></a><a name="p0285116716"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.5.1.2 "><p id="p186461244124"><a name="p186461244124"></a><a name="p186461244124"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.3 "><p id="p131511270"><a name="p131511270"></a><a name="p131511270"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p85125116717"><a name="p85125116717"></a><a name="p85125116717"></a>插件版本号</p>
</td>
</tr>
<tr id="row13993450777"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p19615514719"><a name="p19615514719"></a><a name="p19615514719"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.5.1.2 "><p id="p76467441629"><a name="p76467441629"></a><a name="p76467441629"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.3 "><p id="p1677512070"><a name="p1677512070"></a><a name="p1677512070"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p39115120710"><a name="p39115120710"></a><a name="p39115120710"></a>插件安装参数</p>
</td>
</tr>
<tr id="row129932050276"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p71012512711"><a name="p71012512711"></a><a name="p71012512711"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.5.1.2 "><p id="p96469443216"><a name="p96469443216"></a><a name="p96469443216"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.3 "><p id="p1611451177"><a name="p1611451177"></a><a name="p1611451177"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p71310511711"><a name="p71310511711"></a><a name="p71310511711"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row15994250971"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p17143511479"><a name="p17143511479"></a><a name="p17143511479"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.5.1.2 "><p id="p13646244626"><a name="p13646244626"></a><a name="p13646244626"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.3 "><p id="p131585111714"><a name="p131585111714"></a><a name="p131585111714"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p14173511779"><a name="p14173511779"></a><a name="p14173511779"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row4994135020715"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p41819511710"><a name="p41819511710"></a><a name="p41819511710"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.5.1.2 "><p id="p964613441214"><a name="p964613441214"></a><a name="p964613441214"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.3 "><p id="p41835112715"><a name="p41835112715"></a><a name="p41835112715"></a>Array of <a href="#response_supportVersions">supportVersions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p62019518712"><a name="p62019518712"></a><a name="p62019518712"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row99941250170"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p921651074"><a name="p921651074"></a><a name="p921651074"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.5.1.2 "><p id="p1964764413218"><a name="p1964764413218"></a><a name="p1964764413218"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.3 "><p id="p822115112715"><a name="p822115112715"></a><a name="p822115112715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p172316512713"><a name="p172316512713"></a><a name="p172316512713"></a>创建时间</p>
</td>
</tr>
<tr id="row189953501573"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p18242511270"><a name="p18242511270"></a><a name="p18242511270"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.5.1.2 "><p id="p14647644228"><a name="p14647644228"></a><a name="p14647644228"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.3 "><p id="p62415110712"><a name="p62415110712"></a><a name="p62415110712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1926185116711"><a name="p1926185116711"></a><a name="p1926185116711"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 7**  supportVersions

<a name="response_supportVersions"></a>
<table><thead align="left"><tr id="row3278514710"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p3312511379"><a name="p3312511379"></a><a name="p3312511379"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.879999999999999%" id="mcps1.2.5.1.2"><p id="p16608100332"><a name="p16608100332"></a><a name="p16608100332"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.790000000000001%" id="mcps1.2.5.1.3"><p id="p53235111720"><a name="p53235111720"></a><a name="p53235111720"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p0331511274"><a name="p0331511274"></a><a name="p0331511274"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row7281651376"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p13416518713"><a name="p13416518713"></a><a name="p13416518713"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="12.879999999999999%" headers="mcps1.2.5.1.2 "><p id="p93380712314"><a name="p93380712314"></a><a name="p93380712314"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.790000000000001%" headers="mcps1.2.5.1.3 "><p id="p193412511720"><a name="p193412511720"></a><a name="p193412511720"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p15368511674"><a name="p15368511674"></a><a name="p15368511674"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row9285519712"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p103612510712"><a name="p103612510712"></a><a name="p103612510712"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="12.879999999999999%" headers="mcps1.2.5.1.2 "><p id="p1633847138"><a name="p1633847138"></a><a name="p1633847138"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.790000000000001%" headers="mcps1.2.5.1.3 "><p id="p83745111715"><a name="p83745111715"></a><a name="p83745111715"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p11391151577"><a name="p11391151577"></a><a name="p11391151577"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 8**  instanceSpec

<a name="response_instanceSpec"></a>
<table><thead align="left"><tr id="row74125116711"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p54617513717"><a name="p54617513717"></a><a name="p54617513717"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="11.110000000000001%" id="mcps1.2.5.1.2"><p id="p2512181612313"><a name="p2512181612313"></a><a name="p2512181612313"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.560000000000002%" id="mcps1.2.5.1.3"><p id="p647185120710"><a name="p647185120710"></a><a name="p647185120710"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p34955113718"><a name="p34955113718"></a><a name="p34955113718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13422511472"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p7501511779"><a name="p7501511779"></a><a name="p7501511779"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="11.110000000000001%" headers="mcps1.2.5.1.2 "><p id="p10735152618313"><a name="p10735152618313"></a><a name="p10735152618313"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p55015118712"><a name="p55015118712"></a><a name="p55015118712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p15516511713"><a name="p15516511713"></a><a name="p15516511713"></a>集群id</p>
</td>
</tr>
<tr id="row10423511072"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p11520515717"><a name="p11520515717"></a><a name="p11520515717"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="11.110000000000001%" headers="mcps1.2.5.1.2 "><p id="p37351267320"><a name="p37351267320"></a><a name="p37351267320"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p253135115717"><a name="p253135115717"></a><a name="p253135115717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p125435114714"><a name="p125435114714"></a><a name="p125435114714"></a>插件模板版本号，如1.0.0</p>
</td>
</tr>
<tr id="row742251170"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p35575112718"><a name="p35575112718"></a><a name="p35575112718"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="11.110000000000001%" headers="mcps1.2.5.1.2 "><p id="p187355268314"><a name="p187355268314"></a><a name="p187355268314"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p1056125118713"><a name="p1056125118713"></a><a name="p1056125118713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p125710514710"><a name="p125710514710"></a><a name="p125710514710"></a>插件模板名称，如coredns</p>
</td>
</tr>
<tr id="row1042185111710"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p558155112717"><a name="p558155112717"></a><a name="p558155112717"></a>addonTemplateType</p>
</td>
<td class="cellrowborder" valign="top" width="11.110000000000001%" headers="mcps1.2.5.1.2 "><p id="p1373511268310"><a name="p1373511268310"></a><a name="p1373511268310"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p4591751379"><a name="p4591751379"></a><a name="p4591751379"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p660951672"><a name="p660951672"></a><a name="p660951672"></a>插件模板类型</p>
</td>
</tr>
<tr id="row2043195114710"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p86117511174"><a name="p86117511174"></a><a name="p86117511174"></a>addonTemplateLabels</p>
</td>
<td class="cellrowborder" valign="top" width="11.110000000000001%" headers="mcps1.2.5.1.2 "><p id="p10735142612319"><a name="p10735142612319"></a><a name="p10735142612319"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p962651371"><a name="p962651371"></a><a name="p962651371"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p663451374"><a name="p663451374"></a><a name="p663451374"></a>插件模板所属类型</p>
</td>
</tr>
<tr id="row4431051477"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p96435116719"><a name="p96435116719"></a><a name="p96435116719"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="11.110000000000001%" headers="mcps1.2.5.1.2 "><p id="p1573511263317"><a name="p1573511263317"></a><a name="p1573511263317"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p765551677"><a name="p765551677"></a><a name="p765551677"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p206695110714"><a name="p206695110714"></a><a name="p206695110714"></a>插件模板描述</p>
</td>
</tr>
<tr id="row5449511979"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p11663518714"><a name="p11663518714"></a><a name="p11663518714"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="11.110000000000001%" headers="mcps1.2.5.1.2 "><p id="p573613266313"><a name="p573613266313"></a><a name="p573613266313"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.560000000000002%" headers="mcps1.2.5.1.3 "><p id="p166714514718"><a name="p166714514718"></a><a name="p166714514718"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p18685511374"><a name="p18685511374"></a><a name="p18685511374"></a>插件模板安装参数（各插件不同）</p>
</td>
</tr>
</tbody>
</table>

**表 9**  metadata

<a name="response_metadata"></a>
<table><thead align="left"><tr id="row107017516717"><th class="cellrowborder" valign="top" width="18.59%" id="mcps1.2.5.1.1"><p id="p1751851877"><a name="p1751851877"></a><a name="p1751851877"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.17%" id="mcps1.2.5.1.2"><p id="p432023612314"><a name="p432023612314"></a><a name="p432023612314"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.29%" id="mcps1.2.5.1.3"><p id="p975165119719"><a name="p975165119719"></a><a name="p975165119719"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p1178105116711"><a name="p1178105116711"></a><a name="p1178105116711"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row107135111717"><td class="cellrowborder" valign="top" width="18.59%" headers="mcps1.2.5.1.1 "><p id="p18794519717"><a name="p18794519717"></a><a name="p18794519717"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="12.17%" headers="mcps1.2.5.1.2 "><p id="p12682446834"><a name="p12682446834"></a><a name="p12682446834"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.29%" headers="mcps1.2.5.1.3 "><p id="p128011518712"><a name="p128011518712"></a><a name="p128011518712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p2081165117710"><a name="p2081165117710"></a><a name="p2081165117710"></a>唯一id标识</p>
</td>
</tr>
<tr id="row20712511171"><td class="cellrowborder" valign="top" width="18.59%" headers="mcps1.2.5.1.1 "><p id="p1668510511377"><a name="p1668510511377"></a><a name="p1668510511377"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="12.17%" headers="mcps1.2.5.1.2 "><p id="p18682164618313"><a name="p18682164618313"></a><a name="p18682164618313"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.29%" headers="mcps1.2.5.1.3 "><p id="p86856511373"><a name="p86856511373"></a><a name="p86856511373"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1568545119720"><a name="p1568545119720"></a><a name="p1568545119720"></a>插件名称</p>
</td>
</tr>
<tr id="row127119514717"><td class="cellrowborder" valign="top" width="18.59%" headers="mcps1.2.5.1.1 "><p id="p668519519713"><a name="p668519519713"></a><a name="p668519519713"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="12.17%" headers="mcps1.2.5.1.2 "><p id="p1868220461831"><a name="p1868220461831"></a><a name="p1868220461831"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.29%" headers="mcps1.2.5.1.3 "><p id="p674151342713"><a name="p674151342713"></a><a name="p674151342713"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p268617512718"><a name="p268617512718"></a><a name="p268617512718"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row8727511675"><td class="cellrowborder" valign="top" width="18.59%" headers="mcps1.2.5.1.1 "><p id="p106861651975"><a name="p106861651975"></a><a name="p106861651975"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="12.17%" headers="mcps1.2.5.1.2 "><p id="p1568211464311"><a name="p1568211464311"></a><a name="p1568211464311"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.29%" headers="mcps1.2.5.1.3 "><p id="p176861151678"><a name="p176861151678"></a><a name="p176861151678"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1168665111711"><a name="p1168665111711"></a><a name="p1168665111711"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row1972135120712"><td class="cellrowborder" valign="top" width="18.59%" headers="mcps1.2.5.1.1 "><p id="p4686551974"><a name="p4686551974"></a><a name="p4686551974"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="12.17%" headers="mcps1.2.5.1.2 "><p id="p5682194618315"><a name="p5682194618315"></a><a name="p5682194618315"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.29%" headers="mcps1.2.5.1.3 "><p id="p66869516716"><a name="p66869516716"></a><a name="p66869516716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1568635112719"><a name="p1568635112719"></a><a name="p1568635112719"></a>更新时间</p>
</td>
</tr>
<tr id="row10728511678"><td class="cellrowborder" valign="top" width="18.59%" headers="mcps1.2.5.1.1 "><p id="p368711518711"><a name="p368711518711"></a><a name="p368711518711"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="12.17%" headers="mcps1.2.5.1.2 "><p id="p6683646134"><a name="p6683646134"></a><a name="p6683646134"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.29%" headers="mcps1.2.5.1.3 "><p id="p768715116714"><a name="p768715116714"></a><a name="p768715116714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p15687135118719"><a name="p15687135118719"></a><a name="p15687135118719"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

-   状态码为 200 时

    ```
    {
        "apiVersion": "v3",
        "kind": "Addon",
        "items": [
            {
                "metadata": {
                    "uid": "8ca259cc-553b-11e9-926f-0255ac101a31",
                    "name": "storage-driver",
                    "creationTimestamp": "2019-04-02T11:36:26Z",
                    "updateTimestamp": "2019-04-02T11:36:26Z"
                },
                "apiVersion": "v3",
                "kind": "Addon",
                "spec": {
                    "addonTemplateName": "storage-driver",
                    "addonTemplateLogo": "https://192.168.48.66/cce-addon-aw1hz2u/storage-driverlogo.svg",
                    "addonTemplateType": "helm",
                    "values": {
                        "flavor": {
                            "replicas": 1
                        },
                        "basic": {
                            "obs_url": "",
                            "swr_user": "hwofficial",
                            "euleros_version": "2.2.5",
                            "addon_version": "1.0.10",
                            "platform": "linux-amd64",
                            "swr_addr": "10.125.6.246:20202"
                        },
                        "parameters": {}
                    },
                    "description": "A kubernetes FlexVolume Driver used to support cloud storage",
                    "addonTemplateLabels": [
                        "Storage"
                    ],
                    "clusterID": "0c0e4a63-5539-11e9-95f7-0255ac10177e",
                    "version": "1.0.10"
                },
                "status": {
                    "message": "",
                    "Reason": "Install complete",
                    "currentVersion": {
                        "input": {
                            "basic": {
                                "obs_url": "",
                                "swr_user": "hwofficial",
                                "euleros_version": "2.2.5",
                                "swr_addr": "10.125.6.246:20202"
                            },
                            "parameters": {}
                        },
                        "stable": true,
                        "creationTimestamp": "2019-03-29T13:45:37Z",
                        "version": "1.0.10",
                        "translate": {
                            "en_US": {
                                "addon": {
                                    "changeLog": "The plug-in is upgraded to enhance the storage plug-in function.",
                                    "description": "A kubernetes FlexVolume Driver used to support cloud storage"
                                }
                            },
                            "zh_CN": {
                                "addon": {
                                    "changeLog": "",
                                    "description": ""
                                }
                            }
                        },
                        "updateTimestamp": "2019-03-29T13:45:37Z"
                    },
                    "status": "running"
                }
            }
        ]
    }
    ```

-   状态码为 500 时

    ```
    {
        "code": "SVCSTG.CCE-ADDONMGR.500",
        "message": "internal error"
    }
    ```


## 状态码<a name="section3694185113715"></a>

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

## 错误码<a name="section7695105115718"></a>

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

