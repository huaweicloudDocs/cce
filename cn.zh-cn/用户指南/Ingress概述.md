# Ingress概述<a name="cce_01_0094"></a>

## 为什么需要Ingress<a name="section17868123416122"></a>

Service是基于四层TCP和UDP协议转发的，而在实际使用场景中，四层Service无法满足应用层存在的大量HTTP/HTTPS访问需求，因此需要使用七层负载均衡（Ingress）来暴露服务。Ingress基于七层的HTTP和HTTPS协议进行转发，它并不是一种Service类型，而是集群流量的入口，可以通过域名和路径对访问做到更细粒度的划分。Ingress作为kubernetes集群中一种独立的资源，需要通过创建它来制定外部访问流量的转发规则，并通过Ingress Controller将其分配到一个或多个Service中。

**图 1**  Ingress示意图<a name="fig813352003010"></a>  
![](figures/Ingress示意图.png "Ingress示意图")

Ingress需要区分两个定义：

-   Ingress资源：一组基于域名或URL把请求转发到指定Service实例的访问规则，是Kubernetes的一种资源对象，Ingress实例被存储在对象存储服务etcd中，通过接口服务实现增、删、改、查的操作。
-   Ingress Controller：请求转发的执行器，用以实时监控资源对象Ingress、Service、End-point、Secret（主要是TLS证书和Key）、Node、ConfigMap的变化，解析Ingress定义的规则并负责将请求转发到相应的后端Service。

因此定义了Ingress后必须要有Ingress Controller来负责执行，而Ingress Controller在不同厂商之间有着不同的实现方式，根据负载均衡器的形式不同，主要可分为ELB型和Nginx型。Kubernetes官方维护的[NGINX Ingress Controller](https://github.com/kubernetes/ingress-nginx)属于Nginx型，而CCE所采用的自研Ingress Controller方案属于ELB型。

## ELB Ingress Controller工作原理<a name="section162271821192312"></a>

CCE自研的ELB Ingress Controller基于弹性负载均衡服务ELB实现公网和内网（同一VPC内）的七层网络访问，通过不同的URL将访问流量分发到对应的服务。ELB根据转发规则将访问流量通过NodePort转发至Pod（ENI负载均衡器直通容器时通过ClusterIP直接转发至Pod），集群可通过配置多个Ingress规则绑定多个ELB实例。

ELB Ingress Controller部署于Master节点上，与集群所在VPC下的弹性负载均衡器绑定，支持在同一个ELB实例（同一IP）下进行不同域名、端口和转发策略的设置，不支持路由的重定向。ELB Ingress Controller的工作原理如[图2](#fig195830353)，主要步骤如下：

1.  用户创建Ingress资源，在Ingress中配置流量访问规则，包括负载均衡器、URL、SSL以及访问的后端Service端口等。
2.  Ingress Controller实现Ingress，当监听到Ingress资源发生变化时，就会根据其中定义的流量访问规则，在ELB侧重新配置监听器以及后端服务器路由。
3.  当用户进行访问时，ELB根据配置的转发策略把流量转发到对应的后端服务器Service端口，最终访问到关联的各个工作负载。

**图 2**  ELB Ingress Controller工作原理<a name="fig195830353"></a>  
![](figures/ELB-Ingress-Controller工作原理.png "ELB-Ingress-Controller工作原理")

## Nginx Ingress Controller工作原理<a name="section1973674703410"></a>

Nginx Ingress Controller是基于弹性负载均衡ELB和[nginx-ingress](nginx-ingress.md)插件实现的，在ELB后增加了Nginx反向代理，从而实现流量的负载均衡及访问控制。

>![](public_sys-resources/icon-note.gif) **说明：** 
>nginx-ingress插件直接使用社区模板与镜像，CCE不提供额外维护，不建议用于商用场景。
>开源社区地址：[https://github.com/kubernetes/ingress-nginx](https://github.com/kubernetes/ingress-nginx)

Nginx型的Ingress Controller通过pod部署在工作节点上，因此引入了相应的运维成本和Nginx组件运行成本，其主要工作原理如[图3](#fig10473974419)，主要步骤如下：

1.  当用户更新Ingress资源后，其中定义的转发规则会通过Ingress Controller生成一段新的Nginx配置文件（nginx.conf）。
2.  Ingress Controller将Nginx配置文件（nginx.conf）写入到内置的Nginx组件中，然后reload完成Nginx反向代理配置的修改和更新。
3.  外部流量通过已创建的负载均衡实例转发到Nginx组件，然后Nginx组件再根据配置文件进行反向代理访问到对应的目标Service，最终访问到各个工作负载。

**图 3**  Nginx Ingress Controller工作原理<a name="fig10473974419"></a>  
![](figures/Nginx-Ingress-Controller工作原理.png "Nginx-Ingress-Controller工作原理")

## Ingress特性<a name="section1048715559515"></a>

**表 1**  Ingress特性

<a name="table202288537526"></a>
<table><thead align="left"><tr id="row9228053165215"><th class="cellrowborder" valign="top" width="33.24332433243324%" id="mcps1.2.4.1.1"><p id="p922895316521"><a name="p922895316521"></a><a name="p922895316521"></a>特性</p>
</th>
<th class="cellrowborder" valign="top" width="33.423342334233425%" id="mcps1.2.4.1.2"><p id="p13228125305218"><a name="p13228125305218"></a><a name="p13228125305218"></a>ELB Ingress Controller</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p13228125318527"><a name="p13228125318527"></a><a name="p13228125318527"></a>Nginx Ingress Controller</p>
</th>
</tr>
</thead>
<tbody><tr id="row57816428239"><td class="cellrowborder" valign="top" width="33.24332433243324%" headers="mcps1.2.4.1.1 "><p id="p11781742112317"><a name="p11781742112317"></a><a name="p11781742112317"></a>运维</p>
</td>
<td class="cellrowborder" valign="top" width="33.423342334233425%" headers="mcps1.2.4.1.2 "><p id="p2078842172310"><a name="p2078842172310"></a><a name="p2078842172310"></a>免运维，更新升级由华为云负责</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p137814215237"><a name="p137814215237"></a><a name="p137814215237"></a>自行安装、升级、维护</p>
</td>
</tr>
<tr id="row181084872314"><td class="cellrowborder" rowspan="3" valign="top" width="33.24332433243324%" headers="mcps1.2.4.1.1 "><p id="p1210958152313"><a name="p1210958152313"></a><a name="p1210958152313"></a>性能</p>
</td>
<td class="cellrowborder" valign="top" width="33.423342334233425%" headers="mcps1.2.4.1.2 "><p id="p55431610591"><a name="p55431610591"></a><a name="p55431610591"></a>一个集群支持多个ELB实例</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1654319101097"><a name="p1654319101097"></a><a name="p1654319101097"></a>一个集群只支持一个ELB实例</p>
</td>
</tr>
<tr id="row16585103017248"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p155851630112413"><a name="p155851630112413"></a><a name="p155851630112413"></a>使用企业级LB，高性能高可用，升级、故障等场景不影响业务转发</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p14585103042418"><a name="p14585103042418"></a><a name="p14585103042418"></a>性能依赖pod的资源配置</p>
</td>
</tr>
<tr id="row76851723191713"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p165541962041"><a name="p165541962041"></a><a name="p165541962041"></a>支持配置动态加载</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p55351361844"><a name="p55351361844"></a><a name="p55351361844"></a>更新配置需reload，可能会造成业务中断</p>
</td>
</tr>
<tr id="row722875385215"><td class="cellrowborder" valign="top" width="33.24332433243324%" headers="mcps1.2.4.1.1 "><p id="p222845317526"><a name="p222845317526"></a><a name="p222845317526"></a>组件部署</p>
</td>
<td class="cellrowborder" valign="top" width="33.423342334233425%" headers="mcps1.2.4.1.2 "><p id="p10228175385218"><a name="p10228175385218"></a><a name="p10228175385218"></a>Master节点，不占用工作节点</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p422855365210"><a name="p422855365210"></a><a name="p422855365210"></a>Worker节点，需要Nginx组件运行成本</p>
</td>
</tr>
<tr id="row7228175315211"><td class="cellrowborder" valign="top" width="33.24332433243324%" headers="mcps1.2.4.1.1 "><p id="p263385598"><a name="p263385598"></a><a name="p263385598"></a>路由重定向</p>
</td>
<td class="cellrowborder" valign="top" width="33.423342334233425%" headers="mcps1.2.4.1.2 "><p id="p1222825310522"><a name="p1222825310522"></a><a name="p1222825310522"></a>不支持</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p172284534528"><a name="p172284534528"></a><a name="p172284534528"></a>支持</p>
</td>
</tr>
<tr id="row1987813625219"><td class="cellrowborder" valign="top" width="33.24332433243324%" headers="mcps1.2.4.1.1 "><p id="p19878173615219"><a name="p19878173615219"></a><a name="p19878173615219"></a>SSL配置</p>
</td>
<td class="cellrowborder" valign="top" width="33.423342334233425%" headers="mcps1.2.4.1.2 "><p id="p2087812369527"><a name="p2087812369527"></a><a name="p2087812369527"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p13878113614522"><a name="p13878113614522"></a><a name="p13878113614522"></a>支持</p>
</td>
</tr>
</tbody>
</table>

由于华为云自研的ELB型Ingress和社区开源的Nginx型Ingress在原理上存在本质区别，因此支持的Service类型不同，如[表2](#table2470112719444)中所示。

**表 2**  支持Service类型

<a name="table2470112719444"></a>
<table><thead align="left"><tr id="row947015271448"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p3470182764415"><a name="p3470182764415"></a><a name="p3470182764415"></a>Ingress类型</p>
</th>
<th class="cellrowborder" valign="top" width="24.959999999999997%" id="mcps1.2.5.1.2"><p id="p3869017153517"><a name="p3869017153517"></a><a name="p3869017153517"></a>访问类型</p>
</th>
<th class="cellrowborder" valign="top" width="24.990000000000002%" id="mcps1.2.5.1.3"><p id="p147012276442"><a name="p147012276442"></a><a name="p147012276442"></a>集群内访问（ClusterIP）</p>
</th>
<th class="cellrowborder" valign="top" width="25.05%" id="mcps1.2.5.1.4"><p id="p847082754411"><a name="p847082754411"></a><a name="p847082754411"></a>节点访问（NodePort）</p>
</th>
</tr>
</thead>
<tbody><tr id="row3470182718442"><td class="cellrowborder" rowspan="2" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p14605135412356"><a name="p14605135412356"></a><a name="p14605135412356"></a>ELB型Ingress</p>
</td>
<td class="cellrowborder" valign="top" width="24.959999999999997%" headers="mcps1.2.5.1.2 "><p id="p1786941773516"><a name="p1786941773516"></a><a name="p1786941773516"></a>负载均衡路由</p>
</td>
<td class="cellrowborder" valign="top" width="24.990000000000002%" headers="mcps1.2.5.1.3 "><p id="p947042718448"><a name="p947042718448"></a><a name="p947042718448"></a>不支持</p>
</td>
<td class="cellrowborder" valign="top" width="25.05%" headers="mcps1.2.5.1.4 "><p id="p7470112784412"><a name="p7470112784412"></a><a name="p7470112784412"></a>支持</p>
</td>
</tr>
<tr id="row1282441143612"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p983184118361"><a name="p983184118361"></a><a name="p983184118361"></a>ENI负载均衡路由</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p3392123216378"><a name="p3392123216378"></a><a name="p3392123216378"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p98354110364"><a name="p98354110364"></a><a name="p98354110364"></a>不支持</p>
</td>
</tr>
<tr id="row12470142713442"><td class="cellrowborder" rowspan="2" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p134701027144413"><a name="p134701027144413"></a><a name="p134701027144413"></a>Nginx型Ingress</p>
</td>
<td class="cellrowborder" valign="top" width="24.959999999999997%" headers="mcps1.2.5.1.2 "><p id="p47775145373"><a name="p47775145373"></a><a name="p47775145373"></a>负载均衡路由</p>
</td>
<td class="cellrowborder" valign="top" width="24.990000000000002%" headers="mcps1.2.5.1.3 "><p id="p18470112720447"><a name="p18470112720447"></a><a name="p18470112720447"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" width="25.05%" headers="mcps1.2.5.1.4 "><p id="p14708278442"><a name="p14708278442"></a><a name="p14708278442"></a>支持</p>
</td>
</tr>
<tr id="row191924423618"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p16777141483718"><a name="p16777141483718"></a><a name="p16777141483718"></a>ENI负载均衡路由</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p162311840143712"><a name="p162311840143712"></a><a name="p162311840143712"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p111913440361"><a name="p111913440361"></a><a name="p111913440361"></a>不支持</p>
</td>
</tr>
</tbody>
</table>

ELB型Ingress Controller部署在master节点，所有策略配置和转发行为均在ELB侧完成。不使用ENI负载均衡的情况下，集群外部的ELB只能通过VPC的IP对接集群内部节点，因此ELB型Ingress也只支持NodePort类型的Service。使用ENI负载均衡后，ELB可直接将流量转发到集群内Pod，此时Ingress仅支持对接ClusterIP类型的Service。

Nginx型Ingress Controller运行在集群中，作为服务通过NodePort对外暴露，流量经过Nginx-ingress转发到集群内其他业务，流量转发行为及转发对象均在集群内部，因此支持ClusterIP和NodePort类型的Service。

综上，华为云自研的ELB型Ingress使用企业级LB进行流量转发，拥有高性能和高稳定性的优点，而Nginx型Ingress Controller部署在集群节点上，牺牲了一定的集群资源但可配置性相对更好。

