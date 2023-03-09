# autoscaler<a name="cce_10_0154"></a>

## 插件简介<a name="section25311744154917"></a>

autoscaler是Kubernetes中非常重要的一个Controller，它提供了微服务的弹性能力，并且和Serverless密切相关。

弹性伸缩是很好理解的一个概念，当微服务负载高（CPU/内存使用率过高）时水平扩容，增加pod的数量以降低负载，当负载降低时减少pod的数量，减少资源的消耗，通过这种方式使得微服务始终稳定在一个理想的状态。

云容器引擎简化了Kubernetes集群的创建、升级和手动扩缩容，而集群中应用的负载本身是会随着时间动态变化的，为了更好的平衡资源使用率以及性能，Kubernetes引入了autoscaler插件，它可以根据部署的应用所请求的资源量自动的动态的伸缩集群，详情请了解[创建节点伸缩策略](创建节点伸缩策略.md)。

**开源社区地址：**[https://github.com/kubernetes/autoscaler](https://github.com/kubernetes/autoscaler)

## 插件说明<a name="section11187642115211"></a>

autoscaler可分成扩容和缩容两个方面：

-   **自动扩容**

    集群的自动扩容有以下两种方式实现：

    -   当集群中的Pod由于工作节点资源不足而无法调度时，会触发集群扩容，扩容节点与所在节点池资源配额一致。

        此时需要满足以下条件时才会执行自动扩容：

        -   节点上的资源不足。
        -   Pod的调度配置中不能包含节点亲和的策略（即Pod若已经设置亲和某个节点，则不会自动扩容节点），节点亲和策略设置方法请参见[调度策略（亲和与反亲和）](调度策略（亲和与反亲和）.md)。

    -   当集群满足节点伸缩策略时，也会触发集群扩容，详情请参见[创建节点伸缩策略](创建节点伸缩策略.md)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >当前该插件使用的是最小浪费策略，即若Pod创建需要3核，此时有4核、8核两种规格，优先创建规格为4核的节点。

-   **自动缩容**

    当集群节点处于一段时间空闲状态时（默认10min），会触发集群缩容操作（即节点会被自动删除）。当节点存在以下几种状态的Pod时，不可缩容：

    -   Pod有设置PodDisruptionBudget，当移除Pod不满足对应条件时，节点不会缩容。
    -   Pod由于一些限制，如亲和、反亲和等，无法调度到其他节点，节点不会缩容。
    -   Pod拥有cluster-autoscaler.kubernetes.io/safe-to-evict: 'false'这个annotations时，节点不缩容。
    -   节点上存在kube-system命名空间下的Pod（除kube-system daemonset创建的Pod），节点不缩容。
    -   节点上如果有非controller（deployment/replicaset/job/statefulset）创建的Pod，节点不缩容。


## 约束与限制<a name="section202191122814"></a>

-   集群为1.9.7-r1及以上版本时，才支持此功能。
-   安装时请确保有足够的资源安装本插件。
-   该插件功能仅支持通过**按需计费**方式购买的**虚拟机节点**，不支持“包年/包月“方式购买的节点和裸金属节点。
-   默认节点池不支持弹性扩缩容，详情请参见[默认节点池DefaultPool说明](节点池概述.md#section16928123042115)。

## 安装插件<a name="section15573161754711"></a>

1.  登录CCE控制台，单击集群名称进入集群，在左侧导航栏中选择“ 插件管理“，在右侧找到**autoscaler**，单击“安装“。
2.  配置插件安装参数。

    **表 1**  规格配置

    <a name="table1582194517429"></a>
    <table><thead align="left"><tr id="row178187453428"><th class="cellrowborder" valign="top" width="22.89%" id="mcps1.2.3.1.1"><p id="p14818104534219"><a name="p14818104534219"></a><a name="p14818104534219"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="77.11%" id="mcps1.2.3.1.2"><p id="p181814453425"><a name="p181814453425"></a><a name="p181814453425"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row178631475226"><td class="cellrowborder" valign="top" width="22.89%" headers="mcps1.2.3.1.1 "><p id="p386464792210"><a name="p386464792210"></a><a name="p386464792210"></a>插件规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="77.11%" headers="mcps1.2.3.1.2 "><p id="p1861133733913"><a name="p1861133733913"></a><a name="p1861133733913"></a>插件部署可选择如下几种规格。</p>
    <div class="note" id="note317239144516"><a name="note317239144516"></a><a name="note317239144516"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p21873918457"><a name="p21873918457"></a><a name="p21873918457"></a>autoscaler插件高可用或自定义部署时，插件实例间存在反亲和策略，会分别部署在不同的节点上，因此集群中的可用节点必须大于等于插件实例数才可保证插件高可用。</p>
    </div></div>
    <a name="ul1634319358233"></a><a name="ul1634319358233"></a><ul id="ul1634319358233"><li>单实例：以单实例部署插件。</li><li>高可用50：50节点集群规模多实例部署，实例数为2，具有高可用能力。</li><li>高可用200：200节点集群规模多实例部署，实例数为2，具有高可用能力，每个实例使用资源比高可用50的实例更多。</li><li>自定义：根据需要自定义实例数量和实例规格。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  参数配置

    <a name="table0286202110139"></a>
    <table><thead align="left"><tr id="row3287142131313"><th class="cellrowborder" valign="top" width="28.64%" id="mcps1.2.3.1.1"><p id="p122877214130"><a name="p122877214130"></a><a name="p122877214130"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="71.36%" id="mcps1.2.3.1.2"><p id="p13287112110132"><a name="p13287112110132"></a><a name="p13287112110132"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row228792161312"><td class="cellrowborder" valign="top" width="28.64%" headers="mcps1.2.3.1.1 "><p id="p132872021121315"><a name="p132872021121315"></a><a name="p132872021121315"></a>扩缩容配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.36%" headers="mcps1.2.3.1.2 "><p id="p7582201961710"><a name="p7582201961710"></a><a name="p7582201961710"></a>可以勾选自动扩缩容。</p>
    <a name="ul1871517527163"></a><a name="ul1871517527163"></a><ul id="ul1871517527163"><li><strong id="b1956111198"><a name="b1956111198"></a><a name="b1956111198"></a>当集群下负载实例无法调度时自动扩容（从节点池）</strong><p id="p1477772216710"><a name="p1477772216710"></a><a name="p1477772216710"></a>即当出现Pod处于Pending状态无法调度时，集群会自动扩容节点。若Pod已经设置亲和某个节点，则不会自动扩容节点。该功能一般与HPA策略配合使用，具体请参见<a href="使用HPA+CA实现工作负载和节点联动弹性伸缩.md">使用HPA+CA实现工作负载和节点联动弹性伸缩</a>。</p>
    <p id="p18756721694"><a name="p18756721694"></a><a name="p18756721694"></a>如不勾选，则只能通过<a href="创建节点伸缩策略.md">节点伸缩策略</a>进行扩缩容。</p>
    </li><li><strong id="b0625115171919"><a name="b0625115171919"></a><a name="b0625115171919"></a>自动缩容节点</strong><a name="ul3971951111917"></a><a name="ul3971951111917"></a><ul id="ul3971951111917"><li>空置时间（min）：当集群节点处于一段时间的空闲状态时，会触发集群缩容操作，删除节点，默认10min。</li><li>缩容阈值：当集群节点资源（Request值）低于多少百分比时，进行集群缩容扫描（默认0.5，即50%，cpu和mem都要满足的条件下才会缩容）。</li><li>冷却时间：<p id="p08155492115"><a name="p08155492115"></a><a name="p08155492115"></a>扩容执行后多久能再次判断是否缩容，默认10min。</p>
    <div class="note" id="note11141447375"><a name="note11141447375"></a><a name="note11141447375"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1445674518371"><a name="p1445674518371"></a><a name="p1445674518371"></a>集群中如果同时存在自动扩容和自动缩容的场景，建议配置“扩容执行后多久能再次判断是否缩容”为0min，避免由于部分节点池持续扩容或者扩容失败重试而阻塞整体缩容节点行为，导致非预期的节点资源浪费。</p>
    </div></div>
    <p id="p078505512112"><a name="p078505512112"></a><a name="p078505512112"></a>节点删除后多久能再次判断是否缩容：删除节点后能再次启动缩容评估的时间间隔，默认10min。</p>
    <p id="p18884155610211"><a name="p18884155610211"></a><a name="p18884155610211"></a>缩容失败后多久能再次判断是否缩容：缩容失败后能再次启动缩容评估的时间间隔，默认3min。节点池中配置的缩容冷却时间和此处配置的缩容冷却时间之间的影响和关系请参见<a href="#section59676731017">缩容冷却时间说明</a>。</p>
    </li><li>缩容并发数：最多支持多少个空闲节点同时缩容，默认10。<div class="p" id="p10129161053611"><a name="p10129161053611"></a><a name="p10129161053611"></a>缩容并发数只针对完全空闲节点，完全空闲节点可实现并发缩容。非完全空闲节点则只能逐个缩容。<div class="note" id="note4801630340"><a name="note4801630340"></a><a name="note4801630340"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p19806301449"><a name="p19806301449"></a><a name="p19806301449"></a>节点在缩容的时候，若节点上的Pod不需要驱逐（DaemonSet的Pod认为不需要驱逐），则认为该节点为完全空闲节点，否则认为该节点为非完全空闲。</p>
    </div></div>
    </div>
    </li><li>检查间隔：节点被判定不可移除后能再次启动检查的时间间隔，默认5min。</li></ul>
    </li></ul>
    </td>
    </tr>
    <tr id="row18287122141315"><td class="cellrowborder" valign="top" width="28.64%" headers="mcps1.2.3.1.1 "><p id="p1102571612"><a name="p1102571612"></a><a name="p1102571612"></a>节点总数</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.36%" headers="mcps1.2.3.1.2 "><p id="p1253551412214"><a name="p1253551412214"></a><a name="p1253551412214"></a>集群可管理的节点数目的最大值，扩容时不会让集群下节点数超过此值。</p>
    </td>
    </tr>
    <tr id="row11288721191315"><td class="cellrowborder" valign="top" width="28.64%" headers="mcps1.2.3.1.1 "><p id="p5182513167"><a name="p5182513167"></a><a name="p5182513167"></a>CPU总数（核）</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.36%" headers="mcps1.2.3.1.2 "><p id="p136391289161"><a name="p136391289161"></a><a name="p136391289161"></a>集群中所有节点 CPU 核数之和的最大值，扩容时不会让集群下节点CPU核数之和超过此值。</p>
    </td>
    </tr>
    <tr id="row158581823181616"><td class="cellrowborder" valign="top" width="28.64%" headers="mcps1.2.3.1.1 "><p id="p91162591614"><a name="p91162591614"></a><a name="p91162591614"></a>内存总数（GB）</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.36%" headers="mcps1.2.3.1.2 "><p id="p135351014162119"><a name="p135351014162119"></a><a name="p135351014162119"></a>集群中所有节点内存之和的最大值，扩容时不会让集群下节点内存之和超过此值。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  配置完成后，单击“安装”。

## 缩容冷却时间说明<a name="section59676731017"></a>

节点池中配置的缩容冷却时间和autoscaler插件中配置的缩容冷却时间之间的影响和关系如下：

**节点池配置的缩容冷却时间**

弹性缩容冷却时间：当前节点池扩容出的节点多长时间不能被缩容，作用范围为节点池级别。

**autoscaler插件配置的缩容冷却时间**

扩容后缩容冷却时间：autoscaler触发扩容后（不可调度、指标、周期策略）整个集群多长时间内不能被缩容，作用范围为集群级别。

节点删除后缩容冷却时间：autoscaler触发缩容后整个集群多长时间内不能继续缩容，作用范围为集群级别。

缩容失败后缩容冷却时间：autoscaler触发缩容失败后整个集群多长时间内不能继续缩容，作用范围为集群级别。

## 版本记录<a name="section183121449435"></a>

**表 3**  CCE插件版本记录

<a name="table228364210318"></a>
<table><thead align="left"><tr id="row16283442331"><th class="cellrowborder" valign="top" width="32.2026620867325%" id="mcps1.2.4.1.1"><p id="p4294151015419"><a name="p4294151015419"></a><a name="p4294151015419"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="35.594675826534996%" id="mcps1.2.4.1.2"><p id="p1029413104417"><a name="p1029413104417"></a><a name="p1029413104417"></a>支持的集群版本</p>
</th>
<th class="cellrowborder" valign="top" width="32.2026620867325%" id="mcps1.2.4.1.3"><p id="p152839427312"><a name="p152839427312"></a><a name="p152839427312"></a>社区版本（仅1.17及以上版本集群支持）</p>
</th>
</tr>
</thead>
<tbody><tr id="row1349320135713"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p4493160175720"><a name="p4493160175720"></a><a name="p4493160175720"></a>1.25.7</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p0286151715716"><a name="p0286151715716"></a><a name="p0286151715716"></a>/v1.25.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p154933075720"><a name="p154933075720"></a><a name="p154933075720"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.25.0" target="_blank" rel="noopener noreferrer">1.25.0</a></p>
</td>
</tr>
<tr id="row980164818563"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p10113185725613"><a name="p10113185725613"></a><a name="p10113185725613"></a>1.23.17</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p111325765619"><a name="p111325765619"></a><a name="p111325765619"></a>/v1.23.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p1111335705617"><a name="p1111335705617"></a><a name="p1111335705617"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.23.0" target="_blank" rel="noopener noreferrer">1.23.0</a></p>
</td>
</tr>
<tr id="row1337592419565"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p15375324115618"><a name="p15375324115618"></a><a name="p15375324115618"></a>1.23.10</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p149113895611"><a name="p149113895611"></a><a name="p149113895611"></a>/v1.23.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p918374565612"><a name="p918374565612"></a><a name="p918374565612"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.23.0" target="_blank" rel="noopener noreferrer">1.23.0</a></p>
</td>
</tr>
<tr id="row44271727940"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p342722712413"><a name="p342722712413"></a><a name="p342722712413"></a>1.23.9</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p2362162019521"><a name="p2362162019521"></a><a name="p2362162019521"></a>/v1.23.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p9699134315416"><a name="p9699134315416"></a><a name="p9699134315416"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.23.0" target="_blank" rel="noopener noreferrer">1.23.0</a></p>
</td>
</tr>
<tr id="row2027517815413"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p18275781843"><a name="p18275781843"></a><a name="p18275781843"></a>1.23.8</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p16373162018522"><a name="p16373162018522"></a><a name="p16373162018522"></a>/v1.23.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p1228915241049"><a name="p1228915241049"></a><a name="p1228915241049"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.23.0" target="_blank" rel="noopener noreferrer">1.23.0</a></p>
</td>
</tr>
<tr id="row92834424319"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p1629420102414"><a name="p1629420102414"></a><a name="p1629420102414"></a>1.23.7</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p1838012016525"><a name="p1838012016525"></a><a name="p1838012016525"></a>/v1.23.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p176996431145"><a name="p176996431145"></a><a name="p176996431145"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.23.0" target="_blank" rel="noopener noreferrer">1.23.0</a></p>
</td>
</tr>
<tr id="row628417421638"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p52941510345"><a name="p52941510345"></a><a name="p52941510345"></a>1.23.3</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p7389172010525"><a name="p7389172010525"></a><a name="p7389172010525"></a>/v1.23.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p269916431046"><a name="p269916431046"></a><a name="p269916431046"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.23.0" target="_blank" rel="noopener noreferrer">1.23.0</a></p>
</td>
</tr>
<tr id="row8688516192010"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p1168810161207"><a name="p1168810161207"></a><a name="p1168810161207"></a>1.21.8</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p196514152521"><a name="p196514152521"></a><a name="p196514152521"></a>/v1.21.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p13689203832019"><a name="p13689203832019"></a><a name="p13689203832019"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.21.0" target="_blank" rel="noopener noreferrer">1.21.0</a></p>
</td>
</tr>
<tr id="row12841542238"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p1294151020419"><a name="p1294151020419"></a><a name="p1294151020419"></a>1.21.6</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p1772111565220"><a name="p1772111565220"></a><a name="p1772111565220"></a>/v1.21.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p66165536413"><a name="p66165536413"></a><a name="p66165536413"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.21.0" target="_blank" rel="noopener noreferrer">1.21.0</a></p>
</td>
</tr>
<tr id="row1628412420313"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p5294141018417"><a name="p5294141018417"></a><a name="p5294141018417"></a>1.21.4</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p1078161516529"><a name="p1078161516529"></a><a name="p1078161516529"></a>/v1.21.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p17616195320410"><a name="p17616195320410"></a><a name="p17616195320410"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.21.0" target="_blank" rel="noopener noreferrer">1.21.0</a></p>
</td>
</tr>
<tr id="row128414215316"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p1929418102411"><a name="p1929418102411"></a><a name="p1929418102411"></a>1.21.2</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p158414151523"><a name="p158414151523"></a><a name="p158414151523"></a>/v1.21.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p106161753146"><a name="p106161753146"></a><a name="p106161753146"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.21.0" target="_blank" rel="noopener noreferrer">1.21.0</a></p>
</td>
</tr>
<tr id="row6284114214319"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p11294171013411"><a name="p11294171013411"></a><a name="p11294171013411"></a>1.21.1</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p09321595220"><a name="p09321595220"></a><a name="p09321595220"></a>/v1.21.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p1161610531746"><a name="p1161610531746"></a><a name="p1161610531746"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.21.0" target="_blank" rel="noopener noreferrer">1.21.0</a></p>
</td>
</tr>
<tr id="row728410421638"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p1829513101341"><a name="p1829513101341"></a><a name="p1829513101341"></a>1.19.13</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p8346554522"><a name="p8346554522"></a><a name="p8346554522"></a>/v1.19.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p1361635316416"><a name="p1361635316416"></a><a name="p1361635316416"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.21.0" target="_blank" rel="noopener noreferrer">1.21.0</a></p>
</td>
</tr>
<tr id="row1013418418416"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p192954101246"><a name="p192954101246"></a><a name="p192954101246"></a>1.19.12</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p1935919545212"><a name="p1935919545212"></a><a name="p1935919545212"></a>/v1.19.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p87115211515"><a name="p87115211515"></a><a name="p87115211515"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.19.0" target="_blank" rel="noopener noreferrer">1.19.0</a></p>
</td>
</tr>
<tr id="row47671241418"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p629551011418"><a name="p629551011418"></a><a name="p629551011418"></a>1.19.11</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p1937212517528"><a name="p1937212517528"></a><a name="p1937212517528"></a>/v1.19.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p1771121856"><a name="p1771121856"></a><a name="p1771121856"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.19.0" target="_blank" rel="noopener noreferrer">1.19.0</a></p>
</td>
</tr>
<tr id="row294314411419"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p1429513101449"><a name="p1429513101449"></a><a name="p1429513101449"></a>1.19.9</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p437912525211"><a name="p437912525211"></a><a name="p437912525211"></a>/v1.19.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p177152659"><a name="p177152659"></a><a name="p177152659"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.19.0" target="_blank" rel="noopener noreferrer">1.19.0</a></p>
</td>
</tr>
<tr id="row5100105944"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p929517103410"><a name="p929517103410"></a><a name="p929517103410"></a>1.19.8</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p338420545218"><a name="p338420545218"></a><a name="p338420545218"></a>/v1.19.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p77122455"><a name="p77122455"></a><a name="p77122455"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.19.0" target="_blank" rel="noopener noreferrer">1.19.0</a></p>
</td>
</tr>
<tr id="row1627919510418"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p12951510046"><a name="p12951510046"></a><a name="p12951510046"></a>1.19.7</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p19390175155213"><a name="p19390175155213"></a><a name="p19390175155213"></a>/v1.19.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p172421555"><a name="p172421555"></a><a name="p172421555"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.19.0" target="_blank" rel="noopener noreferrer">1.19.0</a></p>
</td>
</tr>
<tr id="row1543315947"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p829517106415"><a name="p829517106415"></a><a name="p829517106415"></a>1.19.6</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p10395175175211"><a name="p10395175175211"></a><a name="p10395175175211"></a>/v1.19.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p17721621515"><a name="p17721621515"></a><a name="p17721621515"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.19.0" target="_blank" rel="noopener noreferrer">1.19.0</a></p>
</td>
</tr>
<tr id="row136031452416"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p02951610244"><a name="p02951610244"></a><a name="p02951610244"></a>1.19.3</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p5623628125013"><a name="p5623628125013"></a><a name="p5623628125013"></a>/v1.19.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p16721522051"><a name="p16721522051"></a><a name="p16721522051"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.19.0" target="_blank" rel="noopener noreferrer">1.19.0</a></p>
</td>
</tr>
<tr id="row108517255112"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p5557193510113"><a name="p5557193510113"></a><a name="p5557193510113"></a>1.17.21</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p99222049135119"><a name="p99222049135119"></a><a name="p99222049135119"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p165571735618"><a name="p165571735618"></a><a name="p165571735618"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.19.0" target="_blank" rel="noopener noreferrer">1.19.0</a></p>
</td>
</tr>
<tr id="row1576545640"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p72957108420"><a name="p72957108420"></a><a name="p72957108420"></a>1.17.19</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p139431949195110"><a name="p139431949195110"></a><a name="p139431949195110"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p2072525516"><a name="p2072525516"></a><a name="p2072525516"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.19.0" target="_blank" rel="noopener noreferrer">1.19.0</a></p>
</td>
</tr>
<tr id="row1192415512417"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p529551011411"><a name="p529551011411"></a><a name="p529551011411"></a>1.17.17</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p1795534955118"><a name="p1795534955118"></a><a name="p1795534955118"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p1666299354"><a name="p1666299354"></a><a name="p1666299354"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.17.0" target="_blank" rel="noopener noreferrer">1.17.0</a></p>
</td>
</tr>
<tr id="row10961064419"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p122961010341"><a name="p122961010341"></a><a name="p122961010341"></a>1.17.16</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p1496194905115"><a name="p1496194905115"></a><a name="p1496194905115"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p1366217918518"><a name="p1366217918518"></a><a name="p1366217918518"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.17.0" target="_blank" rel="noopener noreferrer">1.17.0</a></p>
</td>
</tr>
<tr id="row1925756445"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p10296610043"><a name="p10296610043"></a><a name="p10296610043"></a>1.17.15</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p119685494518"><a name="p119685494518"></a><a name="p119685494518"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p14662159558"><a name="p14662159558"></a><a name="p14662159558"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.17.0" target="_blank" rel="noopener noreferrer">1.17.0</a></p>
</td>
</tr>
<tr id="row1142836242"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p02968101346"><a name="p02968101346"></a><a name="p02968101346"></a>1.17.14</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p297474911517"><a name="p297474911517"></a><a name="p297474911517"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p16621691754"><a name="p16621691754"></a><a name="p16621691754"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.17.0" target="_blank" rel="noopener noreferrer">1.17.0</a></p>
</td>
</tr>
<tr id="row6589761644"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p8296141014416"><a name="p8296141014416"></a><a name="p8296141014416"></a>1.17.8</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p10981164913519"><a name="p10981164913519"></a><a name="p10981164913519"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p96621991511"><a name="p96621991511"></a><a name="p96621991511"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.17.0" target="_blank" rel="noopener noreferrer">1.17.0</a></p>
</td>
</tr>
<tr id="row9759763419"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p1929613101041"><a name="p1929613101041"></a><a name="p1929613101041"></a>1.17.7</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p1987549115110"><a name="p1987549115110"></a><a name="p1987549115110"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p176621391658"><a name="p176621391658"></a><a name="p176621391658"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.17.0" target="_blank" rel="noopener noreferrer">1.17.0</a></p>
</td>
</tr>
<tr id="row169191861745"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p1629612101643"><a name="p1629612101643"></a><a name="p1629612101643"></a>1.17.5</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p999515497514"><a name="p999515497514"></a><a name="p999515497514"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p6662109054"><a name="p6662109054"></a><a name="p6662109054"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.17.0" target="_blank" rel="noopener noreferrer">1.17.0</a></p>
</td>
</tr>
<tr id="row15761171342"><td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.1 "><p id="p92964101246"><a name="p92964101246"></a><a name="p92964101246"></a>1.17.2</p>
</td>
<td class="cellrowborder" valign="top" width="35.594675826534996%" headers="mcps1.2.4.1.2 "><p id="p146854017231"><a name="p146854017231"></a><a name="p146854017231"></a>/v1.17.*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.2026620867325%" headers="mcps1.2.4.1.3 "><p id="p166621991954"><a name="p166621991954"></a><a name="p166621991954"></a><a href="https://github.com/kubernetes/autoscaler/releases/tag/cluster-autoscaler-1.17.0" target="_blank" rel="noopener noreferrer">1.17.0</a></p>
</td>
</tr>
</tbody>
</table>

