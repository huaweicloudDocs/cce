# CCE控制台的权限依赖<a name="cce_10_0190"></a>

CCE对其他云服务有诸多依赖关系，因此在您开启IAM系统策略授权后，在CCE Console控制台的各项功能需要配置相应的服务权限后才能正常查看或使用，详细说明如下：

-   依赖服务的权限配置均基于您已设置了IAM系统策略授权的CCE FullAccess或CCE ReadOnlyAccess策略权限，详细设置方法请参见[集群权限（IAM授权）](集群权限（IAM授权）.md)。
-   1.11.7-r2及以上版本的集群，显示情况依赖于命名空间权限的设置情况，如果没有设置命名空间权限，则无法查看集群下的资源。
    -   如果您设置了全部命名空间的view权限，则可以查看到对应集群的全部命名空间下的资源，但密钥 \( Secret \)除外，密钥 \( Secret \)需要在命名空间权限下设置admin或者edit权限才能查看。
    -   CustomedHPA与HPA策略需要配置命名空间cluster-admin权限下才能生效。
    -   如果您设置的是单一命名空间的view权限，则看到的只能是指定命名空间下的资源。


## 依赖服务的权限设置<a name="section20316111417244"></a>

如果IAM用户需要在CCE Console控制台拥有相应功能的查看或使用权限，请确认已经对该用户所在的用户组设置了CCE Administrator、CCE FullAccess或CCE ReadOnlyAccess策略的集群权限，再按如下[表1](#table99001215575)增加依赖服务的角色或策略。

>![](public_sys-resources/icon-note.gif) **说明：** 
>**企业项目**能够实现企业不同项目间资源的分组和管理，重在资源隔离，而IAM可以实现细粒度授权，因此强烈推荐您使用IAM实现权限管理。
>若您使用企业项目设置子用户权限，会有如下功能限制：
>-   由于存储资源暂不支持企业项目，因此在CCE控制台，企业项目子用户查看非“Default“企业项目下集群的存储资源相关页面，存储页面中各按钮均置灰，且资源不显示。
>-   在CCE控制台，集群监控获取AOM监控的接口暂不支持企业项目，因此企业项目子用户将无法查看监控相关数据。
>-   在CCE控制台，由于创建节点时的密钥对查询接口不支持企业项目，因此企业项目子用户将无法使用“密钥对“登录方式，您可以选择使用“密码“登录方式。
>-   为企业项目设置**CCE FullAccess**权限后 ，需要在IAM控制台界面中再配置**ecs:availabilityZones:list**权限，企业项目子用户创建节点才可以正常显示并创建，否则将提示没有ecs:availabilityZones:list权限。
>CCE支持细粒度的权限设置，但有如下限制说明：
>-   AOM不支持资源级别细粒度：当通过IAM集群资源细粒度设置特定资源操作权限之后，IAM用户在CCE控制台的总览界面查看集群监控时，将显示非细粒度关联集群的监控信息。
>-   在IAM页面设置**CCE FullAccess**或者**CCE ReadOnlyAccess**权限后，需要配置**sfsturbo:\*:\***权限才能使用极速文件存储卷，否则IAM用户在集群下查询极速文件存储卷将失败。

**表 1**  CCE Console中依赖服务的角色或策略

<a name="table99001215575"></a>
<table><thead align="left"><tr id="row16901181518712"><th class="cellrowborder" valign="top" width="21.872187218721873%" id="mcps1.2.4.1.1"><p id="p109011015875"><a name="p109011015875"></a><a name="p109011015875"></a>Console控制台功能</p>
</th>
<th class="cellrowborder" valign="top" width="28.642864286428644%" id="mcps1.2.4.1.2"><p id="p490115151776"><a name="p490115151776"></a><a name="p490115151776"></a>依赖服务</p>
</th>
<th class="cellrowborder" valign="top" width="49.48494849484948%" id="mcps1.2.4.1.3"><p id="p2090161513711"><a name="p2090161513711"></a><a name="p2090161513711"></a>需配置角色/策略</p>
</th>
</tr>
</thead>
<tbody><tr id="row1090114151176"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p69022151975"><a name="p69022151975"></a><a name="p69022151975"></a>总览</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p119021153716"><a name="p119021153716"></a><a name="p119021153716"></a>应用运维管理 AOM</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><a name="ul223369145920"></a><a name="ul223369145920"></a><ul id="ul223369145920"><li>IAM用户设置了CCE Administrator权限后，需要增加AOM&nbsp;FullAccess权限后才能访问总览中的数据图表。</li><li>支持设置了IAM ReadOnlyAccess和CCE FullAccess或CCE ReadOnlyAccess权限的IAM用户直接访问总览中的数据图表。</li></ul>
</td>
</tr>
<tr id="row19902151514719"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p169022151472"><a name="p169022151472"></a><a name="p169022151472"></a>工作负载</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p10902171518718"><a name="p10902171518718"></a><a name="p10902171518718"></a>弹性负载均衡 ELB</p>
<p id="p736818303252"><a name="p736818303252"></a><a name="p736818303252"></a>应用性能管理 APM</p>
<p id="p1780716195243"><a name="p1780716195243"></a><a name="p1780716195243"></a>应用运维管理 AOM</p>
<p id="p14431322102415"><a name="p14431322102415"></a><a name="p14431322102415"></a>NAT网关 NAT</p>
<p id="p2597316122815"><a name="p2597316122815"></a><a name="p2597316122815"></a>对象存储服务 OBS</p>
<p id="p117241658182817"><a name="p117241658182817"></a><a name="p117241658182817"></a>弹性文件服务 SFS</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><p id="p57471617102017"><a name="p57471617102017"></a><a name="p57471617102017"></a>正常创建工作负载时不依赖其他服务的权限。</p>
<a name="ul8113732182016"></a><a name="ul8113732182016"></a><ul id="ul8113732182016"><li>如果需要创建ELB类型的服务，需要设置ELB FullAccess或者ELB Administrator权限，以及VPC Administrator权限。</li><li>如果需要使用Java探针，需要设置AOM&nbsp;FullAccess和APM FullAccess权限。</li><li>如果需要NAT网关类型的服务，需要设置NAT Gateway Administrator权限。</li><li>如果使用对象存储，需要全局设置OBS Administrator权限。<div class="note" id="note1215220141518"><a name="note1215220141518"></a><a name="note1215220141518"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p0153120121518"><a name="p0153120121518"></a><a name="p0153120121518"></a>由于缓存的存在，对用户、用户组以及企业项目授予OBS相关的RBAC策略后，大概需要等待13分钟RBAC策略才能生效；授予OBS相关的系统策略后，大概需要等待5分钟系统策略能生效。</p>
</div></div>
</li><li>如果使用文件存储，需要设置SFS FullAccess权限。</li></ul>
</td>
</tr>
<tr id="row39021315071"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p8902715071"><a name="p8902715071"></a><a name="p8902715071"></a>集群管理</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p14902111511717"><a name="p14902111511717"></a><a name="p14902111511717"></a>应用运维管理 AOM</p>
<p id="p178879743210"><a name="p178879743210"></a><a name="p178879743210"></a>费用中心 BSS</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><a name="ul772124115296"></a><a name="ul772124115296"></a><ul id="ul772124115296"><li>如果需要弹性扩容权限，需要设置AOM&nbsp;FullAccess权限。</li><li>如果需要转包周期，需要设置BSS Administrator权限。</li></ul>
</td>
</tr>
<tr id="row790217151578"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p1790281519714"><a name="p1790281519714"></a><a name="p1790281519714"></a>节点管理</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p129021156718"><a name="p129021156718"></a><a name="p129021156718"></a>弹性云服务器 ECS</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><p id="p12840824466"><a name="p12840824466"></a><a name="p12840824466"></a>当IAM用户权限为CCE Administrator时，如果创建和删除节点，需要配置ECS FullAccess或ECS Administrator权限，以及VPC Administrator权限。</p>
</td>
</tr>
<tr id="row1890251514716"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p39021615371"><a name="p39021615371"></a><a name="p39021615371"></a>网络管理</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p1588385973516"><a name="p1588385973516"></a><a name="p1588385973516"></a>弹性负载均衡 ELB</p>
<p id="p19883145923514"><a name="p19883145923514"></a><a name="p19883145923514"></a>NAT网关 NAT</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><p id="p052172153518"><a name="p052172153518"></a><a name="p052172153518"></a>正常创建时不依赖其他服务的权限。</p>
<a name="ul5525210353"></a><a name="ul5525210353"></a><ul id="ul5525210353"><li>如果需要创建ELB类型的服务，需要设置ELB FullAccess或者ELB Administrator权限，以及VPC Administrator权限。</li><li>如果需要NAT网关类型的服务，需要设置NAT Administrator权限。</li></ul>
</td>
</tr>
<tr id="row14486172213364"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p18487522123612"><a name="p18487522123612"></a><a name="p18487522123612"></a>存储管理</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p116411756133813"><a name="p116411756133813"></a><a name="p116411756133813"></a>对象存储服务 OBS</p>
<p id="p126411556163811"><a name="p126411556163811"></a><a name="p126411556163811"></a>弹性文件服务 SFS</p>
<p id="p344642920405"><a name="p344642920405"></a><a name="p344642920405"></a>极速文件存储 EFS（SFS Turbo）</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><a name="ul146023714385"></a><a name="ul146023714385"></a><ul id="ul146023714385"><li>如果使用对象存储，需要全局设置OBS Administrator权限。<div class="note" id="cce_10_0190_note1215220141518"><a name="cce_10_0190_note1215220141518"></a><a name="cce_10_0190_note1215220141518"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="cce_10_0190_p0153120121518"><a name="cce_10_0190_p0153120121518"></a><a name="cce_10_0190_p0153120121518"></a>由于缓存的存在，对用户、用户组以及企业项目授予OBS相关的RBAC策略后，大概需要等待13分钟RBAC策略才能生效；授予OBS相关的系统策略后，大概需要等待5分钟系统策略能生效。</p>
</div></div>
</li><li>如果使用文件存储，需要设置SFS FullAccess权限。</li><li>如果使用极速文件存储，需要设置SFS Turbo Admin权限</li></ul>
<p id="p533161762815"><a name="p533161762815"></a><a name="p533161762815"></a>导入存储的功能需要设置CCE Administrator权限。</p>
</td>
</tr>
<tr id="row1488112216362"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p144881022123614"><a name="p144881022123614"></a><a name="p144881022123614"></a>命名空间</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p64880224363"><a name="p64880224363"></a><a name="p64880224363"></a>/</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><p id="p1548818222361"><a name="p1548818222361"></a><a name="p1548818222361"></a>无需其他依赖权限。</p>
</td>
</tr>
<tr id="row748852253612"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p948882214364"><a name="p948882214364"></a><a name="p948882214364"></a>模板市场</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p257594214394"><a name="p257594214394"></a><a name="p257594214394"></a>/</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><p id="p1457514212392"><a name="p1457514212392"></a><a name="p1457514212392"></a>当前仅支持帐号、设置了CCE Administrator权限的IAM用户访问。</p>
</td>
</tr>
<tr id="row248812273618"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p10488142233620"><a name="p10488142233620"></a><a name="p10488142233620"></a>插件管理</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p51171157173918"><a name="p51171157173918"></a><a name="p51171157173918"></a>/</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><p id="p218618303395"><a name="p218618303395"></a><a name="p218618303395"></a>支持帐号、设置了CCE Administrator、CCE FullAccess或CCE ReadOnlyAccess等权限的IAM用户访问本功能。</p>
</td>
</tr>
<tr id="row54891622173617"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p1748919220362"><a name="p1748919220362"></a><a name="p1748919220362"></a>权限管理</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p1214191764016"><a name="p1214191764016"></a><a name="p1214191764016"></a>/</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><a name="ul372099481"></a><a name="ul372099481"></a><ul id="ul372099481"><li>支持帐号访问。</li><li>支持设置了CCE Administrator和Security Administrator（全局级策略）权限的IAM用户访问。</li><li>支持设置了CCE FullAccess或CCE ReadOnlyAccess权限的IAM用户访问。</li></ul>
</td>
</tr>
<tr id="row1588069154010"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p1388110934011"><a name="p1388110934011"></a><a name="p1388110934011"></a>配置中心</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p28816914409"><a name="p28816914409"></a><a name="p28816914409"></a>/</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><a name="ul858844185010"></a><a name="ul858844185010"></a><ul id="ul858844185010"><li>配置项 ( ConfigMap )无需其他依赖权限。</li><li>密钥 ( Secret )需要在命名空间权限下设置cluster-admin、admin或者edit权限才能查看，依赖服务需要添加DEW KeypairFullAccess或者DEW KeypairReadOnlyAccess权限。</li></ul>
</td>
</tr>
<tr id="row1090217151179"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p18903615977"><a name="p18903615977"></a><a name="p18903615977"></a>帮助中心</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p943035294110"><a name="p943035294110"></a><a name="p943035294110"></a>/</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><p id="p1343065219410"><a name="p1343065219410"></a><a name="p1343065219410"></a>无需其他依赖权限。</p>
</td>
</tr>
<tr id="row1853314583492"><td class="cellrowborder" valign="top" width="21.872187218721873%" headers="mcps1.2.4.1.1 "><p id="p9533958114919"><a name="p9533958114919"></a><a name="p9533958114919"></a>其他服务跳转</p>
</td>
<td class="cellrowborder" valign="top" width="28.642864286428644%" headers="mcps1.2.4.1.2 "><p id="p19533258154918"><a name="p19533258154918"></a><a name="p19533258154918"></a>容器镜像服务 SWR</p>
<p id="p11154184565220"><a name="p11154184565220"></a><a name="p11154184565220"></a>应用服务网格 ASM</p>
<p id="p4509331523"><a name="p4509331523"></a><a name="p4509331523"></a>应用运维管理 AOM</p>
<p id="p581510413526"><a name="p581510413526"></a><a name="p581510413526"></a>多云容器平台 MCP</p>
</td>
<td class="cellrowborder" valign="top" width="49.48494849484948%" headers="mcps1.2.4.1.3 "><p id="p253325815496"><a name="p253325815496"></a><a name="p253325815496"></a>为便于您快速进入CCE相关服务的控制台，在CCE控制台增加了其他服务的跳转链接，CCE默认没有这些服务的全部权限，如果IAM用户需要查看或使用其功能，请按照该服务的权限策略说明设置相应的权限策略。</p>
</td>
</tr>
</tbody>
</table>

