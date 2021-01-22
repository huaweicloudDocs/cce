# 获取指定的Endpoints<a name="cce_02_0061"></a>

## 功能介绍<a name="zh-cn_topic_0079615072_section885082"></a>

该API用于获取某个Namespace下指定的Endpoints对象。

## URI<a name="s4c063734e7b04b8aa1818085c9fdd5f3"></a>

GET /api/v1/namespaces/\{namespace\}/endpoints/\{name\}

[表1](#zh-cn_topic_0079615072_table12571834)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615072_table12571834"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615072_row52268049"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615072_p5853587"><a name="zh-cn_topic_0079615072_p5853587"></a><a name="zh-cn_topic_0079615072_p5853587"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.2"><p id="p24602870201644"><a name="p24602870201644"></a><a name="p24602870201644"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="42%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0079615072_p19119237"><a name="zh-cn_topic_0079615072_p19119237"></a><a name="zh-cn_topic_0079615072_p19119237"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615072_row5154373"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615072_p14851049"><a name="zh-cn_topic_0079615072_p14851049"></a><a name="zh-cn_topic_0079615072_p14851049"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615072_p62084314"><a name="zh-cn_topic_0079615072_p62084314"></a><a name="zh-cn_topic_0079615072_p62084314"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615072_p62773503"><a name="zh-cn_topic_0079615072_p62773503"></a><a name="zh-cn_topic_0079615072_p62773503"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615072_row28090616"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615072_p60747463"><a name="zh-cn_topic_0079615072_p60747463"></a><a name="zh-cn_topic_0079615072_p60747463"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615072_p21597503"><a name="zh-cn_topic_0079615072_p21597503"></a><a name="zh-cn_topic_0079615072_p21597503"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615072_p4567303"><a name="zh-cn_topic_0079615072_p4567303"></a><a name="zh-cn_topic_0079615072_p4567303"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615072_row41105728"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615072_p41229700"><a name="zh-cn_topic_0079615072_p41229700"></a><a name="zh-cn_topic_0079615072_p41229700"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615072_p51271404"><a name="zh-cn_topic_0079615072_p51271404"></a><a name="zh-cn_topic_0079615072_p51271404"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615072_p59343073"><a name="zh-cn_topic_0079615072_p59343073"></a><a name="zh-cn_topic_0079615072_p59343073"></a>Name of the Endpoint.</p>
</td>
</tr>
<tr id="rd4d1295455c740438ece36c229eb8c75"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615072_p145446584212"><a name="zh-cn_topic_0079615072_p145446584212"></a><a name="zh-cn_topic_0079615072_p145446584212"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615072_p15454594218"><a name="zh-cn_topic_0079615072_p15454594218"></a><a name="zh-cn_topic_0079615072_p15454594218"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615072_p135451953426"><a name="zh-cn_topic_0079615072_p135451953426"></a><a name="zh-cn_topic_0079615072_p135451953426"></a>Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615072_row798577421"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615072_p10989774219"><a name="zh-cn_topic_0079615072_p10989774219"></a><a name="zh-cn_topic_0079615072_p10989774219"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615072_p298187154210"><a name="zh-cn_topic_0079615072_p298187154210"></a><a name="zh-cn_topic_0079615072_p298187154210"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615072_p898677425"><a name="zh-cn_topic_0079615072_p898677425"></a><a name="zh-cn_topic_0079615072_p898677425"></a>Should this value be exported. Export strips fields that a user can not specify.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="se5dc3a3d39a34f22a7353e5b56820ee1"></a>

N/A

## 响应消息<a name="sb016aaee185e4c39889395b7b34f7968"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Endpoints.md#zh-cn_topic_0079614955_ref458759912)。

**响应示例：**

```
{ 
   "kind": "Endpoints", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "cluster-test", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/endpoints/cluster-test", 
     "uid": "81b1503d-5960-11e6-b444-286ed488fafe", 
     "resourceVersion": "18186", 
     "creationTimestamp": "2016-08-03T09:56:10Z" 
   }, 
   "subsets": [ 
     { 
       "addresses": [ 
         { 
           "ip": "172.16.106.152" 
         }, 
         { 
           "ip": "172.16.79.157" 
         } 
       ], 
       "ports": [ 
         { 
           "port": 1, 
           "protocol": "TCP" 
         } 
       ] 
     } 
   ] 
 }
```

## 状态码<a name="sf826b071d47f4d51bc560ff6f2ef1fbf"></a>

[表2](#zh-cn_topic_0079615072_table12672824)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615072_table12672824"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615072_row17662689"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p39753582201644"><a name="p39753582201644"></a><a name="p39753582201644"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0079615072_p55008403"><a name="zh-cn_topic_0079615072_p55008403"></a><a name="zh-cn_topic_0079615072_p55008403"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615072_row26495667"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615072_p65774263"><a name="zh-cn_topic_0079615072_p65774263"></a><a name="zh-cn_topic_0079615072_p65774263"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615072_p26115080"><a name="zh-cn_topic_0079615072_p26115080"></a><a name="zh-cn_topic_0079615072_p26115080"></a>This operation succeeds, and an Endpoint resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

