# cce-hpa-controller<a name="cce_10_0240"></a>

cce-hpa-controller插件是一款CCE自研的插件，能够基于CPU利用率、内存利用率等指标，对无状态工作负载进行弹性扩缩容。

安装本插件后，可在“弹性伸缩“页面的“工作负载伸缩“页签下，创建CustomedHPA策略，具体请参见[创建工作负载弹性伸缩（CustomedHPA）](创建工作负载弹性伸缩（CustomedHPA）.md)。

## 主要功能<a name="section16202940121214"></a>

-   支持按照当前实例数的百分比进行扩缩容。
-   支持设置一次扩缩容的最小步长。
-   支持按照实际指标值执行不同的扩缩容动作。

## 约束与限制<a name="section147226815158"></a>

-   仅支持在v1.15及以上版本的CCE集群中安装本插件。
-   若cce-hpa-controller版本低于1.2.11，则必须安装[prometheus](prometheus.md)插件，若版本大于或等于1.2.11，则需要安装能够提供Metrics API的插件，如metrics-server和Prometheus。若使用Prometheus，需要将Prometheus注册为Metrics API的服务，详见[提供资源指标](prometheus.md#section13409107262)。

## 安装插件<a name="section046523415137"></a>

1.  登录CCE控制台，单击集群名称进入集群，单击左侧导航栏的“插件管理“，在右侧找到**cce-hpa-controller**，单击“安装“。
2.  该插件可配置“单实例“或“自定义“规格。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >单实例仅用于验证场景，商用场景请根据集群规格使用"自定义"资源配置，cce-hpa-controller插件的规格大小主要受集群中总容器数量和伸缩策略数量影响，通常场景下建议每5000容器配置CPU 500m, 内存1000Mi资源，每1000伸缩策略CPU 100m，内存500Mi。

    -   实例数：选择自定义规格时，请根据业务需求选择合适的实例数。
    -   容器：选择自定义规格时，请根据业务需求选择合适的容器配额。

3.  单击“安装“。

## 版本记录<a name="section183121449435"></a>

**表 1**  CCE插件版本记录

<a name="table88489551792"></a>
<table><thead align="left"><tr id="row139251455994"><th class="cellrowborder" valign="top" width="37.46281342966426%" id="mcps1.2.3.1.1"><p id="p13601510205420"><a name="p13601510205420"></a><a name="p13601510205420"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="62.53718657033575%" id="mcps1.2.3.1.2"><p id="p156011107542"><a name="p156011107542"></a><a name="p156011107542"></a>支持的集群版本</p>
</th>
</tr>
</thead>
<tbody><tr id="row12883172915519"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p1582773613513"><a name="p1582773613513"></a><a name="p1582773613513"></a>1.3.3</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p156598431559"><a name="p156598431559"></a><a name="p156598431559"></a>/v1.(19|21|23|25).*/</p>
</td>
</tr>
<tr id="row8757710175517"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p17256152414514"><a name="p17256152414514"></a><a name="p17256152414514"></a>1.3.1</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p79409120467"><a name="p79409120467"></a><a name="p79409120467"></a><span>/v1.(19|21|23).*/</span></p>
</td>
</tr>
<tr id="row17276317105810"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p182561724653"><a name="p182561724653"></a><a name="p182561724653"></a>1.2.12</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p146211648124613"><a name="p146211648124613"></a><a name="p146211648124613"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row723201855819"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p102563241155"><a name="p102563241155"></a><a name="p102563241155"></a>1.2.11</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p1525510619478"><a name="p1525510619478"></a><a name="p1525510619478"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row19850201865813"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p625615241655"><a name="p625615241655"></a><a name="p625615241655"></a>1.2.10</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p42571367475"><a name="p42571367475"></a><a name="p42571367475"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row1331711107"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p925614241159"><a name="p925614241159"></a><a name="p925614241159"></a>1.2.4</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p182592624711"><a name="p182592624711"></a><a name="p182592624711"></a>/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row56109111006"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p125617241650"><a name="p125617241650"></a><a name="p125617241650"></a>1.2.3</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p1225616241517"><a name="p1225616241517"></a><a name="p1225616241517"></a>/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row97371611105"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p725617242512"><a name="p725617242512"></a><a name="p725617242512"></a>1.2.2</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p132561624859"><a name="p132561624859"></a><a name="p132561624859"></a>/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row1387891111011"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p3257102420516"><a name="p3257102420516"></a><a name="p3257102420516"></a>1.2.1</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p6257324755"><a name="p6257324755"></a><a name="p6257324755"></a>/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row108141216015"><td class="cellrowborder" valign="top" width="37.46281342966426%" headers="mcps1.2.3.1.1 "><p id="p172575244510"><a name="p172575244510"></a><a name="p172575244510"></a>1.1.3</p>
</td>
<td class="cellrowborder" valign="top" width="62.53718657033575%" headers="mcps1.2.3.1.2 "><p id="p1225718241253"><a name="p1225718241253"></a><a name="p1225718241253"></a>/v1.(15|17).*/</p>
</td>
</tr>
</tbody>
</table>

