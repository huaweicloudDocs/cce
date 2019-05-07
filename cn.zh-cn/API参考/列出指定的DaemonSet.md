# 列出指定的DaemonSet<a name="cce_02_0141"></a>

## 功能介绍<a name="section4435211"></a>

This API is used to list all DemonSet resource objects.

## URI<a name="section39916899"></a>

GET /apis/apps/v1/daemonsets \(Supports only1.9\)

GET /apis/extensions/v1beta1/daemonsets \(Compatible\)

[表1](#d0e33270)描述该API的参数。

**表 1**  参数解释

<a name="d0e33270"></a>
<table><thead align="left"><tr id="row19694240"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.16%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61.62%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row37178375"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p58658398"><a name="p58658398"></a><a name="p58658398"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p53709789"><a name="p53709789"></a><a name="p53709789"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p55525677"><a name="p55525677"></a><a name="p55525677"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row29969051"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p11574055"><a name="p11574055"></a><a name="p11574055"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p65083223"><a name="p65083223"></a><a name="p65083223"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p66811698"><a name="p66811698"></a><a name="p66811698"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row64434372"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p51801682"><a name="p51801682"></a><a name="p51801682"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p35186724"><a name="p35186724"></a><a name="p35186724"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p31552419"><a name="p31552419"></a><a name="p31552419"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row15536318"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p50482283"><a name="p50482283"></a><a name="p50482283"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p62533112"><a name="p62533112"></a><a name="p62533112"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p32017293"><a name="p32017293"></a><a name="p32017293"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row19720187"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p53831280"><a name="p53831280"></a><a name="p53831280"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p65366401"><a name="p65366401"></a><a name="p65366401"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p60187160"><a name="p60187160"></a><a name="p60187160"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row4813528"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p54351472"><a name="p54351472"></a><a name="p54351472"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p40393088"><a name="p40393088"></a><a name="p40393088"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p50614705"><a name="p50614705"></a><a name="p50614705"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row52879165"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p55353986"><a name="p55353986"></a><a name="p55353986"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p54487867"><a name="p54487867"></a><a name="p54487867"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p51441105"><a name="p51441105"></a><a name="p51441105"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section23707773"></a>

N/A

## 响应消息<a name="section12043371"></a>

**响应参数：**

**表 2**  响应参数

<a name="table42857549"></a>
<table><thead align="left"><tr id="row21951350"><th class="cellrowborder" valign="top" width="21%" id="mcps1.2.4.1.1"><p id="p33228892"><a name="p33228892"></a><a name="p33228892"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18%" id="mcps1.2.4.1.2"><p id="p7185731"><a name="p7185731"></a><a name="p7185731"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="61%" id="mcps1.2.4.1.3"><p id="p45173330"><a name="p45173330"></a><a name="p45173330"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row35161138"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p29479947"><a name="p29479947"></a><a name="p29479947"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.4.1.2 "><p id="p39065476"><a name="p39065476"></a><a name="p39065476"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p10186949"><a name="p10186949"></a><a name="p10186949"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row24573680"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p44311089"><a name="p44311089"></a><a name="p44311089"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.4.1.2 "><p id="p32428495"><a name="p32428495"></a><a name="p32428495"></a>array</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p9462449"><a name="p9462449"></a><a name="p9462449"></a>A list of daemon sets.</p>
</td>
</tr>
<tr id="row18053184"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p53021763"><a name="p53021763"></a><a name="p53021763"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.4.1.2 "><p id="p66904448"><a name="p66904448"></a><a name="p66904448"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p50551197"><a name="p50551197"></a><a name="p50551197"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="row52307591"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p9056472"><a name="p9056472"></a><a name="p9056472"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.4.1.2 "><p id="p62485597"><a name="p62485597"></a><a name="p62485597"></a><a href="#table1384381715515">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p52190581"><a name="p52190581"></a><a name="p52190581"></a>Standard list metadata.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="table1384381715515"></a>
<table><thead align="left"><tr id="row46876118"><th class="cellrowborder" valign="top" width="20.41%" id="mcps1.2.4.1.1"><p id="p38869215"><a name="p38869215"></a><a name="p38869215"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.37%" id="mcps1.2.4.1.2"><p id="p61398745"><a name="p61398745"></a><a name="p61398745"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="61.22%" id="mcps1.2.4.1.3"><p id="p7242476"><a name="p7242476"></a><a name="p7242476"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49769663"><td class="cellrowborder" valign="top" width="20.41%" headers="mcps1.2.4.1.1 "><p id="p4810874"><a name="p4810874"></a><a name="p4810874"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p54136518"><a name="p54136518"></a><a name="p54136518"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p22981834"><a name="p22981834"></a><a name="p22981834"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row5509921"><td class="cellrowborder" valign="top" width="20.41%" headers="mcps1.2.4.1.1 "><p id="p43650477"><a name="p43650477"></a><a name="p43650477"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p46027782"><a name="p46027782"></a><a name="p46027782"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="61.22%" headers="mcps1.2.4.1.3 "><p id="p37262867"><a name="p37262867"></a><a name="p37262867"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "DaemonSetList",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "selfLink": "/apis/extensions/v1beta1/daemonsets",
        "resourceVersion": "419049"
    },
    "items": [
        {
            "metadata": {
                "name": "icagent",
                "namespace": "default",
                "selfLink": "/apis/extensions/v1beta1/namespaces/default/daemonsets/icagent",
                "uid": "ac2cd485-dc8e-11e7-9c19-fa163e2d897b",
                "resourceVersion": "23583",
                "generation": 1,
                "creationTimestamp": "2017-12-09T03:11:39Z",
                "labels": {
                    "name": "icagent"
                },
                "enable": true
            },
            "spec": {
                "selector": {
                    "matchLabels": {
                        "app": "icagent"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "app": "icagent"
                        },
                        "annotations": {
                            "scheduler.alpha.kubernetes.io/tolerations": "[{\"key\":\"beta.k8s.io/accepted-app\",\"operator\":\"Exists\", \"effect\":\"NoSchedule\"}]"
                        },
                        "enable": true
                    },
                    "spec": {
                        "restartPolicy": "Always",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "ClusterFirst",
                        "securityContext": {},
                        "imagePullSecrets": [
                            {
                                "name": "default_secrets"
                            }
                        ],
                        "schedulerName": "default-scheduler",
                        "processes": [
                            {
                                "name": "icagent",
                                "package": "https://172.16.5.235:20202/swr/v2/domains/op_svc_apm/namespaces/op_svc_apm/repositories/default/packages/icagent-repo/versions/5.6.67/file_paths/ICProbeAgent-5.6.67.zip",
                                "env": [
                                    {
                                        "name": "cluster_id",
                                        "value": "8bfd2e95-dc8d-11e7-8766-0255ac101a0c"
                                    },
                                    {
                                        "name": "cluster_name",
                                        "value": "test-1209"
                                    }
                                ],
                                "resources": {},
                                "livenessProbe": {
                                    "exec": {
                                        "command": [
                                            "/bin/bash",
                                            "-c",
                                            "curl --connect-timeout 5 -m 5 http://127.0.0.1:28002/health 2>/dev/null | /usr/bin/grep -w 200 | /usr/bin/grep -v /usr/bin/grep 1>/dev/null"
                                        ]
                                    },
                                    "initialDelaySeconds": 15,
                                    "timeoutSeconds": 5,
                                    "periodSeconds": 10,
                                    "successThreshold": 1,
                                    "failureThreshold": 3
                                },
                                "lifecycle": {
                                    "install": {
                                        "exec": {
                                            "command": [
                                                "/bin/bash",
                                                "bin/manual/setup.sh",
                                                "-ip",
                                                "172.16.5.235:9999",
                                                "-localip",
                                                "127.0.0.1",
                                                "-user",
                                                "root"
                                            ]
                                        }
                                    },
                                    "uninstall": {
                                        "exec": {
                                            "command": [
                                                "/bin/bash",
                                                "-c",
                                                "/bin/bash bin/manual/uninstall.sh"
                                            ]
                                        }
                                    },
                                    "start": {
                                        "exec": {
                                            "command": [
                                                "/bin/bash",
                                                "-c",
                                                "cd /opt/oss/servicemgr/ICAgent/bin/manual/;/bin/bash mstart.sh"
                                            ]
                                        }
                                    },
                                    "restart": {
                                        "exec": {
                                            "command": [
                                                "/bin/bash",
                                                "-c",
                                                "cd /opt/oss/servicemgr/ICAgent/bin/manual/;/bin/bash mstop.sh;/bin/bash mstart.sh"
                                            ]
                                        }
                                    },
                                    "stop": {
                                        "exec": {
                                            "command": [
                                                "/bin/bash",
                                                "-c",
                                                "cd /opt/oss/servicemgr/ICAgent/bin/manual/;/bin/bash mstop.sh"
                                            ]
                                        }
                                    },
                                    "update": {
                                        "exec": {
                                            "command": [
                                                ""
                                            ]
                                        }
                                    }
                                }
                            }
                        ]
                    }
                },
                "updateStrategy": {
                    "type": "OnDelete"
                },
                "templateGeneration": 1,
                "revisionHistoryLimit": 10
            },
            "status": {
                "currentNumberScheduled": 1,
                "numberMisscheduled": 0,
                "desiredNumberScheduled": 1,
                "numberReady": 1,
                "observedGeneration": 1,
                "updatedNumberScheduled": 1,
                "numberAvailable": 1
            }
        },
        {
            "metadata": {
                "name": "ds-12130306",
                "namespace": "ns-12130306-s",
                "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/daemonsets/ds-12130306",
                "uid": "dc72a82b-dfb3-11e7-9c19-fa163e2d897b",
                "resourceVersion": "419012",
                "generation": 1,
                "creationTimestamp": "2017-12-13T03:15:24Z",
                "labels": {
                    "name": "daemonset-test"
                },
                "enable": true
            },
            "spec": {
                "selector": {
                    "matchLabels": {
                        "name": "daemonset-test"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "name": "daemonset-test"
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "dscon-12130306",
                                "image": "172.16.5.235:20202/test/redis:latest",
                                "resources": {},
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "IfNotPresent"
                            }
                        ],
                        "restartPolicy": "Always",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "ClusterFirst",
                        "securityContext": {},
                        "schedulerName": "default-scheduler"
                    }
                },
                "updateStrategy": {
                    "type": "OnDelete"
                },
                "templateGeneration": 1,
                "revisionHistoryLimit": 10
            },
            "status": {
                "currentNumberScheduled": 1,
                "numberMisscheduled": 0,
                "desiredNumberScheduled": 1,
                "numberReady": 1,
                "observedGeneration": 1,
                "updatedNumberScheduled": 1,
                "numberAvailable": 1
            }
        }
    ]
}
```

## 状态码<a name="section41281476"></a>

[表4](#d0e33483)描述API的状态码。

**表 4**  状态码

<a name="d0e33483"></a>
<table><thead align="left"><tr id="row43074742"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p66502078"><a name="p66502078"></a><a name="p66502078"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p17959251"><a name="p17959251"></a><a name="p17959251"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row45413212"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p54591554"><a name="p54591554"></a><a name="p54591554"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p59839724"><a name="p59839724"></a><a name="p59839724"></a>This operation succeeds, and a DaemonSet resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

