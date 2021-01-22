# cce-hpa-controller<a name="cce_01_0240"></a>

-   [主要功能](#section16202940121214)
-   [约束与限制](#section147226815158)
-   [安装插件](#section046523415137)
-   [升级插件](#section23441939916)
-   [卸载插件](#section1395073191112)
-   [版本记录](#section144262219109)

cce-hpa-controller插件是一款CCE自研的插件，能够基于CPU利用率、内存利用率等指标，对无状态工作负载进行弹性扩缩容。

## 主要功能<a name="section16202940121214"></a>

-   支持按照当前实例数的百分比进行扩缩容。
-   支持设置一次扩缩容的最小步长。
-   支持按照实际指标值执行不同的扩缩容动作。

## 约束与限制<a name="section147226815158"></a>

-   仅支持v1.15及以上版本的混合集群安装本插件。
-   安装本插件后，还需要安装[prometheus插件](prometheus.md)（1.1.0及以上版本），用于指标的采集。

## 安装插件<a name="section046523415137"></a>

安装本插件后，可在“弹性伸缩“页面的“工作负载伸缩“页签下，创建CustomedHPA策略，具体请参见[创建工作负载伸缩策略](创建工作负载伸缩策略.md)。

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击“cce-hpa-controller“下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  该插件可配置“单实例“或“高可用“规格，选择后单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“cce-hpa-controller“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“cce-hpa-controller“插件时，会替换原先节点上的旧版本的“cce-hpa-controller“插件，安装最新版本的“cce-hpa-controller“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  参考[安装插件](#section046523415137)中参数说明配置参数后，单击“升级“即可升级“cce-hpa-controller“插件。

## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击“cce-hpa-controller“下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  cce-hpa-controller版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="24%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row152684214528"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p3639895509"><a name="p3639895509"></a><a name="p3639895509"></a>1.1.3</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p126402917507"><a name="p126402917507"></a><a name="p126402917507"></a>混合集群 v1.(15|17).*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p13640293504"><a name="p13640293504"></a><a name="p13640293504"></a>2020/08/19</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p11113153013506"><a name="p11113153013506"></a><a name="p11113153013506"></a>支持周期扩缩容规则</p>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p156404912504"><a name="p156404912504"></a><a name="p156404912504"></a>1.1.1</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p3640990504"><a name="p3640990504"></a><a name="p3640990504"></a>混合集群 v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p8640189135019"><a name="p8640189135019"></a><a name="p8640189135019"></a>2020/06/23</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p01141830155017"><a name="p01141830155017"></a><a name="p01141830155017"></a>支持周期扩缩容规则</p>
</td>
</tr>
</tbody>
</table>

