# 购买节点-CCE Turbo集群<a name="cce_01_0363"></a>

## 前提条件<a name="section103205496263"></a>

-   已创建至少一个CCE Turbo集群，请参见[购买CCE Turbo集群](购买CCE-Turbo集群.md)。
-   您需要新建一个密钥对，用于远程登录节点时的身份认证。

    若使用密码登录节点，请跳过此操作。创建方法请参见[创建密钥对](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0014250631.html)。


## 约束与限制<a name="cce_01_0298_section1675221242512"></a>

-   创建节点过程中会使用域名方式从OBS下载软件包，需要能够使用云上内网DNS解析OBS域名，否则会导致创建不成功。为此，节点所在子网需要配置为[内网DNS地址](https://support.huaweicloud.com/dns_faq/dns_faq_002.html)，从而使得节点使用内网DNS。在创建子网时DNS默认配置为内网DNS，如果您修改过子网的DNS，请务必**确保子网下的DNS服务器可以解析OBS服务域名**，否则需要将DNS改成内网DNS。
-   CCE Turbo集群的节点目前仅支持基于擎天软硬件协同架构的机型。
-   在1.19版本的CCE Turbo集群中添加的共池BMS节点，容器使用的网卡默认配置是4队列，详情请参见[CCE Turbo共池BMS节点容器网卡多队列配置](CCE-Turbo共池BMS节点容器网卡多队列配置.md)。

## 购买节点步骤<a name="cce_01_0298_section13305183010495"></a>

CCE Turbo集群创建完成后，您可以在集群中购买节点。

1.  单击创建的CCE Turbo集群卡片下方的“购买节点”按钮，在节点配置步骤中参照如下表格设置节点参数。

    **计算配置**：

    配置节点云服务器的规格与操作系统，为节点上的容器应用提供基本运行环境。

    **表 1**  计算配置参数

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
    <a name="ul1138261162510"></a><a name="ul1138261162510"></a><ul id="ul1138261162510"><li>普通容器：runc运行时。</li><li>安全容器：kata运行时。节点选择安全容器后，创建工作负载时如果也选择<span class="uicontrol" id="uicontrol2031523310332"><a name="uicontrol2031523310332"></a><a name="uicontrol2031523310332"></a>“安全容器”</span>，则该工作负载只能运行在使用安全容器的节点上。</li></ul>
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
    <p id="p89866115220"><a name="p89866115220"></a><a name="p89866115220"></a>私有镜像：裸金属服务器支持使用私有镜像，私有镜像制作方法具体请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00026.html" target="_blank" rel="noopener noreferrer">制作CCE节点自定义镜像</a>。</p>
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

    **表 2**  存储配置参数

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
    <p id="p3752312011"><a name="p3752312011"></a><a name="p3752312011"></a>单击后方的“展开”可进行如下设置：</p>
    <a name="ul197721145155911"></a><a name="ul197721145155911"></a><ul id="ul197721145155911"><li>自定义空间分配：勾选后可定义容器运行时在数据盘上占用的空间比例，容器运行时的空间用于存放容器运行时工作目录、容器镜像数据以及镜像元数据。</li><li>加密：数据盘加密功能可为您的数据提供强大的安全防护，加密磁盘生成的快照及通过这些快照创建的磁盘将自动继承加密功能。<a name="ul1998753519474"></a><a name="ul1998753519474"></a><ul id="ul1998753519474"><li>默认不加密。</li><li>点选<span class="uicontrol" id="uicontrol179625395464"><a name="uicontrol179625395464"></a><a name="uicontrol179625395464"></a>“加密”</span>后，可在弹出的<span class="uicontrol" id="uicontrol26061722134114"><a name="uicontrol26061722134114"></a><a name="uicontrol26061722134114"></a>“加密设置”</span>对话框中，选择已有的密钥，若没有可选的密钥，请单击后方的链接创建新密钥，完成创建后单击刷新按钮。</li></ul>
    </li></ul>
    </td>
    </tr>
    </tbody>
    </table>

    **网络配置**：

    配置节点云服务器的网络资源，用于访问节点和容器应用。

    **表 3**  网络配置参数

    <a name="table267212716587"></a>
    <table><thead align="left"><tr id="row126729712588"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p667211795816"><a name="p667211795816"></a><a name="p667211795816"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p867210795810"><a name="p867210795810"></a><a name="p867210795810"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1067237145814"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1367219735815"><a name="p1367219735815"></a><a name="p1367219735815"></a>节点子网与IP</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p46731571584"><a name="p46731571584"></a><a name="p46731571584"></a>节点子网默认使用创建集群时的子网配置，可在此进行修改。创建后不可修改。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **高级配置**：

    节点能力增强，可在此配置节点的标签、污点、启动命令等功能。

    **表 4**  高级配置参数

    <a name="table101545619373"></a>
    <table><thead align="left"><tr id="row115205619372"><th class="cellrowborder" valign="top" width="23.68%" id="mcps1.2.3.1.1"><p id="p2152561377"><a name="p2152561377"></a><a name="p2152561377"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="76.32%" id="mcps1.2.3.1.2"><p id="p1515195616375"><a name="p1515195616375"></a><a name="p1515195616375"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row653985164019"><td class="cellrowborder" valign="top" width="23.68%" headers="mcps1.2.3.1.1 "><p id="p1253915513402"><a name="p1253915513402"></a><a name="p1253915513402"></a>K8S标签</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.32%" headers="mcps1.2.3.1.2 "><p id="p11258124419136"><a name="p11258124419136"></a><a name="p11258124419136"></a>单击<span class="uicontrol" id="uicontrol18258644131312"><a name="uicontrol18258644131312"></a><a name="uicontrol18258644131312"></a>“添加标签”</span>可以设置附加到Kubernetes 对象（比如Pods）上的键值对，最多可以添加10条标签</p>
    <p id="p1442572821211"><a name="p1442572821211"></a><a name="p1442572821211"></a>使用该标签可区分不同节点，可结合工作负载的亲和能力实现容器Pod调度到指定节点的功能。详细请参见<a href="https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/" target="_blank" rel="noopener noreferrer">Labels and Selectors</a>。</p>
    </td>
    </tr>
    <tr id="row25394514014"><td class="cellrowborder" valign="top" width="23.68%" headers="mcps1.2.3.1.1 "><p id="p25391859406"><a name="p25391859406"></a><a name="p25391859406"></a>资源标签</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.32%" headers="mcps1.2.3.1.2 "><p id="p14909254174019"><a name="p14909254174019"></a><a name="p14909254174019"></a>通过为资源添加标签，可以对资源进行自定义标记，实现资源的分类。</p>
    <p id="p10327184710426"><a name="p10327184710426"></a><a name="p10327184710426"></a>您可以在TMS中创建<span class="uicontrol" id="uicontrol922854293212"><a name="uicontrol922854293212"></a><a name="uicontrol922854293212"></a>“预定义标签”</span>，预定义标签对所有支持标签功能的服务资源可见，通过使用预定义标签可以提升标签创建和迁移效率。具体请参见<a href="https://support.huaweicloud.com/usermanual-tms/zh-cn_topic_0144368884.html" target="_blank" rel="noopener noreferrer">创建预定义标签</a>。</p>
    <p id="p1738110524401"><a name="p1738110524401"></a><a name="p1738110524401"></a>CCE服务会自动帮您创建CCE-Dynamic-Provisioning-Node=节点id的标签。</p>
    </td>
    </tr>
    <tr id="row115391952402"><td class="cellrowborder" valign="top" width="23.68%" headers="mcps1.2.3.1.1 "><p id="p55391457404"><a name="p55391457404"></a><a name="p55391457404"></a>Taints</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.32%" headers="mcps1.2.3.1.2 "><div class="p" id="p2875141354415"><a name="p2875141354415"></a><a name="p2875141354415"></a>默认为空。支持给节点加Taints来设置反亲和性，每个节点最多配置10条Taints，每条Taints包含以下3个参数：<a name="ul17274222121015"></a><a name="ul17274222121015"></a><ul id="ul17274222121015"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀。</li><li>Value：必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li><li>Effect：只可选NoSchedule，PreferNoSchedule或NoExecute。</li></ul>
    <div class="notice" id="note77443231113"><a name="note77443231113"></a><a name="note77443231113"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><a name="ul104271158181515"></a><a name="ul104271158181515"></a><ul id="ul104271158181515"><li>Taints配置时需要配合Pod的toleration使用，否则可能导致扩容失败或者Pod无法调度到扩容节点。</li><li>节点池创建后可单击列表项的<span class="uicontrol" id="uicontrol144721126174416"><a name="uicontrol144721126174416"></a><a name="uicontrol144721126174416"></a>“编辑”</span>修改配置，修改后将同步到节点池下的已有节点。</li></ul>
    </div></div>
    </div>
    </td>
    </tr>
    <tr id="row155390520404"><td class="cellrowborder" valign="top" width="23.68%" headers="mcps1.2.3.1.1 "><p id="p054015516406"><a name="p054015516406"></a><a name="p054015516406"></a>最大实例数</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.32%" headers="mcps1.2.3.1.2 "><p id="p18611194424216"><a name="p18611194424216"></a><a name="p18611194424216"></a>节点最大可以正常运行的实例数(Pod)，该数量包含系统默认实例，取值范围为16~256。</p>
    <p id="p272611351429"><a name="p272611351429"></a><a name="p272611351429"></a>该设置的目的为防止节点因管理过多实例而负载过重，请根据您的业务需要进行设置。</p>
    </td>
    </tr>
    <tr id="row124141558173910"><td class="cellrowborder" valign="top" width="23.68%" headers="mcps1.2.3.1.1 "><p id="p154141258193916"><a name="p154141258193916"></a><a name="p154141258193916"></a>云服务器组</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.32%" headers="mcps1.2.3.1.2 "><p id="p53431536184014"><a name="p53431536184014"></a><a name="p53431536184014"></a>云服务器组是对云服务器的一种逻辑划分，同一云服务器组中的云服务器遵从同一策略。</p>
    <p id="p135011254181618"><a name="p135011254181618"></a><a name="p135011254181618"></a>反亲和性策略：同一云服务器组中的云服务器分散地创建在不同主机上，提高业务的可靠性。</p>
    <p id="p19871173217401"><a name="p19871173217401"></a><a name="p19871173217401"></a>选择已创建的云服务器组，或单击<span class="uicontrol" id="uicontrol4227114233214"><a name="uicontrol4227114233214"></a><a name="uicontrol4227114233214"></a>“新建云服务器组”</span>创建，创建完成后单击刷新按钮。</p>
    </td>
    </tr>
    <tr id="row23431056203915"><td class="cellrowborder" valign="top" width="23.68%" headers="mcps1.2.3.1.1 "><p id="p534319566391"><a name="p534319566391"></a><a name="p534319566391"></a>安装前执行脚本</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.32%" headers="mcps1.2.3.1.2 "><p id="p11569142494118"><a name="p11569142494118"></a><a name="p11569142494118"></a>请输入脚本命令，大小限制为0~1000字符。</p>
    <p id="p03368579295"><a name="p03368579295"></a><a name="p03368579295"></a>脚本将在Kubernetes软件安装前执行，可能导致Kubernetes软件无法正常安装，需谨慎使用。常用于格式化数据盘等场景。</p>
    </td>
    </tr>
    <tr id="row1167794673912"><td class="cellrowborder" valign="top" width="23.68%" headers="mcps1.2.3.1.1 "><p id="p18677104643916"><a name="p18677104643916"></a><a name="p18677104643916"></a>安装后执行脚本</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.32%" headers="mcps1.2.3.1.2 "><p id="p1114204119418"><a name="p1114204119418"></a><a name="p1114204119418"></a>请输入脚本命令，大小限制为0~1000字符。</p>
    <p id="p13471136154110"><a name="p13471136154110"></a><a name="p13471136154110"></a>脚本将在Kubernetes软件安装后执行，不影响Kubernetes软件安装。常用于修改Docker配置参数等场景。</p>
    </td>
    </tr>
    <tr id="row3366174093118"><td class="cellrowborder" valign="top" width="23.68%" headers="mcps1.2.3.1.1 "><p id="p123672040183119"><a name="p123672040183119"></a><a name="p123672040183119"></a>委托</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.32%" headers="mcps1.2.3.1.2 "><p id="p15869944123119"><a name="p15869944123119"></a><a name="p15869944123119"></a>委托是由租户管理员在统一身份认证服务上创建的。通过委托，可以将云主机资源共享给其他帐号，或委托更专业的人或团队来代为管理。</p>
    <p id="p151464163220"><a name="p151464163220"></a><a name="p151464163220"></a>如果没有委托请单击右侧<span class="uicontrol" id="uicontrol1182452533216"><a name="uicontrol1182452533216"></a><a name="uicontrol1182452533216"></a>“新建委托”</span>创建。</p>
    </td>
    </tr>
    <tr id="row1864641094712"><td class="cellrowborder" valign="top" width="23.68%" headers="mcps1.2.3.1.1 "><p id="p18875831124716"><a name="p18875831124716"></a><a name="p18875831124716"></a>计费</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.32%" headers="mcps1.2.3.1.2 "><a name="ul1387543119476"></a><a name="ul1387543119476"></a><ul id="ul1387543119476"><li><span class="keyword" id="keyword13875123194718"><a name="keyword13875123194718"></a><a name="keyword13875123194718"></a>包年/包月</span>：预付费模式，按订单的购买周期计费，适用于可预估资源使用周期的场景，价格比按需计费模式更优惠。若选择创建<span class="uicontrol" id="uicontrol198751312470"><a name="uicontrol198751312470"></a><a name="uicontrol198751312470"></a>“包年/包月”</span>的集群，请设置购买时长。包年/包月集群创建后不能删除，如需停止使用，请到<a href="https://account.huaweicloud.com/usercenter/#/userindex/retreatManagement" target="_blank" rel="noopener noreferrer">费用中心</a>执行退订操作。</li><li><span class="keyword" id="keyword58758311476"><a name="keyword58758311476"></a><a name="keyword58758311476"></a>按需计费</span>：后付费模式，按资源的实际使用时长计费，可以随时开通/删除资源。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

2.  单击“下一步：配置确认”，确认所设置的服务选型参数、规格和费用等信息。
3.  确认规格和费用后，单击“提交”，节点开始创建。

    若选择购买“包年包月“的节点，请单击“去支付“，根据界面提示进行付款操作。

    系统将自动跳转到节点列表页面，待节点状态为“可用“，表示节点添加成功。添加节点预计需要6-10分钟左右，请耐心等待。

4.  单击“返回节点列表“，待状态为可用，表示节点创建成功。

