# metrics-server<a name="cce_10_0205"></a>

从Kubernetes 1.8开始，Kubernetes通过Metrics API提供资源使用指标，例如容器CPU和内存使用率。这些度量可以由用户直接访问（例如，通过使用kubectl top命令），或者由集群中的控制器（例如，Horizontal Pod Autoscaler）使用来进行决策，具体的组件为Metrics-Server，用来替换之前的heapster，heapster从1.11开始逐渐被废弃。

Metrics Server是集群核心资源监控数据的聚合器，您可以在CCE控制台快速安装本插件。

安装本插件后，可在“弹性伸缩“页面的“工作负载伸缩“页签下，创建HPA策略，具体请参见[创建工作负载弹性伸缩（HPA）](创建工作负载弹性伸缩（HPA）.md)。

社区官方项目及文档：[https://github.com/kubernetes-sigs/metrics-server](https://github.com/kubernetes-sigs/metrics-server)。

## 安装插件<a name="section1962241123816"></a>

1.  登录CCE控制台，单击集群名称进入集群，单击左侧导航栏的“插件管理“，在右侧找到**metrics-server**，单击“安装“。
2.  该插件可配置“单实例“、“高可用“或“自定义“规格。
    -   实例数：选择自定义规格时，请根据业务需求选择合适的实例数。
    -   容器：选择自定义规格时，请根据业务需求选择合适的容器配额。

3.  单击“安装“。

## 版本记录<a name="section183121449435"></a>

**表 1**  CCE插件版本记录

<a name="table545952314179"></a>
<table><thead align="left"><tr id="row13459112313176"><th class="cellrowborder" valign="top" width="22.669735327963174%" id="mcps1.2.4.1.1"><p id="p206369328181"><a name="p206369328181"></a><a name="p206369328181"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="38.971998465669344%" id="mcps1.2.4.1.2"><p id="p1663653221810"><a name="p1663653221810"></a><a name="p1663653221810"></a>支持的集群版本</p>
</th>
<th class="cellrowborder" valign="top" width="38.35826620636747%" id="mcps1.2.4.1.3"><p id="p445992311174"><a name="p445992311174"></a><a name="p445992311174"></a>社区版本（仅1.17及以上版本集群支持）</p>
</th>
</tr>
</thead>
<tbody><tr id="row782112501741"><td class="cellrowborder" valign="top" width="22.669735327963174%" headers="mcps1.2.4.1.1 "><p id="p125295016517"><a name="p125295016517"></a><a name="p125295016517"></a>1.3.2</p>
</td>
<td class="cellrowborder" valign="top" width="38.971998465669344%" headers="mcps1.2.4.1.2 "><p id="p75299017514"><a name="p75299017514"></a><a name="p75299017514"></a>/v1.(19|21|23|25).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p1752950459"><a name="p1752950459"></a><a name="p1752950459"></a><a href="https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.4.4" target="_blank" rel="noopener noreferrer">0.4.4</a></p>
</td>
</tr>
<tr id="row174592023121714"><td class="cellrowborder" valign="top" width="22.669735327963174%" headers="mcps1.2.4.1.1 "><p id="p16831824223"><a name="p16831824223"></a><a name="p16831824223"></a>1.2.1</p>
</td>
<td class="cellrowborder" valign="top" width="38.971998465669344%" headers="mcps1.2.4.1.2 "><p id="p0459447114310"><a name="p0459447114310"></a><a name="p0459447114310"></a>/v1.(19|21|23).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p7747930162017"><a name="p7747930162017"></a><a name="p7747930162017"></a><a href="https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.4.4" target="_blank" rel="noopener noreferrer">0.4.4</a></p>
</td>
</tr>
<tr id="row10459723151716"><td class="cellrowborder" valign="top" width="22.669735327963174%" headers="mcps1.2.4.1.1 "><p id="p118382132220"><a name="p118382132220"></a><a name="p118382132220"></a>1.1.10</p>
</td>
<td class="cellrowborder" valign="top" width="38.971998465669344%" headers="mcps1.2.4.1.2 "><p id="p7356131316442"><a name="p7356131316442"></a><a name="p7356131316442"></a>/v1.(15|17|19|21).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p974713012207"><a name="p974713012207"></a><a name="p974713012207"></a><a href="https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.4.4" target="_blank" rel="noopener noreferrer">0.4.4</a></p>
</td>
</tr>
<tr id="row3459112341718"><td class="cellrowborder" valign="top" width="22.669735327963174%" headers="mcps1.2.4.1.1 "><p id="p1583152142212"><a name="p1583152142212"></a><a name="p1583152142212"></a>1.1.4</p>
</td>
<td class="cellrowborder" valign="top" width="38.971998465669344%" headers="mcps1.2.4.1.2 "><p id="p1067412015546"><a name="p1067412015546"></a><a name="p1067412015546"></a>/v1.(15|17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p1574773010205"><a name="p1574773010205"></a><a name="p1574773010205"></a><a href="https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.4.4" target="_blank" rel="noopener noreferrer">0.4.4</a></p>
</td>
</tr>
<tr id="row114591523181710"><td class="cellrowborder" valign="top" width="22.669735327963174%" headers="mcps1.2.4.1.1 "><p id="p6844222215"><a name="p6844222215"></a><a name="p6844222215"></a>1.1.2</p>
</td>
<td class="cellrowborder" valign="top" width="38.971998465669344%" headers="mcps1.2.4.1.2 "><p id="p1067811045418"><a name="p1067811045418"></a><a name="p1067811045418"></a>/v1.(15|17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p1574763015207"><a name="p1574763015207"></a><a name="p1574763015207"></a><a href="https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.4.4" target="_blank" rel="noopener noreferrer">0.4.4</a></p>
</td>
</tr>
<tr id="row646042319177"><td class="cellrowborder" valign="top" width="22.669735327963174%" headers="mcps1.2.4.1.1 "><p id="p148432132218"><a name="p148432132218"></a><a name="p148432132218"></a>1.1.1</p>
</td>
<td class="cellrowborder" valign="top" width="38.971998465669344%" headers="mcps1.2.4.1.2 "><p id="p1526315508440"><a name="p1526315508440"></a><a name="p1526315508440"></a>/v1.(13|15|17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p1432123602016"><a name="p1432123602016"></a><a name="p1432123602016"></a><a href="https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.3.7" target="_blank" rel="noopener noreferrer">0.3.7</a></p>
</td>
</tr>
<tr id="row13757134401715"><td class="cellrowborder" valign="top" width="22.669735327963174%" headers="mcps1.2.4.1.1 "><p id="p584172142212"><a name="p584172142212"></a><a name="p584172142212"></a>1.1.0</p>
</td>
<td class="cellrowborder" valign="top" width="38.971998465669344%" headers="mcps1.2.4.1.2 "><p id="p5585378454"><a name="p5585378454"></a><a name="p5585378454"></a>/v1.(13|15|17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p643293614205"><a name="p643293614205"></a><a name="p643293614205"></a><a href="https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.3.7" target="_blank" rel="noopener noreferrer">0.3.7</a></p>
</td>
</tr>
<tr id="row10575174891715"><td class="cellrowborder" valign="top" width="22.669735327963174%" headers="mcps1.2.4.1.1 "><p id="p284928222"><a name="p284928222"></a><a name="p284928222"></a>1.0.5</p>
</td>
<td class="cellrowborder" valign="top" width="38.971998465669344%" headers="mcps1.2.4.1.2 "><p id="p168442142218"><a name="p168442142218"></a><a name="p168442142218"></a>/v1.13.*|v1.15.*|v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p4432736172020"><a name="p4432736172020"></a><a name="p4432736172020"></a><a href="https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.3.7" target="_blank" rel="noopener noreferrer">0.3.7</a></p>
</td>
</tr>
</tbody>
</table>

