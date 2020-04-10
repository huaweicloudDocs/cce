# 购买GPU集群<a name="cce_01_0122"></a>

GPU集群是指使用GPU节点部署的集群，支持主流AI计算框架、支持多容器共享GPU资源。

自从1.8版本开始，Kubernetes已经明确将通过统一的[设备插件方式](https://kubernetes.io/docs/concepts/cluster-administration/device-plugins/)支持像Nvidia GPU，InfiniBand，FPGA等硬件加速设备，而社区的GPU方案已在1.10全面弃用，并在1.11版本彻底从主干代码移除。

若您需要通过华为云GPU容器集群运行机器学习、科学计算、AI推理等高运算密度任务，无需安装nvidia driver，就能实现一键部署和弹性扩缩容等功能。

## 使用限制<a name="section15947165882217"></a>

-   每个账号默认可以创建的云资源有一定的配额，如果超过配额创建集群会失败。请在创建集群前确认您的配额，查看配额请参见[关于配额](https://support.huaweicloud.com/usermanual-iaas/zh-cn_topic_0040259342.html)。如果您需要提高您的配额，请[提交工单](https://console.huaweicloud.com/console/#/quota)申请。
-   Kubernetes 1.9版本的集群，GPU组件默认强制安装；Kubernetes 1.11及以上版本的集群，GPU能力以插件的方式外接提供，需要您在“插件管理“中安装[GPU-beta插件。](gpu-beta.md)
-   ECS 实例使用限制：CUDA需要您自行在镜像中安装。

## 购买GPU集群<a name="section9343750182712"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中单击“资源管理 \> 集群管理“，进入集群列表页面。
2.  单击页面右上角“GPU集群“下方的“购买“按钮，进入购买集群页面。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >由于GPU集群与混合集群的Master节点一致，区别在于Node节点使用GPU类型的ECS，因此购买GPU集群默认进入“购买混合集群“页面。  

    **图 1**  购买GPU集群<a name="fig18961163112247"></a>  
    ![](figures/购买GPU集群.png "购买GPU集群")

3.  参照[表1](#cce_01_0028_table8638121213265)设置服务选型参数，其中带“\*”的参数为必填参数。

    **表 1**  创建集群参数配置

    <a name="cce_01_0028_table8638121213265"></a>
    <table><thead align="left"><tr id="cce_01_0028_row10638181262612"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="cce_01_0028_p1063821214265"><a name="cce_01_0028_p1063821214265"></a><a name="cce_01_0028_p1063821214265"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="cce_01_0028_p1638181232617"><a name="cce_01_0028_p1638181232617"></a><a name="cce_01_0028_p1638181232617"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="cce_01_0028_row1922964644615"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p9231104613468"><a name="cce_01_0028_p9231104613468"></a><a name="cce_01_0028_p9231104613468"></a>* 计费模式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><a name="cce_01_0028_ul463941414445"></a><a name="cce_01_0028_ul463941414445"></a><ul id="cce_01_0028_ul463941414445"><li><span class="keyword" id="cce_01_0028_keyword66602077459"><a name="cce_01_0028_keyword66602077459"></a><a name="cce_01_0028_keyword66602077459"></a>包年/包月</span>：预付费模式，按订单的购买周期计费，适用于可预估资源使用周期的场景，价格比按需计费模式更优惠。包年/包月集群创建后不能删除，如需停止使用，请到<a href="https://account.huaweicloud.com/usercenter/#/userindex/retreatManagement" target="_blank" rel="noopener noreferrer">费用中心</a>执行退订操作。</li><li><span class="keyword" id="cce_01_0028_keyword44309542597"><a name="cce_01_0028_keyword44309542597"></a><a name="cce_01_0028_keyword44309542597"></a>按需计费</span>：后付费模式，按资源的实际使用时长计费，可以随时开通/删除资源。</li></ul>
    <p id="cce_01_0028_p0624127506"><a name="cce_01_0028_p0624127506"></a><a name="cce_01_0028_p0624127506"></a>本章以<span class="uicontrol" id="cce_01_0028_uicontrol8978171712013"><a name="cce_01_0028_uicontrol8978171712013"></a><a name="cce_01_0028_uicontrol8978171712013"></a>“按需计费”</span>类型为例进行讲解。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row42961494311"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p812874116011"><a name="cce_01_0028_p812874116011"></a><a name="cce_01_0028_p812874116011"></a>* 区域</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p161283411302"><a name="cce_01_0028_p161283411302"></a><a name="cce_01_0028_p161283411302"></a>请就近选择靠近您业务的区域，可减少网络时延，提高访问速度；不同区域的云服务产品之间内网互不相通。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row12321131519262"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p14322181522614"><a name="cce_01_0028_p14322181522614"></a><a name="cce_01_0028_p14322181522614"></a>* 企业项目</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p1363744211114"><a name="cce_01_0028_p1363744211114"></a><a name="cce_01_0028_p1363744211114"></a>该参数仅对开通企业项目的企业客户账号显示。选择某企业项目（如：default）后，集群、集群下节点、集群安全组、节点安全组和自动创建的节点EIP将创建到所选企业项目下。</p>
    <p id="cce_01_0028_p73221815122618"><a name="cce_01_0028_p73221815122618"></a><a name="cce_01_0028_p73221815122618"></a>企业项目是一种云资源管理方式，企业项目管理服务提供统一的云资源按项目管理，以及项目内的资源管理、成员管理。了解更多企业项目相关信息，请查看<a href="https://support.huaweicloud.com/usermanual-em/zh-cn_topic_0123692049.html" target="_blank" rel="noopener noreferrer">企业管理</a>。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row1063812126263"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p15639812122620"><a name="cce_01_0028_p15639812122620"></a><a name="cce_01_0028_p15639812122620"></a>* 集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p26391512172614"><a name="cce_01_0028_p26391512172614"></a><a name="cce_01_0028_p26391512172614"></a>新建集群的名称，创建后不可修改。</p>
    <p id="cce_01_0028_p1520317181911"><a name="cce_01_0028_p1520317181911"></a><a name="cce_01_0028_p1520317181911"></a>集群名称长度范围为4-128个字符，以小写字母开头，由小写字母、数字、中划线（-）组成，且不能以中划线（-）结尾。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row6649879161231"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p1769363161231"><a name="cce_01_0028_p1769363161231"></a><a name="cce_01_0028_p1769363161231"></a>* 版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p9100682161231"><a name="cce_01_0028_p9100682161231"></a><a name="cce_01_0028_p9100682161231"></a>Kubernetes社区基线版本，建议选择最新的版本。版本升级请参见<a href="集群版本升级说明.md">集群版本升级说明</a>。</p>
    <p id="cce_01_0028_p1022520483"><a name="cce_01_0028_p1022520483"></a><a name="cce_01_0028_p1022520483"></a>若有<strong id="cce_01_0028_b20728225518"><a name="cce_01_0028_b20728225518"></a><a name="cce_01_0028_b20728225518"></a>Beta</strong>版本时，您可以选择试用，但不建议您将该版本用于商用场景。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row572593234714"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p14725432104718"><a name="cce_01_0028_p14725432104718"></a><a name="cce_01_0028_p14725432104718"></a>* 集群管理规模</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p14899102111550"><a name="cce_01_0028_p14899102111550"></a><a name="cce_01_0028_p14899102111550"></a>当前集群可以管理的最大节点规模（<strong id="cce_01_0028_b19899112165516"><a name="cce_01_0028_b19899112165516"></a><a name="cce_01_0028_b19899112165516"></a>Node节点</strong>），请根据业务需求选择。</p>
    <p id="cce_01_0028_p192696516218"><a name="cce_01_0028_p192696516218"></a><a name="cce_01_0028_p192696516218"></a>若选择<span class="uicontrol" id="cce_01_0028_uicontrol35596531909"><a name="cce_01_0028_uicontrol35596531909"></a><a name="cce_01_0028_uicontrol35596531909"></a>“50节点”</span>，表示当前集群的Master最多可管理50个Node节点。由于不同管理规模的Master节点规格不同，因此配置费用会有差异。集群管理规模在集群创建后不支持调整，请在创建时慎重选择。</p>
    <div class="p" id="cce_01_0028_p102308301014"><a name="cce_01_0028_p102308301014"></a><a name="cce_01_0028_p102308301014"></a>任何一个集群中均包含<span class="uicontrol" id="cce_01_0028_uicontrol144772569118"><a name="cce_01_0028_uicontrol144772569118"></a><a name="cce_01_0028_uicontrol144772569118"></a>“Master节点”</span>和<span class="uicontrol" id="cce_01_0028_uicontrol1458610581110"><a name="cce_01_0028_uicontrol1458610581110"></a><a name="cce_01_0028_uicontrol1458610581110"></a>“Node节点”</span>，每一个节点对应一台云服务器。<a name="cce_01_0028_ul1045015327013"></a><a name="cce_01_0028_ul1045015327013"></a><ul id="cce_01_0028_ul1045015327013"><li>Master节点：集群的控制节点，在创建集群时会自动创建控制节点，负责整个集群的管理和调度。</li><li>Node节点：用户购买或纳管的节点是集群的Node节点，即工作负载节点。Node节点由管理节点分配，当某个Node节点宕机时，管理节点会将工作负载转移到其他Node节点上。</li></ul>
    </div>
    </td>
    </tr>
    <tr id="cce_01_0028_row680585841419"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p11786989141"><a name="cce_01_0028_p11786989141"></a><a name="cce_01_0028_p11786989141"></a>* 高可用</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p17736528151015"><a name="cce_01_0028_p17736528151015"></a><a name="cce_01_0028_p17736528151015"></a>是：开启高可用模式，集群将创建多个控制节点，在单个控制节点发生故障时集群可以继续使用，不影响业务功能。</p>
    <p id="cce_01_0028_p1141462310555"><a name="cce_01_0028_p1141462310555"></a><a name="cce_01_0028_p1141462310555"></a>否：非高可用集群不保证SLA，不适用于商用场景。</p>
    <div class="note" id="cce_01_0028_note1592591594019"><a name="cce_01_0028_note1592591594019"></a><a name="cce_01_0028_note1592591594019"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="cce_01_0028_ul1464620467243"></a><a name="cce_01_0028_ul1464620467243"></a><ul id="cce_01_0028_ul1464620467243"><li>在商用场景中，为提高集群容灾能力，建议您选择<span class="uicontrol" id="cce_01_0028_uicontrol10911327142811"><a name="cce_01_0028_uicontrol10911327142811"></a><a name="cce_01_0028_uicontrol10911327142811"></a>“高可用”</span>模式集群。</li><li>非高可用集群不支持升级为高可用集群，控制节点故障将影响运行业务，只能通过重新创建集群才能调整为高可用集群，请谨慎选择。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="cce_01_0028_row1763991215268"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p15639181282617"><a name="cce_01_0028_p15639181282617"></a><a name="cce_01_0028_p15639181282617"></a>* 虚拟私有云</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p20558173114298"><a name="cce_01_0028_p20558173114298"></a><a name="cce_01_0028_p20558173114298"></a>新建集群所在的虚拟私有云。</p>
    <p id="cce_01_0028_p116393128265"><a name="cce_01_0028_p116393128265"></a><a name="cce_01_0028_p116393128265"></a>虚拟私有云是通过逻辑方式进行网络隔离，提供安全、隔离的网络环境。</p>
    <p id="cce_01_0028_p1063941211266"><a name="cce_01_0028_p1063941211266"></a><a name="cce_01_0028_p1063941211266"></a>若没有可选虚拟私有云，单击<span class="uicontrol" id="cce_01_0028_uicontrol162261618154315"><a name="cce_01_0028_uicontrol162261618154315"></a><a name="cce_01_0028_uicontrol162261618154315"></a>“<span id="cce_01_0028_text112261418174320"><a name="cce_01_0028_text112261418174320"></a><a name="cce_01_0028_text112261418174320"></a>创建虚拟</span>私有云”</span>进行创建，完成创建后点击刷新按钮。操作步骤请参见<a href="https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013935842.html" target="_blank" rel="noopener noreferrer">创建虚拟私有云和子网</a>。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row15639412132615"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p36391812172618"><a name="cce_01_0028_p36391812172618"></a><a name="cce_01_0028_p36391812172618"></a>* 所在子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p924510014306"><a name="cce_01_0028_p924510014306"></a><a name="cce_01_0028_p924510014306"></a>节点虚拟机运行的子网环境。</p>
    <p id="cce_01_0028_p1108371202"><a name="cce_01_0028_p1108371202"></a><a name="cce_01_0028_p1108371202"></a>通过子网提供与其他网络隔离的、可以独享的网络资源，以提高网络安全。虚拟私有云、子网、集群的关系请参见<a href="集群概述.md">集群概述</a>。</p>
    <p id="cce_01_0028_p1369519572172"><a name="cce_01_0028_p1369519572172"></a><a name="cce_01_0028_p1369519572172"></a><strong id="cce_01_0028_b13695957131719"><a name="cce_01_0028_b13695957131719"></a><a name="cce_01_0028_b13695957131719"></a>请确保子网下的DNS服务器可以解析OBS服务域名，否则无法创建节点。</strong></p>
    <p id="cce_01_0028_p41882822012"><a name="cce_01_0028_p41882822012"></a><a name="cce_01_0028_p41882822012"></a><strong id="cce_01_0028_b9136183821711"><a name="cce_01_0028_b9136183821711"></a><a name="cce_01_0028_b9136183821711"></a>集群创建后子网无法修改，请谨慎选择。</strong></p>
    </td>
    </tr>
    <tr id="cce_01_0028_row115671413307"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p16567134113303"><a name="cce_01_0028_p16567134113303"></a><a name="cce_01_0028_p16567134113303"></a>IPv6双栈</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p36131511317"><a name="cce_01_0028_p36131511317"></a><a name="cce_01_0028_p36131511317"></a>默认不开启。<span id="cce_01_0028_ph5829194013718"><a name="cce_01_0028_ph5829194013718"></a><a name="cce_01_0028_ph5829194013718"></a><strong id="cce_01_0028_b3710124814376"><a name="cce_01_0028_b3710124814376"></a><a name="cce_01_0028_b3710124814376"></a>该功能仅在1.15及以上版本的混合集群下显示。</strong></span></p>
    <p id="cce_01_0028_p1656714414305"><a name="cce_01_0028_p1656714414305"></a><a name="cce_01_0028_p1656714414305"></a>开启IPv6：开启后将自动创建IPv6地址的容器网段与服务网段，支持通过IPv6地址段访问集群资源，包括节点，工作负载等。具体请参见<a href="https://support.huaweicloud.com/cce_faq/cce_faq_00222.html" target="_blank" rel="noopener noreferrer">如何通过CCE搭建IPv4/IPv6双栈集群？</a>。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row482955911270"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p9831659192715"><a name="cce_01_0028_p9831659192715"></a><a name="cce_01_0028_p9831659192715"></a>* 网络模型</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p135701052194711"><a name="cce_01_0028_p135701052194711"></a><a name="cce_01_0028_p135701052194711"></a>集群创建成功后，网络模型不可更改，请谨慎选择。</p>
    <p id="cce_01_0028_p0724144517209"><a name="cce_01_0028_p0724144517209"></a><a name="cce_01_0028_p0724144517209"></a><strong id="cce_01_0028_b952205617204"><a name="cce_01_0028_b952205617204"></a><a name="cce_01_0028_b952205617204"></a>容器隧道网络</strong></p>
    <p id="cce_01_0028_p9295195416117"><a name="cce_01_0028_p9295195416117"></a><a name="cce_01_0028_p9295195416117"></a>容器隧道网络下只能添加同一类型的节点，即全部为虚拟机节点或全部为裸金属节点。</p>
    <a name="cce_01_0028_ul1221141842110"></a><a name="cce_01_0028_ul1221141842110"></a><ul id="cce_01_0028_ul1221141842110"><li>基于底层VPC网络，另构建了独立的VXLAN隧道化容器网络，适用于一般场景。</li><li>VXLAN是将以太网报文封装成UDP报文进行隧道传输。容器网络是承载于VPC网络之上的Overlay网络平面，具有付出少量隧道封装性能损耗，获得了通用性强、互通性强、高级特性支持全面（例如Network Policy网络隔离）的优势，可以满足大多数应用需求。</li></ul>
    <p id="cce_01_0028_p6806448162015"><a name="cce_01_0028_p6806448162015"></a><a name="cce_01_0028_p6806448162015"></a><strong id="cce_01_0028_b75401805214"><a name="cce_01_0028_b75401805214"></a><a name="cce_01_0028_b75401805214"></a>VPC网络</strong></p>
    <p id="cce_01_0028_p16547203413121"><a name="cce_01_0028_p16547203413121"></a><a name="cce_01_0028_p16547203413121"></a>VPC网络模式下每个节点占用一条<a href="https://support.huaweicloud.com/usermanual-vpc/route_0002.html" target="_blank" rel="noopener noreferrer">VPC路由规则</a>，Console界面中可显示当前局点支持的VPC路由规则条数，以及每个节点可供分配的容器IP个数（即可创建的Pod实例数目上限）。</p>
    <a name="cce_01_0028_ul68480277225"></a><a name="cce_01_0028_ul68480277225"></a><ul id="cce_01_0028_ul68480277225"><li>采用VPC路由方式与底层网络深度整合，适用于高性能场景，节点数量受限于虚拟私有云VPC的路由配额。</li><li>VPC网络集群下的每个节点将会被分配固定大小的IP地址段，由于没有隧道封装的消耗，容器网络性能相对于容器隧道网络有一定优势。VPC网络集群由于VPC路由中配置有容器网段与节点IP的路由，可以支持集群外直接访问容器实例等特殊场景。</li></ul>
    </td>
    </tr>
    <tr id="cce_01_0028_row64648564171234"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p2042307171234"><a name="cce_01_0028_p2042307171234"></a><a name="cce_01_0028_p2042307171234"></a>* 容器网段</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p31209167171234"><a name="cce_01_0028_p31209167171234"></a><a name="cce_01_0028_p31209167171234"></a>请根据业务需求选择容器网段，确定容器网段后，容器实例将在规划的网段内分配IP。</p>
    <a name="cce_01_0028_ul1423120351449"></a><a name="cce_01_0028_ul1423120351449"></a><ul id="cce_01_0028_ul1423120351449"><li>未勾选“自动选择”：请手动选择网段。若与子网网段有冲突时将有红色文字提示，请重新选择。建议使用网段：10.0.0.0/12~19，172.16.0.0/16~19，192.168.0.0/16~19。<p id="cce_01_0028_p158661543014"><a name="cce_01_0028_p158661543014"></a><a name="cce_01_0028_p158661543014"></a><strong id="cce_01_0028_b02629514118"><a name="cce_01_0028_b02629514118"></a><a name="cce_01_0028_b02629514118"></a>不同集群使用相同的容器网段，会导致容器IP冲突，应用访问异常。</strong></p>
    </li><li>勾选“自动选择”：系统将自动分配与子网网段无冲突的网段。</li></ul>
    <p id="cce_01_0028_p873618346117"><a name="cce_01_0028_p873618346117"></a><a name="cce_01_0028_p873618346117"></a>容器网段要设置合理的掩码，掩码决定集群内可用节点数量。集群中容器网段掩码设置不合适，会导致集群实际可用的节点较少。设置掩码后，选项下方会有当前网段最多支持的实例估算值，请作参考。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row6775143217241"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p677653218246"><a name="cce_01_0028_p677653218246"></a><a name="cce_01_0028_p677653218246"></a>* 服务网段</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p977633218244"><a name="cce_01_0028_p977633218244"></a><a name="cce_01_0028_p977633218244"></a>服务网段为kubernetes service ip网段。</p>
    <a name="cce_01_0028_ul13104152611581"></a><a name="cce_01_0028_ul13104152611581"></a><ul id="cce_01_0028_ul13104152611581"><li>使用默认网段：默认设置为10.247.0.0/16网段。</li><li>手动设置网段：请根据业务需求设置合理的网段和掩码，掩码决定集群内可用service ip数量。</li></ul>
    </td>
    </tr>
    <tr id="cce_01_0028_row773511171567"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p37371717105616"><a name="cce_01_0028_p37371717105616"></a><a name="cce_01_0028_p37371717105616"></a>鉴权方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p2017413473382"><a name="cce_01_0028_p2017413473382"></a><a name="cce_01_0028_p2017413473382"></a><span class="uicontrol" id="cce_01_0028_uicontrol217464712384"><a name="cce_01_0028_uicontrol217464712384"></a><a name="cce_01_0028_uicontrol217464712384"></a>“RBAC”</span>默认勾选，不可取消。</p>
    <p id="cce_01_0028_p16141515161117"><a name="cce_01_0028_p16141515161117"></a><a name="cce_01_0028_p16141515161117"></a>开启RBAC能力后，设置了细粒度权限的IAM用户使用集群下资源将受到权限控制。详细请参见<a href="设置命名空间权限.md">设置命名空间权限</a>。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row1610917221609"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p6655100911"><a name="cce_01_0028_p6655100911"></a><a name="cce_01_0028_p6655100911"></a>认证方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p933784218111"><a name="cce_01_0028_p933784218111"></a><a name="cce_01_0028_p933784218111"></a>认证机制主要用于对集群下的资源做权限控制。例如A用户只能对某个命名空间下的应用有读写权限，B用户对集群下的资源只有读权限等等。角色权限控制的操作请参见<a href="集群管理权限控制.md">集群管理权限控制</a>。</p>
    <a name="cce_01_0028_ul208851410646"></a><a name="cce_01_0028_ul208851410646"></a><ul id="cce_01_0028_ul208851410646"><li>默认状态下不选定<span class="uicontrol" id="cce_01_0028_uicontrol1371105874614"><a name="cce_01_0028_uicontrol1371105874614"></a><a name="cce_01_0028_uicontrol1371105874614"></a>“认证能力增强”</span>，此时默认开启X509认证模式，X.509是一种非常通用的证书格式。</li><li>若需要对集群进行权限控制，请勾选“认证能力增强”，选择“认证代理”。<p id="cce_01_0028_p129632614510"><a name="cce_01_0028_p129632614510"></a><a name="cce_01_0028_p129632614510"></a>单击“CA根证书”后的“上传文件”，上传符合规范且合法的证书，并<strong id="cce_01_0028_b2356470185"><a name="cce_01_0028_b2356470185"></a><a name="cce_01_0028_b2356470185"></a>勾选“我已确认上传的证书合法”</strong>。</p>
    <p id="cce_01_0028_p36719411534"><a name="cce_01_0028_p36719411534"></a><a name="cce_01_0028_p36719411534"></a>证书若不合法，集群将无法创建成功。请上传小于1MB的文件，上传格式支持.crt或.cer格式。</p>
    </li></ul>
    </td>
    </tr>
    <tr id="cce_01_0028_row463941216264"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p2063961212268"><a name="cce_01_0028_p2063961212268"></a><a name="cce_01_0028_p2063961212268"></a>集群描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p664014125268"><a name="cce_01_0028_p664014125268"></a><a name="cce_01_0028_p664014125268"></a>选填，请输入新建容器集群相应的描述信息。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row96582533813"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p2285145420345"><a name="cce_01_0028_p2285145420345"></a><a name="cce_01_0028_p2285145420345"></a>高级设置</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p1911106205716"><a name="cce_01_0028_p1911106205716"></a><a name="cce_01_0028_p1911106205716"></a>单击<span class="uicontrol" id="cce_01_0028_uicontrol151802714513"><a name="cce_01_0028_uicontrol151802714513"></a><a name="cce_01_0028_uicontrol151802714513"></a>“高级设置”</span>后展开详细项目，支持的功能如下（当前可用区中不支持的功能将隐藏）：</p>
    <p id="cce_01_0028_p113568261434"><a name="cce_01_0028_p113568261434"></a><a name="cce_01_0028_p113568261434"></a><strong id="cce_01_0028_b193562261439"><a name="cce_01_0028_b193562261439"></a><a name="cce_01_0028_b193562261439"></a>服务转发模式：</strong></p>
    <a name="cce_01_0028_ul1435618265318"></a><a name="cce_01_0028_ul1435618265318"></a><ul id="cce_01_0028_ul1435618265318"><li>iptables：社区传统的kube-proxy模式，完全以iptables规则的方式来实现service负载均衡。该方式最主要的问题是在服务多的时候产生太多的iptables规则，非增量式更新会引入一定的时延，大规模情况下有明显的性能问题。</li><li>ipvs：由华为主导开发并在社区获得广泛支持的kube-proxy模式，采用增量式更新，吞吐更高，速度更快，并可以保证service更新期间连接保持不断开，适用于大规模场景。<p id="cce_01_0028_p52781357485"><a name="cce_01_0028_p52781357485"></a><a name="cce_01_0028_p52781357485"></a>ipvs模式下，ingress和service使用相同的ELB实例时，无法在集群内的节点和容器中访问ingress。</p>
    </li></ul>
    <div class="note" id="cce_01_0028_note551324732117"><a name="cce_01_0028_note551324732117"></a><a name="cce_01_0028_note551324732117"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="cce_01_0028_ul2513447132113"></a><a name="cce_01_0028_ul2513447132113"></a><ul id="cce_01_0028_ul2513447132113"><li>ipvs为大型集群提供了更好的可扩展性和性能。</li><li>ipvs支持比iptables更复杂的负载平衡算法（最小负载，最少连接，位置，加权等）。</li><li>ipvs支持服务器健康检查和连接重试等。</li></ul>
    </div></div>
    <p id="cce_01_0028_p1530611329220"><a name="cce_01_0028_p1530611329220"></a><a name="cce_01_0028_p1530611329220"></a><strong id="cce_01_0028_b203061532132217"><a name="cce_01_0028_b203061532132217"></a><a name="cce_01_0028_b203061532132217"></a>资源标签：</strong></p>
    <p id="cce_01_0028_p153521813102212"><a name="cce_01_0028_p153521813102212"></a><a name="cce_01_0028_p153521813102212"></a>通过为资源添加标签，可以对资源进行自定义标记，实现资源的分类。</p>
    <p id="cce_01_0028_p1746516915228"><a name="cce_01_0028_p1746516915228"></a><a name="cce_01_0028_p1746516915228"></a>您可以在TMS中创建<span class="uicontrol" id="cce_01_0028_uicontrol9465129142213"><a name="cce_01_0028_uicontrol9465129142213"></a><a name="cce_01_0028_uicontrol9465129142213"></a>“预定义标签”</span>，预定义标签对所有支持标签功能的服务资源可见，通过使用预定义标签可以提升标签创建和迁移效率。具体请参见<a href="https://support.huaweicloud.com/usermanual-tms/zh-cn_topic_0144368884.html" target="_blank" rel="noopener noreferrer">创建预定义标签</a>。</p>
    <p id="cce_01_0028_p2448659163311"><a name="cce_01_0028_p2448659163311"></a><a name="cce_01_0028_p2448659163311"></a><strong id="cce_01_0028_b15868154114358"><a name="cce_01_0028_b15868154114358"></a><a name="cce_01_0028_b15868154114358"></a>CPU管理策略：</strong></p>
    <p id="cce_01_0028_p658055813489"><a name="cce_01_0028_p658055813489"></a><a name="cce_01_0028_p658055813489"></a>该参数仅在v1.13.10-r0及以上版本的集群中显示。</p>
    <a name="cce_01_0028_ul14813182993518"></a><a name="cce_01_0028_ul14813182993518"></a><ul id="cce_01_0028_ul14813182993518"><li>开启：支持给工作负载实例配置CPU独占，适用于对CPU缓存和调度延迟敏感的工作负载。</li><li>关闭：关闭工作负载实例独占CPU核的功能，优点是CPU共享池的可分配核数较多。</li></ul>
    <p id="cce_01_0028_p1363818291491"><a name="cce_01_0028_p1363818291491"></a><a name="cce_01_0028_p1363818291491"></a>更多CPU管理策略内容请参见<a href="https://kubernetes.io/blog/2018/07/24/feature-highlight-cpu-manager/" target="_blank" rel="noopener noreferrer">Feature Highlight: CPU Manager</a>或<a href="https://bbs.huaweicloud.com/forum/thread-28901-1-1.html" target="_blank" rel="noopener noreferrer">深入理解 Kubernetes CPU Mangager</a>。</p>
    <p id="cce_01_0028_p0904172120273"><a name="cce_01_0028_p0904172120273"></a><a name="cce_01_0028_p0904172120273"></a><strong id="cce_01_0028_b15232314276"><a name="cce_01_0028_b15232314276"></a><a name="cce_01_0028_b15232314276"></a>控制节点可用区：</strong></p>
    <p id="cce_01_0028_p187781327216"><a name="cce_01_0028_p187781327216"></a><a name="cce_01_0028_p187781327216"></a>选择控制节点分布在哪个可用区，高可用集群可选择多个可用区，非高可用集群只能选择一个可用区。</p>
    <div class="fignone" id="cce_01_0028_fig19782959108"><a name="cce_01_0028_fig19782959108"></a><a name="cce_01_0028_fig19782959108"></a><span class="figcap"><b>图1 </b>控制节点可用区选择</span><br><a name="cce_01_0028_image0463648706"></a><a name="cce_01_0028_image0463648706"></a><span><img id="cce_01_0028_image0463648706" src="figures/控制节点可用区选择.png" width="413.63" height="53.418253"></span></div>
    <p id="cce_01_0028_p44694192714"><a name="cce_01_0028_p44694192714"></a><a name="cce_01_0028_p44694192714"></a>多可用区模式支持集群管理面多可用区容灾，但是对于集群性能有所损耗。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row76532194177"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p79871037171719"><a name="cce_01_0028_p79871037171719"></a><a name="cce_01_0028_p79871037171719"></a>* 购买时长</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p1991143711174"><a name="cce_01_0028_p1991143711174"></a><a name="cce_01_0028_p1991143711174"></a>若选择创建<span class="uicontrol" id="cce_01_0028_uicontrol10197720111410"><a name="cce_01_0028_uicontrol10197720111410"></a><a name="cce_01_0028_uicontrol10197720111410"></a>“包年/包月”</span>的集群，请设置购买时长。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“下一步：创建节点“，在“创建节点“步骤中，参照如下参数配置节点。
    -   **创建节点：**
        -   现在添加：将为本集群创建节点，创建节点的数量请在下方的节点购买数量中进行设置。

            若您需要使用[应用服务网格ASM](https://support.huaweicloud.com/productdesc-istio/istio_productdesc_0001.html)功能，请选择“现在添加“，集群需要至少创建一个节点来安装Istio控制面。具体请参见[启用服务网格](https://support.huaweicloud.com/usermanual-istio/istio_01_0002.html)。

        -   稍后添加：将不会创建节点，仅创建一个空集群，请直接单击“下一步“。

    -   **计费模式：**支持“包年/包月“和“按需计费“两种计费类型。

        创建集群时节点的计费方式跟随集群的计费方式，如集群的计费模式选择“按需计费“，则创建过程中节点的计费模式只能为“按需计费“，“包年/包月“同理。创建方式请参考[购买节点](购买节点.md)。

        包年/包月节点创建后不能删除，如需停止使用，请到[费用中心](https://account.huaweicloud.com/usercenter/#/userindex/retreatManagement)执行退订操作。

    -   **当前区域：**节点实例所在的物理位置。
    -   **可用区：**请根据业务需要进行选择。可用区是在同一区域下，电力、网络隔离的物理区域，可用区之间内网互通，不同可用区之间物理隔离。

        如果您需要提高工作负载的高可靠性，建议您将云服务器创建在不同的可用区。

        **图 3**  Node节点创建在不同可用区<a name="cce_01_0028_fig920914253210"></a>  
        ![](figures/Node节点创建在不同可用区.png "Node节点创建在不同可用区")

    -   **节点类型：**选择节点类型。
        -   虚拟机节点：选中后创建虚拟机节点。
        -   裸金属节点：创建集群过程中不可选，需在集群创建完成后才可以为集群增加裸金属节点。点此了解[裸金属服务器](https://support.huaweicloud.com/bms/index.html)或[购买裸金属集群](购买裸金属集群.md)。

            >![](public_sys-resources/icon-note.gif) **说明：**   
            >CCE集群中创建裸金属节点需满足以下条件：  
            >-   集群创建完成之后才可以添加裸金属节点。  
            >-   集群为非IPV6模式。  
            >-   VPC网络集群版本高于v1.11.7，容器隧道网络集群版本高于v1.13.10。  
            >-   节点计费模式为包年/包月。  
            >购买裸金属节点请参考[购买节点](购买节点.md)。  


    -   **节点名称：**自定义节点名称。长度范围为4-32个字符，以小写字母开头，由小写字母、数字、中划线\(-\)组成，且不能以中划线\(-\)结尾。

        创建后如需修改请参考[修改云服务器名称](https://support.huaweicloud.com/usermanual-ecs/ecs_03_0145.html)，修改后需要[同步节点信息](同步节点信息.md)。

    -   **节点规格：**请根据业务需求选择**“GPU加速型“**下的节点规格。

        **图 4**  选择GPU节点规格<a name="fig715175671311"></a>  
        ![](figures/选择GPU节点规格.png "选择GPU节点规格")

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >为确保节点稳定性，系统会自动预留部分资源，运行必须的系统组件。详细请参见[节点预留资源计算公式](节点预留资源计算公式.md)。  

    -   **操作系统：**请选择节点对应的操作系统。

        重装操作系统或修改操作系统配置将导致节点不可用，请务必谨慎操作，具体请参见[集群节点高危操作](集群节点高危操作.md)。

    -   **系统盘**和**数据盘：**设置节点磁盘空间。

        -   系统盘：规格为\[40,1024\]GB，用户可以配置，缺省值为40GB。
        -   数据盘：规格为\[100,32678\]GB，用户可以配置，缺省值为100GB。

            单击“数据盘空间分配“后的![](figures/zh-cn_image_0220709079.png)，可以对数据盘中的“k8s空间“和“用户空间“进行自定义设置。

            -   k8s空间：您可以自定义数据盘中Docker和Kubelet的资源占比。Docker资源包含Docker镜像数据以及镜像元数据；Kubelet资源包含Pod配置文件、密钥以及临时存储EmptyDir等挂载数据。
            -   用户空间：定义本地盘中不分配给kubernetes使用的空间大小和用户空间挂载路径。

            >![](public_sys-resources/icon-notice.gif) **须知：**   
            >-   在本地磁盘中设置k8s空间和用户空间时，需满足k8s空间和用户空间总和为100%，设置后可单击![](figures/zh-cn_image_0220709080.png)自动调整数据。  
            >-   磁盘使用direct-lvm模式，移除将使用loop-lvm模式，有影响系统稳定性的风险。详情请点此[了解更多](https://docs.docker.com/engine/userguide/storagedriver/device-mapper-driver/)。  


        系统盘和数据盘均可提供以下性能规格的云硬盘：

        -   普通IO：是指由SATA存储提供资源的磁盘类型。提供可靠的块存储，单个云硬盘的最大IOPS可达到1000，可运行关键应用程序。
        -   高IO：是指由SAS存储提供资源的磁盘类型。提供可达到3000的高IO和低至1 ms的读写延时，支持NoSQL/关系型数据库，数据仓库，文件系统等应用。
        -   超高IO：是指由SSD存储提供资源的磁盘类型。提供可达到20000的超高IO和低至1 ms超低读写时延，支持NoSQL/关系型数据库，数据仓库等应用。

    -   **虚拟私有云：**不可修改，仅用于展示当前集群所在的虚拟私有云，该参数仅在v1.13.10-r0及以上版本的集群中显示。
    -   **所在子网：**通过子网提供与其他网络隔离的、可以独享的网络资源，以提高网络安全。可选择该集群虚拟私有云下的任意子网，集群节点支持跨子网。

        该参数仅在v1.13.10-r0及以上版本的集群中显示。

    -   **弹性IP：**独立申请的公网IP地址，若节点有互联网访问的需求，请选择“现在购买“或“使用已有“。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >CCE默认不启用VPC的SNAT。若VPC启用了SNAT，可以不使用EIP去访问外网。SNAT具体请参见[从容器访问公网](从容器访问公网.md)。  

        -   暂不使用：若新增节点未绑定弹性IP，则在该节点上运行的工作负载将不能被外网访问，仅可作为私有网络中部署业务或者集群所需云服务器进行使用。
        -   现在购买：选中后将根据您的配置购买弹性IP，并自动为每个节点进行分配。当购买的弹性IP数量小于节点个数时，会将弹性IP随机绑定到节点上。

            请根据业务需求和界面提示，选择弹性IP购买数量、规格、计费模式、带宽类型等。创建弹性云服务器过程中，请确保弹性IP配额充足。

        -   使用已有：请选择已有的弹性IP，将为当前节点分配已有弹性IP。

    -   **登录方式：**支持密码和密钥对。
        -   选择“密码“：用户名默认为“root”，请输入登录节点的密码，并确认密码。

            登录节点时需要使用该密码，请妥善管理密码，系统无法获取您设置的密码内容。

        -   选择“密钥对“：选择用于登录本节点的密钥对，支持选择共享密钥。

            密钥对用于远程登录节点时的身份认证。若没有密钥对，可单击选项框右侧的“创建密钥对”来新建，创建密钥对操作步骤请参见[创建密钥对](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0014250631.html)。

            **图 5**  密钥对<a name="cce_01_0028_fig82271742193213"></a>  
            ![](figures/密钥对.png "密钥对")

    -   **云服务器高级设置：**（可选），单击![](figures/zh-cn_image_0183134608.png)展开后可对节点进行如下高级功能配置：
        -   **云服务器组：**选择已创建的云服务器组，或单击右侧的“新建云服务器组“创建，创建完成后单击刷新按钮。

            通过云服务器组功能，弹性云服务器在创建时，将尽量分散地创建在不同的主机上，提高业务的可靠性。

        -   **资源标签：**通过为资源添加标签，可以对资源进行自定义标记，实现资源的分类。

            您可以在TMS中创建“预定义标签“，预定义标签对所有支持标签功能的服务资源可见，通过使用预定义标签可以提升标签创建和迁移效率。具体请参见[创建预定义标签](https://support.huaweicloud.com/usermanual-tms/zh-cn_topic_0144368884.html)。

            CCE服务会自动帮您创建CCE-Dynamic-Provisioning-Node=节点id的标签，允许增加5个标签。

        -   **委托：**委托是由租户管理员在[统一身份认证服务](https://console.huaweicloud.com/iam/#/iam/agencies)上创建的。通过委托，可以将云主机资源共享给其他帐号，或委托更专业的人或团队来代为管理。新建委托请参见[委托其他云服务管理资源](https://support.huaweicloud.com/usermanual-iam/iam_06_0004.html)，创建委托时委托类型选择“云服务“，单击“选择“按钮并在弹出的窗口中选择“ECS BMS“，即允许ECS或BMS调用云服务。
        -   **安装前执行脚本：**请输入脚本命令，大小限制为0\~1000字符。

            脚本将在Kubernetes软件安装前执行，可能导致Kubernetes软件无法正常安装，需谨慎使用。常用于格式化数据盘等场景。

        -   **安装后执行脚本：**请输入脚本命令，大小限制为0\~1000字符。

            脚本将在Kubernetes软件安装后执行，不影响Kubernetes软件安装。常用于修改Docker配置参数等场景。

        -   **新增数据盘：**单击“新增数据盘“增加一个数据盘并设置数据盘容量，该数据盘需要在**安装前执行脚本**中输入脚本命令进行格式化。示例请参见[如何给CCE节点添加第二块数据盘？](https://support.huaweicloud.com/cce_faq/cce_faq_00190.html)
        -   **子网IP：**可选择“自动分配IP地址“和“手动分配IP地址“，推荐使用“自动分配IP地址“。

    -   **Kubernetes高级设置：**（可选），单击![](figures/zh-cn_image_0183134479.png)展开后可对集群进行如下高级功能配置：
        -   **最大实例数：**节点最大允许创建的实例数\(Pod\)，该数量包含系统默认实例，取值范围为16\~250。

            该设置的目的为防止节点因管理过多实例而负载过重，请根据您的业务需要进行设置。

        -   **自定义镜像仓库：**单击“新增自定义镜像仓库地址“输入镜像仓库地址。

            添加自定义镜像仓库地址（非SSL镜像源地址）到docker启动参数中，避免拉取个人镜像仓库的镜像失败，格式可为“IP地址:端口或者域名”。安装后执行脚本与自定义镜像仓库不能同时使用。

        -   **单容器可用数据空间：**该参数用于设置一个容器可用的数据空间大小，设置范围为 10G 到 80G。如果设置的参数超过数据盘中Docker可占用的实际数据空间（由数据盘设置项中的资源分配自定义参数指定，默认为数据盘大小的90%），将以Docker的实际空间大小为主。该参数仅在v1.13.10-r0及以上版本的集群中显示。

    -   **节点购买数量：**此处设置的节点数不能超过集群管理的最大节点规模，请根据业务需求和界面提示进行选择，如需更多配额，请单击[提交工单](https://console.huaweicloud.com/console/#/quota)申请扩大配额。
    -   **购买时长：**若选择创建“包年/包月“的集群，请设置购买时长。

5.  单击“下一步：安装插件“，在“安装插件“步骤中选择要安装的插件。

    “系统资源插件“为必装插件，“高级功能插件“可根据实际需求进行选择性安装。

    所有插件也可以在集群创建完成后，在左侧导航栏中单击“插件管理“进行安装或卸载，具体请参见[插件管理](插件管理.md)  。

6.  单击“下一步：配置确认”，阅读“产品约束“并点选“我已知晓上述限制“，确认所设置的服务选型参数、规格和费用等信息。
7.  确认规格和费用后，单击“提交”，集群开始创建。

    若选择购买“包年包月“的集群，请单击“去支付“，根据界面提示进行付款操作。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >在集群创建页面中，您可以通过选择“启用Istio服务网格“，在混合集群中开启应用服务网格功能。具体请参见[启用服务网格](https://support.huaweicloud.com/usermanual-istio/istio_01_0002.html)。  

    集群创建预计需要6-10分钟，您可以单击“返回集群管理“进行其他操作或单击“查看集群事件列表“后查看集群详情。


## 相关操作<a name="section3667101120592"></a>

-   通过命令行工具连接集群：请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)。
-   添加节点：集群创建完成后，若您需要为集群添加更多节点，请参见[购买节点](购买节点.md)。
-   登录节点：请参见[登录节点](登录节点.md)。

-   创建命名空间：同个集群内可创建多个命名空间，形成逻辑上的不同分组，便于不同的分组在共享使用集群资源时还能被分别管理。若您需要为集群创建命名空间，请参见[命名空间](命名空间.md)。
-   创建工作负载：集群创建完成后，您可以使用镜像创建一个可公网访问的应用，请参见[创建无状态负载\(Deployment\)](创建无状态负载(Deployment).md)或[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)。
-   单击已成功创建的集群名称，进入“集群详情“页可查看集群详情。

    **表 2**  已创建的集群详情

    <a name="cce_01_0028_table1642185503514"></a>
    <table><thead align="left"><tr id="cce_01_0028_row1264365516359"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="cce_01_0028_p76431955153512"><a name="cce_01_0028_p76431955153512"></a><a name="cce_01_0028_p76431955153512"></a>页签类别</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="cce_01_0028_p176431155163517"><a name="cce_01_0028_p176431155163517"></a><a name="cce_01_0028_p176431155163517"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="cce_01_0028_row5975069716956"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p796825616956"><a name="cce_01_0028_p796825616956"></a><a name="cce_01_0028_p796825616956"></a>集群详情</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p4144902016956"><a name="cce_01_0028_p4144902016956"></a><a name="cce_01_0028_p4144902016956"></a>可查看该集群的详情及运行状态等。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row106431055133510"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p1364315552359"><a name="cce_01_0028_p1364315552359"></a><a name="cce_01_0028_p1364315552359"></a>监控</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p5583863516649"><a name="cce_01_0028_p5583863516649"></a><a name="cce_01_0028_p5583863516649"></a>查看集群近1小时、近3小时或近12小时的CPU和内存占用情况。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row1464335593515"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p1264365518351"><a name="cce_01_0028_p1264365518351"></a><a name="cce_01_0028_p1264365518351"></a>事件</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><a name="cce_01_0028_ul42186174161243"></a><a name="cce_01_0028_ul42186174161243"></a><ul id="cce_01_0028_ul42186174161243"><li>可以直接在“事件”页签下查看集群的事件。</li><li>可以设置查询条件，比如设置事件产生的时间段或搜索事件名称，查看相关事件。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>


