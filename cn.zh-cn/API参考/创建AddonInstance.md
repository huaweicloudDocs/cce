# 创建AddonInstance<a name="cce_02_0322"></a>

## 功能描述<a name="section592712481477"></a>

根据提供的插件模板，安装插件实例。

## URI<a name="section79287481718"></a>

POST /api/v3/addons

## 请求消息<a name="section8930154813719"></a>

**请求参数：**

请求参数如[表1](#HeaderParameter)所示。

**表 1**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row199321948779"><th class="cellrowborder" valign="top" width="16.048395160483953%" id="mcps1.2.5.1.1"><p id="p129387486710"><a name="p129387486710"></a><a name="p129387486710"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.108789121087892%" id="mcps1.2.5.1.2"><p id="p13984162219525"><a name="p13984162219525"></a><a name="p13984162219525"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="21.817818218178182%" id="mcps1.2.5.1.3"><p id="p79381481074"><a name="p79381481074"></a><a name="p79381481074"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.02499750024997%" id="mcps1.2.5.1.4"><p id="p15942348876"><a name="p15942348876"></a><a name="p15942348876"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row179328481172"><td class="cellrowborder" valign="top" width="16.048395160483953%" headers="mcps1.2.5.1.1 "><p id="p89441048070"><a name="p89441048070"></a><a name="p89441048070"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="12.108789121087892%" headers="mcps1.2.5.1.2 "><p id="p1957511359529"><a name="p1957511359529"></a><a name="p1957511359529"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.817818218178182%" headers="mcps1.2.5.1.3 "><p id="p1794524819715"><a name="p1794524819715"></a><a name="p1794524819715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.02499750024997%" headers="mcps1.2.5.1.4 "><p id="p1994713481677"><a name="p1994713481677"></a><a name="p1994713481677"></a>消息体的类型（格式），下方类型可任选其一使用：</p>
<a name="ul59661538264"></a><a name="ul59661538264"></a><ul id="ul59661538264"><li>application/json;charset=utf-8</li><li>application/json</li></ul>
</td>
</tr>
<tr id="row79335489710"><td class="cellrowborder" valign="top" width="16.048395160483953%" headers="mcps1.2.5.1.1 "><p id="p1394920485711"><a name="p1394920485711"></a><a name="p1394920485711"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="12.108789121087892%" headers="mcps1.2.5.1.2 "><p id="p7575193505212"><a name="p7575193505212"></a><a name="p7575193505212"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.817818218178182%" headers="mcps1.2.5.1.3 "><p id="p16951948170"><a name="p16951948170"></a><a name="p16951948170"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.02499750024997%" headers="mcps1.2.5.1.4 "><p id="p395314810714"><a name="p395314810714"></a><a name="p395314810714"></a>调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="认证鉴权.md#section2417768214391">获取token</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  请求Body参数

<a name="requestParameter"></a>
<table><thead align="left"><tr id="row119542487717"><th class="cellrowborder" valign="top" width="15.25%" id="mcps1.2.5.1.1"><p id="p6958154810714"><a name="p6958154810714"></a><a name="p6958154810714"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.48%" id="mcps1.2.5.1.2"><p id="p173761159135210"><a name="p173761159135210"></a><a name="p173761159135210"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.32%" id="mcps1.2.5.1.3"><p id="p69592483714"><a name="p69592483714"></a><a name="p69592483714"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p179607481978"><a name="p179607481978"></a><a name="p179607481978"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row195534816713"><td class="cellrowborder" valign="top" width="15.25%" headers="mcps1.2.5.1.1 "><p id="p159613480713"><a name="p159613480713"></a><a name="p159613480713"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="16.48%" headers="mcps1.2.5.1.2 "><p id="p2089971265312"><a name="p2089971265312"></a><a name="p2089971265312"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.32%" headers="mcps1.2.5.1.3 "><p id="p49628487711"><a name="p49628487711"></a><a name="p49628487711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p199661648677"><a name="p199661648677"></a><a name="p199661648677"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row59554481671"><td class="cellrowborder" valign="top" width="15.25%" headers="mcps1.2.5.1.1 "><p id="p89671048679"><a name="p89671048679"></a><a name="p89671048679"></a>apVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.48%" headers="mcps1.2.5.1.2 "><p id="p11899712165312"><a name="p11899712165312"></a><a name="p11899712165312"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.32%" headers="mcps1.2.5.1.3 "><p id="p18969184813710"><a name="p18969184813710"></a><a name="p18969184813710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p897024815715"><a name="p897024815715"></a><a name="p897024815715"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row99552483717"><td class="cellrowborder" valign="top" width="15.25%" headers="mcps1.2.5.1.1 "><p id="p1097119489714"><a name="p1097119489714"></a><a name="p1097119489714"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="16.48%" headers="mcps1.2.5.1.2 "><p id="p12899171275311"><a name="p12899171275311"></a><a name="p12899171275311"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.32%" headers="mcps1.2.5.1.3 "><p id="p3972448871"><a name="p3972448871"></a><a name="p3972448871"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p7974134814712"><a name="p7974134814712"></a><a name="p7974134814712"></a>安装：固定值为{"addon.install/type":"install"}</p>
<p id="p169745481073"><a name="p169745481073"></a><a name="p169745481073"></a>升级：固定值为{"addon.upgrade/type":"upgrade"}</p>
</td>
</tr>
<tr id="row1395534813720"><td class="cellrowborder" valign="top" width="15.25%" headers="mcps1.2.5.1.1 "><p id="p997519485712"><a name="p997519485712"></a><a name="p997519485712"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="16.48%" headers="mcps1.2.5.1.2 "><p id="p178990129538"><a name="p178990129538"></a><a name="p178990129538"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.32%" headers="mcps1.2.5.1.3 "><p id="p4976174810710"><a name="p4976174810710"></a><a name="p4976174810710"></a><a href="#instancerequestspec">instancerequestspec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p597713489716"><a name="p597713489716"></a><a name="p597713489716"></a>spec是集合类的元素类型，内容为插件实例安装/升级的具体请求信息。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  instancerequestspec

<a name="instancerequestspec"></a>
<table><thead align="left"><tr id="row39791448178"><th class="cellrowborder" valign="top" width="17.83%" id="mcps1.2.5.1.1"><p id="p09821648578"><a name="p09821648578"></a><a name="p09821648578"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.340000000000002%" id="mcps1.2.5.1.2"><p id="p173129382537"><a name="p173129382537"></a><a name="p173129382537"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.879999999999999%" id="mcps1.2.5.1.3"><p id="p398317488716"><a name="p398317488716"></a><a name="p398317488716"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p09841248377"><a name="p09841248377"></a><a name="p09841248377"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6979134816713"><td class="cellrowborder" valign="top" width="17.83%" headers="mcps1.2.5.1.1 "><p id="p1698511482716"><a name="p1698511482716"></a><a name="p1698511482716"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="15.340000000000002%" headers="mcps1.2.5.1.2 "><p id="p2511648115318"><a name="p2511648115318"></a><a name="p2511648115318"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.879999999999999%" headers="mcps1.2.5.1.3 "><p id="p189852481277"><a name="p189852481277"></a><a name="p189852481277"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p16987174816719"><a name="p16987174816719"></a><a name="p16987174816719"></a>待安装、升级插件的具体版本版本号，例如1.0.0</p>
</td>
</tr>
<tr id="row59809481715"><td class="cellrowborder" valign="top" width="17.83%" headers="mcps1.2.5.1.1 "><p id="p1898818487713"><a name="p1898818487713"></a><a name="p1898818487713"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="15.340000000000002%" headers="mcps1.2.5.1.2 "><p id="p3511184818532"><a name="p3511184818532"></a><a name="p3511184818532"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.879999999999999%" headers="mcps1.2.5.1.3 "><p id="p199888481471"><a name="p199888481471"></a><a name="p199888481471"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1198919481710"><a name="p1198919481710"></a><a name="p1198919481710"></a>集群id</p>
</td>
</tr>
<tr id="row298084819719"><td class="cellrowborder" valign="top" width="17.83%" headers="mcps1.2.5.1.1 "><p id="p699014481574"><a name="p699014481574"></a><a name="p699014481574"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="15.340000000000002%" headers="mcps1.2.5.1.2 "><p id="p19511248185314"><a name="p19511248185314"></a><a name="p19511248185314"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.879999999999999%" headers="mcps1.2.5.1.3 "><p id="p19990144820711"><a name="p19990144820711"></a><a name="p19990144820711"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1299216482716"><a name="p1299216482716"></a><a name="p1299216482716"></a>待安装或升级模板的具体请求参数，一般为配置文件，各插件不同</p>
</td>
</tr>
<tr id="row189802481479"><td class="cellrowborder" valign="top" width="17.83%" headers="mcps1.2.5.1.1 "><p id="p9993104815714"><a name="p9993104815714"></a><a name="p9993104815714"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="15.340000000000002%" headers="mcps1.2.5.1.2 "><p id="p2051154811532"><a name="p2051154811532"></a><a name="p2051154811532"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.879999999999999%" headers="mcps1.2.5.1.3 "><p id="p39933485713"><a name="p39933485713"></a><a name="p39933485713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1899516487714"><a name="p1899516487714"></a><a name="p1899516487714"></a>待安装插件模板名称，如coredns</p>
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

## 响应消息<a name="section10996248672"></a>

**响应参数：**

响应参数请参见[表4](#responseParameter)。

**表 4**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row1399914481277"><th class="cellrowborder" valign="top" width="16.93%" id="mcps1.2.5.1.1"><p id="p151449979"><a name="p151449979"></a><a name="p151449979"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.040000000000001%" id="mcps1.2.5.1.2"><p id="p1098515414544"><a name="p1098515414544"></a><a name="p1098515414544"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.080000000000002%" id="mcps1.2.5.1.3"><p id="p62049978"><a name="p62049978"></a><a name="p62049978"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p939497717"><a name="p939497717"></a><a name="p939497717"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row139995489718"><td class="cellrowborder" valign="top" width="16.93%" headers="mcps1.2.5.1.1 "><p id="p74549672"><a name="p74549672"></a><a name="p74549672"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="15.040000000000001%" headers="mcps1.2.5.1.2 "><p id="p199817169540"><a name="p199817169540"></a><a name="p199817169540"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.080000000000002%" headers="mcps1.2.5.1.3 "><p id="p1951249076"><a name="p1951249076"></a><a name="p1951249076"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p864491718"><a name="p864491718"></a><a name="p864491718"></a>API类型，固定值“Addon”，该值不可修改。</p>
</td>
</tr>
<tr id="row10549478"><td class="cellrowborder" valign="top" width="16.93%" headers="mcps1.2.5.1.1 "><p id="p271249474"><a name="p271249474"></a><a name="p271249474"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.040000000000001%" headers="mcps1.2.5.1.2 "><p id="p29891625411"><a name="p29891625411"></a><a name="p29891625411"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.080000000000002%" headers="mcps1.2.5.1.3 "><p id="p2070491873"><a name="p2070491873"></a><a name="p2070491873"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p591249673"><a name="p591249673"></a><a name="p591249673"></a>API版本，固定值“v3”，该值不可修改。</p>
</td>
</tr>
<tr id="row1704497713"><td class="cellrowborder" valign="top" width="16.93%" headers="mcps1.2.5.1.1 "><p id="p191010491071"><a name="p191010491071"></a><a name="p191010491071"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="15.040000000000001%" headers="mcps1.2.5.1.2 "><p id="p11981716185412"><a name="p11981716185412"></a><a name="p11981716185412"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.080000000000002%" headers="mcps1.2.5.1.3 "><p id="p81117494719"><a name="p81117494719"></a><a name="p81117494719"></a><a href="#response_metadata">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p19131949371"><a name="p19131949371"></a><a name="p19131949371"></a>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性。</p>
</td>
</tr>
<tr id="row30149176"><td class="cellrowborder" valign="top" width="16.93%" headers="mcps1.2.5.1.1 "><p id="p7141449474"><a name="p7141449474"></a><a name="p7141449474"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="15.040000000000001%" headers="mcps1.2.5.1.2 "><p id="p109817163547"><a name="p109817163547"></a><a name="p109817163547"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.080000000000002%" headers="mcps1.2.5.1.3 "><p id="p2151049772"><a name="p2151049772"></a><a name="p2151049772"></a><a href="#response_instanceSpec">instanceSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p116154914718"><a name="p116154914718"></a><a name="p116154914718"></a>spec是集合类的元素类型，内容为插件实例具体信息，实例的详细描述主体部分都在spec中给出。</p>
</td>
</tr>
<tr id="row12014492720"><td class="cellrowborder" valign="top" width="16.93%" headers="mcps1.2.5.1.1 "><p id="p71714494710"><a name="p71714494710"></a><a name="p71714494710"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="15.040000000000001%" headers="mcps1.2.5.1.2 "><p id="p129871685412"><a name="p129871685412"></a><a name="p129871685412"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.080000000000002%" headers="mcps1.2.5.1.3 "><p id="p1218349175"><a name="p1218349175"></a><a name="p1218349175"></a><a href="#response_status">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p21910491473"><a name="p21910491473"></a><a name="p21910491473"></a>插件实例状态。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  status

<a name="response_status"></a>
<table><thead align="left"><tr id="row102118492713"><th class="cellrowborder" valign="top" width="17.57%" id="mcps1.2.5.1.1"><p id="p1125194918720"><a name="p1125194918720"></a><a name="p1125194918720"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="11.1%" id="mcps1.2.5.1.2"><p id="p151101715205514"><a name="p151101715205514"></a><a name="p151101715205514"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.3"><p id="p92515491073"><a name="p92515491073"></a><a name="p92515491073"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p14266491275"><a name="p14266491275"></a><a name="p14266491275"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row152234915711"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p172717497719"><a name="p172717497719"></a><a name="p172717497719"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="11.1%" headers="mcps1.2.5.1.2 "><p id="p1352152375514"><a name="p1352152375514"></a><a name="p1352152375514"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p828104910714"><a name="p828104910714"></a><a name="p828104910714"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p6298492710"><a name="p6298492710"></a><a name="p6298492710"></a>插件实例状态</p>
</td>
</tr>
<tr id="row1622134914718"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p123011491678"><a name="p123011491678"></a><a name="p123011491678"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="11.1%" headers="mcps1.2.5.1.2 "><p id="p1135216234558"><a name="p1135216234558"></a><a name="p1135216234558"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p13044913719"><a name="p13044913719"></a><a name="p13044913719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p12322491715"><a name="p12322491715"></a><a name="p12322491715"></a>插件安装失败原因</p>
</td>
</tr>
<tr id="row9221049679"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p153214913718"><a name="p153214913718"></a><a name="p153214913718"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="11.1%" headers="mcps1.2.5.1.2 "><p id="p1635242314553"><a name="p1635242314553"></a><a name="p1635242314553"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p6330491979"><a name="p6330491979"></a><a name="p6330491979"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p834049673"><a name="p834049673"></a><a name="p834049673"></a>安装错误详情</p>
</td>
</tr>
<tr id="row92213491178"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p0355491714"><a name="p0355491714"></a><a name="p0355491714"></a>targetVersions</p>
</td>
<td class="cellrowborder" valign="top" width="11.1%" headers="mcps1.2.5.1.2 "><p id="p1935232313553"><a name="p1935232313553"></a><a name="p1935232313553"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p6363496720"><a name="p6363496720"></a><a name="p6363496720"></a>Array&nbsp;of&nbsp;strings</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p93714495711"><a name="p93714495711"></a><a name="p93714495711"></a>此插件版本，支持升级的集群版本</p>
</td>
</tr>
<tr id="row22313493710"><td class="cellrowborder" valign="top" width="17.57%" headers="mcps1.2.5.1.1 "><p id="p73716491719"><a name="p73716491719"></a><a name="p73716491719"></a>currentVersion</p>
</td>
<td class="cellrowborder" valign="top" width="11.1%" headers="mcps1.2.5.1.2 "><p id="p2035342315553"><a name="p2035342315553"></a><a name="p2035342315553"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.3 "><p id="p13385491275"><a name="p13385491275"></a><a name="p13385491275"></a><a href="#response_versions">versions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p239749079"><a name="p239749079"></a><a name="p239749079"></a>当前插件实例使用的具体插件版本信息</p>
</td>
</tr>
</tbody>
</table>

**表 6**  versions

<a name="response_versions"></a>
<table><thead align="left"><tr id="row74013491973"><th class="cellrowborder" valign="top" width="18.86%" id="mcps1.2.5.1.1"><p id="p13430491971"><a name="p13430491971"></a><a name="p13430491971"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.309999999999999%" id="mcps1.2.5.1.2"><p id="p027893416568"><a name="p027893416568"></a><a name="p027893416568"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.86%" id="mcps1.2.5.1.3"><p id="p944134913719"><a name="p944134913719"></a><a name="p944134913719"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.97%" id="mcps1.2.5.1.4"><p id="p15472495713"><a name="p15472495713"></a><a name="p15472495713"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row5406491177"><td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.1 "><p id="p44713491971"><a name="p44713491971"></a><a name="p44713491971"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="13.309999999999999%" headers="mcps1.2.5.1.2 "><p id="p13471164415560"><a name="p13471164415560"></a><a name="p13471164415560"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.3 "><p id="p548154913719"><a name="p548154913719"></a><a name="p548154913719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.97%" headers="mcps1.2.5.1.4 "><p id="p2507492070"><a name="p2507492070"></a><a name="p2507492070"></a>插件版本号</p>
</td>
</tr>
<tr id="row1541249775"><td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.1 "><p id="p19518491176"><a name="p19518491176"></a><a name="p19518491176"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="13.309999999999999%" headers="mcps1.2.5.1.2 "><p id="p347110444563"><a name="p347110444563"></a><a name="p347110444563"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.3 "><p id="p9517491674"><a name="p9517491674"></a><a name="p9517491674"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="48.97%" headers="mcps1.2.5.1.4 "><p id="p17551491676"><a name="p17551491676"></a><a name="p17551491676"></a>插件安装参数</p>
</td>
</tr>
<tr id="row1413491777"><td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.1 "><p id="p1455549171"><a name="p1455549171"></a><a name="p1455549171"></a>stable</p>
</td>
<td class="cellrowborder" valign="top" width="13.309999999999999%" headers="mcps1.2.5.1.2 "><p id="p12471184445610"><a name="p12471184445610"></a><a name="p12471184445610"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.3 "><p id="p1256194917712"><a name="p1256194917712"></a><a name="p1256194917712"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="48.97%" headers="mcps1.2.5.1.4 "><p id="p36210491178"><a name="p36210491178"></a><a name="p36210491178"></a>是否为稳定版本</p>
</td>
</tr>
<tr id="row8412049971"><td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.1 "><p id="p126214494711"><a name="p126214494711"></a><a name="p126214494711"></a>translate</p>
</td>
<td class="cellrowborder" valign="top" width="13.309999999999999%" headers="mcps1.2.5.1.2 "><p id="p154711344195612"><a name="p154711344195612"></a><a name="p154711344195612"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.3 "><p id="p963349876"><a name="p963349876"></a><a name="p963349876"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="48.97%" headers="mcps1.2.5.1.4 "><p id="p19651549477"><a name="p19651549477"></a><a name="p19651549477"></a>供界面使用的翻译信息</p>
</td>
</tr>
<tr id="row941049877"><td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.1 "><p id="p966154916720"><a name="p966154916720"></a><a name="p966154916720"></a>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="13.309999999999999%" headers="mcps1.2.5.1.2 "><p id="p1347134415617"><a name="p1347134415617"></a><a name="p1347134415617"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.3 "><p id="p116734915710"><a name="p116734915710"></a><a name="p116734915710"></a>Array of <a href="#response_supportVersions">supportVersions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="48.97%" headers="mcps1.2.5.1.4 "><p id="p107018492071"><a name="p107018492071"></a><a name="p107018492071"></a>支持集群版本号</p>
</td>
</tr>
<tr id="row241449670"><td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.1 "><p id="p87112494713"><a name="p87112494713"></a><a name="p87112494713"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="13.309999999999999%" headers="mcps1.2.5.1.2 "><p id="p14471144155618"><a name="p14471144155618"></a><a name="p14471144155618"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.3 "><p id="p20729496713"><a name="p20729496713"></a><a name="p20729496713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.97%" headers="mcps1.2.5.1.4 "><p id="p14741492077"><a name="p14741492077"></a><a name="p14741492077"></a>插件创建时间</p>
</td>
</tr>
<tr id="row34204918717"><td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.1 "><p id="p175849472"><a name="p175849472"></a><a name="p175849472"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="13.309999999999999%" headers="mcps1.2.5.1.2 "><p id="p34728448566"><a name="p34728448566"></a><a name="p34728448566"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.86%" headers="mcps1.2.5.1.3 "><p id="p1575249778"><a name="p1575249778"></a><a name="p1575249778"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.97%" headers="mcps1.2.5.1.4 "><p id="p137813491179"><a name="p137813491179"></a><a name="p137813491179"></a>插件更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 7**  supportVersions

<a name="response_supportVersions"></a>
<table><thead align="left"><tr id="row5793491475"><th class="cellrowborder" valign="top" width="18.16%" id="mcps1.2.5.1.1"><p id="p1081144916715"><a name="p1081144916715"></a><a name="p1081144916715"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.25%" id="mcps1.2.5.1.2"><p id="p1542185918565"><a name="p1542185918565"></a><a name="p1542185918565"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.73%" id="mcps1.2.5.1.3"><p id="p88219499719"><a name="p88219499719"></a><a name="p88219499719"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.86%" id="mcps1.2.5.1.4"><p id="p13832049170"><a name="p13832049170"></a><a name="p13832049170"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2801449877"><td class="cellrowborder" valign="top" width="18.16%" headers="mcps1.2.5.1.1 "><p id="p1684104910710"><a name="p1684104910710"></a><a name="p1684104910710"></a>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="15.25%" headers="mcps1.2.5.1.2 "><p id="p1856619611575"><a name="p1856619611575"></a><a name="p1856619611575"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.73%" headers="mcps1.2.5.1.3 "><p id="p38519499716"><a name="p38519499716"></a><a name="p38519499716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.86%" headers="mcps1.2.5.1.4 "><p id="p12866494716"><a name="p12866494716"></a><a name="p12866494716"></a>支持的集群类型</p>
</td>
</tr>
<tr id="row1180154914716"><td class="cellrowborder" valign="top" width="18.16%" headers="mcps1.2.5.1.1 "><p id="p3876495717"><a name="p3876495717"></a><a name="p3876495717"></a>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="15.25%" headers="mcps1.2.5.1.2 "><p id="p1056626125711"><a name="p1056626125711"></a><a name="p1056626125711"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.73%" headers="mcps1.2.5.1.3 "><p id="p10881749775"><a name="p10881749775"></a><a name="p10881749775"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="47.86%" headers="mcps1.2.5.1.4 "><p id="p890184917715"><a name="p890184917715"></a><a name="p890184917715"></a>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

**表 8**  instanceSpec

<a name="response_instanceSpec"></a>
<table><thead align="left"><tr id="row2934491475"><th class="cellrowborder" valign="top" width="18.69%" id="mcps1.2.5.1.1"><p id="p2097114915720"><a name="p2097114915720"></a><a name="p2097114915720"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.99%" id="mcps1.2.5.1.2"><p id="p1799411228577"><a name="p1799411228577"></a><a name="p1799411228577"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="21.44%" id="mcps1.2.5.1.3"><p id="p5986491711"><a name="p5986491711"></a><a name="p5986491711"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.879999999999995%" id="mcps1.2.5.1.4"><p id="p69919492720"><a name="p69919492720"></a><a name="p69919492720"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row893104917720"><td class="cellrowborder" valign="top" width="18.69%" headers="mcps1.2.5.1.1 "><p id="p9104114914710"><a name="p9104114914710"></a><a name="p9104114914710"></a>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="14.99%" headers="mcps1.2.5.1.2 "><p id="p167243375710"><a name="p167243375710"></a><a name="p167243375710"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.44%" headers="mcps1.2.5.1.3 "><p id="p210512491779"><a name="p210512491779"></a><a name="p210512491779"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.879999999999995%" headers="mcps1.2.5.1.4 "><p id="p210719494712"><a name="p210719494712"></a><a name="p210719494712"></a>集群id</p>
</td>
</tr>
<tr id="row6933491572"><td class="cellrowborder" valign="top" width="18.69%" headers="mcps1.2.5.1.1 "><p id="p111075491975"><a name="p111075491975"></a><a name="p111075491975"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="14.99%" headers="mcps1.2.5.1.2 "><p id="p15721433185717"><a name="p15721433185717"></a><a name="p15721433185717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.44%" headers="mcps1.2.5.1.3 "><p id="p10108174914718"><a name="p10108174914718"></a><a name="p10108174914718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.879999999999995%" headers="mcps1.2.5.1.4 "><p id="p210917491278"><a name="p210917491278"></a><a name="p210917491278"></a>插件模板版本号，如1.0.0</p>
</td>
</tr>
<tr id="row1194194911719"><td class="cellrowborder" valign="top" width="18.69%" headers="mcps1.2.5.1.1 "><p id="p141101149675"><a name="p141101149675"></a><a name="p141101149675"></a>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="14.99%" headers="mcps1.2.5.1.2 "><p id="p107293345719"><a name="p107293345719"></a><a name="p107293345719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.44%" headers="mcps1.2.5.1.3 "><p id="p12110124910716"><a name="p12110124910716"></a><a name="p12110124910716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.879999999999995%" headers="mcps1.2.5.1.4 "><p id="p17112144914711"><a name="p17112144914711"></a><a name="p17112144914711"></a>插件模板名称，如coredns</p>
</td>
</tr>
<tr id="row2944493716"><td class="cellrowborder" valign="top" width="18.69%" headers="mcps1.2.5.1.1 "><p id="p911324910719"><a name="p911324910719"></a><a name="p911324910719"></a>addonTemplateType</p>
</td>
<td class="cellrowborder" valign="top" width="14.99%" headers="mcps1.2.5.1.2 "><p id="p1772133115716"><a name="p1772133115716"></a><a name="p1772133115716"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.44%" headers="mcps1.2.5.1.3 "><p id="p15113154911719"><a name="p15113154911719"></a><a name="p15113154911719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.879999999999995%" headers="mcps1.2.5.1.4 "><p id="p201151549179"><a name="p201151549179"></a><a name="p201151549179"></a>插件模板类型</p>
</td>
</tr>
<tr id="row6940499712"><td class="cellrowborder" valign="top" width="18.69%" headers="mcps1.2.5.1.1 "><p id="p81152493718"><a name="p81152493718"></a><a name="p81152493718"></a>addonTemplateLabels</p>
</td>
<td class="cellrowborder" valign="top" width="14.99%" headers="mcps1.2.5.1.2 "><p id="p12721733115711"><a name="p12721733115711"></a><a name="p12721733115711"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="21.44%" headers="mcps1.2.5.1.3 "><p id="p1711618491372"><a name="p1711618491372"></a><a name="p1711618491372"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.879999999999995%" headers="mcps1.2.5.1.4 "><p id="p2117174912717"><a name="p2117174912717"></a><a name="p2117174912717"></a>插件模板所属类型</p>
</td>
</tr>
<tr id="row129516491176"><td class="cellrowborder" valign="top" width="18.69%" headers="mcps1.2.5.1.1 "><p id="p81188499718"><a name="p81188499718"></a><a name="p81188499718"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="14.99%" headers="mcps1.2.5.1.2 "><p id="p12729333577"><a name="p12729333577"></a><a name="p12729333577"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.44%" headers="mcps1.2.5.1.3 "><p id="p171217491179"><a name="p171217491179"></a><a name="p171217491179"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.879999999999995%" headers="mcps1.2.5.1.4 "><p id="p4122164918716"><a name="p4122164918716"></a><a name="p4122164918716"></a>插件模板描述</p>
</td>
</tr>
<tr id="row3951349875"><td class="cellrowborder" valign="top" width="18.69%" headers="mcps1.2.5.1.1 "><p id="p161222498716"><a name="p161222498716"></a><a name="p161222498716"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="14.99%" headers="mcps1.2.5.1.2 "><p id="p117253315711"><a name="p117253315711"></a><a name="p117253315711"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.44%" headers="mcps1.2.5.1.3 "><p id="p55333507718"><a name="p55333507718"></a><a name="p55333507718"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.879999999999995%" headers="mcps1.2.5.1.4 "><p id="p115348501975"><a name="p115348501975"></a><a name="p115348501975"></a>插件模板安装参数（各插件不同）</p>
</td>
</tr>
</tbody>
</table>

**表 9**  metadata

<a name="response_metadata"></a>
<table><thead align="left"><tr id="row612814920717"><th class="cellrowborder" valign="top" width="18.27%" id="mcps1.2.5.1.1"><p id="p053412504717"><a name="p053412504717"></a><a name="p053412504717"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.53%" id="mcps1.2.5.1.2"><p id="p148561930175811"><a name="p148561930175811"></a><a name="p148561930175811"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="22.48%" id="mcps1.2.5.1.3"><p id="p1053585017713"><a name="p1053585017713"></a><a name="p1053585017713"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="46.72%" id="mcps1.2.5.1.4"><p id="p10535135014714"><a name="p10535135014714"></a><a name="p10535135014714"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row121299491775"><td class="cellrowborder" valign="top" width="18.27%" headers="mcps1.2.5.1.1 "><p id="p2053519501774"><a name="p2053519501774"></a><a name="p2053519501774"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="12.53%" headers="mcps1.2.5.1.2 "><p id="p158194065817"><a name="p158194065817"></a><a name="p158194065817"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="22.48%" headers="mcps1.2.5.1.3 "><p id="p4535650777"><a name="p4535650777"></a><a name="p4535650777"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="46.72%" headers="mcps1.2.5.1.4 "><p id="p45355508720"><a name="p45355508720"></a><a name="p45355508720"></a>插件唯一id标识</p>
</td>
</tr>
<tr id="row19129249876"><td class="cellrowborder" valign="top" width="18.27%" headers="mcps1.2.5.1.1 "><p id="p19536155015714"><a name="p19536155015714"></a><a name="p19536155015714"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="12.53%" headers="mcps1.2.5.1.2 "><p id="p35810409580"><a name="p35810409580"></a><a name="p35810409580"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="22.48%" headers="mcps1.2.5.1.3 "><p id="p115361501479"><a name="p115361501479"></a><a name="p115361501479"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="46.72%" headers="mcps1.2.5.1.4 "><p id="p453665013717"><a name="p453665013717"></a><a name="p453665013717"></a>插件名称</p>
</td>
</tr>
<tr id="row1312918492718"><td class="cellrowborder" valign="top" width="18.27%" headers="mcps1.2.5.1.1 "><p id="p8536185014716"><a name="p8536185014716"></a><a name="p8536185014716"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="12.53%" headers="mcps1.2.5.1.2 "><p id="p75811408586"><a name="p75811408586"></a><a name="p75811408586"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="22.48%" headers="mcps1.2.5.1.3 "><p id="p08905564319"><a name="p08905564319"></a><a name="p08905564319"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="46.72%" headers="mcps1.2.5.1.4 "><p id="p135361450471"><a name="p135361450471"></a><a name="p135361450471"></a>插件标签，key/value对格式</p>
</td>
</tr>
<tr id="row111295491277"><td class="cellrowborder" valign="top" width="18.27%" headers="mcps1.2.5.1.1 "><p id="p553710508710"><a name="p553710508710"></a><a name="p553710508710"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="12.53%" headers="mcps1.2.5.1.2 "><p id="p145874019582"><a name="p145874019582"></a><a name="p145874019582"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="22.48%" headers="mcps1.2.5.1.3 "><p id="p153841659163118"><a name="p153841659163118"></a><a name="p153841659163118"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="46.72%" headers="mcps1.2.5.1.4 "><p id="p1553712501474"><a name="p1553712501474"></a><a name="p1553712501474"></a>插件注解，由key/value组成</p>
</td>
</tr>
<tr id="row612974915713"><td class="cellrowborder" valign="top" width="18.27%" headers="mcps1.2.5.1.1 "><p id="p145376505718"><a name="p145376505718"></a><a name="p145376505718"></a>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="12.53%" headers="mcps1.2.5.1.2 "><p id="p1758194085819"><a name="p1758194085819"></a><a name="p1758194085819"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="22.48%" headers="mcps1.2.5.1.3 "><p id="p195387504711"><a name="p195387504711"></a><a name="p195387504711"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="46.72%" headers="mcps1.2.5.1.4 "><p id="p35386503719"><a name="p35386503719"></a><a name="p35386503719"></a>插件更新时间</p>
</td>
</tr>
<tr id="row21303491177"><td class="cellrowborder" valign="top" width="18.27%" headers="mcps1.2.5.1.1 "><p id="p85382501573"><a name="p85382501573"></a><a name="p85382501573"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="12.53%" headers="mcps1.2.5.1.2 "><p id="p145814010586"><a name="p145814010586"></a><a name="p145814010586"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="22.48%" headers="mcps1.2.5.1.3 "><p id="p10538750077"><a name="p10538750077"></a><a name="p10538750077"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="46.72%" headers="mcps1.2.5.1.4 "><p id="p65392506716"><a name="p65392506716"></a><a name="p65392506716"></a>插件创建时间</p>
</td>
</tr>
</tbody>
</table>

**响应示例**：

-   状态码为 200 时

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
    				"swr_addr":"10.125.6.246:20202"
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
    					"swr_addr":"10.125.6.246:20202"
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

-   状态码为 500 时

    ```
    {
    	"code":"SVCSTG.CCE-ADDONMGR.500",
    	"message":"internal error"
    }
    ```


## 状态码<a name="section55496505712"></a>

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

## 错误码<a name="section65514502720"></a>

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

