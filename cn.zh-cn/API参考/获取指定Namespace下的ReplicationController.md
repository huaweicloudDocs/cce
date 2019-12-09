# 获取指定Namespace下的ReplicationController<a name="cce_02_0018"></a>

## 功能介绍<a name="s72d8bf6c161c43558495cd00be7c558b"></a>

该API用于获取指定Namespace下的ReplicationController对象。

## URI<a name="s40af06b4227445939b4721cf5c975a5a"></a>

GET /api/v1/namespaces/\{namespace\}/replicationcontrollers/\{name\}

[表1](#zh-cn_topic_0079614960_table6029955)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614960_table6029955"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614960_row31601207"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614960_p9561011"><a name="zh-cn_topic_0079614960_p9561011"></a><a name="zh-cn_topic_0079614960_p9561011"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.19191919191919%" id="mcps1.2.4.1.2"><p id="p27767863194447"><a name="p27767863194447"></a><a name="p27767863194447"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="47.474747474747474%" id="mcps1.2.4.1.3"><p id="p34604445194447"><a name="p34604445194447"></a><a name="p34604445194447"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614960_row32768815"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614960_p37028364"><a name="zh-cn_topic_0079614960_p37028364"></a><a name="zh-cn_topic_0079614960_p37028364"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614960_p46507526"><a name="zh-cn_topic_0079614960_p46507526"></a><a name="zh-cn_topic_0079614960_p46507526"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="47.474747474747474%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614960_p9013252"><a name="zh-cn_topic_0079614960_p9013252"></a><a name="zh-cn_topic_0079614960_p9013252"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614960_row14010408"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614960_p61101288"><a name="zh-cn_topic_0079614960_p61101288"></a><a name="zh-cn_topic_0079614960_p61101288"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614960_p50257313"><a name="zh-cn_topic_0079614960_p50257313"></a><a name="zh-cn_topic_0079614960_p50257313"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="47.474747474747474%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614960_p44310522"><a name="zh-cn_topic_0079614960_p44310522"></a><a name="zh-cn_topic_0079614960_p44310522"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614960_row63250378"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614960_p23006966"><a name="zh-cn_topic_0079614960_p23006966"></a><a name="zh-cn_topic_0079614960_p23006966"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614960_p51624983"><a name="zh-cn_topic_0079614960_p51624983"></a><a name="zh-cn_topic_0079614960_p51624983"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="47.474747474747474%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614960_p20874133"><a name="zh-cn_topic_0079614960_p20874133"></a><a name="zh-cn_topic_0079614960_p20874133"></a>Name of the ReplicationController.</p>
</td>
</tr>
<tr id="reff3cd4d8cfc450b9b40f31a9d5e8279"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="a717ab34c546d40cba900500dba3da03d"><a name="a717ab34c546d40cba900500dba3da03d"></a><a name="a717ab34c546d40cba900500dba3da03d"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.4.1.2 "><p id="a7399050b61bd4fabb94f629ebe049116"><a name="a7399050b61bd4fabb94f629ebe049116"></a><a name="a7399050b61bd4fabb94f629ebe049116"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="47.474747474747474%" headers="mcps1.2.4.1.3 "><p id="abaed45ac101d46868ceb3c170f13db54"><a name="abaed45ac101d46868ceb3c170f13db54"></a><a name="abaed45ac101d46868ceb3c170f13db54"></a>Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="raf14328054a8479587cc4955cd45b779"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="a0bc9037187c143fd8e626cd378a3737d"><a name="a0bc9037187c143fd8e626cd378a3737d"></a><a name="a0bc9037187c143fd8e626cd378a3737d"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="19.19191919191919%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614960_p838454518297"><a name="zh-cn_topic_0079614960_p838454518297"></a><a name="zh-cn_topic_0079614960_p838454518297"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="47.474747474747474%" headers="mcps1.2.4.1.3 "><p id="a3ec493718af24276b938983c86dfea10"><a name="a3ec493718af24276b938983c86dfea10"></a><a name="a3ec493718af24276b938983c86dfea10"></a>Should this value be exported. Export strips fields that a user can not specify.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sd137b1137fd94187ac772ec406c9e60f"></a>

N/A

## 响应消息<a name="s45c8b8730a374c4eb96a9b714d3685de"></a>

**响应参数：**

响应参数的详细描述请参见[表1](响应数据结构.md#zh-cn_topic_0079614930_table30479638)。

**响应示例：**

```
{ 
   "kind": "ReplicationController", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "frontend-controller", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/replicationcontrollers/frontend-controller", 
     "uid": "9c664f9f-5954-11e6-b444-286ed488fafe", 
     "resourceVersion": "13050", 
     "generation": 1, 
     "creationTimestamp": "2016-08-03T08:31:01Z", 
     "labels": { 
       "state": "serving" 
     } 
   }, 
   "spec": { 
     "replicas": 2, 
     "selector": { 
       "app": "frontend" 
     }, 
     "template": { 
       "metadata": { 
         "creationTimestamp": null, 
         "labels": { 
         "app": "frontend" 
         } 
       }, 
       "spec": { 
         "containers": [ 
           { 
             "name": "php-redis", 
             "image": "redis", 
             "ports": [ 
               { 
                 "containerPort": 80, 
                 "protocol": "TCP" 
               } 
             ], 
             "resources": {}, 
             "terminationMessagePath": "/dev/termination-log", 
             "imagePullPolicy": "IfNotPresent" 
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

## 状态码<a name="s67dd8c74c77143d491256fc58596baba"></a>

[表2](#zh-cn_topic_0079614960_table54269597)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614960_table54269597"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614960_row55372696"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p48784481194447"><a name="p48784481194447"></a><a name="p48784481194447"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p59228882194447"><a name="p59228882194447"></a><a name="p59228882194447"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614960_row17120881"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614960_p44614122"><a name="zh-cn_topic_0079614960_p44614122"></a><a name="zh-cn_topic_0079614960_p44614122"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p3403433640"><a name="p3403433640"></a><a name="p3403433640"></a>This operation succeeds, and a ReplicationController resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

