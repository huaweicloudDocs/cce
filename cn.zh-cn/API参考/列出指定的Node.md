# 列出指定的Node<a name="cce_02_0179"></a>

## 功能介绍<a name="section6571091"></a>

This API is used to obtain a Node list.

## URI<a name="section59139819"></a>

GET /api/v1/nodes

[表1](#d0e44789)描述该API的参数。

**表 1**  参数解释

<a name="d0e44789"></a>
<table><thead align="left"><tr id="row42911876"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="27%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row58244357"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p20172505"><a name="p20172505"></a><a name="p20172505"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p23360209"><a name="p23360209"></a><a name="p23360209"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p13128790"><a name="p13128790"></a><a name="p13128790"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row51050248"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p41429451"><a name="p41429451"></a><a name="p41429451"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p342350"><a name="p342350"></a><a name="p342350"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p27730361"><a name="p27730361"></a><a name="p27730361"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row48246661"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p15665505"><a name="p15665505"></a><a name="p15665505"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p60946360"><a name="p60946360"></a><a name="p60946360"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p3829020"><a name="p3829020"></a><a name="p3829020"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row34461181"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p39892282"><a name="p39892282"></a><a name="p39892282"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p10049428"><a name="p10049428"></a><a name="p10049428"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p8697330"><a name="p8697330"></a><a name="p8697330"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row11167110"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p32120742"><a name="p32120742"></a><a name="p32120742"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p51643327"><a name="p51643327"></a><a name="p51643327"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p22359928"><a name="p22359928"></a><a name="p22359928"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
<tr id="row67021624"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p60042436"><a name="p60042436"></a><a name="p60042436"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p31599173"><a name="p31599173"></a><a name="p31599173"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p9396259"><a name="p9396259"></a><a name="p9396259"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.</p>
</td>
</tr>
<tr id="row17457472"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p4769140"><a name="p4769140"></a><a name="p4769140"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="27%" headers="mcps1.2.4.1.2 "><p id="p50756023"><a name="p50756023"></a><a name="p50756023"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p17597236"><a name="p17597236"></a><a name="p17597236"></a>Timeout for the list/watch call.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section62496324"></a>

N/A

## 响应消息<a name="section25596007"></a>

**响应参数：**

响应参数的详细描述请参见[表4](响应数据结构.md#zh-cn_topic_0079614930_table6622802)。

**响应示例：**

```
{
    "kind": "NodeList",
    "apiVersion": "v1",
    "metadata": {
        "selfLink": "/api/v1/nodes",
        "resourceVersion": "153893"
    },
    "items": [
        {
            "metadata": {
                "name": "192.168.0.123",
                "namespace": "default",
                "selfLink": "/api/v1/namespaces/default/nodes/192.168.0.123",
                "uid": "8c7357aa-4ed8-11e8-ac4b-fa163e28d367",
                "resourceVersion": "153881",
                "creationTimestamp": "2018-05-03T13:47:41Z",
                "labels": {
                    "beta.kubernetes.io/arch": "amd64",
                    "beta.kubernetes.io/os": "linux",
                    "failure-domain.beta.kubernetes.io/region": "southchina",
                    "failure-domain.beta.kubernetes.io/zone": "az1.dc1",
                    "kubernetes.io/availablezone": "az1.dc1",
                    "kubernetes.io/hostname": "192.168.0.123",
                    "os.architecture": "amd64",
                    "os.name": "EulerOS_2.0_SP2",
                    "os.version": "3.10.0-327.59.59.46.h38.x86_64",
                    "supportContainer": "true"
                },
                "annotations": {
                    "alpha.kubernetes.io/provided-node-ip": "192.168.0.123",
                    "node.alpha.kubernetes.io/ttl": "0"
                },
                "enable": true
            },
            "spec": {
                "externalID": "192.168.0.123",
                "loginSecret": {},
                "schedulerHints": {}
            },
            "status": {
                "capacity": {
                    "nvidia.com/gpu": "4",
                    "cpu": "2",
                    "memory": "3744164Ki",
                    "pods": "110"
                },
                "allocatable": {
                    "nvidia.com/gpu": "4",
                    "cpu": "1930m",
                    "memory": "2705828Ki",
                    "pods": "110"
                },
                "phase": "Running",   # 1.13 及以上版本集群已经废弃，不会再返回此字段
                "conditions": [
                    {
                        "type": "OutOfDisk",
                        "status": "False",
                        "lastHeartbeatTime": "2018-05-04T07:38:14Z",
                        "lastTransitionTime": "2018-05-03T13:47:41Z",
                        "reason": "KubeletHasSufficientDisk",
                        "message": "kubelet has sufficient disk space available"
                    },
                    {
                        "type": "MemoryPressure",
                        "status": "False",
                        "lastHeartbeatTime": "2018-05-04T07:38:14Z",
                        "lastTransitionTime": "2018-05-03T13:47:41Z",
                        "reason": "KubeletHasSufficientMemory",
                        "message": "kubelet has sufficient memory available"
                    },
                    {
                        "type": "NetworkCardNotFound",
                        "status": "False",
                        "lastHeartbeatTime": "2018-05-04T07:38:14Z",
                        "lastTransitionTime": "2018-05-03T13:47:41Z",
                        "reason": "NetworkCardFound",
                        "message": "network card has found"
                    },
                    {
                        "type": "DiskPressure",
                        "status": "False",
                        "lastHeartbeatTime": "2018-05-04T07:38:14Z",
                        "lastTransitionTime": "2018-05-03T13:47:41Z",
                        "reason": "KubeletHasNoDiskPressure",
                        "message": "kubelet has no disk pressure"
                    },
                    {
                        "type": "Ready",
                        "status": "True",
                        "lastHeartbeatTime": "2018-05-04T07:38:14Z",
                        "lastTransitionTime": "2018-05-03T13:47:41Z",
                        "reason": "KubeletReady",
                        "message": "kubelet is posting ready status"
                    }
                ],
                "addresses": [
                    {
                        "type": "InternalIP",
                        "address": "192.168.0.123"
                    },
                    {
                        "type": "Hostname",
                        "address": "192.168.0.123"
                    },
                    {
                        "type": "DataIP",
                        "address": "192.168.0.123"
                    }
                ],
                "daemonEndpoints": {
                    "kubeletEndpoint": {
                        "Port": 10250
                    }
                },
                "nodeInfo": {
                    "machineID": "ca7caac8-f192-4a29-8ad5-64e287b39ea9",
                    "systemUUID": "7D7F913C-6E32-44C4-BDAE-782D859E7A0B",
                    "bootID": "1b89eab6-92f3-4352-9613-61c2edf6ee4b",
                    "kernelVersion": "3.10.0-327.59.59.46.h38.x86_64",
                    "osImage": "EulerOS 2.0 (SP2)",
                    "containerRuntimeVersion": "docker://1.11.2",
                    "kubeletVersion": "v1.7.3-CCE2.0.7-B003",
                    "kubeProxyVersion": "v1.7.3-CCE2.0.7-B003",
                    "operatingSystem": "linux",
                    "architecture": "amd64"
                },
                "images": [
                    {
                        "names": [
                            "canal-agent:2.5.T8.B020",
                            "canal-agent:latest"
                        ],
                        "sizeBytes": 479214058
                    },
                    {
                        "names": [
                            "cfe-kubedns-amd64:3.7.6"
                        ],
                        "sizeBytes": 335112956
                    },
                    {
                        "names": [
                            "cfe-exechealthz-amd64:3.7.6"
                        ],
                        "sizeBytes": 326813281
                    },
                    {
                        "names": [
                            "cfe-kube-dnsmasq-amd64:3.7.6"
                        ],
                        "sizeBytes": 325716517
                    },
                    {
                        "names": [
                            "euleros:2.2.5"
                        ],
                        "sizeBytes": 288596478
                    },
                    {
                        "names": [
                            "10.125.5.235:20202/test/apache-php:latest"
                        ],
                        "sizeBytes": 244663227
                    },
                    {
                        "names": [
                            "10.125.5.235:20202/test/redis:latest"
                        ],
                        "sizeBytes": 182837415
                    },
                    {
                        "names": [
                            "10.125.5.235:20202/test/redis:v1"
                        ],
                        "sizeBytes": 109208225
                    },
                    {
                        "names": [
                            "cfe-pause:3.7.6"
                        ],
                        "sizeBytes": 350164
                    }
                ],
                "nodeState": {},
                "hostname": "wj53-64095.novalocal"
            }
        }
    ],
    "httpcode": 200,
    "header": {
        "Transfer-Encoding": "chunked",
        "X-Frame-Options": "SAMEORIGIN",
        "Strict-Transport-Security": "max-age=31536000; includeSubdomains;",
        "Server": "Web Server",
        "X-Content-Type-Options": "nosniff",
        "Connection": "keep-alive",
        "X-Download-Options": "noopen",
        "Set-Cookie": "937fe3f5c57648aa8fb270f46ce19b3d=WyIxODE0MTc3NzEwIl0; Expires=Sat, 05-May-18 07:38:19 GMT; Domain=192.145.50.250; Path=/; Secure; HttpOnly",
        "X-XSS-Protection": "1; mode=block;",
        "Date": "Fri, 04 May 2018 07:38:19 GMT",
        "Content-Type": "application/json"
    }
}
```

## 状态码<a name="section29037478"></a>

[表2](#d0e44910)描述API的状态码。

**表 2**  状态码

<a name="d0e44910"></a>
<table><thead align="left"><tr id="row27892207"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p44676315"><a name="p44676315"></a><a name="p44676315"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p62011796"><a name="p62011796"></a><a name="p62011796"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row56899585"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p45463691"><a name="p45463691"></a><a name="p45463691"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p58680345"><a name="p58680345"></a><a name="p58680345"></a>This operation succeeds, and the JSONs of a group of Node objects are returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

