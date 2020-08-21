# Everest（系统资源插件，必装）<a name="cce_01_0066"></a>

## 插件简介<a name="section25311744154917"></a>

Everest是一个云原生容器存储系统，基于CSI为Kubernetes v1.15.6及以上版本集群对接华为云云硬盘服务 EVS、对象存储服务 OBS、弹性文件服务 SFS、极速文件存储 SFS Turbo等存储服务的能力。

**该插件为系统资源插件，kubernetes 1.15及以上版本的集群在创建时默认安装。**

>![](public_sys-resources/icon-note.gif) **说明：** 
>v1.13.11-r1升级到v1.15.11-r1集群后，原本v1.13的Flexvolume Fuxi容器存储由v1.15的Everest接管（插件版本v1.1.6及以上），原有功能保持不变。

## 约束与限制<a name="section202191122814"></a>

-   仅支持**v1.15及以上版本**的混合集群安装本插件。
-   v1.13及以下版本集群创建时默认必装[storage-driver](storage-driver（系统资源插件-必装）.md)插件。

## 安装插件<a name="section168341157155317"></a>

本插件为系统默认安装，若因特殊情况卸载后，可参照如下步骤重新安装。

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击“everest“插件下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  该插件可配置“单实例“或“高可用“规格，选择后单击“安装“。

    待插件安装完成后，单击“返回插件管理“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section414918421496"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“everest“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级everest插件时，会替换原先节点上的旧版本的everest插件，安装最新版本的everest插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  该插件可配置“单实例“或“高可用“规格，选择后单击“升级“即可升级“everest“插件。

## 卸载插件<a name="section610455514114"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击“everest“下的“卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  everest版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="11.24%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="29.68%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="18.44%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="40.64%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row7335155311559"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p1333565320554"><a name="p1333565320554"></a><a name="p1333565320554"></a><span id="ph5273185635515"><a name="ph5273185635515"></a><a name="ph5273185635515"></a>1.1.11</span></p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p207694410562"><a name="p207694410562"></a><a name="p207694410562"></a>混合集群 v1.(15|17).*</p>
<p id="p117696411564"><a name="p117696411564"></a><a name="p117696411564"></a>裸金属集群 v1.(15|17).*</p>
<p id="p9769840568"><a name="p9769840568"></a><a name="p9769840568"></a>鲲鹏集群 v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p8335165335516"><a name="p8335165335516"></a><a name="p8335165335516"></a><span id="ph3380310155610"><a name="ph3380310155610"></a><a name="ph3380310155610"></a>2020/08/19</span></p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><a name="ul1466354565"></a><a name="ul1466354565"></a><ul id="ul1466354565"><li>配置安全加固</li><li>支持挂载三方OBS存储</li><li>切换更优性能的EVS查询接口</li><li>默认快照以clone模式创建磁盘</li><li>优化和增强Attach和Detach磁盘状态检测和日志输出</li><li>增加认证过期判断可靠性</li></ul>
</td>
</tr>
<tr id="row97875912317"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p32688619116"><a name="p32688619116"></a><a name="p32688619116"></a>1.1.8</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p1326813661113"><a name="p1326813661113"></a><a name="p1326813661113"></a>混合集群 v1.(15|17).*</p>
<p id="p1126886131114"><a name="p1126886131114"></a><a name="p1126886131114"></a>裸金属集群 v1.(15|17).*</p>
<p id="p1926817661110"><a name="p1926817661110"></a><a name="p1926817661110"></a>鲲鹏集群 v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p17268161112"><a name="p17268161112"></a><a name="p17268161112"></a>2020/07/25</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><a name="ul1126810651115"></a><a name="ul1126810651115"></a><ul id="ul1126810651115"><li>支持k8s v1.17</li><li>v1.13升级到v1.15场景支持接管flexvolume fuxi</li><li>支持鲲鹏集群</li></ul>
</td>
</tr>
<tr id="row187865919236"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p82685618110"><a name="p82685618110"></a><a name="p82685618110"></a>1.1.7</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p1799412815122"><a name="p1799412815122"></a><a name="p1799412815122"></a>混合集群 v1.(15|17).*</p>
<p id="p12995118141212"><a name="p12995118141212"></a><a name="p12995118141212"></a>裸金属集群 v1.(15|17).*</p>
<p id="p149958851219"><a name="p149958851219"></a><a name="p149958851219"></a>鲲鹏集群 v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p1268156101115"><a name="p1268156101115"></a><a name="p1268156101115"></a>2020/07/15</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><a name="ul926856141116"></a><a name="ul926856141116"></a><ul id="ul926856141116"><li>支持k8s v1.17</li><li>v1.13升级到v1.15场景支持接管flexvolume fuxi</li><li>支持鲲鹏集群</li></ul>
</td>
</tr>
<tr id="row14788592234"><td class="cellrowborder" valign="top" width="11.24%" headers="mcps1.2.5.1.1 "><p id="p1726806111117"><a name="p1726806111117"></a><a name="p1726806111117"></a>1.0.8</p>
</td>
<td class="cellrowborder" valign="top" width="29.68%" headers="mcps1.2.5.1.2 "><p id="p122681366114"><a name="p122681366114"></a><a name="p122681366114"></a>混合集群 v1.15.*</p>
<p id="p026815691118"><a name="p026815691118"></a><a name="p026815691118"></a>裸金属集群 v1.15.*</p>
</td>
<td class="cellrowborder" valign="top" width="18.44%" headers="mcps1.2.5.1.3 "><p id="p1226814618110"><a name="p1226814618110"></a><a name="p1226814618110"></a>2020/06/21</p>
</td>
<td class="cellrowborder" valign="top" width="40.64%" headers="mcps1.2.5.1.4 "><a name="ul1426811651119"></a><a name="ul1426811651119"></a><ul id="ul1426811651119"><li>支持Ubuntu 16.04</li><li>配置安全加固</li></ul>
</td>
</tr>
</tbody>
</table>

