# 更新AddonInstance<a name="cce_02_0323"></a>

## 功能描述<a name="section1221654910714"></a>

更新插件实例的功能。

>![](public_sys-resources/icon-note.gif) **说明：** 
>URL格式为：**https://\{clusterid\}.Endpoint/uri**。其中\{clusterid\}为集群ID，uri为资源路径，也即API访问的路径。

## URI<a name="section1021716494713"></a>

PUT /api/v3/addons/\{id\}

**表 1**  路径参数

<a name="table422018491378"></a>
<table><thead align="left"><tr id="row1121918490718"><th class="cellrowborder" valign="top" width="13.310000000000002%" id="mcps1.2.5.1.1"><p id="p722054916719"><a name="p722054916719"></a><a name="p722054916719"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.360000000000001%" id="mcps1.2.5.1.2"><p id="p349953513595"><a name="p349953513595"></a><a name="p349953513595"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.3"><p id="p42217491771"><a name="p42217491771"></a><a name="p42217491771"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.95%" id="mcps1.2.5.1.4"><p id="p1022214495718"><a name="p1022214495718"></a><a name="p1022214495718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row62196499718"><td class="cellrowborder" valign="top" width="13.310000000000002%" headers="mcps1.2.5.1.1 "><p id="p122233491170"><a name="p122233491170"></a><a name="p122233491170"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="15.360000000000001%" headers="mcps1.2.5.1.2 "><p id="p14499143518597"><a name="p14499143518597"></a><a name="p14499143518597"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p192241049376"><a name="p192241049376"></a><a name="p192241049376"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p152383501074"><a name="p152383501074"></a><a name="p152383501074"></a>插件实例ID，获取方式请参见<a href="获取AddonInstance列表.md#response_metadata">表9</a>。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section1022684910719"></a>

**请求参数：**

请求参数如[表2](#HeaderParameter)、[表3](#requestParameter)所示。

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row12228449678"><th class="cellrowborder" valign="top" width="15.73%" id="mcps1.2.5.1.1"><p id="p423018491370"><a name="p423018491370"></a><a name="p423018491370"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.629999999999999%" id="mcps1.2.5.1.2"><p id="p116191651105911"><a name="p116191651105911"></a><a name="p116191651105911"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.69%" id="mcps1.2.5.1.3"><p id="p0231184915710"><a name="p0231184915710"></a><a name="p0231184915710"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p42327491079"><a name="p42327491079"></a><a name="p42327491079"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6228124918717"><td class="cellrowborder" valign="top" width="15.73%" headers="mcps1.2.5.1.1 "><p id="p0232449176"><a name="p0232449176"></a><a name="p0232449176"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p9607559155912"><a name="p9607559155912"></a><a name="p9607559155912"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.69%" headers="mcps1.2.5.1.3 "><p id="p1623316493715"><a name="p1623316493715"></a><a name="p1623316493715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p162341349670"><a name="p162341349670"></a><a name="p162341349670"></a>消息体的类型（格式），下方类型可任选其一使用：</p>
<a name="ul18931523162612"></a><a name="ul18931523162612"></a><ul id="ul18931523162612"><li>application/json;charset=utf-8</li><li>application/json</li></ul>
</td>
</tr>
<tr id="row122813491477"><td class="cellrowborder" valign="top" width="15.73%" headers="mcps1.2.5.1.1 "><p id="p1423584915713"><a name="p1423584915713"></a><a name="p1423584915713"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="15.629999999999999%" headers="mcps1.2.5.1.2 "><p id="p1360717591595"><a name="p1360717591595"></a><a name="p1360717591595"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.69%" headers="mcps1.2.5.1.3 "><p id="p11236349477"><a name="p11236349477"></a><a name="p11236349477"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1526702582615"><a name="p1526702582615"></a><a name="p1526702582615"></a>调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="认证鉴权.md#section2417768214391">获取token</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  请求Body参数

<a name="requestParameter"></a>
<table><thead align="left"><tr id="row52384491472"><th class="cellrowborder" valign="top" width="14.470000000000002%" id="mcps1.2.5.1.1"><p id="p124220492716"><a name="p124220492716"></a><a name="p124220492716"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.200000000000001%" id="mcps1.2.5.1.2"><p id="p61566181705"><a name="p61566181705"></a><a name="p61566181705"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.3"><p id="p2243134917713"><a name="p2243134917713"></a><a name="p2243134917713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.95%" id="mcps1.2.5.1.4"><p id="p19244204918712"><a name="p19244204918712"></a><a name="p19244204918712"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12395498718"><td class="cellrowborder" valign="top" width="14.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p15245849373"><a name="p15245849373"></a><a name="p15245849373"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="14.200000000000001%" headers="mcps1.2.5.1.2 "><p id="p456172712016"><a name="p456172712016"></a><a name="p456172712016"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p16245349274"><a name="p16245349274"></a><a name="p16245349274"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p924716493719"><a name="p924716493719"></a><a name="p924716493719"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row132391649371"><td class="cellrowborder" valign="top" width="14.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p2024710496712"><a name="p2024710496712"></a><a name="p2024710496712"></a>apVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.200000000000001%" headers="mcps1.2.5.1.2 "><p id="p125614271000"><a name="p125614271000"></a><a name="p125614271000"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p112488491671"><a name="p112488491671"></a><a name="p112488491671"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p202501249170"><a name="p202501249170"></a><a name="p202501249170"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row324014920719"><td class="cellrowborder" valign="top" width="14.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p225017494714"><a name="p225017494714"></a><a name="p225017494714"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="14.200000000000001%" headers="mcps1.2.5.1.2 "><p id="p135622719019"><a name="p135622719019"></a><a name="p135622719019"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p82517499715"><a name="p82517499715"></a><a name="p82517499715"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p1525284910711"><a name="p1525284910711"></a><a name="p1525284910711"></a>安装：固定值为{"addon.install/type":"install"}</p>
<p id="p11252184914711"><a name="p11252184914711"></a><a name="p11252184914711"></a>升级：固定值为{"addon.upgrade/type":"upgrade"}</p>
</td>
</tr>
<tr id="row162406492710"><td class="cellrowborder" valign="top" width="14.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p3252134910711"><a name="p3252134910711"></a><a name="p3252134910711"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="14.200000000000001%" headers="mcps1.2.5.1.2 "><p id="p10569277018"><a name="p10569277018"></a><a name="p10569277018"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p725313491379"><a name="p725313491379"></a><a name="p725313491379"></a><a href="#instancerequestspec">instancerequestspec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.95%" headers="mcps1.2.5.1.4 "><p id="p102545491174"><a name="p102545491174"></a><a name="p102545491174"></a>spec是集合类的元素类型，内容为插件实例安装/升级的具体请求信息</p>
</td>
</tr>
</tbody>
</table>

**表 4**  instancerequestspec

<a name="instancerequestspec"></a>
<table><thead align="left"><tr id="row112566495713"><th class="cellrowborder" valign="top" width="16.669999999999998%" id="mcps1.2.5.1.1"><p id="p02608493719"><a name="p02608493719"></a><a name="p02608493719"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.17%" id="mcps1.2.5.1.2"><p id="p3319645606"><a name="p3319645606"></a><a name="p3319645606"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.21%" id="mcps1.2.5.1.3"><p id="p1260249476"><a name="p1260249476"></a><a name="p1260249476"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p1026110498719"><a name="p1026110498719"></a><a name="p1026110498719"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row52573499710"><td class="cellrowborder" valign="top" width="16.669999999999998%" headers="mcps1.2.5.1.1 "><p id="p1426254917713"><a name="p1426254917713"></a><a name="p1426254917713"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="16.17%" headers="mcps1.2.5.1.2 "><p id="p646220531401"><a name="p646220531401"></a><a name="p646220531401"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.21%" headers="mcps1.2.5.1.3 "><p id="p112637490713"><a name="p112637490713"></a><a name="p112637490713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1626524918718"><a name="p1626524918718"></a><a name="p1626524918718"></a>待安装、升级插件的具体版本版本号，例如1.0.0</p>
</td>
</tr>
<tr id="row82574492720"><td class="cellrowborder" valign="top" width="16.669999999999998%" headers="mcps1.2.5.1.1 "><p id="p14265124915713"><a name="p14265124915713"></a><a name="p14265124915713"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="16.17%" headers="mcps1.2.5.1.2 "><p id="p94627535019"><a name="p94627535019"></a><a name="p94627535019"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.21%" headers="mcps1.2.5.1.3 "><p id="p826624919714"><a name="p826624919714"></a><a name="p826624919714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p52679497719"><a name="p52679497719"></a><a name="p52679497719"></a>集群id</p>
</td>
</tr>
<tr id="row172574495718"><td class="cellrowborder" valign="top" width="16.669999999999998%" headers="mcps1.2.5.1.1 "><p id="p16268449574"><a name="p16268449574"></a><a name="p16268449574"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="16.17%" headers="mcps1.2.5.1.2 "><p id="p10462753100"><a name="p10462753100"></a><a name="p10462753100"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.21%" headers="mcps1.2.5.1.3 "><p id="p17269164912715"><a name="p17269164912715"></a><a name="p17269164912715"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p3270049177"><a name="p3270049177"></a><a name="p3270049177"></a>待安装或升级模板的具体请求参数，一般为配置文件，各插件不同</p>
</td>
</tr>
<tr id="row92581849472"><td class="cellrowborder" valign="top" width="16.669999999999998%" headers="mcps1.2.5.1.1 "><p id="p527104910720"><a name="p527104910720"></a><a name="p527104910720"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="16.17%" headers="mcps1.2.5.1.2 "><p id="p1462155316014"><a name="p1462155316014"></a><a name="p1462155316014"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.21%" headers="mcps1.2.5.1.3 "><p id="p8272104912717"><a name="p8272104912717"></a><a name="p8272104912717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p13273164916714"><a name="p13273164916714"></a><a name="p13273164916714"></a>待安装插件模板名称，如coredns</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
    "apiVersion": "string",
    "kind": "string",
    "metadata": {},
    "spec": {
        "clusterID": "string",
        "version": "string",
        "addonTemplateName": "string",
        "values": {}
    }
}
```

## 响应消息<a name="section12739492071"></a>

**响应参数：**

响应参数如[表5](#responseParameter)所示。

**表 5**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row5275249277"><th class="cellrowborder" valign="top" width="14.729999999999999%" id="mcps1.2.5.1.1"><p id="p42792491076"><a name="p42792491076"></a><a name="p42792491076"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.93%" id="mcps1.2.5.1.2"><p id="p357821114111"><a name="p357821114111"></a><a name="p357821114111"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.39%" id="mcps1.2.5.1.3"><p id="p428084911714"><a name="p428084911714"></a><a name="p428084911714"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p52814495718"><a name="p52814495718"></a><a name="p52814495718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row182761449276"><td class="cellrowborder" valign="top" width="14.729999999999999%" headers="mcps1.2.5.1.1 "><p id="p228118491376"><a name="p228118491376"></a><a name="p228118491376"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p6673152117118"><a name="p6673152117118"></a><a name="p6673152117118"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.39%" headers="mcps1.2.5.1.3 "><p id="p142823496712"><a name="p142823496712"></a><a name="p142823496712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p428312491676"><a name="p428312491676"></a><a name="p428312491676"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row19276749873"><td class="cellrowborder" valign="top" width="14.729999999999999%" headers="mcps1.2.5.1.1 "><p id="p122845491712"><a name="p122845491712"></a><a name="p122845491712"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p176731821419"><a name="p176731821419"></a><a name="p176731821419"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.39%" headers="mcps1.2.5.1.3 "><p id="p202862491478"><a name="p202862491478"></a><a name="p202862491478"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p152886497713"><a name="p152886497713"></a><a name="p152886497713"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row18276149577"><td class="cellrowborder" valign="top" width="14.729999999999999%" headers="mcps1.2.5.1.1 "><p id="p18288144910711"><a name="p18288144910711"></a><a name="p18288144910711"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p126733211512"><a name="p126733211512"></a><a name="p126733211512"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.39%" headers="mcps1.2.5.1.3 "><p id="p20289104912718"><a name="p20289104912718"></a><a name="p20289104912718"></a><a href="#response_metadata">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1729014491674"><a name="p1729014491674"></a><a name="p1729014491674"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row1427611491279"><td class="cellrowborder" valign="top" width="14.729999999999999%" headers="mcps1.2.5.1.1 "><p id="p12291849172"><a name="p12291849172"></a><a name="p12291849172"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p116737211617"><a name="p116737211617"></a><a name="p116737211617"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.39%" headers="mcps1.2.5.1.3 "><p id="p1629110491273"><a name="p1629110491273"></a><a name="p1629110491273"></a><a href="#response_instanceSpec">instanceSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p031324916712"><a name="p031324916712"></a><a name="p031324916712"></a>spec是集合类的元素类型，内容为插件实例具体信息，实例的详细描述主体部分都在spec中给出</p>
</td>
</tr>
<tr id="row72773491471"><td class="cellrowborder" valign="top" width="14.729999999999999%" headers="mcps1.2.5.1.1 "><p id="p1231418491871"><a name="p1231418491871"></a><a name="p1231418491871"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p16673121517"><a name="p16673121517"></a><a name="p16673121517"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.39%" headers="mcps1.2.5.1.3 "><p id="p53151749875"><a name="p53151749875"></a><a name="p53151749875"></a><a href="#response_status">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1631614491178"><a name="p1631614491178"></a><a name="p1631614491178"></a>插件实例状态</p>
</td>
</tr>
</tbody>
</table>

**表 6**  status

<a name="response_status"></a>
<table><thead align="left"><tr id="row73181049771"><th class="cellrowborder" valign="top" width="14.21%" id="mcps1.2.5.1.1"><p id="p133217499713"><a name="p133217499713"></a><a name="p133217499713"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.46%" id="mcps1.2.5.1.2"><p id="p13334115025"><a name="p13334115025"></a><a name="p13334115025"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.3"><p id="p173223495711"><a name="p173223495711"></a><a name="p173223495711"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p732334912711"><a name="p732334912711"></a><a name="p732334912711"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row631812491770"><td class="cellrowborder" valign="top" width="14.21%" headers="mcps1.2.5.1.1 "><p id="p183231549877"><a name="p183231549877"></a><a name="p183231549877"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="14.46%" headers="mcps1.2.5.1.2 "><p id="p058284213213"><a name="p058284213213"></a><a name="p058284213213"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p103244498714"><a name="p103244498714"></a><a name="p103244498714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p732417491878"><a name="p732417491878"></a><a name="p732417491878"></a>插件实例状态</p>
</td>
</tr>
<tr id="row731920491277"><td class="cellrowborder" valign="top" width="14.21%" headers="mcps1.2.5.1.1 "><p id="p232516494715"><a name="p232516494715"></a><a name="p232516494715"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="14.46%" headers="mcps1.2.5.1.2 "><p id="p1758264213214"><a name="p1758264213214"></a><a name="p1758264213214"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p173261349277"><a name="p173261349277"></a><a name="p173261349277"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1328549278"><a name="p1328549278"></a><a name="p1328549278"></a>插件安装失败原因</p>
</td>
</tr>
<tr id="row93196496718"><td class="cellrowborder" valign="top" width="14.21%" headers="mcps1.2.5.1.1 "><p id="p632815492079"><a name="p632815492079"></a><a name="p632815492079"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="14.46%" headers="mcps1.2.5.1.2 "><p id="p13582342422"><a name="p13582342422"></a><a name="p13582342422"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p14329154915714"><a name="p14329154915714"></a><a name="p14329154915714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1533114499715"><a name="p1533114499715"></a><a name="p1533114499715"></a>安装错误详情</p>
</td>
</tr>
<tr id="row031915493711"><td class="cellrowborder" valign="top" width="14.21%" headers="mcps1.2.5.1.1 "><p id="p1633213493715"><a name="p1633213493715"></a><a name="p1633213493715"></a>targetVersions</p>
</td>
<td class="cellrowborder" valign="top" width="14.46%" headers="mcps1.2.5.1.2 "><p id="p2582184213212"><a name="p2582184213212"></a><a name="p2582184213212"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p53334494717"><a name="p53334494717"></a><a name="p53334494717"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p18334144914716"><a name="p18334144914716"></a><a name="p18334144914716"></a>此插件版本，支持升级的集群版本</p>
</td>
</tr>
<tr id="row13191949976"><td class="cellrowborder" valign="top" width="14.21%" headers="mcps1.2.5.1.1 "><p id="p53356491574"><a name="p53356491574"></a><a name="p53356491574"></a>currentVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.46%" headers="mcps1.2.5.1.2 "><p id="p558224219220"><a name="p558224219220"></a><a name="p558224219220"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p113369498718"><a name="p113369498718"></a><a name="p113369498718"></a><a href="#response_versions">versions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p0337134913713"><a name="p0337134913713"></a><a name="p0337134913713"></a>当前插件实例使用的具体插件版本信息</p>
</td>
</tr>
</tbody>
</table>

**表 7**  versions

<a name="response_versions"></a>
<table><thead align="left"><tr id="row13391491973"><th class="cellrowborder" valign="top" width="13.700000000000001%" id="mcps1.2.5.1.1"><p id="p1534374910716"><a name="p1534374910716"></a><a name="p1534374910716"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.5.1.2"><p id="p1698415018310"><a name="p1698415018310"></a><a name="p1698415018310"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.3"><p id="p234313491712"><a name="p234313491712"></a><a name="p234313491712"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p834554912719"><a name="p834554912719"></a><a name="p834554912719"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row133913492711"><td class="cellrowborder" valign="top" width="13.700000000000001%" headers="mcps1.2.5.1.1 "><p id="p123461649975"><a name="p123461649975"></a><a name="p123461649975"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.5.1.2 "><p id="p238821116318"><a name="p238821116318"></a><a name="p238821116318"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p63462492075"><a name="p63462492075"></a><a name="p63462492075"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p16347549773"><a name="p16347549773"></a><a name="p16347549773"></a>插件版本号</p>
</td>
</tr>
<tr id="row933914914719"><td class="cellrowborder" valign="top" width="13.700000000000001%" headers="mcps1.2.5.1.1 "><p id="p10348164920714"><a name="p10348164920714"></a><a name="p10348164920714"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.5.1.2 "><p id="p17388611831"><a name="p17388611831"></a><a name="p17388611831"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p634818493716"><a name="p634818493716"></a><a name="p634818493716"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p93508491572"><a name="p93508491572"></a><a name="p93508491572"></a>插件安装参数</p>
</td>
</tr>
<tr id="row83392049879"><td class="cellrowborder" valign="top" width="13.700000000000001%" headers="mcps1.2.5.1.1 "><p id="p7350114919719"><a name="p7350114919719"></a><a name="p7350114919719"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.5.1.2 "><p id="p33881411639"><a name="p33881411639"></a><a name="p33881411639"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p4351154919712"><a name="p4351154919712"></a><a name="p4351154919712"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p93521491717"><a name="p93521491717"></a><a name="p93521491717"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row133401649572"><td class="cellrowborder" valign="top" width="13.700000000000001%" headers="mcps1.2.5.1.1 "><p id="p1235315491574"><a name="p1235315491574"></a><a name="p1235315491574"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.5.1.2 "><p id="p20388111115319"><a name="p20388111115319"></a><a name="p20388111115319"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p43545491777"><a name="p43545491777"></a><a name="p43545491777"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p93551749470"><a name="p93551749470"></a><a name="p93551749470"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row18340144910718"><td class="cellrowborder" valign="top" width="13.700000000000001%" headers="mcps1.2.5.1.1 "><p id="p1435510498712"><a name="p1435510498712"></a><a name="p1435510498712"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.5.1.2 "><p id="p103881411535"><a name="p103881411535"></a><a name="p103881411535"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p63565491871"><a name="p63565491871"></a><a name="p63565491871"></a>Array of <a href="#response_supportVersions">supportVersions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p11358649875"><a name="p11358649875"></a><a name="p11358649875"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row334020491074"><td class="cellrowborder" valign="top" width="13.700000000000001%" headers="mcps1.2.5.1.1 "><p id="p1435944914710"><a name="p1435944914710"></a><a name="p1435944914710"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.5.1.2 "><p id="p1538813116315"><a name="p1538813116315"></a><a name="p1538813116315"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p193602496716"><a name="p193602496716"></a><a name="p193602496716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p536194917713"><a name="p536194917713"></a><a name="p536194917713"></a>创建时间</p>
</td>
</tr>
<tr id="row1034010491472"><td class="cellrowborder" valign="top" width="13.700000000000001%" headers="mcps1.2.5.1.1 "><p id="p436213492711"><a name="p436213492711"></a><a name="p436213492711"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.5.1.2 "><p id="p153881111334"><a name="p153881111334"></a><a name="p153881111334"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p2036274912716"><a name="p2036274912716"></a><a name="p2036274912716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p036414491712"><a name="p036414491712"></a><a name="p036414491712"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 8**  supportVersions

<a name="response_supportVersions"></a>
<table><thead align="left"><tr id="row13365449277"><th class="cellrowborder" valign="top" width="16.470000000000002%" id="mcps1.2.5.1.1"><p id="p83678498710"><a name="p83678498710"></a><a name="p83678498710"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.2%" id="mcps1.2.5.1.2"><p id="p44681326834"><a name="p44681326834"></a><a name="p44681326834"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.3"><p id="p5368149078"><a name="p5368149078"></a><a name="p5368149078"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p123691849179"><a name="p123691849179"></a><a name="p123691849179"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1636520491077"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p193708499713"><a name="p193708499713"></a><a name="p193708499713"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.5.1.2 "><p id="p124721534633"><a name="p124721534633"></a><a name="p124721534633"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p203701849178"><a name="p203701849178"></a><a name="p203701849178"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p9372849379"><a name="p9372849379"></a><a name="p9372849379"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row1736613495710"><td class="cellrowborder" valign="top" width="16.470000000000002%" headers="mcps1.2.5.1.1 "><p id="p203739491577"><a name="p203739491577"></a><a name="p203739491577"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.5.1.2 "><p id="p1247233417313"><a name="p1247233417313"></a><a name="p1247233417313"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p13373164919715"><a name="p13373164919715"></a><a name="p13373164919715"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p73754494714"><a name="p73754494714"></a><a name="p73754494714"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 9**  instanceSpec

<a name="response_instanceSpec"></a>
<table><thead align="left"><tr id="row13772497714"><th class="cellrowborder" valign="top" width="23.39%" id="mcps1.2.5.1.1"><p id="p12381174917715"><a name="p12381174917715"></a><a name="p12381174917715"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.719999999999999%" id="mcps1.2.5.1.2"><p id="p1842934610318"><a name="p1842934610318"></a><a name="p1842934610318"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="14.6%" id="mcps1.2.5.1.3"><p id="p1338210497716"><a name="p1338210497716"></a><a name="p1338210497716"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.29%" id="mcps1.2.5.1.4"><p id="p1438312495714"><a name="p1438312495714"></a><a name="p1438312495714"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row737715493710"><td class="cellrowborder" valign="top" width="23.39%" headers="mcps1.2.5.1.1 "><p id="p13846491474"><a name="p13846491474"></a><a name="p13846491474"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="14.719999999999999%" headers="mcps1.2.5.1.2 "><p id="p179814557313"><a name="p179814557313"></a><a name="p179814557313"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.6%" headers="mcps1.2.5.1.3 "><p id="p1538418493717"><a name="p1538418493717"></a><a name="p1538418493717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.29%" headers="mcps1.2.5.1.4 "><p id="p1238617491379"><a name="p1238617491379"></a><a name="p1238617491379"></a>集群id</p>
</td>
</tr>
<tr id="row103775491773"><td class="cellrowborder" valign="top" width="23.39%" headers="mcps1.2.5.1.1 "><p id="p18386149778"><a name="p18386149778"></a><a name="p18386149778"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="14.719999999999999%" headers="mcps1.2.5.1.2 "><p id="p10984551737"><a name="p10984551737"></a><a name="p10984551737"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.6%" headers="mcps1.2.5.1.3 "><p id="p183873499719"><a name="p183873499719"></a><a name="p183873499719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.29%" headers="mcps1.2.5.1.4 "><p id="p18388144911716"><a name="p18388144911716"></a><a name="p18388144911716"></a>插件模板版本号，如1.0.0</p>
</td>
</tr>
<tr id="row1037715491572"><td class="cellrowborder" valign="top" width="23.39%" headers="mcps1.2.5.1.1 "><p id="p15389124911718"><a name="p15389124911718"></a><a name="p15389124911718"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="14.719999999999999%" headers="mcps1.2.5.1.2 "><p id="p189810558312"><a name="p189810558312"></a><a name="p189810558312"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.6%" headers="mcps1.2.5.1.3 "><p id="p93899497713"><a name="p93899497713"></a><a name="p93899497713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.29%" headers="mcps1.2.5.1.4 "><p id="p239116491272"><a name="p239116491272"></a><a name="p239116491272"></a>插件模板名称，如coredns</p>
</td>
</tr>
<tr id="row73771549276"><td class="cellrowborder" valign="top" width="23.39%" headers="mcps1.2.5.1.1 "><p id="p1239113491973"><a name="p1239113491973"></a><a name="p1239113491973"></a>addonTemplateType</p>
</td>
<td class="cellrowborder" valign="top" width="14.719999999999999%" headers="mcps1.2.5.1.2 "><p id="p1598125515311"><a name="p1598125515311"></a><a name="p1598125515311"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.6%" headers="mcps1.2.5.1.3 "><p id="p8392154914718"><a name="p8392154914718"></a><a name="p8392154914718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.29%" headers="mcps1.2.5.1.4 "><p id="p15748850877"><a name="p15748850877"></a><a name="p15748850877"></a>插件模板类型</p>
</td>
</tr>
<tr id="row1037820497710"><td class="cellrowborder" valign="top" width="23.39%" headers="mcps1.2.5.1.1 "><p id="p177493506718"><a name="p177493506718"></a><a name="p177493506718"></a>addonTemplateLabels</p>
</td>
<td class="cellrowborder" valign="top" width="14.719999999999999%" headers="mcps1.2.5.1.2 "><p id="p998145512314"><a name="p998145512314"></a><a name="p998145512314"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="14.6%" headers="mcps1.2.5.1.3 "><p id="p774914509717"><a name="p774914509717"></a><a name="p774914509717"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="47.29%" headers="mcps1.2.5.1.4 "><p id="p12749145017711"><a name="p12749145017711"></a><a name="p12749145017711"></a>插件模板所属类型</p>
</td>
</tr>
<tr id="row737874913710"><td class="cellrowborder" valign="top" width="23.39%" headers="mcps1.2.5.1.1 "><p id="p77491504711"><a name="p77491504711"></a><a name="p77491504711"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="14.719999999999999%" headers="mcps1.2.5.1.2 "><p id="p1898355230"><a name="p1898355230"></a><a name="p1898355230"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.6%" headers="mcps1.2.5.1.3 "><p id="p19750350770"><a name="p19750350770"></a><a name="p19750350770"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.29%" headers="mcps1.2.5.1.4 "><p id="p4750450777"><a name="p4750450777"></a><a name="p4750450777"></a>插件模板描述</p>
</td>
</tr>
<tr id="row173788491271"><td class="cellrowborder" valign="top" width="23.39%" headers="mcps1.2.5.1.1 "><p id="p177505501377"><a name="p177505501377"></a><a name="p177505501377"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="14.719999999999999%" headers="mcps1.2.5.1.2 "><p id="p1898655336"><a name="p1898655336"></a><a name="p1898655336"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.6%" headers="mcps1.2.5.1.3 "><p id="p775011501975"><a name="p775011501975"></a><a name="p775011501975"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="47.29%" headers="mcps1.2.5.1.4 "><p id="p1475014507719"><a name="p1475014507719"></a><a name="p1475014507719"></a>插件模板安装参数（各插件不同）</p>
</td>
</tr>
</tbody>
</table>

**表 10**  metadata

<a name="response_metadata"></a>
<table><thead align="left"><tr id="row1940510491679"><th class="cellrowborder" valign="top" width="21.709999999999997%" id="mcps1.2.5.1.1"><p id="p57511150870"><a name="p57511150870"></a><a name="p57511150870"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.78%" id="mcps1.2.5.1.2"><p id="p9607876415"><a name="p9607876415"></a><a name="p9607876415"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.4%" id="mcps1.2.5.1.3"><p id="p15751145014718"><a name="p15751145014718"></a><a name="p15751145014718"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="49.11%" id="mcps1.2.5.1.4"><p id="p1675219506718"><a name="p1675219506718"></a><a name="p1675219506718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row840511491576"><td class="cellrowborder" valign="top" width="21.709999999999997%" headers="mcps1.2.5.1.1 "><p id="p8752175019717"><a name="p8752175019717"></a><a name="p8752175019717"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="15.78%" headers="mcps1.2.5.1.2 "><p id="p1532914168413"><a name="p1532914168413"></a><a name="p1532914168413"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.4%" headers="mcps1.2.5.1.3 "><p id="p1175225013710"><a name="p1175225013710"></a><a name="p1175225013710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.11%" headers="mcps1.2.5.1.4 "><p id="p14752150971"><a name="p14752150971"></a><a name="p14752150971"></a>唯一id标识</p>
</td>
</tr>
<tr id="row13405184915712"><td class="cellrowborder" valign="top" width="21.709999999999997%" headers="mcps1.2.5.1.1 "><p id="p1675295013715"><a name="p1675295013715"></a><a name="p1675295013715"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="15.78%" headers="mcps1.2.5.1.2 "><p id="p12329181616411"><a name="p12329181616411"></a><a name="p12329181616411"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.4%" headers="mcps1.2.5.1.3 "><p id="p27531850270"><a name="p27531850270"></a><a name="p27531850270"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.11%" headers="mcps1.2.5.1.4 "><p id="p67531250973"><a name="p67531250973"></a><a name="p67531250973"></a>插件名称</p>
</td>
</tr>
<tr id="row1940510498716"><td class="cellrowborder" valign="top" width="21.709999999999997%" headers="mcps1.2.5.1.1 "><p id="p8753145019711"><a name="p8753145019711"></a><a name="p8753145019711"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="15.78%" headers="mcps1.2.5.1.2 "><p id="p12330216444"><a name="p12330216444"></a><a name="p12330216444"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.4%" headers="mcps1.2.5.1.3 "><p id="p1364102614317"><a name="p1364102614317"></a><a name="p1364102614317"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="49.11%" headers="mcps1.2.5.1.4 "><p id="p147546507712"><a name="p147546507712"></a><a name="p147546507712"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row204055494714"><td class="cellrowborder" valign="top" width="21.709999999999997%" headers="mcps1.2.5.1.1 "><p id="p37542050170"><a name="p37542050170"></a><a name="p37542050170"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="15.78%" headers="mcps1.2.5.1.2 "><p id="p1033061618415"><a name="p1033061618415"></a><a name="p1033061618415"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.4%" headers="mcps1.2.5.1.3 "><p id="p1067518346318"><a name="p1067518346318"></a><a name="p1067518346318"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="49.11%" headers="mcps1.2.5.1.4 "><p id="p107547501077"><a name="p107547501077"></a><a name="p107547501077"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row440614495710"><td class="cellrowborder" valign="top" width="21.709999999999997%" headers="mcps1.2.5.1.1 "><p id="p1575513501374"><a name="p1575513501374"></a><a name="p1575513501374"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="15.78%" headers="mcps1.2.5.1.2 "><p id="p433041612417"><a name="p433041612417"></a><a name="p433041612417"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.4%" headers="mcps1.2.5.1.3 "><p id="p77558508715"><a name="p77558508715"></a><a name="p77558508715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.11%" headers="mcps1.2.5.1.4 "><p id="p147558501871"><a name="p147558501871"></a><a name="p147558501871"></a>更新时间</p>
</td>
</tr>
<tr id="row14062491978"><td class="cellrowborder" valign="top" width="21.709999999999997%" headers="mcps1.2.5.1.1 "><p id="p2075519508718"><a name="p2075519508718"></a><a name="p2075519508718"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="15.78%" headers="mcps1.2.5.1.2 "><p id="p1333014169413"><a name="p1333014169413"></a><a name="p1333014169413"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.4%" headers="mcps1.2.5.1.3 "><p id="p107556509712"><a name="p107556509712"></a><a name="p107556509712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.11%" headers="mcps1.2.5.1.4 "><p id="p1755195017719"><a name="p1755195017719"></a><a name="p1755195017719"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

-   状态码为 200 时

    ```
    {
        "metadata": {
            "uid": "24b23108-55c0-11e9-926f-0255ac101a31",
            "name": "gpu-beta",
            "creationTimestamp": "2019-04-03T03:25:34Z",
            "updateTimestamp": "2019-04-03T03:25:34Z"
        },
        "apiVersion": "v3",
        "kind": "Addon",
        "spec": {
            "addonTemplateName": "gpu-beta",
            "addonTemplateLogo": "",
            "addonTemplateType": "helm",
            "values": {
                "basic": {
                    "rbac_enabled": true,
                    "swr_user": "hwofficial",
                    "swr_addr": "10.125.6.246:20202"
                }
            },
            "description": "A device plugin for nvidia.com/gpu resource on nvidia driver",
            "addonTemplateLabels": [
                "Accelerator"
            ],
            "clusterID": "0c0e4a63-5539-11e9-95f7-0255ac10177e",
            "version": "1.0.0"
        },
        "status": {
            "message": "",
            "Reason": "",
            "currentVersion": {
                "input": {
                    "basic": {
                        "swr_user": "hwofficial",
                        "swr_addr": "10.125.6.246:20202"
                    },
                    "parameters": {}
                },
                "stable": true,
                "creationTimestamp": "2018-10-23T13:14:55Z",
                "version": "1.0.0",
                "translate": {
                    "en_US": {
                        "addon": {
                            "changeLog": "A device plugin for nvidia.com/gpu resource on nvidia driver",
                            "description": "A device plugin for nvidia.com/gpu resource on nvidia driver"
                        }
                    },
                    "zh_CN": {
                        "addon": {
                            "changeLog": "",
                            "description": ""
                        }
                    }
                },
                "updateTimestamp": "2018-12-07T09:40:24Z"
            },
            "status": "installing"
        }
    }
    ```

-   状态码为 500 时

    ```
    {
    	"code":"SVCSTG.CCE-ADDONMGR.500",
    	"message":"internal error"
    }
    ```


## 状态码<a name="section117635504719"></a>

**表 11**  状态码

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

## 错误码<a name="section7765250774"></a>

**表 12**  错误码

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

