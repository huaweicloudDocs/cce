# 替换指定的Service<a name="cce_02_0028"></a>

## 功能介绍<a name="s7f16b6de4e854b61a40ec42af83c7a24"></a>

该API用于替换指定的Service对象。

其中以下字段支持更新：

-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.generation
-   metadata.creationTimestamp
-   metadata.deletionTimestamp
-   metadata.labels
-   metadata.clusterName
-   metadata.generateName
-   metadata.annotations
-   spec.externalTrafficPolicy
-   spec.sessionAffinity
-   spec.type

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >spec.type的值，可更新的优先级为LoadBalancer\>NodePort\>ClusterIP，即当spec.type的值为ClusterIP时，可更新为LoadBalancer或NodePort；当spec.type的值为NodePort时，只能更新为LoadBalancer；当spec.type的值为LoadBalancer时，spec.type不可更新。  

-   spec.port
-   spec.selector
-   spec.externalIPs
-   spec.loadBalancerIP
-   spec.loadBalancerSourceRanges

## URI<a name="sd473d9d2d140486eb450698f18eb16e1"></a>

PUT /api/v1/namespaces/\{namespace\}/services/\{name\}

[表1](#zh-cn_topic_0079615066_table59996030)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615066_table59996030"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615066_row4196075"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615066_p4337788"><a name="zh-cn_topic_0079615066_p4337788"></a><a name="zh-cn_topic_0079615066_p4337788"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p45173014195352"><a name="p45173014195352"></a><a name="p45173014195352"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0079615066_p6069154"><a name="zh-cn_topic_0079615066_p6069154"></a><a name="zh-cn_topic_0079615066_p6069154"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615066_row21839497"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615066_p24168795"><a name="zh-cn_topic_0079615066_p24168795"></a><a name="zh-cn_topic_0079615066_p24168795"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615066_p11515394"><a name="zh-cn_topic_0079615066_p11515394"></a><a name="zh-cn_topic_0079615066_p11515394"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615066_p60331750"><a name="zh-cn_topic_0079615066_p60331750"></a><a name="zh-cn_topic_0079615066_p60331750"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615066_row52637298"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615066_p35762716"><a name="zh-cn_topic_0079615066_p35762716"></a><a name="zh-cn_topic_0079615066_p35762716"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615066_p11098866"><a name="zh-cn_topic_0079615066_p11098866"></a><a name="zh-cn_topic_0079615066_p11098866"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615066_p26592990"><a name="zh-cn_topic_0079615066_p26592990"></a><a name="zh-cn_topic_0079615066_p26592990"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615066_row38010318"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615066_p58936947"><a name="zh-cn_topic_0079615066_p58936947"></a><a name="zh-cn_topic_0079615066_p58936947"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615066_p9163425"><a name="zh-cn_topic_0079615066_p9163425"></a><a name="zh-cn_topic_0079615066_p9163425"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615066_p4039935"><a name="zh-cn_topic_0079615066_p4039935"></a><a name="zh-cn_topic_0079615066_p4039935"></a>Name of the Service.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079615066_ref458765758"></a>

**响应参数：**

请求参数的详细描述请参见[表2](创建Service.md#zh-cn_topic_0079615000_ref458759328)。

**请求示例：**

```
{ 
   "kind": "Service", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "myapp", 
     "resourceVersion": "683" 
   }, 
   "spec": { 
     "ports": [{ 
       "port": 80, 
       "targetPort": 80 
     }], 
     "selector": { 
       "app": "example" 
     }, 
     "clusterIP": "10.0.0.139" 
   } 
 }
```

## 响应消息<a name="s45b51f911829442cae934355300a440d"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079615066_ref458765758)。

**响应示例：**

```
{ 
   "kind": "Service", 
   "apiVersion": "v1", 
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
```

## 状态码<a name="s5ba1a0225c3c4dd8948fdd7a6c393876"></a>

[表2](#zh-cn_topic_0079615066_table3093358)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615066_table3093358"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615066_row66569734"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p53137435195352"><a name="p53137435195352"></a><a name="p53137435195352"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0079615066_p19540130"><a name="zh-cn_topic_0079615066_p19540130"></a><a name="zh-cn_topic_0079615066_p19540130"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615066_row39246670"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615066_p24863727"><a name="zh-cn_topic_0079615066_p24863727"></a><a name="zh-cn_topic_0079615066_p24863727"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615066_p696045"><a name="zh-cn_topic_0079615066_p696045"></a><a name="zh-cn_topic_0079615066_p696045"></a>This operation succeeds, and a Service resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

