# Kubectl常用命令<a name="cce_01_0139"></a>

## 基础命令<a name="section18967103615461"></a>

**get**

get命令用于获取集群的一个或一些resource信息。

该命令可以列出集群所有资源的详细信息，resource包括集群节点、运行的pod、Replication Controller、service等。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>集群中可以创建多个namespace，未指定namespace的情况下，所有操作都是针对--namespace=default。

例如：

获取所有pod的详细信息：

```
kubectl get po -o wide
```

获取所有namespace下的运行的所有pod：

```
kubectl get po --all-namespaces
```

获取所有namespace下的运行的所有pod的标签：

```
kubectl get po --show-labels
```

获取该节点的所有命名空间：

```
kubectl get namespace
```

>![](public_sys-resources/icon-note.gif) **说明：** 
>查询其他节点需要加-s指定节点，类似可以使用“kubectl get rc”，“kubectl get svc”，“kubectl get nodes”，“kubectl get deploy”等获取其他resource信息。

以yaml格式输出pod的详细信息：

```
kubectl get po <podname> -o yaml
```

以json格式输出pod的详细信息：

```
kubectl get po <podname> -o json
```

```
kubectl get po rc-nginx-2-btv4j -o=custom-columns=LABELS:.metadata.labels.app
```

>![](public_sys-resources/icon-note.gif) **说明：** 
>其中LABELS为显示的列标题，可以自己设置，“.metadata.labels.app”为查询的数据需要按照之前的yaml或json获取。

**create**

kubectl命令用于根据文件或输入创建集群resource。

如果已经定义了相应resource的yaml或json文件，直接kubectl create -f filename即可创建文件内定义的resource。

```
kubectl create -f filename
```

**expose**

expose将一个资源包括pod、Replication Controller、service、deployment等公开为一个新的service。

```
kubectl expose deployment deployname --port=81 --type=NodePort --target-port=80 --name=service-name
```

>![](public_sys-resources/icon-note.gif) **说明：** 
>给deployname发布一个服务，-port为暴露出去的端口，-type为服务类型，-target-port为容器端口，port通过clusterip加端口访问，target-port通过节点ip加端口访问。

**run**

例如：

在集群中运行一个特定的镜像。

```
kubectl run deployname --image=nginx:latest
```

在创建时指定运行的命令：

```
kubectl run deployname -image=busybox --command -- ping baidu.com
```

**set**

在对象上设置特定功能。

例如：

将一个deployname的image改为镜像为1.0的image：

```
kubectl set image deploy deployname containername=containername:1.0
```

**edit**

edit提供了另一种更新resource源的操作。

例如：

使用edit直接更新pod的命令为：

```
kubectl edit po po-nginx-btv4j
```

上面命令的效果等效于：

```
kubectl get po po-nginx-btv4j -o yaml >> /tmp/nginx-tmp.yaml
vim /tmp/nginx-tmp.yaml
/*do some changes here */
kubectl replace -f /tmp/nginx-tmp.yaml
```

**explain**

查看文档或参考资料。

例如：

查看pods/service的相关文档：

```
kubectl explain pods,svc
```

**delete**

根据resource名或label删除resource。

例如：

立刻删除该pod：

```
kubectl delete po podname --now 
```

```
kubectl delete -f nginx.yaml
kubectl delete deployment deployname
```

## 部署命令<a name="section122665712261"></a>

**rolling-update\***

rolling-update是一个非常重要的命令，对于已经部署并且正在运行的业务，rolling-update提供了不中断业务的更新方式。rolling-update每次起一个新的pod，等新pod完全起来后删除一个旧的pod，然后再起一个新的pod替换旧的pod，直到替换掉所有的pod。rolling-update需要确保新的版本有不同的name，Version和label，否则会报错 。

```
kubectl rolling-update poname -f newfilename
kubectl rolling-update poname -image=image:v2
```

如果在升级过程中，发现有问题可以中途停止update，并回滚到前面版本。

```
kubectl rolling-update poname -rollback
```

**rollout**

管理资源的发布。

例如：

查看指定资源的部署状态：

```
kubectl rollout status deployment/deployname
```

查看指定资源的发布历史：

```
kubectl rollout history deployment/deployname
```

回滚指定资源，默认回滚至上一个版本：

```
kubectl rollout undo deployment/test-nginx
```

**scale**

scale用于程序在负载加重或缩小时将副本进行扩容或缩小。

```
kubectl scale deployment deployname --replicas=newnumber
```

**autoscale**

autoscale命令提供了自动根据pod负载对其副本进行扩缩的功能。autoscale命令会给一个rc指定一个副本数的范围，在实际运行中根据pod中运行的程序的负载自动在指定的范围内对pod进行扩容或缩容。

```
kubectl autoscale deployment deployname --min=minnumber --max=maxnumber
```

## 集群管理命令<a name="section286451412289"></a>

**cordon、drain、uncordon\***

有时候会遇到这样一个场景，一个node需要升级，但是在该node上又有许多运行的pod，或者该node已经瘫痪，需要保证功能的完善，则需要使用这组命令，使用步骤如下：

1.  使用cordon命令将一个node标记为不可调度。这意味着新的pod将不会被调度到该node上。

    ```
    kubectl cordon nodename
    ```

    备注：nodename为节点IP。

2.  使用drain命令，将运行在该node上运行的pod平滑的搬迁到其他节点上。

    ```
    kubectl drain nodename --ignore-daemonsets --ignore-emptydir
    ```

    备注：ignore-emptydir为用户挂载空目录的数据。

3.  对该节点进行一些节点维护的操作，如升级内核、升级Docker等。
4.  节点维护完后，使用uncordon命令解锁该node，使其重新变得可调度。

    ```
    kubectl uncordon nodename
    ```


**cluster-info**

查看在集群中运行的插件：

```
kubectl cluster-info
```

查看详细信息：

```
kubectl cluster-info dump
```

**top\***

显示资源（CPU/Memory/Storage）使用。需要Heapster运行。

**taint\***

修改一个或多个节点上的taint。

**certificate\***

修改证书资源。

## 故障诊断和调试命令<a name="section2283324202914"></a>

**describe**

describe类似于get，同样用于获取resource的相关信息。不同的是，get获得的是更详细的resource个性的详细信息，describe获得的是resource集群相关的信息。describe命令同get类似，但是describe不支持-o选项，对于同一类型resource，describe输出的信息格式，内容域相同。

>![](public_sys-resources/icon-note.gif) **说明：** 
>如果发现是查询某个resource的信息，使用get命令能够获取更加详尽的信息。但是如果想要查询某个resource的状态，如某个pod并不是在running状态，这时需要获取更详尽的状态信息时，就应该使用describe命令。
>```
>kubectl describe po <podname>
>```

**logs**

logs命令用于显示pod运行中，容器内程序输出到标准输出的内容。如果要获得tail -f的方式，需使用-f选项。

```
kubectl logs -f podname
```

**exec**

与docker的exec用法相似，如果一个pod中，有多个容器，需要使用-c选项指定容器。

```
kubectl exec -it podname bash
kubectl exec -it podname -c containername bash
```

**port-forward\***

转发一个或多个本地端口至一个pod。

例如：

转发pod中的6000端口到本地的5000端口：

```
kubectl port -forward podname 5000:6000
```

**proxy\***

运行一个proxy到kubernetes api server。

例如：

控制节点开启HTTP Rest接口：

```
kubectl proxy -accept-hosts=’.*’ -port=8001 -address=’0.0.0.0’
```

**cp**

拷贝文件或目录到容器：

```
cp filename newfilename
```

**auth\***

检查授权。

**attach\***

attach命令效果类似于logs -f，退出查看使用ctrl-c。如果一个pod中有多个容器，要查看具体的某个容器的输出，需要在pod名后使用-c containername指定运行的容器。

```
kubectl attach podname -c containername
```

## 高级命令<a name="section1870143812302"></a>

**replace**

replace命令用于对已有资源进行更新、替换。当我们需要更新resource的一些属性的时候，如果修改副本数量，增加、修改label，更改image版本，修改端口等。都可以直接修改原yaml文件，然后执行replace命令。

```
kubectl replace -f filename
```

>![](public_sys-resources/icon-notice.gif) **须知：** 
>名字不能被更新。另外，如果是更新label，原有标签的pod将会与更新label后的rc断开联系，有新label的rc将会创建指定副本数的新的pod，但是默认并不会删除原来的pod。所以此时如果使用get po将会发现pod数翻倍，进一步check会发现原来的pod已经不会被新rc控制。

**apply\***

apply命令提供了比patch，edit等更严格的更新resource的方式。通过apply，用户可以将resource的configuration使用source control的方式维护在版本库中。每次有更新时，将配置文件push到server，然后使用kubectl apply将更新应用到resource。kubernetes会在引用更新前将当前配置文件中的配置同已经应用的配置做比较，并只更新更改的部分，而不会主动更改任何用户未指定的部分。apply命令的使用方式同replace相同，不同的是，apply不会删除原有resource，然后创建新的。apply直接在原有resource的基础上进行更新。同时kubectl apply还会在resource中添加一条注释，标记当前的apply，类似于git操作。

```
kubectl apply -f
```

**patch**

如果一个容器已经在运行，这时需要对一些容器属性进行修改，又不想删除容器，或不方便通过replace的方式进行更新。kubernetes还提供了一种在容器运行时，直接对容器进行修改的方式，就是patch命令。 例如已存在一个pod的label为app=nginx1，如果需要在运行过程中，将其修改为app=nginx2。

```
kubectl patch pod podname -p '{"metadata":{"lables":{"app":"nginx1"}}}'
```

**convent\***

不同的api版本之间转换配置文件。

## 设置命令<a name="section20145838123111"></a>

**label**

更新资源上的标签：

```
kubectl label pods my-pod new-label=newlabel
```

**annotate**

更新资源上的注释：

```
kubectl annotate pods my-pod icon-url=http://……
```

**completion**

用于实现kubectl工具自动补全。

## 其他命令<a name="section44619483210"></a>

**api-versions**

打印受支持的api版本：

```
kubectl api-versions
```

**api-resources**

打印支持的api资源：

```
kubectl api-resources
```

**config\***

修改kubeconfig文件：用于访问api，比如配置认证信息。

**help**

所有命令帮助。

**version**

打印客户端和服务版本信息。

```
kubectl version
```

