# 创建工作负载弹性伸缩（HPA）<a name="cce_10_0208"></a>

HPA策略即Horizontal Pod Autoscaling，是Kubernetes中实现POD水平自动伸缩的功能。该策略在kubernetes社区HPA功能的基础上，增加了应用级别的冷却时间窗和扩缩容阈值等功能。

## 前提条件<a name="section194973810277"></a>

使用HPA需要安装能够提供Metrics API的插件，如metrics-server或Prometheus。

## 约束与限制<a name="section107429267459"></a>

-   HPA策略：仅支持1.13及以上版本的集群创建。
-   每个工作负载只能创建一个策略，即如果您创建了一个HPA策略，则不能再对其创建[CustomedHPA策略](创建工作负载弹性伸缩（CustomedHPA）.md)或其他HPA策略，您可以删除该HPA策略后再创建。
-   1.19.10以下版本的集群中，如果使用HPA策略对挂载了EVS卷的负载进行扩容，当新Pod被调度到另一个节点时，会导致之前Pod不能正常读写。

    1.19.10及以上版本集群中，如果使用HPA策略对挂载了EVS卷的负载进行扩容，新Pod会因为无法挂载云硬盘导致无法成功启动。


## 操作步骤<a name="section12371183611583"></a>

1.  在CCE控制台，进入集群。
2.  单击左侧导航栏的“负载伸缩“，在右上角单击“创建HPA策略“。
3.  填写策略参数。

    **表 1**  HPA策略参数配置

    <a name="table8638121213265"></a>
    <table><thead align="left"><tr id="row10638181262612"><th class="cellrowborder" valign="top" width="20.02%" id="mcps1.2.3.1.1"><p id="p1063821214265"><a name="p1063821214265"></a><a name="p1063821214265"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="79.97999999999999%" id="mcps1.2.3.1.2"><p id="p1638181232617"><a name="p1638181232617"></a><a name="p1638181232617"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1922964644615"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p9231104613468"><a name="p9231104613468"></a><a name="p9231104613468"></a>策略名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p285719544104"><a name="p285719544104"></a><a name="p285719544104"></a>新建策略的名称，请自定义。</p>
    </td>
    </tr>
    <tr id="row12321131519262"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p14322181522614"><a name="p14322181522614"></a><a name="p14322181522614"></a>命名空间</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1950113815188"><a name="p1950113815188"></a><a name="p1950113815188"></a>请选择工作负载所在的命名空间。</p>
    </td>
    </tr>
    <tr id="row1063812126263"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p15639812122620"><a name="p15639812122620"></a><a name="p15639812122620"></a>关联工作负载</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1520317181911"><a name="p1520317181911"></a><a name="p1520317181911"></a>请选择要设置HPA策略的工作负载。</p>
    </td>
    </tr>
    <tr id="row6649879161231"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p1769363161231"><a name="p1769363161231"></a><a name="p1769363161231"></a>实例范围</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p833113449476"><a name="p833113449476"></a><a name="p833113449476"></a>请输入最小实例数和最大实例数。</p>
    <p id="p9100682161231"><a name="p9100682161231"></a><a name="p9100682161231"></a>策略触发时，工作负载实例将在此范围内伸缩。</p>
    </td>
    </tr>
    <tr id="row22668444436"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p426616448432"><a name="p426616448432"></a><a name="p426616448432"></a>冷却时间</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p1344913426116"><a name="p1344913426116"></a><a name="p1344913426116"></a>请输入缩容和扩容的冷却时间，单位为分钟，<strong id="b211841145615"><a name="b211841145615"></a><a name="b211841145615"></a>缩容扩容冷却时间不能小于1分钟</strong>。</p>
    <p id="p0735245104710"><a name="p0735245104710"></a><a name="p0735245104710"></a><strong id="b753810511926"><a name="b753810511926"></a><a name="b753810511926"></a>该设置仅在1.15及以上版本的集群中显示，1.13版本的集群不支持该设置。</strong></p>
    <p id="p142661744204313"><a name="p142661744204313"></a><a name="p142661744204313"></a>策略成功触发后，在此缩容/扩容冷却时间内，不会再次触发缩容/扩容，目的是等待伸缩动作完成后在系统稳定且集群正常的情况下进行下一次策略匹配。</p>
    </td>
    </tr>
    <tr id="row572593234714"><td class="cellrowborder" valign="top" width="20.02%" headers="mcps1.2.3.1.1 "><p id="p14725432104718"><a name="p14725432104718"></a><a name="p14725432104718"></a>策略规则</p>
    </td>
    <td class="cellrowborder" valign="top" width="79.97999999999999%" headers="mcps1.2.3.1.2 "><p id="p18192141410482"><a name="p18192141410482"></a><a name="p18192141410482"></a>策略规则可基于系统指标或自定义指标。</p>
    <p id="p1287715471508"><a name="p1287715471508"></a><a name="p1287715471508"></a><strong id="b18454121017616"><a name="b18454121017616"></a><a name="b18454121017616"></a>系统策略</strong></p>
    <a name="ul56611653205511"></a><a name="ul56611653205511"></a><ul id="ul56611653205511"><li>指标：可选择<span class="uicontrol" id="uicontrol17979142025717"><a name="uicontrol17979142025717"></a><a name="uicontrol17979142025717"></a>“CPU利用率”</span>或<span class="uicontrol" id="uicontrol48221818165719"><a name="uicontrol48221818165719"></a><a name="uicontrol48221818165719"></a>“内存利用率”</span>。<div class="note" id="note1751133503518"><a name="note1751133503518"></a><a name="note1751133503518"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p12511735183515"><a name="p12511735183515"></a><a name="p12511735183515"></a>利用率 = 工作负载Pod的实际使用量 / 申请量。</p>
    </div></div>
    </li><li>期望值：请输入期望资源平均利用率。<p id="p541111525356"><a name="p541111525356"></a><a name="p541111525356"></a>期望值表示所选指标的期望值，通过向上取整(当前指标值 / 期望值 × 当前实例数)来计算需要伸缩的实例数。</p>
    </li><li>阈值：请输入缩容和扩容阈值。<p id="p795694153617"><a name="p795694153617"></a><a name="p795694153617"></a>当指标值大于缩容阈值且小于扩容阈值时，不会触发扩容或缩容。<strong id="b5203123414405"><a name="b5203123414405"></a><a name="b5203123414405"></a>阈值仅在1.15及以上版本的集群中支持</strong>。</p>
    </li></ul>
    <p id="p08270292315"><a name="p08270292315"></a><a name="p08270292315"></a><strong id="b8532172013619"><a name="b8532172013619"></a><a name="b8532172013619"></a>自定义指标（<strong id="b1990716241417"><a name="b1990716241417"></a><a name="b1990716241417"></a>仅在1.15及以上版本的集群中支持</strong>）</strong></p>
    <a name="ul173519325217"></a><a name="ul173519325217"></a><ul id="ul173519325217"><li>自定义指标名称：自定义指标的名称，输入时可根据联想值进行选择。<p id="p330220386313"><a name="p330220386313"></a><a name="p330220386313"></a>使用该功能需要您安装<a href="prometheus.md">prometheus</a>插件，采集自定义指标的方法及示例请参见<a href="使用Prometheus插件监控.md#section179021319175">监控自定义指标</a>。</p>
    </li><li>指标来源：在下拉框中选择对象类型，可选择“Pod”。</li><li>期望值：Pod支持指标为平均值。</li><li>阈值：缩容和扩容的阈值。只有指标当前值在阈值范围外时会进行扩缩容。指标值大于缩容阈值且小于扩容阈值时，不会触发扩容或缩容。</li></ul>
    <div class="note" id="note766672912376"><a name="note766672912376"></a><a name="note766672912376"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p4667729193716"><a name="p4667729193716"></a><a name="p4667729193716"></a>HPA在计算扩容、缩容实例数时，会选择最近5分钟内实例数的最大值。</p>
    </div></div>
    </td>
    </tr>
    </tbody>
    </table>

4.  设置完成后，单击“创建“，在“完成“步骤中若显示“创建工作负载策略\*\*\*提交成功“，可单击“返回工作负载伸缩策略“。
5.  在“工作负载伸缩“页签下，可以看到刚刚创建的HPA策略。

