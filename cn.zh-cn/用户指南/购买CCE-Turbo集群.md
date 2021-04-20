# 购买CCE Turbo集群<a name="cce_01_0298"></a>

CCE Turbo集群是基于云原生基础设施构建的云原生2.0容器引擎服务，具备软硬协同、网络无损、安全可靠、调度智能的优势，为用户提供一站式、高性价比的全新容器服务体验。

## 约束与限制<a name="section1675221242512"></a>

-   单Region下单用户可创建的集群总数限制为50个，如果配额不满足业务需求，请[到“我的配额”提交申请](https://console.huaweicloud.com/quota/?locale=zh-cn#/quota)，查看配额请参见[关于配额](https://support.huaweicloud.com/usermanual-iaas/zh-cn_topic_0040259342.html)。
-   CCE Turbo集群的网络模式只支持云原生网络2.0，云原生网络2.0的详细介绍请参见[云原生网络2.0](云原生网络2-0.md)。
-   CCE Turbo集群的节点目前仅支持基于擎天软硬件协同架构的机型。
-   TrunkPort能力仅在1.19版本的CCE Turbo集群中使用。
-   在1.19版本的CCE Turbo集群中添加的共池BMS节点，容器使用的网卡默认配置是4队列。

## 购买步骤<a name="section10209182314553"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中单击“资源管理  \>  集群管理”，单击“CCE Turbo集群“右侧的“购买”。

    **图 1**  购买CCE Turbo集群<a name="fig11806912127"></a>  
    ![](figures/购买CCE-Turbo集群.png "购买CCE-Turbo集群")

2.  在购买CCE Turbo集群页面中，参照如下表格设置集群参数。

    **基础配置**：

    创建集群，作为运行容器的独立环境，需要您完成如下基础配置。

    **表 1**  创建集群基础配置

    <a name="table775910549271"></a>
    <table><thead align="left"><tr id="row157523542279"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p167521454102714"><a name="p167521454102714"></a><a name="p167521454102714"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p775275462718"><a name="p775275462718"></a><a name="p775275462718"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3752125482710"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p157521054102715"><a name="p157521054102715"></a><a name="p157521054102715"></a>集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p675285410274"><a name="p675285410274"></a><a name="p675285410274"></a>新建集群的名称，同一账户下集群不可重名，创建后不可修改。</p>
    <p id="p77521954182719"><a name="p77521954182719"></a><a name="p77521954182719"></a>集群名称长度范围为4-128个字符，以小写字母开头，由小写字母、数字、中划线（-）组成，且不能以中划线（-）结尾。</p>
    </td>
    </tr>
    <tr id="row875345462719"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p127531542272"><a name="p127531542272"></a><a name="p127531542272"></a>版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p13753155412716"><a name="p13753155412716"></a><a name="p13753155412716"></a>集群要安装的Kubernetes软件版本。</p>
    </td>
    </tr>
    <tr id="row1175325415272"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p37535546272"><a name="p37535546272"></a><a name="p37535546272"></a>集群管理规模</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p375395414274"><a name="p375395414274"></a><a name="p375395414274"></a>集群管理规模是指当前集群的控制节点可以管理的最大工作节点规模，您可以选择200节点、1000节点或2000节点三种管理规模，请根据您的业务需求选择，该规模在集群创建后不可更改，请慎重选择。如果您需要创建5000节点的集群，请<a href="https://console.huaweicloud.com/quota/?locale=zh-cn#/quota" target="_blank" rel="noopener noreferrer">提交工单</a>申请。</p>
    <p id="p775395402712"><a name="p775395402712"></a><a name="p775395402712"></a>若选择<span class="uicontrol" id="uicontrol17537544279"><a name="uicontrol17537544279"></a><a name="uicontrol17537544279"></a>“1000节点”</span>，表示当前集群的控制节点最多可管理1000个工作节点。由于不同管理规模的控制节点规格不同，因此配置费用会有差异。</p>
    <div class="p" id="p1675313544277"><a name="p1675313544277"></a><a name="p1675313544277"></a>任何一个集群中均包含<span class="uicontrol" id="uicontrol4753254202716"><a name="uicontrol4753254202716"></a><a name="uicontrol4753254202716"></a>“Master Node”</span>和<span class="uicontrol" id="uicontrol12753105492717"><a name="uicontrol12753105492717"></a><a name="uicontrol12753105492717"></a>“Worker Node”</span>，每一个Node对应一台云服务器。<a name="ul27531254132715"></a><a name="ul27531254132715"></a><ul id="ul27531254132715"><li>Master Node：集群的控制节点，在创建集群时会自动创建控制节点，负责整个集群的管理和调度。</li><li>Worker Node：集群的工作节点，即用户购买或纳管的节点。工作负载是由控制节点分配的，当某个工作节点宕机时，控制节点会将工作负载转移到其他工作节点上。</li></ul>
    </div>
    </td>
    </tr>
    </tbody>
    </table>

    **网络配置**：

    选择集群下节点和容器所使用的网段，当网段下IP资源不足时将无法继续创建节点和容器。

    **表 2**  网络配置参数

    <a name="table1719575917289"></a>
    <table><thead align="left"><tr id="row81961759182810"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p181961559132819"><a name="p181961559132819"></a><a name="p181961559132819"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p15196165912281"><a name="p15196165912281"></a><a name="p15196165912281"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row20197165992816"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p11197195922815"><a name="p11197195922815"></a><a name="p11197195922815"></a>网络模型</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1319775917283"><a name="p1319775917283"></a><a name="p1319775917283"></a><strong id="b19197185972816"><a name="b19197185972816"></a><a name="b19197185972816"></a><span>云原生网络2.0：</span></strong><span>深度整合华为云</span><a href="https://support.huaweicloud.com/vpc/index.html" target="_blank" rel="noopener noreferrer">虚拟私有云VPC</a><span>原生弹性网卡（Elastic Network Interface，简称ENI）能力，采用VPC网段分配容器地址，支持ELB直通容器，享有高性能。</span></p>
    <p id="p151971259112818"><a name="p151971259112818"></a><a name="p151971259112818"></a>了解更多请参见<a href="云原生网络2-0.md">云原生网络2.0</a>、<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00162.html" target="_blank" rel="noopener noreferrer">CCE集群创建时如何选择网络模型？</a></p>
    </td>
    </tr>
    <tr id="row1319717598282"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p519725914288"><a name="p519725914288"></a><a name="p519725914288"></a>虚拟私有云</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p20558173114298"><a name="p20558173114298"></a><a name="p20558173114298"></a>请选择新建集群下节点和容器使用的虚拟私有云VPC，集群创建后不可更改。</p>
    <p id="p116393128265"><a name="p116393128265"></a><a name="p116393128265"></a>虚拟私有云是通过逻辑方式进行网络隔离，提供安全、隔离的网络环境。</p>
    <p id="p1063941211266"><a name="p1063941211266"></a><a name="p1063941211266"></a>若没有虚拟私有云可选择，请单击<a href="https://console.huaweicloud.com/vpc/?region=cn-north-4&amp;locale=zh-cn#/vpcs" target="_blank" rel="noopener noreferrer">虚拟私有云控制台</a>进行创建，完成创建后单击刷新按钮。操作步骤请参见<a href="https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013935842.html" target="_blank" rel="noopener noreferrer">创建虚拟私有云和子网</a>。</p>
    </td>
    </tr>
    <tr id="row9961959174010"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p36391812172618"><a name="p36391812172618"></a><a name="p36391812172618"></a>节点子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p143697334237"><a name="p143697334237"></a><a name="p143697334237"></a>选择一个虚拟私有云后可显示该选项。</p>
    <p id="p572616338520"><a name="p572616338520"></a><a name="p572616338520"></a>集群下节点使用的子网，决定了集群下节点的数量上限。创建节点时支持选择相同VPC下的其他子网。</p>
    <p id="p594513252114"><a name="p594513252114"></a><a name="p594513252114"></a>通过节点子网提供与其他网络隔离的、可以独享的网络资源，以提高网络安全。</p>
    <p id="p1108371202"><a name="p1108371202"></a><a name="p1108371202"></a>若没有节点子网可选择，请单击<span class="uicontrol" id="uicontrol626432718115"><a name="uicontrol626432718115"></a><a name="uicontrol626432718115"></a>“<span id="text82642277119"><a name="text82642277119"></a><a name="text82642277119"></a>新建子网</span>”</span>进行创建，完成创建后单击刷新按钮。虚拟私有云、子网、集群的关系请参见<a href="集群概述.md">集群概述</a>。</p>
    <p id="p1369519572172"><a name="p1369519572172"></a><a name="p1369519572172"></a><strong id="b13695957131719"><a name="b13695957131719"></a><a name="b13695957131719"></a>请确保子网下的DNS服务器可以解析OBS服务域名，否则无法创建节点。</strong></p>
    <p id="p9619101653511"><a name="p9619101653511"></a><a name="p9619101653511"></a><strong id="b1119161703511"><a name="b1119161703511"></a><a name="b1119161703511"></a>集群创建后子网无法修改，请谨慎选择。</strong></p>
    </td>
    </tr>
    <tr id="row19944514416"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p2042307171234"><a name="p2042307171234"></a><a name="p2042307171234"></a>容器子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p2046855174516"><a name="p2046855174516"></a><a name="p2046855174516"></a>选择一个虚拟私有云后可显示该选项。</p>
    <p id="p156731551122820"><a name="p156731551122820"></a><a name="p156731551122820"></a>集群下容器使用的子网，决定了集群下容器的数量上限，集群创建后该网段不可更改。</p>
    <p id="p31209167171234"><a name="p31209167171234"></a><a name="p31209167171234"></a>请根据业务需求选择容器子网，确定容器子网后，容器实例将在规划的网段内分配IP。</p>
    <p id="p873618346117"><a name="p873618346117"></a><a name="p873618346117"></a>容器子网要设置合理的掩码，掩码决定集群内可用节点数量。集群中容器网段掩码设置不合适，会导致集群实际可用的节点较少。设置掩码后，选项下方会有当前网段最多支持的实例估算值，请作参考。详情请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00004.html" target="_blank" rel="noopener noreferrer">如何规划CCE集群的网络地址段？</a>。</p>
    <div class="note" id="note1052111161767"><a name="note1052111161767"></a><a name="note1052111161767"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p9522716564"><a name="p9522716564"></a><a name="p9522716564"></a>如果容器子网和节点子网相同，容器和节点将共同使用子网下剩余IP，易出现IP资源不足的场景导致容器或节点创建失败。</p>
    </div></div>
    </td>
    </tr>
    </tbody>
    </table>

    **高级配置**：

    根据业务需求选择配置CCE Turbo集群的增强能力。

    **表 3**  网络配置参数

    <a name="table891216262306"></a>
    <table><thead align="left"><tr id="row1913122610307"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p17913526143020"><a name="p17913526143020"></a><a name="p17913526143020"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p6913192610308"><a name="p6913192610308"></a><a name="p6913192610308"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row13913122623018"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p139133267303"><a name="p139133267303"></a><a name="p139133267303"></a>服务网段</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p209134265308"><a name="p209134265308"></a><a name="p209134265308"></a>服务网段为kubernetes service ip网段，集群创建后该网段不可更改。服务网段与已创建的路由不能冲突，如果冲突，请重新选择。</p>
    <a name="ul1291314265304"></a><a name="ul1291314265304"></a><ul id="ul1291314265304"><li>使用默认网段：默认设置为10.247.0.0/16网段。</li><li>手动设置网段：请根据业务需求设置合理的网段和掩码，掩码决定集群内可用service ip数量。</li></ul>
    <p id="p2091312612308"><a name="p2091312612308"></a><a name="p2091312612308"></a>详情请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00004.html" target="_blank" rel="noopener noreferrer">如何规划CCE集群的网络地址段？</a>。</p>
    </td>
    </tr>
    <tr id="row9381745114114"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p138224519412"><a name="p138224519412"></a><a name="p138224519412"></a>kube-proxy转发模式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p16382124517417"><a name="p16382124517417"></a><a name="p16382124517417"></a>设置Service和其后端容器Pod之间进行负载均衡的方式，创建后不可修改。</p>
    <a name="ul171711948164219"></a><a name="ul171711948164219"></a><ul id="ul171711948164219"><li>iptables：社区传统的kube-proxy模式，完全以iptables规则的方式来实现service负载均衡。该方式最主要的问题是在服务多的时候产生太多的iptables规则，非增量式更新会引入一定的时延，大规模情况下有明显的性能问题。</li></ul>
    </td>
    </tr>
    <tr id="row1640647144410"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p9231104613468"><a name="p9231104613468"></a><a name="p9231104613468"></a>计费</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><a name="ul463941414445"></a><a name="ul463941414445"></a><ul id="ul463941414445"><li><span class="keyword" id="keyword66602077459"><a name="keyword66602077459"></a><a name="keyword66602077459"></a>包年/包月</span>：预付费模式，按订单的购买周期计费，适用于可预估资源使用周期的场景，价格比按需计费模式更优惠。若选择创建<span class="uicontrol" id="uicontrol16915172614306"><a name="uicontrol16915172614306"></a><a name="uicontrol16915172614306"></a>“包年/包月”</span>的集群，请设置购买时长。包年/包月集群创建后不能删除，如需停止使用，请到<a href="https://account.huaweicloud.com/usercenter/#/userindex/retreatManagement" target="_blank" rel="noopener noreferrer">费用中心</a>执行退订操作。</li><li><span class="keyword" id="keyword44309542597"><a name="keyword44309542597"></a><a name="keyword44309542597"></a>按需计费</span>：后付费模式，按资源的实际使用时长计费，可以随时开通/删除资源。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

3.  单击“下一步：配置确认”，确认所设置的服务选型参数、规格和费用等信息，您可以参照如下参数选择企业项目、修改计费模式和购买时长。

    <a name="table8638121213265"></a>
    <table><thead align="left"><tr id="row10638181262612"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.1.3.1.1"><p id="p1063821214265"><a name="p1063821214265"></a><a name="p1063821214265"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.1.3.1.2"><p id="p1638181232617"><a name="p1638181232617"></a><a name="p1638181232617"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row196852801312"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.1.3.1.1 "><p id="p14322181522614"><a name="p14322181522614"></a><a name="p14322181522614"></a>企业项目</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.1.3.1.2 "><p id="p19409193818259"><a name="p19409193818259"></a><a name="p19409193818259"></a>该参数仅对开通企业项目的企业客户帐号显示。</p>
    <p id="p1363744211114"><a name="p1363744211114"></a><a name="p1363744211114"></a>选择某企业项目（如：default）后，集群、集群下节点、集群安全组、节点安全组和自动创建的节点EIP（弹性公网IP）将创建到所选企业项目下。为方便管理资源，在集群创建成功后，建议不要修改集群下节点、集群安全组、节点安全组的企业项目。</p>
    <p id="p73221815122618"><a name="p73221815122618"></a><a name="p73221815122618"></a>企业项目是一种云资源管理方式，企业项目管理服务提供统一的云资源按项目管理，以及项目内的资源管理、成员管理。了解更多企业项目相关信息，请查看<a href="https://support.huaweicloud.com/usermanual-em/zh-cn_topic_0123692049.html" target="_blank" rel="noopener noreferrer">企业管理</a>。</p>
    </td>
    </tr>
    <tr id="row1922964644615"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.1.3.1.1 "><p id="p1998013239111"><a name="p1998013239111"></a><a name="p1998013239111"></a>计费模式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.1.3.1.2 "><p id="p1570094014219"><a name="p1570094014219"></a><a name="p1570094014219"></a>如果确认集群的计费模式有误，您可以在此修改。</p>
    <a name="ul1571804084210"></a><a name="ul1571804084210"></a><ul id="ul1571804084210"><li><span class="keyword" id="keyword77171640124218"><a name="keyword77171640124218"></a><a name="keyword77171640124218"></a>包年/包月</span>：预付费模式，按订单的购买周期计费，适用于可预估资源使用周期的场景，价格比按需计费模式更优惠。包年/包月集群创建后不能删除，如需停止使用，请到<a href="https://account.huaweicloud.com/usercenter/#/userindex/retreatManagement" target="_blank" rel="noopener noreferrer">费用中心</a>执行退订操作。</li><li><span class="keyword" id="keyword11717240164213"><a name="keyword11717240164213"></a><a name="keyword11717240164213"></a>按需计费</span>：后付费模式，按资源的实际使用时长计费，可以随时开通/删除资源。</li></ul>
    </td>
    </tr>
    <tr id="row12321131519262"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.1.3.1.1 "><p id="p79871037171719"><a name="p79871037171719"></a><a name="p79871037171719"></a>购买时长</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.1.3.1.2 "><p id="p1991143711174"><a name="p1991143711174"></a><a name="p1991143711174"></a>若选择创建<span class="uicontrol" id="uicontrol10197720111410"><a name="uicontrol10197720111410"></a><a name="uicontrol10197720111410"></a>“包年/包月”</span>的集群，请设置购买时长。</p>
    <p id="p19521553171418"><a name="p19521553171418"></a><a name="p19521553171418"></a>自动续费：勾选后可在自动。若按月购买，则自动续费周期为1个月；若按年购买，则自动续费周期为1年。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  确认规格和费用后，单击“提交”，集群开始创建。

    集群创建预计需要6-10分钟，您可以单击“返回集群管理“进行其他操作或单击“查看集群事件列表“后查看集群详情。待集群状态为“正常”，表示集群创建成功。

    集群创建完成后，您需要为集群添加节点，请参见[购买节点](购买节点.md)。


## 购买节点步骤<a name="section13305183010495"></a>

CCE Turbo集群创建完成后，可以在集群中购买节点。

1.  单击左侧栏目树的“资源管理 \> 节点管理“，选择创建的CCE Turbo集群，单击右上方的“购买节点”，在节点配置步骤中参照如下表格设置节点参数。

    **计算配置**：

    配置节点云服务器的规格与操作系统，为节点上的容器应用提供基本运行环境。

    **表 4**  计算配置参数

    <a name="table0668137185810"></a>
    <table><thead align="left"><tr id="row46680715812"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p186688710581"><a name="p186688710581"></a><a name="p186688710581"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p16681570588"><a name="p16681570588"></a><a name="p16681570588"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1666817718587"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p13216122213017"><a name="p13216122213017"></a><a name="p13216122213017"></a>可用区</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p4383635121713"><a name="p4383635121713"></a><a name="p4383635121713"></a>节点云服务器所在的可用区，集群下节点创建在不同可用区下可以提高可靠性。创建后不可修改。</p>
    <p id="p13307144019185"><a name="p13307144019185"></a><a name="p13307144019185"></a>建议您选择<span class="uicontrol" id="uicontrol4438451151812"><a name="uicontrol4438451151812"></a><a name="uicontrol4438451151812"></a>“随机分配”</span>，可根据选择的节点规格随机分配一个可以使用的可用区。</p>
    <p id="p4786153575318"><a name="p4786153575318"></a><a name="p4786153575318"></a>可用区是在同一区域下，电力、网络隔离的物理区域，可用区之间内网互通，不同可用区之间物理隔离。如果您需要提高工作负载的高可靠性，建议您将云服务器创建在不同的可用区。</p>
    </td>
    </tr>
    <tr id="row96694785812"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p7669676587"><a name="p7669676587"></a><a name="p7669676587"></a>容器运行时</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1166918711589"><a name="p1166918711589"></a><a name="p1166918711589"></a>选择节点上容器使用的运行时（Runtime），不同容器运行时支持的节点规格不同，创建后不可修改。</p>
    <a name="ul1138261162510"></a><a name="ul1138261162510"></a><ul id="ul1138261162510"><li>docker运行时：普通容器</li><li>安全运行时：节点选择该容器运行时后，创建工作负载时如果也选择<span class="uicontrol" id="uicontrol2031523310332"><a name="uicontrol2031523310332"></a><a name="uicontrol2031523310332"></a>“安全运行时”</span>，则该工作负载只能运行在使用安全运行时的节点上。</li></ul>
    <p id="p17135151618277"><a name="p17135151618277"></a><a name="p17135151618277"></a>两种容器运行时的对比请参见<a href="节点概述.md#section7201124294111">普通容器与安全容器的区别</a>。</p>
    </td>
    </tr>
    <tr id="row156691178589"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1669177185817"><a name="p1669177185817"></a><a name="p1669177185817"></a>节点规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p156695715814"><a name="p156695715814"></a><a name="p156695715814"></a>请根据业务需求选择相应的节点规格。</p>
    <p id="p16878944713"><a name="p16878944713"></a><a name="p16878944713"></a>CCE Turbo集群的节点目前仅支持基于擎天软硬件协同架构的机型。</p>
    </td>
    </tr>
    <tr id="row146695755817"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p176690785813"><a name="p176690785813"></a><a name="p176690785813"></a>操作系统</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1058345314295"><a name="p1058345314295"></a><a name="p1058345314295"></a>公共镜像：请选择节点对应的操作系统。</p>
    <p id="p65923115292"><a name="p65923115292"></a><a name="p65923115292"></a>公共镜像是常见的标准操作系统镜像，所有用户可见，包括操作系统以及预装的公共应用，更多介绍请参见<a href="https://support.huaweicloud.com/productdesc-ecs/ecs_01_0049.html" target="_blank" rel="noopener noreferrer">公共镜像概述</a>。</p>
    </td>
    </tr>
    <tr id="row209270458578"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p15928144516578"><a name="p15928144516578"></a><a name="p15928144516578"></a>节点名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p18111188595"><a name="p18111188595"></a><a name="p18111188595"></a>节点云服务器使用的名称，不支持重名，批量创建时将作为云服务器名称的前缀。</p>
    <p id="p863771115914"><a name="p863771115914"></a><a name="p863771115914"></a>系统会默认生成名称，支持修改。</p>
    <p id="p2017023218586"><a name="p2017023218586"></a><a name="p2017023218586"></a>节点名称以小写字母开头，支持小写字母、数字和中划线(-)，不能以中划线(-)结尾。</p>
    </td>
    </tr>
    <tr id="row6176410173016"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1917631063017"><a name="p1917631063017"></a><a name="p1917631063017"></a>登录方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p12296183663018"><a name="p12296183663018"></a><a name="p12296183663018"></a>支持密码和密钥对。</p>
    <a name="ul72961362303"></a><a name="ul72961362303"></a><ul id="ul72961362303"><li>选择<span class="uicontrol" id="uicontrol629673617303"><a name="uicontrol629673617303"></a><a name="uicontrol629673617303"></a>“密码”</span>：用户名默认为“root”，请输入登录节点的密码，并确认密码。<p id="p1629673613013"><a name="p1629673613013"></a><a name="p1629673613013"></a>登录节点时需要使用该密码，请妥善管理密码，系统无法获取您设置的密码内容。</p>
    </li><li>选择<span class="uicontrol" id="uicontrol5297163643018"><a name="uicontrol5297163643018"></a><a name="uicontrol5297163643018"></a>“密钥对”</span>：选择用于登录本节点的密钥对，支持选择共享密钥。<p id="p16297136153013"><a name="p16297136153013"></a><a name="p16297136153013"></a>密钥对用于远程登录节点时的身份认证。若没有密钥对，可单击选项框右侧的“创建密钥对”来新建，创建密钥对操作步骤请参见<a href="https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0014250631.html" target="_blank" rel="noopener noreferrer">创建密钥对</a>。</p>
    </li></ul>
    </td>
    </tr>
    </tbody>
    </table>

    **存储配置**：

    配置节点云服务器上的存储资源，方便节点上的容器软件与容器应用使用。请根据实际场景设置磁盘大小。

    **表 5**  存储配置参数

    <a name="table56691276581"></a>
    <table><thead align="left"><tr id="row186697710581"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p9669576584"><a name="p9669576584"></a><a name="p9669576584"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p366912711589"><a name="p366912711589"></a><a name="p366912711589"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row5669170585"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p666916719588"><a name="p666916719588"></a><a name="p666916719588"></a>系统盘</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p590942616323"><a name="p590942616323"></a><a name="p590942616323"></a>节点云服务器使用的系统盘，供操作系统使用。您可以设置系统盘的规格为40GB-1024GB之间的数值，缺省值为40GB。</p>
    <p id="p169091267325"><a name="p169091267325"></a><a name="p169091267325"></a>在默认情况下，系统盘可提供高IO、超高IO两种基本的云硬盘类型，关于云硬盘的详细信息请参见<a href="https://support.huaweicloud.com/usermanual-ecs/ecs_03_0301.html" target="_blank" rel="noopener noreferrer">云硬盘概述</a>。</p>
    </td>
    </tr>
    <tr id="row1966913718588"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p0669147185817"><a name="p0669147185817"></a><a name="p0669147185817"></a>数据盘</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p246755017336"><a name="p246755017336"></a><a name="p246755017336"></a>节点云服务器使用的数据盘，供容器运行时和Kubelet组件使用。您可以设置数据盘的规格为100GB-32768GB之间的数值，缺省值为100GB。数据盘可提供的云硬盘类型与上方系统盘一致。</p>
    <div class="caution" id="note124678507331"><a name="note124678507331"></a><a name="note124678507331"></a><span class="cautiontitle"> 注意： </span><div class="cautionbody"><p id="p3467185013330"><a name="p3467185013330"></a><a name="p3467185013330"></a>若数据盘卸载或损坏，会导致docker服务异常，最终导致节点不可用。建议不要删除该数据盘。</p>
    </div></div>
    <p id="p1770724193511"><a name="p1770724193511"></a><a name="p1770724193511"></a>单击后方的“展开”可设置自定义空间分配。</p>
    <p id="p4504175003313"><a name="p4504175003313"></a><a name="p4504175003313"></a>自定义空间分配：勾选后可定义容器运行时在数据盘上占用的空间比例，容器运行时的空间用于存放容器运行时工作目录、容器镜像数据以及镜像元数据。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **网络配置**：

    配置节点云服务器的网络资源，用于访问节点和容器应用。

    **表 6**  网络配置参数

    <a name="table267212716587"></a>
    <table><thead align="left"><tr id="row126729712588"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p667211795816"><a name="p667211795816"></a><a name="p667211795816"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p867210795810"><a name="p867210795810"></a><a name="p867210795810"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1067237145814"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1367219735815"><a name="p1367219735815"></a><a name="p1367219735815"></a>节点子网与IP</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p46731571584"><a name="p46731571584"></a><a name="p46731571584"></a>节点子网默认使用创建集群时的子网配置，可在此进行修改。创建后不可修改</p>
    </td>
    </tr>
    </tbody>
    </table>

    **高级配置**：

    节点能力增强，可在此配置节点的标签、污点、启动命令等功能。

    **表 7**  高级配置参数

    <a name="table101545619373"></a>
    <table><thead align="left"><tr id="row115205619372"><th class="cellrowborder" valign="top" width="33.96%" id="mcps1.2.3.1.1"><p id="p2152561377"><a name="p2152561377"></a><a name="p2152561377"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="66.03999999999999%" id="mcps1.2.3.1.2"><p id="p1515195616375"><a name="p1515195616375"></a><a name="p1515195616375"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row653985164019"><td class="cellrowborder" valign="top" width="33.96%" headers="mcps1.2.3.1.1 "><p id="p1253915513402"><a name="p1253915513402"></a><a name="p1253915513402"></a>K8S标签</p>
    </td>
    <td class="cellrowborder" valign="top" width="66.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p11258124419136"><a name="p11258124419136"></a><a name="p11258124419136"></a>单击<span class="uicontrol" id="uicontrol18258644131312"><a name="uicontrol18258644131312"></a><a name="uicontrol18258644131312"></a>“添加标签”</span>可以设置附加到Kubernetes 对象（比如Pods）上的键值对，最多可以添加10条标签</p>
    <p id="p1442572821211"><a name="p1442572821211"></a><a name="p1442572821211"></a>使用该标签可区分不同节点，可结合工作负载的亲和能力实现容器Pod调度到指定节点的功能。详细请参见<a href="https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/" target="_blank" rel="noopener noreferrer">Labels and Selectors</a>。</p>
    </td>
    </tr>
    <tr id="row25394514014"><td class="cellrowborder" valign="top" width="33.96%" headers="mcps1.2.3.1.1 "><p id="p25391859406"><a name="p25391859406"></a><a name="p25391859406"></a>资源标签</p>
    </td>
    <td class="cellrowborder" valign="top" width="66.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p14909254174019"><a name="p14909254174019"></a><a name="p14909254174019"></a>通过为资源添加标签，可以对资源进行自定义标记，实现资源的分类。</p>
    <p id="p10327184710426"><a name="p10327184710426"></a><a name="p10327184710426"></a>您可以在TMS中创建<span class="uicontrol" id="uicontrol922854293212"><a name="uicontrol922854293212"></a><a name="uicontrol922854293212"></a>“预定义标签”</span>，预定义标签对所有支持标签功能的服务资源可见，通过使用预定义标签可以提升标签创建和迁移效率。具体请参见<a href="https://support.huaweicloud.com/usermanual-tms/zh-cn_topic_0144368884.html" target="_blank" rel="noopener noreferrer">创建预定义标签</a>。</p>
    <p id="p1738110524401"><a name="p1738110524401"></a><a name="p1738110524401"></a>CCE服务会自动帮您创建CCE-Dynamic-Provisioning-Node=节点id的标签，允许增加5个标签。</p>
    </td>
    </tr>
    <tr id="row115391952402"><td class="cellrowborder" valign="top" width="33.96%" headers="mcps1.2.3.1.1 "><p id="p55391457404"><a name="p55391457404"></a><a name="p55391457404"></a>Taints</p>
    </td>
    <td class="cellrowborder" valign="top" width="66.03999999999999%" headers="mcps1.2.3.1.2 "><div class="p" id="p2875141354415"><a name="p2875141354415"></a><a name="p2875141354415"></a>默认为空。支持给该节点池扩容出来的节点加Taints来设置反亲和性，每个节点池最多配置10条Taints，每条Taints包含以下3个参数：<a name="ul17274222121015"></a><a name="ul17274222121015"></a><ul id="ul17274222121015"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀。</li><li>Value：必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li><li>Effect：只可选NoSchedule，PreferNoSchedule或NoExecute。</li></ul>
    <div class="notice" id="note77443231113"><a name="note77443231113"></a><a name="note77443231113"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><a name="ul104271158181515"></a><a name="ul104271158181515"></a><ul id="ul104271158181515"><li>Taints配置时需要配合Pod的toleration使用，否则可能导致扩容失败或者Pod无法调度到扩容节点。</li><li>节点池创建后可单击列表项的<span class="uicontrol" id="uicontrol144721126174416"><a name="uicontrol144721126174416"></a><a name="uicontrol144721126174416"></a>“编辑”</span>修改配置，修改后将同步到节点池下的已有节点。</li></ul>
    </div></div>
    </div>
    </td>
    </tr>
    <tr id="row155390520404"><td class="cellrowborder" valign="top" width="33.96%" headers="mcps1.2.3.1.1 "><p id="p054015516406"><a name="p054015516406"></a><a name="p054015516406"></a>最大实例数</p>
    </td>
    <td class="cellrowborder" valign="top" width="66.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p18611194424216"><a name="p18611194424216"></a><a name="p18611194424216"></a>节点最大可以正常运行的实例数(Pod)，该数量包含系统默认实例，取值范围为16~128。</p>
    <p id="p272611351429"><a name="p272611351429"></a><a name="p272611351429"></a>该设置的目的为防止节点因管理过多实例而负载过重，请根据您的业务需要进行设置。</p>
    </td>
    </tr>
    <tr id="row124141558173910"><td class="cellrowborder" valign="top" width="33.96%" headers="mcps1.2.3.1.1 "><p id="p154141258193916"><a name="p154141258193916"></a><a name="p154141258193916"></a>云服务器组</p>
    </td>
    <td class="cellrowborder" valign="top" width="66.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p53431536184014"><a name="p53431536184014"></a><a name="p53431536184014"></a>云服务器组是对云服务器的一种逻辑划分，同一云服务器组中的云服务器遵从同一策略。</p>
    <p id="p135011254181618"><a name="p135011254181618"></a><a name="p135011254181618"></a>反亲和性策略：同一云服务器组中的云服务器分散地创建在不同主机上，提高业务的可靠性。</p>
    <p id="p19871173217401"><a name="p19871173217401"></a><a name="p19871173217401"></a>选择已创建的云服务器组，或单击<span class="uicontrol" id="uicontrol4227114233214"><a name="uicontrol4227114233214"></a><a name="uicontrol4227114233214"></a>“新建云服务器组”</span>创建，创建完成后单击刷新按钮。</p>
    </td>
    </tr>
    <tr id="row23431056203915"><td class="cellrowborder" valign="top" width="33.96%" headers="mcps1.2.3.1.1 "><p id="p534319566391"><a name="p534319566391"></a><a name="p534319566391"></a>安装前执行脚本</p>
    </td>
    <td class="cellrowborder" valign="top" width="66.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p11569142494118"><a name="p11569142494118"></a><a name="p11569142494118"></a>请输入脚本命令，大小限制为0~1000字符。</p>
    <p id="p03368579295"><a name="p03368579295"></a><a name="p03368579295"></a>脚本将在Kubernetes软件安装前执行，可能导致Kubernetes软件无法正常安装，需谨慎使用。常用于格式化数据盘等场景。</p>
    </td>
    </tr>
    <tr id="row1167794673912"><td class="cellrowborder" valign="top" width="33.96%" headers="mcps1.2.3.1.1 "><p id="p18677104643916"><a name="p18677104643916"></a><a name="p18677104643916"></a>安装后执行脚本</p>
    </td>
    <td class="cellrowborder" valign="top" width="66.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p1114204119418"><a name="p1114204119418"></a><a name="p1114204119418"></a>请输入脚本命令，大小限制为0~1000字符。</p>
    <p id="p13471136154110"><a name="p13471136154110"></a><a name="p13471136154110"></a>脚本将在Kubernetes软件安装后执行，不影响Kubernetes软件安装。常用于修改Docker配置参数等场景。</p>
    </td>
    </tr>
    <tr id="row8356164413910"><td class="cellrowborder" valign="top" width="33.96%" headers="mcps1.2.3.1.1 "><p id="p1435614417397"><a name="p1435614417397"></a><a name="p1435614417397"></a>单容器可用数据空间</p>
    </td>
    <td class="cellrowborder" valign="top" width="66.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p1335794483917"><a name="p1335794483917"></a><a name="p1335794483917"></a>该参数用于设置一个容器可用的数据空间大小，设置范围为10G到80G。如果设置的参数超过数据盘中Docker可占用的实际数据空间（由数据盘设置项中的资源分配自定义参数指定，默认为数据盘大小的90%），将以Docker的实际空间大小为主。</p>
    </td>
    </tr>
    <tr id="row1864641094712"><td class="cellrowborder" valign="top" width="33.96%" headers="mcps1.2.3.1.1 "><p id="p18875831124716"><a name="p18875831124716"></a><a name="p18875831124716"></a>计费</p>
    </td>
    <td class="cellrowborder" valign="top" width="66.03999999999999%" headers="mcps1.2.3.1.2 "><a name="ul1387543119476"></a><a name="ul1387543119476"></a><ul id="ul1387543119476"><li><span class="keyword" id="keyword13875123194718"><a name="keyword13875123194718"></a><a name="keyword13875123194718"></a>包年/包月</span>：预付费模式，按订单的购买周期计费，适用于可预估资源使用周期的场景，价格比按需计费模式更优惠。若选择创建<span class="uicontrol" id="uicontrol198751312470"><a name="uicontrol198751312470"></a><a name="uicontrol198751312470"></a>“包年/包月”</span>的集群，请设置购买时长。包年/包月集群创建后不能删除，如需停止使用，请到<a href="https://account.huaweicloud.com/usercenter/#/userindex/retreatManagement" target="_blank" rel="noopener noreferrer">费用中心</a>执行退订操作。</li><li><span class="keyword" id="keyword58758311476"><a name="keyword58758311476"></a><a name="keyword58758311476"></a>按需计费</span>：后付费模式，按资源的实际使用时长计费，可以随时开通/删除资源。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

2.  单击“下一步：配置确认”，确认所设置的服务选型参数、规格和费用等信息。
3.  确认规格和费用后，单击“提交”，节点开始创建。

    若选择购买“包年包月“的节点，请单击“去支付“，根据界面提示进行付款操作。

    系统将自动跳转到节点列表页面，待节点状态为“可用“，表示节点添加成功。添加节点预计需要6-10分钟左右，请耐心等待。

4.  单击“返回节点列表“，待状态为可用，表示节点创建成功。

## 相关操作<a name="section473818525817"></a>

-   通过命令行工具连接集群：请参见[通过kubectl或web-terminal插件操作CCE集群](通过kubectl或web-terminal插件操作CCE集群.md)。
-   登录节点：请参见[登录节点](登录节点.md)。

-   创建命名空间：同个集群内可创建多个命名空间，形成逻辑上的不同分组，便于不同的分组在共享使用集群资源时还能被分别管理。若您需要为集群创建命名空间，请参见[命名空间](命名空间.md)。
-   创建工作负载：集群创建完成后，您可以使用镜像创建一个可公网访问的应用，请参见[创建无状态负载\(Deployment\)](创建无状态负载(Deployment).md)、[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)或[创建守护进程集\(DaemonSet\)](创建守护进程集(DaemonSet).md)。
-   单击已成功创建的集群名称，进入“集群详情“页可查看集群详情。

    **表 8**  已创建的集群详情

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
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p5583863516649"><a name="cce_01_0028_p5583863516649"></a><a name="cce_01_0028_p5583863516649"></a>可查看集群下全部节点的CPU和内存分配率（即分配量的最大值），以及控制节点的CPU和内存使用率、控制节点规格等信息。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row1464335593515"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p1264365518351"><a name="cce_01_0028_p1264365518351"></a><a name="cce_01_0028_p1264365518351"></a>事件</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><a name="cce_01_0028_ul42186174161243"></a><a name="cce_01_0028_ul42186174161243"></a><ul id="cce_01_0028_ul42186174161243"><li>可以直接在“事件”页签下查看集群的事件。</li><li>可以设置查询条件，比如设置事件产生的时间段或搜索事件名称，查看相关事件。</li></ul>
    </td>
    </tr>
    <tr id="cce_01_0028_row506129238"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p160812132312"><a name="cce_01_0028_p160812132312"></a><a name="cce_01_0028_p160812132312"></a>弹性扩容</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p90512182317"><a name="cce_01_0028_p90512182317"></a><a name="cce_01_0028_p90512182317"></a>您可以根据实际业务需要对集群的工作节点进行扩容和缩容，详情请参见<a href="集群弹性扩容.md">集群弹性扩容</a>。</p>
    <p id="p866618443354"><a name="p866618443354"></a><a name="p866618443354"></a>v1.17版本的集群不再支持AOM提供的弹性伸缩机制，请使用节点池功能进行弹性伸缩，详情请参见<a href="节点池概述.md">节点池概述</a>。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row651036112414"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p1251015692419"><a name="cce_01_0028_p1251015692419"></a><a name="cce_01_0028_p1251015692419"></a>kubectl</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p35101368242"><a name="cce_01_0028_p35101368242"></a><a name="cce_01_0028_p35101368242"></a>若您需要从客户端计算机连接到kubernetes集群，请使用kubernetes命令行客户端<a href="https://kubernetes.io/docs/user-guide/kubectl/" target="_blank" rel="noopener noreferrer">kubectl</a>，详情请参见<a href="通过kubectl或web-terminal插件操作CCE集群.md">通过kubectl或web-terminal插件操作CCE集群</a>。</p>
    </td>
    </tr>
    <tr id="row1562810082313"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p96289022317"><a name="p96289022317"></a><a name="p96289022317"></a>资源标签</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p11774125042315"><a name="p11774125042315"></a><a name="p11774125042315"></a>通过为资源添加标签，可以对资源进行自定义标记，实现资源的分类。</p>
    <p id="p177435013232"><a name="p177435013232"></a><a name="p177435013232"></a>您可以在TMS中创建<span class="uicontrol" id="uicontrol7775105022310"><a name="uicontrol7775105022310"></a><a name="uicontrol7775105022310"></a>“预定义标签”</span>，预定义标签对所有支持标签功能的服务资源可见，通过使用预定义标签可以提升标签创建和迁移效率。具体请参见<a href="https://support.huaweicloud.com/usermanual-tms/zh-cn_topic_0144368884.html" target="_blank" rel="noopener noreferrer">创建预定义标签</a>。</p>
    <p id="p15775125014232"><a name="p15775125014232"></a><a name="p15775125014232"></a>CCE服务会自动帮您创建CCE-Dynamic-Provisioning-Node=节点id的标签，允许增加5个标签。</p>
    </td>
    </tr>
    <tr id="cce_01_0028_row2701721182419"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="cce_01_0028_p6701721122417"><a name="cce_01_0028_p6701721122417"></a><a name="cce_01_0028_p6701721122417"></a>Istioctl</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="cce_01_0028_p1701821112418"><a name="cce_01_0028_p1701821112418"></a><a name="cce_01_0028_p1701821112418"></a>在集群开启istio服务网格功能后，您使用Istio命令行工具Istioctl配置多种路由策略，从而管理服务流量，包括流量转移、故障注入、限流熔断等。详情请参见<a href="通过Istioctl配置路由策略.md">通过Istioctl配置路由策略</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>


