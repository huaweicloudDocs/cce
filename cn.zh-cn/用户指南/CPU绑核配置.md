# CPU绑核配置<a name="cce_10_0351"></a>

默认情况下，kubelet 使用  [CFS 配额](https://www.kernel.org/doc/html/latest/scheduler/sched-design-CFS.html)  来执行 Pod 的 CPU 约束。 当节点上运行了很多 CPU 密集的 Pod 时，工作负载可能会迁移到不同的 CPU 核， 这取决于调度时 Pod 是否被扼制，以及哪些 CPU 核是可用的。许多应用对这种迁移不敏感，因此无需任何干预即可正常工作。有些应用对CPU敏感，CPU敏感型应用有如下特点。

-   对CPU throttling 敏感
-   对上下文切换敏感
-   对处理器缓存未命中敏感
-   对跨socket内存访问敏感
-   期望运行在同一物理CPU的超线程

如果您的应用有以上其中一个特点，可以利用kubernetes中提供的绑核策略去给应用绑核，提升应用性能，减少应用的调度延迟。cpu manager会优先在一个Socket上分配资源，也会优先分配完整的物理核，避免一些干扰。

## 如何为Pod绑核<a name="section1211174714517"></a>

想要让Pod能够绑核，有如下几点要求：

-   节点上开启静态绑核策略。具体方法请参见[开启CPU管理策略](#section173918176434)。
-   Pod的定义里都要设置request和limits，request和limits要一致。
-   对于要绑核的容器，request值必须是整数。
-   如果有init container希望进行绑核的话，init container的request最好与业务容器设置的request一致（避免业务容器未继承init container的cpu分配结果，导致cpu manager多预留一部分cpu）。更多信息请参见[App Containers can't inherit Init Containers CPUs - CPU Manager Static Policy](https://github.com/kubernetes/kubernetes/issues/94220#issuecomment-868489201)。

在使用时您可以利用[调度策略（亲和与反亲和）](调度策略（亲和与反亲和）.md)将如上配置的Pod调度到开启静态绑核策略的节点上，这样就能够达到绑核的效果。

## 开启CPU管理策略<a name="section173918176434"></a>

[CPU 管理策略](https://kubernetes.io/zh/docs/tasks/administer-cluster/cpu-management-policies/)通过 kubelet 参数 --cpu-manager-policy 来指定。支持两种策略：

-   关闭（none）：默认策略，显式地启用现有的默认 CPU 亲和方案，不提供操作系统调度器默认行为之外的亲和性策略。
-   开启（static）：针对具有整数型 CPU requests 的 Guaranteed Pod ，它允许该类 Pod 中的容器访问节点上的独占 CPU 资源（绑核）。

在创建集群时的高级配置中可以配置CPU管理策略，如下图所示。

![](figures/zh-cn_image_0000001244261055.png)

另外在节点池中也可以配置CPU管理策略，配置后会自动修改节点的上kubelet 参数 --cpu-manager-policy。登录CCE控制台，进入集群，在左侧选择“节点管理“，在右侧选择“节点池“页签，单击节点池名称后的“更多 \> 配置管理“，将cpu-manager-policy的值修改为static即可。

## Pod资源配置<a name="section193243402534"></a>

Pod的resources中cpu的request值需为整数，且request和limits要一致。

```
kind: Deployment
apiVersion: apps/v1
metadata:
  name: test
spec:
  replicas: 1
  selector:
    matchLabels:
      app: test
  template:
    metadata:
      labels:
        app: test
    spec:
      containers:
        - name: container-1
          image: nginx:alpine
          resources:
            requests:
              cpu: 2           # 必须为整数，且需要与limits中一致
              memory: 2048Mi
            limits:
              cpu: 2           # 必须为整数，且需要与requests中一致
              memory: 2048Mi
      imagePullSecrets:
        - name: default-secret
```

