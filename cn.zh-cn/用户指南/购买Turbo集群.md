# 购买Turbo集群<a name="cce_01_0246"></a>

CCE Turbo支持新一代裸金属容器2.0集群，同时支持传统虚拟机节点，基于华为云新一代高性能基础设施提供极致的性能体验。

新一代裸金属容器集群，是华为云针对企业大规模业务生中的产高性能、低成本诉求，基于擎天架构构建的新一代容器解决方案。基于擎天架构深度软硬协同能力，将容器组件全部卸载到擎天卡上，使用户业务最大限度的使用服务器资源，进一步提升用户资源利用率；同时基于网络硬件直通能力和动态网络队列，有效减少网络性能损耗，使用户业务的网络性能大幅提升；Turbo集群同时支持裸金属服务器与虚拟机混合部署，满足用户业务高密度以及灵活性诉求。

**图 1**  CCE Turbo集群<a name="fig2054479209"></a>  
![](figures/CCE-Turbo集群.png "CCE-Turbo集群")

## 约束与限制<a name="section1675221242512"></a>

-   每个账号默认可以创建的云资源有一定的配额，如果超过配额创建集群会失败。请在创建集群前确认您的配额，查看配额请参见[关于配额](https://support.huaweicloud.com/usermanual-iaas/zh-cn_topic_0040259342.html)。如果您需要提高您的配额，请[提交工单](https://console.huaweicloud.com/ticket/#/ticketindex/createIndex)申请。
-   CCE Turbo集群只支持Yangtse网络，Yangtse网络的详细介绍请参见[什么是Yangtse网络，适用于什么场景？](https://support.huaweicloud.com/cce_faq/cce_faq_00246.html)。

## 申请公测<a name="section9459441124"></a>

CCE Turbo集群目前正在公测中，您可以登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在“总览”页面申请公测。申请通过后，就可以开始体验CCE Turbo集群。

**图 2**  公测入口<a name="fig5105519141512"></a>  
![](figures/公测入口.png "公测入口")

## 操作步骤<a name="section463761220269"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中单击“资源管理  \>  集群管理”，单击“CCE Turbo集群“下的“购买”。

    **图 3**  集群管理-购买Turbo集群<a name="fig11806912127"></a>  
    ![](figures/集群管理-购买Turbo集群.png "集群管理-购买Turbo集群")

2.  参照[表1](#table8638121213265)设置集群参数，其中带“\*”的参数需重点关注。

    **表 1**  创建集群参数配置

    <a name="table8638121213265"></a>
    <table><thead align="left"><tr id="row10638181262612"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p1063821214265"><a name="p1063821214265"></a><a name="p1063821214265"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p1638181232617"><a name="p1638181232617"></a><a name="p1638181232617"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1922964644615"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p9231104613468"><a name="p9231104613468"></a><a name="p9231104613468"></a>计费模式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p45631827103420"><a name="p45631827103420"></a><a name="p45631827103420"></a><span class="keyword" id="keyword44309542597"><a name="keyword44309542597"></a><a name="keyword44309542597"></a>按需计费</span>：后付费模式，按资源的实际使用时长计费，可以随时开通/删除资源。</p>
    <p id="p0624127506"><a name="p0624127506"></a><a name="p0624127506"></a>当前仅支持<span class="uicontrol" id="uicontrol8978171712013"><a name="uicontrol8978171712013"></a><a name="uicontrol8978171712013"></a>“按需计费”</span>。</p>
    </td>
    </tr>
    <tr id="row42961494311"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p812874116011"><a name="p812874116011"></a><a name="p812874116011"></a>区域</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p161283411302"><a name="p161283411302"></a><a name="p161283411302"></a>不同区域的云服务产品之间内网互不相通；请就近选择靠近您业务的区域，可减少网络时延，提高访问速度。</p>
    </td>
    </tr>
    <tr id="row12321131519262"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p14322181522614"><a name="p14322181522614"></a><a name="p14322181522614"></a>企业项目</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p19409193818259"><a name="p19409193818259"></a><a name="p19409193818259"></a>该参数仅对开通企业项目的企业客户账号显示。</p>
    <p id="p1363744211114"><a name="p1363744211114"></a><a name="p1363744211114"></a>选择某企业项目（如：default）后，集群、集群下节点、集群安全组、节点安全组和自动创建的节点EIP将创建到所选企业项目下。</p>
    <p id="p73221815122618"><a name="p73221815122618"></a><a name="p73221815122618"></a>企业项目是一种云资源管理方式，企业项目管理服务提供统一的云资源按项目管理，以及项目内的资源管理、成员管理。了解更多企业项目相关信息，请查看<a href="https://support.huaweicloud.com/usermanual-em/zh-cn_topic_0123692049.html" target="_blank" rel="noopener noreferrer">企业管理</a>。</p>
    </td>
    </tr>
    <tr id="row1063812126263"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p15639812122620"><a name="p15639812122620"></a><a name="p15639812122620"></a>* 集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p26391512172614"><a name="p26391512172614"></a><a name="p26391512172614"></a>新建集群的名称，创建后不可修改。</p>
    <p id="p1520317181911"><a name="p1520317181911"></a><a name="p1520317181911"></a>集群名称长度范围为4-128个字符，以小写字母开头，由小写字母、数字、中划线（-）组成，且不能以中划线（-）结尾。</p>
    </td>
    </tr>
    <tr id="row6649879161231"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1769363161231"><a name="p1769363161231"></a><a name="p1769363161231"></a>版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p9100682161231"><a name="p9100682161231"></a><a name="p9100682161231"></a>Kubernetes社区基线版本。默认为v1.17.9。</p>
    </td>
    </tr>
    <tr id="row572593234714"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p14725432104718"><a name="p14725432104718"></a><a name="p14725432104718"></a>集群管理规模</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p14899102111550"><a name="p14899102111550"></a><a name="p14899102111550"></a>集群管理规模是指当前集群的控制节点可以管理的最大工作节点规模，您可以选择50节点、200节点、1000节点或2000节点（仅1.15.11及以上版本的混合集群支持）四种管理规模，请根据您的业务需求选择，该规模在集群创建后不可更改，请慎重选择。如果您需要创建5000节点的集群，请<a href="https://console.huaweicloud.com/quota/?locale=zh-cn#/quota" target="_blank" rel="noopener noreferrer">提交工单</a>申请。</p>
    <p id="p192696516218"><a name="p192696516218"></a><a name="p192696516218"></a>若选择<span class="uicontrol" id="uicontrol35596531909"><a name="uicontrol35596531909"></a><a name="uicontrol35596531909"></a>“1000节点”</span>，表示当前集群的控制节点最多可管理1000个工作节点。由于不同管理规模的控制节点规格不同，因此配置费用会有差异。</p>
    <div class="p" id="p102308301014"><a name="p102308301014"></a><a name="p102308301014"></a>任何一个集群中均包含<span class="uicontrol" id="uicontrol144772569118"><a name="uicontrol144772569118"></a><a name="uicontrol144772569118"></a>“Master Node”</span>和<span class="uicontrol" id="uicontrol1458610581110"><a name="uicontrol1458610581110"></a><a name="uicontrol1458610581110"></a>“Worker Node”</span>，每一个Node对应一台云服务器。<a name="ul1045015327013"></a><a name="ul1045015327013"></a><ul id="ul1045015327013"><li>Master Node：集群的控制节点，在创建集群时会自动创建控制节点，负责整个集群的管理和调度。</li><li>Worker Node：集群的工作节点，即用户购买或纳管的节点。工作负载是由控制节点分配的，当某个工作节点宕机时，控制节点会将工作负载转移到其他工作节点上。</li></ul>
    </div>
    </td>
    </tr>
    <tr id="row17367436403"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p16736194318408"><a name="p16736194318408"></a><a name="p16736194318408"></a>控制节点数</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p67371743164017"><a name="p67371743164017"></a><a name="p67371743164017"></a>3：集群将创建三个控制节点，在单个控制节点发生故障后集群可以继续使用，不影响业务功能。单击“更改”，在“容灾设置”页面，可选择容灾级别。</p>
    <a name="ul196515617488"></a><a name="ul196515617488"></a><ul id="ul196515617488"><li>可用区：通过把控制节点建在不同的可用区，达到容灾目的。</li><li>故障域：通过把控制节点建在同一可用区下不同故障域，达到容灾目的。当环境支持故障域时，才会显示该选项。</li><li>主机：通过把控制节点建在同一可用区下不同主机，达到容灾目的。</li><li>自定义：您可以自行选择每个控制节点的位置。故障域模式控制节点必须在同一可用区下。</li></ul>
    <p id="p14985022174110"><a name="p14985022174110"></a><a name="p14985022174110"></a>1：集群仅创建一个控制节点，单控制节点集群不保证SLA，不适用于商用场景。单击“更改”，在“可用区设置”页面可选择控制节点可用区。</p>
    <div class="note" id="note15800847104112"><a name="note15800847104112"></a><a name="note15800847104112"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul1869875074110"></a><a name="ul1869875074110"></a><ul id="ul1869875074110"><li>在商用场景中，为提高集群容灾能力，建议您选择多控制节点模式集群。</li><li>多控制节点模式开关在集群创建完成后不可变更。单控制节点集群不支持升级为多控制节点集群，控制节点故障将影响运行业务，请谨慎选择。</li><li>为保证可靠性，1000及以上集群管理规模默认开启多控制节点模式。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row1763991215268"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p15639181282617"><a name="p15639181282617"></a><a name="p15639181282617"></a>* 虚拟私有云</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p20558173114298"><a name="p20558173114298"></a><a name="p20558173114298"></a>新建集群所在的虚拟私有云，集群创建后不可更改。</p>
    <p id="p116393128265"><a name="p116393128265"></a><a name="p116393128265"></a>虚拟私有云是通过逻辑方式进行网络隔离，提供安全、隔离的网络环境。</p>
    <p id="p1063941211266"><a name="p1063941211266"></a><a name="p1063941211266"></a>若没有虚拟私有云可选择，请单击<span class="uicontrol" id="uicontrol162261618154315"><a name="uicontrol162261618154315"></a><a name="uicontrol162261618154315"></a>“<span id="text112261418174320"><a name="text112261418174320"></a><a name="text112261418174320"></a>创建虚拟</span>私有云”</span>进行创建，完成创建后单击刷新按钮。操作步骤请参见<a href="https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013935842.html" target="_blank" rel="noopener noreferrer">创建虚拟私有云和子网</a>。</p>
    </td>
    </tr>
    <tr id="row15639412132615"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p36391812172618"><a name="p36391812172618"></a><a name="p36391812172618"></a>* 所在子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p924510014306"><a name="p924510014306"></a><a name="p924510014306"></a>节点虚拟机运行的子网环境，集群创建后不可更改。</p>
    <p id="p594513252114"><a name="p594513252114"></a><a name="p594513252114"></a>通过子网提供与其他网络隔离的、可以独享的网络资源，以提高网络安全。</p>
    <p id="p1108371202"><a name="p1108371202"></a><a name="p1108371202"></a>若没有子网可选择，请单击<span class="uicontrol" id="uicontrol626432718115"><a name="uicontrol626432718115"></a><a name="uicontrol626432718115"></a>“<span id="text82642277119"><a name="text82642277119"></a><a name="text82642277119"></a>创建子网</span>”</span>进行创建，完成创建后单击刷新按钮。虚拟私有云、子网、集群的关系请参见<a href="集群概述.md">集群概述</a>。</p>
    <p id="p1369519572172"><a name="p1369519572172"></a><a name="p1369519572172"></a><strong id="b13695957131719"><a name="b13695957131719"></a><a name="b13695957131719"></a>请确保子网下的DNS服务器可以解析OBS服务域名，否则无法创建节点。</strong></p>
    </td>
    </tr>
    <tr id="row482955911270"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p9831659192715"><a name="p9831659192715"></a><a name="p9831659192715"></a>网络模型</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p0724144517209"><a name="p0724144517209"></a><a name="p0724144517209"></a><strong id="b952205617204"><a name="b952205617204"></a><a name="b952205617204"></a>Yangtse：</strong>深度整合华为云<a href="https://support.huaweicloud.com/vpc/index.html" target="_blank" rel="noopener noreferrer">虚拟私有云VPC</a>原生弹性网卡（Elastic Network Interface，简称ENI）能力，采用VPC网段分配容器地址，支持ELB直通容器，享有高性能。</p>
    <p id="p135701052194711"><a name="p135701052194711"></a><a name="p135701052194711"></a>各网络模型的区别请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00162.html" target="_blank" rel="noopener noreferrer">CCE集群创建时如何选择网络模型？各模型的区别是什么？</a></p>
    <p id="p10517183918380"><a name="p10517183918380"></a><a name="p10517183918380"></a><strong id="b17724104473920"><a name="b17724104473920"></a><a name="b17724104473920"></a>Yangtse网络模式为公测阶段，集群创建后不可更改，请谨慎选择。</strong></p>
    </td>
    </tr>
    <tr id="row64648564171234"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p2042307171234"><a name="p2042307171234"></a><a name="p2042307171234"></a>容器网段</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p31209167171234"><a name="p31209167171234"></a><a name="p31209167171234"></a>请根据业务需求选择容器网段，确定容器网段后，容器实例将在规划的网段内分配IP。若没有容器网段可选择，请单击<span class="uicontrol" id="uicontrol142373564415"><a name="uicontrol142373564415"></a><a name="uicontrol142373564415"></a>“<span id="text14231635104415"><a name="text14231635104415"></a><a name="text14231635104415"></a>创建子网</span>”</span>进行创建，完成创建后单击刷新按钮。</p>
    <p id="p1726545494318"><a name="p1726545494318"></a><a name="p1726545494318"></a><strong id="b86161238448"><a name="b86161238448"></a><a name="b86161238448"></a>容器网段不能和服务网段冲突，不建议选择集群子网作为容器网段</strong>。若所选网段和集群子网相同，容器和节点将共同使用子网下剩余IP，易出现IP资源不足的场景导致容器或节点创建失败。</p>
    </td>
    </tr>
    <tr id="row6775143217241"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p677653218246"><a name="p677653218246"></a><a name="p677653218246"></a>服务网段</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p977633218244"><a name="p977633218244"></a><a name="p977633218244"></a>服务网段为kubernetes service ip网段。</p>
    <a name="ul13104152611581"></a><a name="ul13104152611581"></a><ul id="ul13104152611581"><li>使用默认网段：默认设置为10.247.0.0/16网段。</li><li>手动设置网段：请根据业务需求设置合理的网段和掩码，掩码决定集群内可用service ip数量。</li></ul>
    <p id="p1325817337153"><a name="p1325817337153"></a><a name="p1325817337153"></a>详情请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00004.html" target="_blank" rel="noopener noreferrer">如何规划CCE集群的网络地址段？</a>。</p>
    </td>
    </tr>
    <tr id="row773511171567"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p37371717105616"><a name="p37371717105616"></a><a name="p37371717105616"></a>鉴权方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p2017413473382"><a name="p2017413473382"></a><a name="p2017413473382"></a><span class="uicontrol" id="uicontrol217464712384"><a name="uicontrol217464712384"></a><a name="uicontrol217464712384"></a>“RBAC”</span>默认勾选，不可取消。</p>
    <p id="p16141515161117"><a name="p16141515161117"></a><a name="p16141515161117"></a>开启RBAC能力后，设置了细粒度权限的IAM用户使用集群下资源将受到权限控制。详细请参见<a href="设置命名空间权限.md">设置命名空间权限</a>。</p>
    </td>
    </tr>
    <tr id="row1610917221609"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p6655100911"><a name="p6655100911"></a><a name="p6655100911"></a>认证方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p933784218111"><a name="p933784218111"></a><a name="p933784218111"></a>认证机制主要用于对集群下的资源做权限控制。例如A用户只能对某个命名空间下的应用有读写权限，B用户对集群下的资源只有读权限等等。角色权限控制的操作请参见<a href="集群管理权限控制.md">集群管理权限控制</a>。</p>
    <a name="ul208851410646"></a><a name="ul208851410646"></a><ul id="ul208851410646"><li>默认状态下不选定<span class="uicontrol" id="uicontrol1371105874614"><a name="uicontrol1371105874614"></a><a name="uicontrol1371105874614"></a>“认证能力增强”</span>，此时默认开启X509认证模式，X509是一种非常通用的证书格式。</li><li>若需要对集群进行权限控制，请勾选“认证能力增强”，选择“认证代理”。<p id="p129632614510"><a name="p129632614510"></a><a name="p129632614510"></a>单击“CA根证书”后的“上传文件”，上传符合规范且合法的证书，并<strong id="b2356470185"><a name="b2356470185"></a><a name="b2356470185"></a>勾选“我已确认上传的证书合法”</strong>。</p>
    <p id="p36719411534"><a name="p36719411534"></a><a name="p36719411534"></a>证书若不合法，集群将无法创建成功。请上传小于1MB的文件，上传格式支持.crt或.cer格式。</p>
    </li></ul>
    </td>
    </tr>
    <tr id="row463941216264"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p2063961212268"><a name="p2063961212268"></a><a name="p2063961212268"></a>集群描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p664014125268"><a name="p664014125268"></a><a name="p664014125268"></a>选填，请输入新建容器集群相应的描述信息。</p>
    </td>
    </tr>
    <tr id="row96582533813"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p2285145420345"><a name="p2285145420345"></a><a name="p2285145420345"></a>高级设置</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1911106205716"><a name="p1911106205716"></a><a name="p1911106205716"></a>单击<span class="uicontrol" id="uicontrol151802714513"><a name="uicontrol151802714513"></a><a name="uicontrol151802714513"></a>“高级设置”</span>后展开详细项目，支持的功能如下（当前可用区中不支持的功能将隐藏）：</p>
    <p id="p113568261434"><a name="p113568261434"></a><a name="p113568261434"></a><strong id="b193562261439"><a name="b193562261439"></a><a name="b193562261439"></a>服务转发模式：</strong></p>
    <a name="ul1435618265318"></a><a name="ul1435618265318"></a><ul id="ul1435618265318"><li>iptables：社区传统的kube-proxy模式，完全以iptables规则的方式来实现service负载均衡。该方式最主要的问题是在服务多的时候产生太多的iptables规则，非增量式更新会引入一定的时延，大规模情况下有明显的性能问题。</li><li>ipvs：由华为主导开发并在社区获得广泛支持的kube-proxy模式，采用增量式更新，吞吐更高，速度更快，并可以保证service更新期间连接保持不断开，适用于大规模场景。<p id="p52781357485"><a name="p52781357485"></a><a name="p52781357485"></a>ipvs模式下，ingress和service使用相同的ELB实例时，无法在集群内的节点和容器中访问ingress。</p>
    </li></ul>
    <div class="note" id="note551324732117"><a name="note551324732117"></a><a name="note551324732117"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul2513447132113"></a><a name="ul2513447132113"></a><ul id="ul2513447132113"><li>ipvs为大型集群提供了更好的可扩展性和性能。</li><li>ipvs支持比iptables更复杂的负载平衡算法（最小负载，最少连接，位置，加权等）。</li><li>ipvs支持服务器健康检查和连接重试等。</li></ul>
    </div></div>
    <p id="p1530611329220"><a name="p1530611329220"></a><a name="p1530611329220"></a><strong id="b203061532132217"><a name="b203061532132217"></a><a name="b203061532132217"></a>资源标签：</strong></p>
    <p id="p153521813102212"><a name="p153521813102212"></a><a name="p153521813102212"></a>通过为资源添加标签，可以对资源进行自定义标记，实现资源的分类。</p>
    <p id="p1746516915228"><a name="p1746516915228"></a><a name="p1746516915228"></a>您可以在TMS中创建<span class="uicontrol" id="uicontrol9465129142213"><a name="uicontrol9465129142213"></a><a name="uicontrol9465129142213"></a>“预定义标签”</span>，预定义标签对所有支持标签功能的服务资源可见，通过使用预定义标签可以提升标签创建和迁移效率。具体请参见<a href="https://support.huaweicloud.com/usermanual-tms/zh-cn_topic_0144368884.html" target="_blank" rel="noopener noreferrer">创建预定义标签</a>。</p>
    <p id="p2448659163311"><a name="p2448659163311"></a><a name="p2448659163311"></a><strong id="b15868154114358"><a name="b15868154114358"></a><a name="b15868154114358"></a>CPU管理策略：</strong></p>
    <p id="p658055813489"><a name="p658055813489"></a><a name="p658055813489"></a>该参数仅在v1.13.10-r0及以上版本的集群中显示。</p>
    <a name="ul14813182993518"></a><a name="ul14813182993518"></a><ul id="ul14813182993518"><li>开启：支持给工作负载实例配置CPU独占，适用于对CPU缓存和调度延迟敏感的工作负载。</li><li>关闭：关闭工作负载实例独占CPU核的功能，优点是CPU共享池的可分配核数较多。</li></ul>
    <p id="p1363818291491"><a name="p1363818291491"></a><a name="p1363818291491"></a>更多CPU管理策略内容请参见<a href="https://kubernetes.io/blog/2018/07/24/feature-highlight-cpu-manager/" target="_blank" rel="noopener noreferrer">Feature Highlight: CPU Manager</a>或<a href="https://bbs.huaweicloud.com/forum/thread-28901-1-1.html" target="_blank" rel="noopener noreferrer">深入理解 Kubernetes CPU Mangager</a>。</p>
    </td>
    </tr>
    <tr id="row76532194177"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p79871037171719"><a name="p79871037171719"></a><a name="p79871037171719"></a>购买时长</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1991143711174"><a name="p1991143711174"></a><a name="p1991143711174"></a>若选择创建<span class="uicontrol" id="uicontrol10197720111410"><a name="uicontrol10197720111410"></a><a name="uicontrol10197720111410"></a>“包年/包月”</span>的集群，请设置购买时长。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  单击“下一步：配置确认”，阅读“使用说明“并点选“我已知晓上述限制“，确认所设置的服务选型参数、规格和费用等信息。
4.  确认规格和费用后，单击“提交”，集群开始创建。

    集群创建预计需要6-10分钟，您可以单击“返回集群管理“进行其他操作或单击“查看集群事件列表“后查看集群详情。

    集群创建完成后，您需要为集群添加节点，请参见[购买节点](购买节点.md)。


## 相关操作<a name="section473818525817"></a>

-   通过命令行工具连接集群：请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)。
-   登录节点：请参见[登录节点](登录节点.md)。

-   创建命名空间：同个集群内可创建多个命名空间，形成逻辑上的不同分组，便于不同的分组在共享使用集群资源时还能被分别管理。若您需要为集群创建命名空间，请参见[命名空间](命名空间.md)。
-   创建工作负载：集群创建完成后，您可以使用镜像创建一个可公网访问的应用，请参见[创建无状态负载\(Deployment\)](创建无状态负载(Deployment).md)、[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)或[创建守护进程集\(DaemonSet\)](创建守护进程集(DaemonSet).md)。
-   单击已成功创建的集群名称，进入“集群详情“页可查看集群详情。

    **表 2**  已创建的集群详情

    <a name="zh-cn_topic_0107283640_table1642185503514"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0107283640_row1264365516359"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0107283640_p76431955153512"><a name="zh-cn_topic_0107283640_p76431955153512"></a><a name="zh-cn_topic_0107283640_p76431955153512"></a>页签类别</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0107283640_p176431155163517"><a name="zh-cn_topic_0107283640_p176431155163517"></a><a name="zh-cn_topic_0107283640_p176431155163517"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0107283640_row5975069716956"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0107283640_p796825616956"><a name="zh-cn_topic_0107283640_p796825616956"></a><a name="zh-cn_topic_0107283640_p796825616956"></a>集群详情</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0107283640_p4144902016956"><a name="zh-cn_topic_0107283640_p4144902016956"></a><a name="zh-cn_topic_0107283640_p4144902016956"></a>可查看该集群的详情及运行状态等。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0107283640_row106431055133510"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0107283640_p1364315552359"><a name="zh-cn_topic_0107283640_p1364315552359"></a><a name="zh-cn_topic_0107283640_p1364315552359"></a>监控</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0107283640_p5583863516649"><a name="zh-cn_topic_0107283640_p5583863516649"></a><a name="zh-cn_topic_0107283640_p5583863516649"></a>可查看集群下全部节点的CPU和内存分配率（即分配量的最大值），以及控制节点的CPU和内存使用率、控制节点规格等信息。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0107283640_row1464335593515"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0107283640_p1264365518351"><a name="zh-cn_topic_0107283640_p1264365518351"></a><a name="zh-cn_topic_0107283640_p1264365518351"></a>事件</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><a name="zh-cn_topic_0107283640_ul42186174161243"></a><a name="zh-cn_topic_0107283640_ul42186174161243"></a><ul id="zh-cn_topic_0107283640_ul42186174161243"><li>可以直接在“事件”页签下查看集群的事件。</li><li>可以设置查询条件，比如设置事件产生的时间段或搜索事件名称，查看相关事件。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0107283640_row506129238"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0107283640_p160812132312"><a name="zh-cn_topic_0107283640_p160812132312"></a><a name="zh-cn_topic_0107283640_p160812132312"></a>弹性扩容</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0107283640_p90512182317"><a name="zh-cn_topic_0107283640_p90512182317"></a><a name="zh-cn_topic_0107283640_p90512182317"></a>您可以根据实际业务需要对集群的工作节点进行扩容和缩容，详情请参见<a href="集群弹性扩容.md">集群弹性扩容</a>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0107283640_row651036112414"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0107283640_p1251015692419"><a name="zh-cn_topic_0107283640_p1251015692419"></a><a name="zh-cn_topic_0107283640_p1251015692419"></a>kubectl</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0107283640_p35101368242"><a name="zh-cn_topic_0107283640_p35101368242"></a><a name="zh-cn_topic_0107283640_p35101368242"></a>若您需要从客户端计算机连接到kubernetes集群，请使用kubernetes命令行客户端<a href="https://kubernetes.io/docs/user-guide/kubectl/" target="_blank" rel="noopener noreferrer">kubectl</a>，详情请参见<a href="通过kubectl或web-terminal插件连接CCE集群.md">通过kubectl或web-terminal插件连接CCE集群</a>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0107283640_row2701721182419"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0107283640_p6701721122417"><a name="zh-cn_topic_0107283640_p6701721122417"></a><a name="zh-cn_topic_0107283640_p6701721122417"></a>Istioctl</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0107283640_p1701821112418"><a name="zh-cn_topic_0107283640_p1701821112418"></a><a name="zh-cn_topic_0107283640_p1701821112418"></a>在集群开启istio服务网格功能后，您使用Istio命令行工具Istioctl配置多种路由策略，从而管理服务流量，包括流量转移、故障注入、限流熔断等。详情请参见<a href="通过Istioctl配置路由策略.md">通过Istioctl配置路由策略</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>


