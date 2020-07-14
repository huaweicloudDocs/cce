# 创建有状态负载\(StatefulSet\)<a name="cce_01_0048"></a>

在运行过程中会保存数据或状态的工作负载称为“有状态工作负载（statefulset）”。例如Mysql，它需要存储产生的新数据。

因为容器可以在不同主机间迁移，所以在宿主机上并不会保存数据，这依赖于CCE提供的高可用存储卷，将存储卷挂载在容器上，从而实现有状态工作负载的数据持久化。

## 准备工作<a name="section1734962819219"></a>

-   在创建容器工作负载前，您需要存在一个可用集群。若没有请参照3.3-购买混合集群中内容创建。
-   若工作负载需要被外网访问，请确保集群中至少有一个节点已绑定弹性IP，或已购买负载均衡实例。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >创建多个工作负载时，请确保容器使用的端口不冲突 ，否则部署会失败。


## 通过控制台创建<a name="section16385130102112"></a>

云容器引擎提供了多种创建工作负载的方式，您可以通过如下方式进行创建：

1.  基于“Dockerhub官方镜像“创建工作负载，无需上传镜像。
2.  基于“我的镜像“创建工作负载，用户首先需要将镜像上传至容器镜像服务，上传镜像的方式请参考[镜像管理](https://support.huaweicloud.com/usermanual-swr/swr_01_0011.html)。
3.  基于“共享镜像“创建工作负载，即其它租户通过“容器镜像服务“共享给您的镜像。
4.  若您希望通过YAML方式创建工作负载，您可在“创建有状态工作负载”页面单击界面右侧的“YAML创建“，通过yaml的方式创建工作负载。YAML的说明请参见[通过kubectl命令行创建](#section113441881214)。YAML编写完成后，可单击“创建“，直接创建工作负载。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >YAML文件是和界面保持同步的，您也可界面和YAML互动完成工作负载的创建。例如界面中填写工作负载名称后，YAML文件会自动关联该名称。例如界面中添加完镜像后，YAML中也会自动关联该镜像。


1.  登录CCE控制台，在左侧导航栏中选择“工作负载 \> 有状态负载 StatefulSet”，单击“创建有状态工作负载”。在打开的创建有状态工作负载页面中，参照[表1](#table12741447488)设置工作负载基本信息，其中带“\*”标志的参数为必填参数。

    **表 1**  工作负载基本信息

    <a name="table12741447488"></a>
    <table><thead align="left"><tr id="cce_01_0047_row52758419481"><th class="cellrowborder" valign="top" width="23.07%" id="mcps1.2.3.1.1"><p id="cce_01_0047_p152759464816"><a name="cce_01_0047_p152759464816"></a><a name="cce_01_0047_p152759464816"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="76.92999999999999%" id="mcps1.2.3.1.2"><p id="cce_01_0047_p3275134114811"><a name="cce_01_0047_p3275134114811"></a><a name="cce_01_0047_p3275134114811"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="cce_01_0047_row18415163712618"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p32763416485"><a name="cce_01_0047_p32763416485"></a><a name="cce_01_0047_p32763416485"></a>* 工作负载名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p5276341485"><a name="cce_01_0047_p5276341485"></a><a name="cce_01_0047_p5276341485"></a>新建工作负载的名称，命名必须唯一。</p>
    <p id="cce_01_0047_p99562111597"><a name="cce_01_0047_p99562111597"></a><a name="cce_01_0047_p99562111597"></a>请输入4到63个字符的字符串，可以包含小写英文字母、数字和中划线（-），并以小写英文字母开头，小写英文字母或数字结尾。</p>
    </td>
    </tr>
    <tr id="cce_01_0047_row81437181202"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p514451811010"><a name="cce_01_0047_p514451811010"></a><a name="cce_01_0047_p514451811010"></a>* 集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p323714215492"><a name="cce_01_0047_p323714215492"></a><a name="cce_01_0047_p323714215492"></a>新建工作负载所在的集群。</p>
    </td>
    </tr>
    <tr id="cce_01_0047_row169810201307"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p19698152011011"><a name="cce_01_0047_p19698152011011"></a><a name="cce_01_0047_p19698152011011"></a>* 命名空间</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p12447336131710"><a name="cce_01_0047_p12447336131710"></a><a name="cce_01_0047_p12447336131710"></a>在单集群中，不同命名空间中的数据彼此隔离。使应用可以共享同个集群的服务，也能够互不干扰。若您不设置命名空间，系统会默认使用default命名空间。</p>
    </td>
    </tr>
    <tr id="cce_01_0047_row165805182316"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p45913512317"><a name="cce_01_0047_p45913512317"></a><a name="cce_01_0047_p45913512317"></a>* 实例数量</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p1042648123717"><a name="cce_01_0047_p1042648123717"></a><a name="cce_01_0047_p1042648123717"></a>工作负载的实例数量。工作负载可以有一个或多个实例，用户可以设置具体实例个数，默认为2，可自定义设置为1。</p>
    <p id="cce_01_0047_p17713926910"><a name="cce_01_0047_p17713926910"></a><a name="cce_01_0047_p17713926910"></a>每个工作负载实例都由相同的容器部署而成。设置多个实例主要用于实现高可靠性，当某个实例故障时，工作负载还能正常运行。若使用单实例，节点异常或实例异常会导致服务异常。</p>
    </td>
    </tr>
    <tr id="cce_01_0047_row1233713478354"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p15337247203514"><a name="cce_01_0047_p15337247203514"></a><a name="cce_01_0047_p15337247203514"></a>弹性网卡</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p476333074117"><a name="cce_01_0047_p476333074117"></a><a name="cce_01_0047_p476333074117"></a>Pod中的容器支持绑定弹性网卡，单击选中<span class="uicontrol" id="cce_01_0047_uicontrol187631230104117"><a name="cce_01_0047_uicontrol187631230104117"></a><a name="cce_01_0047_uicontrol187631230104117"></a>“绑定弹性网卡”</span>可以绑定已有的网络平面。更多网络平面信息请参见<a href="网络平面(NetworkAttachmentDefinition).md">网络平面(NetworkAttachmentDefinition)</a>。</p>
    <p id="cce_01_0047_p58611513174112"><a name="cce_01_0047_p58611513174112"></a><a name="cce_01_0047_p58611513174112"></a><strong id="cce_01_0047_b10861121314119"><a name="cce_01_0047_b10861121314119"></a><a name="cce_01_0047_b10861121314119"></a>仅v1.13.7-r0及以上版本且网络模型为VPC网络的混合集群才能绑定弹性网卡，不符合条件的集群将不显示<span class="uicontrol" id="cce_01_0047_uicontrol1986171319410"><a name="cce_01_0047_uicontrol1986171319410"></a><a name="cce_01_0047_uicontrol1986171319410"></a>“弹性网卡”</span>选项。</strong></p>
    <div class="note" id="cce_01_0047_note124412587394"><a name="cce_01_0047_note124412587394"></a><a name="cce_01_0047_note124412587394"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="cce_01_0047_ul1444165810398"></a><a name="cce_01_0047_ul1444165810398"></a><ul id="cce_01_0047_ul1444165810398"><li>网络平面是CCE新增的一种crd资源，记录了租户ID，子网ID，安全组等的配置项，作为申请弹性网卡的配置信息。</li><li>创建工作负载时，在<a href="创建无状态负载(Deployment).md#li3580132418215">设置工作负载访问方式</a>步骤中如果添加了节点级别的Service，将无法绑定弹性网卡；同理，绑定了弹性网卡的工作负载，将无法添加节点级别的Service。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="cce_01_0047_row18442191224514"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p244261214513"><a name="cce_01_0047_p244261214513"></a><a name="cce_01_0047_p244261214513"></a>时区同步</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p644215125454"><a name="cce_01_0047_p644215125454"></a><a name="cce_01_0047_p644215125454"></a>勾选<span class="uicontrol" id="cce_01_0047_uicontrol3743418174611"><a name="cce_01_0047_uicontrol3743418174611"></a><a name="cce_01_0047_uicontrol3743418174611"></a>“开启”</span>，容器将和节点使用相同时区。</p>
    <div class="notice" id="cce_01_0047_note5422953172616"><a name="cce_01_0047_note5422953172616"></a><a name="cce_01_0047_note5422953172616"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><p id="cce_01_0047_p11422145392614"><a name="cce_01_0047_p11422145392614"></a><a name="cce_01_0047_p11422145392614"></a>时区同步功能开启后，在<span class="uicontrol" id="cce_01_0047_uicontrol107671854164714"><a name="cce_01_0047_uicontrol107671854164714"></a><a name="cce_01_0047_uicontrol107671854164714"></a>“数据存储 &gt; 本地磁盘”</span>中，将会自动添加HostPath类型的磁盘，请勿修改删除该磁盘。</p>
    </div></div>
    </td>
    </tr>
    <tr id="cce_01_0047_row15877104919019"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p4877104910012"><a name="cce_01_0047_p4877104910012"></a><a name="cce_01_0047_p4877104910012"></a>CCI弹性承载</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p187282214438"><a name="cce_01_0047_p187282214438"></a><a name="cce_01_0047_p187282214438"></a>勾选此选项后，当集群资源不足时，支持将Pod部署到CCI集群。</p>
    <p id="cce_01_0047_p11595204219"><a name="cce_01_0047_p11595204219"></a><a name="cce_01_0047_p11595204219"></a><strong id="cce_01_0047_b17562201711376"><a name="cce_01_0047_b17562201711376"></a><a name="cce_01_0047_b17562201711376"></a>该参数仅在安装virtual kubelet插件后才显示</strong>，具体请参见<a href="virtual-kubelet.md">virtual kubelet</a>。</p>
    </td>
    </tr>
    <tr id="cce_01_0047_row1027719414818"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p1527715418485"><a name="cce_01_0047_p1527715418485"></a><a name="cce_01_0047_p1527715418485"></a>工作负载描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p827734134817"><a name="cce_01_0047_p827734134817"></a><a name="cce_01_0047_p827734134817"></a>工作负载描述信息。</p>
    </td>
    </tr>
    </tbody>
    </table>

2.  单击“下一步：容器设置“，添加容器。
    1.  单击“添加容器“，选择需要部署的镜像。
        -   **我的镜像：**展示了您创建的所有镜像仓库。
        -   **Dockerhub官方镜像：**展示了Dockerhub仓库中的官方镜像。
        -   **第三方镜像：**CCE支持拉取第三方镜像仓库（即镜像仓库与Dockerhub之外的镜像仓库）的镜像创建工作负载。使用第三方镜像时，请确保工作负载运行的节点可访问公网。第三方镜像的具体使用方法请参见[如何使用第三方镜像](如何使用第三方镜像.md)。
            -   若您的镜像仓库不需要认证，密钥认证请选择“否“，并输入“镜像地址“，单击“确定“。
            -   若您的镜像仓库都必须经过认证（帐号密码）才能访问，您需要先创建密钥再使用第三方镜像，具体操作请参见[如何使用第三方镜像](如何使用第三方镜像.md)。

        -   **共享镜像：**其它租户通过“容器镜像服务“共享给您的镜像将在此处展示，您可以基于共享镜像创建工作负载。

    2.  配置镜像基本信息。

        工作负载是Kubernetes对一组Pod的抽象模型，用于描述业务的运行载体，一个Pod可以封装1个或多个容器，您可以单击右上方的“添加容器”，添加多个容器镜像并分别进行设置。

        **表 2**  镜像参数说明

        <a name="table14155182113372"></a>
        <table><thead align="left"><tr id="cce_01_0047_row0282348486"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.3.1.1"><p id="cce_01_0047_p3282147483"><a name="cce_01_0047_p3282147483"></a><a name="cce_01_0047_p3282147483"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="77%" id="mcps1.2.3.1.2"><p id="cce_01_0047_p1828244144819"><a name="cce_01_0047_p1828244144819"></a><a name="cce_01_0047_p1828244144819"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="cce_01_0047_row1844916557597"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p182837474815"><a name="cce_01_0047_p182837474815"></a><a name="cce_01_0047_p182837474815"></a>镜像名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p3283134134820"><a name="cce_01_0047_p3283134134820"></a><a name="cce_01_0047_p3283134134820"></a>导入的镜像，您可单击<span class="uicontrol" id="cce_01_0047_uicontrol1217815019463"><a name="cce_01_0047_uicontrol1217815019463"></a><a name="cce_01_0047_uicontrol1217815019463"></a>“更换镜像”</span>进行更换。</p>
        </td>
        </tr>
        <tr id="cce_01_0047_row338117362515"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p1038143616517"><a name="cce_01_0047_p1038143616517"></a><a name="cce_01_0047_p1038143616517"></a>* 镜像版本</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p1338110368519"><a name="cce_01_0047_p1338110368519"></a><a name="cce_01_0047_p1338110368519"></a>若选择Dockerhub官方镜像，请选择需要部署的镜像版本。</p>
        </td>
        </tr>
        <tr id="cce_01_0047_row32839494813"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p122831140486"><a name="cce_01_0047_p122831140486"></a><a name="cce_01_0047_p122831140486"></a>* 容器名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p528314415486"><a name="cce_01_0047_p528314415486"></a><a name="cce_01_0047_p528314415486"></a>容器的名称，可修改。</p>
        </td>
        </tr>
        <tr id="cce_01_0047_row1449911299503"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p53374336504"><a name="cce_01_0047_p53374336504"></a><a name="cce_01_0047_p53374336504"></a>特权容器</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p49887211526"><a name="cce_01_0047_p49887211526"></a><a name="cce_01_0047_p49887211526"></a>特权容器是指容器里面的程序具有一定的特权。</p>
        <p id="cce_01_0047_p65001729105011"><a name="cce_01_0047_p65001729105011"></a><a name="cce_01_0047_p65001729105011"></a>若选中，容器将获得超级权限，例如可以操作宿主机上面的网络设备、修改内核参数等。</p>
        </td>
        </tr>
        <tr id="cce_01_0047_row152831345485"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p875325925918"><a name="cce_01_0047_p875325925918"></a><a name="cce_01_0047_p875325925918"></a>容器规格</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p5379182494610"><a name="cce_01_0047_p5379182494610"></a><a name="cce_01_0047_p5379182494610"></a><strong id="cce_01_0047_b2155195713314"><a name="cce_01_0047_b2155195713314"></a><a name="cce_01_0047_b2155195713314"></a>CPU配额：</strong></p>
        <a name="cce_01_0047_ul67283495467"></a><a name="cce_01_0047_ul67283495467"></a><ul id="cce_01_0047_ul67283495467"><li>申请：容器需要使用的最小CPU值，默认0.25Core。</li><li>限制：允许容器使用的CPU最大值。建议设容器配额的最高限额，避免容器资源超额导致系统故障。</li></ul>
        <p id="cce_01_0047_p633394210502"><a name="cce_01_0047_p633394210502"></a><a name="cce_01_0047_p633394210502"></a><strong id="cce_01_0047_b5114173113411"><a name="cce_01_0047_b5114173113411"></a><a name="cce_01_0047_b5114173113411"></a>内存配额：</strong></p>
        <a name="cce_01_0047_ul14326165915010"></a><a name="cce_01_0047_ul14326165915010"></a><ul id="cce_01_0047_ul14326165915010"><li>申请：容器需要使用的内存最小值，默认512MiB。</li><li>限制：允许容器使用的内存最大值。如果超过，容器会被终止。</li></ul>
        <p id="cce_01_0047_p1825119142351"><a name="cce_01_0047_p1825119142351"></a><a name="cce_01_0047_p1825119142351"></a>申请和限制的具体请参见<a href="设置容器规格.md">设置容器规格</a>。</p>
        <p id="cce_01_0047_p38521896343"><a name="cce_01_0047_p38521896343"></a><a name="cce_01_0047_p38521896343"></a><strong id="cce_01_0047_b11557151512341"><a name="cce_01_0047_b11557151512341"></a><a name="cce_01_0047_b11557151512341"></a>GPU配额：</strong>当集群中包含GPU节点时，才能设置GPU，无GPU节点不显示此选项。</p>
        <p id="cce_01_0047_p15403132914341"><a name="cce_01_0047_p15403132914341"></a><a name="cce_01_0047_p15403132914341"></a>容器需要使用的GPU百分比。勾选<span class="uicontrol" id="cce_01_0047_uicontrol952171455614"><a name="cce_01_0047_uicontrol952171455614"></a><a name="cce_01_0047_uicontrol952171455614"></a>“使用”</span>并设置百分比，例如设置为10%，表示该容器需使用GPU资源的10%。若不勾选<span class="uicontrol" id="cce_01_0047_uicontrol12950184715612"><a name="cce_01_0047_uicontrol12950184715612"></a><a name="cce_01_0047_uicontrol12950184715612"></a>“使用”</span>，或设置为0，则无法使用GPU资源。</p>
        <p id="cce_01_0047_p9626154413340"><a name="cce_01_0047_p9626154413340"></a><a name="cce_01_0047_p9626154413340"></a><strong id="cce_01_0047_b423894943411"><a name="cce_01_0047_b423894943411"></a><a name="cce_01_0047_b423894943411"></a>GPU显卡：</strong>工作负载实例将被调度到GPU显卡类型为指定显卡的节点上。</p>
        <p id="cce_01_0047_p15765438173416"><a name="cce_01_0047_p15765438173416"></a><a name="cce_01_0047_p15765438173416"></a>若勾选“不限制”，容器将会随机使用节点中的任一显卡。您也可以勾选某个显卡，容器将使用特定显卡。</p>
        <p id="cce_01_0047_p58663964520"><a name="cce_01_0047_p58663964520"></a><a name="cce_01_0047_p58663964520"></a><strong id="cce_01_0047_b188666944516"><a name="cce_01_0047_b188666944516"></a><a name="cce_01_0047_b188666944516"></a>昇腾&nbsp;310配额：</strong>容器需要使用的昇腾 310芯片个数，此处须为整数。</p>
        <p id="cce_01_0047_p2097772173513"><a name="cce_01_0047_p2097772173513"></a><a name="cce_01_0047_p2097772173513"></a>选用AI加速型节点并安装<strong id="cce_01_0047_b99085210250"><a name="cce_01_0047_b99085210250"></a><a name="cce_01_0047_b99085210250"></a>huawei-npu</strong>插件后该参数设置将生效。AI加速型节点目前已开放公测，该节点搭载高性能、低功耗的海思Ascend 310 AI处理器，适用于图像识别、视频处理、推理计算以及机器学习等场景，点此可<a href="https://account.huaweicloud.com/usercenter/#/userindex/betaManagement?serviceCode=ecs_ascend_ai1" target="_blank" rel="noopener noreferrer">立即申请</a>。</p>
        </td>
        </tr>
        </tbody>
        </table>

    3.  **生命周期：**用于设置容器启动和运行时需要执行的命令。
        -   启动命令：设置容器启动时执行的命令，具体请参见[设置容器启动命令](设置容器启动命令.md)。
        -   启动后处理：设置容器成功运行后执行的命令，详细配置方法请参见[设置容器生命周期](设置容器生命周期.md)。
        -   停止前处理：设置容器结束前执行的命令，通常用于删除日志/临时文件等，详细配置方法请参见[设置容器生命周期](设置容器生命周期.md)。

    4.  **健康检查：**CCE提供了存活与业务两种探针，用于判断容器和用户业务是否正常运行。详细配置方法请参见[设置容器健康检查](设置容器健康检查.md)。
        -   工作负载存活探针：检查容器是否正常，不正常则重启实例。
        -   工作负载业务探针：检查用户业务是否就绪，不就绪则不转发流量到当前实例。

    5.  **环境变量：**在容器中添加环境变量，一般用于通过环境变量设置参数。

        在“环境变量“页签，单击“添加环境变量“，当前支持三种类型：

        -   手动添加：输入变量名称、变量/变量引用。
        -   密钥导入：输入变量名称，选择导入的密钥名称和数据。您需要提前创建密钥，具体请参见[创建密钥](创建密钥.md)。
        -   配置项导入：输入变量名称，选择导入的配置项名称和数据。您需要提前创建配置项，具体请参见[创建配置项](创建配置项.md)。

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >对于已设置的环境变量，单击环境变量后的“编辑”，可对该环境变量进行编辑。单击环境变量后的“删除”，可删除该环境变量。


    6.  **数据存储：**给容器挂载数据存储，支持本地磁盘和云存储，适用于需持久化存储、高磁盘IO等场景。具体请参见[使用本地磁盘存储](使用本地磁盘存储.md)、[使用文件存储卷](使用文件存储卷.md)、[使用对象存储卷](使用对象存储卷.md)、[使用极速文件存储卷](使用极速文件存储卷.md)。
    7.  **安全设置：**对容器权限进行设置，保护系统和其他容器不受其影响。

        请输入用户ID，容器将以当前用户权限运行。

    8.  **容器日志：**设置容器日志采集策略、配置日志目录。用于收集容器日志便于统一管理和分析。详细配置请参见[采集容器标准输出日志](采集容器标准输出日志.md)、[采集容器内路径日志](采集容器内路径日志.md)。

3.  单击“下一步：工作负载访问设置“，设置“实例间发现服务“和工作负载访问方式。

    **设置“实例间发现服务“**，如[表3](#table2293204814496)。

    **表 3**  参数配置

    <a name="table2293204814496"></a>
    <table><thead align="left"><tr id="row4293184813490"><th class="cellrowborder" valign="top" width="18%" id="mcps1.2.3.1.1"><p id="p1929315489491"><a name="p1929315489491"></a><a name="p1929315489491"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="82%" id="mcps1.2.3.1.2"><p id="p11293948134919"><a name="p11293948134919"></a><a name="p11293948134919"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row9293194864911"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p229384818497"><a name="p229384818497"></a><a name="p229384818497"></a>服务名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p1229313484495"><a name="p1229313484495"></a><a name="p1229313484495"></a>输入工作负载所对应的服务名称，用于集群内工作负载间的互相访问。该服务主要用于实例的内部发现，不需要有单独的IP地址，也不需要做负载均衡。</p>
    </td>
    </tr>
    <tr id="row15293748104915"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p6293144814912"><a name="p6293144814912"></a><a name="p6293144814912"></a>端口名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p9293144884912"><a name="p9293144884912"></a><a name="p9293144884912"></a>端口名称用于给容器端口命名，通常以端口用途命名。</p>
    </td>
    </tr>
    <tr id="row1129313489499"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p1829304834913"><a name="p1829304834913"></a><a name="p1829304834913"></a>容器端口</p>
    </td>
    <td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p42931448114914"><a name="p42931448114914"></a><a name="p42931448114914"></a>输入容器的监听端口。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **单击“添加服务”，设置工作负载访问方式。**

    若工作负载需要和其它服务互访，或需要被公网访问，您需要添加服务，设置工作负载访问方式。

    工作负载访问的方式决定了这个工作负载的网络属性，不同访问方式的工作负载可以提供不同网络能力，具体请参见[网络概述](网络概述.md)。

4.  单击“下一步：高级配置“，配置更多高级策略。
    -   升级策略：仅支持“滚动升级“。
        -   滚动升级：将逐步用新版本的实例替换旧版本的实例，升级的过程中，业务流量会同时负载均衡分布到新老的实例上，因此业务不会中断。
            -   最大无效实例数：每次滚动升级允许的最大无效实例数，如果等于实例数有断服风险（最小存活实例数 = 实例数 - 最大无效实例数）。

    -   实例管理策略：支持“有序策略“和“并行策略“两种。

        有序策略：默认策略，有状态负载会逐个的、按顺序的进行部署、删除、伸缩实例， 只有前一个实例部署Ready或删除完成后，有状态负载才会操作后一个实例。

        并行策略：支持有状态负载并行创建或删除所有的实例，有状态负载发生变更时立刻在实例上生效。

    -   **缩容策略：**为工作负载删除提供一个时间窗，预留给生命周期中PreStop阶段执行命令。若超过此时间窗，进程仍未停止，该工作负载将被强制删除。
        -   缩容时间窗 \(s\)：请输入时间，该时间为工作负载停止前命令的执行时间窗（0-9999秒），默认30秒。
        -   缩容优先级：可根据业务需要选择“优先减少新实例“或“优先减少老实例“。

    -   **调度策略：**你可以根据需要自由组合静态的全局调度策略或动态的运行时调度策略来实现自己的需求。具体请参见[调度策略概述](调度策略概述.md)。
    -   **Pod高级设置**

        -   Pod标签：内置app标签在工作负载创建时指定，主要用于设置亲和性与反亲和性调度，暂不支持修改。您可以单击下方的“添加标签“增加标签。

        **图 1**  Pod高级设置<a name="cce_01_0047_fig2225829163110"></a>  
        ![](figures/Pod高级设置.png "Pod高级设置")

    -   **客户端DNS配置**：CCE集群内置DNS插件CoreDNS，为集群内的工作负载提供域名解析服务。详细使用方法请参见[Kubernetes集群内置DNS配置说明](Kubernetes集群内置DNS配置说明.md)。
        -   DNS策略：
            -   追加域名解析配置：选择该配置后，将保留默认配置，以下“IP地址“和“搜索域“配置可能不生效。
            -   替换域名解析配置：选择该配置后，将仅使用以下“IP地址“和“搜索域“配置进行域名解析。
            -   继承Pod所在节点域名解析配置：将继承Pod所在节点的域名解析配置。

        -   IP地址：您可对自定义的域名配置域名服务器，值为一个或一组DNS IP地址，如“1.2.3.4”。
        -   搜索域：定义域名的搜索域列表，当访问的域名不能被DNS解析时，会把该域名与搜索域列表中的域依次进行组合，并重新向DNS发起请求，直到域名被正确解析或者尝试完搜索域列表为止。
        -   超时时间（s）：查询超时时间，请自定义。
        -   ndots：表示域名中必须出现的“.”的个数，如果域名中的“.”的个数不小于ndots，则该域名为一个FQDN，操作系统会直接查询；如果域名中的“.”的个数小于ndots，操作系统会在搜索域中进行查询。

    -   **自定义指标监控：**是指监控系统提供的一种指标收集机制，该机制允许工作负载在部署时自定义需要上报的指标名称以及获取这些指标数据的接入点信息，在应用运行时由监控系统按固定的频率访问接入点进行指标的收集。详细请参见[对接Prometheus实现自定义指标监控](对接Prometheus实现自定义指标监控.md)。
    -   **性能管理配置：**华为云的性能管理服务可协助您快速进行工作负载的问题定位与性能瓶颈分析。详细请参见[性能管理配置（性能瓶颈分析）](性能管理配置（性能瓶颈分析）.md)。

5.  配置完成后，单击“创建”，单击“返回工作负载列表”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   在工作负载列表中，当工作负载状态为“运行中”时，表示工作负载创建成功。如果工作负载状态未实时更新，请单击右上角的![](figures/zh-cn_image_0172679846.png)图标或按F5刷新页面查看。
    >-   节点不可用时，pod状态变为“未就绪“，此时需要手工删除有状态工作负载的pod，pod实例才会迁移到正常节点上。
    >-   工作负载列表页在超过500条以上时，将采用Kubernetes的分页机制进行分页。Kubernetes的分页机制：仅支持回到第一页和查看下一页，不支持查看上一页，且在分页显示的情况下，资源总数显示的是批量查询出的数目而不是真实总数。


## 通过kubectl命令行创建<a name="section113441881214"></a>

本节以etcd为例来进行说明。

**前提条件**

请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令，使弹性云服务器连接集群。

**操作步骤**

1.  登录已配置好kubectl命令的弹性云服务器。登录方法请参见[登录Linux弹性云服务器](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0013771089.html)。
2.  创建一个名为etcd-statefulset.yaml的文件。

    其中，etcd-statefulset.yaml为自定义名称，您可以随意命名。

    **vi etcd-statefulset.yaml**

    以下内容仅为示例，若需要了解statefulset的详细内容，请参考[kubernetes官方文档](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)。

    ```
    apiVersion: apps/v1beta1
    kind: StatefulSet
    metadata:
      name: etcd
    spec:
      replicas: 2
      selector:
        matchLabels:
          app: etcd
      serviceName: etcd-svc
      template:
        metadata:
          labels:
            app: etcd
        spec:
          containers:
          - env:
            - name: PAAS_APP_NAME
              value: tesyhhj
            - name: PAAS_NAMESPACE
              value: default
            - name: PAAS_PROJECT_ID
              value: 9632fae707ce4416a0ab1e3e121fe555
            image: etcd
            imagePullPolicy: IfNotPresent
            name: container-0
      updateStrategy:
        type: RollingUpdate
    ```

    **vi etcd-headless.yaml**

    ```
    apiVersion: v1
    kind: Service
    metadata:
      labels:
        app: etcd
      name: etcd-svc
    spec:
      clusterIP: None
      ports:
      - name: etcd-svc
        port: 3120
        protocol: TCP
        targetPort: 3120
      selector:
        app: etcd
      sessionAffinity: None
      type: ClusterIP
    ```

3.  创建工作负载以及对应headless服务。

    **kubectl create -f etcd-statefulset.yaml**

    回显如下，表示有状态工作负载（stateful）已创建成功。

    ```
    statefulset.apps/etcd created
    ```

    **kubectl create -f  **etcd-headless**.yaml**

    回显如下，表示对应headless服务已创建成功。

    ```
    service/etcd-svc created
    ```

4.  若工作负载需要被访问（集群内访问或节点访问），您需要设置访问方式，具体请参见[网络管理](网络管理.md)创建对应服务。

