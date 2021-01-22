# storage-driver（系统资源插件，必装）<a name="cce_01_0127"></a>

-   [插件简介](#section25311744154917)
-   [约束与限制](#section3993231122718)
-   [安装插件](#section776571919194)
-   [升级插件](#section455343310401)
-   [卸载插件](#section20765191931911)
-   [版本记录](#section1945192816714)

## 插件简介<a name="section25311744154917"></a>

storage-driver插件是用于对接华为云块存储、文件存储、对象存储、极速文件存储等Iaas存储服务的FlexVolume驱动。

storage-driver是一款云存储驱动插件，北向遵循标准容器平台存储驱动接口。实现Kubernetes Flex Volume标准接口，提供容器使用华为云EVS块存储、SFS文件存储、OBS 对象存储、SFS Turbo 极速文件存储等华为云IAAS存储的能力。通过安装升级云存储插件可以实现云存储功能的快速安装和更新升级。

**该插件为系统资源插件，kubernetes 1.13及以下版本的集群在创建时默认安装。**

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   v1.15.11-r1是Flexvolume fuxi（即storage-driver）和CSI（即[Everest](Everest（系统资源插件-必装）.md)插件）兼容接管的过渡版本，在v1.17集群中已经去除了对Flexvolume fuxi的支持，请您将Flexvolume fuxi的使用切换CSI Everest上。
>-   CSI Everest兼容接管Flexvolume fuxi后，原有功能保持不变，但请注意不要新建fuxi Flexvolume的存储，否则将导致部分存储功能异常。
>-   当存储功能有升级或者BUG修复时，用户无需升级集群或新建集群来升级存储功能，仅需安装或升级storage-driver插件。

## 约束与限制<a name="section3993231122718"></a>

本插件仅支持在**v1.13及以下版本**的集群中安装，v1.15及以上版本集群创建时默认必装[Everest](Everest（系统资源插件-必装）.md)插件。

## 安装插件<a name="section776571919194"></a>

本插件为系统默认安装，若因特殊情况卸载后，可参照如下步骤重新安装。

在云容器引擎CCE中，kubernetes 1.11及以上版本的新建集群，将会默认安装storage-driver插件。

未安装storage-driver插件的集群，可参考如下步骤进行安装：

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件市场“页签下，单击**storage-driver**插件下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  云存储插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。


## 升级插件<a name="section455343310401"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**storage-driver**下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级storage-driver插件时，会替换原先节点上的旧版本的storage-driver插件，安装最新版本的storage-driver插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  云存储插件暂未开放可配置参数，直接单击“升级“即可升级storage-driver插件。

## 卸载插件<a name="section20765191931911"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击**storage-driver**下的“ 卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 版本记录<a name="section1945192816714"></a>

**表 1**  storage-driver版本记录

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
<tbody><tr id="row8606152894117"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p16881172917440"><a name="p16881172917440"></a><a name="p16881172917440"></a>1.0.22</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p18881192915443"><a name="p18881192915443"></a><a name="p18881192915443"></a>混合集群 v1.7.3~v1.13.*</p>
<p id="p19881229144415"><a name="p19881229144415"></a><a name="p19881229144415"></a>鲲鹏集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p19881129114419"><a name="p19881129114419"></a><a name="p19881129114419"></a>2020/04/04</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p14386367469"><a name="p14386367469"></a><a name="p14386367469"></a>加固配置信息、修复鲲鹏节点安装x86 obsfs的问题、支持安装新版obsfs</p>
</td>
</tr>
<tr id="row12566114195411"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p2881162920449"><a name="p2881162920449"></a><a name="p2881162920449"></a>1.0.21</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p11881122911445"><a name="p11881122911445"></a><a name="p11881122911445"></a>混合集群 v1.7.3~v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p15881122944416"><a name="p15881122944416"></a><a name="p15881122944416"></a>2020/03/12</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p15464113674612"><a name="p15464113674612"></a><a name="p15464113674612"></a>加固配置信息、修复鲲鹏节点安装x86 obsfs的问题、支持安装新版obsfs</p>
</td>
</tr>
<tr id="row97875912317"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p9881132911446"><a name="p9881132911446"></a><a name="p9881132911446"></a>1.0.19</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p3881152934410"><a name="p3881152934410"></a><a name="p3881152934410"></a>混合集群 v1.7.3~v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p8881202914412"><a name="p8881202914412"></a><a name="p8881202914412"></a>2019/11/28</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p5490936184612"><a name="p5490936184612"></a><a name="p5490936184612"></a>为v1.13.10集群提供EVS RWO非共享卷功能, 增加noresvport作为SFS/SFS Turbo的默认挂载参数增加网络可靠性，设置本插件的资源限制</p>
</td>
</tr>
<tr id="row187865919236"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p188826298440"><a name="p188826298440"></a><a name="p188826298440"></a>1.0.18</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p78721727185012"><a name="p78721727185012"></a><a name="p78721727185012"></a>混合集群 v1.7.3~v1.13.*</p>
<p id="p188212292449"><a name="p188212292449"></a><a name="p188212292449"></a>鲲鹏集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p208821829134411"><a name="p208821829134411"></a><a name="p208821829134411"></a>2019/10/17</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p24915362464"><a name="p24915362464"></a><a name="p24915362464"></a>优化加固fuxivol增强getvolumeinfo接口可靠性和异常处理能力、修复kubelet重启后挂载obs桶的未重启容器丢失容器内挂载路径、识别和拒绝挂载分区过或者具有非ext4文件系统的云硬盘</p>
</td>
</tr>
<tr id="row14788592234"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p0882182917448"><a name="p0882182917448"></a><a name="p0882182917448"></a>1.0.16</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p1088219291441"><a name="p1088219291441"></a><a name="p1088219291441"></a>混合集群 v1.7.3~v1.13.*</p>
<p id="p088212974416"><a name="p088212974416"></a><a name="p088212974416"></a>鲲鹏集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p388215290441"><a name="p388215290441"></a><a name="p388215290441"></a>2019/09/27</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p194911736164610"><a name="p194911736164610"></a><a name="p194911736164610"></a>新增支持匹配任意Taints节点、支持obs挂载写入文件有正确的mime.types、支持kubelet metrics，优化加固以减少不必要的插件加载</p>
</td>
</tr>
<tr id="row7533713124512"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p1553451314454"><a name="p1553451314454"></a><a name="p1553451314454"></a>1.0.13</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p208821229154411"><a name="p208821229154411"></a><a name="p208821229154411"></a>混合集群 v1.7.3~v1.13.*</p>
<p id="p1988252994411"><a name="p1988252994411"></a><a name="p1988252994411"></a>鲲鹏集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p053417134451"><a name="p053417134451"></a><a name="p053417134451"></a>2019/07/10</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p0492143664610"><a name="p0492143664610"></a><a name="p0492143664610"></a>增加对基于块存储盘符限制的调度支持,重复unmount efs实例失败问题。</p>
</td>
</tr>
<tr id="row832631715452"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p173264174457"><a name="p173264174457"></a><a name="p173264174457"></a>1.0.11</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p20882229164415"><a name="p20882229164415"></a><a name="p20882229164415"></a>混合集群 v1.7.3~v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p14326151724512"><a name="p14326151724512"></a><a name="p14326151724512"></a>2019/06/10</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p0492153654617"><a name="p0492153654617"></a><a name="p0492153654617"></a>升级插件，适配新的集群版本。</p>
</td>
</tr>
</tbody>
</table>

