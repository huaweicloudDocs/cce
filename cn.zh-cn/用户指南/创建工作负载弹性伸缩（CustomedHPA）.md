# 创建工作负载弹性伸缩（CustomedHPA）<a name="cce_01_0292"></a>

CustomedHPA策略是华为云自研的弹性伸缩增强能力，能够基于指标（CPU利用率、内存利用率）或周期（每天、每周、每月或每年的具体时间点），对无状态工作负载进行弹性扩缩容。

主要功能如下：

-   支持按照当前实例数的百分比进行扩缩容。
-   支持设置一次扩缩容的最小步长。
-   支持按照实际指标值执行不同的扩缩容动作。

## 前提条件<a name="section194973810277"></a>

若使用CustomedHPA策略，则必须安装[cce-hpa-controller](cce-hpa-controller.md)和[prometheus](prometheus.md)插件，且两个插件版本均需为1.1.0及以上：

-   cce-hpa-controller：支持按照当前实例数的百分比进行扩缩容；支持设置一次扩缩容的最小步长；支持按照实际指标值执行不同的扩缩容动作。创建CustomedHPA策略必须安装此插件。
-   prometheus：负责采集kubernetes集群中kubelet的公开指标项（CPU利用率、内存利用率）。创建CustomedHPA策略必须安装此插件。

## 约束与限制<a name="section107429267459"></a>

-   CustomedHPA策略：仅支持1.15及以上版本的集群创建。
-   CustomedHPA策略不支持鲲鹏集群。
-   每个工作负载只能创建一个策略，即如果您创建了一个[HPA策略](创建工作负载弹性伸缩（HPA）.md)，则不能再对其创建CustomedHPA策略或其他HPA策略，您可以删除该HPA策略后再创建。

## 操作步骤<a name="section15633192745418"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“弹性伸缩“，在“工作负载伸缩“页签下，单击“创建CustomedHPA策略“按钮。
2.  进入创建工作负载CustomedHPA策略页面，在“插件检测“步骤中：
    -   若插件名称后方显示![](figures/zh-cn_image_0000001089686450.png)，请单击插件后方的“现在安装“按钮，根据业务需求配置插件参数后单击“立即安装“，等待插件安装完成。
    -   若插件名称后方显示![](figures/zh-cn_image_0000001136785453.png)，则说明插件已安装成功。

3.  确认插件已安装成功后，单击“下一步：策略配置“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果插件已提前安装成功，单击“创建CustomedHPA策略”按钮后，在“插件检测“步骤中经过短暂检测后将直接进入“策略配置“步骤。

4.  在“策略配置“步骤中，参照[表1](#table1318553420299)设置策略参数。

    **表 1**  CustomedHPA策略参数配置

    <a name="table1318553420299"></a>
    <table><thead align="left"><tr id="row1718512347298"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p21851034142915"><a name="p21851034142915"></a><a name="p21851034142915"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p9185134122918"><a name="p9185134122918"></a><a name="p9185134122918"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row13185434192914"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1818519343291"><a name="p1818519343291"></a><a name="p1818519343291"></a>策略名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p171851134112914"><a name="p171851134112914"></a><a name="p171851134112914"></a>新建策略的名称，请自定义。</p>
    </td>
    </tr>
    <tr id="row6185133422918"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p418573419299"><a name="p418573419299"></a><a name="p418573419299"></a>集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p181851034152917"><a name="p181851034152917"></a><a name="p181851034152917"></a>请选择工作负载所在的集群。</p>
    </td>
    </tr>
    <tr id="row14185173417296"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p61852346296"><a name="p61852346296"></a><a name="p61852346296"></a>命名空间</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p12185163410297"><a name="p12185163410297"></a><a name="p12185163410297"></a>请选择工作负载所在的命名空间。</p>
    </td>
    </tr>
    <tr id="row2018563419298"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p13185133415295"><a name="p13185133415295"></a><a name="p13185133415295"></a>关联工作负载</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p181851934122917"><a name="p181851934122917"></a><a name="p181851934122917"></a>请选择要设置CustomedHPA策略的工作负载。</p>
    </td>
    </tr>
    <tr id="row1318511345294"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1918573418291"><a name="p1918573418291"></a><a name="p1918573418291"></a>实例范围</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p17739423181414"><a name="p17739423181414"></a><a name="p17739423181414"></a>请输入最小实例数和最大实例数。</p>
    <p id="p1718553411296"><a name="p1718553411296"></a><a name="p1718553411296"></a>策略触发时，工作负载实例将在此范围内伸缩。</p>
    </td>
    </tr>
    <tr id="row1428311016121"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1328314013126"><a name="p1328314013126"></a><a name="p1328314013126"></a>冷却时间</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p161910175143"><a name="p161910175143"></a><a name="p161910175143"></a>请输入冷却时间值，单位为分钟。</p>
    <p id="p9283180161212"><a name="p9283180161212"></a><a name="p9283180161212"></a>策略成功触发后，在此冷却时间内，不会再次触发缩容/扩容，目的是等待伸缩动作完成后在系统稳定且集群正常的情况下进行下一次策略匹配。</p>
    </td>
    </tr>
    <tr id="row20185183462913"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p918583418295"><a name="p918583418295"></a><a name="p918583418295"></a>策略规则</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p3272153618157"><a name="p3272153618157"></a><a name="p3272153618157"></a>单击<span class="uicontrol" id="uicontrol827055114156"><a name="uicontrol827055114156"></a><a name="uicontrol827055114156"></a>“添加策略规则”</span>在弹出的窗口中设置伸缩策略参数：</p>
    <a name="ul1118523472911"></a><a name="ul1118523472911"></a><ul id="ul1118523472911"><li>规则名称：请输入规则名称，可自定义。</li><li>类型：可选择<span class="uicontrol" id="uicontrol111853343295"><a name="uicontrol111853343295"></a><a name="uicontrol111853343295"></a>“指标触发”</span>或<span class="uicontrol" id="uicontrol8537183924318"><a name="uicontrol8537183924318"></a><a name="uicontrol8537183924318"></a>“周期触发”</span>。</li></ul>
    <p id="p51991125164415"><a name="p51991125164415"></a><a name="p51991125164415"></a><strong id="b112712277447"><a name="b112712277447"></a><a name="b112712277447"></a>指标触发</strong></p>
    <a name="ul7210112510444"></a><a name="ul7210112510444"></a><ul id="ul7210112510444"><li>触发条件：请选择<span class="uicontrol" id="uicontrol92106257445"><a name="uicontrol92106257445"></a><a name="uicontrol92106257445"></a>“CPU利用率”</span>或<span class="uicontrol" id="uicontrol20210725144412"><a name="uicontrol20210725144412"></a><a name="uicontrol20210725144412"></a>“内存利用率”</span>，选择<span class="uicontrol" id="uicontrol0210182534413"><a name="uicontrol0210182534413"></a><a name="uicontrol0210182534413"></a>“&gt;”</span>或<span class="uicontrol" id="uicontrol32101925184420"><a name="uicontrol32101925184420"></a><a name="uicontrol32101925184420"></a>“&lt;”</span>，并输入百分比的值。如<a href="#fig16210182584412">图1</a>中所示，则表示CPU利用率瞬时值 &gt; 50% 时，立即执行此规则。<div class="fignone" id="fig16210182584412"><a name="fig16210182584412"></a><a name="fig16210182584412"></a><span class="figcap"><b>图1 </b>触发条件</span><br><a name="image5615192313225"></a><a name="image5615192313225"></a><span><img id="image5615192313225" src="figures/触发条件.png" width="413.63" height="131.699792"></span></div>
    </li><li>执行动作：与上述<span class="uicontrol" id="uicontrol1621082513447"><a name="uicontrol1621082513447"></a><a name="uicontrol1621082513447"></a>“触发条件”</span>相对应，达到触发条件值后所要执行的动作，可添加多个执行动作。如<a href="#fig921072518446">图2</a>中所示，当CPU利用率超过50%时将伸缩至5个实例，当超过70%时伸缩至8个实例，当超过90%时在8个实例基础上再增加10个实例。反之，按此规则执行缩容。<div class="fignone" id="fig921072518446"><a name="fig921072518446"></a><a name="fig921072518446"></a><span class="figcap"><b>图2 </b>执行动作</span><br><a name="image1226732611245"></a><a name="image1226732611245"></a><span><img id="image1226732611245" src="figures/执行动作.png" width="413.63" height="138.05293600000002"></span></div>
    </li><li>是否启用：可单击启用或关闭该策略规则。</li></ul>
    <p id="p1559773314518"><a name="p1559773314518"></a><a name="p1559773314518"></a><strong id="b1244574912453"><a name="b1244574912453"></a><a name="b1244574912453"></a>周期触发</strong></p>
    <a name="ul676113102462"></a><a name="ul676113102462"></a><ul id="ul676113102462"><li>触发时间：可选择每天、每周、每月或每年的具体时间点，如设置为<a href="#fig626073005017">图3</a>所示，则为每天17:00触发。<div class="fignone" id="fig626073005017"><a name="fig626073005017"></a><a name="fig626073005017"></a><span class="figcap"><b>图3 </b>周期触发-每天</span><br><a name="image814831725011"></a><a name="image814831725011"></a><span><img id="image814831725011" src="figures/周期触发-每天.png" height="178.12929400000002" width="413.63"></span></div>
    </li><li>执行动作：与上述<span class="uicontrol" id="uicontrol9492546161716"><a name="uicontrol9492546161716"></a><a name="uicontrol9492546161716"></a>“触发时间”</span>相对应，达到触发时间值后所要执行的动作。如<a href="#fig5492546111720">图4</a>中所示，即每天17:00时将执行减少4个实例的动作。<div class="fignone" id="fig5492546111720"><a name="fig5492546111720"></a><a name="fig5492546111720"></a><span class="figcap"><b>图4 </b>周期触发-执行动作</span><br><a name="image11168046532"></a><a name="image11168046532"></a><span><img id="image11168046532" src="figures/周期触发-执行动作.png" width="413.63" height="272.199795"></span></div>
    </li><li>是否启用：可单击启用或关闭该策略规则。</li></ul>
    <p id="p16849185724113"><a name="p16849185724113"></a><a name="p16849185724113"></a>单击确定后，您可以在<span class="uicontrol" id="uicontrol38493574412"><a name="uicontrol38493574412"></a><a name="uicontrol38493574412"></a>“策略规则”</span>列表中查看添加的规则，并可执行开启关闭、编辑、删除等操作。</p>
    <p id="p191851634172918"><a name="p191851634172918"></a><a name="p191851634172918"></a>单击<span class="uicontrol" id="uicontrol14289104184212"><a name="uicontrol14289104184212"></a><a name="uicontrol14289104184212"></a>“策略规则”</span>列表下方的<span class="uicontrol" id="uicontrol418543422918"><a name="uicontrol418543422918"></a><a name="uicontrol418543422918"></a>“添加策略规则”</span>，可设置多条策略。</p>
    </td>
    </tr>
    </tbody>
    </table>

5.  设置完成后，单击“创建“，在“完成“步骤中若显示“创建工作负载策略\*\*\*提交成功“，可单击“返回工作负载伸缩策略“。
6.  在“工作负载伸缩“页签下，可以看到刚刚创建的CustomedHPA策略。

    **图 5**  创建CustomedHPA策略<a name="fig111856344292"></a>  
    ![](figures/创建CustomedHPA策略.png "创建CustomedHPA策略")


