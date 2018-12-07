# PATCH请求方法操作示例<a name="cce_02_0086"></a>

本章节主要介绍PATCH请求方法中，“Merge Patch“与“Strategic Merge Patch“类型的操作示例。

## 操作示例<a name="section34671706181610"></a>

以创建ReplicationController资源对象为例。

**请求示例**

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
                    "app": "nginx"
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

**响应示例**

```
{
    "kind": "ReplicationController",
    "apiVersion": "v1",
    "metadata": {
        "name": "frontend-controller",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/replicationcontrollers/nginx-controller",
        "uid": "549b2234-5d46-11e6-aeb9-286ed488fafe",
        "resourceVersion": "4110",
        "generation": 1,
        "creationTimestamp": "2016-08-08T08:58:52Z",
        "labels": {
            "app": "nginx"
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
                    "app": "nginx"
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
        "replicas": 0
    }
}
```

-   如果使用“Merge Patch“类型操作，添加一个容器到指定ReplicationController的“template“参数中，则其中的整个容器列表将被新添加的容器所替换。

    **Merge Patch请求**

    ```
    {
        "spec": {
            "template": {
                "spec": {
                    "containers": [
                        {
                            "name": "hello-world",
                            "image": "busybox:latest"
                        }
                    ]
                }
            }
        }
    }
    ```

    **Merge Patch响应**

    ```
    {
        "kind": "ReplicationController",
        "apiVersion": "v1",
        "metadata": {
            "name": "frontend-controller",
            "namespace": "default",
            "selfLink": "/api/v1/namespaces/default/replicationcontrollers/nginx-controller",
            "uid": "549b2234-5d46-11e6-aeb9-286ed488fafe",
            "resourceVersion": "4159",
            "generation": 2,
            "creationTimestamp": "2016-08-08T08:58:52Z",
            "labels": {
                "app": "nginx"
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
                        "app": "nginx"
                    }
                },
                "spec": {
                    "containers": [
                        {
                            "name": "hello-world",
                            "image": "busybox:latest",
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
            "replicas": 2,
            "fullyLabeledReplicas": 2,
            "observedGeneration": 1
        }
    }
    ```

    其中“containers“参数列表被新添加的内容所替换。


-   而使用“Strategic Merge Patch“类型操作，是添加元数据到资源对象中，并通过这些新元数据来决定各个列表是否需要被合并。

    **Strategic Merge Patch请求**

    ```
    {
        "spec": {
            "template": {
                "spec": {
                    "containers": [
                        {
                            "name": "hello-world",
                            "image": "busybox:latest"
                        }
                    ]
                }
            }
        }
    }'
    ```

    **Strategic Merge Patch响应**

    ```
    {
        "kind": "ReplicationController",
        "apiVersion": "v1",
        "metadata": {
            "name": "frontend-controller",
            "namespace": "default",
            "selfLink": "/api/v1/namespaces/default/replicationcontrollers/nginx-controller",
            "uid": "f2e048bb-5d46-11e6-aeb9-286ed488fafe",
            "resourceVersion": "4250",
            "generation": 2,
            "creationTimestamp": "2016-08-08T09:03:18Z",
            "labels": {
                "app": "nginx"
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
                        "app": "nginx"
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
                        },
                        {
                            "name": "hello-world",
                            "image": "busybox:latest",
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
            "replicas": 2,
            "fullyLabeledReplicas": 2,
            "observedGeneration": 1
        }
    }
    ```

    其中“containers“参数列表与新添加的内容合并，而不是替换，合并的依据为“name”域的值。


