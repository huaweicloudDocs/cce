# 查询API版本信息列表<a name="ShowVersion"></a>

## 功能介绍<a name="section594314711356"></a>

该API用于查询CCE服务当前支持的API版本信息列表。

## 调试<a name="section119433715354"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?product=CCE&api=ShowVersion)中调试该接口，支持自动认证鉴权。API Explorer可以自动生成SDK代码示例，并提供SDK代码示例调试功能。

## URI<a name="section794427153519"></a>

GET /

## 请求参数<a name="section16945270358"></a>

无

## 响应参数<a name="section18945157103511"></a>

**状态码： 200**

**表 1**  响应Body参数

<a name="response_APIVersionList"></a>
<table><thead align="left"><tr id="row159461376353"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p189479773519"><a name="p189479773519"></a><a name="p189479773519"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p494719793512"><a name="p494719793512"></a><a name="p494719793512"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p29471373356"><a name="p29471373356"></a><a name="p29471373356"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row129467783513"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p19480713510"><a name="p19480713510"></a><a name="p19480713510"></a>versions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p49483710359"><a name="p49483710359"></a><a name="p49483710359"></a>Array of <a href="#response_APIVersionDetail">APIVersionDetail</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1094816793511"><a name="p1094816793511"></a><a name="p1094816793511"></a>API版本信息列表</p>
</td>
</tr>
</tbody>
</table>

**表 2**  APIVersionDetail

<a name="response_APIVersionDetail"></a>
<table><thead align="left"><tr id="row10949977358"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p19494714357"><a name="p19494714357"></a><a name="p19494714357"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p159501712356"><a name="p159501712356"></a><a name="p159501712356"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p4950137143519"><a name="p4950137143519"></a><a name="p4950137143519"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row139492715358"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1795014717354"><a name="p1795014717354"></a><a name="p1795014717354"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p15950197103510"><a name="p15950197103510"></a><a name="p15950197103510"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1495057153513"><a name="p1495057153513"></a><a name="p1495057153513"></a>API版本ID。例如v3。</p>
</td>
</tr>
<tr id="row129499723516"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p69510711356"><a name="p69510711356"></a><a name="p69510711356"></a>links</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p209517714351"><a name="p209517714351"></a><a name="p209517714351"></a>Array of <a href="#response_APIVersionLink">APIVersionLink</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1595114793514"><a name="p1595114793514"></a><a name="p1595114793514"></a>API版本的URL链接信息。</p>
</td>
</tr>
<tr id="row1894918714356"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1895114719354"><a name="p1895114719354"></a><a name="p1895114719354"></a>min_version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p395219713510"><a name="p395219713510"></a><a name="p395219713510"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1095247203512"><a name="p1095247203512"></a><a name="p1095247203512"></a>如果API的这个版本支持微版本，则支持最小的微版本。如果不支持微版本，这将是空字符串。</p>
</td>
</tr>
<tr id="row1194917113513"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1395217753517"><a name="p1395217753517"></a><a name="p1395217753517"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p119527711357"><a name="p119527711357"></a><a name="p119527711357"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p595211718357"><a name="p595211718357"></a><a name="p595211718357"></a>API版本的状态。 可以是：</p>
<a name="ul595312718351"></a><a name="ul595312718351"></a><ul id="ul595312718351"><li>CURRENT这是使用的API的首选版本；</li><li>SUPPORTED：这是一个较老的，但仍然支持的API版本；</li><li>DEPRECATED：一个被废弃的API版本，该版本将被删除</li></ul>
</td>
</tr>
<tr id="row10949974354"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1195467183514"><a name="p1195467183514"></a><a name="p1195467183514"></a>updated</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p495411713517"><a name="p495411713517"></a><a name="p495411713517"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p49541716353"><a name="p49541716353"></a><a name="p49541716353"></a>API发布时间（UTC格式）。例如API版本为v3时，值为'2018-09-15 00:00:00Z'。</p>
</td>
</tr>
<tr id="row199496793511"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1995477123519"><a name="p1995477123519"></a><a name="p1995477123519"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p149541979352"><a name="p149541979352"></a><a name="p149541979352"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17955674352"><a name="p17955674352"></a><a name="p17955674352"></a>如果API的这个版本支持微版本，则支持最大的微版本。如果不支持微版本，这将是空字符串。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  APIVersionLink

<a name="response_APIVersionLink"></a>
<table><thead align="left"><tr id="row1695516743515"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p595619723510"><a name="p595619723510"></a><a name="p595619723510"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1295616710358"><a name="p1295616710358"></a><a name="p1295616710358"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p14956197193518"><a name="p14956197193518"></a><a name="p14956197193518"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1595512763517"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p29568710351"><a name="p29568710351"></a><a name="p29568710351"></a>href</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16956117153512"><a name="p16956117153512"></a><a name="p16956117153512"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p59577753511"><a name="p59577753511"></a><a name="p59577753511"></a>API版本信息的链接。</p>
</td>
</tr>
<tr id="row1895597103510"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p595787103516"><a name="p595787103516"></a><a name="p595787103516"></a>rel</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1595713773516"><a name="p1595713773516"></a><a name="p1595713773516"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1595716717358"><a name="p1595716717358"></a><a name="p1595716717358"></a>链接属性。self：自助链接包含版本链接的资源。立即链接后使用这些链接。</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section8958147143514"></a>

无

## 响应示例<a name="section129581777356"></a>

**状态码： 200**

表示查询API版本信息列表成功。

```
{
  "versions" : [ {
    "id" : "v3",
    "links" : [ {
      "href" : "https://cce.region.***.com/v3",
      "rel" : "self"
    } ],
    "min_version" : "",
    "status" : "CURRENT",
    "updated" : "2018-09-15 00:00:00Z",
    "version" : ""
  } ]
}
```

## 状态码<a name="section199621713351"></a>

<a name="status_code"></a>
<table><thead align="left"><tr id="row129631271355"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p17963137123518"><a name="p17963137123518"></a><a name="p17963137123518"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p0963976358"><a name="p0963976358"></a><a name="p0963976358"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row179639717354"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p79648783513"><a name="p79648783513"></a><a name="p79648783513"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p296419717357"><a name="p296419717357"></a><a name="p296419717357"></a>表示查询API版本信息列表成功。</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section209641272358"></a>

请参见[错误码](错误码.md)。

