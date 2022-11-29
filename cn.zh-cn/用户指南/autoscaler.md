# autoscaler<a name="cce_10_0154"></a>

## 插件简介<a name="section25311744154917"></a>

autoscaler是Kubernetes中非常重要的一个Controller，它提供了微服务的弹性能力，并且和Serverless密切相关。

弹性伸缩是很好理解的一个概念，当微服务负载高（CPU/内存使用率过高）时水平扩容，增加pod的数量以降低负载，当负载降低时减少pod的数量，减少资源的消耗，通过这种方式使得微服务始终稳定在一个理想的状态。

云容器引擎简化了Kubernetes集群的创建、升级和手动扩缩容，而集群中应用的负载本身是会随着时间动态变化的，为了更好的平衡资源使用率以及性能，kubernetes引入了autoscaler插件，它可以根据部署的应用所请求的资源量自动的动态的伸缩集群，详情请了解[创建节点伸缩策略](创建节点伸缩策略.md)。

**开源社区地址：**[https://github.com/kubernetes/autoscaler](https://github.com/kubernetes/autoscaler)

## 插件说明<a name="section11187642115211"></a>

autoscaler可分成扩容和缩容两个方面：

-   **自动扩容**

    当集群中的Pod由于工作节点资源不足而无法调度时，会触发集群扩容，扩容节点与所在分组资源配额一致。详情请参见[创建节点伸缩策略](创建节点伸缩策略.md)。

    当前该插件使用的是最小浪费策略，即若pod创建需要3核，此时有4核、8核两种规格，优先创建规格为4核的节点。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >自动扩容策略在满足如下条件时才会执行：
    >-   节点上的资源不足。
    >-   Pod的调度配置中不能包含节点亲和的策略（即Pod若已经设置亲和某个节点，则不会自动扩容节点），节点亲和策略设置方法请参见[调度策略（亲和与反亲和）](调度策略（亲和与反亲和）.md)。

-   **自动缩容**

    当集群节点处于一段时间空闲状态时（默认10min），会触发集群缩容操作（即节点会被自动删除）。当节点存在以下几种状态的pod时，不可缩容：

    -   pod有设置PodDisruptionBudget，当移除pod不满足对应条件时，节点不会缩容。
    -   pod由于一些限制，如亲和、反亲和等，无法调度到其他节点，节点不会缩容。
    -   pod拥有cluster-autoscaler.kubernetes.io/safe-to-evict: 'false'这个annotations时，节点不缩容。
    -   节点上存在kube-system namespace下的Pod（除kube-system daemonset创建的Pod），节点不缩容。
    -   节点上如果有非controller（deployment/replica set/job/stateful set）创建的Pod，节点不缩容。


## 约束与限制<a name="section202191122814"></a>

-   集群为1.9.7-r1及以上版本时，才支持此功能。
-   安装时请确保有足够的资源安装本插件。
-   该插件功能仅支持通过**按需计费**方式购买的**虚拟机节点**，不支持“包年/包月“方式购买的节点和裸金属节点。
-   默认节点池不支持弹性扩缩容，详情请参见[默认节点池DefaultPool说明](节点池概述.md#section16928123042115)。

## 安装插件<a name="section15573161754711"></a>

1.  登录CCE控制台，进入集群，在左侧导航栏中选择“ 插件管理“，在右侧找到**autoscaler**，单击“安装“。
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
    <a name="ul1871517527163"></a><a name="ul1871517527163"></a><ul id="ul1871517527163"><li><strong id="b1956111198"><a name="b1956111198"></a><a name="b1956111198"></a>当集群下负载实例无法调度时自动扩容（从节点池）</strong><p id="p1477772216710"><a name="p1477772216710"></a><a name="p1477772216710"></a>即当出现Pod处于Pending状态无法调度时自动扩容，一般与HPA策略配合使用，具体请参见<a href="使用HPA+CA实现工作负载和节点联动弹性伸缩.md">使用HPA+CA实现工作负载和节点联动弹性伸缩</a>。</p>
    <p id="p18756721694"><a name="p18756721694"></a><a name="p18756721694"></a>如不勾选，则只能通过<a href="创建节点伸缩策略.md">节点伸缩策略</a>进行扩缩容。</p>
    </li><li><strong id="b0625115171919"><a name="b0625115171919"></a><a name="b0625115171919"></a>自动缩容节点</strong><a name="ul3971951111917"></a><a name="ul3971951111917"></a><ul id="ul3971951111917"><li>空置时间（min）：当集群节点处于一段时间的空闲状态时，会触发集群缩容操作，删除节点，默认10min。</li><li>缩容阈值：当集群节点资源（Request值）低于多少百分比时，进行集群缩容扫描（默认0.5，即50%，cpu和mem都要满足的条件下才会缩容）。</li><li>冷却时间：<p id="p08155492115"><a name="p08155492115"></a><a name="p08155492115"></a>扩容执行后多久能再次判断是否缩容，默认10min。</p>
    <div class="note" id="note11141447375"><a name="note11141447375"></a><a name="note11141447375"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1445674518371"><a name="p1445674518371"></a><a name="p1445674518371"></a>集群中如果同时存在自动扩容和自动缩容的场景，建议配置“扩容执行后多久能再次判断是否缩容”为0min，避免由于部分节点池持续扩容或者扩容失败重试而阻塞整体缩容节点行为，导致非预期的节点资源浪费。</p>
    </div></div>
    <p id="p078505512112"><a name="p078505512112"></a><a name="p078505512112"></a>节点删除后多久能再次判断是否缩容：删除节点后能再次启动缩容评估的时间间隔，默认10min。</p>
    <p id="p18884155610211"><a name="p18884155610211"></a><a name="p18884155610211"></a>缩容失败后多久能再次判断是否缩容：缩容失败后能再次启动缩容评估的时间间隔，默认3min。节点池中配置的缩容冷却时间和此处配置的缩容冷却时间之间的影响和关系请参见<a href="#section59676731017">缩容冷却时间说明</a>。</p>
    </li><li>缩容并发数：最多支持多少个空闲节点同时缩容，默认10。</li><li>检查间隔：节点被判定不可移除后能再次启动检查的时间间隔，默认5min。</li></ul>
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

