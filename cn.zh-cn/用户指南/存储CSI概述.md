# 存储CSI概述<a name="cce_01_0042"></a>

容器存储是为容器工作负载提供存储的组件，支持多种类型的存储，同一个工作负载（pod\)可以使用任意数量的存储。

云容器引擎CCE的容器存储功能基于Kubernetes存储系统，并深度融合华为云存储服务，完全兼容Kubernetes原生的存储服务，例如EmptyDir、HostPath、Secret、ConfigMap等存储。CCE基于Kubernetes社区容器存储接口（CSI，即Container Storage Interface）实现了华为云存储服务接入能力，旨在能为容器编排引擎和存储系统间建立一套标准的存储调用接口，通过该接口能为容器编排引擎提供存储服务。

**在CCE集群中的CSI容器存储插件名为[Everest](Everest（系统资源插件-必装）.md)**，集群版本为Kubernetes 1.15及以上时默认安装该插件。

本文介绍CCE容器存储CSI概览、CSI版本说明、CSI和Flexvolume存储插件的区别等。

## CCE容器存储概览<a name="section326216625217"></a>

CCE支持工作负载Pod绑定[存储卷类型说明](存储基础知识.md#section16559121287)中的多种本地磁盘存储和云存储，每种存储卷的主要特点及应用场景如下表：

**图 1**  CCE支持的存储类型<a name="fig128444399616"></a>  
![](figures/CCE支持的存储类型.png "CCE支持的存储类型")

**表 1**  网络存储对比

<a name="table1381911241505"></a>
<table><thead align="left"><tr id="row681972410017"><th class="cellrowborder" valign="top" width="12.2%" id="mcps1.2.6.1.1"><p id="p1182114718218"><a name="p1182114718218"></a><a name="p1182114718218"></a>对比维度</p>
</th>
<th class="cellrowborder" valign="top" width="21.95%" id="mcps1.2.6.1.2"><p id="p8821971729"><a name="p8821971729"></a><a name="p8821971729"></a>云硬盘EVS</p>
</th>
<th class="cellrowborder" valign="top" width="21.95%" id="mcps1.2.6.1.3"><p id="p68211275218"><a name="p68211275218"></a><a name="p68211275218"></a>弹性文件服务SFS</p>
</th>
<th class="cellrowborder" valign="top" width="21.95%" id="mcps1.2.6.1.4"><p id="p882187327"><a name="p882187327"></a><a name="p882187327"></a>对象存储OBS</p>
</th>
<th class="cellrowborder" valign="top" width="21.95%" id="mcps1.2.6.1.5"><p id="p18211714216"><a name="p18211714216"></a><a name="p18211714216"></a>极速文件存储SFS Turbo</p>
</th>
</tr>
</thead>
<tbody><tr id="row753513520417"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p853513528414"><a name="p853513528414"></a><a name="p853513528414"></a>概念</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p105361652941"><a name="p105361652941"></a><a name="p105361652941"></a>云硬盘（Elastic Volume Service）可以为云服务器提供高可靠、高性能、规格丰富并且可弹性扩展的块存储服务，可满足不同场景的业务需求，适用于分布式文件系统、开发测试、数据仓库以及高性能计算等场景。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p15606133319315"><a name="p15606133319315"></a><a name="p15606133319315"></a>SFS为用户提供一个完全托管的共享文件存储，能够弹性伸缩至PB规模，具备高可用性和持久性，为海量数据、高带宽型应用提供有力支持。适用于多种应用场景，包括HPC、媒体处理、文件共享、内容管理和Web服务等。</p>
<p id="p1560663343117"><a name="p1560663343117"></a><a name="p1560663343117"></a></p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p107261619142811"><a name="p107261619142811"></a><a name="p107261619142811"></a>对象存储服务（Object Storage Service，OBS）提供海量、安全、高可靠、低成本的数据存储能力，可供用户存储任意类型和大小的数据。适合企业备份/归档、视频点播、视频监控等多种数据存储场景。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p91731911183120"><a name="p91731911183120"></a><a name="p91731911183120"></a>SFS Turbo为用户提供一个完全托管的共享文件存储，能够弹性伸缩至320TB规模，具备高可用性和持久性，为海量的小文件、低延迟高IOPS型应用提供有力支持。适用于多种应用场景，包括高性能网站、日志存储、压缩解压、DevOps、企业办公、容器应用等。</p>
</td>
</tr>
<tr id="row107852010714"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p1178122018714"><a name="p1178122018714"></a><a name="p1178122018714"></a>存储数据的逻辑</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p187812201879"><a name="p187812201879"></a><a name="p187812201879"></a>存放的是二进制数据，无法直接存放文件，如果需要存放文件，需要先格式化文件系统后使用。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p77852011712"><a name="p77852011712"></a><a name="p77852011712"></a>存放的是文件，会以文件和文件夹的层次结构来整理和呈现数据。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p178420475"><a name="p178420475"></a><a name="p178420475"></a>存放的是对象，可以直接存放文件，文件会自动产生对应的系统元数据，用户也可以自定义文件的元数据。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p107819201277"><a name="p107819201277"></a><a name="p107819201277"></a>存放的是文件，会以文件和文件夹的层次结构来整理和呈现数据。</p>
</td>
</tr>
<tr id="row285818816813"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p15858186817"><a name="p15858186817"></a><a name="p15858186817"></a>访问方式</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p085813810814"><a name="p085813810814"></a><a name="p085813810814"></a>只能在ECS/BMS中挂载使用，不能被操作系统应用直接访问，需要格式化成文件系统进行访问。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p98591186815"><a name="p98591186815"></a><a name="p98591186815"></a>在ECS/BMS中通过网络协议挂载使用。需要指定网络地址进行访问，也可以将网络地址映射为本地目录后进行访问。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p16859118685"><a name="p16859118685"></a><a name="p16859118685"></a>可以通过互联网或专线访问。需要指定桶地址进行访问，使用的是HTTP和HTTPS等传输协议。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p2859881785"><a name="p2859881785"></a><a name="p2859881785"></a>提供标准的文件访问协议NFS（仅支持NFSv3），用户可以将现有应用和工具与SFS Turbo无缝集成。</p>
</td>
</tr>
<tr id="row1762415820302"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p11821177928"><a name="p11821177928"></a><a name="p11821177928"></a>静态数据卷</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p19821127024"><a name="p19821127024"></a><a name="p19821127024"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p1782117710220"><a name="p1782117710220"></a><a name="p1782117710220"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p4821871721"><a name="p4821871721"></a><a name="p4821871721"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p158211574216"><a name="p158211574216"></a><a name="p158211574216"></a>支持</p>
</td>
</tr>
<tr id="row118192240012"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p16821117228"><a name="p16821117228"></a><a name="p16821117228"></a>动态数据卷</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p10821371929"><a name="p10821371929"></a><a name="p10821371929"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p16821871824"><a name="p16821871824"></a><a name="p16821871824"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p68213714215"><a name="p68213714215"></a><a name="p68213714215"></a>支持</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p1282118711218"><a name="p1282118711218"></a><a name="p1282118711218"></a>不支持</p>
</td>
</tr>
<tr id="row178196241102"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p2821178210"><a name="p2821178210"></a><a name="p2821178210"></a>主要特点</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p58211971024"><a name="p58211971024"></a><a name="p58211971024"></a>非共享存储，每个云盘只能在单个节点挂载。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p128211976217"><a name="p128211976217"></a><a name="p128211976217"></a>共享存储，可提供高性能、高吞吐存储服务。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p128210717211"><a name="p128210717211"></a><a name="p128210717211"></a>共享存储，用户态文件系统。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p8821471622"><a name="p8821471622"></a><a name="p8821471622"></a>高性能、高带宽、共享存储。</p>
</td>
</tr>
<tr id="row20738549306"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p1273954916010"><a name="p1273954916010"></a><a name="p1273954916010"></a>应用场景</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p17367132813016"><a name="p17367132813016"></a><a name="p17367132813016"></a>HPC高性能计算、企业核心集群应用、企业应用系统和开发测试等。</p>
<div class="note" id="note1547152375919"><a name="note1547152375919"></a><a name="note1547152375919"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p947172385920"><a name="p947172385920"></a><a name="p947172385920"></a>高性能计算：主要是高速率、高IOPS的需求，用于作为高性能存储，比如工业设计、能源勘探等。</p>
</div></div>
<p id="p13670281018"><a name="p13670281018"></a><a name="p13670281018"></a>更多信息，请参见<a href="云硬盘存储卷概述.md">云硬盘存储卷概述</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p12791013514"><a name="p12791013514"></a><a name="p12791013514"></a>HPC高性能计算、媒体处理、内容管理和Web服务、大数据和分析应用程序等。</p>
<div class="note" id="note1482333019011"><a name="note1482333019011"></a><a name="note1482333019011"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p17823530504"><a name="p17823530504"></a><a name="p17823530504"></a>高性能计算：主要是高带宽的需求，用于共享文件存储，比如基因测序、图片渲染等。</p>
</div></div>
<p id="p436819282009"><a name="p436819282009"></a><a name="p436819282009"></a>更多信息，请参见<a href="文件存储卷概述.md">文件存储卷概述</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p6507161018"><a name="p6507161018"></a><a name="p6507161018"></a>大数据分析、静态网站托管、在线视频点播、基因测序、智能视频监控、备份归档、企业云盘（网盘）等。</p>
<p id="p736814281704"><a name="p736814281704"></a><a name="p736814281704"></a>更多信息，请参见<a href="对象存储卷概述.md">对象存储卷概述</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p11807135612"><a name="p11807135612"></a><a name="p11807135612"></a>高性能网站、日志存储、DevOps、企业办公等。</p>
<p id="p617733317117"><a name="p617733317117"></a><a name="p617733317117"></a>更多信息，请参见<a href="极速文件存储卷概述.md">极速文件存储卷概述</a>。</p>
</td>
</tr>
<tr id="row795117183197"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p295218186195"><a name="p295218186195"></a><a name="p295218186195"></a>容量</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p19521418111910"><a name="p19521418111910"></a><a name="p19521418111910"></a>TB级别</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p095211871914"><a name="p095211871914"></a><a name="p095211871914"></a>PB级别</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p179521318161916"><a name="p179521318161916"></a><a name="p179521318161916"></a>EB级别</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p1795201812198"><a name="p1795201812198"></a><a name="p1795201812198"></a>TB级别</p>
</td>
</tr>
<tr id="row2051631112018"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p9516161102020"><a name="p9516161102020"></a><a name="p9516161102020"></a>时延</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p07991430122212"><a name="p07991430122212"></a><a name="p07991430122212"></a>1~2ms</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p97991230122210"><a name="p97991230122210"></a><a name="p97991230122210"></a>3~10ms</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p16799103015229"><a name="p16799103015229"></a><a name="p16799103015229"></a>10ms</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p1551631182013"><a name="p1551631182013"></a><a name="p1551631182013"></a>1~2ms</p>
</td>
</tr>
<tr id="row81345119220"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p47361048233"><a name="p47361048233"></a><a name="p47361048233"></a>IOPS/TPS</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p14736184122317"><a name="p14736184122317"></a><a name="p14736184122317"></a>单盘 33K</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p1373618414230"><a name="p1373618414230"></a><a name="p1373618414230"></a>单文件系统 10K</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p177368492319"><a name="p177368492319"></a><a name="p177368492319"></a>千万级</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p13134181152219"><a name="p13134181152219"></a><a name="p13134181152219"></a>100K</p>
</td>
</tr>
<tr id="row16110165119224"><td class="cellrowborder" valign="top" width="12.2%" headers="mcps1.2.6.1.1 "><p id="p207361748233"><a name="p207361748233"></a><a name="p207361748233"></a>带宽</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.2 "><p id="p3736124102318"><a name="p3736124102318"></a><a name="p3736124102318"></a>MB/s级别</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.3 "><p id="p97361041234"><a name="p97361041234"></a><a name="p97361041234"></a>GB/s级别</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.4 "><p id="p7736114112319"><a name="p7736114112319"></a><a name="p7736114112319"></a>TB/s级别</p>
</td>
<td class="cellrowborder" valign="top" width="21.95%" headers="mcps1.2.6.1.5 "><p id="p71101151202212"><a name="p71101151202212"></a><a name="p71101151202212"></a>GB/s级别</p>
</td>
</tr>
</tbody>
</table>

## 插件使用推荐<a name="section059455612532"></a>

-   使用CSI插件（[Everest](Everest（系统资源插件-必装）.md)）要求Kubernetes版本需为**1.15及以上**，v1.15及以上版本的集群在创建时将默认安装本插件，v1.13及以下版本集群创建时默认安装Flexvolume插件（[storage-driver](storage-driver（系统资源插件-必装）.md)）。
-   集群版本由v1.13升级到v1.15后，v1.13版本集群中的Flexvolume容器存储插件（[storage-driver](storage-driver（系统资源插件-必装）.md)）能力将由v1.15的CSI插件（Everest，插件版本v1.1.6及以上）接管，接管后原有功能保持不变。
-   插件版本为1.2.0的Everest优化了使用OBS存储时的**密钥认证功能**，低于该版本的Everest插件在升级完成后，需要重启集群中使用OBS存储的全部工作负载，否则工作负载使用存储的能力将受影响！

## CSI插件安装与升级<a name="section04121133018"></a>

关于CSI存储插件的安装与升级，请参见[Everest](Everest（系统资源插件-必装）.md)。

## CSI和Flexvolume存储插件的区别<a name="section1690993510317"></a>

**表 2**  CSI与Flexvolume

<a name="table9704165418310"></a>
<table><thead align="left"><tr id="row1757135413114"><th class="cellrowborder" valign="top" width="16.520000000000003%" id="mcps1.2.5.1.1"><p id="p177571954173119"><a name="p177571954173119"></a><a name="p177571954173119"></a>Kubernetes插件方案</p>
</th>
<th class="cellrowborder" valign="top" width="13.450000000000001%" id="mcps1.2.5.1.2"><p id="p105501460334"><a name="p105501460334"></a><a name="p105501460334"></a>CCE插件名称</p>
</th>
<th class="cellrowborder" valign="top" width="38.57%" id="mcps1.2.5.1.3"><p id="p575715443110"><a name="p575715443110"></a><a name="p575715443110"></a>插件特性</p>
</th>
<th class="cellrowborder" valign="top" width="31.46%" id="mcps1.2.5.1.4"><p id="p97571054183119"><a name="p97571054183119"></a><a name="p97571054183119"></a>使用推荐</p>
</th>
</tr>
</thead>
<tbody><tr id="row5119842113215"><td class="cellrowborder" valign="top" width="16.520000000000003%" headers="mcps1.2.5.1.1 "><p id="p97574546316"><a name="p97574546316"></a><a name="p97574546316"></a><span>CSI</span></p>
</td>
<td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p0550106143311"><a name="p0550106143311"></a><a name="p0550106143311"></a>Everest</p>
</td>
<td class="cellrowborder" valign="top" width="38.57%" headers="mcps1.2.5.1.3 "><p id="p137578549318"><a name="p137578549318"></a><a name="p137578549318"></a><span>CSI</span><span>插件是</span><span>kubernetes</span><span>社区推荐的存储插件机制。</span><span>CCE</span><span>发布的</span><span>kubernetes1.15</span><span>版本及以上版本默认安装</span><span>CSI</span><span>插件</span><span>Everest</span><span>，并用于对接华为云块存储、文件存储、对象存储、极速文件存储等</span><span>Iaas</span><span>存储服务。</span></p>
<p id="p11757754123115"><a name="p11757754123115"></a><a name="p11757754123115"></a><span>Everest</span><span>插件包含两部分：</span></p>
<a name="ul6619114334611"></a><a name="ul6619114334611"></a><ul id="ul6619114334611"><li><span>Everest-</span><span>csi</span><span>-controller</span><span>：提供存储卷的创建、删除、扩容、云盘快照等功能；</span></li><li><span>Everest-</span><span>csi</span><span>-driver</span><span>：提供存储卷在</span><span>node</span><span>上的挂载、卸载、格式化等功能。</span></li></ul>
<p id="p1387091118582"><a name="p1387091118582"></a><a name="p1387091118582"></a>详情请参见<a href="Everest（系统资源插件-必装）.md">Everest</a></p>
</td>
<td class="cellrowborder" valign="top" width="31.46%" headers="mcps1.2.5.1.4 "><p id="p516783510588"><a name="p516783510588"></a><a name="p516783510588"></a>针对<strong id="b6889332175813"><a name="b6889332175813"></a><a name="b6889332175813"></a>1.15及以上</strong>版本的集群，在创建时将默认安装CSI插件（<a href="Everest（系统资源插件-必装）.md">Everest</a>）。CCE会跟随社区持续更新CSI插件的各种能力。</p>
</td>
</tr>
<tr id="row4757195473110"><td class="cellrowborder" valign="top" width="16.520000000000003%" headers="mcps1.2.5.1.1 "><p id="p1175710548316"><a name="p1175710548316"></a><a name="p1175710548316"></a><span>Flexvolume</span></p>
</td>
<td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p45508612335"><a name="p45508612335"></a><a name="p45508612335"></a>storage-driver</p>
</td>
<td class="cellrowborder" valign="top" width="38.57%" headers="mcps1.2.5.1.3 "><p id="p19757145483115"><a name="p19757145483115"></a><a name="p19757145483115"></a><span>Flexvolume</span><span>插件是</span><span>kubernetes</span><span>社区早期实现的存储卷插件机制。自</span><span>CCE</span><span>上线伊始，提供的就是</span><span>Flexvolume</span><span>数据卷服务。</span><span>CCE</span><span>发布的</span><span>kubernetes</span><span> 1.13</span><span>及以下版本安装的插件是“</span><span>storage-driver</span><span>”，并用于对接华为云块存储、文件存储、对象存储、极速文件存储等</span><span>Iaas</span><span>存储服务。</span></p>
<p id="p16757654153113"><a name="p16757654153113"></a><a name="p16757654153113"></a>详情请参见<a href="storage-driver（系统资源插件-必装）.md">storage-driver</a></p>
</td>
<td class="cellrowborder" valign="top" width="31.46%" headers="mcps1.2.5.1.4 "><p id="p18569134265811"><a name="p18569134265811"></a><a name="p18569134265811"></a>针对已经创建的<strong id="b149171340145819"><a name="b149171340145819"></a><a name="b149171340145819"></a>1.13及以下</strong>版本的集群，仍然使用已经安装的Flexvolume存储插件（<a href="storage-driver（系统资源插件-必装）.md">storage-driver</a>），CCE已停止更新该插件，您可以<a href="升级集群（1-13及以下版本）.md">升级集群版本</a>。</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   不支持CSI和Flexvolume插件在同一个集群中使用。
>-   不支持将v1.13及以下版本集群的Flexvolume插件转变到CSI插件，v1.13版本的集群可以通过升级集群版本切换为CSI插件，详情请参见[大版本升级说明](集群升级概述.md#section16738338445)。

## 如何判断集群的存储插件模式<a name="section8832124618543"></a>

1.  登录CCE控制台。
2.  在控制台左侧栏目树中，单击“插件管理“。
3.  在右侧的插件管理列表中，单击“插件实例“页签。
4.  在插件实例页面下，选择右上方的集群后，可以看到创建该集群时默认安装的存储插件，如下图：

    **图 2**  确认存储插件<a name="fig18171214131016"></a>  
    ![](figures/确认存储插件.png "确认存储插件")


