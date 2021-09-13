# VPC网络<a name="cce_01_0283"></a>

## VPC网络模型<a name="section1747411510358"></a>

VPC网络采用VPC路由方式与底层网络深度整合，适用于高性能场景，节点数量受限于虚拟私有云VPC的路由配额。每个节点将会被分配固定大小的IP地址段。VPC网络由于没有隧道封装的消耗，容器网络性能相对于容器隧道网络有一定优势。VPC网络集群由于VPC路由中配置有容器网段与节点IP的路由，可以支持集群外直接访问容器实例等特殊场景。

**图 1**  VPC网络<a name="zh-cn_topic_0146398798_fig105374614243"></a>  
![](figures/VPC网络.png "VPC网络")

**说明如下：**

-   节点内Pod间通信：ipvlan子接口分配给节点上的Pod，同节点的Pod间通信直接通过ipvlan直接转发。
-   跨节点Pod间通信：所有跨节点Pod间的通信通过默认路由到默认网关，借助VPC的路由转发能力，转发到对端节点上。

## 容器IP地址管理<a name="section1574982552114"></a>

VPC网络按如下规则分配容器IP：

-   容器网段需单独分配
-   节点维度划分地址段，集群的所有节点从容器网段中分配一个固定大小（用户自己配置）的IP网段
-   容器网段依次循环分配IP网段给新增节点
-   调度到节点上的Pod依次循环从分配给节点的IP网段内分配IP地址

**图 2**  VPC网络IP地址管理<a name="fig790744862219"></a>  
![](figures/VPC网络IP地址管理.png "VPC网络IP地址管理")

按如上IP分配，VPC网络的集群最多能创建节点数量 = 容器网段IP数量 ÷ 节点从容器网段中分配IP网段的IP数量

比如容器网段为172.16.0.0/16，则IP数量为65536，节点分配容器网段掩码为25，也就是每个节点容器IP数量为128，则最多可创建节点数量为65536/128=512。当然，集群能创建多少节点，还受节点网络和集群规模的影响。

**图 3**  容器网段配置<a name="fig320115593351"></a>  
![](figures/容器网段配置.png "容器网段配置")

## 优缺点<a name="section207316301745"></a>

**优点**

-   由于没有隧道封装，网络问题易排查、性能较高
-   支持VPC内的外部网络与容器IP直通

**缺点**

-   节点数量受限于虚拟私有云VPC的路由配额
-   每个节点将会被分配固定大小的IP地址段，存在一定的容器网段IP地址浪费
-   无法直接利用VPC提供的负载均衡、安全组等能力

## 应用场景<a name="section474217381446"></a>

-   性能要求高：由于没有额外的隧道封装，相比于容器隧道网络模式，性能接近于VPC网络的性能，所以适用于对性能要求较高的业务场景，比如：AI计算、大数据计算等。
-   中小规模组网：由于VPC路由网络受限于VPC路由表条目配额的限制，当前默认最大只支持200个节点，如果有更大规模的需求，可提升VPC路由表条目配额。

## VPC网络访问示例<a name="section10441454192410"></a>

创建一个VPC网络的集群。

**图 4**  集群网络<a name="fig1830324293611"></a>  
![](figures/集群网络-17.png "集群网络-17")

集群有一个Node节点。

```
$ kubectl get node
NAME           STATUS   ROLES    AGE   VERSION
192.168.0.99   Ready    <none>   9d    v1.17.17-r0-CCE21.6.1.B004-17.37.5
```

查看VPC的路由表，会看到如下一条路由，目的地址172.16.0.0/25是分配给节点的容器网段，下一跳指向对应的节点，当访问容器IP时，VPC路由就会转发给下一跳的节点。这印证了前面说的VPC网络模型使用VPC的路由。

**图 5**  路由<a name="fig215015117361"></a>  
![](figures/路由.png "路由")

在集群中创建一个Deployment。

```
kind: Deployment
apiVersion: apps/v1
metadata:
  name: example
  namespace: default
spec:
  replicas: 4
  selector:
    matchLabels:
      app: example
  template:
    metadata:
      labels:
        app: example
    spec:
      containers:
        - name: container-0
          image: 'nginx:perl'
      imagePullSecrets:
        - name: default-secret
```

然后查看Pod。

```
$ kubectl get pod -owide
NAME                       READY   STATUS    RESTARTS   AGE   IP           NODE           NOMINATED NODE   READINESS GATES
example-86b9779494-l8qrw   1/1     Running   0          14s   172.16.0.6   192.168.0.99   <none>           <none>
example-86b9779494-svs8t   1/1     Running   0          14s   172.16.0.7   192.168.0.99   <none>           <none>
example-86b9779494-x8kl5   1/1     Running   0          14s   172.16.0.5   192.168.0.99   <none>           <none>
example-86b9779494-zt627   1/1     Running   0          14s   172.16.0.8   192.168.0.99   <none>           <none>
```

此时如果在集群同VPC下集群外部直接访问Pod的IP，会发现可以访问，这就是VPC网络的特性，支持外部网络与容器IP直通。

而在集群内部节点或Pod内，都能正常访问Pod，如下进入到容器中直接访问Pod能够正常访问。

```
$ kubectl exec -it example-86b9779494-l8qrw -- curl 172.16.0.7
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```

