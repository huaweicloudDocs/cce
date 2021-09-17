# 创建AddonInstance<a name="cce_02_0322"></a>

## 功能介绍

根据提供的插件模板，安装插件实例。

## 调试

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?product=CCE&api=CreateAddonInstance)中调试该接口。

## URI

POST /api/v3/addons

## 请求参数

**表 1**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>消息体的类型（格式）</p>
<p>缺省值：<strong>application/json</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>"调用接口的认证方式分为Token和AK/SK两种，如果您使用的Token方式，此参数为必填，请填写Token的值，获取方式请参见<a href="https://support.huaweicloud.com/api-cce/cce_02_0004.html#cce_02_0004__section2417768214391" target="_blank" rel="noopener noreferrer">获取token</a>。"</p>
<p>最大长度：<strong>16384</strong></p>
</td>
</tr>
</tbody>
</table>

**表 2**  请求Body参数

<a name="request_InstanceRequest"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>API类型，固定值“Addon”，该值不可修改。</p>
<p>缺省值：<strong>Addon</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>API版本，固定值“v3”，该值不可修改。</p>
<p>缺省值：<strong>v3</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p><a href="#request_Metadata">Metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p><a href="#request_InstanceRequestSpec">InstanceRequestSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>spec是集合类的元素类型，内容为插件实例安装/升级的具体请求信息</p>
</td>
</tr>
</tbody>
</table>

**表 3**  Metadata

<a name="request_Metadata"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>唯一id标识</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>插件名称</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>插件标签，key/value对格式，接口保留字段，填写不会生效</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>插件注解，由key/value组成</p>
<ul><li><p>安装：固定值为{"addon.install/type":"install"}</p>
</li><li><p>升级：固定值为{"addon.upgrade/type":"upgrade"}</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>更新时间</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>创建时间</p>
</td>
</tr>
</tbody>
</table>

**表 4**  InstanceRequestSpec

<a name="request_InstanceRequestSpec"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>待安装、升级插件的具体版本版本号，例如1.0.0</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>集群id</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>values</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>Map&lt;String,Object&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>插件模板安装参数（各插件不同），升级插件时需要填写全量安装参数，未填写参数将使用插件模板中的默认值，当前插件安装参数可通过查询插件实例接口获取。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>待安装插件模板名称，如coredns</p>
</td>
</tr>
</tbody>
</table>

## 响应参数

**状态码： 200**

**表 5**  响应Body参数

<a name="response_AddonInstance"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>API类型，固定值“Addon”，该值不可修改。</p>
<p>缺省值：<strong>Addon</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>API版本，固定值“v3”，该值不可修改。</p>
<p>缺省值：<strong>v3</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_Metadata">Metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>基本信息，为集合类的元素类型，包含一组由不同名称定义的属性</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_InstanceSpec">InstanceSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>spec是集合类的元素类型，内容为插件实例具体信息，实例的详细描述主体部分都在spec中给出</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_AddonInstanceStatus">AddonInstanceStatus</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件实例状态</p>
</td>
</tr>
</tbody>
</table>

**表 6**  Metadata

<a name="response_Metadata"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>唯一id标识</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件名称</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件标签，key/value对格式，接口保留字段，填写不会生效</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Map&lt;String,String&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件注解，由key/value组成</p>
<ul><li><p>安装：固定值为{"addon.install/type":"install"}</p>
</li><li><p>升级：固定值为{"addon.upgrade/type":"upgrade"}</p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>更新时间</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>创建时间</p>
</td>
</tr>
</tbody>
</table>

**表 7**  InstanceSpec

<a name="response_InstanceSpec"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>clusterID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>集群id</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件模板版本号，如1.0.0</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>addonTemplateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件模板名称，如coredns</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>addonTemplateType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件模板类型</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>addonTemplateLogo</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件模板logo图片的地址</p>
<p>最大长度：<strong>200</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>addonTemplateLabels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件模板所属类型</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>description</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件模板描述</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>values</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Map&lt;String,Object&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件模板安装参数（各插件不同），请根据具体插件模板信息填写安装参数。</p>
</td>
</tr>
</tbody>
</table>

**表 8**  AddonInstanceStatus

<a name="response_AddonInstanceStatus"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件实例状态</p>
<p>枚举值：</p>
<ul><li><p><strong>running</strong></p>
</li><li><p><strong>abnormal</strong></p>
</li><li><p><strong>installing</strong></p>
</li><li><p><strong>installFailed</strong></p>
</li><li><p><strong>upgrading</strong></p>
</li><li><p><strong>upgradeFailed</strong></p>
</li><li><p><strong>deleting</strong></p>
</li><li><p><strong>deleteSuccess</strong></p>
</li><li><p><strong>deleteFailed</strong></p>
</li><li><p><strong>available</strong></p>
</li><li><p><strong>rollbacking</strong></p>
</li></ul>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>Reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件安装失败原因</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>安装错误详情</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>targetVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>此插件版本，支持升级的集群版本</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>currentVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_Versions">Versions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>当前插件实例使用的具体插件版本信息</p>
</td>
</tr>
</tbody>
</table>

**表 9**  Versions

<a name="response_Versions"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件版本号</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>input</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件安装参数</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>stable</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>是否为稳定版本</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>translate</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>供界面使用的翻译信息</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>supportVersions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of <a href="#response_SupportVersions">SupportVersions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>支持集群版本号</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>创建时间</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>updateTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>更新时间</p>
</td>
</tr>
</tbody>
</table>

**表 10**  SupportVersions

<a name="response_SupportVersions"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>clusterType</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>支持的集群类型</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>clusterVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>支持的集群版本（正则表达式）</p>
</td>
</tr>
</tbody>
</table>

## 请求示例

```
{
  "kind" : "Addon",
  "apiVersion" : "v3",
  "metadata" : {
    "annotations" : {
      "addon.install/type" : "install"
    }
  },
  "spec" : {
    "addonTemplateName" : "npd",
    "clusterID" : "7fd16832-e9c1-11ea-a67b-0255ac10043d",
    "values" : {
      "basic" : {
        "rbac_enabled" : true,
        "swr_addr" : "100.125.6.246:20202",
        "swr_user" : "hwofficial"
      }
    },
    "version" : "1.13.5"
  }
}
```

## 响应示例

**状态码： 200**

OK

```
{
  "kind" : "Addon",
  "apiVersion" : "v3",
  "metadata" : {
    "uid" : "24b23108-55c0-11e9-926f-0255ac101a31",
    "name" : "gpu-beta",
    "creationTimestamp" : "2019-04-03T03:25:34Z",
    "updateTimestamp" : "2019-04-03T03:25:34Z"
  },
  "spec" : {
    "clusterID" : "0c0e4a63-5539-11e9-95f7-0255ac10177e",
    "version" : "1.0.0",
    "addonTemplateName" : "gpu-beta",
    "addonTemplateType" : "helm",
    "addonTemplateLogo" : "",
    "addonTemplateLabels" : [ "Accelerator" ],
    "description" : "A device plugin for nvidia.com/gpu resource on nvidia driver",
    "values" : {
      "basic" : {
        "rbac_enabled" : true,
        "swr_addr" : "100.125.6.246:20202",
        "swr_user" : "hwofficial"
      }
    }
  },
  "status" : {
    "status" : "installing",
    "Reason" : "",
    "message" : "",
    "targetVersions" : null,
    "currentVersion" : {
      "version" : "1.0.0",
      "input" : {
        "basic" : {
          "swr_addr" : "100.125.6.246:20202",
          "swr_user" : "hwofficial"
        },
        "parameters" : { }
      },
      "stable" : true,
      "translate" : {
        "en_US" : {
          "addon" : {
            "changeLog" : "A device plugin for nvidia.com/gpu resource on nvidia driver",
            "description" : "A device plugin for nvidia.com/gpu resource on nvidia driver"
          }
        },
        "zh_CN" : {
          "addon" : {
            "changeLog" : "支持容器里使用GPU显卡的设备管理插件，仅支持nvidia驱动",
            "description" : "支持容器里使用GPU显卡的设备管理插件，仅支持nvidia驱动"
          }
        }
      },
      "supportVersions" : null,
      "creationTimestamp" : "2018-10-23T13:14:55Z",
      "updateTimestamp" : "2018-12-07T09:40:24Z"
    }
  }
}
```

## 状态码

<a name="status_code"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p>状态码 </p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p>OK</p>
</td>
</tr>
</tbody>
</table>

## 错误码

请参见[错误码](错误码.md)。

