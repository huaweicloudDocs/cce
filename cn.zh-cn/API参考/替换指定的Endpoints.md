# 替换指定的Endpoints<a name="cce_02_0062"></a>

## 功能介绍<a name="sc37501af9b7044f4ae092cb00715a785"></a>

该API用于替换指定Namespace下指定的Endpoints资源对象。

其中以下字段支持更新：

-   metadata.name
-   metadata.namespace
-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.uid
-   metadata.labels
-   metadata.clusterName
-   metadata.generateName
-   metadata.annotations
-   subnet.\*
-   metadata.deletionGracePeriodSeconds

## URI<a name="s86f7cb5e4d6541d0914295e89856a8f2"></a>

PUT /api/v1/namespaces/\{namespace\}/endpoints/\{name\}

[表1](#zh-cn_topic_0079614957_table31235479)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614957_table31235479"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614957_row3156250"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614957_p54329699"><a name="zh-cn_topic_0079614957_p54329699"></a><a name="zh-cn_topic_0079614957_p54329699"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p811366201648"><a name="p811366201648"></a><a name="p811366201648"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p65720655201648"><a name="p65720655201648"></a><a name="p65720655201648"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614957_row45300995"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614957_p45501950"><a name="zh-cn_topic_0079614957_p45501950"></a><a name="zh-cn_topic_0079614957_p45501950"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614957_p61779338"><a name="zh-cn_topic_0079614957_p61779338"></a><a name="zh-cn_topic_0079614957_p61779338"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614957_p38070478"><a name="zh-cn_topic_0079614957_p38070478"></a><a name="zh-cn_topic_0079614957_p38070478"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614957_row18472885"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614957_p19908716"><a name="zh-cn_topic_0079614957_p19908716"></a><a name="zh-cn_topic_0079614957_p19908716"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614957_p1993291"><a name="zh-cn_topic_0079614957_p1993291"></a><a name="zh-cn_topic_0079614957_p1993291"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614957_p27238907"><a name="zh-cn_topic_0079614957_p27238907"></a><a name="zh-cn_topic_0079614957_p27238907"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614957_row43823577"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614957_p60048837"><a name="zh-cn_topic_0079614957_p60048837"></a><a name="zh-cn_topic_0079614957_p60048837"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614957_p32117589"><a name="zh-cn_topic_0079614957_p32117589"></a><a name="zh-cn_topic_0079614957_p32117589"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614957_p51387889"><a name="zh-cn_topic_0079614957_p51387889"></a><a name="zh-cn_topic_0079614957_p51387889"></a>Name of the Endpoints.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079614957_ref458707209"></a>

**请求参数：**

请求参数的详细描述请参见[表2](创建Endpoints.md#zh-cn_topic_0079614955_ref458759912)。

**请求示例：**

```
{ 
   "kind": "Endpoints", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "cluster-test" 
   }, 
   "subsets": [ 
     { 
       "addresses": [ 
         { 
           "ip": "172.16.106.150" 
         } 
       ], 
       "ports": [ 
         { 
           "port": 1 
         } 
       ] 
     }, 
     { 
       "addresses": [ 
         { 
           "ip": "172.16.79.223" 
         } 
       ], 
       "ports": [ 
         { 
           "port": 1 
         } 
       ] 
     },{ 
       "addresses": [ 
         { 
           "ip": "172.16.106.154" 
         } 
       ], 
       "ports": [ 
         { 
           "port": 1 
         } 
       ] 
     } 
   ] 
 }
```

## 响应消息<a name="s53cdaea7a7a849248695c65ad5d83aa2"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079614957_ref458707209)。

**响应示例：**

```
{ 
   "kind": "Endpoints", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "cluster-test", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/endpoints/cluster-test", 
     "uid": "88a7230f-5d36-11e6-aeb9-286ed488fafe", 
     "resourceVersion": "3203", 
     "creationTimestamp": "2016-08-08T07:05:48Z" 
   }, 
   "subsets": [ 
     { 
       "addresses": [ 
         { 
           "ip": "172.16.106.150" 
         }, 
         { 
           "ip": "172.16.106.154" 
         }, 
         { 
           "ip": "172.16.79.223" 
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

## 状态码<a name="s3fa127a04c544cefb712cbbcb09fc524"></a>

[表2](#zh-cn_topic_0079614957_table12683857)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614957_table12683857"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614957_row49320909"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p12685718201648"><a name="p12685718201648"></a><a name="p12685718201648"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p20910256201648"><a name="p20910256201648"></a><a name="p20910256201648"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614957_row41609976"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614957_p14964925"><a name="zh-cn_topic_0079614957_p14964925"></a><a name="zh-cn_topic_0079614957_p14964925"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614957_p4199435"><a name="zh-cn_topic_0079614957_p4199435"></a><a name="zh-cn_topic_0079614957_p4199435"></a>This operation succeeds, and a group of Endpoint resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

