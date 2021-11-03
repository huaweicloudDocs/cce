# 列出指定Namespace下的Deployment<a name="cce_02_0127"></a>

## 功能介绍<a name="section51078739"></a>

This API is used to list all Deployment resource objects under a specified Namespace.

## URI<a name="section57055467"></a>

GET /apis/apps/v1/namespaces/\{namespace\}/deployments

**表 1**  参数解释

<a name="d0e36539"></a>
<table><thead align="left"><tr id="row2135501"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.16%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61.62%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row59065999"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p19616629"><a name="p19616629"></a><a name="p19616629"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p45443123"><a name="p45443123"></a><a name="p45443123"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p57014386"><a name="p57014386"></a><a name="p57014386"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row43367434"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p23101228"><a name="p23101228"></a><a name="p23101228"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p59260195"><a name="p59260195"></a><a name="p59260195"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p35346519"><a name="p35346519"></a><a name="p35346519"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row49683219"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p64917804"><a name="p64917804"></a><a name="p64917804"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p23850806"><a name="p23850806"></a><a name="p23850806"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p6042403"><a name="p6042403"></a><a name="p6042403"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row54381628"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p42835719"><a name="p42835719"></a><a name="p42835719"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p47141219"><a name="p47141219"></a><a name="p47141219"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p60342391"><a name="p60342391"></a><a name="p60342391"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row6210614"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p33297746"><a name="p33297746"></a><a name="p33297746"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p12762939"><a name="p12762939"></a><a name="p12762939"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p27165144"><a name="p27165144"></a><a name="p27165144"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row43159710"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p6275621"><a name="p6275621"></a><a name="p6275621"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p38563284"><a name="p38563284"></a><a name="p38563284"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p36618324"><a name="p36618324"></a><a name="p36618324"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row61129466"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p52539702"><a name="p52539702"></a><a name="p52539702"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p27857430"><a name="p27857430"></a><a name="p27857430"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p41859330"><a name="p41859330"></a><a name="p41859330"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row41189657"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p48027907"><a name="p48027907"></a><a name="p48027907"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p65055278"><a name="p65055278"></a><a name="p65055278"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.62%" headers="mcps1.2.4.1.3 "><p id="p34986178"><a name="p34986178"></a><a name="p34986178"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section43737161"></a>

N/A

## 响应消息<a name="section58090133"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Deployment.md#table12862324102610)。

**响应示例**：

```
{
    "kind": "DeploymentList",
    "apiVersion": "apps/v1",
    "metadata": {
        "selfLink": "/apis/apps/v1/namespaces/kube-system/deployments",
        "resourceVersion": "11628542"
    },
    "items": [
        {
            "metadata": {
                "name": "coredns",
                "namespace": "kube-system",
                "selfLink": "/apis/apps/v1/namespaces/kube-system/deployments/coredns",
                "uid": "08b538c7-c9f9-4bd8-96fb-9a161a25ba48",
                "resourceVersion": "10574590",
                "generation": 1,
                "creationTimestamp": "2020-11-11T02:54:56Z",
                "labels": {
                    "app": "coredns",
                    "k8s-app": "coredns",
                    "kubernetes.io/cluster-service": "true",
                    "kubernetes.io/name": "CoreDNS",
                    "release": "cceaddon-coredns"
                },
                "annotations": {
                    "deployment.kubernetes.io/revision": "1"
                }
            },
            "spec": {
                "replicas": 2,
                "selector": {
                    "matchLabels": {
                        "app": "coredns",
                        "k8s-app": "coredns"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "app": "coredns",
                            "k8s-app": "coredns",
                            "kubernetes.io/evictcritical": "",
                            "release": "cceaddon-coredns"
                        },
                        "annotations": {
                            "checksum/config": "cd3bc40fa01a7ca64fa89c3923c7ffe69e8d679a55cbd4a89d0d172bf9fdb966",
                            "scheduler.alpha.kubernetes.io/critical-pod": "",
                            "scheduler.alpha.kubernetes.io/tolerations": "[{\"key\":\"CriticalAddonsOnly\", \"operator\":\"Exists\"}]",
                            "seccomp.security.alpha.kubernetes.io/pod": "runtime/default"
                        }
                    },
                    "spec": {
                        "volumes": [
                            {
                                "name": "logfile",
                                "hostPath": {
                                    "path": "/var/paas/sys/log/coredns/",
                                    "type": ""
                                }
                            },
                            {
                                "name": "tmp",
                                "emptyDir": {}
                            },
                            {
                                "name": "config-volume",
                                "configMap": {
                                    "name": "coredns",
                                    "items": [
                                        {
                                            "key": "Corefile",
                                            "path": "Corefile"
                                        }
                                    ],
                                    "defaultMode": 420
                                }
                            }
                        ],
                        "containers": [
                            {
                                "name": "coredns",
                                "image": "coredns:1.15.7",
                                "command": [
                                    "/bin/sh",
                                    "-c",
                                    "/coredns -conf=/etc/coredns/Corefile -rmem=udp#8388608 -wmem=udp#1048576 1\u003e\u003e/var/paas/sys/log/coredns/coredns.log 2\u003e\u00261"
                                ],
                                "ports": [
                                    {
                                        "containerPort": 5353,
                                        "protocol": "UDP"
                                    }
                                ],
                                "env": [
                                    {
                                        "name": "POD_IP",
                                        "valueFrom": {
                                            "fieldRef": {
                                                "apiVersion": "v1",
                                                "fieldPath": "status.podIP"
                                            }
                                        }
                                    }
                                ],
                                "resources": {
                                    "limits": {
                                        "cpu": "500m",
                                        "memory": "512Mi"
                                    },
                                    "requests": {
                                        "cpu": "500m",
                                        "memory": "512Mi"
                                    }
                                },
                                "volumeMounts": [
                                    {
                                        "name": "config-volume",
                                        "mountPath": "/etc/coredns"
                                    },
                                    {
                                        "name": "tmp",
                                        "mountPath": "/tmp"
                                    },
                                    {
                                        "name": "logfile",
                                        "mountPath": "/var/paas/sys/log/coredns/",
                                        "policy": {
                                            "logs": {
                                                "rotate": "Daily"
                                            }
                                        }
                                    }
                                ],
                                "livenessProbe": {
                                    "httpGet": {
                                        "path": "/health",
                                        "port": 8080,
                                        "scheme": "HTTP"
                                    },
                                    "initialDelaySeconds": 60,
                                    "timeoutSeconds": 5,
                                    "periodSeconds": 10,
                                    "successThreshold": 1,
                                    "failureThreshold": 5
                                },
                                "readinessProbe": {
                                    "httpGet": {
                                        "path": "/health",
                                        "port": 8080,
                                        "scheme": "HTTP"
                                    },
                                    "initialDelaySeconds": 3,
                                    "timeoutSeconds": 3,
                                    "periodSeconds": 5,
                                    "successThreshold": 1,
                                    "failureThreshold": 3
                                },
                                "lifecycle": {
                                    "preStop": {
                                        "exec": {
                                            "command": [
                                                "sleep",
                                                "5"
                                            ]
                                        }
                                    }
                                },
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "Always",
                                "securityContext": {
                                    "capabilities": {
                                        "add": [
                                            "NET_BIND_SERVICE"
                                        ],
                                        "drop": [
                                            "all"
                                        ]
                                    },
                                    "runAsUser": 10000,
                                    "readOnlyRootFilesystem": true
                                }
                            }
                        ],
                        "restartPolicy": "Always",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "Default",
                        "serviceAccountName": "coredns",
                        "serviceAccount": "coredns",
                        "securityContext": {},
                        "affinity": {
                            "podAntiAffinity": {
                                "requiredDuringSchedulingIgnoredDuringExecution": [
                                    {
                                        "labelSelector": {
                                            "matchExpressions": [
                                                {
                                                    "key": "app",
                                                    "operator": "In",
                                                    "values": [
                                                        "coredns"
                                                    ]
                                                }
                                            ]
                                        },
                                        "topologyKey": "kubernetes.io/hostname"
                                    }
                                ]
                            }
                        },
                        "schedulerName": "default-scheduler",
                        "tolerations": [
                            {
                                "key": "node.kubernetes.io/not-ready",
                                "operator": "Exists",
                                "effect": "NoExecute",
                                "tolerationSeconds": 60
                            },
                            {
                                "key": "node.kubernetes.io/unreachable",
                                "operator": "Exists",
                                "effect": "NoExecute",
                                "tolerationSeconds": 60
                            }
                        ],
                        "priorityClassName": "system-cluster-critical"
                    }
                },
                "strategy": {
                    "type": "RollingUpdate",
                    "rollingUpdate": {
                        "maxUnavailable": 0,
                        "maxSurge": "10%"
                    }
                },
                "revisionHistoryLimit": 10,
                "progressDeadlineSeconds": 600
            },
            "status": {
                "observedGeneration": 1,
                "replicas": 2,
                "updatedReplicas": 2,
                "readyReplicas": 2,
                "availableReplicas": 2,
                "conditions": [
                    {
                        "type": "Progressing",
                        "status": "True",
                        "lastUpdateTime": "2020-11-11T10:59:56Z",
                        "lastTransitionTime": "2020-11-11T10:59:56Z",
                        "reason": "NewReplicaSetAvailable",
                        "message": "ReplicaSet \"coredns-749d9dd57\" has successfully progressed."
                    },
                    {
                        "type": "Available",
                        "status": "True",
                        "lastUpdateTime": "2020-12-11T12:23:40Z",
                        "lastTransitionTime": "2020-12-11T12:23:40Z",
                        "reason": "MinimumReplicasAvailable",
                        "message": "Deployment has minimum availability."
                    }
                ]
            }
        },
        {
            "metadata": {
                "name": "everest-csi-controller",
                "namespace": "kube-system",
                "selfLink": "/apis/apps/v1/namespaces/kube-system/deployments/everest-csi-controller",
                "uid": "e51e7fcb-5e2e-43b7-a830-cf7a708a9081",
                "resourceVersion": "10202131",
                "generation": 1,
                "creationTimestamp": "2020-11-11T02:54:56Z",
                "labels": {
                    "app": "everest-csi-controller",
                    "release": "cceaddon-everest"
                },
                "annotations": {
                    "deployment.kubernetes.io/revision": "1"
                }
            },
            "spec": {
                "replicas": 2,
                "selector": {
                    "matchLabels": {
                        "app": "everest-csi-controller"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "app": "everest-csi-controller",
                            "release": "cceaddon-everest"
                        },
                        "annotations": {
                            "seccomp.security.alpha.kubernetes.io/pod": "runtime/default"
                        }
                    },
                    "spec": {
                        "volumes": [
                            {
                                "name": "cipher-root",
                                "hostPath": {
                                    "path": "/var/paas/srv/kubernetes",
                                    "type": "Directory"
                                }
                            },
                            {
                                "name": "host-log",
                                "hostPath": {
                                    "path": "/var/paas/sys/log/everest-csi-controller",
                                    "type": "DirectoryOrCreate"
                                }
                            },
                            {
                                "name": "localtime",
                                "hostPath": {
                                    "path": "/etc/localtime",
                                    "type": "File"
                                }
                            }
                        ],
                        "containers": [
                            {
                                "name": "everest-csi-controller",
                                "image": "everest-csi-controller:1.1.15",
                                "args": [
                                    "--controllers=*",
                                    "--v=2",
                                    "--leader-elect=true",
                                    "--leader-elect-resource-lock=endpoints",
                                    "--leader-elect-namespace=kube-system",
                                    "--feature-gates=Topology=true",
                                    "--provision-with-strict-topology=true"
                                ],
                                "ports": [
                                    {
                                        "name": "healthzport",
                                        "containerPort": 3225,
                                        "protocol": "TCP"
                                    }
                                ],
                                "resources": {
                                    "limits": {
                                        "cpu": "250m",
                                        "memory": "600Mi"
                                    },
                                    "requests": {
                                        "cpu": "250m",
                                        "memory": "600Mi"
                                    }
                                },
                                "volumeMounts": [
                                    {
                                        "name": "cipher-root",
                                        "readOnly": true,
                                        "mountPath": "/var/paas/everest-csi-driver/cipher"
                                    },
                                    {
                                        "name": "host-log",
                                        "mountPath": "/var/paas/sys/log/everest-csi-controller",
                                        "policy": {
                                            "logs": {
                                                "rotate": "Hourly"
                                            }
                                        }
                                    },
                                    {
                                        "name": "localtime",
                                        "readOnly": true,
                                        "mountPath": "/etc/localtime"
                                    }
                                ],
                                "livenessProbe": {
                                    "httpGet": {
                                        "path": "/healthz",
                                        "port": "healthzport",
                                        "scheme": "HTTP"
                                    },
                                    "initialDelaySeconds": 60,
                                    "timeoutSeconds": 5,
                                    "periodSeconds": 10,
                                    "successThreshold": 1,
                                    "failureThreshold": 5
                                },
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "IfNotPresent",
                                "securityContext": {
                                    "capabilities": {
                                        "add": [
                                            "SYS_ADMIN",
                                            "DAC_OVERRIDE"
                                        ],
                                        "drop": [
                                            "all"
                                        ]
                                    }
                                }
                            }
                        ],
                        "restartPolicy": "Always",
                        "terminationGracePeriodSeconds": 10,
                        "dnsPolicy": "Default",
                        "serviceAccountName": "everest-csi-plugin",
                        "serviceAccount": "everest-csi-plugin",
                        "securityContext": {},
                        "affinity": {
                            "nodeAffinity": {
                                "requiredDuringSchedulingIgnoredDuringExecution": {
                                    "nodeSelectorTerms": [
                                        {
                                            "matchExpressions": [
                                                {
                                                    "key": "kubernetes.io/role",
                                                    "operator": "NotIn",
                                                    "values": [
                                                        "virtual-kubelet",
                                                        "edge"
                                                    ]
                                                }
                                            ]
                                        }
                                    ]
                                }
                            },
                            "podAffinity": {
                                "preferredDuringSchedulingIgnoredDuringExecution": [
                                    {
                                        "weight": 50,
                                        "podAffinityTerm": {
                                            "labelSelector": {
                                                "matchExpressions": [
                                                    {
                                                        "key": "k8s-app",
                                                        "operator": "In",
                                                        "values": [
                                                            "coredns"
                                                        ]
                                                    }
                                                ]
                                            },
                                            "topologyKey": "kubernetes.io/hostname"
                                        }
                                    }
                                ]
                            },
                            "podAntiAffinity": {
                                "requiredDuringSchedulingIgnoredDuringExecution": [
                                    {
                                        "labelSelector": {
                                            "matchExpressions": [
                                                {
                                                    "key": "app",
                                                    "operator": "In",
                                                    "values": [
                                                        "everest-csi-controller"
                                                    ]
                                                }
                                            ]
                                        },
                                        "topologyKey": "kubernetes.io/hostname"
                                    }
                                ]
                            }
                        },
                        "schedulerName": "default-scheduler",
                        "tolerations": [
                            {
                                "key": "node.kubernetes.io/not-ready",
                                "operator": "Exists",
                                "effect": "NoExecute",
                                "tolerationSeconds": 60
                            },
                            {
                                "key": "node.kubernetes.io/unreachable",
                                "operator": "Exists",
                                "effect": "NoExecute",
                                "tolerationSeconds": 60
                            }
                        ],
                        "priorityClassName": "system-cluster-critical"
                    }
                },
                "strategy": {
                    "type": "RollingUpdate",
                    "rollingUpdate": {
                        "maxUnavailable": "50%",
                        "maxSurge": "25%"
                    }
                },
                "revisionHistoryLimit": 10,
                "progressDeadlineSeconds": 600
            },
            "status": {
                "observedGeneration": 1,
                "replicas": 2,
                "updatedReplicas": 2,
                "readyReplicas": 2,
                "availableReplicas": 2,
                "conditions": [
                    {
                        "type": "Available",
                        "status": "True",
                        "lastUpdateTime": "2020-11-11T02:55:39Z",
                        "lastTransitionTime": "2020-11-11T02:55:39Z",
                        "reason": "MinimumReplicasAvailable",
                        "message": "Deployment has minimum availability."
                    },
                    {
                        "type": "Progressing",
                        "status": "True",
                        "lastUpdateTime": "2020-11-11T10:59:55Z",
                        "lastTransitionTime": "2020-11-11T10:59:55Z",
                        "reason": "NewReplicaSetAvailable",
                        "message": "ReplicaSet \"everest-csi-controller-66955966db\" has successfully progressed."
                    }
                ]
            }
        }
    ]
}
```

## 状态码<a name="section53049152"></a>

[表2](#d0e36668)描述API的状态码。

**表 2**  状态码

<a name="d0e36668"></a>
<table><thead align="left"><tr id="row17031726"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p37392545"><a name="p37392545"></a><a name="p37392545"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p8897276"><a name="p8897276"></a><a name="p8897276"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49590760"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p57428620"><a name="p57428620"></a><a name="p57428620"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p21206673"><a name="p21206673"></a><a name="p21206673"></a>This operation succeeds, and a Deployment resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

