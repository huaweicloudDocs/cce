# 列出指定的Deployment<a name="cce_02_0128"></a>

## 功能介绍<a name="section13286196"></a>

This API is used to list all Deployment resource objects.

## URI<a name="section52466902"></a>

GET /apis/apps/v1/deployments \(Supports only1.9\)

GET /apis/apps/v1beta1/deployments \(Supports only1.7\)

GET /apis/extensions/v1beta1/deployments \(Compatible\)

[表1](#d0e36743)描述该API的参数。

**表 1**  参数解释

<a name="d0e36743"></a>
<table><thead align="left"><tr id="row36083750"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.61%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15513823"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p48660142"><a name="p48660142"></a><a name="p48660142"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p49157454"><a name="p49157454"></a><a name="p49157454"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p22330855"><a name="p22330855"></a><a name="p22330855"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row66759968"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p38848288"><a name="p38848288"></a><a name="p38848288"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p59703596"><a name="p59703596"></a><a name="p59703596"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p4153133"><a name="p4153133"></a><a name="p4153133"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row37378205"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p7735784"><a name="p7735784"></a><a name="p7735784"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p22618780"><a name="p22618780"></a><a name="p22618780"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p20181855"><a name="p20181855"></a><a name="p20181855"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row47418975"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p15731775"><a name="p15731775"></a><a name="p15731775"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p66314243"><a name="p66314243"></a><a name="p66314243"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p2744596"><a name="p2744596"></a><a name="p2744596"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row24701364"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p54653474"><a name="p54653474"></a><a name="p54653474"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p64855313"><a name="p64855313"></a><a name="p64855313"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p18789033"><a name="p18789033"></a><a name="p18789033"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row34883571"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p6997018"><a name="p6997018"></a><a name="p6997018"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p29887614"><a name="p29887614"></a><a name="p29887614"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p4977670"><a name="p4977670"></a><a name="p4977670"></a>Timeout for the list/watch call.</p>
</td>
</tr>
<tr id="row44799035"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p4843253"><a name="p4843253"></a><a name="p4843253"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p56759240"><a name="p56759240"></a><a name="p56759240"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p34095707"><a name="p34095707"></a><a name="p34095707"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section2440076"></a>

N/A

## 响应消息<a name="section21960685"></a>

**响应参数：**

响应参数的详细描述请参见[表4](公共响应参数.md#zh-cn_topic_0079614930_table6622802)。

**响应示例：**

```
{
    "kind": "DeploymentList",
    "apiVersion": "extensions/v1beta1",
    "metadata": {
        "selfLink": "/apis/extensions/v1beta1/deployments",
        "resourceVersion": "418820"
    },
    "items": [
        {
            "metadata": {
                "name": "nginx",
                "namespace": "default",
                "selfLink": "/apis/extensions/v1beta1/namespaces/default/deployments/nginx",
                "uid": "3f7846b5-dc93-11e7-9c19-fa163e2d897b",
                "resourceVersion": "28579",
                "generation": 2,
                "creationTimestamp": "2017-12-09T03:44:24Z",
                "labels": {
                    "app": "nginx"
                },
                "annotations": {
                    "deployment.kubernetes.io/revision": "1",
                    "service.protal.kubernetes.io/access-ip": "10.247.51.55:123",
                    "service.protal.kubernetes.io/type": "ClusterIP"
                },
                "enable": true
            },
            "spec": {
                "replicas": 1,
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
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "nginx",
                                "image": "172.16.5.235:20202/test-01/mysql:v1",
                                "resources": {},
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "Always"
                            }
                        ],
                        "restartPolicy": "Always",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "ClusterFirst",
                        "securityContext": {},
                        "schedulerName": "default-scheduler"
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
                "observedGeneration": 2,
                "replicas": 1,
                "updatedReplicas": 1,
                "readyReplicas": 1,
                "availableReplicas": 1,
                "conditions": [
                    {
                        "type": "Available",
                        "status": "True",
                        "lastUpdateTime": "2017-12-09T03:44:24Z",
                        "lastTransitionTime": "2017-12-09T03:44:24Z",
                        "reason": "MinimumReplicasAvailable",
                        "message": "Deployment has minimum availability."
                    }
                ]
            }
        },
        {
            "metadata": {
                "name": "nginx1",
                "namespace": "default",
                "selfLink": "/apis/extensions/v1beta1/namespaces/default/deployments/nginx1",
                "uid": "179598d2-dc94-11e7-9c19-fa163e2d897b",
                "resourceVersion": "2789",
                "generation": 1,
                "creationTimestamp": "2017-12-09T03:50:26Z",
                "labels": {
                    "app": "nginx"
                },
                "annotations": {
                    "deployment.kubernetes.io/revision": "1"
                },
                "enable": true
            },
            "spec": {
                "replicas": 1,
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
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "nginx",
                                "image": "172.16.5.235:20202/test-01/mysql:v1",
                                "resources": {},
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "Always"
                            }
                        ],
                        "restartPolicy": "Always",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "ClusterFirst",
                        "securityContext": {},
                        "schedulerName": "default-scheduler"
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
                "observedGeneration": 1,
                "replicas": 1,
                "updatedReplicas": 1,
                "readyReplicas": 1,
                "availableReplicas": 1,
                "conditions": [
                    {
                        "type": "Available",
                        "status": "True",
                        "lastUpdateTime": "2017-12-09T03:50:26Z",
                        "lastTransitionTime": "2017-12-09T03:50:26Z",
                        "reason": "MinimumReplicasAvailable",
                        "message": "Deployment has minimum availability."
                    }
                ]
            }
        },
        {
            "metadata": {
                "name": "kube-dns",
                "namespace": "kube-system",
                "selfLink": "/apis/extensions/v1beta1/namespaces/kube-system/deployments/kube-dns",
                "uid": "87211a1c-dc8e-11e7-9c19-fa163e2d897b",
                "resourceVersion": "137",
                "generation": 1,
                "creationTimestamp": "2017-12-09T03:10:36Z",
                "labels": {
                    "addonmanager.kubernetes.io/mode": "Reconcile",
                    "kubernetes-app": "kube-dns",
                    "kubernetes.io/cluster-service": "true"
                },
                "annotations": {
                    "deployment.kubernetes.io/revision": "1"
                },
                "enable": true
            },
            "spec": {
                "replicas": 1,
                "selector": {
                    "matchLabels": {
                        "kubernetes-app": "kube-dns",
                        "podaffinity": "kube-dns-pod"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "kubernetes-app": "kube-dns",
                            "podaffinity": "kube-dns-pod"
                        },
                        "annotations": {
                            "pod.alpha.kubernetes.io/init-containers": "[{\"name\":\"bootstrap-kubedns-init\",\"image\":\"euleros:2.2.5\",\"command\":[\"/bin/sh\",\"-c\",\"touch /var/log/skydns.log; touch /var/log/dnsmasq.log; touch /var/log/exechealthz.log; chown paas:paas /var/log/skydns.log /var/log/dnsmasq.log /var/log/exechealthz.log; chmod 640 /var/log/skydns.log /var/log/dnsmasq.log /var/log/exechealthz.log\"],\"resources\":{},\"volumeMounts\":[{\"name\":\"logfile\",\"mountPath\":\"/var/log\",\"policy\":{\"logs\":{\"rotate\":\"Hourly\"}}}],\"terminationMessagePath\":\"/dev/termination-log\",\"terminationMessagePolicy\":\"File\",\"imagePullPolicy\":\"Never\"}]",
                            "pod.beta.kubernetes.io/init-containers": "[{\"name\":\"bootstrap-kubedns-init\",\"image\":\"euleros:2.2.5\",\"command\":[\"/bin/sh\",\"-c\",\"touch /var/log/skydns.log; touch /var/log/dnsmasq.log; touch /var/log/exechealthz.log; chown paas:paas /var/log/skydns.log /var/log/dnsmasq.log /var/log/exechealthz.log; chmod 640 /var/log/skydns.log /var/log/dnsmasq.log /var/log/exechealthz.log\"],\"resources\":{},\"volumeMounts\":[{\"name\":\"logfile\",\"mountPath\":\"/var/log\",\"policy\":{\"logs\":{\"rotate\":\"Hourly\"}}}],\"terminationMessagePath\":\"/dev/termination-log\",\"terminationMessagePolicy\":\"File\",\"imagePullPolicy\":\"Never\"}]"
                        },
                        "enable": true
                    },
                    "spec": {
                        "volumes": [
                            {
                                "name": "crypto",
                                "emptyDir": {
                                    "sizeLimit": "0"
                                }
                            },
                            {
                                "name": "material",
                                "hostPath": {
                                    "path": "/var/paas/srv/kubernetes"
                                }
                            },
                            {
                                "name": "logfile",
                                "hostPath": {
                                    "path": "/var/paas/sys/log/kubernetes"
                                }
                            },
                            {
                                "name": "kube-dns-config",
                                "configMap": {
                                    "name": "kube-dns",
                                    "defaultMode": 420,
                                    "optional": true
                                }
                            }
                        ],
                        "initContainers": [
                            {
                                "name": "bootstrap-kubedns-init",
                                "image": "euleros:2.2.5",
                                "command": [
                                    "/bin/sh",
                                    "-c",
                                    "touch /var/log/skydns.log; touch /var/log/dnsmasq.log; touch /var/log/exechealthz.log; chown paas:paas /var/log/skydns.log /var/log/dnsmasq.log /var/log/exechealthz.log; chmod 640 /var/log/skydns.log /var/log/dnsmasq.log /var/log/exechealthz.log"
                                ],
                                "resources": {},
                                "volumeMounts": [
                                    {
                                        "name": "logfile",
                                        "mountPath": "/var/log",
                                        "policy": {
                                            "logs": {
                                                "rotate": "Hourly"
                                            }
                                        }
                                    }
                                ],
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "Never"
                            }
                        ],
                        "containers": [
                            {
                                "name": "kubedns",
                                "image": "cfe-kubedns-amd64:2.11.25",
                                "command": [
                                    "/bin/sh",
                                    "-c",
                                    "/kube-dns 1>>/var/log/skydns.log 2>&1 --domain=cluster.local. --dns-port=10053 --config-dir=/kube-dns-config --v=2"
                                ],
                                "ports": [
                                    {
                                        "name": "dns-local",
                                        "containerPort": 10053,
                                        "protocol": "UDP"
                                    },
                                    {
                                        "name": "dns-tcp-local",
                                        "containerPort": 10053,
                                        "protocol": "TCP"
                                    },
                                    {
                                        "name": "metrics",
                                        "containerPort": 10055,
                                        "protocol": "TCP"
                                    }
                                ],
                                "env": [
                                    {
                                        "name": "PROMETHEUS_PORT",
                                        "value": "10055"
                                    },
                                    {
                                        "name": "PAAS_CRYPTO_PATH",
                                        "value": "/var/paas/kubernetes/material"
                                    }
                                ],
                                "resources": {
                                    "limits": {
                                        "cpu": "100m",
                                        "memory": "512Mi"
                                    },
                                    "requests": {
                                        "cpu": "100m",
                                        "memory": "100Mi"
                                    }
                                },
                                "volumeMounts": [
                                    {
                                        "name": "crypto",
                                        "mountPath": "/var/paas"
                                    },
                                    {
                                        "name": "material",
                                        "readOnly": true,
                                        "mountPath": "/var/paas/kubernetes/material"
                                    },
                                    {
                                        "name": "logfile",
                                        "mountPath": "/var/log",
                                        "policy": {
                                            "logs": {
                                                "rotate": "Hourly"
                                            }
                                        }
                                    },
                                    {
                                        "name": "kube-dns-config",
                                        "mountPath": "/kube-dns-config"
                                    }
                                ],
                                "livenessProbe": {
                                    "httpGet": {
                                        "path": "/healthcheck/kubedns",
                                        "port": 10054,
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
                                        "path": "/readiness",
                                        "port": 8081,
                                        "scheme": "HTTP"
                                    },
                                    "initialDelaySeconds": 3,
                                    "timeoutSeconds": 5,
                                    "periodSeconds": 10,
                                    "successThreshold": 1,
                                    "failureThreshold": 3
                                },
                                "terminationMessagePath": "/dev/termination-log",
                                "terminationMessagePolicy": "File",
                                "imagePullPolicy": "IfNotPresent"
                            },
                            {
                                "name": "dnsmasq",
                                "image": "cfe-kube-dnsmasq-amd64:2.11.25",
                                "command": [
                                    "/bin/sh",
                                    "-c",
                                    "/dnsmasq-nanny 1>>/var/log/dnsmasq.log 2>&1 -v=2 -logtostderr -configDir=/etc/kubernetes/dns/dnsmasq-nanny -restartDnsmasq=true -- -k --port=5353 --cache-size=1000 --log-facility=- --server=/cluster.local/127.0.0.1#10053 --server=/in-addr.arpa/127.0.0.1#10053 --server=/ip6.arpa/127.0.0.1#10053"
                                ],
                                "ports": [
                                    {
                                        "name": "dns",
                                        "containerPort": 5353,
                                        "protocol": "UDP"
                                    },
                                    {
                                        "name": "dns-tcp",
                                        "containerPort": 5353,
                                        "protocol": "TCP"
                                    }
                                ],
                                "resources": {
                                    "requests": {
                                        "cpu": "150m",
                                        "memory": "200Mi"
                                    }
                                },
                                "volumeMounts": [
                                    {
                                        "name": "logfile",
                                        "mountPath": "/var/log",
                                        "policy": {
                                            "logs": {
                                                "rotate": "Hourly"
                                            }
                                        }
                                    },
                                    {
                                        "name": "kube-dns-config",
                                        "mountPath": "/etc/kubernetes/dns/dnsmasq-nanny"
                                    }
                                ],
                                "livenessProbe": {
                                    "httpGet": {
                                        "path": "/healthcheck/dnsmasq",
                                        "port": 10054,
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
                                "imagePullPolicy": "IfNotPresent"
                            },
                            {
                                "name": "sidecar",
                                "image": "cfe-exechealthz-amd64:2.11.25",
                                "command": [
                                    "/bin/sh",
                                    "-c",
                                    "/sidecar 1>>/var/log/exechealthz.log 2>&1 --v=2 --logtostderr --probe=kubedns,127.0.0.1:10053,kubernetes.default.svc.cluster.local,5,A --probe=dnsmasq,127.0.0.1:5353,kubernetes.default.svc.cluster.local,5,A"
                                ],
                                "ports": [
                                    {
                                        "name": "metrics",
                                        "containerPort": 10054,
                                        "protocol": "TCP"
                                    }
                                ],
                                "resources": {
                                    "limits": {
                                        "cpu": "50m",
                                        "memory": "50Mi"
                                    },
                                    "requests": {
                                        "cpu": "50m",
                                        "memory": "50Mi"
                                    }
                                },
                                "volumeMounts": [
                                    {
                                        "name": "logfile",
                                        "mountPath": "/var/log",
                                        "policy": {
                                            "logs": {
                                                "rotate": "Hourly"
                                            }
                                        }
                                    }
                                ],
                                "livenessProbe": {
                                    "httpGet": {
                                        "path": "/metrics",
                                        "port": 10054,
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
                                "imagePullPolicy": "IfNotPresent"
                            }
                        ],
                        "restartPolicy": "Always",
                        "terminationGracePeriodSeconds": 30,
                        "dnsPolicy": "Default",
                        "securityContext": {},
                        "affinity": {
                            "podAntiAffinity": {
                                "requiredDuringSchedulingIgnoredDuringExecution": [
                                    {
                                        "labelSelector": {
                                            "matchExpressions": [
                                                {
                                                    "key": "podaffinity",
                                                    "operator": "In",
                                                    "values": [
                                                        "kube-dns-pod"
                                                    ]
                                                }
                                            ]
                                        },
                                        "topologyKey": "kubernetes.io/hostname",
                                        "numOfMatchingPods": "1"
                                    }
                                ]
                            }
                        },
                        "schedulerName": "default-scheduler"
                    }
                },
                "strategy": {
                    "type": "RollingUpdate",
                    "rollingUpdate": {
                        "maxUnavailable": 0,
                        "maxSurge": "10%"
                    }
                }
            },
            "status": {
                "observedGeneration": 1,
                "replicas": 1,
                "updatedReplicas": 1,
                "readyReplicas": 1,
                "availableReplicas": 1,
                "conditions": [
                    {
                        "type": "Available",
                        "status": "True",
                        "lastUpdateTime": "2017-12-09T03:10:59Z",
                        "lastTransitionTime": "2017-12-09T03:10:59Z",
                        "reason": "MinimumReplicasAvailable",
                        "message": "Deployment has minimum availability."
                    }
                ]
            }
        },
        {
            "metadata": {
                "name": "deploy-12130304",
                "namespace": "ns-12130304-s",
                "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130304-s/deployments/deploy-12130304",
                "uid": "9c31c8f3-dfb3-11e7-9c19-fa163e2d897b",
                "resourceVersion": "418807",
                "generation": 2,
                "creationTimestamp": "2017-12-13T03:13:37Z",
                "labels": {
                    "cce/appgroup": "deploy_test"
                },
                "annotations": {
                    "deployment.kubernetes.io/revision": "1"
                },
                "enable": true
            },
            "spec": {
                "replicas": 1,
                "selector": {
                    "matchLabels": {
                        "cce/appgroup": "deploy_test"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "cce/appgroup": "deploy_test"
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "deploycon-12130304",
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
                "strategy": {
                    "type": "RollingUpdate",
                    "rollingUpdate": {
                        "maxUnavailable": "25%",
                        "maxSurge": "25%"
                    }
                },
                "revisionHistoryLimit": 2,
                "progressDeadlineSeconds": 600
            },
            "status": {
                "observedGeneration": 2,
                "replicas": 1,
                "updatedReplicas": 1,
                "readyReplicas": 1,
                "availableReplicas": 1,
                "conditions": [
                    {
                        "type": "Progressing",
                        "status": "True",
                        "lastUpdateTime": "2017-12-13T03:13:37Z",
                        "lastTransitionTime": "2017-12-13T03:13:37Z",
                        "reason": "NewReplicaSetAvailable",
                        "message": "ReplicaSet \"deploy-12130304-1294264020\" has successfully progressed."
                    },
                    {
                        "type": "Available",
                        "status": "True",
                        "lastUpdateTime": "2017-12-13T03:13:39Z",
                        "lastTransitionTime": "2017-12-13T03:13:39Z",
                        "reason": "MinimumReplicasAvailable",
                        "message": "Deployment has minimum availability."
                    }
                ]
            }
        },
        {
            "metadata": {
                "name": "deploy-ex-12130306",
                "namespace": "ns-12130306-s",
                "selfLink": "/apis/extensions/v1beta1/namespaces/ns-12130306-s/deployments/deploy-ex-12130306",
                "uid": "934db57d-dfb3-11e7-9c19-fa163e2d897b",
                "resourceVersion": "418771",
                "generation": 2,
                "creationTimestamp": "2017-12-13T03:13:22Z",
                "labels": {
                    "cce/appgroup": "deploy-ex-test"
                },
                "annotations": {
                    "deployment.kubernetes.io/revision": "1"
                },
                "enable": true
            },
            "spec": {
                "replicas": 1,
                "selector": {
                    "matchLabels": {
                        "cce/appgroup": "deploy-ex-test"
                    }
                },
                "template": {
                    "metadata": {
                        "creationTimestamp": null,
                        "labels": {
                            "cce/appgroup": "deploy-ex-test"
                        },
                        "enable": true
                    },
                    "spec": {
                        "containers": [
                            {
                                "name": "deploycon-12130306",
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
                "strategy": {
                    "type": "RollingUpdate",
                    "rollingUpdate": {
                        "maxUnavailable": 1,
                        "maxSurge": 1
                    }
                }
            },
            "status": {
                "observedGeneration": 2,
                "replicas": 1,
                "updatedReplicas": 1,
                "readyReplicas": 1,
                "availableReplicas": 1,
                "conditions": [
                    {
                        "type": "Available",
                        "status": "True",
                        "lastUpdateTime": "2017-12-13T03:13:22Z",
                        "lastTransitionTime": "2017-12-13T03:13:22Z",
                        "reason": "MinimumReplicasAvailable",
                        "message": "Deployment has minimum availability."
                    }
                ]
            }
        }
    ]
}
```

## 状态码<a name="section63428444"></a>

[表2](#d0e36862)描述API的状态码。

**表 2**  状态码

<a name="d0e36862"></a>
<table><thead align="left"><tr id="row54527983"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p54690482"><a name="p54690482"></a><a name="p54690482"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p744029"><a name="p744029"></a><a name="p744029"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row60266393"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p49739661"><a name="p49739661"></a><a name="p49739661"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p2380770"><a name="p2380770"></a><a name="p2380770"></a>This operation succeeds, and a Deployment resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

