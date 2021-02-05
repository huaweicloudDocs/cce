# prometheus<a name="cce_01_0221"></a>

-   [插件简介](#section173631312185614)
-   [插件特点](#section4740192825614)
-   [约束与限制](#section11172124718374)
-   [安装插件](#section189463341114)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1395073191112)
-   [采集自定义指标](#section16495203010263)
-   [采集自定义指标示例](#section11344192116206)
-   [版本记录](#section144262219109)
-   [参考资源](#section16331426191116)

## 插件简介<a name="section173631312185614"></a>

Prometheus是一套开源的系统监控报警框架。它启发于Google的borgmon监控系统，由工作在SoundCloud的Google前员工在2012年创建，作为社区开源项目进行开发，并于2015年正式发布。2016年，Prometheus正式加入Cloud Native Computing Foundation，成为受欢迎度仅次于Kubernetes的项目。

在云容器引擎CCE中，支持以插件的方式快捷安装Prometheus。

插件官网：[https://prometheus.io/](https://prometheus.io/)

开源社区地址：[https://github.com/prometheus/prometheus](https://github.com/prometheus/prometheus)

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

## 约束与限制<a name="section11172124718374"></a>

1.11及以上版本的混合集群支持此插件功能。

## 安装插件<a name="section189463341114"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**Prometheus**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  <a name="li126079206265"></a>在“规格配置“步骤中，配置以下参数：

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
    <tr id="row1535723154615"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p83591731124620"><a name="p83591731124620"></a><a name="p83591731124620"></a>监控数据保留期</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p1736012314462"><a name="p1736012314462"></a><a name="p1736012314462"></a>自定义监控数据需要保留的天数，默认为15天。</p>
    </td>
    </tr>
    <tr id="row133224252315"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p23228259314"><a name="p23228259314"></a><a name="p23228259314"></a>存储</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p13325193219477"><a name="p13325193219477"></a><a name="p13325193219477"></a>按照界面提示配置如下参数：</p>
    <a name="ul14470191614487"></a><a name="ul14470191614487"></a><ul id="ul14470191614487"><li>类型：支持云硬盘。</li><li>可用区：请根据业务需要进行选择。可用区是在同一区域下，电力、网络隔离的物理区域，可用区之间内网互通，不同可用区之间物理隔离。</li><li>子类型：支持普通IO、高IO和超高IO三种类型。各类型对比请参见<a href="购买混合集群.md#li12223421320">系统盘和数据盘</a>。</li><li>容量：请根据业务需要输入存储容量，默认10G。</li></ul>
    <div class="note" id="note132861729114815"><a name="note132861729114815"></a><a name="note132861729114815"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1328618298481"><a name="p1328618298481"></a><a name="p1328618298481"></a>若命名空间monitoring下已存在pvc，将使用此存储作为存储源。</p>
    </div></div>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。

5.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例”中，单击“Prometheus”进入详情页，可以查看插件实例的详细情况。

## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“Prometheus“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“Prometheus“插件时，会替换原先节点上的旧版本的“Prometheus“插件，安装最新版本的“Prometheus“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  参考[安装插件](#li126079206265)中参数说明配置参数后，单击“升级“即可升级“Prometheus“插件。

## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**Prometheus**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 采集自定义指标<a name="section16495203010263"></a>

要采集应用自定义指标，首先要在应用代码中使用Prometheus的[client libraries](https://prometheus.io/docs/instrumenting/clientlibs)采集自定义指标，具体请参考Prometheus的[指导文档](https://prometheus.io/docs/practices/instrumentation)。

应用具备采集指标功能后，需要在工作负载对应的资源上增加配置，让Prometheus拉取指标。

可以在Pod或Service的metadata.annotation增加：

```
prometheus.io/path：'PATH'
prometheus.io/port: 'PORT'
prometheus.io/scrape: 'true'
```

其中，PATH为访问指标的URL，默认为“/metrics”，PORT为指标服务监听的端口。

>![](public_sys-resources/icon-caution.gif) **注意：** 
>若要采集Pod类型的自定义指标，修改的是Deployment中的spec.templates.metadata.annotations。

加上配置后，就能在Prometheus的dashboard中查询到应用的自定义指标了。

如果要将自定义指标用于负载弹性伸缩（HPA），还需要确保Prometheus的指标能够被转换为Kubernetes的指标。安装Prometheus插件后，monitoring命名空间下的custom-metrics-apiserver无状态负载负责将Prometheus的指标转换为Kubernetes的指标，转换规则配置在monitoring命名空间下的配置项（ConfigMap）adapter-config中，请参考[规则配置说明](https://github.com/DirectXMan12/k8s-prometheus-adapter/blob/master/docs/config-walkthrough.md)。

## 采集自定义指标示例<a name="section11344192116206"></a>

我们使用Go语言编写一个采集HTTP请求数的程序，然后让Prometheus抓取指标数据。

>![](public_sys-resources/icon-caution.gif) **注意：** 
>本示例使用[Go modules](https://github.com/golang/go/wiki/Modules#how-to-use-modules)管理依赖。

新建文件夹custom-metrics-demo，进入文件夹，然后将下面的代码保存为main.go：

```
package main

import (
	"fmt"
	"log"
	"net/http"
	"strconv"

	"github.com/prometheus/client_golang/prometheus"
	"github.com/prometheus/client_golang/prometheus/promhttp"
	promclient "github.com/prometheus/client_model/go"
)

// create a Counter metric
var httpRequestCounter = prometheus.NewCounter(
	prometheus.CounterOpts{
		Namespace: "demo",
		Name: "http_requests_total",
		Help: "Number of HTTP requests.",
	},
)

type handler struct {}

func (h *handler) count(w http.ResponseWriter, r *http.Request) {
	// increment the counter on every request
	httpRequestCounter.Inc()

	// get metric value
	m := promclient.Metric{}
	httpRequestCounter.Write(&m)
	count := int64(m.GetCounter().GetValue())

	// log and respond
	text := strconv.FormatInt(count, 10)
	log.Println(text)
	w.Write([]byte(text))
}

func main() {
	// register metrics for collection
	prometheus.MustRegister(httpRequestCounter)

	h := &handler{}
	http.HandleFunc("/count", h.count)
	// expose metrics for Prometheus to collect
	http.Handle("/metrics", promhttp.Handler())

	port := 8080
	addr := fmt.Sprintf(":%d", port)

	log.Printf("serving on port %d", port)

	if err := http.ListenAndServe(addr, nil); err != nil {
		log.Println(err)
	}
}
```

在上面的代码中，我们定义了指标demo\_http\_requests\_total，访问/count接口时增加指标值，访问/metrics接口查询Prometheus指标，服务监听8080端口。

执行以下命令生成模块定义，构建可执行文件：

```
go mod init custom-metrics-demo
go mod tidy
go build .
```

运行服务：

```
./custom-metrics-demo
```

增加demo\_http\_requests\_total指标值：

```
curl http://localhost:8080/count
```

查询Prometheus指标：

```
curl http://localhost:8080/metrics
```

可以看到demo\_http\_requests\_total的值为1。

将示例程序制作成Docker镜像，创建无状态负载，接下来要让Prometheus插件拉取示例程序的指标。

可以在工作负载的Service中增加配置：

```
metadata:
  annotations:
    prometheus.io/port: '8080'
    prometheus.io/scrape: 'true'
```

给Prometheus有状态负载所在节点绑定弹性IP，将Prometheus的Service的访问类型改为节点访问，然后复制访问地址，在浏览器中打开，即可进入Prometheus dashboard，在查询输入框中输入demo\_http\_requests\_total可查询到指标。

由于配置项monitoring/adapter-config中存在如下规则：

```
- seriesQuery: '{kubernetes_namespace!="",kubernetes_service!=""}'
      seriesFilters:
      - isNot: .*_seconds_total
      resources:
        overrides:
          kubernetes_namespace:
            resource: namespace
          kubernetes_service:
            resource: service
      name:
        matches: ^(.*)_total$
        as: ""
      metricsQuery: (avg(sum(rate(<<.Series>>{}[5m])) by (kubernetes_service, instance)) by (kubernetes_service))
```

Prometheus的指标demo\_http\_requests\_total被转换为Kubernetes的指标demo\_http\_requests，其值为5分钟内平均每秒HTTP请求数，调用Kubernetes自定义指标接口查询：

```
kubectl get --raw '/apis/custom.metrics.k8s.io/v1beta1/namespaces/default/services/*/demo_http_requests'
```

>![](public_sys-resources/icon-caution.gif) **注意：** 
>如果修改了monitoring/adapter-config，需要重启monitoring命名空间下的custom-metrics-apiserver无状态负载的实例，使修改生效。

Kubernetes的自定义指标可用于[工作负载伸缩（HPA）](创建工作负载伸缩策略.md)。

## 版本记录<a name="section144262219109"></a>

**表 2**  prometheus版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="24%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row152684214528"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p755643112519"><a name="p755643112519"></a><a name="p755643112519"></a>1.15.1</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p18556831165115"><a name="p18556831165115"></a><a name="p18556831165115"></a>混合集群 v1.(15|17).*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p11556123125117"><a name="p11556123125117"></a><a name="p11556123125117"></a>2020/08/19</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1133595216510"><a name="p1133595216510"></a><a name="p1133595216510"></a>Prometheus是一个监控系统和时间序列库</p>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p45561331155116"><a name="p45561331155116"></a><a name="p45561331155116"></a>1.1.0</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p1055663118517"><a name="p1055663118517"></a><a name="p1055663118517"></a>混合集群 v1.11.*|v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p9556173112515"><a name="p9556173112515"></a><a name="p9556173112515"></a>2020/07/29</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p193487529519"><a name="p193487529519"></a><a name="p193487529519"></a>Prometheus是一个监控系统和时间序列库</p>
</td>
</tr>
</tbody>
</table>

## 参考资源<a name="section16331426191116"></a>

-   Prometheus概念及详细配置请参阅[Prometheus 官方文档](https://prometheus.io/docs/introduction/overview/)
-   Node exporter安装请参考[node\_exporter github 仓库](https://github.com/prometheus/node_exporter)
-   Slack 信息发送请参考  [Incoming Webhooks](https://api.slack.com/incoming-webhooks)

