# 创建无状态负载\(Deployment\)<a name="cce_01_0047"></a>

在运行中始终不保存任何数据或状态的工作负载称为“无状态负载 Deployment”，例如nginx。

## 准备工作<a name="section7271245481"></a>

-   在创建容器工作负载前，您需要存在一个可用集群。若没有可用集群 ，请参照[购买混合集群](购买混合集群.md)中内容创建。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >创建多个容器的工作负载时，请确保容器使用的端口不冲突 ，否则部署会失败。  

-   若工作负载需要被外网访问，请确保集群中至少有一个节点已绑定弹性IP，或已购买负载均衡实例。

## 通过控制台创建<a name="section1996635141916"></a>

云容器引擎提供了多种创建工作负载的方式，您可以通过如下方式进行创建：

-   基于“Dockerhub官方镜像“创建工作负载，无需上传镜像。
-   基于“我的镜像“创建工作负载，用户首先需要将镜像上传至容器镜像服务，上传镜像的方式请参考[镜像管理](https://support.huaweicloud.com/usermanual-swr/swr_01_0011.html)
-   基于“共享镜像“创建工作负载，即其它租户通过“容器镜像服务“共享给您的镜像。
-   您希望通过YAML方式创建工作负载，您可在“创建无状态工作负载”页面单击界面右侧的“YAML创建“，通过yaml的方式创建工作负载。YAML的说明请参见[表3](#table132326831016)。YAML编写完成后，可单击“创建“，直接创建工作负载。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >YAML文件是和界面保持同步的，您也可界面和YAML互动完成工作负载的创建。例如界面中填写工作负载名称后，YAML文件会自动关联该名称。例如界面中添加完镜像后，YAML中也会自动关联该镜像。  


1.  登录CCE控制台，在左侧导航栏中选择“工作负载 \> 无状态负载 Deployment”，单击“创建无状态工作负载”。参照[表1](#table12741447488)设置工作负载基本信息，其中带“\*”标志的参数为必填参数。

    **表 1**  工作负载基本信息

    <a name="table12741447488"></a>
    <table><thead align="left"><tr id="row52758419481"><th class="cellrowborder" valign="top" width="23.07%" id="mcps1.2.3.1.1"><p id="p152759464816"><a name="p152759464816"></a><a name="p152759464816"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="76.92999999999999%" id="mcps1.2.3.1.2"><p id="p3275134114811"><a name="p3275134114811"></a><a name="p3275134114811"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row18415163712618"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="p32763416485"><a name="p32763416485"></a><a name="p32763416485"></a>* 工作负载名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="p5276341485"><a name="p5276341485"></a><a name="p5276341485"></a>新建工作负载的名称，命名必须唯一。</p>
    </td>
    </tr>
    <tr id="row81437181202"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="p514451811010"><a name="p514451811010"></a><a name="p514451811010"></a>* 集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="p323714215492"><a name="p323714215492"></a><a name="p323714215492"></a>新建工作负载所在的集群。</p>
    </td>
    </tr>
    <tr id="row169810201307"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="p19698152011011"><a name="p19698152011011"></a><a name="p19698152011011"></a>* 命名空间</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="p12447336131710"><a name="p12447336131710"></a><a name="p12447336131710"></a>在单集群中，不同命名空间中的数据彼此隔离。使应用可以共享同个集群的服务，也能够互不干扰。若您不设置命名空间，系统会默认使用default命名空间。</p>
    </td>
    </tr>
    <tr id="row165805182316"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="p45913512317"><a name="p45913512317"></a><a name="p45913512317"></a>* 实例数量</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="p1042648123717"><a name="p1042648123717"></a><a name="p1042648123717"></a>工作负载的实例数量。工作负载可以有一个或多个实例，用户可以设置具体实例个数，默认为2，可自定义设置为1。</p>
    <p id="p17713926910"><a name="p17713926910"></a><a name="p17713926910"></a>每个工作负载实例都由相同的容器部署而成。设置多个实例主要用于实现高可靠性，当某个实例故障时，工作负载还能正常运行。若使用单实例，节点异常或实例异常会导致服务异常。</p>
    </td>
    </tr>
    <tr id="row18442191224514"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="p244261214513"><a name="p244261214513"></a><a name="p244261214513"></a>时区同步</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="p644215125454"><a name="p644215125454"></a><a name="p644215125454"></a>勾选<span class="uicontrol" id="uicontrol3743418174611"><a name="uicontrol3743418174611"></a><a name="uicontrol3743418174611"></a>“开启”</span>，容器将和节点使用相同时区。</p>
    <div class="notice" id="note5422953172616"><a name="note5422953172616"></a><a name="note5422953172616"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><p id="p11422145392614"><a name="p11422145392614"></a><a name="p11422145392614"></a>时区同步功能开启后，在<span class="uicontrol" id="uicontrol107671854164714"><a name="uicontrol107671854164714"></a><a name="uicontrol107671854164714"></a>“数据存储 &gt; 本地磁盘”</span>中，将会自动添加HostPath类型的磁盘，请勿修改删除该磁盘。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row15877104919019"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="p4877104910012"><a name="p4877104910012"></a><a name="p4877104910012"></a>CCI弹性承载</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="p11595204219"><a name="p11595204219"></a><a name="p11595204219"></a><strong id="b17562201711376"><a name="b17562201711376"></a><a name="b17562201711376"></a>该参数仅在安装virtual kubelet插件后才显示</strong>，具体请参见<a href="virtual-kubelet.md">virtual kubelet</a>。</p>
    <p id="p118778495016"><a name="p118778495016"></a><a name="p118778495016"></a>勾选此选项后，当集群资源不足时，支持将Pod部署到CCI集群。</p>
    </td>
    </tr>
    <tr id="row1027719414818"><td class="cellrowborder" valign="top" width="23.07%" headers="mcps1.2.3.1.1 "><p id="p1527715418485"><a name="p1527715418485"></a><a name="p1527715418485"></a>工作负载描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.92999999999999%" headers="mcps1.2.3.1.2 "><p id="p827734134817"><a name="p827734134817"></a><a name="p827734134817"></a>工作负载描述信息。</p>
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

        <a name="table128216444815"></a>
        <table><thead align="left"><tr id="row0282348486"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.3.1.1"><p id="p3282147483"><a name="p3282147483"></a><a name="p3282147483"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="77%" id="mcps1.2.3.1.2"><p id="p1828244144819"><a name="p1828244144819"></a><a name="p1828244144819"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1844916557597"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="p182837474815"><a name="p182837474815"></a><a name="p182837474815"></a>镜像名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="p3283134134820"><a name="p3283134134820"></a><a name="p3283134134820"></a>导入的镜像，您可单击<span class="uicontrol" id="uicontrol1217815019463"><a name="uicontrol1217815019463"></a><a name="uicontrol1217815019463"></a>“更换镜像”</span>进行更换。</p>
        </td>
        </tr>
        <tr id="row338117362515"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="p1038143616517"><a name="p1038143616517"></a><a name="p1038143616517"></a>* 镜像版本</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="p1338110368519"><a name="p1338110368519"></a><a name="p1338110368519"></a>若选择Dockerhub官方镜像，请选择需要部署的镜像版本。</p>
        </td>
        </tr>
        <tr id="row32839494813"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="p122831140486"><a name="p122831140486"></a><a name="p122831140486"></a>* 容器名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="p528314415486"><a name="p528314415486"></a><a name="p528314415486"></a>容器的名称，可修改。</p>
        </td>
        </tr>
        <tr id="row1449911299503"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="p53374336504"><a name="p53374336504"></a><a name="p53374336504"></a>特权容器</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="p49887211526"><a name="p49887211526"></a><a name="p49887211526"></a>特权容器是指容器里面的程序具有一定的特权。</p>
        <p id="p65001729105011"><a name="p65001729105011"></a><a name="p65001729105011"></a>若选中，容器将获得超级权限，例如可以操作宿主机上面的网络设备、修改内核参数等。</p>
        </td>
        </tr>
        <tr id="row152831345485"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="p875325925918"><a name="p875325925918"></a><a name="p875325925918"></a>容器规格</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="p5379182494610"><a name="p5379182494610"></a><a name="p5379182494610"></a><strong id="b2155195713314"><a name="b2155195713314"></a><a name="b2155195713314"></a>CPU配额：</strong></p>
        <a name="ul67283495467"></a><a name="ul67283495467"></a><ul id="ul67283495467"><li>申请：容器需要使用的最小CPU值，默认0.25Core。</li><li>限制：允许容器使用的CPU最大值。建议设容器配额的最高限额，避免容器资源超额导致系统故障。</li></ul>
        <p id="p633394210502"><a name="p633394210502"></a><a name="p633394210502"></a><strong id="b5114173113411"><a name="b5114173113411"></a><a name="b5114173113411"></a>内存配额：</strong></p>
        <a name="ul14326165915010"></a><a name="ul14326165915010"></a><ul id="ul14326165915010"><li>申请：容器需要使用的内存最小值，默认512MiB。</li><li>限制：允许容器使用的内存最大值。如果超过，容器会被终止。</li></ul>
        <p id="p1825119142351"><a name="p1825119142351"></a><a name="p1825119142351"></a>申请和限制的具体请参见<a href="设置容器规格.md">设置容器规格</a>。</p>
        <p id="p38521896343"><a name="p38521896343"></a><a name="p38521896343"></a><strong id="b11557151512341"><a name="b11557151512341"></a><a name="b11557151512341"></a>GPU配额：</strong>当集群中包含GPU节点时，才能设置GPU，无GPU节点不显示此选项。</p>
        <p id="p15403132914341"><a name="p15403132914341"></a><a name="p15403132914341"></a>容器需要使用的GPU百分比。勾选<span class="uicontrol" id="uicontrol952171455614"><a name="uicontrol952171455614"></a><a name="uicontrol952171455614"></a>“使用”</span>并设置百分比，例如设置为10%，表示该容器需使用GPU资源的10%。若不勾选<span class="uicontrol" id="uicontrol12950184715612"><a name="uicontrol12950184715612"></a><a name="uicontrol12950184715612"></a>“使用”</span>，或设置为0，则无法使用GPU资源。</p>
        <p id="p9626154413340"><a name="p9626154413340"></a><a name="p9626154413340"></a><strong id="b423894943411"><a name="b423894943411"></a><a name="b423894943411"></a>GPU显卡：</strong>工作负载实例将被调度到GPU显卡类型为指定显卡的节点上。</p>
        <p id="p15765438173416"><a name="p15765438173416"></a><a name="p15765438173416"></a>若勾选“不限制”，容器将会随机使用节点中的任一显卡。您也可以勾选某个显卡，容器将使用特定显卡。</p>
        <p id="p58663964520"><a name="p58663964520"></a><a name="p58663964520"></a><strong id="b188666944516"><a name="b188666944516"></a><a name="b188666944516"></a>昇腾&nbsp;310配额：</strong>容器需要使用的昇腾 310芯片个数，此处须为整数。</p>
        <p id="p2097772173513"><a name="p2097772173513"></a><a name="p2097772173513"></a>选用AI加速型节点并安装<strong id="b99085210250"><a name="b99085210250"></a><a name="b99085210250"></a>huawei-npu</strong>插件后该参数设置将生效。AI加速型节点目前已开放公测，该实例搭载高性能、低功耗的海思Ascend 310 AI处理器，适用于图像识别、视频处理、推理计算以及机器学习等场景，点此可<a href="https://account.huaweicloud.com/usercenter/#/userindex/betaManagement?serviceCode=ecs_ascend_ai1" target="_blank" rel="noopener noreferrer">立即申请</a>。</p>
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

3.  <a name="li3580132418215"></a>单击“下一步：工作负载访问设置“，单击“添加服务“，设置工作负载访问方式。

    若工作负载需要和其它服务互访，或需要被公网访问，您需要添加服务，设置工作负载访问方式。

    工作负载访问的方式决定了这个工作负载的网络属性，不同访问方式的工作负载可以提供不同网络能力，具体请参见[网络概述](网络概述.md)。

4.  单击“下一步：高级设置“，配置更多高级策略。
    -   **升级策略：**你可以指定无状态工作负载的升级方式，包括逐步“滚动升级“和整体“替换升级“。
        -   滚动升级：将逐步用新版本的实例替换旧版本的实例，升级的过程中，业务流量会同时负载均衡分布到新老的实例上，因此业务不会中断。
            -   最大无效实例数：每次滚动升级允许的最大无效实例数，如果等于实例数有断服风险（最小存活实例数 = 实例数 - 最大无效实例数）。

        -   替换升级：将先把您工作负载的老版本实例删除，再安装指定的新版本，升级过程中业务会中断。

    -   **缩容策略：**为工作负载删除提供一个时间窗，预留给生命周期中PreStop阶段执行命令。若超过此时间窗，进程仍未停止，该工作负载将被强制删除。
        -   缩容时间窗 \(s\)：请输入时间，该时间为工作负载停止前命令的执行时间窗（0-9999秒），默认30秒。
        -   缩容优先级：可根据业务需要选择“优先减少新实例“或“优先减少老实例“。

    -   **迁移策略：**当工作负载实例所在的节点不可用时，系统将实例重新调度到其它可用节点的时间窗。
        -   迁移时间窗 \(s\)：请输入时间，默认为300秒。

    -   **调度策略：**你可以根据需要自由组合静态的全局调度策略或动态的运行时调度策略来实现自己的需求。具体请参见[调度策略概述](调度策略概述.md)。
    -   **Pod高级设置**

        -   Pod标签：内置app标签在工作负载创建时指定，暂不支持修改。您可以单击下方的“添加标签“增加标签。
        -   弹性网卡：Pod中的容器支持绑定弹性网卡。单击选中“绑定弹性网卡“可以绑定已有的网络平面，如果没有可绑定的网络平面，请单击右侧的“添加网络平面“，完成添加后单击刷新按钮。更多网络平面信息请参见[网络平面（NetworkAttachmentDefinition）](网络平面（NetworkAttachmentDefinition）.md)。

            >![](public_sys-resources/icon-note.gif) **说明：**   
            >-   **仅v1.13.7-r0及以上版本且网络模型为VPC网络的混合集群才能绑定弹性网卡，不符合条件的集群将不显示“弹性网卡“选项。**  
            >-   网络平面是CCE新增的一种crd资源，记录了租户ID，子网ID，安全组等的配置项，作为申请弹性网卡的配置信息。  
            >-   创建工作负载时，在[设置工作负载访问方式](#li3580132418215)步骤中如果添加了节点级别的Service，将无法绑定弹性网卡；同理，绑定了弹性网卡的工作负载，将无法添加节点级别的Service。  


        **图 1**  Pod高级设置<a name="fig2225829163110"></a>  
        ![](figures/Pod高级设置.png "Pod高级设置")

    -   **客户端DNS配置**：CCE集群内置DNS插件CoreDNS，为集群内的工作负载提供域名解析服务。详细使用方法请参见[Kubernetes集群内置DNS使用指南](Kubernetes集群内置DNS使用指南.md)。
        -   DNS策略：
            -   追加域名解析配置：选择该配置后，将保留默认配置，以下“IP地址“和“搜索域“配置可能不生效。
            -   替换域名解析配置：选择该配置后，将仅使用以下“IP地址“和“搜索域“配置进行域名解析。
            -   继承Pod所在节点域名解析配置：将继承Pod所在节点的域名解析配置。

        -   IP地址：您可对自定义的域名配置域名服务器，值为一个或一组DNS IP地址，如“1.2.3.4”。
        -   搜索域：定义域名的搜索域列表，当访问的域名不能被DNS解析时，会把该域名与搜索域列表中的域依次进行组合，并重新向DNS发起请求，直到域名被正确解析或者尝试完搜索域列表为止。
        -   超时时间（s）：查询超时时间，请自定义。
        -   ndots：表示域名中必须出现的“.”的个数，如果域名中的“.”的个数不小于ndots，则该域名为一个FQDN，操作系统会直接查询；如果域名中的“.”的个数小于ndots，操作系统会在搜索域中进行查询。

    -   **自定义指标监控：**是指监控系统提供的一种指标收集机制，该机制允许工作负载在部署时自定义需要上报的指标名称以及获取这些指标数据的接入点信息，在应用运行时由监控系统按固定的频率访问接入点进行指标的收集。详细请参见[对接普罗米修斯（自定义监控）](对接普罗米修斯（自定义监控）.md)。
    -   **性能管理配置：**华为云的性能管理服务可协助您快速进行工作负载的问题定位与性能瓶颈分析。详细请参见[性能管理配置（性能瓶颈分析）](性能管理配置（性能瓶颈分析）.md)。

5.  配置完成后，单击“创建”，在创建成功页面单击“返回工作负载列表”，查看工作负载状态。

    在工作负载列表中，当工作负载状态为“运行中”时，表示工作负载创建成功。

    工作负载状态不会实时更新，请单击右上角的![](figures/zh-cn_image_0183674977.png)图标或按F5刷新页面查看。

6.  在“工作负载”页面的工作负载列表中，复制“外部访问地址”，可在浏览器中访问工作负载。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   当工作负载访问方式设为“节点访问（NodePort）“并绑定弹性IP或设为“负载均衡 \( LoadBalancer \)“时，才可以获取外部访问地址，可以访问外网。  
    >-   工作负载列表页在超过500条以上时，将采用Kubernetes的分页机制进行分页。Kubernetes的分页机制：仅支持回到第一页和查看下一页，不支持查看上一页，且在分页显示的情况下，资源总数显示的是批量查询出的数目而不是真实总数。  


## 通过kubectl命令行创建<a name="section155246177178"></a>

本节以nginx工作负载为例，说明kubectl命令创建工作负载的方法。

**前提条件**

请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令，使弹性云服务器连接集群。

**操作步骤**

1.  登录已配置好kubectl命令的弹性云服务器。登录方法请参见[登录Linux弹性云服务器](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0013771089.html)。
2.  创建一个名为nginx-deployment.yaml的描述文件。其中，nginx-deployment.yaml为自定义名称，您可以随意命名。

    **vi nginx-deployment.yaml**

    描述文件内容如下。此处仅为示例，deployment的详细说明请参见[kubernetes官方文档](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)。

    ```
    apiVersion: extensions/v1beta1
    kind: Deployment
    metadata:
      name: nginx
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: nginx
      strategy:
        type: RollingUpdate
      template:
        metadata:
          labels:
            app: nginx
        spec:
          containers:
          - image: nginx 
            imagePullPolicy: Always
            name: nginx
          imagePullSecrets:
          - name: default-secret
    ```

    以上yaml字段解释如[表3](#table132326831016)。

    **表 3**  deployment字段详解

    <a name="table132326831016"></a>
    <table><thead align="left"><tr id="row523318817104"><th class="cellrowborder" valign="top" width="37%" id="mcps1.2.4.1.1"><p id="p162344817100"><a name="p162344817100"></a><a name="p162344817100"></a>字段名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="47%" id="mcps1.2.4.1.2"><p id="p16234138161012"><a name="p16234138161012"></a><a name="p16234138161012"></a>字段说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="16%" id="mcps1.2.4.1.3"><p id="p102881159151016"><a name="p102881159151016"></a><a name="p102881159151016"></a>必选/可选</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row112346841018"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p182345811107"><a name="p182345811107"></a><a name="p182345811107"></a>apiVersion</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p2023458141014"><a name="p2023458141014"></a><a name="p2023458141014"></a>表示API的版本号。</p>
    <div class="note" id="note143305521379"><a name="note143305521379"></a><a name="note143305521379"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p19331452133715"><a name="p19331452133715"></a><a name="p19331452133715"></a>集群版本为1.9之前的无状态应用apiVersion格式为extensions/v1beta1，1.9之后的集群兼容extensions/v1beta1和apps/v1两种格式Version，请根据集群版本输入。</p>
    </div></div>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p6234158101019"><a name="p6234158101019"></a><a name="p6234158101019"></a>必选</p>
    </td>
    </tr>
    <tr id="row202347814100"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p172342815109"><a name="p172342815109"></a><a name="p172342815109"></a>kind</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p142346871019"><a name="p142346871019"></a><a name="p142346871019"></a>创建的对象类别。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p2023416841019"><a name="p2023416841019"></a><a name="p2023416841019"></a>必选</p>
    </td>
    </tr>
    <tr id="row1459172931315"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p1659232941311"><a name="p1659232941311"></a><a name="p1659232941311"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p165932298137"><a name="p165932298137"></a><a name="p165932298137"></a>资源对象的元数据定义。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p16593112941310"><a name="p16593112941310"></a><a name="p16593112941310"></a>必选</p>
    </td>
    </tr>
    <tr id="row33638545115"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p036575412114"><a name="p036575412114"></a><a name="p036575412114"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p1036510541116"><a name="p1036510541116"></a><a name="p1036510541116"></a>deployment的名称。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1936585415110"><a name="p1936585415110"></a><a name="p1936585415110"></a>必选</p>
    </td>
    </tr>
    <tr id="row52341382109"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p2234188171017"><a name="p2234188171017"></a><a name="p2234188171017"></a>Spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p1023414811012"><a name="p1023414811012"></a><a name="p1023414811012"></a>用户对deployment的详细描述的主体部分都在spec中给出。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p92341186101"><a name="p92341186101"></a><a name="p92341186101"></a>必选</p>
    </td>
    </tr>
    <tr id="row490820516139"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p99089513134"><a name="p99089513134"></a><a name="p99089513134"></a>replicas</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p1890815551313"><a name="p1890815551313"></a><a name="p1890815551313"></a>实例数量。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1390895141312"><a name="p1390895141312"></a><a name="p1390895141312"></a>必选</p>
    </td>
    </tr>
    <tr id="row29372135139"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p1493821315132"><a name="p1493821315132"></a><a name="p1493821315132"></a>selector</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p10938171341312"><a name="p10938171341312"></a><a name="p10938171341312"></a>定义Deployment可管理的容器实例。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p5939181320135"><a name="p5939181320135"></a><a name="p5939181320135"></a>必选</p>
    </td>
    </tr>
    <tr id="row393931310133"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p8731714131517"><a name="p8731714131517"></a><a name="p8731714131517"></a>strategy</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p18939313201310"><a name="p18939313201310"></a><a name="p18939313201310"></a>升级类型。当前支持两种升级方式，默认为滚动升级。</p>
    <a name="ul20636151912336"></a><a name="ul20636151912336"></a><ul id="ul20636151912336"><li>RollingUpdate：滚动升级。</li><li>ReplaceUpdate：替换升级。</li></ul>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p169393137138"><a name="p169393137138"></a><a name="p169393137138"></a>可选</p>
    </td>
    </tr>
    <tr id="row793916134135"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p14939131391317"><a name="p14939131391317"></a><a name="p14939131391317"></a>template</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p993921331312"><a name="p993921331312"></a><a name="p993921331312"></a>描述创建的容器实例详细信息。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1193919138132"><a name="p1193919138132"></a><a name="p1193919138132"></a>必选</p>
    </td>
    </tr>
    <tr id="row69398139139"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p132126496218"><a name="p132126496218"></a><a name="p132126496218"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p10939121391317"><a name="p10939121391317"></a><a name="p10939121391317"></a>元数据。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p4939161321314"><a name="p4939161321314"></a><a name="p4939161321314"></a>必选</p>
    </td>
    </tr>
    <tr id="row1479918372441"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p67994378445"><a name="p67994378445"></a><a name="p67994378445"></a>labels</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p1680012377440"><a name="p1680012377440"></a><a name="p1680012377440"></a>metadata.labels定义容器标签。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p180033714449"><a name="p180033714449"></a><a name="p180033714449"></a>可选</p>
    </td>
    </tr>
    <tr id="row6939151316138"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p793911361316"><a name="p793911361316"></a><a name="p793911361316"></a>spec:</p>
    <p id="p17330235102212"><a name="p17330235102212"></a><a name="p17330235102212"></a>containers</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><a name="ul48282256265"></a><a name="ul48282256265"></a><ul id="ul48282256265"><li>image（必选）：容器镜像名称。</li><li>imagePullPolicy（可选）：获取镜像的策略，可选值包括Always（每次都尝试重新下载镜像）、Never（仅使用本地镜像）、IfNotPresent（如果本地有该镜像，则使用本地镜像，本地不存在时下载镜像），默认为Always。</li><li>name（必选）：容器名称。</li></ul>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1193991381318"><a name="p1193991381318"></a><a name="p1193991381318"></a>必选</p>
    </td>
    </tr>
    <tr id="row18939013161315"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p159394135139"><a name="p159394135139"></a><a name="p159394135139"></a>imagePullSecrets</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p49391813131318"><a name="p49391813131318"></a><a name="p49391813131318"></a>Pull镜像时使用的secret名称。若使用私有镜像，该参数为必选。</p>
    <a name="ul125550172614"></a><a name="ul125550172614"></a><ul id="ul125550172614"><li>需要Pull SWR容器镜像仓库的镜像时，参数值固定为default-secret。</li><li>当Pull第三方镜像仓库的镜像时，需设置为创建的secret名称。</li></ul>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1193981391318"><a name="p1193981391318"></a><a name="p1193981391318"></a>可选</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  创建deployment。

    **kubectl create -f nginx-deployment.yaml**

    回显如下表示已开始创建deployment。

    ```
    deployment "nginx" created
    ```

4.  查看deployment状态。

    **kubectl get pods**

    deployment状态显示为Running，表示deployment已创建成功。

    ```
    NAME                     READY     STATUS    RESTARTS   AGE
    icagent-m9dkt            0/0       Running   0          3d
    nginx-1212400781-qv313   1/1       Running   0          3d
    ```

    **参数解析：**

    -   NAME：pod名
    -   READY：准备好的副本数
    -   STATUS：状态
    -   RESTARTS：重启
    -   AGE：已经运行的时间

5.  若工作负载（即deployment）需要被访问（集群内访问或节点访问），您需要设置访问方式，具体请参见[网络管理](网络管理.md)创建对应服务。

