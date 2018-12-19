# 集群中使用ELB的操作方法<a name="cce_02_0087"></a>

本章节介绍在CCE创建的集群中使用ELB时的操作方法。

## 操作方法<a name="section50156865193415"></a>

创建对应的service。开源接口的使用方法请参见[创建Service](创建Service.md)。

```
{
    "apiVersion": "v1",
    "kind": "Service",
    "metadata": {
        "annotations":[
             {
		  "kubernetes.io/elb.class": "elasticity"
		  "kubernetes.io/elb.vpc.id": "a95ef7c1-34b4-48c4-9c4f-ae9ea6cc442b"
		  "kubernetes.io/elb.subnet-id": "bf04639b-9e67-4f02-ac63-379e9ce48ea2"
	     }
       ],
	"name": "test-service"
    },
    "spec": {
        "loadBalancerIP": "172.16.78.223",
        "ports": [
            {
                "name": "elbtest",
                "port": 80,
                "protocol": "TCP",
                "targetPort": 80
            }
        ],
        "selector": {
            "name": "elbtest"
        },
        "type": "LoadBalancer"
    }
}
```

其中：

-   **kubernetes.io/elb.class**：对接负载均衡时需要增加该参数。若对接经典型负载均衡器，值配置为elasticity；若对接增强型负载均衡，值配置为union。
-   **kubernetes.io/elb.vpc.id**：当对接的为经典型负载均衡且网络类型为私网时，需填写此参数，指定负载均衡实例所在的vpc id。
-   **kubernetes.io/elb.subnet-id**：当对接的为增强型负载均衡时，需填写此参数，指定负载均衡实例所在的子网id。
-   **loadBalancerIP**：用户在弹性云服务器中创建ELB时分配的IP地址。

    >![](public_sys-resources/icon-notice.gif) **注意：**   
    >请确认选择的ELB是否还有Listener配额，如果配额不足请重新创建ELB实例,并将“loadBalancerIP“赋值为新创建ELB时分配的IP地址。  

-   **protocol**：必须为“TCP“。
-   **targetPort**：不能与监听端口一致。
-   **type**：必须为“LoadBalancer“。

