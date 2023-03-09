# everest（系统资源插件，必装）<a name="cce_10_0066"></a>

## 插件简介<a name="section25311744154917"></a>

Everest是一个云原生容器存储系统，基于CSI（即Container Storage Interface）为Kubernetes v1.15.6及以上版本集群对接云存储服务的能力。

**该插件为系统资源插件，kubernetes 1.15及以上版本的集群在创建时默认安装。**

## 约束与限制<a name="section202191122814"></a>

-   集群版本由v1.13升级到v1.15后，v1.13版本集群中的Flexvolume容器存储插件（[storage-driver](storage-driver（系统资源插件-已废弃）.md)）能力将由v1.15的CSI插件（Everest，插件版本v1.1.6及以上）接管，接管后原有功能保持不变。
-   插件版本为1.2.0的Everest优化了使用OBS存储时的**密钥认证功能**，低于该版本的Everest插件在升级完成后，需要重启集群中使用OBS存储的全部工作负载，否则工作负载使用存储的能力将受影响！
-   **v1.15及以上版本**的集群默认安装本插件，v1.13及以下版本集群创建时默认安装[storage-driver](storage-driver（系统资源插件-已废弃）.md)插件。

## 安装插件<a name="section168341157155317"></a>

本插件为系统默认安装，若因特殊情况卸载后，可参照如下步骤重新安装。

1.  登录CCE控制台，单击集群名称进入集群，单击左侧导航栏的“插件管理“，在右侧找到**everest**，单击“安装“。
2.  该插件可配置“单实例“、“高可用“或自定义规格。

    Everest插件包含以下容器，您可根据需求自定义调整规格：

    -   everest-csi-controller：由Deployment形式部署，Pod中含有一个everest-csi-controller容器，此容器负责存储卷的创建、删除、快照、扩容、attach/detach等功能。若集群版本大于等于1.19，everest-csi-driver组件的Pod还会默认带有一个everest-localvolume-manager容器，此容器负责管理节点上的lvm存储池及localpv的创建。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >选择自定义规格时，everest-csi-controller内存配置推荐如下。
        >-   Pod和PVC的数量均小于2000时，everest-csi-controller的内存上限推荐配置为600Mi。
        >-   Pod和PVC的数量均小于5000时，everest-csi-controller的内存上限推荐配置为1Gi。

    -   everest-csi-driver：由DaemonSet形式部署，Pod中含有一个基本容器everest-csi-driver容器，负责PV的挂载、卸载、文件系统resize等功能。若集群所在区域支持node-attacher，everest-csi-driver组件的Pod还会带有一个everest-node-attacher的容器，此容器负责分布式attach EVS，该配置项在部分Region开放。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >选择自定义规格时，everest-csi-driver内存限制推荐配置不低于300Mi。若该值太小可能导致插件实例容器启动异常，从而导致插件不可用的情况。


3.  参数配置。

    everest 1.2.26以上版本针对大批量挂EVS卷的性能做了优化，提供了如下3个参数供用户配置。

    -   csi\_attacher\_worker\_threads：everest插件中同时处理挂EVS卷的worker数，默认值为“60”。
    -   csi\_attacher\_detach\_worker\_threads：everest插件中同时处理卸载EVS卷的worker数，默认值均为“60”。
    -   volume\_attaching\_flow\_ctrl：everest插件在1分钟内可以挂载EVS卷的最大数量，此参数的默认值“0”表示everest插件不做挂卷限制，此时挂卷性能由底层存储资源决定。

    上述三个参数由于存在关联性且与集群所在局点的底层存储资源限制有关，当您对大批量挂卷的性能有要求（大于500EVS卷/分钟）时，请联系客服，在指导下进行配置，否则可能会因为参数配置不合理导致出现everest插件运行不正常的情况。

4.  单击“安装“。

## 版本记录<a name="section183121449435"></a>

**表 1**  CCE插件版本记录

<a name="table88489551792"></a>
<table><thead align="left"><tr id="row139251455994"><th class="cellrowborder" valign="top" width="38.13183564883239%" id="mcps1.2.3.1.1"><p id="p1969103105514"><a name="p1969103105514"></a><a name="p1969103105514"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="61.8681643511676%" id="mcps1.2.3.1.2"><p id="p396917314551"><a name="p396917314551"></a><a name="p396917314551"></a>支持的集群版本</p>
</th>
</tr>
</thead>
<tbody><tr id="row430645515010"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p1628014016115"><a name="p1628014016115"></a><a name="p1628014016115"></a>2.1.13</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p628019013117"><a name="p628019013117"></a><a name="p628019013117"></a>/v1.(19|21|23|25).*/</p>
</td>
</tr>
<tr id="row2172125215010"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p1628012014115"><a name="p1628012014115"></a><a name="p1628012014115"></a>2.1.9</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p162806011115"><a name="p162806011115"></a><a name="p162806011115"></a>/v1.(19|21|23|25).*/</p>
</td>
</tr>
<tr id="row7437827135415"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p167881228145419"><a name="p167881228145419"></a><a name="p167881228145419"></a>2.0.9</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p378852835420"><a name="p378852835420"></a><a name="p378852835420"></a>/v1.(19|21|23).*/</p>
</td>
</tr>
<tr id="row639517571151"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p173961657121518"><a name="p173961657121518"></a><a name="p173961657121518"></a>1.3.28</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p128006523165"><a name="p128006523165"></a><a name="p128006523165"></a>/v1.(19|21|23).*/</p>
</td>
</tr>
<tr id="row8757710175517"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p14518171518235"><a name="p14518171518235"></a><a name="p14518171518235"></a>1.3.22</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p16547175972612"><a name="p16547175972612"></a><a name="p16547175972612"></a>/v1.(19|21|23).*/</p>
</td>
</tr>
<tr id="row1292974112718"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p58582050172713"><a name="p58582050172713"></a><a name="p58582050172713"></a>1.3.20</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p5858115052714"><a name="p5858115052714"></a><a name="p5858115052714"></a>/v1.(19|21|23).*/</p>
</td>
</tr>
<tr id="row3926175518912"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p175181515192310"><a name="p175181515192310"></a><a name="p175181515192310"></a>1.3.17</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p151812156236"><a name="p151812156236"></a><a name="p151812156236"></a>/v1.(19|21|23).*/</p>
</td>
</tr>
<tr id="row15926105520911"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p25189151232"><a name="p25189151232"></a><a name="p25189151232"></a>1.3.8</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p13675151302820"><a name="p13675151302820"></a><a name="p13675151302820"></a>/v1.23.*/</p>
</td>
</tr>
<tr id="row2035714120472"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p11518151542319"><a name="p11518151542319"></a><a name="p11518151542319"></a>1.3.6</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p5920112320288"><a name="p5920112320288"></a><a name="p5920112320288"></a>/v1.23.*/</p>
</td>
</tr>
<tr id="row58816436322"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p1951881522318"><a name="p1951881522318"></a><a name="p1951881522318"></a>1.2.55</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p142694583710"><a name="p142694583710"></a><a name="p142694583710"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row75239215371"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p552362110378"><a name="p552362110378"></a><a name="p552362110378"></a><span>1.2.53</span></p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p4432102283720"><a name="p4432102283720"></a><a name="p4432102283720"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row440924363210"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p185189157234"><a name="p185189157234"></a><a name="p185189157234"></a>1.2.51</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p17161114619371"><a name="p17161114619371"></a><a name="p17161114619371"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row126511443153215"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p105199157231"><a name="p105199157231"></a><a name="p105199157231"></a>1.2.44</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p19801226153819"><a name="p19801226153819"></a><a name="p19801226153819"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row396884320323"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p3519151512312"><a name="p3519151512312"></a><a name="p3519151512312"></a>1.2.42</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p988204683816"><a name="p988204683816"></a><a name="p988204683816"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row6555510228"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p051921552312"><a name="p051921552312"></a><a name="p051921552312"></a>1.2.30</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p5360141123914"><a name="p5360141123914"></a><a name="p5360141123914"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row1610155582219"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p351918158233"><a name="p351918158233"></a><a name="p351918158233"></a>1.2.28</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p817811179395"><a name="p817811179395"></a><a name="p817811179395"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row14491123418397"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p1549223453911"><a name="p1549223453911"></a><a name="p1549223453911"></a><span>1.2.27</span></p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p1933011432399"><a name="p1933011432399"></a><a name="p1933011432399"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row118881558224"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p251912157238"><a name="p251912157238"></a><a name="p251912157238"></a>1.2.13</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p128516475400"><a name="p128516475400"></a><a name="p128516475400"></a>/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row15399384411"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p5399198174116"><a name="p5399198174116"></a><a name="p5399198174116"></a><span>1.2.9</span></p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p19333141913419"><a name="p19333141913419"></a><a name="p19333141913419"></a>/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row33611566226"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p2519161572318"><a name="p2519161572318"></a><a name="p2519161572318"></a>1.2.5</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p63614210413"><a name="p63614210413"></a><a name="p63614210413"></a>/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row15250145714229"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p12520111562318"><a name="p12520111562318"></a><a name="p12520111562318"></a>1.1.12</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p18871181512423"><a name="p18871181512423"></a><a name="p18871181512423"></a>/v1.(15|17).*/</p>
</td>
</tr>
<tr id="row1588816118232"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p152031515231"><a name="p152031515231"></a><a name="p152031515231"></a>1.1.11</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p10263103117420"><a name="p10263103117420"></a><a name="p10263103117420"></a>/v1.(15|17).*/</p>
</td>
</tr>
<tr id="row1025481315238"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p18520715112312"><a name="p18520715112312"></a><a name="p18520715112312"></a>1.1.8</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p3661650134214"><a name="p3661650134214"></a><a name="p3661650134214"></a>/v1.(15|17).*/</p>
</td>
</tr>
<tr id="row1182705994210"><td class="cellrowborder" valign="top" width="38.13183564883239%" headers="mcps1.2.3.1.1 "><p id="p97712711430"><a name="p97712711430"></a><a name="p97712711430"></a>1.1.7</p>
</td>
<td class="cellrowborder" valign="top" width="61.8681643511676%" headers="mcps1.2.3.1.2 "><p id="p18776784315"><a name="p18776784315"></a><a name="p18776784315"></a>/v1.(15|17).*/</p>
</td>
</tr>
</tbody>
</table>

