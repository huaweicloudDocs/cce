# prometheus<a name="cce_10_0221"></a>

## 插件简介<a name="section173631312185614"></a>

Prometheus是一套开源的系统监控报警框架。它启发于Google的borgmon监控系统，由工作在SoundCloud的Google前员工在2012年创建，作为社区开源项目进行开发，并于2015年正式发布。2016年，Prometheus正式加入Cloud Native Computing Foundation，成为受欢迎度仅次于Kubernetes的项目。

在云容器引擎CCE中，支持以插件的方式快捷安装Prometheus。

插件官网：[https://prometheus.io/](https://prometheus.io/)

开源社区地址：[https://github.com/prometheus/prometheus](https://github.com/prometheus/prometheus)

## 约束与限制<a name="section127964318113"></a>

CCE提供的Prometheus插件仅支持1.21及以下版本的集群。1.23及以上集群请使用[kube-prometheus-stack](kube-prometheus-stack.md)插件替代。

## 插件特点<a name="section4740192825614"></a>

作为新一代的监控框架，Prometheus具有以下特点：

-   强大的多维度数据模型：
    1.  时间序列数据通过metric名和键值对来区分。
    2.  所有的metrics都可以设置任意的多维标签。
    3.  数据模型更随意，不需要刻意设置为以点分隔的字符串。
    4.  可以对数据模型进行聚合，切割和切片操作。
    5.  支持双精度浮点类型，标签可以设为全unicode。


-   灵活而强大的查询语句（PromQL）：在同一个查询语句，可以对多个metrics进行乘法、加法、连接、取分数位等操作。
-   易于管理：Prometheus server是一个单独的二进制文件，可直接在本地工作，不依赖于分布式存储。
-   高效：平均每个采样点仅占 3.5 bytes，且一个Prometheus server可以处理数百万的metrics。
-   使用pull模式采集时间序列数据，这样不仅有利于本机测试而且可以避免有问题的服务器推送坏的metrics。
-   可以采用push gateway的方式把时间序列数据推送至Prometheus server端。
-   可以通过服务发现或者静态配置去获取监控的targets。
-   有多种可视化图形界面。
-   易于伸缩。

需要指出的是，由于数据采集可能会有丢失，所以Prometheus不适用对采集数据要100%准确的情形。但如果用于记录时间序列数据，Prometheus具有很大的查询优势，此外，Prometheus适用于微服务的体系架构。

## 安装插件<a name="section189463341114"></a>

1.  登录CCE控制台，单击集群名称进入集群，单击左侧导航栏的“插件管理“，在右侧找到**Prometheus**，单击“安装“。
2.  在“规格配置“步骤中，配置以下参数：

    **表 1**  Prometheus配置参数说明

    <a name="table16321825732"></a>
    <table><thead align="left"><tr id="row173212251235"><th class="cellrowborder" valign="top" width="28.000000000000004%" id="mcps1.2.3.1.1"><p id="p43211725338"><a name="p43211725338"></a><a name="p43211725338"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="72%" id="mcps1.2.3.1.2"><p id="p0322102516320"><a name="p0322102516320"></a><a name="p0322102516320"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row163229255313"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p1232219251339"><a name="p1232219251339"></a><a name="p1232219251339"></a>插件规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p173227259312"><a name="p173227259312"></a><a name="p173227259312"></a>根据业务需求，选择插件的规格，包含如下选项：</p>
    <a name="ul53876450305"></a><a name="ul53876450305"></a><ul id="ul53876450305"><li>演示规格（100容器以内）：适用于体验和功能演示环境，该规模下prometheus占用资源较少，但处理能力有限。建议在集群内容器数目不超过100时使用。</li><li>小规格（2000容器以内）：建议在集群中的容器数目不超过2000时使用。</li><li>中规格（5000容器以内）：建议在集群中的容器数目不超过5000时使用。</li><li>大规格（超过5000容器）：建议集群中容器数目超过5000时使用此规格。</li></ul>
    </td>
    </tr>
    <tr id="row6334727910"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p233592498"><a name="p233592498"></a><a name="p233592498"></a>实例数</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p93701640145120"><a name="p93701640145120"></a><a name="p93701640145120"></a>选择上方插件规格后，显示插件中的实例数，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row111551253912"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p51551451293"><a name="p51551451293"></a><a name="p51551451293"></a>容器</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p1437014065110"><a name="p1437014065110"></a><a name="p1437014065110"></a>选择插件规格后，显示插件容器的CPU和内存配额，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row1535723154615"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p83591731124620"><a name="p83591731124620"></a><a name="p83591731124620"></a>数据保留期</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p1736012314462"><a name="p1736012314462"></a><a name="p1736012314462"></a>自定义监控数据需要保留的天数，默认为15天。</p>
    </td>
    </tr>
    <tr id="row133224252315"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p23228259314"><a name="p23228259314"></a><a name="p23228259314"></a>存储</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p13325193219477"><a name="p13325193219477"></a><a name="p13325193219477"></a>支持云硬盘作为存储，按照界面提示配置如下参数：</p>
    <a name="ul14470191614487"></a><a name="ul14470191614487"></a><ul id="ul14470191614487"><li>可用区：请根据业务需要进行选择。可用区是在同一区域下，电力、网络隔离的物理区域，可用区之间内网互通，不同可用区之间物理隔离。</li><li>子类型：支持普通IO、高IO和超高IO三种类型。</li><li>容量：请根据业务需要输入存储容量，默认10G。</li></ul>
    <div class="note" id="note132861729114815"><a name="note132861729114815"></a><a name="note132861729114815"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1328618298481"><a name="p1328618298481"></a><a name="p1328618298481"></a>若命名空间monitoring下已存在pvc，将使用此存储作为存储源。</p>
    </div></div>
    </td>
    </tr>
    </tbody>
    </table>

3.  单击“安装“。安装完成后，插件会在集群中部署以下实例。
    -   prometheus-operator：根据自定义资源（Custom Resource Definition / CRDs）来部署和管理Prometheus Server，同时监控这些自定义资源事件的变化来做相应的处理，是整个系统的控制中心。
    -   prometheus（Server）：Operator根据自定义资源Prometheus类型中定义的内容而部署的Prometheus Server集群，这些自定义资源可以看作是用来管理Prometheus Server集群的 StatefulSets 资源。
    -   prometheus-kube-state-metrics：将Prometheus的metrics数据格式转换成K8s API接口能识别的格式。
    -   custom-metrics-apiserver：将自定义指标聚合到原生的kubernetes apiserver。
    -   prometheus-node-exporter：每个节点上均有部署，收集Node级别的监控数据。
    -   grafana：可视化浏览普罗监控数据。


## 提供资源指标<a name="section13409107262"></a>

容器和节点的资源指标，如CPU、内存使用量，可通过Kubernetes的Metrics API获得。这些指标可以直接被用户访问，比如用kubectl top命令，也可以被HPA或者CustomedHPA使用，根据资源使用率使负载弹性伸缩。

插件可为Kubernetes提供Metrics API，但默认未开启，若要将其开启，需要创建以下APIService对象：

```
apiVersion: apiregistration.k8s.io/v1
kind: APIService
metadata:
  labels:
    app: custom-metrics-apiserver
    release: cceaddon-prometheus
  name: v1beta1.metrics.k8s.io
spec:
  group: metrics.k8s.io
  groupPriorityMinimum: 100
  insecureSkipTLSVerify: true
  service:
    name: custom-metrics-apiserver
    namespace: monitoring
    port: 443
  version: v1beta1
  versionPriority: 100
```

可以将该对象保存为文件，命名为metrics-apiservice.yaml，然后执行以下命令：

```
kubectl create -f metrics-apiservice.yaml
```

执行kubectl top命令，若显示如下，则表示Metrics API能正常访问：

```
# kubectl top pod -n monitoring
NAME                                                      CPU(cores)   MEMORY(bytes)
......
custom-metrics-apiserver-d4f556ff9-l2j2m                  38m          44Mi
......
```

>![](public_sys-resources/icon-notice.gif) **须知：** 
>卸载插件时，需要执行以下kubectl命令，同时删除APIService对象，否则残留的APIService资源将导致metrics-server插件安装失败。
>```
>kubectl delete APIService v1beta1.metrics.k8s.io
>```

## 参考资源<a name="section16331426191116"></a>

-   Prometheus概念及详细配置请参阅[Prometheus 官方文档](https://prometheus.io/docs/introduction/overview/)
-   Node exporter安装请参考[node\_exporter github 仓库](https://github.com/prometheus/node_exporter)
-   Slack 信息发送请参考  [Incoming Webhooks](https://api.slack.com/incoming-webhooks)

## 版本记录<a name="section183121449435"></a>

**表 2**  CCE插件版本记录

<a name="table545952314179"></a>
<table><thead align="left"><tr id="row13459112313176"><th class="cellrowborder" valign="top" width="26.697353279631752%" id="mcps1.2.4.1.1"><p id="p206369328181"><a name="p206369328181"></a><a name="p206369328181"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="34.94438051400076%" id="mcps1.2.4.1.2"><p id="p1663653221810"><a name="p1663653221810"></a><a name="p1663653221810"></a>支持的集群版本</p>
</th>
<th class="cellrowborder" valign="top" width="38.35826620636747%" id="mcps1.2.4.1.3"><p id="p445992311174"><a name="p445992311174"></a><a name="p445992311174"></a>社区版本（仅1.17及以上版本集群支持）</p>
</th>
</tr>
</thead>
<tbody><tr id="row174592023121714"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p946017346239"><a name="p946017346239"></a><a name="p946017346239"></a>2.23.32</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p11289140124818"><a name="p11289140124818"></a><a name="p11289140124818"></a>/v1.(17|19|21).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p1143218810236"><a name="p1143218810236"></a><a name="p1143218810236"></a><a href="https://github.com/prometheus/prometheus/releases/tag/v2.10.0" target="_blank" rel="noopener noreferrer">2.10.0</a></p>
</td>
</tr>
<tr id="row10459723151716"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p16461163410236"><a name="p16461163410236"></a><a name="p16461163410236"></a>2.23.31</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p123031127114817"><a name="p123031127114817"></a><a name="p123031127114817"></a>/v1.15.*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p943208102317"><a name="p943208102317"></a><a name="p943208102317"></a><a href="https://github.com/prometheus/prometheus/releases/tag/v2.10.0" target="_blank" rel="noopener noreferrer">2.10.0</a></p>
</td>
</tr>
<tr id="row3459112341718"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p15461434132316"><a name="p15461434132316"></a><a name="p15461434132316"></a>2.23.30</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p919101814815"><a name="p919101814815"></a><a name="p919101814815"></a>/v1.(17|19|21).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p84329816239"><a name="p84329816239"></a><a name="p84329816239"></a><a href="https://github.com/prometheus/prometheus/releases/tag/v2.10.0" target="_blank" rel="noopener noreferrer">2.10.0</a></p>
</td>
</tr>
<tr id="row114591523181710"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p1746183492312"><a name="p1746183492312"></a><a name="p1746183492312"></a>2.21.14</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p728918104814"><a name="p728918104814"></a><a name="p728918104814"></a>/v1.(17|19|21).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p124328811237"><a name="p124328811237"></a><a name="p124328811237"></a><a href="https://github.com/prometheus/prometheus/releases/tag/v2.10.0" target="_blank" rel="noopener noreferrer">2.10.0</a></p>
</td>
</tr>
<tr id="row646042319177"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p184611634182310"><a name="p184611634182310"></a><a name="p184611634182310"></a>2.21.12</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p12593158154810"><a name="p12593158154810"></a><a name="p12593158154810"></a>/v1.15.*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p18432128132311"><a name="p18432128132311"></a><a name="p18432128132311"></a><a href="https://github.com/prometheus/prometheus/releases/tag/v2.10.0" target="_blank" rel="noopener noreferrer">2.10.0</a></p>
</td>
</tr>
<tr id="row13757134401715"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p1046153432314"><a name="p1046153432314"></a><a name="p1046153432314"></a>2.21.11</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p727861016499"><a name="p727861016499"></a><a name="p727861016499"></a>/v1.(17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p1243216810236"><a name="p1243216810236"></a><a name="p1243216810236"></a><a href="https://github.com/prometheus/prometheus/releases/tag/v2.10.0" target="_blank" rel="noopener noreferrer">2.10.0</a></p>
</td>
</tr>
<tr id="row10575174891715"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p1446143415231"><a name="p1446143415231"></a><a name="p1446143415231"></a>1.15.1</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p13461173472316"><a name="p13461173472316"></a><a name="p13461173472316"></a>/v1.(15|17).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p124321988237"><a name="p124321988237"></a><a name="p124321988237"></a><a href="https://github.com/prometheus/prometheus/releases/tag/v2.10.0" target="_blank" rel="noopener noreferrer">2.10.0</a></p>
</td>
</tr>
</tbody>
</table>

