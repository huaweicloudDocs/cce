# 获取AddonInstance详情<a name="cce_02_0325"></a>

## 功能介绍<a name="section132251505716"></a>

获取插件实例详情

## URI<a name="section1922614501578"></a>

GET /api/v3/addons/\{id\}?cluster\_id=\{cluster\_id\}

**表 1**  路径参数

<a name="table14230135012719"></a>
<table><thead align="left"><tr id="row32281850277"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p62314501171"><a name="p62314501171"></a><a name="p62314501171"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1223195020719"><a name="p1223195020719"></a><a name="p1223195020719"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p1723310504710"><a name="p1723310504710"></a><a name="p1723310504710"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p12332501719"><a name="p12332501719"></a><a name="p12332501719"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row122920501870"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p423465011714"><a name="p423465011714"></a><a name="p423465011714"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1223420501672"><a name="p1223420501672"></a><a name="p1223420501672"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p2023525017713"><a name="p2023525017713"></a><a name="p2023525017713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p523615011714"><a name="p523615011714"></a><a name="p523615011714"></a>集群id</p>
</td>
</tr>
<tr id="row1222914501074"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p123619502072"><a name="p123619502072"></a><a name="p123619502072"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p172375508710"><a name="p172375508710"></a><a name="p172375508710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p112378501277"><a name="p112378501277"></a><a name="p112378501277"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p152383501074"><a name="p152383501074"></a><a name="p152383501074"></a>插件实例id</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section19239850779"></a>

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row1024020502719"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1324316501874"><a name="p1324316501874"></a><a name="p1324316501874"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p152431750278"><a name="p152431750278"></a><a name="p152431750278"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p20244950378"><a name="p20244950378"></a><a name="p20244950378"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p19244125020718"><a name="p19244125020718"></a><a name="p19244125020718"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1724118502077"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p112451950277"><a name="p112451950277"></a><a name="p112451950277"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p19246550670"><a name="p19246550670"></a><a name="p19246550670"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p824711501874"><a name="p824711501874"></a><a name="p824711501874"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p124811501371"><a name="p124811501371"></a><a name="p124811501371"></a>消息体的类型（格式），下方类型可任选其一使用</p>
<p id="p0250850673"><a name="p0250850673"></a><a name="p0250850673"></a>application/json;charset=utf-8</p>
<p id="p525118507713"><a name="p525118507713"></a><a name="p525118507713"></a>application/json</p>
</td>
</tr>
<tr id="row6241650672"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p425225010712"><a name="p425225010712"></a><a name="p425225010712"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p72531501718"><a name="p72531501718"></a><a name="p72531501718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p122531150878"><a name="p122531150878"></a><a name="p122531150878"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p17254155011717"><a name="p17254155011717"></a><a name="p17254155011717"></a>在华为云上调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section122556506719"></a>

状态码为 200 时:

**表 3**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row0259125011720"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p426215506713"><a name="p426215506713"></a><a name="p426215506713"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p726213501471"><a name="p726213501471"></a><a name="p726213501471"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p12632501074"><a name="p12632501074"></a><a name="p12632501074"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p42645501477"><a name="p42645501477"></a><a name="p42645501477"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row0259135019711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p172655503712"><a name="p172655503712"></a><a name="p172655503712"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p926565018713"><a name="p926565018713"></a><a name="p926565018713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p8266135010716"><a name="p8266135010716"></a><a name="p8266135010716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1726635017718"><a name="p1726635017718"></a><a name="p1726635017718"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row1625995016717"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p426725015717"><a name="p426725015717"></a><a name="p426725015717"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p52680509711"><a name="p52680509711"></a><a name="p52680509711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1026919501675"><a name="p1026919501675"></a><a name="p1026919501675"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p027013500719"><a name="p027013500719"></a><a name="p027013500719"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row1026025017720"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p52714507716"><a name="p52714507716"></a><a name="p52714507716"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p52754501476"><a name="p52754501476"></a><a name="p52754501476"></a><a href="#response_metadata">metadata</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p52771050676"><a name="p52771050676"></a><a name="p52771050676"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p627813501175"><a name="p627813501175"></a><a name="p627813501175"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr id="row32602050272"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p152791950274"><a name="p152791950274"></a><a name="p152791950274"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p628112505716"><a name="p628112505716"></a><a name="p628112505716"></a><a href="#response_instanceSpec">instanceSpec</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p10282175015720"><a name="p10282175015720"></a><a name="p10282175015720"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1828316502711"><a name="p1828316502711"></a><a name="p1828316502711"></a>spec是集合类的元素类型，内容为插件实例具体信息，实例的详细描述主体部分都在spec中给出</p>
</td>
</tr>
<tr id="row926017506714"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p928415016712"><a name="p928415016712"></a><a name="p928415016712"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p72854508712"><a name="p72854508712"></a><a name="p72854508712"></a><a href="#response_status">status</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1628755015718"><a name="p1628755015718"></a><a name="p1628755015718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p92889501379"><a name="p92889501379"></a><a name="p92889501379"></a>插件实例状态</p>
</td>
</tr>
</tbody>
</table>

**表 4**  status

<a name="response_status"></a>
<table><thead align="left"><tr id="row1129110501475"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p102992505716"><a name="p102992505716"></a><a name="p102992505716"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p123017501973"><a name="p123017501973"></a><a name="p123017501973"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p530213501979"><a name="p530213501979"></a><a name="p530213501979"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1930316508714"><a name="p1930316508714"></a><a name="p1930316508714"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row129118501474"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p530416501476"><a name="p530416501476"></a><a name="p530416501476"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p430519508715"><a name="p430519508715"></a><a name="p430519508715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p8306550272"><a name="p8306550272"></a><a name="p8306550272"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1330712505718"><a name="p1330712505718"></a><a name="p1330712505718"></a>插件实例状态</p>
</td>
</tr>
<tr id="row829235015720"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18309950271"><a name="p18309950271"></a><a name="p18309950271"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p163108505710"><a name="p163108505710"></a><a name="p163108505710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p53115501175"><a name="p53115501175"></a><a name="p53115501175"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p12312155018718"><a name="p12312155018718"></a><a name="p12312155018718"></a>插件安装失败原因</p>
</td>
</tr>
<tr id="row729219501574"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2313125015716"><a name="p2313125015716"></a><a name="p2313125015716"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1831313504715"><a name="p1831313504715"></a><a name="p1831313504715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1314145019715"><a name="p1314145019715"></a><a name="p1314145019715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p15315125019719"><a name="p15315125019719"></a><a name="p15315125019719"></a>安装错误详情</p>
</td>
</tr>
<tr id="row182939501710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p16315145010710"><a name="p16315145010710"></a><a name="p16315145010710"></a>targetVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p17316105012718"><a name="p17316105012718"></a><a name="p17316105012718"></a>Array of array</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p133163501872"><a name="p133163501872"></a><a name="p133163501872"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p93177501072"><a name="p93177501072"></a><a name="p93177501072"></a>此插件版本，支持升级的集群版本</p>
</td>
</tr>
<tr id="row129316507713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p831710501875"><a name="p831710501875"></a><a name="p831710501875"></a>currentVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p03187507711"><a name="p03187507711"></a><a name="p03187507711"></a><a href="#response_versions">versions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p153191550677"><a name="p153191550677"></a><a name="p153191550677"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p183209501713"><a name="p183209501713"></a><a name="p183209501713"></a>当前插件实例使用的具体插件版本信息</p>
</td>
</tr>
</tbody>
</table>

**表 5**  versions

<a name="response_versions"></a>
<table><thead align="left"><tr id="row18322450879"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p732825017710"><a name="p732825017710"></a><a name="p732825017710"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p433014501575"><a name="p433014501575"></a><a name="p433014501575"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p2331115013718"><a name="p2331115013718"></a><a name="p2331115013718"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p18332125015713"><a name="p18332125015713"></a><a name="p18332125015713"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row23231950379"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p143321501279"><a name="p143321501279"></a><a name="p143321501279"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p933385018717"><a name="p933385018717"></a><a name="p933385018717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p17334750476"><a name="p17334750476"></a><a name="p17334750476"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p2033525015714"><a name="p2033525015714"></a><a name="p2033525015714"></a>插件版本号</p>
</td>
</tr>
<tr id="row7323850473"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p933505016710"><a name="p933505016710"></a><a name="p933505016710"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p123361150573"><a name="p123361150573"></a><a name="p123361150573"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p63374508718"><a name="p63374508718"></a><a name="p63374508718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1333712509712"><a name="p1333712509712"></a><a name="p1333712509712"></a>插件安装参数</p>
</td>
</tr>
<tr id="row12323175016710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p193386501774"><a name="p193386501774"></a><a name="p193386501774"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p10339115020718"><a name="p10339115020718"></a><a name="p10339115020718"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p9339125020714"><a name="p9339125020714"></a><a name="p9339125020714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p2340650674"><a name="p2340650674"></a><a name="p2340650674"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row43241350975"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p14340450772"><a name="p14340450772"></a><a name="p14340450772"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p434118501272"><a name="p434118501272"></a><a name="p434118501272"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p134214500716"><a name="p134214500716"></a><a name="p134214500716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p163456506714"><a name="p163456506714"></a><a name="p163456506714"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row6324145013719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p133452502071"><a name="p133452502071"></a><a name="p133452502071"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1334645011719"><a name="p1334645011719"></a><a name="p1334645011719"></a>Array of <a href="#response_supportVersions">supportVersions</a></p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p7347135014714"><a name="p7347135014714"></a><a name="p7347135014714"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p133471504715"><a name="p133471504715"></a><a name="p133471504715"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row732518503718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1334875016713"><a name="p1334875016713"></a><a name="p1334875016713"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p734818501074"><a name="p734818501074"></a><a name="p734818501074"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p4349950377"><a name="p4349950377"></a><a name="p4349950377"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p193494506713"><a name="p193494506713"></a><a name="p193494506713"></a>创建时间</p>
</td>
</tr>
<tr id="row17325750173"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p535011501377"><a name="p535011501377"></a><a name="p535011501377"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1735016505715"><a name="p1735016505715"></a><a name="p1735016505715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p203512050177"><a name="p203512050177"></a><a name="p203512050177"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1535285015716"><a name="p1535285015716"></a><a name="p1535285015716"></a>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 6**  supportVersions

<a name="response_supportVersions"></a>
<table><thead align="left"><tr id="row1035415504718"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p935645015710"><a name="p935645015710"></a><a name="p935645015710"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p10357450274"><a name="p10357450274"></a><a name="p10357450274"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p1635775015711"><a name="p1635775015711"></a><a name="p1635775015711"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p4358350274"><a name="p4358350274"></a><a name="p4358350274"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row33544501779"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p133593505712"><a name="p133593505712"></a><a name="p133593505712"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p43600501075"><a name="p43600501075"></a><a name="p43600501075"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p123612508716"><a name="p123612508716"></a><a name="p123612508716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1361450677"><a name="p1361450677"></a><a name="p1361450677"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row3354115011714"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p536217501774"><a name="p536217501774"></a><a name="p536217501774"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p3363195019719"><a name="p3363195019719"></a><a name="p3363195019719"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14364195019717"><a name="p14364195019717"></a><a name="p14364195019717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p103652508713"><a name="p103652508713"></a><a name="p103652508713"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 7**  instanceSpec

<a name="response_instanceSpec"></a>
<table><thead align="left"><tr id="row1236845013711"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p4371135010717"><a name="p4371135010717"></a><a name="p4371135010717"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p12372155016710"><a name="p12372155016710"></a><a name="p12372155016710"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p143721750178"><a name="p143721750178"></a><a name="p143721750178"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1937315506716"><a name="p1937315506716"></a><a name="p1937315506716"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row123683501873"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p53731505719"><a name="p53731505719"></a><a name="p53731505719"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1374145016719"><a name="p1374145016719"></a><a name="p1374145016719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p73751150377"><a name="p73751150377"></a><a name="p73751150377"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1137575016713"><a name="p1137575016713"></a><a name="p1137575016713"></a>集群id</p>
</td>
</tr>
<tr id="row173684501271"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p23762501718"><a name="p23762501718"></a><a name="p23762501718"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p9377165013713"><a name="p9377165013713"></a><a name="p9377165013713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1537810501719"><a name="p1537810501719"></a><a name="p1537810501719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p133781750476"><a name="p133781750476"></a><a name="p133781750476"></a>插件模板版本号，如1.0.0</p>
</td>
</tr>
<tr id="row18368135014713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18379750378"><a name="p18379750378"></a><a name="p18379750378"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1638035010718"><a name="p1638035010718"></a><a name="p1638035010718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p15380750278"><a name="p15380750278"></a><a name="p15380750278"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p163810501071"><a name="p163810501071"></a><a name="p163810501071"></a>插件模板名称，如coredns</p>
</td>
</tr>
<tr id="row1636917506718"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p0382450172"><a name="p0382450172"></a><a name="p0382450172"></a>addonTemplateType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p938220501078"><a name="p938220501078"></a><a name="p938220501078"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p838515016717"><a name="p838515016717"></a><a name="p838515016717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p5386550472"><a name="p5386550472"></a><a name="p5386550472"></a>插件模板类型</p>
</td>
</tr>
<tr id="row73691850673"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p6387115011719"><a name="p6387115011719"></a><a name="p6387115011719"></a>addonTemplateLabels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p11389175014712"><a name="p11389175014712"></a><a name="p11389175014712"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p139116506715"><a name="p139116506715"></a><a name="p139116506715"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p183930508710"><a name="p183930508710"></a><a name="p183930508710"></a>插件模板所属类型</p>
</td>
</tr>
<tr id="row336920501711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p139455011710"><a name="p139455011710"></a><a name="p139455011710"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p43951450571"><a name="p43951450571"></a><a name="p43951450571"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p8395105018718"><a name="p8395105018718"></a><a name="p8395105018718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p5396450871"><a name="p5396450871"></a><a name="p5396450871"></a>插件模板描述</p>
</td>
</tr>
<tr id="row103697501716"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p639611501470"><a name="p639611501470"></a><a name="p639611501470"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p83984502717"><a name="p83984502717"></a><a name="p83984502717"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p1399165013716"><a name="p1399165013716"></a><a name="p1399165013716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p1340019502072"><a name="p1340019502072"></a><a name="p1340019502072"></a>插件模板安装参数（各插件不同）</p>
</td>
</tr>
</tbody>
</table>

**表 8**  metadata

<a name="response_metadata"></a>
<table><thead align="left"><tr id="row19404650575"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p114096509716"><a name="p114096509716"></a><a name="p114096509716"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1541010508718"><a name="p1541010508718"></a><a name="p1541010508718"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="10%" id="mcps1.2.5.1.3"><p id="p1641718501677"><a name="p1641718501677"></a><a name="p1641718501677"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p1142019503720"><a name="p1142019503720"></a><a name="p1142019503720"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row8405550878"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p342113501718"><a name="p342113501718"></a><a name="p342113501718"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1842305015719"><a name="p1842305015719"></a><a name="p1842305015719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p14245503715"><a name="p14245503715"></a><a name="p14245503715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p842511501178"><a name="p842511501178"></a><a name="p842511501178"></a>唯一id标识</p>
</td>
</tr>
<tr id="row44056502074"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p74271250076"><a name="p74271250076"></a><a name="p74271250076"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p17428195014719"><a name="p17428195014719"></a><a name="p17428195014719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p164288501713"><a name="p164288501713"></a><a name="p164288501713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p4429135012718"><a name="p4429135012718"></a><a name="p4429135012718"></a>插件名称</p>
</td>
</tr>
<tr id="row1140513501672"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1642925016710"><a name="p1642925016710"></a><a name="p1642925016710"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p154307508710"><a name="p154307508710"></a><a name="p154307508710"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p74311550675"><a name="p74311550675"></a><a name="p74311550675"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p114326501875"><a name="p114326501875"></a><a name="p114326501875"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row64069501975"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p543313503716"><a name="p543313503716"></a><a name="p543313503716"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p943385014716"><a name="p943385014716"></a><a name="p943385014716"></a>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p12434350973"><a name="p12434350973"></a><a name="p12434350973"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p174349501076"><a name="p174349501076"></a><a name="p174349501076"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row5406850773"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p13435195011715"><a name="p13435195011715"></a><a name="p13435195011715"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p643619501473"><a name="p643619501473"></a><a name="p643619501473"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p54362501673"><a name="p54362501673"></a><a name="p54362501673"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p24377505713"><a name="p24377505713"></a><a name="p24377505713"></a>更新时间</p>
</td>
</tr>
<tr id="row640611501171"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p3438185017710"><a name="p3438185017710"></a><a name="p3438185017710"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p164380501714"><a name="p164380501714"></a><a name="p164380501714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="10%" headers="mcps1.2.5.1.3 "><p id="p204705511676"><a name="p204705511676"></a><a name="p204705511676"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p34703510718"><a name="p34703510718"></a><a name="p34703510718"></a>创建时间</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section247018512710"></a>

无

## 响应示例<a name="section7470135119717"></a>

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

## 返回值<a name="section14766511178"></a>

<a name="table28"></a>
<table><thead align="left"><tr id="row19490145016717"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p347716518719"><a name="p347716518719"></a><a name="p347716518719"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p16477851979"><a name="p16477851979"></a><a name="p16477851979"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row6490185017713"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p2477105110711"><a name="p2477105110711"></a><a name="p2477105110711"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p20477551179"><a name="p20477551179"></a><a name="p20477551179"></a>OK</p>
</td>
</tr>
<tr id="row3490125020712"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p154771151376"><a name="p154771151376"></a><a name="p154771151376"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p1447775111717"><a name="p1447775111717"></a><a name="p1447775111717"></a>Internal Server Error</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section5477151478"></a>

<a name="table29"></a>
<table><thead align="left"><tr id="row150135013711"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.5.1.1"><p id="p447713511773"><a name="p447713511773"></a><a name="p447713511773"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.2"><p id="p174781151674"><a name="p174781151674"></a><a name="p174781151674"></a>错误码</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.3"><p id="p147812511179"><a name="p147812511179"></a><a name="p147812511179"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="35%" id="mcps1.1.5.1.4"><p id="p04783517713"><a name="p04783517713"></a><a name="p04783517713"></a>解决方案</p>
</th>
</tr>
</thead>
<tbody><tr id="row17501125011713"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p447812511973"><a name="p447812511973"></a><a name="p447812511973"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p104781251579"><a name="p104781251579"></a><a name="p104781251579"></a>400</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p84786516710"><a name="p84786516710"></a><a name="p84786516710"></a>bad request</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row2050135016717"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p1447813511678"><a name="p1447813511678"></a><a name="p1447813511678"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p547914512078"><a name="p547914512078"></a><a name="p547914512078"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p547910518711"><a name="p547910518711"></a><a name="p547910518711"></a>Authenticate failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row1450215501474"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p1647915112719"><a name="p1647915112719"></a><a name="p1647915112719"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p124794515712"><a name="p124794515712"></a><a name="p124794515712"></a>403</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p64791951172"><a name="p64791951172"></a><a name="p64791951172"></a>Authorize failed</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row45028501476"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p14479151774"><a name="p14479151774"></a><a name="p14479151774"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p047916511278"><a name="p047916511278"></a><a name="p047916511278"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p5479651774"><a name="p5479651774"></a><a name="p5479651774"></a>addon instance not exist</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
<tr id="row550214506716"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.5.1.1 "><p id="p17480145118717"><a name="p17480145118717"></a><a name="p17480145118717"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p248017519717"><a name="p248017519717"></a><a name="p248017519717"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1848085118718"><a name="p1848085118718"></a><a name="p1848085118718"></a>server internal error</p>
</td>
<td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.5.1.4 ">&nbsp;&nbsp;</td>
</tr>
</tbody>
</table>

