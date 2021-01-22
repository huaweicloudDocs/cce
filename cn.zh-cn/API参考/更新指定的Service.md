# 更新指定的Service<a name="cce_02_0031"></a>

## 功能介绍<a name="s79a46a3bbf834e65a768cf502c42239e"></a>

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

## URI<a name="s2bcf1feaf0bc43ee938e4fcc63b3849c"></a>

PATCH /api/v1/namespaces/\{namespace\}/services/\{name\}

[表1](#zh-cn_topic_0079614894_table66627661)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614894_table66627661"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614894_row3622792"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614894_p25010772"><a name="zh-cn_topic_0079614894_p25010772"></a><a name="zh-cn_topic_0079614894_p25010772"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p38778720203035"><a name="p38778720203035"></a><a name="p38778720203035"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0079614894_p14503239"><a name="zh-cn_topic_0079614894_p14503239"></a><a name="zh-cn_topic_0079614894_p14503239"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614894_row33911744"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614894_p62496749"><a name="zh-cn_topic_0079614894_p62496749"></a><a name="zh-cn_topic_0079614894_p62496749"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614894_p29071927"><a name="zh-cn_topic_0079614894_p29071927"></a><a name="zh-cn_topic_0079614894_p29071927"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614894_p6015877"><a name="zh-cn_topic_0079614894_p6015877"></a><a name="zh-cn_topic_0079614894_p6015877"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614894_row23698059"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614894_p40494599"><a name="zh-cn_topic_0079614894_p40494599"></a><a name="zh-cn_topic_0079614894_p40494599"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614894_p58837112"><a name="zh-cn_topic_0079614894_p58837112"></a><a name="zh-cn_topic_0079614894_p58837112"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614894_p1076806"><a name="zh-cn_topic_0079614894_p1076806"></a><a name="zh-cn_topic_0079614894_p1076806"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614894_row9691259"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614894_p46794527"><a name="zh-cn_topic_0079614894_p46794527"></a><a name="zh-cn_topic_0079614894_p46794527"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614894_p32260306"><a name="zh-cn_topic_0079614894_p32260306"></a><a name="zh-cn_topic_0079614894_p32260306"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614894_p62948031"><a name="zh-cn_topic_0079614894_p62948031"></a><a name="zh-cn_topic_0079614894_p62948031"></a>Name of the Service.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s6972b4d28cf840328e55c95e180ccd87"></a>

**响应参数：**

“Content-Type“的详细描述请参见 [PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

请求参数的详细描述请参见[表2](创建Service.md#zh-cn_topic_0079615000_ref458759328)。

**请求示例：**

```
Content-Type: application/strategic-merge-patch+json
```

```
 { 
     "spec": { 
         "ports": [ 
             { 
                 "name": "ttt1", 
                 "protocol": "TCP", 
                 "port": 8765, 
                 "targetPort": 9376 
             }, 
             { 
                 "name": "ttt2", 
                 "protocol": "TCP", 
                 "port": 8765, 
                 "targetPort": 9076 
             } 
         ], 
         "selector": { 
             "app": "example" 
         } 
     } 
 }
```

## 响应消息<a name="sab68cc958da442f79a8bdd2c90aae544"></a>

**响应参数：**

响应参数的详细描述请参见[表2](获取指定的Service.md#zh-cn_topic_0079614941_ref458765062)。

**响应示例：**

```
{ 
   "kind": "Service", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "raoy", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/services/raoy", 
     "uid": "e0d681b7-5d17-11e6-aeb9-286ed488fafe", 
     "resourceVersion": "1602", 
     "creationTimestamp": "2016-08-08T03:26:21Z" 
   }, 
   "spec": { 
     "ports": [ 
       { 
         "name": "ttt1", 
         "protocol": "TCP", 
         "port": 8765, 
         "targetPort": 9376 
       }, 
       { 
         "name": "ttt2", 
         "protocol": "TCP", 
         "port": 8765, 
         "targetPort": 9076 
       } 
     ], 
     "selector": { 
       "app": "example" 
     }, 
     "clusterIP": "10.0.0.193", 
     "type": "ClusterIP", 
     "sessionAffinity": "None" 
   }, 
   "status": { 
     "loadBalancer": {} 
   } 
 }
```

## 状态码<a name="s3f10ef39263445cabc5b032a11c66233"></a>

[表2](#zh-cn_topic_0079614894_table62778039)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614894_table62778039"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614894_row29754946"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p50518267203035"><a name="p50518267203035"></a><a name="p50518267203035"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0079614894_p2516162"><a name="zh-cn_topic_0079614894_p2516162"></a><a name="zh-cn_topic_0079614894_p2516162"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614894_row2482606"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614894_p66873365"><a name="zh-cn_topic_0079614894_p66873365"></a><a name="zh-cn_topic_0079614894_p66873365"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614894_p48033505"><a name="zh-cn_topic_0079614894_p48033505"></a><a name="zh-cn_topic_0079614894_p48033505"></a>This operation succeeds, and a Service resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

