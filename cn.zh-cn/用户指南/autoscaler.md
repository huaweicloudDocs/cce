# autoscaler<a name="cce_01_0154"></a>

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
    >-   Pod的调度配置中不能包含节点亲和的策略（即Pod若已经设置亲和某个节点，则不会自动扩容节点），节点亲和策略设置方法请参见[节点亲和性](节点亲和性.md)。

-   **自动缩容**

    当集群节点处于一段时间空闲状态时（默认10min），会触发集群缩容操作（即节点会被自动删除）。当节点存在以下几种状态的pod时，不可缩容：

    -   pod有设置PodDisruptionBudget，当移除pod不满足对应条件时，节点不会缩容。
    -   pod由于一些限制，如亲和、反亲和等，无法调度到其他节点，节点不会缩容。
    -   pod拥有cluster-autoscaler.kubernetes.io/safe-to-evict: 'false'这个annotations时，节点不缩容。
    -   节点上存在kube-system namespace下的Pod（除kube-system daemonset创建的Pod），节点不缩容。
    -   节点上有非controller（deployment/replica set/job/stateful set）创建的Pod，节点不缩容。


## 约束与限制<a name="section202191122814"></a>

-   集群为1.9.7-r1及以上版本时，才支持此功能。
-   安装时请确保有足够的资源安装本插件。
-   该插件功能仅支持通过**按需计费**方式购买的**虚拟机节点**，不支持“包年/包月“方式购买的节点和裸金属节点。

## 安装插件<a name="section15573161754711"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“ 插件管理“，在“插件市场“页签下，单击**autoscaler**插件下的“安装插件“。
2.  在安装插件页面，选择您要安装插件的集群和插件版本，单击“下一步：规格配置“。
3.  参照[表1](#table1582194517429)配置插件安装参数。

    **表 1**  基本配置

    <a name="table1582194517429"></a>
    <table><thead align="left"><tr id="row178187453428"><th class="cellrowborder" valign="top" width="18.33%" id="mcps1.2.4.1.1"><p id="p14818104534219"><a name="p14818104534219"></a><a name="p14818104534219"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="19.919999999999998%" id="mcps1.2.4.1.2"><p id="p102901135192211"><a name="p102901135192211"></a><a name="p102901135192211"></a>支持的插件版本</p>
    </th>
    <th class="cellrowborder" valign="top" width="61.75000000000001%" id="mcps1.2.4.1.3"><p id="p181814453425"><a name="p181814453425"></a><a name="p181814453425"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row178631475226"><td class="cellrowborder" valign="top" width="18.33%" headers="mcps1.2.4.1.1 "><p id="p386464792210"><a name="p386464792210"></a><a name="p386464792210"></a>插件规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.919999999999998%" headers="mcps1.2.4.1.2 "><p id="p111958230594"><a name="p111958230594"></a><a name="p111958230594"></a>所有版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75000000000001%" headers="mcps1.2.4.1.3 "><p id="p1861133733913"><a name="p1861133733913"></a><a name="p1861133733913"></a>插件部署可选择<span class="uicontrol" id="uicontrol183682402402"><a name="uicontrol183682402402"></a><a name="uicontrol183682402402"></a>“单实例”</span>和<span class="uicontrol" id="uicontrol12789143104015"><a name="uicontrol12789143104015"></a><a name="uicontrol12789143104015"></a>“高可用”</span>两种规格。</p>
    <a name="ul1634319358233"></a><a name="ul1634319358233"></a><ul id="ul1634319358233"><li>单实例：以单实例部署插件。</li><li>高可用：以多实例部署插件，具有高可用能力，需占用更多的计算资源。</li></ul>
    </td>
    </tr>
    <tr id="row921611101579"><td class="cellrowborder" valign="top" width="18.33%" headers="mcps1.2.4.1.1 "><p id="p13217111055715"><a name="p13217111055715"></a><a name="p13217111055715"></a>实例数</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.919999999999998%" headers="mcps1.2.4.1.2 "><p id="p2264124945914"><a name="p2264124945914"></a><a name="p2264124945914"></a>所有版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75000000000001%" headers="mcps1.2.4.1.3 "><p id="p93701640145120"><a name="p93701640145120"></a><a name="p93701640145120"></a>选择上方插件规格后，显示插件中的实例数，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row087474432717"><td class="cellrowborder" valign="top" width="18.33%" headers="mcps1.2.4.1.1 "><p id="p17875104414275"><a name="p17875104414275"></a><a name="p17875104414275"></a>容器</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.919999999999998%" headers="mcps1.2.4.1.2 "><p id="p179441523596"><a name="p179441523596"></a><a name="p179441523596"></a>所有版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75000000000001%" headers="mcps1.2.4.1.3 "><p id="p1437014065110"><a name="p1437014065110"></a><a name="p1437014065110"></a>选择插件规格后，显示插件容器的CPU和内存配额，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row1166495115206"><td class="cellrowborder" valign="top" width="18.33%" headers="mcps1.2.4.1.1 "><p id="p146651551122019"><a name="p146651551122019"></a><a name="p146651551122019"></a>登录方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.919999999999998%" headers="mcps1.2.4.1.2 "><p id="p17242135513412"><a name="p17242135513412"></a><a name="p17242135513412"></a>部分版本无此参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75000000000001%" headers="mcps1.2.4.1.3 "><p id="p1011412155524"><a name="p1011412155524"></a><a name="p1011412155524"></a>为自动扩容工作节点选择登录方式，当前支持<span class="uicontrol" id="uicontrol6266130175014"><a name="uicontrol6266130175014"></a><a name="uicontrol6266130175014"></a>“密码”</span>和<span class="uicontrol" id="uicontrol17468113316505"><a name="uicontrol17468113316505"></a><a name="uicontrol17468113316505"></a>“密钥对”</span>两种方式，您可根据需要进行选择。</p>
    <p id="p14460644195117"><a name="p14460644195117"></a><a name="p14460644195117"></a><strong id="b9415460515"><a name="b9415460515"></a><a name="b9415460515"></a>选择<span class="uicontrol" id="uicontrol1488552616504"><a name="uicontrol1488552616504"></a><a name="uicontrol1488552616504"></a>“密码”</span>方式：</strong></p>
    <a name="ul427315025119"></a><a name="ul427315025119"></a><ul id="ul427315025119"><li>密码：自动扩容工作节点密码。通过该密码登录工作节点执行相关操作，用户名为root。</li><li>确认密码：再次输入自动扩容工作节点密码。</li></ul>
    <p id="p1973095275113"><a name="p1973095275113"></a><a name="p1973095275113"></a><strong id="b189751355125320"><a name="b189751355125320"></a><a name="b189751355125320"></a>选择<span class="uicontrol" id="uicontrol13155165310"><a name="uicontrol13155165310"></a><a name="uicontrol13155165310"></a>“密钥对”</span>方式：</strong></p>
    <p id="p1863961317528"><a name="p1863961317528"></a><a name="p1863961317528"></a>密钥对：密钥对用于远程登录节点时的身份认证，请选择已有密钥对或<a href="https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0014250631.html" target="_blank" rel="noopener noreferrer">创建密钥对</a>。</p>
    </td>
    </tr>
    <tr id="row7820124544210"><td class="cellrowborder" valign="top" width="18.33%" headers="mcps1.2.4.1.1 "><p id="p7820184519425"><a name="p7820184519425"></a><a name="p7820184519425"></a><span class="keyword" id="keyword93481830179"><a name="keyword93481830179"></a><a name="keyword93481830179"></a>自动缩容</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="19.919999999999998%" headers="mcps1.2.4.1.2 "><p id="p4606103215012"><a name="p4606103215012"></a><a name="p4606103215012"></a>所有版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75000000000001%" headers="mcps1.2.4.1.3 "><p id="p15974173353612"><a name="p15974173353612"></a><a name="p15974173353612"></a>默认不开启：将不开启自动缩容，只进行自动扩容。</p>
    <p id="p597311174372"><a name="p597311174372"></a><a name="p597311174372"></a>开启：开启自动缩容，且自建节点和插件扩容所创建的节点均可缩容。</p>
    <a name="ul20302135243"></a><a name="ul20302135243"></a><ul id="ul20302135243"><li>空置时间（min）：当集群节点处于一段时间的空闲状态时，会触发集群缩容操作，删除节点，默认10min。</li><li>百分比：当集群节点资源低于多少百分比时，进行集群缩容扫描（默认0.5，即50%，cpu和mem都要满足的条件下才会缩容）。</li><li>扩容后缩容冷却时间：扩容执行后能再次启动缩容评估的时间间隔，默认10min。</li><li>节点删除后缩容冷却时间：删除节点后能再次启动缩容评估的时间间隔，默认10min。</li><li>缩容失败后缩容冷却时间：缩容失败后能再次启动缩容评估的时间间隔，默认3min。</li><li>空节点缩容最大并发数：默认10。</li><li>不可移除节点的重检查时间：节点被判定不可移除后能再次启动检查的时间间隔，默认5min。</li></ul>
    <div class="note" id="note15581214141911"><a name="note15581214141911"></a><a name="note15581214141911"></a><span class="notetitle"> 说明： </span><div class="notebody"><div class="p" id="p424619478180"><a name="p424619478180"></a><a name="p424619478180"></a>当节点处于以下几种状态时，不可缩容：<a name="ul128441417142719"></a><a name="ul128441417142719"></a><ul id="ul128441417142719"><li>pod设置为PodDisruptionBudget，当不满足条件时，节点不会缩容。</li><li>pod设置本地存储时，节点不会缩容。</li><li>pod由于一些限制，如亲和、反亲和等，无法调度到其他节点，节点不会缩容。</li><li>pod拥有cluster-autoscaler.kubernetes.io/safe-to-evict: 'false'这个annotations时，节点不缩容。</li><li>节点上存在kube-system命名空间下的Pod（除kube-system daemonset创建的Pod）。</li><li>节点上有非controller（deployment/replica set/job/stateful set）创建的Pod。</li></ul>
    </div>
    </div></div>
    </td>
    </tr>
    <tr id="row10588111641417"><td class="cellrowborder" valign="top" width="18.33%" headers="mcps1.2.4.1.1 "><p id="p20580042144816"><a name="p20580042144816"></a><a name="p20580042144816"></a>预置节点池配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.919999999999998%" headers="mcps1.2.4.1.2 "><p id="p369616371304"><a name="p369616371304"></a><a name="p369616371304"></a>部分版本无此参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75000000000001%" headers="mcps1.2.4.1.3 "><p id="p106311133304"><a name="p106311133304"></a><a name="p106311133304"></a>此为默认资源组。集群扩容时，若没有其他可用分组，将使用默认分组的资源规格进行扩容节点。</p>
    <p id="p2087715518406"><a name="p2087715518406"></a><a name="p2087715518406"></a><strong id="b965815211127"><a name="b965815211127"></a><a name="b965815211127"></a>单击<span class="uicontrol" id="uicontrol10496224154110"><a name="uicontrol10496224154110"></a><a name="uicontrol10496224154110"></a>“添加预置节点池配置”</span>进行参数设置：</strong></p>
    <a name="ul378119275614"></a><a name="ul378119275614"></a><ul id="ul378119275614"><li>可用区：选择一个可用区。可用区是指在同一区域下，电力、网络隔离的物理区域。</li><li>操作系统：选择节点对应的操作系统。</li><li>Taints：可选项，默认为空。<div class="p" id="p7853111720153"><a name="p7853111720153"></a><a name="p7853111720153"></a>支持给该节点池扩容出来的节点加Taints来设置反亲和性，每个节点池最多配置10条Taints，每条Taints包含以下3个参数：<a name="ul17274222121015"></a><a name="ul17274222121015"></a><ul id="ul17274222121015"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀。</li><li>Value：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li><li>Effect：只可选NoSchedule，PreferNoSchedule或NoExecute。</li></ul>
    <div class="notice" id="note77443231113"><a name="note77443231113"></a><a name="note77443231113"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><a name="ul104271158181515"></a><a name="ul104271158181515"></a><ul id="ul104271158181515"><li>Taints配置时需要配合Pod的toleration使用，否则可能导致扩容失败或者Pod无法调度到扩容节点。</li><li>配置后无法修改，请您谨慎配置，错误的配置可能会导致扩容失败或pod无法调度。</li></ul>
    </div></div>
    </div>
    </li><li>标签管理：通过为资源添加标签，可以对资源进行自定义标记，实现资源的分类。<div class="note" id="note1873655813232"><a name="note1873655813232"></a><a name="note1873655813232"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1682495163615"><a name="p1682495163615"></a><a name="p1682495163615"></a>您可以在TMS中创建<span class="uicontrol" id="uicontrol1152414253303"><a name="uicontrol1152414253303"></a><a name="uicontrol1152414253303"></a>“预定义标签”</span>，预定义标签对所有支持标签功能的服务资源可见，通过使用预定义标签可以提升标签创建和迁移效率。具体请参见<a href="https://support.huaweicloud.com/usermanual-tms/zh-cn_topic_0144368884.html" target="_blank" rel="noopener noreferrer">创建预定义标签</a>。</p>
    </div></div>
    </li><li>节点规格：节点的CPU配置和内存配置。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

    单击下方的“高级设置“，可以配置更多插件参数：

    **表 2**  高级设置

    <a name="table9850103573510"></a>
    <table><thead align="left"><tr id="row4607144693512"><th class="cellrowborder" valign="top" width="18.528147185281473%" id="mcps1.2.4.1.1"><p id="p39151855123517"><a name="p39151855123517"></a><a name="p39151855123517"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="19.71802819718028%" id="mcps1.2.4.1.2"><p id="p1412212191402"><a name="p1412212191402"></a><a name="p1412212191402"></a>插件版本</p>
    </th>
    <th class="cellrowborder" valign="top" width="61.75382461753826%" id="mcps1.2.4.1.3"><p id="p18915195517356"><a name="p18915195517356"></a><a name="p18915195517356"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row385043515351"><td class="cellrowborder" valign="top" width="18.528147185281473%" headers="mcps1.2.4.1.1 "><p id="p129911124203017"><a name="p129911124203017"></a><a name="p129911124203017"></a>节点总数</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.71802819718028%" headers="mcps1.2.4.1.2 "><p id="p436632542"><a name="p436632542"></a><a name="p436632542"></a>所有版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75382461753826%" headers="mcps1.2.4.1.3 "><p id="p29911924143017"><a name="p29911924143017"></a><a name="p29911924143017"></a>可扩容的最大节点总数。</p>
    </td>
    </tr>
    <tr id="row1785163517352"><td class="cellrowborder" valign="top" width="18.528147185281473%" headers="mcps1.2.4.1.1 "><p id="p09919249305"><a name="p09919249305"></a><a name="p09919249305"></a>cpu总数（核）</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.71802819718028%" headers="mcps1.2.4.1.2 "><p id="p16496194815118"><a name="p16496194815118"></a><a name="p16496194815118"></a>所有版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75382461753826%" headers="mcps1.2.4.1.3 "><p id="p10991724113018"><a name="p10991724113018"></a><a name="p10991724113018"></a>可扩容的最大cpu总数（核）。</p>
    </td>
    </tr>
    <tr id="row208511335113518"><td class="cellrowborder" valign="top" width="18.528147185281473%" headers="mcps1.2.4.1.1 "><p id="p7991152414302"><a name="p7991152414302"></a><a name="p7991152414302"></a>内存总数（GB）</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.71802819718028%" headers="mcps1.2.4.1.2 "><p id="p5197195215113"><a name="p5197195215113"></a><a name="p5197195215113"></a>所有版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75382461753826%" headers="mcps1.2.4.1.3 "><p id="p199916247301"><a name="p199916247301"></a><a name="p199916247301"></a>可扩容的最大内存总数（GB）。</p>
    </td>
    </tr>
    <tr id="row12626156103612"><td class="cellrowborder" valign="top" width="18.528147185281473%" headers="mcps1.2.4.1.1 "><p id="p1627256173617"><a name="p1627256173617"></a><a name="p1627256173617"></a>自动扩容</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.71802819718028%" headers="mcps1.2.4.1.2 "><p id="p5194172018453"><a name="p5194172018453"></a><a name="p5194172018453"></a>部分版本无此参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75382461753826%" headers="mcps1.2.4.1.3 "><p id="p96272569366"><a name="p96272569366"></a><a name="p96272569366"></a><strong id="b83511403568"><a name="b83511403568"></a><a name="b83511403568"></a>未调度实例扩容：</strong>默认选中。</p>
    <p id="p3215717541"><a name="p3215717541"></a><a name="p3215717541"></a><strong id="b411810475619"><a name="b411810475619"></a><a name="b411810475619"></a>启用集群使用率扩容：</strong>可选，扩容能力增强。</p>
    <a name="ul658616239553"></a><a name="ul658616239553"></a><ul id="ul658616239553"><li>cpu扩容使用率：当节点池CPU达到所设置的使用上限，将扩容当前预置节点池的节点数。</li><li>内存扩容使用率：当节点池内存达到所设置的使用上限，将扩容当前预置节点池的节点数。</li></ul>
    </td>
    </tr>
    <tr id="row1242052163614"><td class="cellrowborder" valign="top" width="18.528147185281473%" headers="mcps1.2.4.1.1 "><p id="p162421452153620"><a name="p162421452153620"></a><a name="p162421452153620"></a>磁盘</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.71802819718028%" headers="mcps1.2.4.1.2 "><p id="p9813132834516"><a name="p9813132834516"></a><a name="p9813132834516"></a>部分版本无此参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75382461753826%" headers="mcps1.2.4.1.3 "><div class="p" id="p16199190205513"><a name="p16199190205513"></a><a name="p16199190205513"></a>系统盘和数据盘：设置节点磁盘空间。<a name="ul1220313142710"></a><a name="ul1220313142710"></a><ul id="ul1220313142710"><li>系统盘：规格为[40,1024]GB，用户可以配置，缺省值为40GB。</li><li>数据盘：规格为[100,32768]GB，用户可以配置，缺省值为100GB。<p id="p149151439185614"><a name="p149151439185614"></a><a name="p149151439185614"></a>勾选<span class="uicontrol" id="uicontrol5468812165717"><a name="uicontrol5468812165717"></a><a name="uicontrol5468812165717"></a>“资源分配自定义”</span>后，您可以对数据盘中的Docker和Kubelet资源占比进行自定义设置。</p>
    <div class="notice" id="note1420420141375"><a name="note1420420141375"></a><a name="note1420420141375"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><a name="ul6609174914587"></a><a name="ul6609174914587"></a><ul id="ul6609174914587"><li>磁盘使用direct-lvm模式，移除将使用loop-lvm模式，有影响系统稳定性的风险。</li><li>Docker资源包含Docker镜像数据以及镜像元数据，Kubelet资源包含Pod配置文件、密钥以及临时存储EmptyDir等挂载数据。</li></ul>
    </div></div>
    </li><li>数据盘：单击<span class="uicontrol" id="uicontrol14989121667"><a name="uicontrol14989121667"></a><a name="uicontrol14989121667"></a>“新增数据盘”</span>，您可以增加一块数据盘。</li></ul>
    </div>
    <p id="p220415148710"><a name="p220415148710"></a><a name="p220415148710"></a>系统盘和数据盘均可提供以下性能规格的云硬盘：</p>
    <a name="ul82049141772"></a><a name="ul82049141772"></a><ul id="ul82049141772"><li>普通IO：是指由SATA存储提供资源的磁盘类型。提供可靠的块存储，单个云硬盘的最大IOPS可达到1000，可运行关键应用程序。</li><li>高IO：是指由SAS存储提供资源的磁盘类型。提供可达到3000的高IO和低至1 ms的读写延时，支持NoSQL/关系型数据库，数据仓库，文件系统等应用。</li><li>超高IO：是指由SSD存储提供资源的磁盘类型。提供可达到20000的超高IO和低至1 ms超低读写时延，支持NoSQL/关系型数据库，数据仓库等应用。</li></ul>
    </td>
    </tr>
    <tr id="row144889497367"><td class="cellrowborder" valign="top" width="18.528147185281473%" headers="mcps1.2.4.1.1 "><p id="p94899496360"><a name="p94899496360"></a><a name="p94899496360"></a>命令行注入</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.71802819718028%" headers="mcps1.2.4.1.2 "><p id="p834518108397"><a name="p834518108397"></a><a name="p834518108397"></a>部分版本无此参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.75382461753826%" headers="mcps1.2.4.1.3 "><p id="p124899494362"><a name="p124899494362"></a><a name="p124899494362"></a>请输入脚本命令。</p>
    <div class="note" id="note15181132114611"><a name="note15181132114611"></a><a name="note15181132114611"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul5782152581219"></a><a name="ul5782152581219"></a><ul id="ul5782152581219"><li>脚本命令大小限制：0~1000字符。</li><li>命令行注入示例及使用方法，请参见<a href="https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0032380449.html" target="_blank" rel="noopener noreferrer">用户数据注入</a>。</li></ul>
    </div></div>
    </td>
    </tr>
    </tbody>
    </table>

4.  配置完成后，单击“安装”。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section3578191413712"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击autoscaler下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作；
    >-   若升级按钮可单击，则单击升级按钮即可升级autoscaler插件。
    >-   升级autoscaler插件时，会替换原先节点上的旧版本的autoscaler插件，安装最新版本的autoscaler插件以实现功能的快速升级。

2.  在弹出的窗口中，配置参数后，升级该插件。配置参数可参考[安装插件](#section15573161754711)中的参数说明。

## 卸载插件<a name="section610455514114"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“ 插件管理“，在“插件实例“页签下，选择对应的集群，单击**autoscaler**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

