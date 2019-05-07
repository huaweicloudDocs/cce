# 替换指定Namespace下的ReplicationController<a name="cce_02_0019"></a>

## 功能介绍<a name="sd260f7fabf5f4b4d865a12b9684b3e61"></a>

该API用于替换指定Namespace下的ReplicationController对象。

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

## URI<a name="s809d83357f834d5db9fcef24cc401c05"></a>

PUT /api/v1/namespaces/\{namespace\}/replicationcontrollers/\{name\}

[表1](#zh-cn_topic_0079615034_table32997867)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615034_table32997867"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615034_row66921528"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615034_p51934691"><a name="zh-cn_topic_0079615034_p51934691"></a><a name="zh-cn_topic_0079615034_p51934691"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p33301740194622"><a name="p33301740194622"></a><a name="p33301740194622"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p13086452194622"><a name="p13086452194622"></a><a name="p13086452194622"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615034_row26178814"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615034_p40109162"><a name="zh-cn_topic_0079615034_p40109162"></a><a name="zh-cn_topic_0079615034_p40109162"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615034_p27616715"><a name="zh-cn_topic_0079615034_p27616715"></a><a name="zh-cn_topic_0079615034_p27616715"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p28675043"><a name="p28675043"></a><a name="p28675043"></a>设置为true后，会打印漂亮的输出结果。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615034_row54818237"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615034_p11092193"><a name="zh-cn_topic_0079615034_p11092193"></a><a name="zh-cn_topic_0079615034_p11092193"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615034_p26052434"><a name="zh-cn_topic_0079615034_p26052434"></a><a name="zh-cn_topic_0079615034_p26052434"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615034_p29872375"><a name="zh-cn_topic_0079615034_p29872375"></a><a name="zh-cn_topic_0079615034_p29872375"></a><span id="ph10700343175010"><a name="ph10700343175010"></a><a name="ph10700343175010"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615034_row415920"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615034_p33689599"><a name="zh-cn_topic_0079615034_p33689599"></a><a name="zh-cn_topic_0079615034_p33689599"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615034_p44503031"><a name="zh-cn_topic_0079615034_p44503031"></a><a name="zh-cn_topic_0079615034_p44503031"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615034_p47975743"><a name="zh-cn_topic_0079615034_p47975743"></a><a name="zh-cn_topic_0079615034_p47975743"></a>ReplicationController<span id="ph15785147205113"><a name="ph15785147205113"></a><a name="ph15785147205113"></a>名称</span></p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079615034_ref458789946"></a>

**请求参数：**

请求参数的详细描述请参见[表1](公共请求参数.md#zh-cn_topic_0079614925_table51284307)。

**请求示例：**

```
{
    "apiVersion": "v1",
    "kind": "ReplicationController",
    "metadata": {
        "name": "frontend-controller"
    },
    "spec": {
        "replicas": 2,
        "selector": {
            "app": "nginx"
        },
        "template": {
            "metadata": {
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
                                "containerPort": 80
                            }
                        ]
                    }
                ]
            }
        }
    }
}
```

## 响应消息<a name="s3b4b0acea03b4a71ab54570cf27ed243"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079615034_ref458789946)。

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
    "resourceVersion": "3544",
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
    "fullyLabe;edRelicas": 2,
    "observedGeneration": 1
  }
}
```

## 状态码<a name="s212d917d62f14ec9a3abff22d4821fb3"></a>

[表2](#zh-cn_topic_0079615034_table28545349)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079615034_table28545349"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615034_row18868465"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p19895807194622"><a name="p19895807194622"></a><a name="p19895807194622"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p947651194622"><a name="p947651194622"></a><a name="p947651194622"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615034_row2482522"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615034_p66866633"><a name="zh-cn_topic_0079615034_p66866633"></a><a name="zh-cn_topic_0079615034_p66866633"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615034_p47488225"><a name="zh-cn_topic_0079615034_p47488225"></a><a name="zh-cn_topic_0079615034_p47488225"></a><span id="ph1489102319516"><a name="ph1489102319516"></a><a name="ph1489102319516"></a>操作成功，返回ReplicationController资源对象</span></p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

