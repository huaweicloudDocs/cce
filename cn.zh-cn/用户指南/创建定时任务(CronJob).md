# 创建定时任务\(CronJob\)<a name="cce_01_0151"></a>

定时任务是按照指定时间周期运行的短任务。使用场景为在某个固定时间点，为所有运行中的节点做时间同步。

定时任务是基于时间的Job，就类似于Linux系统的crontab，在指定的时间周期运行指定的Job，即：

-   在给定时间点只运行一次。
-   在给定时间点周期性地运行。

CronJob的典型用法如下所示：

-   在给定的时间点调度 Job 运行。
-   创建周期性运行的 Job，例如数据库备份、发送邮件。

## 准备工作<a name="s50bf087555b1437aa249c1259138706c"></a>

已创建资源，具体操作请参见[购买节点（按需计费）](购买节点.md)。若已有集群和节点资源，无需重复操作。

## 操作步骤<a name="s631f9f0386834b23ae6d1e4d19d53382"></a>

1.  （可选）定时任务需要基于镜像创建，若选择私有镜像，用户首先需要将镜像上传至镜像仓库。

    镜像仓库的使用步骤请参考[上传镜像至容器镜像服务](https://support.huaweicloud.com/usermanual-swr/swr_01_0009.html)。

2.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“工作负载 \> 定时任务 CronJob“，单击“创建定时任务”_。_
3.  参照[表1](#tfadd3a11520b424d9063fe347c9c8c46)配置定时任务基本信息，其中带“\*”标志的参数为必填参数。

    **表 1**  任务基本信息

    <a name="tfadd3a11520b424d9063fe347c9c8c46"></a>
    <table><thead align="left"><tr id="r18c18c1a53de41548275e3d1a693371d"><th class="cellrowborder" valign="top" width="19.77%" id="mcps1.2.3.1.1"><p id="a88b4790b6aa74bfc9eb95386662ddebd"><a name="a88b4790b6aa74bfc9eb95386662ddebd"></a><a name="a88b4790b6aa74bfc9eb95386662ddebd"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80.23%" id="mcps1.2.3.1.2"><p id="a958597fbe1df427a8adb7f8cd27f7ae3"><a name="a958597fbe1df427a8adb7f8cd27f7ae3"></a><a name="a958597fbe1df427a8adb7f8cd27f7ae3"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r56788b8cc82f49d290f64df3cc1dc0f3"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="a7ce6034eee6a45c4a2025b16a465af01"><a name="a7ce6034eee6a45c4a2025b16a465af01"></a><a name="a7ce6034eee6a45c4a2025b16a465af01"></a>* 任务名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="a0c8ce3cf0d1348f9a9671b5175534afd"><a name="a0c8ce3cf0d1348f9a9671b5175534afd"></a><a name="a0c8ce3cf0d1348f9a9671b5175534afd"></a>新建任务的名称，命名必须唯一。</p>
    <p id="p14468184014213"><a name="p14468184014213"></a><a name="p14468184014213"></a>请输入4到52个字符的字符串，可以包含小写英文字母、数字和中划线（-），并以小写英文字母开头，小写英文字母或数字结尾。</p>
    </td>
    </tr>
    <tr id="row15341125115344"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="a75643f9a614b4180b6b9404f503c5dfd"><a name="a75643f9a614b4180b6b9404f503c5dfd"></a><a name="a75643f9a614b4180b6b9404f503c5dfd"></a>* 容器集群</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="a760cf36b9e3b4d168c5ea807b62896d2"><a name="a760cf36b9e3b4d168c5ea807b62896d2"></a><a name="a760cf36b9e3b4d168c5ea807b62896d2"></a>新建任务所在的集群。</p>
    </td>
    </tr>
    <tr id="row1259861015571"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="p125066193578"><a name="p125066193578"></a><a name="p125066193578"></a>* 命名空间</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="p2050991925711"><a name="p2050991925711"></a><a name="p2050991925711"></a>新建任务所在的命名空间。若不选择，默认配置为default。</p>
    </td>
    </tr>
    <tr id="rdc1b35b8ff3c4072a49b1da4db8f71e5"><td class="cellrowborder" valign="top" width="19.77%" headers="mcps1.2.3.1.1 "><p id="a26499db509ff4ab7a1ac006ca3a8746d"><a name="a26499db509ff4ab7a1ac006ca3a8746d"></a><a name="a26499db509ff4ab7a1ac006ca3a8746d"></a>任务描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.23%" headers="mcps1.2.3.1.2 "><p id="a49218e0435a24eb7bdfce65248bef274"><a name="a49218e0435a24eb7bdfce65248bef274"></a><a name="a49218e0435a24eb7bdfce65248bef274"></a>任务描述信息。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  配置完成后，单击“下一步：定时规则“。
5.  设置定时规则。

    **表 2**  定时规则参数

    <a name="t3c443d636816401eb8c228607c440faf"></a>
    <table><thead align="left"><tr id="rb7c79e2ffbb74c248bcef71ba9477eca"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0093532762_p72699752917"><a name="zh-cn_topic_0093532762_p72699752917"></a><a name="zh-cn_topic_0093532762_p72699752917"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0093532762_p9269379294"><a name="zh-cn_topic_0093532762_p9269379294"></a><a name="zh-cn_topic_0093532762_p9269379294"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r6305be1a630244bf81ac437522f31cf0"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0093532762_p162871332056"><a name="zh-cn_topic_0093532762_p162871332056"></a><a name="zh-cn_topic_0093532762_p162871332056"></a>* <span class="keyword" id="keyword536182114411"><a name="keyword536182114411"></a><a name="keyword536182114411"></a>并发策略</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="a1238035c6c934a228d56a1884594bf19"><a name="a1238035c6c934a228d56a1884594bf19"></a><a name="a1238035c6c934a228d56a1884594bf19"></a>支持如下三种模式：</p>
    <a name="u8a387ed341d640999663e82cfc513fb5"></a><a name="u8a387ed341d640999663e82cfc513fb5"></a><ul id="u8a387ed341d640999663e82cfc513fb5"><li><span class="keyword" id="keyword175416136441"><a name="keyword175416136441"></a><a name="keyword175416136441"></a>Forbid</span>：在前一个任务未完成时，不创建新任务。</li><li><span class="keyword" id="keyword11529101520448"><a name="keyword11529101520448"></a><a name="keyword11529101520448"></a>Allow</span>：定时任务不断新建Job。</li><li><span class="keyword" id="keyword457320174442"><a name="keyword457320174442"></a><a name="keyword457320174442"></a>Replace</span>：已到新任务创建时间点，但前一个任务还未完成，新的任务会取代前一个任务。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0093532762_row8270974297"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="a86a31e64aad144e19e5df3d4e25158b9"><a name="a86a31e64aad144e19e5df3d4e25158b9"></a><a name="a86a31e64aad144e19e5df3d4e25158b9"></a>* <span class="keyword" id="keyword68782234441"><a name="keyword68782234441"></a><a name="keyword68782234441"></a>定时规则</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="aca0cc43e08524e1d86ab0896157991c5"><a name="aca0cc43e08524e1d86ab0896157991c5"></a><a name="aca0cc43e08524e1d86ab0896157991c5"></a>指定新建定时任务在何时执行。</p>
    </td>
    </tr>
    <tr id="row57993169"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p5369911316108"><a name="p5369911316108"></a><a name="p5369911316108"></a>任务记录</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p5466090716108"><a name="p5466090716108"></a><a name="p5466090716108"></a>可以设置保留执行成功或执行失败的任务个数，设置为 0 表示不保留。</p>
    </td>
    </tr>
    </tbody>
    </table>

6.  单击“下一步：添加容器“，添加容器。
    1.  单击“选择镜像”，选择需要部署的镜像。
        -   我的镜像：展示了您创建的所有镜像仓库。
        -   开源镜像中心：展示了开源镜像中心仓库中的官方镜像。
        -   第三方镜像：CCE支持拉取第三方镜像仓库（即镜像仓库与开源镜像中心之外的镜像仓库）的镜像创建任务。使用第三方镜像时，请确保任务运行的节点可访问公网。第三方镜像的具体使用方法请参见[如何使用第三方镜像](如何使用第三方镜像.md)。
            -   若您的镜像仓库不需要认证，密钥认证请选择“否“，并输入“镜像地址“，单击“确定“。
            -   若您的镜像仓库都必须经过认证（帐号密码）才能访问，您需要先创建密钥再使用第三方镜像，具体操作请参见[如何使用第三方镜像](如何使用第三方镜像.md)。

        -   共享镜像：其它租户通过“容器镜像服务“共享给您的镜像将在此处展示，您可以基于共享镜像创建工作负载。

    2.  配置镜像参数。

        **表 3**  添加容器参数说明

        <a name="t7eeb89498d8449aaaf341f1d6441a1e6"></a>
        <table><thead align="left"><tr id="cce_01_0150_zh-cn_topic_0107283470_row0282348486"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.3.1.1"><p id="cce_01_0150_zh-cn_topic_0107283470_p3282147483"><a name="cce_01_0150_zh-cn_topic_0107283470_p3282147483"></a><a name="cce_01_0150_zh-cn_topic_0107283470_p3282147483"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="77%" id="mcps1.2.3.1.2"><p id="cce_01_0150_zh-cn_topic_0107283470_p1828244144819"><a name="cce_01_0150_zh-cn_topic_0107283470_p1828244144819"></a><a name="cce_01_0150_zh-cn_topic_0107283470_p1828244144819"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="cce_01_0150_zh-cn_topic_0107283470_row1844916557597"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0150_zh-cn_topic_0107283470_p182837474815"><a name="cce_01_0150_zh-cn_topic_0107283470_p182837474815"></a><a name="cce_01_0150_zh-cn_topic_0107283470_p182837474815"></a>镜像</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0150_zh-cn_topic_0107283470_p3283134134820"><a name="cce_01_0150_zh-cn_topic_0107283470_p3283134134820"></a><a name="cce_01_0150_zh-cn_topic_0107283470_p3283134134820"></a>导入的镜像，您可单击<span class="uicontrol" id="cce_01_0150_zh-cn_topic_0107283470_uicontrol1217815019463"><a name="cce_01_0150_zh-cn_topic_0107283470_uicontrol1217815019463"></a><a name="cce_01_0150_zh-cn_topic_0107283470_uicontrol1217815019463"></a>“更换镜像”</span>进行更换。</p>
        </td>
        </tr>
        <tr id="cce_01_0150_zh-cn_topic_0107283470_row338117362515"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0150_zh-cn_topic_0107283470_p1038143616517"><a name="cce_01_0150_zh-cn_topic_0107283470_p1038143616517"></a><a name="cce_01_0150_zh-cn_topic_0107283470_p1038143616517"></a>* 镜像版本</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0150_zh-cn_topic_0107283470_p1338110368519"><a name="cce_01_0150_zh-cn_topic_0107283470_p1338110368519"></a><a name="cce_01_0150_zh-cn_topic_0107283470_p1338110368519"></a>若选择<span id="cce_01_0150_ph15324124018410"><a name="cce_01_0150_ph15324124018410"></a><a name="cce_01_0150_ph15324124018410"></a><span class="uicontrol" id="cce_01_0150_uicontrol18207174312413"><a name="cce_01_0150_uicontrol18207174312413"></a><a name="cce_01_0150_uicontrol18207174312413"></a>“开源镜像中心”</span></span>，请选择需要部署的镜像版本。</p>
        </td>
        </tr>
        <tr id="cce_01_0150_zh-cn_topic_0107283470_row32839494813"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0150_zh-cn_topic_0107283470_p122831140486"><a name="cce_01_0150_zh-cn_topic_0107283470_p122831140486"></a><a name="cce_01_0150_zh-cn_topic_0107283470_p122831140486"></a>* 容器名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0150_zh-cn_topic_0107283470_p528314415486"><a name="cce_01_0150_zh-cn_topic_0107283470_p528314415486"></a><a name="cce_01_0150_zh-cn_topic_0107283470_p528314415486"></a>容器的名称，可修改。</p>
        </td>
        </tr>
        <tr id="cce_01_0150_zh-cn_topic_0107283470_row152831345485"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="cce_01_0150_zh-cn_topic_0107283470_p875325925918"><a name="cce_01_0150_zh-cn_topic_0107283470_p875325925918"></a><a name="cce_01_0150_zh-cn_topic_0107283470_p875325925918"></a>容器规格</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><p id="cce_01_0150_p5379182494610"><a name="cce_01_0150_p5379182494610"></a><a name="cce_01_0150_p5379182494610"></a><strong id="cce_01_0150_b2155195713314"><a name="cce_01_0150_b2155195713314"></a><a name="cce_01_0150_b2155195713314"></a>CPU配额：</strong></p>
        <a name="cce_01_0150_ul67283495467"></a><a name="cce_01_0150_ul67283495467"></a><ul id="cce_01_0150_ul67283495467"><li>申请：容器需要使用的最小CPU值，默认0.25Core。</li><li>限制：允许容器使用的CPU最大值。建议设容器配额的最高限额，避免容器资源超额导致系统故障。</li></ul>
        <p id="cce_01_0150_p633394210502"><a name="cce_01_0150_p633394210502"></a><a name="cce_01_0150_p633394210502"></a><strong id="cce_01_0150_b5114173113411"><a name="cce_01_0150_b5114173113411"></a><a name="cce_01_0150_b5114173113411"></a>内存配额：</strong></p>
        <a name="cce_01_0150_ul14326165915010"></a><a name="cce_01_0150_ul14326165915010"></a><ul id="cce_01_0150_ul14326165915010"><li>申请：容器需要使用的内存最小值，默认0.5GiB。</li><li>限制：允许容器使用的内存最大值。如果超过，容器会被终止。</li></ul>
        <p id="cce_01_0150_p1825119142351"><a name="cce_01_0150_p1825119142351"></a><a name="cce_01_0150_p1825119142351"></a>申请和限制的具体请参见<a href="设置容器规格.md">设置容器规格</a>。</p>
        <p id="cce_01_0150_p38521896343"><a name="cce_01_0150_p38521896343"></a><a name="cce_01_0150_p38521896343"></a><strong id="cce_01_0150_b11557151512341"><a name="cce_01_0150_b11557151512341"></a><a name="cce_01_0150_b11557151512341"></a>GPU配额：</strong>当集群中包含GPU节点时，才能设置GPU，无GPU节点不显示此选项。</p>
        <p id="cce_01_0150_p15403132914341"><a name="cce_01_0150_p15403132914341"></a><a name="cce_01_0150_p15403132914341"></a>容器需要使用的GPU百分比。勾选<span class="uicontrol" id="cce_01_0150_uicontrol952171455614"><a name="cce_01_0150_uicontrol952171455614"></a><a name="cce_01_0150_uicontrol952171455614"></a>“使用”</span>并设置百分比，例如设置为10%，表示该容器需使用GPU资源的10%。若不勾选<span class="uicontrol" id="cce_01_0150_uicontrol12950184715612"><a name="cce_01_0150_uicontrol12950184715612"></a><a name="cce_01_0150_uicontrol12950184715612"></a>“使用”</span>，或设置为0，则无法使用GPU资源。</p>
        <p id="cce_01_0150_p9626154413340"><a name="cce_01_0150_p9626154413340"></a><a name="cce_01_0150_p9626154413340"></a><strong id="cce_01_0150_b423894943411"><a name="cce_01_0150_b423894943411"></a><a name="cce_01_0150_b423894943411"></a>GPU显卡：</strong>工作负载实例将被调度到GPU显卡类型为指定显卡的节点上。</p>
        <p id="cce_01_0150_p15765438173416"><a name="cce_01_0150_p15765438173416"></a><a name="cce_01_0150_p15765438173416"></a>若勾选“不限制”，容器将会随机使用节点中的任一显卡。您也可以勾选某个显卡，容器将使用特定显卡。</p>
        <p id="cce_01_0150_p58663964520"><a name="cce_01_0150_p58663964520"></a><a name="cce_01_0150_p58663964520"></a><strong id="cce_01_0150_b188666944516"><a name="cce_01_0150_b188666944516"></a><a name="cce_01_0150_b188666944516"></a>昇腾&nbsp;310配额：</strong>容器需要使用的昇腾 310芯片个数，此处须为整数。</p>
        <p id="cce_01_0150_p2097772173513"><a name="cce_01_0150_p2097772173513"></a><a name="cce_01_0150_p2097772173513"></a>选用AI加速型节点并安装<strong id="cce_01_0150_b99085210250"><a name="cce_01_0150_b99085210250"></a><a name="cce_01_0150_b99085210250"></a>huawei-npu</strong>插件后该参数设置将生效。AI加速型节点目前已开放公测，该节点搭载高性能、低功耗的海思Ascend 310 AI处理器，适用于图像识别、视频处理、推理计算以及机器学习等场景，点此可<a href="https://account.huaweicloud.com/usercenter/#/userindex/betaManagement?serviceCode=ecs_ascend_ai1" target="_blank" rel="noopener noreferrer">立即申请</a>。</p>
        </td>
        </tr>
        </tbody>
        </table>

    3.  （可选）高级设置。

        **表 4**  高级设置

        <a name="tf56c7b65fd00476dbf686d494609ec01"></a>
        <table><thead align="left"><tr id="rd70607f9bfa74a83a6e424e8abda265c"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.3.1.1"><p id="a85705044d3104d34957e244b20e98de2"><a name="a85705044d3104d34957e244b20e98de2"></a><a name="a85705044d3104d34957e244b20e98de2"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="77%" id="mcps1.2.3.1.2"><p id="ab80a0aae28b54ab1afe9009e2466b2e6"><a name="ab80a0aae28b54ab1afe9009e2466b2e6"></a><a name="ab80a0aae28b54ab1afe9009e2466b2e6"></a>参数说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="r616e69d5a2004b079888d8a4a2a83762"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="ae1906e2a0f4e48c8a290d2ffdc9e83bf"><a name="ae1906e2a0f4e48c8a290d2ffdc9e83bf"></a><a name="ae1906e2a0f4e48c8a290d2ffdc9e83bf"></a>生命周期</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><div class="p" id="p35489275239"><a name="p35489275239"></a><a name="p35489275239"></a>生命周期脚本定义，主要针对容器类任务的生命周期事件工作负载采取的动作。<a name="u86a34d59537a4e5ebbcd8d62f0fb6fc7"></a><a name="u86a34d59537a4e5ebbcd8d62f0fb6fc7"></a><ul id="u86a34d59537a4e5ebbcd8d62f0fb6fc7"><li>启动命令：输入容器启动命令，容器启动后会立即执行。详细步骤请参见<a href="容器设置.md">容器设置</a>。</li><li>启动后处理：任务启动后触发。详细步骤请参见<a href="设置容器生命周期.md">设置容器生命周期</a>。</li><li>停止前处理：任务停止前触发。详细步骤请参见<a href="设置容器生命周期.md">设置容器生命周期</a>。</li></ul>
        </div>
        </td>
        </tr>
        <tr id="r159688429d2c4ad5b55d2b63b5bc6a46"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.3.1.1 "><p id="acab0841bbf1548e08722d5ec9fb378e9"><a name="acab0841bbf1548e08722d5ec9fb378e9"></a><a name="acab0841bbf1548e08722d5ec9fb378e9"></a>环境变量</p>
        </td>
        <td class="cellrowborder" valign="top" width="77%" headers="mcps1.2.3.1.2 "><div class="p" id="p19408181613184"><a name="p19408181613184"></a><a name="p19408181613184"></a>在容器中添加环境变量，一般用于通过环境变量设置参数。在<span class="uicontrol" id="uicontrol148428462214"><a name="uicontrol148428462214"></a><a name="uicontrol148428462214"></a>“环境变量”</span>页签，单击<span class="uicontrol" id="uicontrol9842146626"><a name="uicontrol9842146626"></a><a name="uicontrol9842146626"></a>“添加环境变量”</span>。当前支持三种类型。<a name="ul145379401817"></a><a name="ul145379401817"></a><ul id="ul145379401817"><li>手动添加：输入变量名称、变量/变量引用。</li><li>密钥导入：输入变量名称，选择导入的密钥名称和数据。您需要提前创建密钥，具体请参见<a href="创建密钥.md">创建密钥</a>。</li><li>配置项导入：输入变量名称，选择导入的配置项名称和数据。您需要提前创建配置项，具体请参见<a href="创建配置项.md">创建配置项</a>。</li></ul>
        </div>
        </td>
        </tr>
        </tbody>
        </table>

    4.  （可选）一个任务实例包含1个或多个相关容器。若您的任务包含多个容器，请单击“添加容器”，再执行添加容器的操作。

7.  设置完成后，单击“创建“。

    待状态为“已启动“，定时任务创建成功。


## 使用kubectl创建CronJob<a name="section13519162224919"></a>

CronJob的配置参数如下所示：

-   .spec.schedule指定任务运行时间与周期，格式与[Cron](https://en.wikipedia.org/wiki/Cron)相同，例如“0 \* \* \* \* “或“@hourly“。
-   .spec.jobTemplate指定需要运行的任务，格式与[使用kubectl创建Job](创建普通任务(Job).md#section450152719412)相同。
-   .spec.startingDeadlineSeconds指定任务开始的截止期限。
-   .spec.concurrencyPolicy指定任务的并发策略，支持Allow、Forbid和Replace三个选项。
    -   Allow（默认）：允许并发运行 Job。
    -   Forbid：禁止并发运行，如果前一个还没有完成，则直接跳过下一个。
    -   Replace：取消当前正在运行的 Job，用一个新的来替换。


下面是一个CronJob的示例，保存在cronjob.yaml文件中。

```
apiVersion: batch/v1beta1
kind: CronJob
metadata:
  name: hello
spec:
  schedule: "*/1 * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: hello
            image: busybox
            args:
            - /bin/sh
            - -c
            - date; echo Hello from the Kubernetes cluster
          restartPolicy: OnFailure
```

1.  创建CronJob。

    **kubectl create -f cronjob.yaml**

    命令行终端显示如下信息：

    ```
    cronjob.batch/hello created
    ```

2.  执行如下命令，查看执行情况。

    **kubectl get cronjob**

    ```
    NAME      SCHEDULE      SUSPEND   ACTIVE    LAST SCHEDULE   AGE
    hello     */1 * * * *   False     0         <none>          9s
    ```

    **kubectl get jobs**

    ```
    NAME               COMPLETIONS   DURATION   AGE
    hello-1597387980   1/1           27s        45s
    ```

    **kubectl get pod**

    ```
    NAME                           READY     STATUS      RESTARTS   AGE
    hello-1597387980-tjv8f         0/1       Completed   0          114s
    hello-1597388040-lckg9         0/1       Completed   0          39s
    ```

    **kubectl logs hello-1597387980-tjv8f**

    ```
    Fri Aug 14 06:56:31 UTC 2020
    Hello from the Kubernetes cluster
    ```

    **kubectl delete cronjob hello**

    ```
    cronjob.batch "hello" deleted
    ```

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >删除CronJob时，对应的普通任务及相关的Pod都会被删除。


## 相关操作<a name="s28175da725cf46d49a4cfca59155a5d2"></a>

定时任务创建完成后，您还可执行[表5](#t6d520710097a4ee098eae42bcb508608)中操作。

**表 5**  其他操作

<a name="t6d520710097a4ee098eae42bcb508608"></a>
<table><thead align="left"><tr id="r8d59bf3aa5394e84ae626a36c585013d"><th class="cellrowborder" valign="top" width="28.999999999999996%" id="mcps1.2.3.1.1"><p id="a8245dffabcbf4810a7333d8ce9a67789"><a name="a8245dffabcbf4810a7333d8ce9a67789"></a><a name="a8245dffabcbf4810a7333d8ce9a67789"></a>操作</p>
</th>
<th class="cellrowborder" valign="top" width="71%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0093532762_p685713442569"><a name="zh-cn_topic_0093532762_p685713442569"></a><a name="zh-cn_topic_0093532762_p685713442569"></a>操作说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row82414466296"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="p147711757162810"><a name="p147711757162810"></a><a name="p147711757162810"></a>编辑YAML</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><p id="p15771257142816"><a name="p15771257142816"></a><a name="p15771257142816"></a>单击定时任务名称后的<span class="uicontrol" id="uicontrol33801326152917"><a name="uicontrol33801326152917"></a><a name="uicontrol33801326152917"></a>“编辑YAML”</span>，可修改当前任务对应的YAML文件。</p>
</td>
</tr>
<tr id="r25f2ff5451494127b1af5ab34b807936"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="a6abaef816404455581dc7dbaddf656ee"><a name="a6abaef816404455581dc7dbaddf656ee"></a><a name="a6abaef816404455581dc7dbaddf656ee"></a>停止定时任务</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><a name="obe7516d58ade42a389e52e27f663e03d"></a><a name="obe7516d58ade42a389e52e27f663e03d"></a><ol id="obe7516d58ade42a389e52e27f663e03d"><li>选择待停止的任务，单击操作列的“停止”。</li><li>单击“确定”。</li></ol>
</td>
</tr>
<tr id="r9fec8c34ebbb44e3888c677862a174e0"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0093532762_p685874410564"><a name="zh-cn_topic_0093532762_p685874410564"></a><a name="zh-cn_topic_0093532762_p685874410564"></a>删除定时任务</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><a name="o9409a54b32c14e4799c05e5f0a643633"></a><a name="o9409a54b32c14e4799c05e5f0a643633"></a><ol id="o9409a54b32c14e4799c05e5f0a643633"><li>选择待删除的任务，单击操作列的<span class="uicontrol" id="ub5a9da6130d04758b1d07c5b9e4f06e0"><a name="ub5a9da6130d04758b1d07c5b9e4f06e0"></a><a name="ub5a9da6130d04758b1d07c5b9e4f06e0"></a>“删除”</span>。</li><li>单击“确定”。<p id="a3be1d4db3fa4464dbc950b89a31d57aa"><a name="a3be1d4db3fa4464dbc950b89a31d57aa"></a><a name="a3be1d4db3fa4464dbc950b89a31d57aa"></a>任务删除后将无法恢复，请谨慎操作。</p>
</li></ol>
</td>
</tr>
</tbody>
</table>

