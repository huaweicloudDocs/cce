# 列出Service<a name="cce_02_0030"></a>

## 功能介绍<a name="s736281ff6cae4504a1799269e854cea4"></a>

该API用于获取集群中的Service列表。

## URI<a name="s82950b8ceaeb46a289e0b2df893ab41a"></a>

GET /api/v1/services

[表1](#zh-cn_topic_0079615003_table12028692)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615003_table12028692"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615003_row28117851"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615003_p62953453"><a name="zh-cn_topic_0079615003_p62953453"></a><a name="zh-cn_topic_0079615003_p62953453"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="27.27272727272727%" id="mcps1.2.4.1.2"><p id="p9699704195439"><a name="p9699704195439"></a><a name="p9699704195439"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="39.39393939393939%" id="mcps1.2.4.1.3"><p id="p47478553195439"><a name="p47478553195439"></a><a name="p47478553195439"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615003_row62894678"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615003_p61304121"><a name="zh-cn_topic_0079615003_p61304121"></a><a name="zh-cn_topic_0079615003_p61304121"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="27.27272727272727%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615003_p66686806"><a name="zh-cn_topic_0079615003_p66686806"></a><a name="zh-cn_topic_0079615003_p66686806"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615003_p32922195"><a name="zh-cn_topic_0079615003_p32922195"></a><a name="zh-cn_topic_0079615003_p32922195"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615003_row27864301"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615003_p42415902"><a name="zh-cn_topic_0079615003_p42415902"></a><a name="zh-cn_topic_0079615003_p42415902"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="27.27272727272727%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615003_p13136003"><a name="zh-cn_topic_0079615003_p13136003"></a><a name="zh-cn_topic_0079615003_p13136003"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615003_p57383300"><a name="zh-cn_topic_0079615003_p57383300"></a><a name="zh-cn_topic_0079615003_p57383300"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615003_row46687659"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615003_p23604067"><a name="zh-cn_topic_0079615003_p23604067"></a><a name="zh-cn_topic_0079615003_p23604067"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="27.27272727272727%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615003_p32881259"><a name="zh-cn_topic_0079615003_p32881259"></a><a name="zh-cn_topic_0079615003_p32881259"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615003_p46136299"><a name="zh-cn_topic_0079615003_p46136299"></a><a name="zh-cn_topic_0079615003_p46136299"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615003_row12573512"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615003_p11821552"><a name="zh-cn_topic_0079615003_p11821552"></a><a name="zh-cn_topic_0079615003_p11821552"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="27.27272727272727%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615003_p18021669"><a name="zh-cn_topic_0079615003_p18021669"></a><a name="zh-cn_topic_0079615003_p18021669"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615003_p50469070"><a name="zh-cn_topic_0079615003_p50469070"></a><a name="zh-cn_topic_0079615003_p50469070"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615003_row51568450"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615003_p16294901"><a name="zh-cn_topic_0079615003_p16294901"></a><a name="zh-cn_topic_0079615003_p16294901"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="27.27272727272727%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615003_p44818576"><a name="zh-cn_topic_0079615003_p44818576"></a><a name="zh-cn_topic_0079615003_p44818576"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615003_p6426044"><a name="zh-cn_topic_0079615003_p6426044"></a><a name="zh-cn_topic_0079615003_p6426044"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615003_row57834400"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615003_p54074791"><a name="zh-cn_topic_0079615003_p54074791"></a><a name="zh-cn_topic_0079615003_p54074791"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="27.27272727272727%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615003_p17981971"><a name="zh-cn_topic_0079615003_p17981971"></a><a name="zh-cn_topic_0079615003_p17981971"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615003_p47253580"><a name="zh-cn_topic_0079615003_p47253580"></a><a name="zh-cn_topic_0079615003_p47253580"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="ra3c1878c796b4f2abccbfa07d60b9bf4"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615003_p89223287542"><a name="zh-cn_topic_0079615003_p89223287542"></a><a name="zh-cn_topic_0079615003_p89223287542"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="27.27272727272727%" headers="mcps1.2.4.1.2 "><p id="abff098a626ba448fba969c7777fa8f89"><a name="abff098a626ba448fba969c7777fa8f89"></a><a name="abff098a626ba448fba969c7777fa8f89"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.4.1.3 "><p id="a7bd008baf20d47ddbf6197fd1a933fe0"><a name="a7bd008baf20d47ddbf6197fd1a933fe0"></a><a name="a7bd008baf20d47ddbf6197fd1a933fe0"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s9f8bbef4c3b44d0585c0f8b6b4b4fcb2"></a>

N/A

## 响应消息<a name="s8ec496224893446e8c1e890f065f8589"></a>

**响应参数：**

响应参数的详细描述请参见[表2](列出指定Namespace下的Service.md#zh-cn_topic_0079614912_ref458774242)。

**响应示例：**

```
{ 
   "kind": "ServiceList", 
   "apiVersion": "v1", 
   "metadata": { 
     "selfLink": "/api/v1/services", 
     "resourceVersion": "1244" 
   }, 
   "items": [ 
     { 
       "metadata": { 
         "name": "kubernetes", 
         "namespace": "default", 
         "selfLink": "/api/v1/namespaces/default/services/kubernetes", 
         "uid": "a50a2352-5d0b-11e6-aeb9-286ed488fafe", 
         "resourceVersion": "8", 
         "creationTimestamp": "2016-08-08T01:58:47Z", 
         "labels": { 
           "component": "apiserver", 
           "provider": "kubernetes" 
         } 
       }, 
       "spec": { 
         "ports": [ 
           { 
             "name": "https", 
             "protocol": "TCP", 
             "port": 443, 
             "targetPort": 443 
           } 
         ], 
         "clusterIP": "10.0.0.1", 
         "type": "ClusterIP", 
         "sessionAffinity": "None" 
       }, 
       "status": { 
         "loadBalancer": {} 
       } 
     }, 
     { 
       "metadata": { 
         "name": "myapp", 
         "namespace": "default", 
         "selfLink": "/api/v1/namespaces/default/services/myapp", 
         "uid": "58b5ca7c-5d12-11e6-aeb9-286ed488fafe", 
         "resourceVersion": "1204", 
         "creationTimestamp": "2016-08-08T02:46:46Z" 
       }, 
       "spec": { 
         "ports": [ 
           { 
             "protocol": "TCP", 
             "port": 80, 
             "targetPort": 80 
           } 
         ], 
         "selector": { 
           "app": "example" 
         }, 
         "clusterIP": "10.0.0.139", 
         "type": "ClusterIP", 
         "sessionAffinity": "None" 
       }, 
       "status": { 
         "loadBalancer": {} 
       } 
     } 
   ] 
 }
```

## 状态码<a name="s8fa10dad0efe4ace92835bdac8d7c16e"></a>

[表2](#zh-cn_topic_0079615003_table41149367)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615003_table41149367"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615003_row22020160"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p23604512195439"><a name="p23604512195439"></a><a name="p23604512195439"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p32917320195439"><a name="p32917320195439"></a><a name="p32917320195439"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615003_row39488647"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615003_p44463832"><a name="zh-cn_topic_0079615003_p44463832"></a><a name="zh-cn_topic_0079615003_p44463832"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615003_p44800605"><a name="zh-cn_topic_0079615003_p44800605"></a><a name="zh-cn_topic_0079615003_p44800605"></a>This operation succeeds, and a group of Service resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

