# GPU调度<a name="cce_01_0345"></a>

CCE支持在容器中使用GPU资源。

## 前提条件<a name="section18703125715210"></a>

-   购买GPU类型节点，具体请参见[购买节点](购买节点.md)。
-   安装gpu-beta插件，安装时注意要选择节点上GPU对应的驱动，具体请参见[gpu-beta](gpu-beta.md)。

## 使用GPU<a name="section17426191045420"></a>

创建工作负载申请GPU资源，可按如下方法配置，指定显卡的数量。

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: gpu-test
  namespace: default
spec:
  replicas: 1
  selector:
    matchLabels:
      app: gpu-test
  template:
    metadata:
      labels:
        app: gpu-test
    spec:
      containers:
      - image: nginx:perl
        name: container-0
        resources:
          requests:
            cpu: 250m
            memory: 512Mi
            nvidia.com/gpu: 1   # 申请GPU的数量
          limits:
            cpu: 250m
            memory: 512Mi
            nvidia.com/gpu: 1   # GPU数量的使用上限
      imagePullSecrets:
      - name: default-secret
```

通过  **nvidia.com/gpu**  指定申请GPU的数量，支持申请设置为小于1的数量，比如** nvidia.com/gpu: 0.5**，这样可以多个Pod共享使用GPU。

指定**nvidia.com/gpu**后，在调度时不会将负载调度到没有GPU的节点。如果缺乏GPU资源，会报类似“0/2 nodes are available: 2 Insufficient nvidia.com/gpu.”的Kubernetes事件。

在CCE控制台使用GPU资源，只需在创建负载时，勾选GPU配额，并指定使用的比例即可，如下图所示。

**图 1**  使用GPU<a name="fig348242715203"></a>  
![](figures/使用GPU.png "使用GPU")

## GPU节点标签<a name="section1869217223111"></a>

购买GPU节点后，CCE会给节点打上对应标签，如下所示，不同类型的GPU节点有不同标签。

**图 2**  GPU节点标签<a name="fig1847151615318"></a>  
![](figures/GPU节点标签.png "GPU节点标签")

在使用GPU时，可以根据标签让Pod与节点亲和，从而让Pod选择正确的节点，如下所示。

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: gpu-test
  namespace: default
spec:
  replicas: 1
  selector:
    matchLabels:
      app: gpu-test
  template:
    metadata:
      labels:
        app: gpu-test
    spec:
      nodeSelector:
        accelerator: navidia-t4
      containers:
      - image: nginx:perl
        name: container-0
        resources:
          requests:
            cpu: 250m
            memory: 512Mi
            nvidia.com/gpu: 1   # 申请GPU的数量
          limits:
            cpu: 250m
            memory: 512Mi
            nvidia.com/gpu: 1   # GPU数量的使用上限
      imagePullSecrets:
      - name: default-secret
```

