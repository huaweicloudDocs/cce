# 获取指定的Node<a name="cce_02_0178"></a>

## 功能介绍<a name="section52726081"></a>

This API is used to read the specified Node.

## URI<a name="section4772685"></a>

GET /api/v1/nodes/\{name\}

[表1](#d0e44633)描述该API的参数。

**表 1**  参数解释

<a name="d0e44633"></a>
<table><thead align="left"><tr id="row34472411"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="36.36363636363636%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row54180705"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p26561024"><a name="p26561024"></a><a name="p26561024"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p3959368"><a name="p3959368"></a><a name="p3959368"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p52273376"><a name="p52273376"></a><a name="p52273376"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row698337"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p56565365"><a name="p56565365"></a><a name="p56565365"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p18391853"><a name="p18391853"></a><a name="p18391853"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p13345138"><a name="p13345138"></a><a name="p13345138"></a>Name of the Node.</p>
</td>
</tr>
<tr id="row52997380"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p64929415"><a name="p64929415"></a><a name="p64929415"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p24791242"><a name="p24791242"></a><a name="p24791242"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p61933557"><a name="p61933557"></a><a name="p61933557"></a>Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="row20531105"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p52406845"><a name="p52406845"></a><a name="p52406845"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p17096020"><a name="p17096020"></a><a name="p17096020"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="36.36363636363636%" headers="mcps1.2.4.1.3 "><p id="p42600400"><a name="p42600400"></a><a name="p42600400"></a>Should this value be exported. Export strips fields that a user cannot specify.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section42954172"></a>

N/A

## 响应消息<a name="section51043229"></a>

**响应参数：**

响应参数的详细描述请参见[表3](公共响应参数.md#zh-cn_topic_0079614930_table52931650)。

**响应示例：**

```
{
    "kind": "Node",
    "apiVersion": "v1",
    "metadata": {
        "name": "192.168.0.197",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/nodes/192.168.0.197",
        "uid": "868ecebc-dc8e-11e7-9c19-fa163e2d897b",
        "resourceVersion": "417841",
        "creationTimestamp": "2017-12-09T03:10:35Z",
        "labels": {
            "beta.kubernetes.io/arch": "amd64",
            "beta.kubernetes.io/os": "linux",
            "kubernetes.io/hostname": "192.168.0.197",
            "os.architecture": "amd64",
            "os.name": "EulerOS_2.0_SP2",
            "os.version": "3.10.0-327.44.58.35.x86_64",
            "supportContainer": "true"
        },
        "annotations": {
            "alpha.kubernetes.io/provided-node-ip": "192.168.0.197",
            "node.alpha.kubernetes.io/ttl": "0"
        },
        "enable": true
    },
    "spec": {
        "externalID": "192.168.0.197",
        "loginSecret": {},
        "schedulerHints": {}
    },
    "status": {
        "capacity": {
            "cpu": "2",
            "memory": "3744212Ki",
            "pods": "110"
        },
        "allocatable": {
            "cpu": "2",
            "memory": "3641812Ki",
            "pods": "110"
        },
        "phase": "Running",
        "conditions": [
            {
                "type": "OutOfDisk",
                "status": "False",
                "lastHeartbeatTime": "2017-12-13T03:05:57Z",
                "lastTransitionTime": "2017-12-09T03:10:35Z",
                "reason": "KubeletHasSufficientDisk",
                "message": "kubelet has sufficient disk space available"
            },
            {
                "type": "MemoryPressure",
                "status": "False",
                "lastHeartbeatTime": "2017-12-13T03:05:57Z",
                "lastTransitionTime": "2017-12-09T03:10:35Z",
                "reason": "KubeletHasSufficientMemory",
                "message": "kubelet has sufficient memory available"
            },
            {
                "type": "NetworkCardNotFound",
                "status": "False",
                "lastHeartbeatTime": "2017-12-13T03:05:57Z",
                "lastTransitionTime": "2017-12-09T03:10:35Z",
                "reason": "NetworkCardFound",
                "message": "network card has found"
            },
            {
                "type": "DiskPressure",
                "status": "False",
                "lastHeartbeatTime": "2017-12-13T03:05:57Z",
                "lastTransitionTime": "2017-12-09T03:10:35Z",
                "reason": "KubeletHasNoDiskPressure",
                "message": "kubelet has no disk pressure"
            },
            {
                "type": "Ready",
                "status": "True",
                "lastHeartbeatTime": "2017-12-13T03:05:57Z",
                "lastTransitionTime": "2017-12-09T03:10:35Z",
                "reason": "KubeletReady",
                "message": "kubelet is posting ready status"
            }
        ],
        "addresses": [
            {
                "type": "InternalIP",
                "address": "192.168.0.197"
            },
            {
                "type": "Hostname",
                "address": "192.168.0.197"
            },
            {
                "type": "DataIP",
                "address": "192.168.0.197"
            }
        ],
        "daemonEndpoints": {
            "kubeletEndpoint": {
                "Port": 10250
            }
        },
        "nodeInfo": {
            "machineID": "6f7a744cc4094fea9ed9558f18f59093",
            "systemUUID": "E73BC002-0E0C-4166-8321-6FE46B5AD12D",
            "bootID": "747fd7db-1e6c-400b-a703-a1f43371f56f",
            "kernelVersion": "3.10.0-327.44.58.35.x86_64",
            "osImage": "EulerOS 2.0 (SP2)",
            "containerRuntimeVersion": "docker://1.11.2",
            "kubeletVersion": "v1.7.3-r13",
            "kubeProxyVersion": "v1.7.3-r13",
            "operatingSystem": "linux",
            "architecture": "amd64"
        },
        "images": [
            {
                "names": [
                    "canal-agent:2.5.T3.B020",
                    "canal-agent:latest"
                ],
                "sizeBytes": 461728195
            },
            {
                "names": [
                    "cfe-kubedns-amd64:2.11.25"
                ],
                "sizeBytes": 334909612
            },
            {
                "names": [
                    "cfe-exechealthz-amd64:2.11.25"
                ],
                "sizeBytes": 326663593
            },
            {
                "names": [
                    "cfe-kube-dnsmasq-amd64:2.11.25"
                ],
                "sizeBytes": 325558483
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
                    "10.125.5.235:20202/test/redis:latest",
                    "10.125.5.235:20202/test/redis:v1"
                ],
                "sizeBytes": 109208225
            },
            {
                "names": [
                    "172.16.5.235:20202/test-01/mysql:v1"
                ],
                "sizeBytes": 108362139
            },
            {
                "names": [
                    "cfe-pause:2.11.25"
                ],
                "sizeBytes": 350164
            }
        ],
        "nodeState": {},
        "hostname": "node-v17.novalocal"
    }
}
```

## 状态码<a name="section56735883"></a>

[表2](#d0e44722)描述API的状态码。

**表 2**  状态码

<a name="d0e44722"></a>
<table><thead align="left"><tr id="row9649085"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p43378458"><a name="p43378458"></a><a name="p43378458"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p23994199"><a name="p23994199"></a><a name="p23994199"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row64481948"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p55655314"><a name="p55655314"></a><a name="p55655314"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11786592"><a name="p11786592"></a><a name="p11786592"></a>This operation succeeds, and a Node resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

