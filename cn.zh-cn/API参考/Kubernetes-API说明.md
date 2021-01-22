# Kubernetes API说明<a name="cce_02_0362"></a>

## Kubernetes API URL说明<a name="section41207155509"></a>

Kubernetes原生接口的URL格式为：**https://\{clusterid\}.Endpoint/uri**。其中\{clusterid\}为集群ID，uri为资源路径，也即API访问的路径。

**表 1**  URL中的参数说明

<a name="table7272144324912"></a>
<table><thead align="left"><tr id="zh-cn_topic_0092901339_row12957510145518"><th class="cellrowborder" valign="top" width="24.529999999999998%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0092901339_p195751012559"><a name="zh-cn_topic_0092901339_p195751012559"></a><a name="zh-cn_topic_0092901339_p195751012559"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="75.47%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0092901339_p5957810135511"><a name="zh-cn_topic_0092901339_p5957810135511"></a><a name="zh-cn_topic_0092901339_p5957810135511"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0092901339_row12957210115515"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0092901339_p20957181010553"><a name="zh-cn_topic_0092901339_p20957181010553"></a><a name="zh-cn_topic_0092901339_p20957181010553"></a>{clusterid}</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0092901339_p19571410195516"><a name="zh-cn_topic_0092901339_p19571410195516"></a><a name="zh-cn_topic_0092901339_p19571410195516"></a>集群ID，创建集群后，调用<a href="获取指定项目下的集群.md">获取指定项目下的集群</a>接口获取。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092901339_row195716107550"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0092901339_p119571610115515"><a name="zh-cn_topic_0092901339_p119571610115515"></a><a name="zh-cn_topic_0092901339_p119571610115515"></a>Endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0092901339_p4957181017553"><a name="zh-cn_topic_0092901339_p4957181017553"></a><a name="zh-cn_topic_0092901339_p4957181017553"></a>Web服务入口点的URL，可以从<a href="https://developer.huaweicloud.com/endpoint?cce" target="_blank" rel="noopener noreferrer">地区和终端节点</a>中获取。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092901339_row0957191065512"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0092901339_p179581410115511"><a name="zh-cn_topic_0092901339_p179581410115511"></a><a name="zh-cn_topic_0092901339_p179581410115511"></a>uri</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0092901339_p149587102555"><a name="zh-cn_topic_0092901339_p149587102555"></a><a name="zh-cn_topic_0092901339_p149587102555"></a>资源路径，也即API访问路径。从具体接口的URI模块获取，例如“<strong id="zh-cn_topic_0092901339_b19958151018554"><a name="zh-cn_topic_0092901339_b19958151018554"></a><a name="zh-cn_topic_0092901339_b19958151018554"></a>获取用户Token</strong>”API的resource-path为“v3/auth/tokens”。</p>
</td>
</tr>
</tbody>
</table>

## 如何调用API<a name="section28643518411"></a>

-   [构造请求](构造请求.md)
-   [认证鉴权](认证鉴权.md)
-   [返回结果](返回结果.md)

## API删除资源的响应体例外说明<a name="section988269203415"></a>

通过Kubernetes原生SDK调用删除资源相关接口时，可能会遇到实际响应和预期响应不一致的问题，由于SDK是通过Kubernetes的swagger2.0 OpenAPI生成，对应的响应只能有一个，而实际的响应体会有两种，例如在删除Pod时会有如下两种情况，一种是Kubernetes status响应体，另一种是对应的deployment实际的资源描述响应体，导致SDK报错，如果调用返回200则成功，示例如下：

情况1：Kubernetes status响应体

```
{ 
   "kind": "Status", 
   "apiVersion": "v1", 
   "metadata": {}, 
   "status": "Success", 
   "code": 200 
 }
```

情况2：对应的deployment实际的资源描述响应体

```
{
    "kind": "Pod",
    "apiVersion": "v1",
    "metadata": {
        "name": "test-delete-pod-6fd8bd995f-225lr",
        "generateName": "test-delete-pod-6fd8bd995f-",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/pods/test-delete-pod-6fd8bd995f-225lr",
        "uid": "e9d2cf9e-497a-4ed3-81a7-2308c2ce7ce1",
        "resourceVersion": "440357",
        "creationTimestamp": "2020-10-12T02:13:17Z",
        "deletionTimestamp": "2020-10-12T02:14:25Z",
        "deletionGracePeriodSeconds": 30,
        "labels": {
            "app": "test-delete-pod",
            "pod-template-hash": "6fd8bd995f"
        },
        "annotations": {
            "k8s.v1.cni.cncf.io/network-status": "[{\n    \"name\": \"default-network\",\n    \"ips\": [\n        \"10.0.1.133\"\n    ],\n    \"default\": true\n}]",
            "kubernetes.io/psp": "psp-global",
            "metrics.alpha.kubernetes.io/custom-endpoints": "[{\"api\":\"\",\"path\":\"\",\"port\":\"\",\"names\":\"\"}]"
        },
        "ownerReferences": [
            {
                "apiVersion": "apps/v1",
                "kind": "ReplicaSet",
                "name": "test-delete-pod-6fd8bd995f",
                "uid": "ea5c9294-d725-4fa0-8a77-a31559281c0d",
                "controller": true,
                "blockOwnerDeletion": true
            }
        ]
    },
    "spec": {
        "volumes": [
            {
                "name": "default-token-pgdkj",
                "secret": {
                    "secretName": "default-token-pgdkj",
                    "defaultMode": 420
                }
            }
        ],
        "containers": [
            {
                "name": "container-0",
                "image": "swr.cn-north-7.myhuaweicloud.com/paas_cce_y00416048/nginx:latest",
                "env": [
                    {
                        "name": "PAAS_APP_NAME",
                        "value": "test-delete-pod"
                    },
                    {
                        "name": "PAAS_NAMESPACE",
                        "value": "default"
                    },
                    {
                        "name": "PAAS_PROJECT_ID",
                        "value": "47eb1d64cbeb45cfa01ae20af4f4b563"
                    }
                ],
                "resources": {
                    "limits": {
                        "cpu": "250m",
                        "memory": "512Mi"
                    },
                    "requests": {
                        "cpu": "250m",
                        "memory": "512Mi"
                    }
                },
                "volumeMounts": [
                    {
                        "name": "default-token-pgdkj",
                        "readOnly": true,
                        "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount"
                    }
                ],
                "terminationMessagePath": "/dev/termination-log",
                "terminationMessagePolicy": "File",
                "imagePullPolicy": "Always"
            }
        ],
        "restartPolicy": "Always",
        "terminationGracePeriodSeconds": 30,
        "dnsPolicy": "ClusterFirst",
        "serviceAccountName": "default",
        "serviceAccount": "default",
        "nodeName": "192.168.0.241",
        "securityContext": {},
        "imagePullSecrets": [
            {
                "name": "default-secret"
            }
        ],
        "affinity": {},
        "schedulerName": "default-scheduler",
        "tolerations": [
            {
                "key": "node.kubernetes.io/not-ready",
                "operator": "Exists",
                "effect": "NoExecute",
                "tolerationSeconds": 300
            },
            {
                "key": "node.kubernetes.io/unreachable",
                "operator": "Exists",
                "effect": "NoExecute",
                "tolerationSeconds": 300
            }
        ],
        "priority": 0,
        "dnsConfig": {
            "options": [
                {
                    "name": "timeout",
                    "value": ""
                },
                {
                    "name": "ndots",
                    "value": "5"
                },
                {
                    "name": "single-request-reopen"
                }
            ]
        },
        "enableServiceLinks": true
    },
    "status": {
        "phase": "Running",
        "conditions": [
            {
                "type": "Initialized",
                "status": "True",
                "lastProbeTime": null,
                "lastTransitionTime": "2020-10-12T02:13:17Z"
            },
            {
                "type": "Ready",
                "status": "True",
                "lastProbeTime": null,
                "lastTransitionTime": "2020-10-12T02:13:23Z"
            },
            {
                "type": "ContainersReady",
                "status": "True",
                "lastProbeTime": null,
                "lastTransitionTime": "2020-10-12T02:13:23Z"
            },
            {
                "type": "PodScheduled",
                "status": "True",
                "lastProbeTime": null,
                "lastTransitionTime": "2020-10-12T02:13:17Z"
            }
        ],
        "hostIP": "192.168.0.241",
        "podIP": "10.0.1.133",
        "podIPs": [
            {
                "ip": "10.0.1.133"
            }
        ],
        "startTime": "2020-10-12T02:13:17Z",
        "containerStatuses": [
            {
                "name": "container-0",
                "state": {
                    "running": {
                        "startedAt": "2020-10-12T02:13:22Z"
                    }
                },
                "lastState": {},
                "ready": true,
                "restartCount": 0,
                "image": "nginx:latest",
                "imageID": "f1c72ba4d94d57",
                "containerID": "docker://8c382e61f99ff3c9fe6d5b01edaad419b878174e25792b6fe5581659b5e63c67",
                "started": true
            }
        ],
        "qosClass": "Guaranteed"
    }
}
```

详情请参见社区原生Java SDK相关issue链接：[https://github.com/kubernetes-client/java/issues/86](https://github.com/kubernetes-client/java/issues/86)

