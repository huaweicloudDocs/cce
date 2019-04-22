# 更新指定的ReplicationController<a name="cce_02_0023"></a>

## 功能介绍<a name="s615bc0b56fbf44b6a8f921b400a80a30"></a>

该API用于更新指定Namespace下的ReplicationController对象。

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
-   spec.replicas
-   template.contaions
-   spec.restartPolicy
-   spec.activeDeadlineSeconds

## URI<a name="s1fa3f000cd23422083df6d59217fcd93"></a>

PATCH /api/v1/namespaces/\{namespace\}/replicationcontrollers/\{name\}

[表1](#zh-cn_topic_0079615044_table33153663)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615044_table33153663"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615044_row53250102"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615044_p18291030"><a name="zh-cn_topic_0079615044_p18291030"></a><a name="zh-cn_topic_0079615044_p18291030"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p65451938195026"><a name="p65451938195026"></a><a name="p65451938195026"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p6801195026"><a name="p6801195026"></a><a name="p6801195026"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615044_row18916265"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615044_p55822491"><a name="zh-cn_topic_0079615044_p55822491"></a><a name="zh-cn_topic_0079615044_p55822491"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615044_p25327909"><a name="zh-cn_topic_0079615044_p25327909"></a><a name="zh-cn_topic_0079615044_p25327909"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615044_p38294768"><a name="zh-cn_topic_0079615044_p38294768"></a><a name="zh-cn_topic_0079615044_p38294768"></a>设置为true后，会打印漂亮的输出结果。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615044_row9108597"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615044_p66707780"><a name="zh-cn_topic_0079615044_p66707780"></a><a name="zh-cn_topic_0079615044_p66707780"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615044_p34621095"><a name="zh-cn_topic_0079615044_p34621095"></a><a name="zh-cn_topic_0079615044_p34621095"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615044_p52845319"><a name="zh-cn_topic_0079615044_p52845319"></a><a name="zh-cn_topic_0079615044_p52845319"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615044_row5845825"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615044_p3749798"><a name="zh-cn_topic_0079615044_p3749798"></a><a name="zh-cn_topic_0079615044_p3749798"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615044_p35298236"><a name="zh-cn_topic_0079615044_p35298236"></a><a name="zh-cn_topic_0079615044_p35298236"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615044_p40584874"><a name="zh-cn_topic_0079615044_p40584874"></a><a name="zh-cn_topic_0079615044_p40584874"></a>ReplicationController的名称</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="scb1fe2c0ceef4190939652221c118528"></a>

**响应参数：**

“Content-Type“的详细描述请参见 [PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

请求参数的详细描述请参见[表1](公共请求参数.md#zh-cn_topic_0079614925_table51284307)。

**请求示例：**

```
Content-Type: application/strategic-merge-patch+json
```

```
 { 
   "spec": { 
         "template": { 
             "spec": { 
                 "containers": [ 
                     { 
                         "name": "hello-world", 
                         "image": "busybox:latest" 
                     }, 
                     { 
                         "name": "hello", 
                         "image": "busybox:latest" 
                     } 
                 ] 
             } 
         } 
     } 
 }
```

## 响应消息<a name="zh-cn_topic_0079615044_section988213"></a>

**响应参数：**

响应参数的详细描述请参见[表1](公共响应参数.md#zh-cn_topic_0079614930_table30479638)。

**响应示例：**

```
{ 
   "kind": "ReplicationController", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "frontend-controller", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/replicationcontrollers/frontend-controller", 
     "uid": "cd4594b6-5d0b-11e6-aeb9-286ed488fafe", 
     "resourceVersion": "1658", 
     "generation": 2, 
     "creationTimestamp": "2016-08-08T01:59:55Z", 
     "labels": { 
       "app": "nginx" 
     } 
   }, 
   "spec": { 
     "replicas": 2, 
     "selector": { 
       "app": "nginx" 
     }, 
     "template": { 
       "metadata": { 
         "creationTimestamp": null, 
         "labels": { 
           "app": "nginx" 
         } 
       }, 
       "spec": { 
         "containers": [ 
         { 
             "name": "hello-world", 
             "image": "busybox:latest", 
             "resources": {}, 
             "terminationMessagePath": "/dev/termination-log", 
             "imagePullPolicy": "Always" 
           }, 
           { 
             "name": "hello", 
             "image": "busybox:latest", 
             "resources": {}, 
             "terminationMessagePath": "/dev/termination-log", 
             "imagePullPolicy": "Always" 
           } 
         ], 
         "restartPolicy": "Always", 
         "terminationGracePeriodSeconds": 30, 
         "dnsPolicy": "ClusterFirst", 
         "securityContext": {} 
       } 
     } 
   }, 
   "status": { 
     "replicas": 2, 
     "fullyLabeledReplicas": 2, 
     "observedGeneration": 1 
   } 
 }
```

## 状态码<a name="s6211e732eeb946dcb43c007e90829a94"></a>

[表2](#zh-cn_topic_0079615044_table29947515)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615044_table29947515"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615044_row41083762"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p64069331195026"><a name="p64069331195026"></a><a name="p64069331195026"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p22233337195026"><a name="p22233337195026"></a><a name="p22233337195026"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615044_row62212303"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615044_p6031802"><a name="zh-cn_topic_0079615044_p6031802"></a><a name="zh-cn_topic_0079615044_p6031802"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615044_p18813966"><a name="zh-cn_topic_0079615044_p18813966"></a><a name="zh-cn_topic_0079615044_p18813966"></a>操作成功，返回ReplicationController资源对象。</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

