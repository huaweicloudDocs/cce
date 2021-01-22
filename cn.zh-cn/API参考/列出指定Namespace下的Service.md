# 列出指定Namespace下的Service<a name="cce_02_0029"></a>

## 功能介绍<a name="scd7c5d26006f4f2fa18d7944090a515a"></a>

该API用于列出指定Namespace下的Service对象。

## URI<a name="sf266bb0aca594ae0bfe7c7952d99b504"></a>

GET /api/v1/namespaces/\{namespace\}/services

[表1](#zh-cn_topic_0079614912_table30173457)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614912_table30173457"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614912_row62631706"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614912_p40003440"><a name="zh-cn_topic_0079614912_p40003440"></a><a name="zh-cn_topic_0079614912_p40003440"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="24%" id="mcps1.2.4.1.2"><p id="p55041445195410"><a name="p55041445195410"></a><a name="p55041445195410"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="43%" id="mcps1.2.4.1.3"><p id="p29172047195410"><a name="p29172047195410"></a><a name="p29172047195410"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614912_row51438757"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p5789773"><a name="zh-cn_topic_0079614912_p5789773"></a><a name="zh-cn_topic_0079614912_p5789773"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p66318445"><a name="zh-cn_topic_0079614912_p66318445"></a><a name="zh-cn_topic_0079614912_p66318445"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p3084974"><a name="zh-cn_topic_0079614912_p3084974"></a><a name="zh-cn_topic_0079614912_p3084974"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row27764770"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p34353911"><a name="zh-cn_topic_0079614912_p34353911"></a><a name="zh-cn_topic_0079614912_p34353911"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p31203392"><a name="zh-cn_topic_0079614912_p31203392"></a><a name="zh-cn_topic_0079614912_p31203392"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p44446822"><a name="zh-cn_topic_0079614912_p44446822"></a><a name="zh-cn_topic_0079614912_p44446822"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row64477079"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p55260882"><a name="zh-cn_topic_0079614912_p55260882"></a><a name="zh-cn_topic_0079614912_p55260882"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p46946462"><a name="zh-cn_topic_0079614912_p46946462"></a><a name="zh-cn_topic_0079614912_p46946462"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p44567074"><a name="zh-cn_topic_0079614912_p44567074"></a><a name="zh-cn_topic_0079614912_p44567074"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row65559353"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p8707397"><a name="zh-cn_topic_0079614912_p8707397"></a><a name="zh-cn_topic_0079614912_p8707397"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p34210590"><a name="zh-cn_topic_0079614912_p34210590"></a><a name="zh-cn_topic_0079614912_p34210590"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p19594411"><a name="zh-cn_topic_0079614912_p19594411"></a><a name="zh-cn_topic_0079614912_p19594411"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row42131977"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p57246976"><a name="zh-cn_topic_0079614912_p57246976"></a><a name="zh-cn_topic_0079614912_p57246976"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p6493471"><a name="zh-cn_topic_0079614912_p6493471"></a><a name="zh-cn_topic_0079614912_p6493471"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p56209167"><a name="zh-cn_topic_0079614912_p56209167"></a><a name="zh-cn_topic_0079614912_p56209167"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row36120461"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p40076217"><a name="zh-cn_topic_0079614912_p40076217"></a><a name="zh-cn_topic_0079614912_p40076217"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p24948105"><a name="zh-cn_topic_0079614912_p24948105"></a><a name="zh-cn_topic_0079614912_p24948105"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p7530597"><a name="zh-cn_topic_0079614912_p7530597"></a><a name="zh-cn_topic_0079614912_p7530597"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row666516"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p53987822"><a name="zh-cn_topic_0079614912_p53987822"></a><a name="zh-cn_topic_0079614912_p53987822"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p10937481"><a name="zh-cn_topic_0079614912_p10937481"></a><a name="zh-cn_topic_0079614912_p10937481"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p13520781"><a name="zh-cn_topic_0079614912_p13520781"></a><a name="zh-cn_topic_0079614912_p13520781"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="r8a408c32e95a4e11a0f37c7e8c496ae9"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p62023147538"><a name="zh-cn_topic_0079614912_p62023147538"></a><a name="zh-cn_topic_0079614912_p62023147538"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.4.1.2 "><p id="afed04ce8ed5b4563a1682d61a3792448"><a name="afed04ce8ed5b4563a1682d61a3792448"></a><a name="afed04ce8ed5b4563a1682d61a3792448"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p120261435313"><a name="zh-cn_topic_0079614912_p120261435313"></a><a name="zh-cn_topic_0079614912_p120261435313"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sfa72efcb12544146a6d0110ec99bdde9"></a>

N/A

## 响应消息<a name="sadda659ddfa046368c5c736891a5c24d"></a>

**响应参数：**

响应参数如[表2](#zh-cn_topic_0079614912_ref458774242)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079614912_ref458774242"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614912_row38450714"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614912_p27500114"><a name="zh-cn_topic_0079614912_p27500114"></a><a name="zh-cn_topic_0079614912_p27500114"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p27065320195410"><a name="p27065320195410"></a><a name="p27065320195410"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p44807289195410"><a name="p44807289195410"></a><a name="p44807289195410"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614912_row55335660"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p53003510"><a name="zh-cn_topic_0079614912_p53003510"></a><a name="zh-cn_topic_0079614912_p53003510"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p65425945"><a name="zh-cn_topic_0079614912_p65425945"></a><a name="zh-cn_topic_0079614912_p65425945"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p65010172"><a name="zh-cn_topic_0079614912_p65010172"></a><a name="zh-cn_topic_0079614912_p65010172"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row48220637"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p13557507"><a name="zh-cn_topic_0079614912_p13557507"></a><a name="zh-cn_topic_0079614912_p13557507"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p24416319"><a name="zh-cn_topic_0079614912_p24416319"></a><a name="zh-cn_topic_0079614912_p24416319"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p31564790"><a name="zh-cn_topic_0079614912_p31564790"></a><a name="zh-cn_topic_0079614912_p31564790"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row15647660"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p59500970"><a name="zh-cn_topic_0079614912_p59500970"></a><a name="zh-cn_topic_0079614912_p59500970"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p54849240"><a name="zh-cn_topic_0079614912_p54849240"></a><a name="zh-cn_topic_0079614912_p54849240"></a><a href="#zh-cn_topic_0079614912_table3125665">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p55321938"><a name="zh-cn_topic_0079614912_p55321938"></a><a name="zh-cn_topic_0079614912_p55321938"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row28135397"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p64374676"><a name="zh-cn_topic_0079614912_p64374676"></a><a name="zh-cn_topic_0079614912_p64374676"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p46966292"><a name="zh-cn_topic_0079614912_p46966292"></a><a name="zh-cn_topic_0079614912_p46966292"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p12906742"><a name="zh-cn_topic_0079614912_p12906742"></a><a name="zh-cn_topic_0079614912_p12906742"></a>List of services，具体请参见<a href="获取指定的Service.md#zh-cn_topic_0079614941_ref458765062">表2</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="zh-cn_topic_0079614912_table3125665"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614912_row13211630"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614912_p63509122"><a name="zh-cn_topic_0079614912_p63509122"></a><a name="zh-cn_topic_0079614912_p63509122"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p58481405195410"><a name="p58481405195410"></a><a name="p58481405195410"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p39373359195410"><a name="p39373359195410"></a><a name="p39373359195410"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614912_row21923775"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p30995332"><a name="zh-cn_topic_0079614912_p30995332"></a><a name="zh-cn_topic_0079614912_p30995332"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p27593978"><a name="zh-cn_topic_0079614912_p27593978"></a><a name="zh-cn_topic_0079614912_p27593978"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p20519752"><a name="zh-cn_topic_0079614912_p20519752"></a><a name="zh-cn_topic_0079614912_p20519752"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614912_row50460048"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614912_p60732119"><a name="zh-cn_topic_0079614912_p60732119"></a><a name="zh-cn_topic_0079614912_p60732119"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614912_p20354569"><a name="zh-cn_topic_0079614912_p20354569"></a><a name="zh-cn_topic_0079614912_p20354569"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614912_p38107408"><a name="zh-cn_topic_0079614912_p38107408"></a><a name="zh-cn_topic_0079614912_p38107408"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{ 
   "kind": "ServiceList", 
   "apiVersion": "v1", 
   "metadata": { 
     "selfLink": "/api/v1/namespaces/default/services", 
     "resourceVersion": "1230" 
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

## 状态码<a name="sb209ebbf78944af4b92248c35b3aecfc"></a>

[表4](#zh-cn_topic_0079614912_table28130990)描述API的状态码。

**表 4**  状态码

<a name="zh-cn_topic_0079614912_table28130990"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614912_row58140769"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p51917783195410"><a name="p51917783195410"></a><a name="p51917783195410"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p44590880195410"><a name="p44590880195410"></a><a name="p44590880195410"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614912_row58604130"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614912_p49314056"><a name="zh-cn_topic_0079614912_p49314056"></a><a name="zh-cn_topic_0079614912_p49314056"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614912_p35015599"><a name="zh-cn_topic_0079614912_p35015599"></a><a name="zh-cn_topic_0079614912_p35015599"></a>This operation succeeds, and a group of Service resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

