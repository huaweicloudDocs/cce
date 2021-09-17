# 查询AddonTemplates列表<a name="cce_02_0321"></a>

## 功能介绍

插件模板查询接口，查询插件信息。

## 调试

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?product=CCE&api=ListAddonTemplates)中调试该接口。

## URI

GET /api/v3/addontemplates

**表 1**  Query参数

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
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>addon_template_name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>指定的模板名称，不填写则查询列表。</p>
<p>最小长度：<strong>2</strong></p>
<p>最大长度：<strong>30</strong></p>
</td>
</tr>
</tbody>
</table>

## 请求参数

**表 2**  请求Header参数

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

## 响应参数

**状态码： 200**

**表 3**  响应Body参数

<a name="response_AddonTemplates"></a>
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
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>items</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of <a href="#response_AddonTemplate">AddonTemplate</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件模板列表</p>
</td>
</tr>
</tbody>
</table>

**表 4**  AddonTemplate

<a name="response_AddonTemplate"></a>
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
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p><a href="#response_Templatespec">Templatespec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>spec是集合类的元素类型，内容为插件模板具体信息，插件模板的详细描述主体部分都在spec中给出</p>
</td>
</tr>
</tbody>
</table>

**表 5**  Metadata

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

**表 6**  Templatespec

<a name="response_Templatespec"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>模板类型（helm，static）</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>require</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>是否为必安装插件</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>模板所属分组</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>logoURL</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>Logo图片地址</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>readmeURL</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>插件详情描述及使用说明</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>description</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>模板描述</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>versions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of <a href="#response_Versions">Versions</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>模板具体版本详情</p>
</td>
</tr>
</tbody>
</table>

**表 7**  Versions

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

**表 8**  SupportVersions

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

无

## 响应示例

**状态码： 200**

OK

```
{
  "kind" : "Addon",
  "apiVersion" : "v3",
  "items" : [ {
    "kind" : "Addon",
    "apiVersion" : "v3",
    "metadata" : {
      "uid" : "web-terminal",
      "name" : "web-terminal",
      "creationTimestamp" : "2019-01-07T13:22:48Z",
      "updateTimestamp" : "2019-03-28T06:52:58Z"
    },
    "spec" : {
      "type" : "helm",
      "labels" : [ "Maintenance" ],
      "logoURL" : "https://192.149.48.66/cce-addon-southchina-aw1hz2u/web-terminallogo.svg",
      "readmeURL" : "https://192.149.48.66/cce-addon-southchina-y24tcmvhzg1l/web-terminalcn-readme.md##https://192.149.48.66/cce-addon-southchina-zw4tcmvhzg1l/web-terminalen-readme.md",
      "description" : "A plug-in that allows users to run kubectl commands using a web browser.",
      "versions" : [ {
        "version" : "1.0.0",
        "input" : {
          "basic" : {
            "euleros_version" : "2.2.5",
            "swr_addr" : "100.125.6.246:20202",
            "swr_user" : "hwofficial"
          },
          "parameters" : {
            "custom" : {
              "password" : "hwcloud_cce"
            },
            "flavor1" : {
              "description" : "Has only one instance",
              "name" : "Single",
              "replicas" : 1,
              "resources" : [ {
                "limitsCpu" : "200m",
                "limitsMem" : "512Mi",
                "name" : "web-terminal",
                "requestsCpu" : "100m",
                "requestsMem" : "256Mi"
              } ]
            }
          }
        },
        "stable" : true,
        "translate" : {
          "en_US" : {
            "addon" : {
              "changeLog" : "none",
              "description" : "A plug-in that allows users to run kubectl commands using a web browser."
            },
            "description" : {
              "Parameters.flavor1.description" : "Deploy with one instance",
              "Parameters.flavor1.name" : "Single"
            },
            "key" : {
              "Parameters.custom.password" : "password"
            }
          },
          "zh_CN" : {
            "addon" : {
              "changeLog" : "无",
              "description" : "一款支持在web界面上使用kubectl的插件。"
            },
            "description" : {
              "Parameters.flavor1.description" : "单实例部署",
              "Parameters.flavor1.name" : "单实例"
            },
            "key" : {
              "Parameters.custom.password" : "密码"
            }
          }
        },
        "supportVersions" : [ {
          "clusterType" : "VirtualMachine",
          "clusterVersion" : [ "v1.(9|11).*" ]
        }, {
          "clusterType" : "BareMetal",
          "clusterVersion" : [ "v1.(9|11).*" ]
        } ],
        "creationTimestamp" : "2019-01-07T13:22:48Z",
        "updateTimestamp" : "2019-02-22T07:01:16Z"
      }, {
        "version" : "1.0.1",
        "input" : {
          "basic" : {
            "euleros_version" : "2.2.5",
            "rbac_enabled" : true,
            "swr_addr" : "100.125.6.246:20202",
            "swr_user" : "hwofficial"
          },
          "parameters" : {
            "custom" : {
              "elbClass" : "union",
              "elbID" : 0,
              "loadBalancerIP" : "127.0.0.1",
              "password" : "hwcloud_cce",
              "port" : 3000,
              "serviceType" : "NodePort",
              "targetPort" : 3000
            },
            "flavor1" : {
              "description" : "Has only one instance",
              "name" : "Single",
              "replicas" : 1,
              "resources" : [ {
                "limitsCpu" : "200m",
                "limitsMem" : "512Mi",
                "name" : "web-terminal",
                "requestsCpu" : "100m",
                "requestsMem" : "256Mi"
              } ]
            }
          }
        },
        "stable" : true,
        "translate" : {
          "en_US" : {
            "addon" : {
              "changeLog" : "1.include service creation  2.simplify operation  3.support access via elb",
              "description" : "A plug-in that allows users to run kubectl commands using a web browser."
            },
            "description" : {
              "Parameters.custom.serviceType" : "Service type for accessing web-terminal",
              "Parameters.flavor1.description" : "Deploy with one instance",
              "Parameters.flavor1.name" : "Single"
            },
            "key" : {
              "Parameters.custom.serviceType" : "Access type"
            }
          },
          "zh_CN" : {
            "addon" : {
              "changeLog" : "1.包含service创建  2.操作简化  3.支持通过elb访问",
              "description" : "一款支持在web界面上使用kubectl的插件。"
            },
            "description" : {
              "Parameters.custom.serviceType" : "访问web-terminal的service类型",
              "Parameters.flavor1.description" : "单实例部署",
              "Parameters.flavor1.name" : "单实例"
            },
            "key" : {
              "Parameters.custom.serviceType" : "访问类型"
            }
          }
        },
        "supportVersions" : [ {
          "clusterType" : "VirtualMachine",
          "clusterVersion" : [ "v1.(9|11).*" ]
        }, {
          "clusterType" : "BareMetal",
          "clusterVersion" : [ "v1.(9|11).*" ]
        } ],
        "creationTimestamp" : "2019-03-28T06:52:57Z",
        "updateTimestamp" : "2019-03-28T06:52:57Z"
      } ]
    }
  } ]
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

