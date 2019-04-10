# 创建GPU集群<a name="cce_01_0122"></a>

GPU集群是指使用GPU节点部署的集群，支持主流AI计算框架、支持多容器共享GPU资源。

自从1.8版本开始，Kubernetes已经明确表示要通过统一的[设备插件方式](https://kubernetes.io/docs/concepts/cluster-administration/device-plugins/)支持像Nvidia PU，InfiniBand，FPGA等硬件加速设备，而社区的GPU方案将在1.10全面弃用，并在1.11版本彻底从主干代码移除。

若您需要通过华为云GPU容器集群运行机器学习、科学计算、AI推理等高运算密度任务，无需安装nvidia driver，就能实现一键部署和弹性扩缩容等功能。

## 使用限制<a name="section15947165882217"></a>

-   每个账号默认可以创建的云资源有一定的配额，如果超过配额创建集群会失败。请在创建集群前确认您的配额，查看配额请参见[关于配额](https://support.huaweicloud.com/usermanual-iaas/zh-cn_topic_0040259342.html)。如果您需要提高您的配额，请[提交工单](https://console.huaweicloud.com/ticket/?agencyId=3FkSnJuoySIcmAPKH8ddQIoUQHVIkInv&region=cn-north-1&locale=zh-cn#/ticketindex/createfeedback?templeteId=004)申请。
-   Kubernetes 1.9版本的集群，GPU组件默认强制安装；Kubernetes 1.11及以上版本的集群，GPU能力以插件的方式外接提供，需要您在“插件管理“中安装“GPU-beta“插件。
-   ECS 实例使用限制：
    -   仅支持 EulerOS 2.2 操作系统。
    -   CUDA需要您自行在镜像中安装。


## 创建GPU集群<a name="section9343750182712"></a>

1.  登录[云容器引擎管理控制台](https://console.huaweicloud.com/cce2.0/)，在左侧导航栏中单击“资源管理 \> 集群管理“，进入集群列表页面。
2.  单击页面右上角“GPU集群“下方的“购买“按钮，进入“购买混合集群“页面。

    **图 1**  购买GPU集群<a name="fig8331155503518"></a>  
    ![](figures/购买GPU集群.png "购买GPU集群")

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >默认进入混合集群配置页面。  
    >为了创建GPU集群，通常情况下，Worker节点使用GPU类型的ECS。其他集群的参数配置，请参见[创建混合集群](创建混合集群.md)。  

3.  参照[表1](#table1156068114817)设置新增集群参数，其中带“\*”的参数为必填参数。

    **表 1**  创建集群参数配置

    <a name="table1156068114817"></a>
    <table><thead align="left"><tr id="row4562485485"><th class="cellrowborder" valign="top" width="18.13%" id="mcps1.2.3.1.1"><p id="p20359114265313"><a name="p20359114265313"></a><a name="p20359114265313"></a>* 计费模式</p>
    </th>
    <th class="cellrowborder" valign="top" width="81.87%" id="mcps1.2.3.1.2"><a name="ul463941414445"></a><a name="ul463941414445"></a><ul id="ul463941414445"><li><span class="keyword" id="keyword1617519316453"><a name="keyword1617519316453"></a><a name="keyword1617519316453"></a>按需计费</span>：根据实际使用的资源按小时计费。</li><li><span class="keyword" id="keyword66602077459"><a name="keyword66602077459"></a><a name="keyword66602077459"></a>包年/包月</span>：包周期计费。包年/包月集群创建后不能删除，如需停止使用，请到<span class="uicontrol" id="uicontrol2093921714410"><a name="uicontrol2093921714410"></a><a name="uicontrol2093921714410"></a>“费用中心”</span>执行退订操作。</li></ul>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row056288104814"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p1846512125412"><a name="p1846512125412"></a><a name="p1846512125412"></a>* 区域</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p161283411302"><a name="p161283411302"></a><a name="p161283411302"></a>请就近选择靠近您业务的区域，可减少网络时延，提高访问速度。</p>
    </td>
    </tr>
    <tr id="row35624894814"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p752771095411"><a name="p752771095411"></a><a name="p752771095411"></a>* 集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p25620811482"><a name="p25620811482"></a><a name="p25620811482"></a>新建集群的名称。</p>
    </td>
    </tr>
    <tr id="row7797145275013"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p5171161719545"><a name="p5171161719545"></a><a name="p5171161719545"></a>* 版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p9100682161231"><a name="p9100682161231"></a><a name="p9100682161231"></a>选择集群对应的版本，对应Kubernetes社区基线版本。</p>
    </td>
    </tr>
    <tr id="row77972522502"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p4243122425411"><a name="p4243122425411"></a><a name="p4243122425411"></a>* 集群管理规模</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p192696516218"><a name="p192696516218"></a><a name="p192696516218"></a>当前集群支持管理的最大节点规模。若选择50节点，表示当前集群最多可管理50个节点。</p>
    </td>
    </tr>
    <tr id="row6797125245019"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p479913322549"><a name="p479913322549"></a><a name="p479913322549"></a>* 高可用</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><a name="ul97916871415"></a><a name="ul97916871415"></a><ul id="ul97916871415"><li>是：集群将创建三个管理节点，当其中某两个管理节点故障时，集群依然可用。</li><li>否：集群仅创建一个管理节点，当这个管理节点故障时，集群将不可用，但已运行的工作负载不受影响。</li></ul>
    <div class="notice" id="note67979861410"><a name="note67979861410"></a><a name="note67979861410"></a><span class="noticetitle"> 注意： </span><div class="noticebody"><a name="ul1279710812141"></a><a name="ul1279710812141"></a><ul id="ul1279710812141"><li>集群一旦创建，便无法更改集群模式，需要重新创建集群才能调整。</li><li>针对开发和测试环境等对可靠性要求不高的场景，可根据需求选择是否开启<span class="uicontrol" id="uicontrol080416821415"><a name="uicontrol080416821415"></a><a name="uicontrol080416821415"></a>“高可用”</span>。针对生产环境，为提高集群容灾能力，建议开启<span class="uicontrol" id="uicontrol1804118111413"><a name="uicontrol1804118111413"></a><a name="uicontrol1804118111413"></a>“高可用”</span>。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row57972528509"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p1538501795514"><a name="p1538501795514"></a><a name="p1538501795514"></a>* 虚拟私有云</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p116393128265"><a name="p116393128265"></a><a name="p116393128265"></a>新建集群所在的虚拟私有云。</p>
    <p id="p1063941211266"><a name="p1063941211266"></a><a name="p1063941211266"></a>若没有可选虚拟私有云，单击<span class="uicontrol" id="uicontrol162261618154315"><a name="uicontrol162261618154315"></a><a name="uicontrol162261618154315"></a>“<span id="text112261418174320"><a name="text112261418174320"></a><a name="text112261418174320"></a>创建虚拟</span>私有云”</span>进行创建，操作步骤请参见<a href="创建混合集群.md#section725610233159">创建虚拟私有云</a>。</p>
    </td>
    </tr>
    <tr id="row65621280481"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p1679675214559"><a name="p1679675214559"></a><a name="p1679675214559"></a>* 所在子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p16639712132616"><a name="p16639712132616"></a><a name="p16639712132616"></a>节点运行的子网环境。</p>
    </td>
    </tr>
    <tr id="row1287951145211"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p136753085614"><a name="p136753085614"></a><a name="p136753085614"></a>* 网络模型</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><a name="ul19705159132810"></a><a name="ul19705159132810"></a><ul id="ul19705159132810"><li>容器隧道网络（Overlay）：基于VXLAN技术实现的Overlay容器网络。VXLAN是将以太网报文封装成UDP报文进行隧道传输。容器网络是承载于VPC网络之上的Overlay网络平面，具有付出少量隧道封装性能损耗，获得了通用性强、互通性强、高级特性支持全面（例如Network Policy网络隔离）的优势，可以满足大多数应用需求。</li><li>VPC网络：基于VPC网络的自定义路由，直接将容器网络承载于VPC网络之中。每个节点将会被分配固定大小的IP地址段。vpc-router网络由于没有隧道封装的消耗，容器网络性能相对于容器隧道网络有一定优势。vpc-router集群由于VPC路由中配置有容器网段与节点IP的路由，可以支持集群外直接访问容器实例等特殊场景。</li></ul>
    </td>
    </tr>
    <tr id="row7879171125217"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p134561388563"><a name="p134561388563"></a><a name="p134561388563"></a>* 容器网段</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p31209167171234"><a name="p31209167171234"></a><a name="p31209167171234"></a>请根据业务需求选择容器网段，确定容器网段后，容器实例将在规划的网段内分配IP。</p>
    <div class="notice" id="note1171212351935"><a name="note1171212351935"></a><a name="note1171212351935"></a><span class="noticetitle"> 注意： </span><div class="noticebody"><a name="ul10579113961"></a><a name="ul10579113961"></a><ul id="ul10579113961"><li>集群一旦创建，便无法更改容器网段，需要重新创建集群才能调整。</li><li>创建集群前，请提前规划好网段。不同集群使用相同的容器网段，会导致容器IP冲突，应用访问异常。</li><li>容器网段要设置合理的掩码，掩码决定集群内可用节点数量。集群中容器网段掩码设置不合适，会导致集群实际可用的节点较少。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row5298103814351"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p1429918380352"><a name="p1429918380352"></a><a name="p1429918380352"></a>服务网段</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p977633218244"><a name="p977633218244"></a><a name="p977633218244"></a>服务网段为kubernetes service ip网段，请根据业务需求选择该网段。</p>
    <div class="notice" id="note2837135211258"><a name="note2837135211258"></a><a name="note2837135211258"></a><span class="noticetitle"> 注意： </span><div class="noticebody"><a name="ul18837252152517"></a><a name="ul18837252152517"></a><ul id="ul18837252152517"><li>此参数仅支持1.11.7及以上版本的集群。</li><li>创建集群前，请提前规划好网段，集群一旦创建，便无法更改服务网段，需要重新创建集群才能调整。</li><li>服务网段要设置合理的掩码，掩码决定集群内可用service ip数量。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row322218685211"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p5713152655617"><a name="p5713152655617"></a><a name="p5713152655617"></a>认证方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p933784218111"><a name="p933784218111"></a><a name="p933784218111"></a>认证机制主要用于对集群下的资源做权限控制。例如A用户只能对某个命名空间下的应用有读写权限，B用户对集群下的资源只有读权限等等。</p>
    <a name="ul159513321026"></a><a name="ul159513321026"></a><ul id="ul159513321026"><li>若需要对集群进行权限控制，请勾选“认证能力增强”，选择“Authenticating Proxy”。请单击“CA根证书”后的“上传文件”，上传符合规范且合法的证书。角色权限控制的操作请参见<a href="集群管理权限控制.md">集群管理权限控制</a>。</li><li>IAM认证暂不支持。</li><li>RBAC：开启Kubernetes的RBAC功能，详情请参见<a href="https://kubernetes.io/docs/reference/access-authn-authz/rbac/" target="_blank" rel="noopener noreferrer">Kubernetes官方文档</a>。</li></ul>
    </td>
    </tr>
    <tr id="row102228617526"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p8169142911568"><a name="p8169142911568"></a><a name="p8169142911568"></a>集群描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p664014125268"><a name="p664014125268"></a><a name="p664014125268"></a>新建容器集群的描述信息。</p>
    </td>
    </tr>
    <tr id="row15978941125217"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p1077195045211"><a name="p1077195045211"></a><a name="p1077195045211"></a>高级配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p284112360275"><a name="p284112360275"></a><a name="p284112360275"></a>一些高级功能统一存放的位置，如果该区域（Region）不支持高级功能，则高级配置项隐藏。</p>
    <a name="ul2309153715491"></a><a name="ul2309153715491"></a><ul id="ul2309153715491"><li>暂不设置：选择后不对高级功能做任何设置。</li><li>现在设置：选择后显示高级功能，并可对其进行设置。目前支持对<span class="uicontrol" id="uicontrol1733381515219"><a name="uicontrol1733381515219"></a><a name="uicontrol1733381515219"></a>“服务转发模式”</span>和<span class="uicontrol" id="uicontrol161981316152012"><a name="uicontrol161981316152012"></a><a name="uicontrol161981316152012"></a>“多可用区”</span>功能配置。<p id="p1670793614204"><a name="p1670793614204"></a><a name="p1670793614204"></a><strong id="b1164483412229"><a name="b1164483412229"></a><a name="b1164483412229"></a>服务转发模式：</strong></p>
    <a name="ul13333115929"></a><a name="ul13333115929"></a><ul id="ul13333115929"><li>iptables：社区传统的kube-proxy模式。</li><li>ipvs：由华为主导开发并在社区获得广泛支持的kube-proxy模式，吞吐更高，速度更快。适用于大规模场景。</li></ul>
    </li></ul>
    </td>
    </tr>
    <tr id="row0148101717229"><td class="cellrowborder" valign="top" width="18.13%" headers="mcps1.2.3.1.1 "><p id="p79871037171719"><a name="p79871037171719"></a><a name="p79871037171719"></a>* 购买时长</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.87%" headers="mcps1.2.3.1.2 "><p id="p1991143711174"><a name="p1991143711174"></a><a name="p1991143711174"></a>若选择创建包年/包月的集群，请设置购买时长。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  创建节点。
    -   选择是否创建节点。
        -   是：为集群创建第一个节点。

            >![](public_sys-resources/icon-note.gif) **说明：**   
            >若需要使用服务网格能力，请选择“是“，至少创建一个节点以供控制面节点安装。  

        -   否：创建一个集群，不需要添加节点，请直接单击“下一步“，再单击“提交订单“。

    -   计费模式：支持按需计费和包年/包月类型。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >添加的第一个节点的付费方式只能是“按需付费”，若想要给集群添加付费方式为“包年/包月”的节点，请参考[新建节点（包年包月）](https://support.huaweicloud.com/usermanual-cce/cce_01_0003.html)操作。  

    -   当前区域：节点实例所在的物理位置。
    -   可用区：指在同一区域下，电力、网络隔离的物理区域，可用区之间内网互通，不同可用区之间物理隔离。
    -   节点名称：自定义节点名称。
    -   节点规格：请根据业务需求选择“GPU加速型“的节点规格。

        **图 2**  选择GPU节点规格<a name="fig715175671311"></a>  
        ![](figures/选择节点规格.png "选择节点规格")

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >为确保节点稳定性，系统会自动预留部分资源，运行必须的系统组件。详细请参见[节点预留资源计算公式](节点预留资源计算公式.md)。  

    -   操作系统：目前仅支持EulerOS 2.2。
    -   配置网络。弹性IP是独立申请的公网IP地址。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >若新增节点有互联网访问的需求，则弹性IP请选择“现在购买或使用已有“。若新增节点未绑定弹性IP，则在该节点上运行的工作负载将不能被外网访问。  

        -   暂不使用：不使用弹性IP的节点不能与互联网互通，仅可作为私有网络中部署业务或者集群所需云服务器进行使用。
        -   现在购买：自动为每台云服务器分配独享带宽的弹性IP。创建弹性云服务器过程中，请确保弹性IP配额充足。请根据界面要求，选择规格、购买量、计费模式、带宽等。
        -   使用已有：为当前节点分配已有弹性IP，请选择已有的弹性IP。

            **图 3**  配置节点网络<a name="fig1774223931914"></a>  
            ![](figures/配置节点网络.png "配置节点网络")


    -   设置节点磁盘空间，分为系统盘和数据盘。

        -   系统盘的规格为\[40,1024\]GB，用户可以配置，缺省值为40GB。
        -   数据盘的规格为\[100,32678\]GB，用户可以配置，缺省值为100GB。

        提供以下性能规格的云硬盘。

        -   普通IO：提供可靠的块存储，单个云硬盘的最大IOPS可达到1000，可运行关键应用程序。
        -   高IO：提供可达到3000的高IO和低至1 ms的读写延时，支持NoSQL/关系型数据库，数据仓库，文件系统等应用。
        -   超高IO：提供可达到20000的超高IO和低至1 ms超低读写时延，支持NoSQL/关系型数据库，数据仓库等应用。

        资源分配自定义：用户可自定义数据盘中Docker和Kubelet的资源占比，Docker资源包含Docker镜像数据以及镜像元数据，Kubelet资源包含Pod配置文件、密钥以及临时存储EmptyDir等挂载数据。

    -   选择登录方式。当前支持密码和密钥对。
        -   登录方式为“密码“：请输入登录节点的密码，并确认密码。请牢记该密码，登录节点时需要使用该密码。
        -   登录方式为“密钥对“：选择登录节点的密钥对。

            密钥对用于远程登录节点时的身份认证，若没有密钥对，可单击“创建密钥对”来新建。创建密钥对操作步骤请参见[创建密钥对](创建混合集群.md#section395546121513)。

            **图 4**  密钥对<a name="fig8513194014235"></a>  
            ![](figures/密钥对.jpg "密钥对")


    -   高级配置：当您有如下需求时，请单击“现在配置“，使用文件注入功能将文件注入到节点。

        -   需要通过脚本简化弹性云服务器配置。
        -   通过脚本初始化系统。
        -   已有脚本，在创建弹性云服务器时一并上传到服务器。
        -   其他可以使用脚本完成的事情。

        **操作步骤如下：**

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >详细的使用方法请参见[这里](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0013898301.html)。  

        1.  设置最大实例数。

            最大实例数是指节点允许创建的最大实例数（Pod），包含系统默认的实例，防止节点因管理过多的实例而负载过重。

        2.  单击“增加一个文件“。
        3.  输入保存路径或文件名：Linux系统请输入注入文件保存路径，例如 “/etc/foo.txt”，文件名只能包含字母和数字。
        4.  单击“选择文件“，选择已写好的脚本，脚本符合操作系统要求即可。

    -   设置节点购买数量。

        此处设置的节点数不能超过集群管理的最大节点规模，请根据业务需求选择。


5.  安装插件。

    系统资源插件必须要安装，高级功能插件可根据实际需求选择性进行安装。插件相关功能请参见[13-插件管理](https://support.huaweicloud.com/usermanual-cce/cce_01_0064.html)  。

6.  规格确认。

    确认所设置的服务选型参数好规格。

7.  单击“立即购买”，确认费用后，单击“提交”。

    集群创建预计需要6-10分钟。请根据界面提示查看集群创建过程。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   在集群创建完成页面中，可以通过选择“启用Istio服务网格“，在混合集群中使能Istio服务网格。详情请参见[5.2-启用服务网格](https://support.huaweicloud.com/usermanual-cce/cce_01_0036.html)。  
    >-   若选择创建包年包月的集群，请根据界面提示进行付款操作。  


