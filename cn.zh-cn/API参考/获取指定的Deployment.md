# 获取指定的Deployment<a name="cce_02_0096"></a>

## 功能介绍<a name="section530813545496"></a>

该API用于获取某个Namespace下指定的Deployment对象。

## URI<a name="section158974212501"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\} （适用于1.9及以上版本的所有集群）

GET /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments/\{name\} （仅适用于1.15及以下版本的集群）

[表1](#table2027961241820)描述该API的参数。

**表 1**  参数描述

<a name="table2027961241820"></a>
<table><thead align="left"><tr id="row122809120186"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p91421758131813"><a name="p91421758131813"></a><a name="p91421758131813"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.4.1.2"><p id="p101421758131816"><a name="p101421758131816"></a><a name="p101421758131816"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p19143115818187"><a name="p19143115818187"></a><a name="p19143115818187"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row32801312121810"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1063164520553"><a name="p1063164520553"></a><a name="p1063164520553"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p12630545165513"><a name="p12630545165513"></a><a name="p12630545165513"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p12630114513557"><a name="p12630114513557"></a><a name="p12630114513557"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row29001310466"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p69007101268"><a name="p69007101268"></a><a name="p69007101268"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p1790020109614"><a name="p1790020109614"></a><a name="p1790020109614"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1900110968"><a name="p1900110968"></a><a name="p1900110968"></a>name of the Deployment</p>
</td>
</tr>
<tr id="row1744184023617"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p644184043617"><a name="p644184043617"></a><a name="p644184043617"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p194494017365"><a name="p194494017365"></a><a name="p194494017365"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p3447402366"><a name="p3447402366"></a><a name="p3447402366"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row2076664616361"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p13191114910562"><a name="p13191114910562"></a><a name="p13191114910562"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p99465435616"><a name="p99465435616"></a><a name="p99465435616"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p12191849135617"><a name="p12191849135617"></a><a name="p12191849135617"></a>Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="row1627094733719"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p319154955611"><a name="p319154955611"></a><a name="p319154955611"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p1294155405612"><a name="p1294155405612"></a><a name="p1294155405612"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p919118492563"><a name="p919118492563"></a><a name="p919118492563"></a>Should this value be exported. Export strips fields that a user can not specify.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section106320105520"></a>

N/A

## 响应消息<a name="section12955134485515"></a>

响应消息请参见[表2](创建Deployment.md#table12862324102610)

响应示例：

```
{
    "kind": "Deployment",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "name": "deployment-example",
        "namespace": "default",
        "selfLink": "/apis/apps/v1beta1/namespaces/default/deployments/deployment-example",
        "uid": "1b33145a-9c63-11e6-9c54-42010a800148",
        "resourceVersion": "2064726",
        "generation": 4,
        "creationTimestamp": "2016-10-27T16:33:35Z",
        "labels": {
            "app": "nginx"
        },
        "annotations": {
            "deployment.kubernetes.io/revision": "1"
        }
    },
    "spec": {
        "replicas": 3,
        "selector": {
            "matchLabels": {
                "app": "nginx"
            }
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
                        "name": "nginx",
                        "image": "nginx:1.10",
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
        },
        "strategy": {
            "type": "RollingUpdate",
            "rollingUpdate": {
                "maxUnavailable": 1,
                "maxSurge": 1
            }
        }
    },
    "status": {
        "observedGeneration": 4,
        "replicas": 3,
        "updatedReplicas": 3,
        "availableReplicas": 3
    }
}
```

## 状态码<a name="section164701657181718"></a>

[表2](#zh-cn_topic_0079616894_zh-cn_topic_0079614986_table13421100171015)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079616894_zh-cn_topic_0079614986_table13421100171015"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079616894_zh-cn_topic_0079614986_row58580616171015"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p3324338133814"><a name="p3324338133814"></a><a name="p3324338133814"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p17324938123815"><a name="p17324938123815"></a><a name="p17324938123815"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079616894_zh-cn_topic_0079614986_row3769153171015"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079616894_zh-cn_topic_0079614986_p34614774161656"><a name="zh-cn_topic_0079616894_zh-cn_topic_0079614986_p34614774161656"></a><a name="zh-cn_topic_0079616894_zh-cn_topic_0079614986_p34614774161656"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079616894_zh-cn_topic_0079614986_p51022873161656"><a name="zh-cn_topic_0079616894_zh-cn_topic_0079614986_p51022873161656"></a><a name="zh-cn_topic_0079616894_zh-cn_topic_0079614986_p51022873161656"></a>This operation succeeds, and a deployment resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

