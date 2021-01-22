# volcano<a name="cce_01_0193"></a>

-   [插件简介](#section173631312185614)
-   [约束与限制](#section11172124718374)
-   [安装插件](#section564214328158)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1395073191112)
-   [版本记录](#section144262219109)

## 插件简介<a name="section173631312185614"></a>

Volcano是一个基于Kubernetes的批处理平台，提供了机器学习、深度学习、生物信息学、基因组学及其他大数据应用所需要而Kubernetes当前缺失的一系列特性。

Volcano源自于华为云高性能批量计算解决方案，在支撑华为云一站式AI开发平台ModelArts、云容器实例CCI等服务稳定运行中发挥重要作用。Volcano提供了高性能任务调度引擎、高性能异构芯片管理、高性能任务运行管理等通用计算能力，通过接入AI、大数据、基因、渲染等诸多行业计算框架服务终端用户。\(目前Volcano项目已经在Github开源\)

Volcano针对计算型应用提供了作业调度、作业管理、队列管理等多项功能，主要特性包括：

-   丰富的计算框架支持：通过CRD提供了批量计算任务的通用API，通过提供丰富的插件及作业生命周期高级管理，支持TensorFlow，MPI，Spark等计算框架容器化运行在Kubernetes上。
-   高级调度：面向批量计算、高性能计算场景提供丰富的高级调度能力，包括成组调度，优先级抢占、装箱、资源预留、任务拓扑关系等。
-   队列管理：支持分队列调度，提供队列优先级、多级队列等复杂任务调度能力。

项目开源地址：[https://github.com/volcano-sh/volcano](https://github.com/volcano-sh/volcano)

## 约束与限制<a name="section11172124718374"></a>

此插件支持[混合集群](购买混合集群.md)，集群版本需为1.13及以上版本。

## 安装插件<a name="section564214328158"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**Volcano**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  Volcano插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“Volcano“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“Volcano“插件时，会替换原先节点上的旧版本的“Volcano“插件，安装最新版本的“Volcano“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  单击“升级“即可升级“Volcano“插件。

## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**Volcano**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  Volcano版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="15.509999999999998%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="27.05%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="17.44%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row152684214528"><td class="cellrowborder" valign="top" width="15.509999999999998%" headers="mcps1.2.5.1.1 "><p id="p18148922182411"><a name="p18148922182411"></a><a name="p18148922182411"></a>1.2.1</p>
</td>
<td class="cellrowborder" valign="top" width="27.05%" headers="mcps1.2.5.1.2 "><p id="p7148192212249"><a name="p7148192212249"></a><a name="p7148192212249"></a>混合集群 v1.13.*|v1.15.*</p>
<p id="p814816222241"><a name="p814816222241"></a><a name="p814816222241"></a>鲲鹏集群 v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.3 "><p id="p1714812252412"><a name="p1714812252412"></a><a name="p1714812252412"></a>2020/08/21</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><a name="ul2148222122412"></a><a name="ul2148222122412"></a><ul id="ul2148222122412"><li>安全增强</li><li>Volcano作业零副本支持</li><li>边缘计算场景支持</li></ul>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="15.509999999999998%" headers="mcps1.2.5.1.1 "><p id="p101481422112413"><a name="p101481422112413"></a><a name="p101481422112413"></a>1.1.2</p>
</td>
<td class="cellrowborder" valign="top" width="27.05%" headers="mcps1.2.5.1.2 "><p id="p1618414467244"><a name="p1618414467244"></a><a name="p1618414467244"></a>混合集群 v1.13.*|v1.15.*</p>
<p id="p4184046162417"><a name="p4184046162417"></a><a name="p4184046162417"></a>鲲鹏集群 v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.3 "><p id="p1148192212417"><a name="p1148192212417"></a><a name="p1148192212417"></a>2020/11/19</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p111080280253"><a name="p111080280253"></a><a name="p111080280253"></a>解决极端情况下Tensorflow作业OOM的问题。</p>
</td>
</tr>
<tr id="row17524111141813"><td class="cellrowborder" valign="top" width="15.509999999999998%" headers="mcps1.2.5.1.1 "><p id="p141481622122418"><a name="p141481622122418"></a><a name="p141481622122418"></a>1.1.0</p>
</td>
<td class="cellrowborder" valign="top" width="27.05%" headers="mcps1.2.5.1.2 "><p id="p16869134972410"><a name="p16869134972410"></a><a name="p16869134972410"></a>混合集群 v1.13.*|v1.15.*</p>
<p id="p3869174918241"><a name="p3869174918241"></a><a name="p3869174918241"></a>鲲鹏集群 v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.3 "><p id="p1714862222410"><a name="p1714862222410"></a><a name="p1714862222410"></a>2020/05/26</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><a name="ul1314882292413"></a><a name="ul1314882292413"></a><ul id="ul1314882292413"><li>支持GPU调度功能</li><li>支持作业扩缩容功能</li><li>支持Linux ARM平台</li></ul>
</td>
</tr>
<tr id="row20524711182"><td class="cellrowborder" valign="top" width="15.509999999999998%" headers="mcps1.2.5.1.1 "><p id="p114852292412"><a name="p114852292412"></a><a name="p114852292412"></a>1.0.4</p>
</td>
<td class="cellrowborder" valign="top" width="27.05%" headers="mcps1.2.5.1.2 "><p id="p5258205319247"><a name="p5258205319247"></a><a name="p5258205319247"></a>混合集群 v1.13.*|v1.15.*</p>
<p id="p1125875315245"><a name="p1125875315245"></a><a name="p1125875315245"></a>鲲鹏集群 v1.13.*|v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.3 "><p id="p1214822214240"><a name="p1214822214240"></a><a name="p1214822214240"></a>2020/11/06</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p571717302251"><a name="p571717302251"></a><a name="p571717302251"></a>解决1.0.3版本升级问题（仅限1.0.3版本）</p>
</td>
</tr>
<tr id="row12172151072417"><td class="cellrowborder" valign="top" width="15.509999999999998%" headers="mcps1.2.5.1.1 "><p id="p18148222162417"><a name="p18148222162417"></a><a name="p18148222162417"></a>1.0.3</p>
</td>
<td class="cellrowborder" valign="top" width="27.05%" headers="mcps1.2.5.1.2 "><p id="p5148422172411"><a name="p5148422172411"></a><a name="p5148422172411"></a>混合集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.3 "><p id="p1714832262416"><a name="p1714832262416"></a><a name="p1714832262416"></a>2019/11/18</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p4438634172519"><a name="p4438634172519"></a><a name="p4438634172519"></a>Volcano是一个基于Kubernetes的批处理平台，提供了机器学习、深度学习、生物信息学、基因组学及其他大数据应用所需要的而 Kubernetes当下缺失的一系列特性。</p>
</td>
</tr>
<tr id="row9487166161815"><td class="cellrowborder" valign="top" width="15.509999999999998%" headers="mcps1.2.5.1.1 "><p id="p1514852242414"><a name="p1514852242414"></a><a name="p1514852242414"></a>1.0.0</p>
</td>
<td class="cellrowborder" valign="top" width="27.05%" headers="mcps1.2.5.1.2 "><p id="p161485229244"><a name="p161485229244"></a><a name="p161485229244"></a>混合集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.5.1.3 "><p id="p1414910221241"><a name="p1414910221241"></a><a name="p1414910221241"></a>2019/08/14</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p104632034132520"><a name="p104632034132520"></a><a name="p104632034132520"></a>kube-batch是一个kubernetes的调度器，提供批量调度工作负载的能力。</p>
</td>
</tr>
</tbody>
</table>

