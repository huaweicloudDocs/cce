# 创建普通任务\(Job\)<a name="cce_01_0150"></a>

## 操作场景<a name="section142417128434"></a>

普通任务是一次性运行的短任务，部署完成后即可执行。正常退出（exit 0）后，任务即执行完成。

普通任务是用来控制批处理型任务的资源对象。批处理业务与长期伺服业务（Deployment、Statefulset）的主要区别是：

批处理业务的运行有头有尾，而长期伺服业务在用户不停止的情况下永远运行。Job管理的Pod根据用户的设置把任务成功完成就自动退出了。成功完成的标志根据不同的spec.completions策略而不同，即：

-   单Pod型任务有一个Pod成功就标志完成。
-   定数成功型任务保证有N个任务全部成功。
-   工作队列型任务根据应用确认的全局成功而标志成功。

## 前提条件<a name="s50bf087555b1437aa249c1259138706c"></a>

已创建资源，具体操作请参见[购买节点（按需计费）](购买节点.md)。若已有集群和节点资源，无需重复操作。

## 操作步骤<a name="sb8a02965b2624dbbabab320046ca4973"></a>

1.  （可选）普通任务需要基于镜像创建，若选择私有镜像，用户首先需要将镜像上传至镜像仓库。

    镜像仓库的使用步骤请参考[上传镜像至容器镜像服务](https://support.huaweicloud.com/usermanual-swr/swr_01_0009.html)。

2.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“工作负载 \> 普通任务 Job“，单击“创建普通任务”_。_
3.  参照[表1](#t70ce3a99637a44ce8f7274857fb245b1)配置任务基本信息，其中带“\*”标志的参数为必填参数。

    **表 1**  任务基本信息

    <a name="t70ce3a99637a44ce8f7274857fb245b1"></a>
    <table><thead align="left"><tr id="r1a0b6bbef01240158b8e679b6165cf76"><th class="cellrowborder" valign="top" width="19.77%" id="mcps1.2.3.1.1"><p id="a51b64f77c7d04e0f9025ed260d38faa3"><a name="a51b64f77c7d04e0f9025ed260d38faa3"></a><a name="a51b64f77c7d04e0f9025ed260d38faa3"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80.23%" id="mcps1.2.3.1.2"><p id="a639151b15ff74221a51e0b671a591976"><a name="a639151b15ff74221a51e0b671a591976"></a><a name="a639151b15ff74221a51e0b671a591976"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r92a0394079de48da83876059957c2b78"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="a989ec542e71a4040a82cbf2931695364"><a name="a989ec542e71a4040a82cbf2931695364"></a><a name="a989ec542e71a4040a82cbf2931695364"></a>* 任务名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="a55e0ddd0f9c24b239315111b39913395"><a name="a55e0ddd0f9c24b239315111b39913395"></a><a name="a55e0ddd0f9c24b239315111b39913395"></a>新建任务的名称，命名必须唯一。</p>
    <p id="p142031631123"><a name="p142031631123"></a><a name="p142031631123"></a>请输入4到63个字符的字符串，可以包含小写英文字母、数字和中划线（-），并以小写英文字母开头，小写英文字母或数字结尾。</p>
    </td>
    </tr>
    <tr id="r80610bcddd944c02a6e928130b1bc574"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="a75643f9a614b4180b6b9404f503c5dfd"><a name="a75643f9a614b4180b6b9404f503c5dfd"></a><a name="a75643f9a614b4180b6b9404f503c5dfd"></a>* 容器集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="a760cf36b9e3b4d168c5ea807b62896d2"><a name="a760cf36b9e3b4d168c5ea807b62896d2"></a><a name="a760cf36b9e3b4d168c5ea807b62896d2"></a>新建任务所在的集群。</p>
    </td>
    </tr>
    <tr id="row43713551547"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="p1381455125415"><a name="p1381455125415"></a><a name="p1381455125415"></a>* 命名空间</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="p18383552541"><a name="p18383552541"></a><a name="p18383552541"></a>新建任务所属的命名空间，默认为default。</p>
    </td>
    </tr>
    <tr id="row0507119121413"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="p19507591149"><a name="p19507591149"></a><a name="p19507591149"></a>* 实例数量</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="p1042648123717"><a name="p1042648123717"></a><a name="p1042648123717"></a>任务的实例数量。任务可以有一个或多个实例，用户可以设置具体实例个数，默认为1。</p>
    <p id="p17713926910"><a name="p17713926910"></a><a name="p17713926910"></a>每个任务实例都由相同的容器部署而成。设置多个实例主要用于实现高可靠性，当某个实例故障时，任务还能正常运行。</p>
    </td>
    </tr>
    <tr id="row33213981613"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="p1522718171417"><a name="p1522718171417"></a><a name="p1522718171417"></a>* 容器运行时</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><div class="p" id="p1192543112451"><a name="p1192543112451"></a><a name="p1192543112451"></a>请选择容器的运行时（Runtime），创建后不可修改。<strong id="b1631410435919"><a name="b1631410435919"></a><a name="b1631410435919"></a>该参数仅支持CCE Turbo集群。</strong><a name="ul149613219450"></a><a name="ul149613219450"></a><ul id="ul149613219450"><li>docker运行时：普通容器</li><li>安全运行时：选择该运行时后将升级为安全容器，该任务只能运行在使用安全运行时的节点上。</li></ul>
    </div>
    <p id="p10118529112613"><a name="p10118529112613"></a><a name="p10118529112613"></a>两种容器运行时的对比请参见<a href="节点概述.md#section7201124294111">普通容器与安全容器的区别</a>。</p>
    </td>
    </tr>
    <tr id="row65301051950"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="p4877104910012"><a name="p4877104910012"></a><a name="p4877104910012"></a>CCI弹性承载</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="p11595204219"><a name="p11595204219"></a><a name="p11595204219"></a>该参数仅在安装virtual kubelet插件后才显示，具体请参见<a href="virtual-kubelet.md">virtual-kubelet</a>。</p>
    <p id="p118778495016"><a name="p118778495016"></a><a name="p118778495016"></a>勾选此选项后，当集群资源不足时，支持将Pod部署到云容器实例CCI。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0093532761_row2314820103"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="ab9807e25b58e4d3e88a5fe580e46e093"><a name="ab9807e25b58e4d3e88a5fe580e46e093"></a><a name="ab9807e25b58e4d3e88a5fe580e46e093"></a>任务描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="a8f8f3f458f7c416eb54e58701713294d"><a name="a8f8f3f458f7c416eb54e58701713294d"></a><a name="a8f8f3f458f7c416eb54e58701713294d"></a>任务描述信息。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“下一步：添加容器“，添加容器和镜像。
    1.  单击“选择镜像”，选择需要部署的镜像。
        -   我的镜像：展示了您创建的所有镜像仓库。
        -   开源镜像中心：展示了开源镜像中心仓库中的官方镜像。
        -   第三方镜像：CCE支持拉取第三方镜像仓库（即镜像仓库与开源镜像中心之外的镜像仓库）的镜像创建任务。使用第三方镜像时，请确保任务运行的节点可访问公网。第三方镜像的具体使用方法请参见[如何使用第三方镜像](如何使用第三方镜像.md)。
            -   若您的镜像仓库不需要认证，密钥认证请选择“否“，并输入“镜像地址“，单击“确定“。
            -   若您的镜像仓库都必须经过认证（帐号密码）才能访问，您需要先创建密钥再使用第三方镜像，具体操作请参见[如何使用第三方镜像](如何使用第三方镜像.md)。

        -   共享镜像：其它租户通过“容器镜像服务“共享给您的镜像将在此处展示，您可以基于共享镜像创建工作负载。

    2.  配置镜像参数。

        **表 2**  添加容器参数说明

        <a name="t2fdf8c3943d948f6873da4b75b46d3f5"></a>
        <table><thead align="left"><tr id="cce_01_0047_row0282348486"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.3.1.1"><p id="cce_01_0047_p3282147483"><a name="cce_01_0047_p3282147483"></a><a name="cce_01_0047_p3282147483"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="77%" id="mcps1.2.3.1.2"><p id="cce_01_0047_p1828244144819"><a name="cce_01_0047_p1828244144819"></a><a name="cce_01_0047_p1828244144819"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="cce_01_0047_row1844916557597"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p182837474815"><a name="cce_01_0047_p182837474815"></a><a name="cce_01_0047_p182837474815"></a>镜像</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p3283134134820"><a name="cce_01_0047_p3283134134820"></a><a name="cce_01_0047_p3283134134820"></a>导入的镜像，您可单击<span class="uicontrol" id="cce_01_0047_uicontrol1217815019463"><a name="cce_01_0047_uicontrol1217815019463"></a><a name="cce_01_0047_uicontrol1217815019463"></a>“更换镜像”</span>进行更换。</p>
        </td>
        </tr>
        <tr id="cce_01_0047_row338117362515"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p1038143616517"><a name="cce_01_0047_p1038143616517"></a><a name="cce_01_0047_p1038143616517"></a>* 镜像版本</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p1338110368519"><a name="cce_01_0047_p1338110368519"></a><a name="cce_01_0047_p1338110368519"></a>选择需要部署的镜像版本。</p>
        </td>
        </tr>
        <tr id="cce_01_0047_row32839494813"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p122831140486"><a name="cce_01_0047_p122831140486"></a><a name="cce_01_0047_p122831140486"></a>* 容器名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0047_p528314415486"><a name="cce_01_0047_p528314415486"></a><a name="cce_01_0047_p528314415486"></a>容器的名称，可修改。</p>
        </td>
        </tr>
        <tr id="cce_01_0047_row152831345485"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0047_p875325925918"><a name="cce_01_0047_p875325925918"></a><a name="cce_01_0047_p875325925918"></a>容器规格</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="p5379182494610"><a name="p5379182494610"></a><a name="p5379182494610"></a><strong id="b2155195713314"><a name="b2155195713314"></a><a name="b2155195713314"></a>CPU配额：</strong></p>
        <a name="ul67283495467"></a><a name="ul67283495467"></a><ul id="ul67283495467"><li>申请：容器需要使用的最小CPU值，默认0.25Core。</li><li>限制：允许容器使用的CPU最大值。建议设容器配额的最高限额，避免容器资源超额导致系统故障。</li></ul>
        <p id="p633394210502"><a name="p633394210502"></a><a name="p633394210502"></a><strong id="b5114173113411"><a name="b5114173113411"></a><a name="b5114173113411"></a>内存配额：</strong></p>
        <a name="ul14326165915010"></a><a name="ul14326165915010"></a><ul id="ul14326165915010"><li>申请：容器需要使用的内存最小值，默认0.5GiB。</li><li>限制：允许容器使用的内存最大值。如果超过，容器会被终止。</li></ul>
        <p id="p1825119142351"><a name="p1825119142351"></a><a name="p1825119142351"></a>申请和限制的具体请参见<a href="设置容器规格.md">设置容器规格</a>。</p>
        <p id="p38521896343"><a name="p38521896343"></a><a name="p38521896343"></a><strong id="b11557151512341"><a name="b11557151512341"></a><a name="b11557151512341"></a>GPU配额：</strong>当集群中包含GPU节点时，才能设置GPU，无GPU节点不显示此选项。</p>
        <p id="p15403132914341"><a name="p15403132914341"></a><a name="p15403132914341"></a>容器需要使用的GPU百分比。勾选<span class="uicontrol" id="uicontrol952171455614"><a name="uicontrol952171455614"></a><a name="uicontrol952171455614"></a>“使用”</span>并设置百分比，例如设置为10%，表示该容器需使用GPU资源的10%。若不勾选<span class="uicontrol" id="uicontrol12950184715612"><a name="uicontrol12950184715612"></a><a name="uicontrol12950184715612"></a>“使用”</span>，或设置为0，则无法使用GPU资源。</p>
        <p id="p9626154413340"><a name="p9626154413340"></a><a name="p9626154413340"></a><strong id="b423894943411"><a name="b423894943411"></a><a name="b423894943411"></a>GPU显卡：</strong>工作负载实例将被调度到GPU显卡类型为指定显卡的节点上。</p>
        <p id="p15765438173416"><a name="p15765438173416"></a><a name="p15765438173416"></a>若勾选“不限制”，容器将会随机使用节点中的任一显卡。您也可以勾选某个显卡，容器将使用特定显卡。</p>
        <p id="p58663964520"><a name="p58663964520"></a><a name="p58663964520"></a><strong id="b188666944516"><a name="b188666944516"></a><a name="b188666944516"></a>昇腾&nbsp;310配额：</strong>容器需要使用的昇腾 310芯片个数，此处须为整数。</p>
        <p id="p2097772173513"><a name="p2097772173513"></a><a name="p2097772173513"></a>选用AI加速型节点并安装<strong id="b99085210250"><a name="b99085210250"></a><a name="b99085210250"></a>huawei-npu</strong>插件后该参数设置将生效。AI加速型节点目前已开放公测，该节点搭载高性能、低功耗的海思Ascend 310 AI处理器，适用于图像识别、视频处理、推理计算以及机器学习等场景，点此可<a href="https://account.huaweicloud.com/usercenter/#/userindex/betaManagement?serviceCode=ecs_ascend_ai1" target="_blank" rel="noopener noreferrer">立即申请</a>。</p>
        </td>
        </tr>
        </tbody>
        </table>

    3.  （可选）高级设置。

        **表 3**  高级设置

        <a name="tf56c7b65fd00476dbf686d494609ec01"></a>
        <table><thead align="left"><tr id="rd70607f9bfa74a83a6e424e8abda265c"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.3.1.1"><p id="a85705044d3104d34957e244b20e98de2"><a name="a85705044d3104d34957e244b20e98de2"></a><a name="a85705044d3104d34957e244b20e98de2"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="77%" id="mcps1.2.3.1.2"><p id="ab80a0aae28b54ab1afe9009e2466b2e6"><a name="ab80a0aae28b54ab1afe9009e2466b2e6"></a><a name="ab80a0aae28b54ab1afe9009e2466b2e6"></a>参数说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="r616e69d5a2004b079888d8a4a2a83762"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="ae1906e2a0f4e48c8a290d2ffdc9e83bf"><a name="ae1906e2a0f4e48c8a290d2ffdc9e83bf"></a><a name="ae1906e2a0f4e48c8a290d2ffdc9e83bf"></a>生命周<span>期</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><div class="p" id="a72815832aa2c4ad6953cec368b824346"><a name="a72815832aa2c4ad6953cec368b824346"></a><a name="a72815832aa2c4ad6953cec368b824346"></a>生命周期脚本定义，主要针对容器类任务的生命周期事件采取的动作。<a name="u86a34d59537a4e5ebbcd8d62f0fb6fc7"></a><a name="u86a34d59537a4e5ebbcd8d62f0fb6fc7"></a><ul id="u86a34d59537a4e5ebbcd8d62f0fb6fc7"><li>启动命令：输入容器启动命令，容器启动后会立即执行。详细步骤请参见<a href="容器设置.md">容器设置</a>。</li><li>启动后处<span>理：</span>任务启动后<span>触发。</span>详细步骤请参见<a href="设置容器生命周期.md">设置容器生命周期</a>。</li><li>停止前处理：任务停止前触发。详细步骤请参见<a href="设置容器生命周期.md">设置容器生命周期</a>。</li></ul>
        </div>
        </td>
        </tr>
        <tr id="r159688429d2c4ad5b55d2b63b5bc6a46"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="acab0841bbf1548e08722d5ec9fb378e9"><a name="acab0841bbf1548e08722d5ec9fb378e9"></a><a name="acab0841bbf1548e08722d5ec9fb378e9"></a>环境变<span>量</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><div class="p" id="p1033073311186"><a name="p1033073311186"></a><a name="p1033073311186"></a>在容器中添加环境变量，一般用于通过环境变量设置参数。在环境变量页签，单击<span class="uicontrol" id="uicontrol9842146626"><a name="uicontrol9842146626"></a><a name="uicontrol9842146626"></a>“添加环境变量”</span>。当前支持三种类型。<a name="ul145379401817"></a><a name="ul145379401817"></a><ul id="ul145379401817"><li>手动添加：输入变量名称、变量/变量引用。</li><li>密钥导入：输入变量名称，选择导入的密钥名称和数据。您需要提前创建密钥，具体请参见<a href="创建密钥.md">创建密钥</a>。</li><li>配置项导入：输入变量名称，选择导入的配置项名称和数据。您需要提前创建配置项，具体请参见<a href="创建配置项.md">创建配置项</a>。</li></ul>
        </div>
        </td>
        </tr>
        <tr id="r23157569d21e4f1eaca7fddbb384abd8"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="a8540d286ec904152a0ae2a7706f81b13"><a name="a8540d286ec904152a0ae2a7706f81b13"></a><a name="a8540d286ec904152a0ae2a7706f81b13"></a>数据存储</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="a8b0122d13c334988999081ca36bcd194"><a name="a8b0122d13c334988999081ca36bcd194"></a><a name="a8b0122d13c334988999081ca36bcd194"></a>支持挂载本地磁盘或者云存储到容器中，以实现数据文件的持久化存储<span>。</span></p>
        <p id="a15513eb91b5c4c3daf720ca0b6365c60"><a name="a15513eb91b5c4c3daf720ca0b6365c60"></a><a name="a15513eb91b5c4c3daf720ca0b6365c60"></a>详细步骤请参见<a href="存储管理.md">存储管理</a>。</p>
        </td>
        </tr>
        <tr id="r547f9887aa95447fae37c69bf28e8d09"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="a4a93ff2a806b494c8d80b89595802cbe"><a name="a4a93ff2a806b494c8d80b89595802cbe"></a><a name="a4a93ff2a806b494c8d80b89595802cbe"></a>容器日志</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="ac6fc6fa08da64fdc9d6366f5f9834e11"><a name="ac6fc6fa08da64fdc9d6366f5f9834e11"></a><a name="ac6fc6fa08da64fdc9d6366f5f9834e11"></a>CCE支持配置工作负载日志策略，便于日志收集分析，以及按周期防爆处理。详细步骤请参见<a href="采集容器标准输出日志.md">采集容器标准输出日志</a>。</p>
        </td>
        </tr>
        </tbody>
        </table>

    4.  （可选）一个任务实例包含1个或多个相关容器。若您的任务包含多个容器，请单击“添加容器”，再执行添加容器的操作。

5.  配置完成后，单击“创建“。

    待状态为“执行中“，普通任务创建成功。


## 使用kubectl创建Job<a name="section450152719412"></a>

Job的配置参数如下所示。

-   spec.template格式与Pod相同。
-   RestartPolicy仅支持Never或OnFailure。
-   单个Pod时，默认Pod成功运行后Job即结束。
-   .spec.completions表示Job结束需要成功运行的Pod个数，默认为1。
-   .spec.parallelism表示并行运行的Pod的个数，默认为1。
-   spec.backoffLimit表示失败Pod的重试最大次数，超过这个次数不会继续重试。
-   .spec.activeDeadlineSeconds表示Pod运行时间，一旦达到这个时间，Job即其所有的Pod都会停止。且activeDeadlineSeconds优先级高于backoffLimit，即到达activeDeadlineSeconds的Job会忽略backoffLimit的设置。

根据.spec.completions和.spec.Parallelism的设置，可以将Job划分为以下几种类型。

**表 4**  任务类型

<a name="table19214202022111"></a>
<table><thead align="left"><tr id="row221419208210"><th class="cellrowborder" valign="top" width="21%" id="mcps1.2.4.1.1"><p id="p192146200219"><a name="p192146200219"></a><a name="p192146200219"></a>Job类型</p>
</th>
<th class="cellrowborder" valign="top" width="39%" id="mcps1.2.4.1.2"><p id="p0214720122118"><a name="p0214720122118"></a><a name="p0214720122118"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.4.1.3"><p id="p62149208219"><a name="p62149208219"></a><a name="p62149208219"></a>使用示例</p>
</th>
</tr>
</thead>
<tbody><tr id="row82141620152119"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p2050935122113"><a name="p2050935122113"></a><a name="p2050935122113"></a>一次性Job</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.4.1.2 "><p id="p124101856162110"><a name="p124101856162110"></a><a name="p124101856162110"></a>创建一个Pod直至其成功结束</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p58403110224"><a name="p58403110224"></a><a name="p58403110224"></a>数据库迁移</p>
</td>
</tr>
<tr id="row1221432052118"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p14512351132120"><a name="p14512351132120"></a><a name="p14512351132120"></a>固定结束次数的Job</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.4.1.2 "><p id="p741405662112"><a name="p741405662112"></a><a name="p741405662112"></a>依次创建一个Pod运行直至completions个成功结束</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p1284481192220"><a name="p1284481192220"></a><a name="p1284481192220"></a>处理工作队列的Pod</p>
</td>
</tr>
<tr id="row1321432013217"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p195159512216"><a name="p195159512216"></a><a name="p195159512216"></a>固定结束次数的并行Job</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.4.1.2 "><p id="p134205562218"><a name="p134205562218"></a><a name="p134205562218"></a>依次创建多个Pod运行直至completions个成功结束</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p3847512224"><a name="p3847512224"></a><a name="p3847512224"></a>多个Pod同时处理工作队列</p>
</td>
</tr>
<tr id="row8214192020217"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p115209514218"><a name="p115209514218"></a><a name="p115209514218"></a>并行Job</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.4.1.2 "><p id="p12424856142114"><a name="p12424856142114"></a><a name="p12424856142114"></a>创建一个或多个Pod直至有一个成功结束</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p285251142217"><a name="p285251142217"></a><a name="p285251142217"></a>多个Pod同时处理工作队列</p>
</td>
</tr>
</tbody>
</table>

以下是一个Job配置示例，保存在myjob.yaml中，其计算π到2000位并打印输出。

```
apiVersion: batch/v1
kind: Job
metadata:
  name: pi-with-timeout
spec:
  completions: 50        # Job结束需要运行50个Pod，这个示例中就是打印π 50次
  parallelism: 5        # 并行5个Pod
  backoffLimit: 5        # 最多重试5次
  template:
    spec:
      containers:
      - name: pi
        image: perl
        command: ["perl",  "-Mbignum=bpi", "-wle", "print bpi(2000)"]
      restartPolicy: Never
```

**说明：**

-   apiVersion: batch/v1 是当前job的Version
-   kind: Job：指定当前资源的类型时Job
-   restartPolicy: Never：是指当前的重启策略。对于Job，只能设置为Never或者OnFailure。对于其他controller（比如Deployment）可以设置为Always。

**运行该任务，如下：**

1.  启动这个job。

    ```
    [root@k8s-master k8s]# kubectl apply -f myjob.yaml
    job.batch/myjob created
    ```

2.  查看这个job。

    **kubectl get job**

    ```
    [root@k8s-master k8s]# kubectl get job
    NAME    COMPLETIONS   DURATION   AGE
    myjob   1/1           23s        3m45s
    ```

    completions为 1/1 表示成功运行了这个job。

3.  查看pod的状态。

    **kubectl get pod**

    ```
    [root@k8s-master k8s]# kubectl get pod
    NAME          READY   STATUS      RESTARTS   AGE
    myjob-29qlw   0/1     Completed   0          4m5s
    ```

    状态为Completed表示这个job已经运行完成。

4.  查看这个pod的日志。

    **kubectl  logs**

    ```
    [root@k8s-master k8s]# kubectl logs myjob-29qlw 
    hello k8s job!
    ```


## 相关操作<a name="s9bef0428158a4935b466ea150ccae961"></a>

普通任务创建完成后，您还可执行[表5](#t84075653e7544394939d13740fad0c20)中操作。

**表 5**  其他操作

<a name="t84075653e7544394939d13740fad0c20"></a>
<table><thead align="left"><tr id="r83819c2bd882441798d949cbee32fa6a"><th class="cellrowborder" valign="top" width="28.999999999999996%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0093532761_p92150167611"><a name="zh-cn_topic_0093532761_p92150167611"></a><a name="zh-cn_topic_0093532761_p92150167611"></a>操作</p>
</th>
<th class="cellrowborder" valign="top" width="71%" id="mcps1.2.3.1.2"><p id="a6b27fdd2dcc340f3baa6024edb5b3ae9"><a name="a6b27fdd2dcc340f3baa6024edb5b3ae9"></a><a name="a6b27fdd2dcc340f3baa6024edb5b3ae9"></a>操作说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row17717577287"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="p147711757162810"><a name="p147711757162810"></a><a name="p147711757162810"></a>查看YAML</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><p id="p15771257142816"><a name="p15771257142816"></a><a name="p15771257142816"></a>单击任务名称后的<span class="uicontrol" id="uicontrol33801326152917"><a name="uicontrol33801326152917"></a><a name="uicontrol33801326152917"></a>“查看YAML”</span>，可查看到当前任务对应的YAML文件。</p>
</td>
</tr>
<tr id="r27a8f438ed1d4cbba2ad07f7a08acb06"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="a1f9f2bb06252439c82b01c1d4bbb9ab0"><a name="a1f9f2bb06252439c82b01c1d4bbb9ab0"></a><a name="a1f9f2bb06252439c82b01c1d4bbb9ab0"></a>删除普通任务</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><a name="od5720c015360452491819af825ce5845"></a><a name="od5720c015360452491819af825ce5845"></a><ol id="od5720c015360452491819af825ce5845"><li>选择待删除的任务，单击操作列的<span class="uicontrol" id="u6db22cf752d54806adb4997e43ca3376"><a name="u6db22cf752d54806adb4997e43ca3376"></a><a name="u6db22cf752d54806adb4997e43ca3376"></a>“删除”</span>。</li><li>单击“确定”。<p id="aad27c67674e84e898611af0725bfe1cf"><a name="aad27c67674e84e898611af0725bfe1cf"></a><a name="aad27c67674e84e898611af0725bfe1cf"></a>任务删除后将无法恢复，请谨慎操作。</p>
</li></ol>
</td>
</tr>
</tbody>
</table>

