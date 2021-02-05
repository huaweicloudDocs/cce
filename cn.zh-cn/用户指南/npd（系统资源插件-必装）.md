# npd（系统资源插件，必装）<a name="cce_01_0132"></a>

-   [插件简介](#section173631312185614)
-   [约束与限制](#section11172124718374)
-   [安装插件](#section189463341114)
-   [卸载插件](#section1395073191112)
-   [升级插件](#section136451128328)
-   [版本记录](#section144262219109)

## 插件简介<a name="section173631312185614"></a>

node-problem-detector（简称：npd）是一款监控集群节点异常事件的插件，以及对接第三方监控平台功能的组件。它是一个在每个节点上运行的守护程序，可从不同的守护进程中搜集节点问题并将其报告给apiserver。node-problem-detector可以作为DaemonSet运行， 也可以独立运行。

该插件为系统资源插件，在1.13以上版本的CCE集群中默认启用该插件 。

有关社区开源项目node-problem-detector的详细信息，请参见[node-problem-detector](https://github.com/kubernetes/node-problem-detector)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>1.15.11和1.17.9版本的混合集群已发布NPD插件新版本1.13.6，诚邀您升级插件。
>为快速提升您NPD插件的能力和可靠性，2020年12月30日后系统将定期自动升级插件到最新版本，升级过程会重启各节点上的NPD容器，但不会对您的业务造成影响。若您想提前体验，可以主动在CCE控制台的“插件管理”页面进行升级。升级插件方法请参见[升级插件](#section136451128328)。
>我们强烈建议您进行此次升级，如果您不希望升级npd插件，可以通过提交工单免除此次升级。

## 约束与限制<a name="section11172124718374"></a>

仅1.13以上版本的混合集群支持此功能。

## 安装插件<a name="section189463341114"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**npd**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  npd插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**npd**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 升级插件<a name="section136451128328"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**npd**下的“升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。

2.  在基本信息页面选择集群和插件版本，单击“下一步“。
3.  云存储插件暂未开放可配置参数，直接单击“升级“即可升级npd插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  npd版本记录

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
<tbody><tr id="row152684214528"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p1295205110548"><a name="p1295205110548"></a><a name="p1295205110548"></a>1.13.6</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p112951051175410"><a name="p112951051175410"></a><a name="p112951051175410"></a>混合集群 v1.15.11|v1.17.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p52951251155419"><a name="p52951251155419"></a><a name="p52951251155419"></a>2020/11/06</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p14441101310554"><a name="p14441101310554"></a><a name="p14441101310554"></a>修复僵尸进程未被回收的问题</p>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p4295115135416"><a name="p4295115135416"></a><a name="p4295115135416"></a>1.13.5</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p629595116542"><a name="p629595116542"></a><a name="p629595116542"></a>混合集群 v1.15.11|v1.17.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p62957519549"><a name="p62957519549"></a><a name="p62957519549"></a>2020/09/12</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p187346147555"><a name="p187346147555"></a><a name="p187346147555"></a>增加污点容忍配置</p>
</td>
</tr>
<tr id="row97875912317"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p129511511543"><a name="p129511511543"></a><a name="p129511511543"></a>1.13.2</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p14295951205417"><a name="p14295951205417"></a><a name="p14295951205417"></a>混合集群 v1.15.11|v1.17.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p192951451165416"><a name="p192951451165416"></a><a name="p192951451165416"></a>2020/08/19</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p17594715105514"><a name="p17594715105514"></a><a name="p17594715105514"></a>增加资源限制，增强cni插件的检测能力</p>
</td>
</tr>
<tr id="row187865919236"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p1229565110547"><a name="p1229565110547"></a><a name="p1229565110547"></a>1.13.0</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p11295175185417"><a name="p11295175185417"></a><a name="p11295175185417"></a>混合集群 v1.(13|15).*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p182951351185413"><a name="p182951351185413"></a><a name="p182951351185413"></a>2019/12/16</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1657121612556"><a name="p1657121612556"></a><a name="p1657121612556"></a>支持prometheus指标，新增CCE相关自研探测插件</p>
</td>
</tr>
<tr id="row14788592234"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p14295551125412"><a name="p14295551125412"></a><a name="p14295551125412"></a>0.6.3</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p17295155112549"><a name="p17295155112549"></a><a name="p17295155112549"></a>混合集群 v1.13.*|v1.11.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p152959518546"><a name="p152959518546"></a><a name="p152959518546"></a>2019/08/15</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1568911755512"><a name="p1568911755512"></a><a name="p1568911755512"></a>首次上线node-problem-detector插件</p>
</td>
</tr>
</tbody>
</table>

