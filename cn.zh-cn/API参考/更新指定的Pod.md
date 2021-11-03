# 更新指定的Pod<a name="cce_02_0041"></a>

## 功能介绍<a name="sa4fea4daced64d1888668eec5dfdf81e"></a>

该API用于更新指定Namespace下一个Pod对象。

## URI<a name="s325d88a5c7a84313849b743675883694"></a>

PATCH /api/v1/namespaces/\{namespace\}/pods/\{name\}

[表1](#zh-cn_topic_0079614948_table57906594)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614948_table57906594"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614948_row34327759"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614948_p29085133"><a name="zh-cn_topic_0079614948_p29085133"></a><a name="zh-cn_topic_0079614948_p29085133"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p21409415201616"><a name="p21409415201616"></a><a name="p21409415201616"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p56441034201616"><a name="p56441034201616"></a><a name="p56441034201616"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614948_row49181313"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614948_p24263425"><a name="zh-cn_topic_0079614948_p24263425"></a><a name="zh-cn_topic_0079614948_p24263425"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614948_p19180389"><a name="zh-cn_topic_0079614948_p19180389"></a><a name="zh-cn_topic_0079614948_p19180389"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614948_p10107670"><a name="zh-cn_topic_0079614948_p10107670"></a><a name="zh-cn_topic_0079614948_p10107670"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614948_row55758965"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614948_p20182332"><a name="zh-cn_topic_0079614948_p20182332"></a><a name="zh-cn_topic_0079614948_p20182332"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614948_p24156224"><a name="zh-cn_topic_0079614948_p24156224"></a><a name="zh-cn_topic_0079614948_p24156224"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614948_p10497128"><a name="zh-cn_topic_0079614948_p10497128"></a><a name="zh-cn_topic_0079614948_p10497128"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614948_row27365293"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614948_p1996295"><a name="zh-cn_topic_0079614948_p1996295"></a><a name="zh-cn_topic_0079614948_p1996295"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614948_p27482234"><a name="zh-cn_topic_0079614948_p27482234"></a><a name="zh-cn_topic_0079614948_p27482234"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614948_p11468461"><a name="zh-cn_topic_0079614948_p11468461"></a><a name="zh-cn_topic_0079614948_p11468461"></a>Name of the Pod.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s6a7fc85aeb5e45b0b6b5f3c3337f3c4e"></a>

请求参数：

“Content-Type“的详细描述请参见 [PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/json-patch+json
```

```
[ 
 { 
     "op": "add", 
     "path": "/spec/containers/0/image", 
     "value": "busybox:latest" 
 } 
 ]
```

## 响应消息<a name="s55aebe546007422f85cedc60f252aeb0"></a>

**响应参数：**

响应参数的详细描述请参见[表3](响应数据结构.md#zh-cn_topic_0079614930_table52931650)。

**响应示例：**

```
{ 
   "kind": "Pod", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "hello-world", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/pods/hello-world", 
     "uid": "b4b50f8d-5d0e-11e6-aeb9-286ed488fafe", 
     "resourceVersion": "1638", 
     "creationTimestamp": "2016-08-08T02:20:42Z", 
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
         "image": "busybox:latest", 
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
         "status": "False", 
         "lastProbeTime": null, 
         "lastTransitionTime": "2016-08-08T02:20:44Z", 
         "reason": "ContainersNotReady", 
         "message": "containers with unready status: [hello-world]" 
       } 
     ], 
     "hostIP": "127.0.0.1", 
     "podIP": "172.16.0.4", 
     "startTime": "2016-08-08T02:20:42Z", 
     "containerStatuses": [ 
       { 
         "name": "hello-world", 
         "state": { 
           "waiting": { 
             "reason": "CrashLoopBackOff", 
             "message": "Back-off 5m0s restarting failed container=hello-world pod=hello-world_default(b4b50f8d-5d0e-11e6-aeb9-286ed488fafe)" 
           } 
         }, 
         "lastState": { 
           "terminated": { 
             "exitCode": 0, 
             "reason": "Completed", 
             "startedAt": "2016-08-08T03:38:17Z", 
             "finishedAt": "2016-08-08T03:38:17Z", 
             "containerID": "docker://601ce41bd6cafd403ed30d0beb3d27573c74d0207818b973f42268b37051627c" 
           } 
         }, 
         "ready": false, 
         "restartCount": 24, 
         "image": "busybox:latest", 
         "imageID": "docker://sha256:2b8fd9751c4c0f5dd266fcae00707e67a2545ef34f9a29354585f93dac906749", 
         "containerID": "docker://601ce41bd6cafd403ed30d0beb3d27573c74d0207818b973f42268b37051627c" 
       } 
     ] 
   } 
 }
```

## 状态码<a name="s1475b257e1dc4d05a32f69a2a126377c"></a>

[表2](#zh-cn_topic_0079614948_table51397302)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614948_table51397302"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614948_row10764825"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p58289285201616"><a name="p58289285201616"></a><a name="p58289285201616"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p23811654201616"><a name="p23811654201616"></a><a name="p23811654201616"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614948_row40433035"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614948_p53850421"><a name="zh-cn_topic_0079614948_p53850421"></a><a name="zh-cn_topic_0079614948_p53850421"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614948_p66916835"><a name="zh-cn_topic_0079614948_p66916835"></a><a name="zh-cn_topic_0079614948_p66916835"></a>This operation succeeds, and the JSON of a Pod object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

