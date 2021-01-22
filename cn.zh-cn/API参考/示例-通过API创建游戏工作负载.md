# 示例：通过API创建游戏工作负载<a name="cce_02_0237"></a>

本节通过调用一系列API使用2048镜像创建一个游戏工作负载为例，介绍使用CCE API的基本流程，创建出来的工作负载如下所示。

**图 1**  使用2048镜像创建工作负载<a name="fig7882172214119"></a>  
![](figures/使用2048镜像创建工作负载.png "使用2048镜像创建工作负载")

创建2048工作负载的流程如下：

1.  首先调用[Token认证](认证鉴权.md#zh-cn_topic_0121671869_section2417768214391)获取用户的token，因为在后续的请求中需要将token放到请求消息头中作为认证。
2.  其次创建集群并获取集群UUID。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果您已经创建集群，可以跳过创建集群的步骤，直接使用获取已创建的集群UUID。

    1.  调用CCE的[创建集群](创建集群.md)接口，创建一个集群。
    2.  调用CCE的[创建节点](创建节点.md)接口，为集群添加一个节点。

3.  调用kubernetes接口创建工作负载。
    1.  调用[创建Deployment](创建Deployment.md)接口，使用2048镜像创建工作负载。
    2.  调用[创建Service](创建Service.md)创建一个Service，Service创建后，用户就可以从外部访问这个工作负载。


## 前提条件<a name="section196401353584"></a>

-   已获取Token，具体请参见[Token认证](认证鉴权.md#zh-cn_topic_0121671869_section2417768214391)。
-   已创建VPC和子网，并获取VPC和子网的ID，具体请参见[创建VPC和子网](创建VPC和子网.md)。
-   已创建密钥对，并获取密钥对的名称具体请参见[创建密钥对](创建密钥对.md)。
-   已获取IAM和CCE的Endpoint，具体请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint)。
-   已经上传用于创建工作负载的2048镜像，具体方法请参考[客户端上传镜像](https://support.huaweicloud.com/usermanual-swr/swr_01_0011.html)，并获取镜像地址。

## 创建集群<a name="section844664611353"></a>

假设已获取前提条件中的信息为如下值（实际操作中您需要根据实际情况替换）：

-   IAM的Endpoint：下面示例中以**iam\_endpoint**代替，具体请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint?IAM)。
-   CCE的Endpoint：下面示例中以**cce\_endpoint**代替，具体请参见[地区和终端节点](https://developer.huaweicloud.com/endpoint?CCE)。
-   VPC的ID：**219ab8a0-1272-4049-a383-8ad0b770fa11**
-   子网的ID：**d23ef2e9-8b90-49b3-bc4a-fd7d6bea6bec**
-   密钥对的名称：**keypair-cce**
-   区域的名称：**cn-north-4**
-   项目ID：下面示例中以project\_id代替，获取方式请参见[如何获取接口URI中参数](如何获取接口URI中参数.md)。

则可以通过如下步骤创建一个带有单个节点的集群。

1.  调用其他接口前，需要调用[Token认证](认证鉴权.md#zh-cn_topic_0121671869_section2417768214391)获取token，并设置成环境变量。

    其中加粗的部分，需要替换为真实的数据。

    -   username：华为云的用户帐号。
    -   password：华为云的用户密码。
    -   domainname：若是子帐号，请填写对应的主帐号名称。若不是子帐号，请与username保持一致。
    -   cn-north-4：此处以中国华北区4为例。

        ```
        curl -H "Content-Type:application/json" https://{iam_endpoint}/v3/auth/tokens -X POST -d '{ 
           "auth": { 
             "identity": { 
               "methods": [ 
                 "password" 
               ], 
               "password": { 
                 "user": { 
                   "name": "username", 
                   "password": "******", 
                   "domain": { 
                     "name": "domainname" 
                   } 
                 } 
               } 
             }, 
             "scope": { 
               "project": { 
                 "name": "cn-north-4" 
               } 
             } 
           } 
         }' -v
        ```


    响应Header中“X-Subject-Token“的值即为Token：

    ```
    X-Subject-Token:
    ******
    ```

    使用如下命令将token设置为环境变量，方便后续事项。

    **export Token=_\{_**_**X-Subject-Token\}**_

    **X-Subject-Token**即为上一步骤获取到的token。

2.  调用[创建集群](创建集群.md)接口创建一个不带节点的空集群。

    ```
    curl -H "X-Auth-Token:$Token" -H "Content-Type:application/json;charset=utf-8" -X POST https://{cce_endpoint}/api/v3/projects/{project_id}/clusters -d '{
        "kind": "Cluster",
        "apiVersion": "v3",
        "metadata": {
            "name": "cluster-sample"
        },
        "spec": {
            "type": "VirtualMachine",
            "flavor": "cce.s1.small",
            "version": "v1.9.7-r0",
            "hostNetwork": {
                "vpc": "219ab8a0-1272-4049-a383-8ad0b770fa11",
                "subnet": "d23ef2e9-8b90-49b3-bc4a-fd7d6bea6bec"
            },
            "containerNetwork": {
                "mode": "overlay_l2"
            }
        }
    }'
    ```

    响应消息体中items数组中metadata.uid参数即为集群ID。

    ```
    "uid":"d8cbca81-889a-11e8-88e9-0255ac10212d"
    ```

    为方便后续事项，使用如下命令将集群ID设置为环境变量，后续使用中**\{cluster\_id\}**即为集群ID。

    ```
    export cluster_id=d8cbca81-889a-11e8-88e9-0255ac10212d
    ```

3.  集群创建成功后，调用[创建节点](创建节点.md)接口为该集群创建一个节点。

    ```
    curl -H "X-Auth-Token:$Token" -H "Content-Type:application/json;charset=utf-8" -X POST https://{cce_endpoint}/api/v3/projects/{project_id}/clusters/{cluster_id}/nodes -d '{
        "kind": "Node",
        "apiVersion": "v3",
        "metadata": {
            "name": "node-sample"
        },
        "spec": {
            "flavor": "c3.large.2",
            "az": "cn-north-4a",
            "login": {
                "sshKey": "keypair-cce"
            },
            "rootVolume": {
                "size": 40,
                "volumetype": "SATA"
            },
            "dataVolumes": [
              {
                  "size": 100,
                  "volumetype": "SATA"
              }
            ],
            "publicIP": {
                "count": 1,
                "eip": {
                    "iptype": "5_bgp",
                    "bandwidth": {
                        "chargemode": "traffic",
                        "size": 10,
                        "sharetype": "PER"
                    }
                }
            },
            "count": 1
        }
    }'
    ```


## 创建工作负载<a name="section209711527643"></a>

假设已获取前提条件中的信息为如下值（实际操作中您需要根据实际情况替换）：

私有docker镜像地址：**swr.cn-north-4.myhuaweicloud.com/full/2048-demo:v1.2**（此地址为示例，获取方法请参见[客户端上传镜像](https://support.huaweicloud.com/usermanual-swr/swr_01_0011.html)）。

则可以通过如下步骤创建一个工作负载。

1.  调用[创建Deployment](创建Deployment.md)使用镜像创建2048工作负载。

    创建一个Deployment，名称为deployment-test，且添加一个标签name:deployment-test。使用镜像为  **swr.cn-north-4.myhuaweicloud.com/full/2048-demo:v1.2**  （此地址为示例）**。**

    ```
    curl -X POST -H "Content-Type:application/json" -H "X-Cluster-ID:$UUID" -H "X-Auth-Token:$Token" -d '{ 
         "apiVersion": "extensions/v1beta1", 
         "kind": "Deployment", 
         "metadata": { 
             "labels": { 
                 "app": "deployment-test" 
             }, 
             "name": "deployment-test" 
         }, 
         "spec": { 
             "replicas": 1, 
             "selector": { 
                 "matchLabels": { 
                     "app": "deployment-test" 
                 } 
             }, 
             "template": { 
                 "metadata": { 
                     "labels": { 
                         "app": "deployment-test" 
                     } 
                 }, 
                 "spec": { 
                     "containers": [ 
                         { 
                             "image": "swr.cn-north-4.myhuaweicloud.com/full/2048-demo:v1.2", 
                             "imagePullPolicy": "IfNotPresent", 
                             "name": "deployment-test" 
                         } 
                     ], 
                     "imagePullSecrets": [{ 
                         "name": "default-secret" 
                     }] 
                 } 
             } 
         } 
     }' https://{集群id}.{cce_endpoint}/apis/extensions/v1beta1/namespaces/default/deployments -k -v
    ```

2.  调用[获取指定的Deployment](获取指定的Deployment.md)获取某个Namespace下指定的Deployment对象查询Deployment是否创建成功。

    ```
    curl -X GET -H 'Content-Type:application/json;charset=utf-8' -H "X-Cluster-ID:$UUID" -H "X-Auth-Token:$Token" https://{集群id}.{cce_endpoint}/apis/extensions/v1beta1/namespaces/default/deployments/deployment-test -k -v
    ```

    如果返回的响应显示availableReplicas的数量为1，则说明创建成功，即代表工作负载创建成功。

    ```
     "status": { 
             "observedGeneration ": 1, 
             "replicas ": 1, 
             "updatedReplicas ": 1, 
             "availableReplicas": 1
     }
    ```

    您还可以从CCE控制台中查看工作负载是否创建成功，登录CCE控制台，单击左侧“工作负载“，即可看到“deployment-test“工作负载。

3.  Deployment创建成功后，调用[创建Service](创建Service.md)创建Service，我们可以通过Service访问到Deployment里面的Pod。

    Service的名称为service-test，访问类型选择NodePort，访问协议为TCP。

    ```
    curl -X POST -H "Content-Type:application/json" -H "X-Cluster-UUID:$UUID" -H "X-Auth-Token:$Token" -d '{ 
         "kind":"Service", 
         "apiVersion":"v1", 
         "metadata":{ 
            "name":"service-test", 
            "creationTimestamp":null, 
            "labels":{ 
               "app":"deployment-test" 
            } 
         }, 
         "spec":{ 
            "ports":[{ 
               "name":"http", 
             "nodePort":30023,
               "port":80,
             "protocol":"TCP",  
               "targetPort":80 
            }], 
            "selector":{ 
            "app":"deployment-test" 
            }, 
                   "type":"NodePort"
        }
     }' https://{集群id}.{cce_endpoint} /api/v1/namespaces/default/services -k -v
    ```

    若返回状态码201，说明命令执行成功。

4.  调用[获取指定的Service](获取指定的Service.md)查询Service的状态，确定是否创建成功。

    ```
    curl -X GET -H 'Content-Type:application/json;charset=utf-8' -H "X-Cluster-ID:$UUID" -H "X-Auth-Token:$Token" https://{集群id}.{cce_endpoint} /api/v1/namespaces/default/services/service-test -k -v
    ```

    响应如下，表示创建成功：

    ```
    {
     "kind": "Service",
     "apiVersion": "v1",
     "metadata": {
         "name": "service-test",
         "namespace": "default",
         "selfLink": "/api/v1/namespaces/default/services/service-test",
         "uid": "cb932657-214a-11e8-b486-fa163ecd089c",
         "resourceVersion": "340196",
         "creationTimestamp": "2018-03-06T14:29:36Z",
         "labels": {
             "app": "deployment-test"
         },
         "enable": true
     },
     "spec": {
         "ports": [{
             "name": "http",
             "protocol": "TCP",
             "port": 80,
             "targetPort": 80,
             "nodePort": 30023
         }],
         "selector": {
             "app": "deployment-test "
         },
         "clusterIP": "10.247.90.130",
         "type": "NodePort",
         "sessionAffinity": "None",
         "externalTrafficPolicy": "Cluster"
     },
     "status": {
         "loadBalancer": {}
     }
    }
    ```

    您还可以从CCE控制台查看创建的服务，登录CCE控制台，单击左侧“工作负载“，单击**deployment-test**工作负载，进入工作负载详情，在“访问方式“页签中，可查看到访问地址，nodePort为30023。

    若该访问节点绑定了弹性IP，可通过**弹性IP地址:nodePort**从外部访问工作负载。


