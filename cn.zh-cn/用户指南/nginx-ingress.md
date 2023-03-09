# nginx-ingress<a name="cce_10_0034"></a>

## 插件简介<a name="section26181722164712"></a>

Kubernetes通过kube-proxy服务实现了Service的对外发布及负载均衡，它的各种方式都是基于传输层实现的。在实际的互联网应用场景中，不仅要实现单纯的转发，还有更加细致的策略需求，如果使用真正的负载均衡器更会增加操作的灵活性和转发性能。

基于以上需求，Kubernetes引入了资源对象Ingress，Ingress为Service提供了可直接被集群外部访问的虚拟主机、负载均衡、SSL代理、HTTP路由等应用层转发功能。

Kubernetes官方发布了基于Nginx的Ingress控制器，nginx-ingress是一款使用configmap来存储nginx配置的插件，nginx ingress controller会将ingress生成一段nginx的配置，将这个配置通过Kubernetes API写到Nginx的Pod中，然后reload完成nginx的配置修改和更新。

nginx-ingress插件直接使用社区模板与镜像，CCE不提供额外维护，不建议用于商用场景。

开源社区地址：[https://github.com/kubernetes/ingress-nginx](https://github.com/kubernetes/ingress-nginx)

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   安装该插件时，您可以通过“定义nginx配置“添加配置，此处的设置将会全局生效，该参数直接通过配置nginx.conf生成，将影响管理的全部Ingress，相关参数可通过[configmap](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/)查找，如果您配置的参数不包含在[configmap](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/)所列出的选项中将不会生效。
>-   安装该插件后，您在CCE控制台[创建Ingress](通过控制台使用ELB-Ingress.md#section19352112471617)时可以开启“对接Nginx“按钮，并通过“Nginx配置“下的“自定义配置“将Kubernetes annotations添加到特定的Ingress对象，以自定义其行为，Kubernetes annotations字段详情请参见[Annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/)。
>-   请勿手动修改和删除CCE自动创建的ELB和监听器，否则将出现工作负载异常；若您已经误修改或删除，请卸载Nginx Ingress插件后重装。

## 工作原理<a name="section971014351338"></a>

Nginx Ingress由资源对象Ingress、Ingress控制器、Nginx三部分组成，Ingress控制器用以将Ingress资源实例组装成Nginx配置文件（nginx.conf），并重新加载 Nginx使变更的配置生效。当它监听到Service中Pod变化时通过动态变更的方式实现Nginx上游服务器组配置的变更，无须重新加载Nginx进程。工作原理如[图1](#fig204075132570)所示。

-   Ingress：一组基于域名或URL把请求转发到指定Service实例的访问规则，是Kubernetes的一种资源对象，Ingress实例被存储在对象存储服务etcd中，通过接口服务被实现增、删、改、查的操作。
-   Ingress控制器（Ingress controller）：用以实时监控资源对象Ingress、Service、End-point、Secret（主要是TLS证书和Key）、Node、ConfigMap的变化，自动对Nginx进行相应的操作。
-   Nginx：实现具体的应用层负载均衡及访问控制。

**图 1**  Nginx Ingress工作原理<a name="fig204075132570"></a>  
![](figures/Nginx-Ingress工作原理.png "Nginx-Ingress工作原理")

## 使用约束<a name="section3200193614201"></a>

-   仅支持在1.15及以上版本的CCE集群中安装此插件。
-   通过api调接口创建的Ingress annotation必须添加kubernetes.io/ingress.class: "nginx"。
-   独享型ELB规格必须支持网络型（TCP/UDP），且网络类型必须支持私网（有私有IP地址）。
-   运行nginx-ingress-controller的节点以及该节点上运行的容器，无法访问Nginx Ingress，请将工作负载Pod与nginx-ingress-controller进行反亲和部署，具体操作步骤请参见[工作负载与nginx-ingress-controller反亲和部署](#section15456140194414)。

## 前提条件<a name="zh-cn_topic_0226102211_section92541494210"></a>

在创建容器工作负载前，您需要存在一个可用集群。若没有可用集群 ，请参照[购买CCE集群](购买CCE集群.md)中的步骤创建。

## 安装插件<a name="section1152424015224"></a>

新UI支持使用独享型负载均衡实例。

1.  登录CCE控制台。
2.  在左侧选择“插件市场“，找到“nginx-ingress“插件，单击“安装“。
3.  填写配置参数。
    -   **选择集群**：选择要安装的集群
    -   **规格配置**：请根据业务需求选择插件规格，可自定义资源规格部署。
        -   实例数：选择自定义规格时，请根据业务需求选择合适的实例数。
        -   容器：选择自定义规格时，请根据业务需求选择合适的容器配额。

    -   **负载均衡器**：支持对接共享型或独享型负载均衡实例，如果可用实例，请先创建。负载均衡器需要拥有至少两个监听器配额，且端口 80 和 443 没有被监听器占用。
    -   **nginx配置参数**：配置nginx.conf文件，将影响管理的全部Ingress，相关参数可通过[configmap](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/)查找，如果您配置的参数不包含在[configmap](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/)所列出的选项中将不会生效。
    -   **默认404服务**：默认使用插件自带的404服务。支持自定义404服务，填写“命名空间/服务名称“，如果服务不存在，插件会安装失败。

4.  单击“安装“。

## 工作负载与nginx-ingress-controller反亲和部署<a name="section15456140194414"></a>

运行nginx-ingress-controller的节点以及该节点上运行的容器，无法访问Nginx Ingress，为避免这个问题发生，需要将工作负载与nginx-ingress-controller反亲和部署，即工作负载Pod无法调度至nginx-ingress-controller运行的节点。

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx
  strategy:
    type: RollingUpdate
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - image: nginx:aplpine
        imagePullPolicy: IfNotPresent
        name: nginx
      imagePullSecrets:
      - name: default-secret
      affinity:
        podAntiAffinity:
          requiredDuringSchedulingIgnoredDuringExecution:
            - labelSelector:
                matchExpressions:    #通过nginx-ingress-controller的标签实现反亲和
                  - key: app
                    operator: In
                    values:
                      - nginx-ingress
                  - key: component
                    operator: In
                    values:
                      - controller
              namespaces:
                - kube-system
              topologyKey: kubernetes.io/hostname
```

## 相关操作<a name="section59831252163212"></a>

[部署多个Nginx Ingress Controller](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_0342.html)

## 版本记录<a name="section183121449435"></a>

**表 1**  CCE插件版本记录

<a name="table545952314179"></a>
<table><thead align="left"><tr id="row13459112313176"><th class="cellrowborder" valign="top" width="27.47106810851831%" id="mcps1.2.4.1.1"><p id="p206369328181"><a name="p206369328181"></a><a name="p206369328181"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="34.58546765319673%" id="mcps1.2.4.1.2"><p id="p1663653221810"><a name="p1663653221810"></a><a name="p1663653221810"></a>支持的集群版本</p>
</th>
<th class="cellrowborder" valign="top" width="37.94346423828496%" id="mcps1.2.4.1.3"><p id="p445992311174"><a name="p445992311174"></a><a name="p445992311174"></a>社区版本（仅1.17及以上版本集群支持）</p>
</th>
</tr>
</thead>
<tbody><tr id="row7864202635"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p10808571233"><a name="p10808571233"></a><a name="p10808571233"></a>2.2.1</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p1180818717319"><a name="p1180818717319"></a><a name="p1180818717319"></a>/v1.25.*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p158641121531"><a name="p158641121531"></a><a name="p158641121531"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v1.5.1" target="_blank" rel="noopener noreferrer">1.5.1</a></p>
</td>
</tr>
<tr id="row751774215218"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p191444481020"><a name="p191444481020"></a><a name="p191444481020"></a>2.1.3</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p1144144817212"><a name="p1144144817212"></a><a name="p1144144817212"></a>/v1.(19|21|23).*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p20500159823"><a name="p20500159823"></a><a name="p20500159823"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v1.2.1" target="_blank" rel="noopener noreferrer">1.2.1</a></p>
</td>
</tr>
<tr id="row174592023121714"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p6939533161911"><a name="p6939533161911"></a><a name="p6939533161911"></a>2.1.1</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p1014425619521"><a name="p1014425619521"></a><a name="p1014425619521"></a>/v1.(19|21|23).*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p81496260158"><a name="p81496260158"></a><a name="p81496260158"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v1.2.1" target="_blank" rel="noopener noreferrer">1.2.1</a></p>
</td>
</tr>
<tr id="row10459723151716"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p863693217186"><a name="p863693217186"></a><a name="p863693217186"></a>2.1.0</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p114955612526"><a name="p114955612526"></a><a name="p114955612526"></a>/v1.(19|21|23).*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p121491263156"><a name="p121491263156"></a><a name="p121491263156"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v1.2.0" target="_blank" rel="noopener noreferrer">1.2.0</a></p>
</td>
</tr>
<tr id="row3459112341718"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p76362032111815"><a name="p76362032111815"></a><a name="p76362032111815"></a>2.0.1</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p71526563528"><a name="p71526563528"></a><a name="p71526563528"></a>/v1.(19|21|23).*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p414952619159"><a name="p414952619159"></a><a name="p414952619159"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v1.1.1" target="_blank" rel="noopener noreferrer">1.1.1</a></p>
</td>
</tr>
<tr id="row114591523181710"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p1363713211811"><a name="p1363713211811"></a><a name="p1363713211811"></a>1.3.2</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p478101916273"><a name="p478101916273"></a><a name="p478101916273"></a>/v1.(15|17|19|21).*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p188761932161717"><a name="p188761932161717"></a><a name="p188761932161717"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v0.49.3" target="_blank" rel="noopener noreferrer">0.49.3</a></p>
</td>
</tr>
<tr id="row646042319177"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p1063719324182"><a name="p1063719324182"></a><a name="p1063719324182"></a>1.2.6</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p166191242195218"><a name="p166191242195218"></a><a name="p166191242195218"></a>/v1.(15|17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p587411321171"><a name="p587411321171"></a><a name="p587411321171"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v0.46.0" target="_blank" rel="noopener noreferrer">0.46.0</a></p>
</td>
</tr>
<tr id="row13757134401715"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p663714320184"><a name="p663714320184"></a><a name="p663714320184"></a>1.2.5</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p18624194220524"><a name="p18624194220524"></a><a name="p18624194220524"></a>/v1.(15|17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p154122020161718"><a name="p154122020161718"></a><a name="p154122020161718"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v0.46.0" target="_blank" rel="noopener noreferrer">0.46.0</a></p>
</td>
</tr>
<tr id="row10575174891715"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p66377329182"><a name="p66377329182"></a><a name="p66377329182"></a>1.2.3</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p697194462710"><a name="p697194462710"></a><a name="p697194462710"></a>/v1.(15|17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p940918209172"><a name="p940918209172"></a><a name="p940918209172"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v0.43.0" target="_blank" rel="noopener noreferrer">0.43.0</a></p>
</td>
</tr>
<tr id="row1559018514172"><td class="cellrowborder" valign="top" width="27.47106810851831%" headers="mcps1.2.4.1.1 "><p id="p46371332101818"><a name="p46371332101818"></a><a name="p46371332101818"></a>1.2.2</p>
</td>
<td class="cellrowborder" valign="top" width="34.58546765319673%" headers="mcps1.2.4.1.2 "><p id="p1458429165215"><a name="p1458429165215"></a><a name="p1458429165215"></a>/v1.(15|17).*/</p>
</td>
<td class="cellrowborder" valign="top" width="37.94346423828496%" headers="mcps1.2.4.1.3 "><p id="p541184719168"><a name="p541184719168"></a><a name="p541184719168"></a><a href="https://github.com/kubernetes/ingress-nginx/releases/tag/controller-v0.43.0" target="_blank" rel="noopener noreferrer">0.43.0</a></p>
</td>
</tr>
</tbody>
</table>

