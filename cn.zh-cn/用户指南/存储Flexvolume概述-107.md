# 存储Flexvolume概述<a name="cce_01_0306"></a>

容器存储是为容器工作负载提供存储的组件，支持多种类型的存储，同一个工作负载（pod\)可以使用任意数量的存储。

云容器引擎CCE的容器存储功能基于Kubernetes存储系统，并深度融合华为云存储服务，完全兼容Kubernetes原生的存储服务，例如EmptyDir、HostPath、Secret、ConfigMap等存储。

**1.13及以下版本**的CCE基于Kubernetes社区Flexvolume容器存储接口（[storage-driver](storage-driver（系统资源插件-必装）.md)）实现了华为云存储服务接入能力，目前该插件已经不是官方建议的存储扩展方式，**在1.15及以上版本的CCE集群中默认安装CSI容器存储插件（[Everest](Everest（系统资源插件-必装）.md)）**，详情参见[存储概述](存储概述-89.md)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   Kubernetes1.13版本之前的CCE集群不支持端到端容器存储扩容功能，PVC容量与存储容量不一致。
>-   在**v1.13及以下版本**的集群中，当存储功能有升级或者BUG修复时，用户无需升级集群或新建集群来升级存储功能，仅需安装或升级storage-driver插件。

## 约束与限制<a name="section3993231122718"></a>

-   在CCE所创的集群中，Kubernetes v1.15.11版本是Flexvolume插件（storage-driver）被CSI插件（[Everest](Everest（系统资源插件-必装）.md)）兼容接管的过渡版本，v1.17及之后版本的集群中将彻底去除对Flexvolume插件（[storage-driver](storage-driver（系统资源插件-必装）.md)）的支持，请您将Flexvolume插件的使用切换到CSI插件上。CSI和Flexvolume能力对比请参见[CSI和Flexvolume存储插件的区别](#section86752053123513)。
-   CSI插件（[Everest](Everest（系统资源插件-必装）.md)）兼容接管Flexvolume插件（storage-driver）后，原有功能保持不变，但请注意不要新建Flexvolume插件（storage-driver）的存储，否则将导致部分存储功能异常。

## CSI和Flexvolume存储插件的区别<a name="section86752053123513"></a>

**表 1**  CSI与Flexvolume

<a name="zh-cn_topic_0107283763_table9704165418310"></a>
<table><thead align="left"><tr id="zh-cn_topic_0107283763_row1757135413114"><th class="cellrowborder" valign="top" width="16.520000000000003%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0107283763_p177571954173119"><a name="zh-cn_topic_0107283763_p177571954173119"></a><a name="zh-cn_topic_0107283763_p177571954173119"></a>Kubernetes插件方案</p>
</th>
<th class="cellrowborder" valign="top" width="13.450000000000001%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0107283763_p105501460334"><a name="zh-cn_topic_0107283763_p105501460334"></a><a name="zh-cn_topic_0107283763_p105501460334"></a>CCE插件名称</p>
</th>
<th class="cellrowborder" valign="top" width="38.57%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0107283763_p575715443110"><a name="zh-cn_topic_0107283763_p575715443110"></a><a name="zh-cn_topic_0107283763_p575715443110"></a>插件特性</p>
</th>
<th class="cellrowborder" valign="top" width="31.46%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0107283763_p97571054183119"><a name="zh-cn_topic_0107283763_p97571054183119"></a><a name="zh-cn_topic_0107283763_p97571054183119"></a>使用推荐</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0107283763_row5119842113215"><td class="cellrowborder" valign="top" width="16.520000000000003%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0107283763_p97574546316"><a name="zh-cn_topic_0107283763_p97574546316"></a><a name="zh-cn_topic_0107283763_p97574546316"></a><span>CSI</span></p>
</td>
<td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0107283763_p0550106143311"><a name="zh-cn_topic_0107283763_p0550106143311"></a><a name="zh-cn_topic_0107283763_p0550106143311"></a>Everest</p>
</td>
<td class="cellrowborder" valign="top" width="38.57%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0107283763_p137578549318"><a name="zh-cn_topic_0107283763_p137578549318"></a><a name="zh-cn_topic_0107283763_p137578549318"></a><span>CSI</span><span>插件是</span><span>kubernetes</span><span>社区推荐的存储插件机制。</span><span>CCE</span><span>发布的</span><span>kubernetes1.15</span><span>版本及以上版本默认安装</span><span>CSI</span><span>插件</span><span>Everest</span><span>，并用于对接块存储、文件存储、对象存储、极速文件存储等</span><span>Iaas</span><span>存储服务。</span></p>
<p id="zh-cn_topic_0107283763_p11757754123115"><a name="zh-cn_topic_0107283763_p11757754123115"></a><a name="zh-cn_topic_0107283763_p11757754123115"></a><span>Everest</span><span>插件包含两部分：</span></p>
<a name="zh-cn_topic_0107283763_ul6619114334611"></a><a name="zh-cn_topic_0107283763_ul6619114334611"></a><ul id="zh-cn_topic_0107283763_ul6619114334611"><li><span>Everest-</span><span>csi</span><span>-controller</span><span>：提供存储卷的创建、删除、扩容、云盘快照等功能；</span></li><li><span>Everest-</span><span>csi</span><span>-driver</span><span>：提供存储卷在</span><span>node</span><span>上的挂载、卸载、格式化等功能。</span></li></ul>
<p id="zh-cn_topic_0107283763_p1387091118582"><a name="zh-cn_topic_0107283763_p1387091118582"></a><a name="zh-cn_topic_0107283763_p1387091118582"></a>详情请参见<a href="Everest（系统资源插件-必装）.md">Everest</a></p>
</td>
<td class="cellrowborder" valign="top" width="31.46%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0107283763_p516783510588"><a name="zh-cn_topic_0107283763_p516783510588"></a><a name="zh-cn_topic_0107283763_p516783510588"></a>针对<strong id="zh-cn_topic_0107283763_b6889332175813"><a name="zh-cn_topic_0107283763_b6889332175813"></a><a name="zh-cn_topic_0107283763_b6889332175813"></a>1.15及以上</strong>版本的集群，在创建时将默认安装CSI插件（<a href="Everest（系统资源插件-必装）.md">Everest</a>）。CCE会跟随社区持续更新CSI插件的各种能力。</p>
</td>
</tr>
<tr id="zh-cn_topic_0107283763_row4757195473110"><td class="cellrowborder" valign="top" width="16.520000000000003%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0107283763_p1175710548316"><a name="zh-cn_topic_0107283763_p1175710548316"></a><a name="zh-cn_topic_0107283763_p1175710548316"></a><span>Flexvolume</span></p>
</td>
<td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0107283763_p45508612335"><a name="zh-cn_topic_0107283763_p45508612335"></a><a name="zh-cn_topic_0107283763_p45508612335"></a>storage-driver</p>
</td>
<td class="cellrowborder" valign="top" width="38.57%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0107283763_p19757145483115"><a name="zh-cn_topic_0107283763_p19757145483115"></a><a name="zh-cn_topic_0107283763_p19757145483115"></a><span>Flexvolume</span><span>插件是</span><span>kubernetes</span><span>社区早期实现的存储卷插件机制。自</span><span>CCE</span><span>上线伊始，提供的就是</span><span>Flexvolume</span><span>数据卷服务。</span><span>CCE</span><span>发布的</span><span>kubernetes</span><span> 1.13</span><span>及以下版本安装的插件是“</span><span>storage-driver</span><span>”，并用于对接块存储、文件存储、对象存储、极速文件存储等</span><span>Iaas</span><span>存储服务。</span></p>
<p id="zh-cn_topic_0107283763_p16757654153113"><a name="zh-cn_topic_0107283763_p16757654153113"></a><a name="zh-cn_topic_0107283763_p16757654153113"></a>详情请参见<a href="storage-driver（系统资源插件-必装）.md">storage-driver</a></p>
</td>
<td class="cellrowborder" valign="top" width="31.46%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0107283763_p18569134265811"><a name="zh-cn_topic_0107283763_p18569134265811"></a><a name="zh-cn_topic_0107283763_p18569134265811"></a>针对已经创建的<strong id="zh-cn_topic_0107283763_b149171340145819"><a name="zh-cn_topic_0107283763_b149171340145819"></a><a name="zh-cn_topic_0107283763_b149171340145819"></a>1.13及以下</strong>版本的集群，仍然使用已经安装的Flexvolume存储插件（<a href="storage-driver（系统资源插件-必装）.md">storage-driver</a>），CCE已停止更新该插件，您可以<a href="重置升级-滚动升级（1-13及以下版本）.md">升级集群版本</a>。</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   不支持CSI和Flexvolume插件在同一个集群中使用。
>-   不支持将v1.13及以下版本集群的Flexvolume插件转变到CSI插件，v1.13版本的集群可以通过升级集群版本切换为CSI插件，详情请参见[大版本升级说明](集群升级概述-10.md#section16738338445)。

## 插件使用推荐<a name="section8895112716599"></a>

-   使用CSI插件（[Everest](Everest（系统资源插件-必装）.md)）要求Kubernetes版本需为**1.15及以上**，v1.15及以上版本的集群在创建时将默认安装本插件，v1.13及以下版本集群创建时默认安装Flexvolume插件（[storage-driver](storage-driver（系统资源插件-必装）.md)）。
-   集群版本由v1.13升级到v1.15后，v1.13版本集群中的Flexvolume容器存储插件（[storage-driver](storage-driver（系统资源插件-必装）.md)）能力将由v1.15的CSI插件（Everest，插件版本v1.1.6及以上）接管，接管后原有功能保持不变。
-   插件版本为1.2.0的Everest优化了使用OBS存储时的**密钥认证功能**，低于该版本的Everest插件在升级完成后，需要重启集群中使用OBS存储的全部工作负载，否则工作负载使用存储的能力将受影响！

## 如何判断集群的存储插件模式<a name="section366174392017"></a>

1.  登录CCE控制台。
2.  在控制台左侧栏目树中，单击“插件管理“。
3.  在右侧的插件管理列表中，单击“插件实例“页签。
4.  在插件实例页面下，选择右上方的集群后，可以看到创建该集群时默认安装的存储插件。如下图：

    **图 1**  确认存储插件<a name="fig18171214131016"></a>  
    ![](figures/确认存储插件.png "确认存储插件")


