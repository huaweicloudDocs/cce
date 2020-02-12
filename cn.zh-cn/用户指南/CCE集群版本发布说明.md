# CCE集群版本发布说明<a name="cce_01_0068"></a>

为了能够更好地方便您使用容器服务，确保您使用稳定又可靠的Kubernetes版本，云容器引擎CCE推出Kubernetes版本支持机制，将在每半年发布一个版本，每个版本的支持周期为一年，请您务必在维护周期结束之前升级您的Kubernetes集群。

CCE集群版本更迭策略，请参见[Kubernetes版本支持机制](cce_01_0237.md)。

CCE集群新版本升级，请参见[集群版本升级说明](集群版本升级说明.md)。

## V1.15版本<a name="section18351606577"></a>

**表 1**  V1.15公测版本集群特性说明

<a name="table1381822411498"></a>
<table><thead align="left"><tr id="row18181424144918"><th class="cellrowborder" valign="top" width="29.12%" id="mcps1.2.3.1.1"><p id="p18188245498"><a name="p18188245498"></a><a name="p18188245498"></a>Kubernetes版本（CCE增强版）</p>
</th>
<th class="cellrowborder" valign="top" width="70.88%" id="mcps1.2.3.1.2"><p id="p13819424114915"><a name="p13819424114915"></a><a name="p13819424114915"></a>升级说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row9819824154913"><td class="cellrowborder" valign="top" width="29.12%" headers="mcps1.2.3.1.1 "><p id="p181952410497"><a name="p181952410497"></a><a name="p181952410497"></a>v1.15.6-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.88%" headers="mcps1.2.3.1.2 "><p id="p989313443514"><a name="p989313443514"></a><a name="p989313443514"></a><strong id="b213552014167"><a name="b213552014167"></a><a name="b213552014167"></a>1.15版本已正式发布，欢迎使用。</strong></p>
<p id="p41121229115010"><a name="p41121229115010"></a><a name="p41121229115010"></a>1.15版本集群提供如下主要特性能力:</p>
<a name="ul9447153212409"></a><a name="ul9447153212409"></a><ul id="ul9447153212409"><li>支持Kubernetes参数动态配置。详情参见<a href="配置管理.md">配置管理</a>和<a href="管理节点池.md">管理节点池</a>。</li><li>支持IPV6访问。具体请参见<a href="https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_0022.html" target="_blank" rel="noopener noreferrer">搭建IPv4/IPv6双栈集群</a>。</li><li>CCE存储支持基于CSI的云原生容器存储系统。具体请参见<a href="Everest（系统资源插件-必装）.md">Everest</a>插件。</li></ul>
</td>
</tr>
</tbody>
</table>

## V1.13版本<a name="section1801516195711"></a>

**表 2**  V1.13版本集群特性说明

<a name="table14450940866"></a>
<table><thead align="left"><tr id="row145024011618"><th class="cellrowborder" valign="top" width="29.12%" id="mcps1.2.3.1.1"><p id="p3450154019612"><a name="p3450154019612"></a><a name="p3450154019612"></a>Kubernetes版本（CCE增强版）</p>
</th>
<th class="cellrowborder" valign="top" width="70.88%" id="mcps1.2.3.1.2"><p id="p19450184018614"><a name="p19450184018614"></a><a name="p19450184018614"></a>升级说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row445115408610"><td class="cellrowborder" valign="top" width="29.12%" headers="mcps1.2.3.1.1 "><p id="p845119408613"><a name="p845119408613"></a><a name="p845119408613"></a>v1.13.10-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.88%" headers="mcps1.2.3.1.2 "><p id="p84511140467"><a name="p84511140467"></a><a name="p84511140467"></a>主要特性：</p>
<a name="ul1745134011611"></a><a name="ul1745134011611"></a><ul id="ul1745134011611"><li>混合集群支持添加ARM节点</li><li>负载均衡支持设置名称</li><li>4层负载均衡支持健康检查，7层负载均衡支持健康检查/分配策略/会话保持</li><li>混合集群支持创建裸金属节点（容器隧道网络）</li><li>支持AI加速型节点（搭载海思Ascend 310 AI处理器），适用于图像识别、视频处理、推理计算以及机器学习等场景</li><li>支持配置docker baseSize</li><li>支持命名空间亲和调度</li><li>支持节点数据盘划分用户空间</li><li>支持集群cpu管理策略</li><li>支持集群下的节点跨子网（容器隧道网络）</li></ul>
</td>
</tr>
<tr id="row119478492200"><td class="cellrowborder" valign="top" width="29.12%" headers="mcps1.2.3.1.1 "><p id="p1994784972010"><a name="p1994784972010"></a><a name="p1994784972010"></a>v1.13.7-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.88%" headers="mcps1.2.3.1.2 "><a name="ul770414515210"></a><a name="ul770414515210"></a><ul id="ul770414515210"><li>Kubernetes同步社区1.13.7版本</li><li>支持网络平面（NetworkAttachmentDefinition）</li></ul>
</td>
</tr>
</tbody>
</table>

## V1.11及之前版本<a name="section19479153020578"></a>

**表 3**  V1.11及之前版本集群特性说明

<a name="table7445114645410"></a>
<table><thead align="left"><tr id="row244694645413"><th class="cellrowborder" valign="top" width="29.03%" id="mcps1.2.3.1.1"><p id="p174461846165411"><a name="p174461846165411"></a><a name="p174461846165411"></a>Kubernetes版本（CCE增强版）</p>
</th>
<th class="cellrowborder" valign="top" width="70.97%" id="mcps1.2.3.1.2"><p id="p1446154614545"><a name="p1446154614545"></a><a name="p1446154614545"></a>升级说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row2023116441905"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p863710461905"><a name="p863710461905"></a><a name="p863710461905"></a>v1.11.7-r2</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p17637174616018"><a name="p17637174616018"></a><a name="p17637174616018"></a>主要特性：</p>
<a name="ul963719461905"></a><a name="ul963719461905"></a><ul id="ul963719461905"><li>GPU支持V100类型</li><li>集群支持权限管理</li></ul>
</td>
</tr>
<tr id="row190113461164"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p15901194614161"><a name="p15901194614161"></a><a name="p15901194614161"></a>v1.11.7-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p10901164618166"><a name="p10901164618166"></a><a name="p10901164618166"></a>主要特性：</p>
<a name="ul1513752874712"></a><a name="ul1513752874712"></a><ul id="ul1513752874712"><li>Kubernetes同步社区1.11.7版本</li><li>支持创建节点池（<span>nodepool</span>），虚拟机/鲲鹏ARM集群均支持</li><li>混合集群支持创建裸金属节点（vpc 网络），支持裸金属和虚机混合部署</li><li>GPU支持V100类型</li><li>1.11集群对接AOM告警通知机制</li><li>Service支持访问类型切换</li><li>支持服务网段</li><li>集群支持自定义每个节点分配的IP数（IP分配）</li></ul>
</td>
</tr>
<tr id="row1760182091416"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p15760320151412"><a name="p15760320151412"></a><a name="p15760320151412"></a>v1.11.3-r2</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p87608204144"><a name="p87608204144"></a><a name="p87608204144"></a>主要特性：</p>
<a name="ul184061349161515"></a><a name="ul184061349161515"></a><ul id="ul184061349161515"><li>集群支持IPV6双栈</li><li>ELB负载均衡支持源IP跟后端服务会话保持</li></ul>
</td>
</tr>
<tr id="row13751104313019"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p177511443701"><a name="p177511443701"></a><a name="p177511443701"></a>v1.11.3-r1</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p1775154314015"><a name="p1775154314015"></a><a name="p1775154314015"></a>主要特性：</p>
<a name="ul1999017372616"></a><a name="ul1999017372616"></a><ul id="ul1999017372616"><li>Ingress的URL匹配支持Perl语法的正则表达式</li></ul>
</td>
</tr>
<tr id="row0226111212582"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p822671216588"><a name="p822671216588"></a><a name="p822671216588"></a>v1.11.3-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p20226181211581"><a name="p20226181211581"></a><a name="p20226181211581"></a>主要特性：</p>
<a name="ul169031946461"></a><a name="ul169031946461"></a><ul id="ul169031946461"><li>Kubernetes同步社区1.11.3版本</li><li>集群Master节点支持多可用区</li><li>容器存储支持对接SFS Turbo极速文件存储</li></ul>
</td>
</tr>
<tr id="row136651538121314"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p16652038131318"><a name="p16652038131318"></a><a name="p16652038131318"></a>v1.9.10-r2</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p1666533815133"><a name="p1666533815133"></a><a name="p1666533815133"></a>主要特性：</p>
<a name="ul124764157147"></a><a name="ul124764157147"></a><ul id="ul124764157147"><li>ELB负载均衡支持源IP跟后端服务会话保持</li></ul>
</td>
</tr>
<tr id="row193481521542"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p53481952205413"><a name="p53481952205413"></a><a name="p53481952205413"></a>v1.9.10-r1</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p734825215416"><a name="p734825215416"></a><a name="p734825215416"></a>主要特性：</p>
<a name="ul692918571614"></a><a name="ul692918571614"></a><ul id="ul692918571614"><li>支持对接EFS存储</li><li>支持Service自动创建二代ELB</li><li>支持公网二代ELB透传源IP</li><li>支持设置节点最大实例数maxPods</li></ul>
</td>
</tr>
<tr id="row7688248145420"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p1688448205411"><a name="p1688448205411"></a><a name="p1688448205411"></a>v1.9.10-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p1168894815417"><a name="p1168894815417"></a><a name="p1168894815417"></a>主要特性：</p>
<a name="ul1771853679"></a><a name="ul1771853679"></a><ul id="ul1771853679"><li>kubernetes对接ELB/Ingress，新增流控机制</li><li>Kubernetes同步社区1.9.10版本</li><li>支持Kubernetes RBAC能力授权</li></ul>
<p id="p1257813375617"><a name="p1257813375617"></a><a name="p1257813375617"></a>问题修复：</p>
<a name="ul13926122681411"></a><a name="ul13926122681411"></a><ul id="ul13926122681411"><li>修复操作系统cgroup内核BUG导致概率出现的节点内存泄漏问题</li></ul>
</td>
</tr>
<tr id="row184578529509"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p945916523506"><a name="p945916523506"></a><a name="p945916523506"></a>v1.9.7-r1</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p74594528501"><a name="p74594528501"></a><a name="p74594528501"></a>主要特性：</p>
<a name="ul1080183571411"></a><a name="ul1080183571411"></a><ul id="ul1080183571411"><li>增强PVC和PV事件的上报机制，PVC详情页支持查看事件</li><li>支持对接第三方认证系统</li><li>集群支持纳管EulerOS2.3的物理机</li><li>数据盘支持用户自定义分配比例</li><li>裸金属场景支持对接EVS云硬盘存储</li><li>裸金属场景下支持IB网卡</li><li>裸金属集群支持通过CM-v3接口创建节点</li></ul>
</td>
</tr>
<tr id="row114461746125410"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p147321753124016"><a name="p147321753124016"></a><a name="p147321753124016"></a>v1.9.7-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p5732175312401"><a name="p5732175312401"></a><a name="p5732175312401"></a>主要特性：</p>
<a name="ul055117481143"></a><a name="ul055117481143"></a><ul id="ul055117481143"><li>新建集群的Docker版本升级到1706</li><li>支持DNS级联</li><li>支持插件化管理</li><li>Kubernetes同步社区1.9.7版本</li><li>支持7层ingress的https功能</li><li>有状态工作负载支持迁移调度更新升级</li></ul>
</td>
</tr>
<tr id="row244634610548"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p1073275354018"><a name="p1073275354018"></a><a name="p1073275354018"></a>v1.9.2-r3</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p7336195164511"><a name="p7336195164511"></a><a name="p7336195164511"></a>主要特性：</p>
<a name="ul13013019154"></a><a name="ul13013019154"></a><ul id="ul13013019154"><li>集群支持创建/纳管CentOS7.4操作系统的节点</li><li>kubernetes的Service支持对接DNAT网关服务</li><li>NetworkPolicy能力开放</li><li>增强型ELB支持Service配置多个端口</li></ul>
<p id="p03473518458"><a name="p03473518458"></a><a name="p03473518458"></a>问题修复：</p>
<a name="ul182521301519"></a><a name="ul182521301519"></a><ul id="ul182521301519"><li>修复kubernetes资源回收过程中连不上kube-apiserver导致pod残留的问题</li><li>修复节点弹性扩容数据不准确的问题</li></ul>
</td>
</tr>
<tr id="row2044604619544"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p1973285324018"><a name="p1973285324018"></a><a name="p1973285324018"></a>v1.9.2-r2</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p1973215312400"><a name="p1973215312400"></a><a name="p1973215312400"></a>主要特性：</p>
<a name="ul680672012154"></a><a name="ul680672012154"></a><ul id="ul680672012154"><li>经典型ELB支持自定义健康检查端口</li><li>经典型ELB性能优化</li><li>ELB四层负载均衡支持修改Service的端口</li></ul>
<p id="p12072015598"><a name="p12072015598"></a><a name="p12072015598"></a>问题修复：</p>
<a name="ul1546113081515"></a><a name="ul1546113081515"></a><ul id="ul1546113081515"><li>修复网络插件防止健康检查概率死锁问题</li><li>修复高可用集群haproxy连接数限制问题</li></ul>
</td>
</tr>
<tr id="row44477467549"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p17734153104013"><a name="p17734153104013"></a><a name="p17734153104013"></a>v1.9.2-r1</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p17849318105413"><a name="p17849318105413"></a><a name="p17849318105413"></a>主要特性：</p>
<a name="ul43911610101310"></a><a name="ul43911610101310"></a><ul id="ul43911610101310"><li>Kubernetes同步社区1.9.2版本</li><li>集群节点支持CentOS 7.1操作系统</li><li>支持GPU节点，支持GPU资源限制</li><li>支持web-terminal插件</li></ul>
</td>
</tr>
<tr id="row12447184612543"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p1973414530408"><a name="p1973414530408"></a><a name="p1973414530408"></a>v1.7.3-r13</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p14305115718469"><a name="p14305115718469"></a><a name="p14305115718469"></a>主要特性：</p>
<a name="ul109523572122"></a><a name="ul109523572122"></a><ul id="ul109523572122"><li>新建集群的Docker版本升级到1706</li><li>支持DNS级联</li><li>支持插件化管理</li><li>增强PVC和PV事件的上报机制</li></ul>
</td>
</tr>
<tr id="row7718776556"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p12734155319403"><a name="p12734155319403"></a><a name="p12734155319403"></a>v1.7.3-r12</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p3734744104115"><a name="p3734744104115"></a><a name="p3734744104115"></a>主要特性：</p>
<a name="ul1220014718124"></a><a name="ul1220014718124"></a><ul id="ul1220014718124"><li>集群支持创建/纳管CentOS7.4操作系统的节点</li><li>kubernetes的Service支持对接DNAT网关服务</li><li>NetworkPolicy能力开放</li><li>增强型ELB支持Service配置多个端口</li></ul>
<p id="p198333541432"><a name="p198333541432"></a><a name="p198333541432"></a>问题修复：</p>
<a name="ul47184051216"></a><a name="ul47184051216"></a><ul id="ul47184051216"><li>修复kubernetes资源回收过程中连不上kube-apiserver导致pod残留的问题</li><li>修复节点弹性扩容数据不准确的问题</li><li>事件老化周期提示修正：集群老化周期为1小时</li></ul>
</td>
</tr>
<tr id="row685121145914"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p1173425374014"><a name="p1173425374014"></a><a name="p1173425374014"></a>v1.7.3-r11</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p1542765013540"><a name="p1542765013540"></a><a name="p1542765013540"></a>主要特性：</p>
<a name="ul1662182618123"></a><a name="ul1662182618123"></a><ul id="ul1662182618123"><li>经典型ELB支持自定义健康检查端口</li><li>经典型ELB性能优化</li><li>ELB四层负载均衡支持修改Service的端口</li><li>支持删除命名空间</li><li>支持EVS云硬盘存储解绑</li><li>支持配置迁移策略</li></ul>
<p id="p111749433574"><a name="p111749433574"></a><a name="p111749433574"></a>问题修复：</p>
<a name="ul13646619181212"></a><a name="ul13646619181212"></a><ul id="ul13646619181212"><li>修复网络插件防止健康检查概率死锁问题</li><li>修复高可用集群haproxy连接数限制问题</li></ul>
</td>
</tr>
<tr id="row1328201465917"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p147341153104013"><a name="p147341153104013"></a><a name="p147341153104013"></a>v1.7.3-r10</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p37571333101518"><a name="p37571333101518"></a><a name="p37571333101518"></a>主要特性：</p>
<a name="ul552378131214"></a><a name="ul552378131214"></a><ul id="ul552378131214"><li>容器网络支持Overlay L2模式</li><li>集群节点支持GPU类型虚机</li><li>集群节点支持CentOS 7.1操作系统，支持操作系统选择</li><li>Windows集群支持对接二代ELB</li><li>支持弹性文件服务SFS导入</li><li>裸金属场景支持对接SFS文件存储、OBS对象存储</li></ul>
</td>
</tr>
<tr id="row7597191665914"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p16734185311409"><a name="p16734185311409"></a><a name="p16734185311409"></a>v1.7.3-r9</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p21087116496"><a name="p21087116496"></a><a name="p21087116496"></a>主要特性：</p>
<a name="ul14714175411113"></a><a name="ul14714175411113"></a><ul id="ul14714175411113"><li>工作负载支持跨AZ部署</li><li>容器存储支持OBS对象存储服务</li><li>支持ELB L7负载均衡</li><li>Windows集群支持EVS存储</li><li>裸金属集群支持devicemapper direct-lvm模式</li></ul>
</td>
</tr>
<tr id="row15124153951815"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p137351753124016"><a name="p137351753124016"></a><a name="p137351753124016"></a>v1.7.3-r8</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p5919174415467"><a name="p5919174415467"></a><a name="p5919174415467"></a>主要特性：</p>
<a name="ul102771346191113"></a><a name="ul102771346191113"></a><ul id="ul102771346191113"><li>集群支持节点弹性扩容</li><li>支持纳管ARM节点</li></ul>
</td>
</tr>
<tr id="row42151109118"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p1673575320409"><a name="p1673575320409"></a><a name="p1673575320409"></a>v1.7.3-r7</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p1094774518390"><a name="p1094774518390"></a><a name="p1094774518390"></a>主要特性：</p>
<a name="ul74221734141119"></a><a name="ul74221734141119"></a><ul id="ul74221734141119"><li>容器隧道网络集群支持纳管SUSE 12sp2节点</li><li>docker支持direct-lvm模式挂载devicemapper</li><li>集群支持安装dashboard</li><li>支持创建Windows集群</li></ul>
</td>
</tr>
<tr id="row192158018111"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p6737125318403"><a name="p6737125318403"></a><a name="p6737125318403"></a>v1.7.3-r6</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p716518253818"><a name="p716518253818"></a><a name="p716518253818"></a>主要特性：</p>
<a name="ul119781427151114"></a><a name="ul119781427151114"></a><ul id="ul119781427151114"><li>集群存储对接原生EVS接口</li></ul>
</td>
</tr>
<tr id="row22151501112"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p5737125317401"><a name="p5737125317401"></a><a name="p5737125317401"></a>v1.7.3-r5</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p1588084917202"><a name="p1588084917202"></a><a name="p1588084917202"></a>主要特性：</p>
<a name="ul3154152071118"></a><a name="ul3154152071118"></a><ul id="ul3154152071118"><li>支持创建HA高可靠集群</li></ul>
<p id="p267517230"><a name="p267517230"></a><a name="p267517230"></a>问题修复：</p>
<a name="ul197111154119"></a><a name="ul197111154119"></a><ul id="ul197111154119"><li>节点重启后容器网络不通</li></ul>
</td>
</tr>
<tr id="row178217494010"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p13738105394010"><a name="p13738105394010"></a><a name="p13738105394010"></a>v1.7.3-r4</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p11573174852613"><a name="p11573174852613"></a><a name="p11573174852613"></a>主要特性：</p>
<a name="ul434867151112"></a><a name="ul434867151112"></a><ul id="ul434867151112"><li>集群性能优化</li><li>裸金属集群支持对接ELB</li></ul>
</td>
</tr>
<tr id="row19887142710119"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p1373865312406"><a name="p1373865312406"></a><a name="p1373865312406"></a>v1.7.3-r3</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p25732322242"><a name="p25732322242"></a><a name="p25732322242"></a>主要特性：</p>
<a name="ul2708101191110"></a><a name="ul2708101191110"></a><ul id="ul2708101191110"><li>容器存储支持KVM虚拟机挂载</li></ul>
</td>
</tr>
<tr id="row388714274111"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p1738145364010"><a name="p1738145364010"></a><a name="p1738145364010"></a>v1.7.3-r2</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p20873342162219"><a name="p20873342162219"></a><a name="p20873342162219"></a>主要特性：</p>
<a name="ul19355184918109"></a><a name="ul19355184918109"></a><ul id="ul19355184918109"><li>容器存储支持SFS文件存储</li><li>工作负载支持自定义应用日志</li><li>开放工作负载优雅缩容</li></ul>
<p id="p1767195515222"><a name="p1767195515222"></a><a name="p1767195515222"></a>问题修复：</p>
<a name="ul1028924317109"></a><a name="ul1028924317109"></a><ul id="ul1028924317109"><li>修复容器存储AK/SK会过期的问题</li></ul>
</td>
</tr>
<tr id="row68879271917"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p2738155324010"><a name="p2738155324010"></a><a name="p2738155324010"></a>v1.7.3-r1</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p59371326220"><a name="p59371326220"></a><a name="p59371326220"></a>主要特性：</p>
<a name="ul727115370102"></a><a name="ul727115370102"></a><ul id="ul727115370102"><li>kube-dns支持外部域名解析</li></ul>
</td>
</tr>
<tr id="row13696412411"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="p17738165354012"><a name="p17738165354012"></a><a name="p17738165354012"></a>v1.7.3-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="p35582046192118"><a name="p35582046192118"></a><a name="p35582046192118"></a>主要特性：</p>
<a name="ul18348102821015"></a><a name="ul18348102821015"></a><ul id="ul18348102821015"><li>Kubernetes同步社区1.7.3版本</li><li>支持ELB负载均衡</li><li>容器存储支持XEN虚拟机挂载</li><li>容器存储支持EVS云硬盘存储</li></ul>
</td>
</tr>
</tbody>
</table>

