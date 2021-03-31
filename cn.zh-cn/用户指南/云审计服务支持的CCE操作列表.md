# 云审计服务支持的CCE操作列表<a name="cce_01_0025"></a>

CCE通过云审计服务（Cloud Trace Service，简称CTS）为您提供云服务资源的操作记录，记录内容包括您从云管理控制台或者开放API发起的云服务资源操作请求以及每次请求的结果，供您查询、审计和回溯使用。

**表 1**  云审计服务支持的CCE操作列表

<a name="table10122133613599"></a>
<table><thead align="left"><tr id="row1612243618593"><th class="cellrowborder" valign="top" width="28.37%" id="mcps1.2.4.1.1"><p id="p5122153665915"><a name="p5122153665915"></a><a name="p5122153665915"></a>操作名称</p>
</th>
<th class="cellrowborder" valign="top" width="25.230000000000004%" id="mcps1.2.4.1.2"><p id="p11394135314515"><a name="p11394135314515"></a><a name="p11394135314515"></a>资源类型</p>
</th>
<th class="cellrowborder" valign="top" width="46.400000000000006%" id="mcps1.2.4.1.3"><p id="p13195515620"><a name="p13195515620"></a><a name="p13195515620"></a>事件名称</p>
</th>
</tr>
</thead>
<tbody><tr id="row14122193635917"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p125118355399"><a name="p125118355399"></a><a name="p125118355399"></a>创建集群</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p63951953453"><a name="p63951953453"></a><a name="p63951953453"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p479310893919"><a name="p479310893919"></a><a name="p479310893919"></a>createCluster</p>
</td>
</tr>
<tr id="row1512383615911"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p16511133514395"><a name="p16511133514395"></a><a name="p16511133514395"></a>更新集群</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p558318520817"><a name="p558318520817"></a><a name="p558318520817"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p279412853917"><a name="p279412853917"></a><a name="p279412853917"></a>updateCluster</p>
</td>
</tr>
<tr id="row2123103625916"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p151120356398"><a name="p151120356398"></a><a name="p151120356398"></a>删除集群</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p792271788"><a name="p792271788"></a><a name="p792271788"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p77941883396"><a name="p77941883396"></a><a name="p77941883396"></a>deleteCluster/claimCluster</p>
</td>
</tr>
<tr id="row5816121312386"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p451112356392"><a name="p451112356392"></a><a name="p451112356392"></a>创建节点</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p262008180"><a name="p262008180"></a><a name="p262008180"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p14794188153913"><a name="p14794188153913"></a><a name="p14794188153913"></a>createNode</p>
</td>
</tr>
<tr id="row546661415383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p15511735153916"><a name="p15511735153916"></a><a name="p15511735153916"></a>添加静态节点</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p173251011817"><a name="p173251011817"></a><a name="p173251011817"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p20794198173915"><a name="p20794198173915"></a><a name="p20794198173915"></a>addStaticNode</p>
</td>
</tr>
<tr id="row168015145382"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1651243519395"><a name="p1651243519395"></a><a name="p1651243519395"></a>更新节点</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p12546411887"><a name="p12546411887"></a><a name="p12546411887"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p5794381398"><a name="p5794381398"></a><a name="p5794381398"></a>updateNode</p>
</td>
</tr>
<tr id="row066512346381"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1851293593911"><a name="p1851293593911"></a><a name="p1851293593911"></a>删除一个主机</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1844311316815"><a name="p1844311316815"></a><a name="p1844311316815"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p10794158193910"><a name="p10794158193910"></a><a name="p10794158193910"></a>deleteOneHost</p>
</td>
</tr>
<tr id="row39231134123816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1651273543915"><a name="p1651273543915"></a><a name="p1651273543915"></a>删除所有主机</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p513051514813"><a name="p513051514813"></a><a name="p513051514813"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p137942873917"><a name="p137942873917"></a><a name="p137942873917"></a>deleteAllHosts</p>
</td>
</tr>
<tr id="row11185193513816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1651218355392"><a name="p1651218355392"></a><a name="p1651218355392"></a>挂起用户资源</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p19733141618812"><a name="p19733141618812"></a><a name="p19733141618812"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p10794108193916"><a name="p10794108193916"></a><a name="p10794108193916"></a>suspendUserResource</p>
</td>
</tr>
<tr id="row16450535103817"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1351243543918"><a name="p1351243543918"></a><a name="p1351243543918"></a>创建ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p14476171817820"><a name="p14476171817820"></a><a name="p14476171817820"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p14794158123914"><a name="p14794158123914"></a><a name="p14794158123914"></a>createConfigmaps</p>
</td>
</tr>
<tr id="row107342035123814"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p85121835133911"><a name="p85121835133911"></a><a name="p85121835133911"></a>创建DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1831114214817"><a name="p1831114214817"></a><a name="p1831114214817"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p179458103919"><a name="p179458103919"></a><a name="p179458103919"></a>createDaemonsets</p>
</td>
</tr>
<tr id="row189915354383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p85121535103919"><a name="p85121535103919"></a><a name="p85121535103919"></a>创建Deployment</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1568316221812"><a name="p1568316221812"></a><a name="p1568316221812"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p77941781394"><a name="p77941781394"></a><a name="p77941781394"></a>createDeployments</p>
</td>
</tr>
<tr id="row11247123618381"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p451213352396"><a name="p451213352396"></a><a name="p451213352396"></a>创建Event</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p16516162415811"><a name="p16516162415811"></a><a name="p16516162415811"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p17794188173919"><a name="p17794188173919"></a><a name="p17794188173919"></a>createEvents</p>
</td>
</tr>
<tr id="row13528183623818"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p251210351397"><a name="p251210351397"></a><a name="p251210351397"></a>创建Ingress</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1258626289"><a name="p1258626289"></a><a name="p1258626289"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p97948863919"><a name="p97948863919"></a><a name="p97948863919"></a>createIngresses</p>
</td>
</tr>
<tr id="row138443361388"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p35131235103910"><a name="p35131235103910"></a><a name="p35131235103910"></a>创建Job</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p96658281811"><a name="p96658281811"></a><a name="p96658281811"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p3794883397"><a name="p3794883397"></a><a name="p3794883397"></a>createJobs</p>
</td>
</tr>
<tr id="row11196173713381"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1051363523919"><a name="p1051363523919"></a><a name="p1051363523919"></a>创建namespace</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p154721136185"><a name="p154721136185"></a><a name="p154721136185"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p147941873920"><a name="p147941873920"></a><a name="p147941873920"></a>createNamespaces</p>
</td>
</tr>
<tr id="row1547923713817"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p151316356394"><a name="p151316356394"></a><a name="p151316356394"></a>创建Node</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p74721836288"><a name="p74721836288"></a><a name="p74721836288"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p47958813910"><a name="p47958813910"></a><a name="p47958813910"></a>createNodes</p>
</td>
</tr>
<tr id="row1806137163818"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1151310357393"><a name="p1151310357393"></a><a name="p1151310357393"></a>创建PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p5472136185"><a name="p5472136185"></a><a name="p5472136185"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p16795128113912"><a name="p16795128113912"></a><a name="p16795128113912"></a>createPersistentvolumeclaims</p>
</td>
</tr>
<tr id="row15143838133818"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1451343543916"><a name="p1451343543916"></a><a name="p1451343543916"></a>创建Pod</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p12472193617810"><a name="p12472193617810"></a><a name="p12472193617810"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1079513812399"><a name="p1079513812399"></a><a name="p1079513812399"></a>createPods</p>
</td>
</tr>
<tr id="row14502038193811"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p5513935123919"><a name="p5513935123919"></a><a name="p5513935123919"></a>创建ReplicaSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p24722364819"><a name="p24722364819"></a><a name="p24722364819"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p197955843913"><a name="p197955843913"></a><a name="p197955843913"></a>createReplicasets</p>
</td>
</tr>
<tr id="row1980053883816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p75138353395"><a name="p75138353395"></a><a name="p75138353395"></a>创建ResourceQuota</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p447220361787"><a name="p447220361787"></a><a name="p447220361787"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p197958863913"><a name="p197958863913"></a><a name="p197958863913"></a>createResourcequotas</p>
</td>
</tr>
<tr id="row11151173923816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p10513835193915"><a name="p10513835193915"></a><a name="p10513835193915"></a>创建密钥</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p164728361786"><a name="p164728361786"></a><a name="p164728361786"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p37958833915"><a name="p37958833915"></a><a name="p37958833915"></a>createSecrets</p>
</td>
</tr>
<tr id="row1950073943815"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p4514835193915"><a name="p4514835193915"></a><a name="p4514835193915"></a>创建服务</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p447219361584"><a name="p447219361584"></a><a name="p447219361584"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1679519813919"><a name="p1679519813919"></a><a name="p1679519813919"></a>createServices</p>
</td>
</tr>
<tr id="row118871714163811"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p4514935153910"><a name="p4514935153910"></a><a name="p4514935153910"></a>创建StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p114721236883"><a name="p114721236883"></a><a name="p114721236883"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p779514820397"><a name="p779514820397"></a><a name="p779514820397"></a>createStatefulsets</p>
</td>
</tr>
<tr id="row11704159385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p13514133513392"><a name="p13514133513392"></a><a name="p13514133513392"></a>创建卷</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p028711401889"><a name="p028711401889"></a><a name="p028711401889"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p127951887398"><a name="p127951887398"></a><a name="p127951887398"></a>createVolumes</p>
</td>
</tr>
<tr id="row6236161516385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p175141335173920"><a name="p175141335173920"></a><a name="p175141335173920"></a>删除ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p14287134019816"><a name="p14287134019816"></a><a name="p14287134019816"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p117959818394"><a name="p117959818394"></a><a name="p117959818394"></a>deleteConfigmaps</p>
</td>
</tr>
<tr id="row64003156383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p45141635123918"><a name="p45141635123918"></a><a name="p45141635123918"></a>删除DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p528716401089"><a name="p528716401089"></a><a name="p528716401089"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p97951280398"><a name="p97951280398"></a><a name="p97951280398"></a>deleteDaemonsets</p>
</td>
</tr>
<tr id="row8588151520383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p45149357396"><a name="p45149357396"></a><a name="p45149357396"></a>删除Deployment</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p11287340186"><a name="p11287340186"></a><a name="p11287340186"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p47951889391"><a name="p47951889391"></a><a name="p47951889391"></a>deleteDeployments</p>
</td>
</tr>
<tr id="row976691573816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p145141535183916"><a name="p145141535183916"></a><a name="p145141535183916"></a>删除Event</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1428764013814"><a name="p1428764013814"></a><a name="p1428764013814"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p127951786399"><a name="p127951786399"></a><a name="p127951786399"></a>deleteEvents</p>
</td>
</tr>
<tr id="row1093116152383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p351414356394"><a name="p351414356394"></a><a name="p351414356394"></a>删除Ingress</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p172878401282"><a name="p172878401282"></a><a name="p172878401282"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p117951580397"><a name="p117951580397"></a><a name="p117951580397"></a>deleteIngresses</p>
</td>
</tr>
<tr id="row8952162389"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p185141935123913"><a name="p185141935123913"></a><a name="p185141935123913"></a>删除Job</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p5287204019810"><a name="p5287204019810"></a><a name="p5287204019810"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p77966815390"><a name="p77966815390"></a><a name="p77966815390"></a>deleteJobs</p>
</td>
</tr>
<tr id="row627551663812"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1151417358393"><a name="p1151417358393"></a><a name="p1151417358393"></a>删除Namespace</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p0287194020815"><a name="p0287194020815"></a><a name="p0287194020815"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1079648183911"><a name="p1079648183911"></a><a name="p1079648183911"></a>deleteNamespaces</p>
</td>
</tr>
<tr id="row24561416203810"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p2051523520395"><a name="p2051523520395"></a><a name="p2051523520395"></a>删除Node</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p52872401818"><a name="p52872401818"></a><a name="p52872401818"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1579614813394"><a name="p1579614813394"></a><a name="p1579614813394"></a>deleteNodes/claimOneHost</p>
</td>
</tr>
<tr id="row86221816163818"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p15151135103918"><a name="p15151135103918"></a><a name="p15151135103918"></a>删除Pod</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p83571450812"><a name="p83571450812"></a><a name="p83571450812"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1379668193911"><a name="p1379668193911"></a><a name="p1379668193911"></a>deletePods</p>
</td>
</tr>
<tr id="row1779151617386"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1751583512391"><a name="p1751583512391"></a><a name="p1751583512391"></a>删除ReplicaSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1335718451081"><a name="p1335718451081"></a><a name="p1335718451081"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p20796686397"><a name="p20796686397"></a><a name="p20796686397"></a>deleteReplicasets</p>
</td>
</tr>
<tr id="row1995721663817"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p14515143503916"><a name="p14515143503916"></a><a name="p14515143503916"></a>删除ResourceQuota</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p0357174518810"><a name="p0357174518810"></a><a name="p0357174518810"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p107966817394"><a name="p107966817394"></a><a name="p107966817394"></a>deleteResourcequotas</p>
</td>
</tr>
<tr id="row1412191773811"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p251510357397"><a name="p251510357397"></a><a name="p251510357397"></a>删除Secret</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1735720451786"><a name="p1735720451786"></a><a name="p1735720451786"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p879638113910"><a name="p879638113910"></a><a name="p879638113910"></a>deleteSecrets</p>
</td>
</tr>
<tr id="row7664121717383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p451543520393"><a name="p451543520393"></a><a name="p451543520393"></a>删除Service</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p835774514820"><a name="p835774514820"></a><a name="p835774514820"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p13796108103917"><a name="p13796108103917"></a><a name="p13796108103917"></a>deleteServices</p>
</td>
</tr>
<tr id="row1079231717386"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p4515113518397"><a name="p4515113518397"></a><a name="p4515113518397"></a>删除StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p73578452814"><a name="p73578452814"></a><a name="p73578452814"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p107964812397"><a name="p107964812397"></a><a name="p107964812397"></a>deleteStatefulsets</p>
</td>
</tr>
<tr id="row69931317173813"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p135151335143920"><a name="p135151335143920"></a><a name="p135151335143920"></a>删除卷</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p93574457816"><a name="p93574457816"></a><a name="p93574457816"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p127963811395"><a name="p127963811395"></a><a name="p127963811395"></a>deleteVolumes</p>
</td>
</tr>
<tr id="row18139518193810"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1751673511397"><a name="p1751673511397"></a><a name="p1751673511397"></a>替换指定的ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p93571945888"><a name="p93571945888"></a><a name="p93571945888"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p127961184391"><a name="p127961184391"></a><a name="p127961184391"></a>updateConfigmaps</p>
</td>
</tr>
<tr id="row20277111853814"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p951693519394"><a name="p951693519394"></a><a name="p951693519394"></a>替换指定的DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p2357845683"><a name="p2357845683"></a><a name="p2357845683"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p979614863919"><a name="p979614863919"></a><a name="p979614863919"></a>updateDaemonsets</p>
</td>
</tr>
<tr id="row54522018183815"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1051610358398"><a name="p1051610358398"></a><a name="p1051610358398"></a>替换指定的Deployment</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1186104915816"><a name="p1186104915816"></a><a name="p1186104915816"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1679678103917"><a name="p1679678103917"></a><a name="p1679678103917"></a>updateDeployments</p>
</td>
</tr>
<tr id="row360941815385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1551653515395"><a name="p1551653515395"></a><a name="p1551653515395"></a>替换指定的Event</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p38619493818"><a name="p38619493818"></a><a name="p38619493818"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1679616820395"><a name="p1679616820395"></a><a name="p1679616820395"></a>updateEvents</p>
</td>
</tr>
<tr id="row16763111843812"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p10516133517390"><a name="p10516133517390"></a><a name="p10516133517390"></a>替换指定的Ingress</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p128619494817"><a name="p128619494817"></a><a name="p128619494817"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1679648203910"><a name="p1679648203910"></a><a name="p1679648203910"></a>updateIngresses</p>
</td>
</tr>
<tr id="row1992131833810"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p851683510393"><a name="p851683510393"></a><a name="p851683510393"></a>替换指定的Job</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p48619491817"><a name="p48619491817"></a><a name="p48619491817"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1379712820396"><a name="p1379712820396"></a><a name="p1379712820396"></a>updateJobs</p>
</td>
</tr>
<tr id="row1892121915386"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p55161635173912"><a name="p55161635173912"></a><a name="p55161635173912"></a>替换指定的Namespace</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p386134914810"><a name="p386134914810"></a><a name="p386134914810"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p2797188397"><a name="p2797188397"></a><a name="p2797188397"></a>updateNamespaces</p>
</td>
</tr>
<tr id="row12598191387"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1851783510393"><a name="p1851783510393"></a><a name="p1851783510393"></a>替换指定的Node</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p18861449280"><a name="p18861449280"></a><a name="p18861449280"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p10797184398"><a name="p10797184398"></a><a name="p10797184398"></a>updateNodes</p>
</td>
</tr>
<tr id="row245716197383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p135174357398"><a name="p135174357398"></a><a name="p135174357398"></a>替换指定的PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p48624912816"><a name="p48624912816"></a><a name="p48624912816"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p179748163912"><a name="p179748163912"></a><a name="p179748163912"></a>updatePersistentvolumeclaims</p>
</td>
</tr>
<tr id="row1464391963816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p205179354391"><a name="p205179354391"></a><a name="p205179354391"></a>替换指定的Pod</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1286349084"><a name="p1286349084"></a><a name="p1286349084"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p5797118153916"><a name="p5797118153916"></a><a name="p5797118153916"></a>updatePods</p>
</td>
</tr>
<tr id="row2840101919381"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p451710355392"><a name="p451710355392"></a><a name="p451710355392"></a>替换指定的Replicaset</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p28634910818"><a name="p28634910818"></a><a name="p28634910818"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p57978893918"><a name="p57978893918"></a><a name="p57978893918"></a>updateReplicasets</p>
</td>
</tr>
<tr id="row644102018385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1751793513395"><a name="p1751793513395"></a><a name="p1751793513395"></a>替换指定的ResourceQuota</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p069875419814"><a name="p069875419814"></a><a name="p069875419814"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p57978819395"><a name="p57978819395"></a><a name="p57978819395"></a>updateResourcequotas</p>
</td>
</tr>
<tr id="row1324482019385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1151716357397"><a name="p1151716357397"></a><a name="p1151716357397"></a>替换指定的Secret</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1069885412820"><a name="p1069885412820"></a><a name="p1069885412820"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p77972820393"><a name="p77972820393"></a><a name="p77972820393"></a>updateSecrets</p>
</td>
</tr>
<tr id="row1244119202386"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p19517183553910"><a name="p19517183553910"></a><a name="p19517183553910"></a>替换指定的Service</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p196984542081"><a name="p196984542081"></a><a name="p196984542081"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p167976817394"><a name="p167976817394"></a><a name="p167976817394"></a>updateServices</p>
</td>
</tr>
<tr id="row564613201384"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p2051713515397"><a name="p2051713515397"></a><a name="p2051713515397"></a>替换指定的Statefulset</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p26982541084"><a name="p26982541084"></a><a name="p26982541084"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p107973820392"><a name="p107973820392"></a><a name="p107973820392"></a>updateStatefulsets</p>
</td>
</tr>
<tr id="row0883172013813"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p851813523918"><a name="p851813523918"></a><a name="p851813523918"></a>替换指定的状态</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p069865411814"><a name="p069865411814"></a><a name="p069865411814"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p9797128143918"><a name="p9797128143918"></a><a name="p9797128143918"></a>updateStatus</p>
</td>
</tr>
<tr id="row10923218388"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p8518163593919"><a name="p8518163593919"></a><a name="p8518163593919"></a>上传组件模板</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1169835419811"><a name="p1169835419811"></a><a name="p1169835419811"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p279716816396"><a name="p279716816396"></a><a name="p279716816396"></a>uploadChart</p>
</td>
</tr>
<tr id="row16310621113819"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p165182350390"><a name="p165182350390"></a><a name="p165182350390"></a>更新组件模板</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p569895412810"><a name="p569895412810"></a><a name="p569895412810"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p97972853914"><a name="p97972853914"></a><a name="p97972853914"></a>updateChart</p>
</td>
</tr>
<tr id="row1540921183816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1751833516394"><a name="p1751833516394"></a><a name="p1751833516394"></a>删除组件模板</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p15698854787"><a name="p15698854787"></a><a name="p15698854787"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p879712816397"><a name="p879712816397"></a><a name="p879712816397"></a>deleteChart</p>
</td>
</tr>
<tr id="row912313616599"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1851853518391"><a name="p1851853518391"></a><a name="p1851853518391"></a>创建模板应用</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p06982541811"><a name="p06982541811"></a><a name="p06982541811"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p77971980392"><a name="p77971980392"></a><a name="p77971980392"></a>createRelease</p>
</td>
</tr>
<tr id="row161231136185917"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p15518163523911"><a name="p15518163523911"></a><a name="p15518163523911"></a>更新模板应用</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p41114318910"><a name="p41114318910"></a><a name="p41114318910"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p07971889398"><a name="p07971889398"></a><a name="p07971889398"></a>updateRelease</p>
</td>
</tr>
<tr id="row4919512193916"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1051813520394"><a name="p1051813520394"></a><a name="p1051813520394"></a>删除模板应用</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p18110316912"><a name="p18110316912"></a><a name="p18110316912"></a>cce</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p17919131216393"><a name="p17919131216393"></a><a name="p17919131216393"></a>deleteRelease</p>
</td>
</tr>
</tbody>
</table>

