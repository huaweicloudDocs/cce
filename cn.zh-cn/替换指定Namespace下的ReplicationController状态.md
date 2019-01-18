# 替换指定Namespace下的ReplicationController状态<a name="cce_02_0020"></a>

## 功能介绍<a name="s5cd699f1cc7646178135f9434a99fb74"></a>

该API用于替换指定Namespace下的某个ReplicationController对象的状态，即修改ReplicationController对象status各字段的值。

## URI<a name="se57cf21fb2e540ecad94c48767ea612d"></a>

PUT /api/v1/namespaces/\{namespace\}/replicationcontrollers/\{name\}/status

[表1](#zh-cn_topic_0079614898_table55442294)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614898_table55442294"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614898_row16283894"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614898_p43927036"><a name="zh-cn_topic_0079614898_p43927036"></a><a name="zh-cn_topic_0079614898_p43927036"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p22501634194649"><a name="p22501634194649"></a><a name="p22501634194649"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p10693081194649"><a name="p10693081194649"></a><a name="p10693081194649"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614898_row4357576"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614898_p17419343"><a name="zh-cn_topic_0079614898_p17419343"></a><a name="zh-cn_topic_0079614898_p17419343"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614898_p1680699"><a name="zh-cn_topic_0079614898_p1680699"></a><a name="zh-cn_topic_0079614898_p1680699"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614898_p1918964"><a name="zh-cn_topic_0079614898_p1918964"></a><a name="zh-cn_topic_0079614898_p1918964"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614898_row26210932"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614898_p42710723"><a name="zh-cn_topic_0079614898_p42710723"></a><a name="zh-cn_topic_0079614898_p42710723"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614898_p37016527"><a name="zh-cn_topic_0079614898_p37016527"></a><a name="zh-cn_topic_0079614898_p37016527"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614898_p45548671"><a name="zh-cn_topic_0079614898_p45548671"></a><a name="zh-cn_topic_0079614898_p45548671"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614898_row7284856"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614898_p53202458"><a name="zh-cn_topic_0079614898_p53202458"></a><a name="zh-cn_topic_0079614898_p53202458"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614898_p14431828"><a name="zh-cn_topic_0079614898_p14431828"></a><a name="zh-cn_topic_0079614898_p14431828"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614898_p28127439"><a name="zh-cn_topic_0079614898_p28127439"></a><a name="zh-cn_topic_0079614898_p28127439"></a>Name of the ReplicationController.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079614898_ref458790189"></a>

**请求参数：**

请求参数的详细描述请参见[表1](公共请求参数.md#zh-cn_topic_0079614925_table51284307)。

**请求示例：**

```
{
  "kind": "ReplicationController",
  "apiVersion": "v1",
  "metadata": {
    "name": "frontend-controller",
    "namespace": "default",
    "selfLink": "/api/v1/namespaces/default/replicationcontrollers/frontend-controller",
    "uid": "cd4594b6-5d0b-11e6-aeb9-286ed488fafe",
    "resourceVersion": "3586",
    "generation": 4,
    "creationTimestamp": "2016-08-08T01:59:55Z",
    "labels": {
      "app": "nginx",
      "label1": "testexample"
    }
  },
  "status": {
    "replicas": 1,
    "observedGeneration": 3
  }
}
```

## 响应消息<a name="s76a8b9fc01944171a9a63cbfbc490b3b"></a>

**响应参数:**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079614898_ref458790189)。

**响应示例：**

```
{
  "kind": "ReplicationController",
  "apiVersion": "v1",
  "metadata": {
    "name": "frontend-controller",
    "namespace": "default",
    "selfLink": "/api/v1/namespaces/default/replicationcontrollers/frontend-controller/status",
    "uid": "cd4594b6-5d0b-11e6-aeb9-286ed488fafe",
    "resourceVersion": "3593",
    "generation": 4,
    "creationTimestamp": "2016-08-08T01:59:55Z",
    "labels": {
      "app": "nginx",
      "label1": "testexample"
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
          "app": "nginx",
          "label1": "testexample"
        }
      },
      "spec": {
        "containers": [
          {
            "name": "redis",
            "image": "redis:latest",
            "ports": [
              {
                "containerPort": 80,
                "protocol": "TCP"
              }
            ],
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
    "replicas": 1,
    "observedGeneration": 3
  }
}
```

## 状态码<a name="s640db036c4474963bd0cfa6776ea90b2"></a>

[表2](#zh-cn_topic_0079614898_table29218602)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614898_table29218602"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614898_row8218569"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p33367786194649"><a name="p33367786194649"></a><a name="p33367786194649"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p18436160194649"><a name="p18436160194649"></a><a name="p18436160194649"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614898_row38731835"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614898_p50270949"><a name="zh-cn_topic_0079614898_p50270949"></a><a name="zh-cn_topic_0079614898_p50270949"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614898_p45415059"><a name="zh-cn_topic_0079614898_p45415059"></a><a name="zh-cn_topic_0079614898_p45415059"></a>This operation succeeds, and a ReplicationController resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

