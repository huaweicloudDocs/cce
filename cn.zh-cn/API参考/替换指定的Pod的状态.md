# 替换指定的Pod的状态<a name="cce_02_0038"></a>

## 功能介绍<a name="s14b3085e84f44f248c15900b7a9ae75e"></a>

该API用于替换指定Namespace下的一个Pod对象的status，即修改Pod对象status各字段的值。

## URI<a name="s2146020c33a84ca5aa9bc6e54586edc9"></a>

PUT /api/v1/namespaces/\{namespace\}/pods/\{name\}/status

[表1](#zh-cn_topic_0079614908_table13708463)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614908_table13708463"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614908_row53056665"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614908_p2622637"><a name="zh-cn_topic_0079614908_p2622637"></a><a name="zh-cn_topic_0079614908_p2622637"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p25672384203057"><a name="p25672384203057"></a><a name="p25672384203057"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p66197242203057"><a name="p66197242203057"></a><a name="p66197242203057"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614908_row60209123"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614908_p45100793"><a name="zh-cn_topic_0079614908_p45100793"></a><a name="zh-cn_topic_0079614908_p45100793"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614908_p29285587"><a name="zh-cn_topic_0079614908_p29285587"></a><a name="zh-cn_topic_0079614908_p29285587"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614908_p23322329"><a name="zh-cn_topic_0079614908_p23322329"></a><a name="zh-cn_topic_0079614908_p23322329"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614908_row16574033"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614908_p319438"><a name="zh-cn_topic_0079614908_p319438"></a><a name="zh-cn_topic_0079614908_p319438"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614908_p25874536"><a name="zh-cn_topic_0079614908_p25874536"></a><a name="zh-cn_topic_0079614908_p25874536"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614908_p15462662"><a name="zh-cn_topic_0079614908_p15462662"></a><a name="zh-cn_topic_0079614908_p15462662"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614908_row4946234"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614908_p65100698"><a name="zh-cn_topic_0079614908_p65100698"></a><a name="zh-cn_topic_0079614908_p65100698"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614908_p38665203"><a name="zh-cn_topic_0079614908_p38665203"></a><a name="zh-cn_topic_0079614908_p38665203"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614908_p44873708"><a name="zh-cn_topic_0079614908_p44873708"></a><a name="zh-cn_topic_0079614908_p44873708"></a>Name of the Pod.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079614908_ref458608140"></a>

**请求参数：**

请求参数的详细描述请参见[表3](响应数据结构.md#zh-cn_topic_0079614930_table52931650)。

**请求示例：**

```
{ 
     "kind": "Pod", 
     "apiVersion": "v1", 
     "metadata": { 
         "name": "hello-world", 
         "namespace": "default", 
         "selfLink": "/api/v1/namespaces/default/pods/hello-world", 
         "uid": "84973056-5d3b-11e6-aeb9-286ed488fafe", 
         "resourceVersion": "3636", 
         "creationTimestamp": "2016-08-08T07:41:29Z", 
         "labels": { 
             "name": "brace" 
         } 
     }, 
     "status": { 
         "phase": "Running", 
         "conditions": [ 
             { 
                 "type": "Ready", 
                 "status": "True", 
                 "lastProbeTime": null, 
                 "lastTransitionTime": "2016-08-08T07:41:29Z" 
             } 
         ], 
         "hostIP": "127.0.0.1", 
         "podIP": "172.16.0.4", 
         "startTime": "2016-08-08T07:41:29Z" 
   } 
 }
```

## 响应消息<a name="s279a234cda4443f0afa7d8de9b799a5a"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079614908_ref458608140)。

**响应示例：**

```
{ 
   "kind": "Pod", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "hello-world", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/pods/hello-world/status", 
     "uid": "84973056-5d3b-11e6-aeb9-286ed488fafe", 
     "resourceVersion": "3641", 
     "creationTimestamp": "2016-08-08T07:41:29Z", 
   "labels": { 
       "name": "brace" 
     } 
   }, 
   "spec": { 
     "volumes": [ 
       { 
         "name": "test", 
         "emptyDir": {} 
       }, 
       { 
         "name": "default-token-test2", 
         "secret": { 
           "secretName": "default-token-test2" 
         } 
       } 
     ], 
     "containers": [ 
       { 
         "name": "hello-world", 
         "image": "beego:v1", 
         "env": [ 
           { 
             "name": "cy", 
             "value": "cy" 
           } 
         ], 
         "resources": {}, 
         "volumeMounts": [ 
           { 
             "name": "test", 
             "mountPath": "/tmp/foo" 
           }, 
           { 
             "name": "default-token-test2", 
             "readOnly": true, 
             "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount" 
           } 
         ], 
         "terminationMessagePath": "/dev/termination-log", 
         "imagePullPolicy": "IfNotPresent" 
       } 
     ], 
     "restartPolicy": "Always", 
     "terminationGracePeriodSeconds": 30, 
     "dnsPolicy": "ClusterFirst", 
     "serviceAccountName": "default", 
     "serviceAccount": "default", 
     "nodeName": "127.0.0.1", 
     "securityContext": {} 
   }, 
   "status": { 
     "phase": "Running", 
     "conditions": [ 
       { 
         "type": "Ready", 
         "status": "True", 
         "lastProbeTime": null, 
         "lastTransitionTime": "2016-08-08T07:41:29Z" 
       } 
     ], 
     "hostIP": "127.0.0.1", 
     "podIP": "172.16.0.4", 
     "startTime": "2016-08-08T07:41:29Z" 
   } 
 }
```

## 状态码<a name="s8a2da3e1bb8a49d2af7cf2027ab3fea0"></a>

[表2](#zh-cn_topic_0079614908_table56267310)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614908_table56267310"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614908_row31065142"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p26385296203057"><a name="p26385296203057"></a><a name="p26385296203057"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p56834228203057"><a name="p56834228203057"></a><a name="p56834228203057"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614908_row39832915"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614908_p5240702"><a name="zh-cn_topic_0079614908_p5240702"></a><a name="zh-cn_topic_0079614908_p5240702"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614908_p21843730"><a name="zh-cn_topic_0079614908_p21843730"></a><a name="zh-cn_topic_0079614908_p21843730"></a>This operation succeeds, and the JSON of a Pod object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

