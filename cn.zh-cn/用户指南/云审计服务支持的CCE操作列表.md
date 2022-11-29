# 云审计服务支持的CCE操作列表<a name="cce_10_0025"></a>

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
<tbody><tr id="row384725144914"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p13908102164920"><a name="p13908102164920"></a><a name="p13908102164920"></a>创建用户委托</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p15333419174616"><a name="p15333419174616"></a><a name="p15333419174616"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1993945965019"><a name="p1993945965019"></a><a name="p1993945965019"></a>createUserAgencies</p>
</td>
</tr>
<tr id="row1284895184910"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p199081221194919"><a name="p199081221194919"></a><a name="p199081221194919"></a>创建集群</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p433311984616"><a name="p433311984616"></a><a name="p433311984616"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p593905975012"><a name="p593905975012"></a><a name="p593905975012"></a>createCluster</p>
</td>
</tr>
<tr id="row188480514492"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p10908162113496"><a name="p10908162113496"></a><a name="p10908162113496"></a>创建包周期集群</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p3796730413"><a name="p3796730413"></a><a name="p3796730413"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p149391059145016"><a name="p149391059145016"></a><a name="p149391059145016"></a>createCluster/createPeriodicCluster</p>
</td>
</tr>
<tr id="row17848185114913"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1990920218494"><a name="p1990920218494"></a><a name="p1990920218494"></a>更新集群描述</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p147962302015"><a name="p147962302015"></a><a name="p147962302015"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p49391596502"><a name="p49391596502"></a><a name="p49391596502"></a>updateCluster</p>
</td>
</tr>
<tr id="row784805164917"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1090912210492"><a name="p1090912210492"></a><a name="p1090912210492"></a>升级集群</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p155208351618"><a name="p155208351618"></a><a name="p155208351618"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p29392059115015"><a name="p29392059115015"></a><a name="p29392059115015"></a>clusterUpgrade</p>
</td>
</tr>
<tr id="row18494524910"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p17909162174912"><a name="p17909162174912"></a><a name="p17909162174912"></a>删除集群</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p752019351819"><a name="p752019351819"></a><a name="p752019351819"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p139391059125010"><a name="p139391059125010"></a><a name="p139391059125010"></a>claimCluster/deleteCluster</p>
</td>
</tr>
<tr id="row9849205154915"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p12909122174919"><a name="p12909122174919"></a><a name="p12909122174919"></a>下载集群证书</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p12520133510112"><a name="p12520133510112"></a><a name="p12520133510112"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p3939105975020"><a name="p3939105975020"></a><a name="p3939105975020"></a>getClusterCertByUID</p>
</td>
</tr>
<tr id="row684915513497"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p390972118494"><a name="p390972118494"></a><a name="p390972118494"></a>绑定、解绑eip</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1952018351410"><a name="p1952018351410"></a><a name="p1952018351410"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1393995925016"><a name="p1393995925016"></a><a name="p1393995925016"></a>operateMasterEIP</p>
</td>
</tr>
<tr id="row2084918564916"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1490922117497"><a name="p1490922117497"></a><a name="p1490922117497"></a>集群休眠唤醒、节点纳管重置（V2）</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p186260487111"><a name="p186260487111"></a><a name="p186260487111"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p12939195912508"><a name="p12939195912508"></a><a name="p12939195912508"></a>operateCluster</p>
</td>
</tr>
<tr id="row82138711593"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p2909182110497"><a name="p2909182110497"></a><a name="p2909182110497"></a>集群休眠（V3）</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1462714816114"><a name="p1462714816114"></a><a name="p1462714816114"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p20939105925019"><a name="p20939105925019"></a><a name="p20939105925019"></a>hibernateCluster</p>
</td>
</tr>
<tr id="row2213779595"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p6909122124915"><a name="p6909122124915"></a><a name="p6909122124915"></a>集群唤醒（V3）</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p16271648711"><a name="p16271648711"></a><a name="p16271648711"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1693995916508"><a name="p1693995916508"></a><a name="p1693995916508"></a>awakeCluster</p>
</td>
</tr>
<tr id="row18491564913"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p11909152124916"><a name="p11909152124916"></a><a name="p11909152124916"></a>按需集群规格变更</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1062714481712"><a name="p1062714481712"></a><a name="p1062714481712"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p16939205918504"><a name="p16939205918504"></a><a name="p16939205918504"></a>resizeCluster</p>
</td>
</tr>
<tr id="row785015504914"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1909152194913"><a name="p1909152194913"></a><a name="p1909152194913"></a>包周期集群规格变更</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1622145319120"><a name="p1622145319120"></a><a name="p1622145319120"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p169391591507"><a name="p169391591507"></a><a name="p169391591507"></a>resizePeriodCluster</p>
</td>
</tr>
<tr id="row14159124616588"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p8909122117491"><a name="p8909122117491"></a><a name="p8909122117491"></a>修改集群配置</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1162245314111"><a name="p1162245314111"></a><a name="p1162245314111"></a>集群</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1393995915502"><a name="p1393995915502"></a><a name="p1393995915502"></a>updateConfiguration</p>
</td>
</tr>
<tr id="row108501254498"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p16909112184915"><a name="p16909112184915"></a><a name="p16909112184915"></a>创建节点池</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p380202410469"><a name="p380202410469"></a><a name="p380202410469"></a>节点池</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p194012597503"><a name="p194012597503"></a><a name="p194012597503"></a>createNodePool</p>
</td>
</tr>
<tr id="row1085013554914"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p15909102144912"><a name="p15909102144912"></a><a name="p15909102144912"></a>更新节点池</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1780212413468"><a name="p1780212413468"></a><a name="p1780212413468"></a>节点池</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p49407593507"><a name="p49407593507"></a><a name="p49407593507"></a>updateNodePool</p>
</td>
</tr>
<tr id="row0114164016599"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p119091621124910"><a name="p119091621124910"></a><a name="p119091621124910"></a>删除节点池</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p177971572218"><a name="p177971572218"></a><a name="p177971572218"></a>节点池</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p129404598501"><a name="p129404598501"></a><a name="p129404598501"></a>claimNodePool</p>
</td>
</tr>
<tr id="row785017564910"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p3909162104914"><a name="p3909162104914"></a><a name="p3909162104914"></a>迁移节点池</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p9798127421"><a name="p9798127421"></a><a name="p9798127421"></a>节点池</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p15940125912508"><a name="p15940125912508"></a><a name="p15940125912508"></a>migrateNodepool</p>
</td>
</tr>
<tr id="row2965135415912"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1790902112496"><a name="p1790902112496"></a><a name="p1790902112496"></a>修改节点池配置</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p13334131994612"><a name="p13334131994612"></a><a name="p13334131994612"></a>节点池</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p179399594508"><a name="p179399594508"></a><a name="p179399594508"></a>updateConfiguration</p>
</td>
</tr>
<tr id="row158507514494"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p13909112112490"><a name="p13909112112490"></a><a name="p13909112112490"></a>创建节点</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p13334219144613"><a name="p13334219144613"></a><a name="p13334219144613"></a>节点</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p8939859205016"><a name="p8939859205016"></a><a name="p8939859205016"></a>createNode</p>
</td>
</tr>
<tr id="row1485010554910"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p790932110496"><a name="p790932110496"></a><a name="p790932110496"></a>创建包周期节点</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1733421974614"><a name="p1733421974614"></a><a name="p1733421974614"></a>节点</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1393965912502"><a name="p1393965912502"></a><a name="p1393965912502"></a>createPeriodNode</p>
</td>
</tr>
<tr id="row128501050492"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1390982110492"><a name="p1390982110492"></a><a name="p1390982110492"></a>删除集群下所有节点</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1547962610210"><a name="p1547962610210"></a><a name="p1547962610210"></a>节点</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p3940135919502"><a name="p3940135919502"></a><a name="p3940135919502"></a>deleteAllHosts</p>
</td>
</tr>
<tr id="row285020515496"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p8909122120498"><a name="p8909122120498"></a><a name="p8909122120498"></a>删除单个节点</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p15479126929"><a name="p15479126929"></a><a name="p15479126929"></a>节点</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p209404590505"><a name="p209404590505"></a><a name="p209404590505"></a>deleteOneHost/claimOneHost</p>
</td>
</tr>
<tr id="row88504534919"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1690942194917"><a name="p1690942194917"></a><a name="p1690942194917"></a>更新节点描述</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1930214311225"><a name="p1930214311225"></a><a name="p1930214311225"></a>节点</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p7940959125011"><a name="p7940959125011"></a><a name="p7940959125011"></a>updateNode</p>
</td>
</tr>
<tr id="row785120513499"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p15909142111496"><a name="p15909142111496"></a><a name="p15909142111496"></a>创建插件实例</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p9302931825"><a name="p9302931825"></a><a name="p9302931825"></a>插件实例</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p6940659195015"><a name="p6940659195015"></a><a name="p6940659195015"></a>createAddonInstance</p>
</td>
</tr>
<tr id="row58431159124518"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1390910213499"><a name="p1390910213499"></a><a name="p1390910213499"></a>删除插件实例</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1990710595494"><a name="p1990710595494"></a><a name="p1990710595494"></a>插件实例</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p694012594504"><a name="p694012594504"></a><a name="p694012594504"></a>deleteAddonInstance</p>
</td>
</tr>
<tr id="row19844559124519"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1990932114918"><a name="p1990932114918"></a><a name="p1990932114918"></a>上传模板</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p7532155174914"><a name="p7532155174914"></a><a name="p7532155174914"></a>模板</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1940135915010"><a name="p1940135915010"></a><a name="p1940135915010"></a>uploadChart</p>
</td>
</tr>
<tr id="row48441859124517"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1890972104914"><a name="p1890972104914"></a><a name="p1890972104914"></a>更新模板</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p16532855174914"><a name="p16532855174914"></a><a name="p16532855174914"></a>模板</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p179401598508"><a name="p179401598508"></a><a name="p179401598508"></a>updateChart</p>
</td>
</tr>
<tr id="row884417597459"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p190912119493"><a name="p190912119493"></a><a name="p190912119493"></a>删除模板</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p171112818311"><a name="p171112818311"></a><a name="p171112818311"></a>模板</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p209401159165020"><a name="p209401159165020"></a><a name="p209401159165020"></a>deleteChart</p>
</td>
</tr>
<tr id="row118441759144514"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p4910122114496"><a name="p4910122114496"></a><a name="p4910122114496"></a>创建模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p164601332936"><a name="p164601332936"></a><a name="p164601332936"></a>模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p12940115916506"><a name="p12940115916506"></a><a name="p12940115916506"></a>createRelease</p>
</td>
</tr>
<tr id="row17844195912458"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p0910162118492"><a name="p0910162118492"></a><a name="p0910162118492"></a>升级模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1846010326310"><a name="p1846010326310"></a><a name="p1846010326310"></a>模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p29401859185012"><a name="p29401859185012"></a><a name="p29401859185012"></a>updateRelease</p>
</td>
</tr>
<tr id="row13844175934515"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p3910182164916"><a name="p3910182164916"></a><a name="p3910182164916"></a>删除模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p135329556494"><a name="p135329556494"></a><a name="p135329556494"></a>模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p18940125919509"><a name="p18940125919509"></a><a name="p18940125919509"></a>deleteRelease</p>
</td>
</tr>
<tr id="row16450535103817"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1351243543918"><a name="p1351243543918"></a><a name="p1351243543918"></a>创建ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p14476171817820"><a name="p14476171817820"></a><a name="p14476171817820"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p14794158123914"><a name="p14794158123914"></a><a name="p14794158123914"></a>createConfigmaps</p>
</td>
</tr>
<tr id="row107342035123814"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p85121835133911"><a name="p85121835133911"></a><a name="p85121835133911"></a>创建DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1831114214817"><a name="p1831114214817"></a><a name="p1831114214817"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p179458103919"><a name="p179458103919"></a><a name="p179458103919"></a>createDaemonsets</p>
</td>
</tr>
<tr id="row189915354383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p85121535103919"><a name="p85121535103919"></a><a name="p85121535103919"></a>创建Deployment</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p126142345"><a name="p126142345"></a><a name="p126142345"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p77941781394"><a name="p77941781394"></a><a name="p77941781394"></a>createDeployments</p>
</td>
</tr>
<tr id="row11247123618381"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p451213352396"><a name="p451213352396"></a><a name="p451213352396"></a>创建Event</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p152615214410"><a name="p152615214410"></a><a name="p152615214410"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p17794188173919"><a name="p17794188173919"></a><a name="p17794188173919"></a>createEvents</p>
</td>
</tr>
<tr id="row13528183623818"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p251210351397"><a name="p251210351397"></a><a name="p251210351397"></a>创建Ingress</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p184187315412"><a name="p184187315412"></a><a name="p184187315412"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p97948863919"><a name="p97948863919"></a><a name="p97948863919"></a>createIngresses</p>
</td>
</tr>
<tr id="row138443361388"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p35131235103910"><a name="p35131235103910"></a><a name="p35131235103910"></a>创建Job</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p9418731347"><a name="p9418731347"></a><a name="p9418731347"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p3794883397"><a name="p3794883397"></a><a name="p3794883397"></a>createJobs</p>
</td>
</tr>
<tr id="row11196173713381"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1051363523919"><a name="p1051363523919"></a><a name="p1051363523919"></a>创建namespace</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p12304126246"><a name="p12304126246"></a><a name="p12304126246"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p147941873920"><a name="p147941873920"></a><a name="p147941873920"></a>createNamespaces</p>
</td>
</tr>
<tr id="row1547923713817"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p151316356394"><a name="p151316356394"></a><a name="p151316356394"></a>创建Node</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p4304366410"><a name="p4304366410"></a><a name="p4304366410"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p47958813910"><a name="p47958813910"></a><a name="p47958813910"></a>createNodes</p>
</td>
</tr>
<tr id="row1806137163818"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1151310357393"><a name="p1151310357393"></a><a name="p1151310357393"></a>创建PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p23046620416"><a name="p23046620416"></a><a name="p23046620416"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p16795128113912"><a name="p16795128113912"></a><a name="p16795128113912"></a>createPersistentvolumeclaims</p>
</td>
</tr>
<tr id="row15143838133818"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1451343543916"><a name="p1451343543916"></a><a name="p1451343543916"></a>创建Pod</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p19304664419"><a name="p19304664419"></a><a name="p19304664419"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1079513812399"><a name="p1079513812399"></a><a name="p1079513812399"></a>createPods</p>
</td>
</tr>
<tr id="row14502038193811"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p5513935123919"><a name="p5513935123919"></a><a name="p5513935123919"></a>创建ReplicaSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1330413612410"><a name="p1330413612410"></a><a name="p1330413612410"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p197955843913"><a name="p197955843913"></a><a name="p197955843913"></a>createReplicasets</p>
</td>
</tr>
<tr id="row1980053883816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p75138353395"><a name="p75138353395"></a><a name="p75138353395"></a>创建ResourceQuota</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p193041261843"><a name="p193041261843"></a><a name="p193041261843"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p197958863913"><a name="p197958863913"></a><a name="p197958863913"></a>createResourcequotas</p>
</td>
</tr>
<tr id="row11151173923816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p10513835193915"><a name="p10513835193915"></a><a name="p10513835193915"></a>创建密钥</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p198581310146"><a name="p198581310146"></a><a name="p198581310146"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p37958833915"><a name="p37958833915"></a><a name="p37958833915"></a>createSecrets</p>
</td>
</tr>
<tr id="row1950073943815"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p4514835193915"><a name="p4514835193915"></a><a name="p4514835193915"></a>创建服务</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p18859121011410"><a name="p18859121011410"></a><a name="p18859121011410"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1679519813919"><a name="p1679519813919"></a><a name="p1679519813919"></a>createServices</p>
</td>
</tr>
<tr id="row118871714163811"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p4514935153910"><a name="p4514935153910"></a><a name="p4514935153910"></a>创建StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p48590101244"><a name="p48590101244"></a><a name="p48590101244"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p779514820397"><a name="p779514820397"></a><a name="p779514820397"></a>createStatefulsets</p>
</td>
</tr>
<tr id="row11704159385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p13514133513392"><a name="p13514133513392"></a><a name="p13514133513392"></a>创建卷</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p138596101745"><a name="p138596101745"></a><a name="p138596101745"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p127951887398"><a name="p127951887398"></a><a name="p127951887398"></a>createVolumes</p>
</td>
</tr>
<tr id="row6236161516385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p175141335173920"><a name="p175141335173920"></a><a name="p175141335173920"></a>删除ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1485914101947"><a name="p1485914101947"></a><a name="p1485914101947"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p117959818394"><a name="p117959818394"></a><a name="p117959818394"></a>deleteConfigmaps</p>
</td>
</tr>
<tr id="row64003156383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p45141635123918"><a name="p45141635123918"></a><a name="p45141635123918"></a>删除DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1785911010413"><a name="p1785911010413"></a><a name="p1785911010413"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p97951280398"><a name="p97951280398"></a><a name="p97951280398"></a>deleteDaemonsets</p>
</td>
</tr>
<tr id="row8588151520383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p45149357396"><a name="p45149357396"></a><a name="p45149357396"></a>删除Deployment</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p16859191014418"><a name="p16859191014418"></a><a name="p16859191014418"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p47951889391"><a name="p47951889391"></a><a name="p47951889391"></a>deleteDeployments</p>
</td>
</tr>
<tr id="row976691573816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p145141535183916"><a name="p145141535183916"></a><a name="p145141535183916"></a>删除Event</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p5859131013417"><a name="p5859131013417"></a><a name="p5859131013417"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p127951786399"><a name="p127951786399"></a><a name="p127951786399"></a>deleteEvents</p>
</td>
</tr>
<tr id="row1093116152383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p351414356394"><a name="p351414356394"></a><a name="p351414356394"></a>删除Ingress</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1885913101146"><a name="p1885913101146"></a><a name="p1885913101146"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p117951580397"><a name="p117951580397"></a><a name="p117951580397"></a>deleteIngresses</p>
</td>
</tr>
<tr id="row8952162389"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p185141935123913"><a name="p185141935123913"></a><a name="p185141935123913"></a>删除Job</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p68590102411"><a name="p68590102411"></a><a name="p68590102411"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p77966815390"><a name="p77966815390"></a><a name="p77966815390"></a>deleteJobs</p>
</td>
</tr>
<tr id="row627551663812"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1151417358393"><a name="p1151417358393"></a><a name="p1151417358393"></a>删除Namespace</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1985920103415"><a name="p1985920103415"></a><a name="p1985920103415"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1079648183911"><a name="p1079648183911"></a><a name="p1079648183911"></a>deleteNamespaces</p>
</td>
</tr>
<tr id="row24561416203810"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p2051523520395"><a name="p2051523520395"></a><a name="p2051523520395"></a>删除Node</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1859111018414"><a name="p1859111018414"></a><a name="p1859111018414"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1579614813394"><a name="p1579614813394"></a><a name="p1579614813394"></a>deleteNodes</p>
</td>
</tr>
<tr id="row86221816163818"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p15151135103918"><a name="p15151135103918"></a><a name="p15151135103918"></a>删除Pod</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p166639124418"><a name="p166639124418"></a><a name="p166639124418"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1379668193911"><a name="p1379668193911"></a><a name="p1379668193911"></a>deletePods</p>
</td>
</tr>
<tr id="row1779151617386"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1751583512391"><a name="p1751583512391"></a><a name="p1751583512391"></a>删除ReplicaSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1866361217412"><a name="p1866361217412"></a><a name="p1866361217412"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p20796686397"><a name="p20796686397"></a><a name="p20796686397"></a>deleteReplicasets</p>
</td>
</tr>
<tr id="row1995721663817"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p14515143503916"><a name="p14515143503916"></a><a name="p14515143503916"></a>删除ResourceQuota</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p566421215420"><a name="p566421215420"></a><a name="p566421215420"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p107966817394"><a name="p107966817394"></a><a name="p107966817394"></a>deleteResourcequotas</p>
</td>
</tr>
<tr id="row1412191773811"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p251510357397"><a name="p251510357397"></a><a name="p251510357397"></a>删除Secret</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p266461212419"><a name="p266461212419"></a><a name="p266461212419"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p879638113910"><a name="p879638113910"></a><a name="p879638113910"></a>deleteSecrets</p>
</td>
</tr>
<tr id="row7664121717383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p451543520393"><a name="p451543520393"></a><a name="p451543520393"></a>删除Service</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p0664151216418"><a name="p0664151216418"></a><a name="p0664151216418"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p13796108103917"><a name="p13796108103917"></a><a name="p13796108103917"></a>deleteServices</p>
</td>
</tr>
<tr id="row1079231717386"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p4515113518397"><a name="p4515113518397"></a><a name="p4515113518397"></a>删除StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p466415122412"><a name="p466415122412"></a><a name="p466415122412"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p107964812397"><a name="p107964812397"></a><a name="p107964812397"></a>deleteStatefulsets</p>
</td>
</tr>
<tr id="row69931317173813"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p135151335143920"><a name="p135151335143920"></a><a name="p135151335143920"></a>删除卷</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p86648121546"><a name="p86648121546"></a><a name="p86648121546"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p127963811395"><a name="p127963811395"></a><a name="p127963811395"></a>deleteVolumes</p>
</td>
</tr>
<tr id="row18139518193810"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1751673511397"><a name="p1751673511397"></a><a name="p1751673511397"></a>替换指定的ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p176641312140"><a name="p176641312140"></a><a name="p176641312140"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p127961184391"><a name="p127961184391"></a><a name="p127961184391"></a>updateConfigmaps</p>
</td>
</tr>
<tr id="row20277111853814"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p951693519394"><a name="p951693519394"></a><a name="p951693519394"></a>替换指定的DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p126642125411"><a name="p126642125411"></a><a name="p126642125411"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p979614863919"><a name="p979614863919"></a><a name="p979614863919"></a>updateDaemonsets</p>
</td>
</tr>
<tr id="row54522018183815"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1051610358398"><a name="p1051610358398"></a><a name="p1051610358398"></a>替换指定的Deployment</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p56647124411"><a name="p56647124411"></a><a name="p56647124411"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1679678103917"><a name="p1679678103917"></a><a name="p1679678103917"></a>updateDeployments</p>
</td>
</tr>
<tr id="row360941815385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1551653515395"><a name="p1551653515395"></a><a name="p1551653515395"></a>替换指定的Event</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1166461210411"><a name="p1166461210411"></a><a name="p1166461210411"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1679616820395"><a name="p1679616820395"></a><a name="p1679616820395"></a>updateEvents</p>
</td>
</tr>
<tr id="row16763111843812"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p10516133517390"><a name="p10516133517390"></a><a name="p10516133517390"></a>替换指定的Ingress</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p17664151210410"><a name="p17664151210410"></a><a name="p17664151210410"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1679648203910"><a name="p1679648203910"></a><a name="p1679648203910"></a>updateIngresses</p>
</td>
</tr>
<tr id="row1992131833810"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p851683510393"><a name="p851683510393"></a><a name="p851683510393"></a>替换指定的Job</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p9820181413410"><a name="p9820181413410"></a><a name="p9820181413410"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p1379712820396"><a name="p1379712820396"></a><a name="p1379712820396"></a>updateJobs</p>
</td>
</tr>
<tr id="row1892121915386"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p55161635173912"><a name="p55161635173912"></a><a name="p55161635173912"></a>替换指定的Namespace</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1382017141543"><a name="p1382017141543"></a><a name="p1382017141543"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p2797188397"><a name="p2797188397"></a><a name="p2797188397"></a>updateNamespaces</p>
</td>
</tr>
<tr id="row12598191387"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1851783510393"><a name="p1851783510393"></a><a name="p1851783510393"></a>替换指定的Node</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p982018146411"><a name="p982018146411"></a><a name="p982018146411"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p10797184398"><a name="p10797184398"></a><a name="p10797184398"></a>updateNodes</p>
</td>
</tr>
<tr id="row245716197383"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p135174357398"><a name="p135174357398"></a><a name="p135174357398"></a>替换指定的PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p158205149420"><a name="p158205149420"></a><a name="p158205149420"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p179748163912"><a name="p179748163912"></a><a name="p179748163912"></a>updatePersistentvolumeclaims</p>
</td>
</tr>
<tr id="row1464391963816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p205179354391"><a name="p205179354391"></a><a name="p205179354391"></a>替换指定的Pod</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p10821141419419"><a name="p10821141419419"></a><a name="p10821141419419"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p5797118153916"><a name="p5797118153916"></a><a name="p5797118153916"></a>updatePods</p>
</td>
</tr>
<tr id="row2840101919381"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p451710355392"><a name="p451710355392"></a><a name="p451710355392"></a>替换指定的Replicaset</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p88215148413"><a name="p88215148413"></a><a name="p88215148413"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p57978893918"><a name="p57978893918"></a><a name="p57978893918"></a>updateReplicasets</p>
</td>
</tr>
<tr id="row644102018385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1751793513395"><a name="p1751793513395"></a><a name="p1751793513395"></a>替换指定的ResourceQuota</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1882118141541"><a name="p1882118141541"></a><a name="p1882118141541"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p57978819395"><a name="p57978819395"></a><a name="p57978819395"></a>updateResourcequotas</p>
</td>
</tr>
<tr id="row1324482019385"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1151716357397"><a name="p1151716357397"></a><a name="p1151716357397"></a>替换指定的Secret</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p18214144415"><a name="p18214144415"></a><a name="p18214144415"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p77972820393"><a name="p77972820393"></a><a name="p77972820393"></a>updateSecrets</p>
</td>
</tr>
<tr id="row1244119202386"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p19517183553910"><a name="p19517183553910"></a><a name="p19517183553910"></a>替换指定的Service</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p11821171414418"><a name="p11821171414418"></a><a name="p11821171414418"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p167976817394"><a name="p167976817394"></a><a name="p167976817394"></a>updateServices</p>
</td>
</tr>
<tr id="row564613201384"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p2051713515397"><a name="p2051713515397"></a><a name="p2051713515397"></a>替换指定的Statefulset</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p082117144418"><a name="p082117144418"></a><a name="p082117144418"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p107973820392"><a name="p107973820392"></a><a name="p107973820392"></a>updateStatefulsets</p>
</td>
</tr>
<tr id="row0883172013813"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p851813523918"><a name="p851813523918"></a><a name="p851813523918"></a>替换指定的状态</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1182110141544"><a name="p1182110141544"></a><a name="p1182110141544"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p9797128143918"><a name="p9797128143918"></a><a name="p9797128143918"></a>updateStatus</p>
</td>
</tr>
<tr id="row10923218388"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p8518163593919"><a name="p8518163593919"></a><a name="p8518163593919"></a>上传组件模板</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p1582181415417"><a name="p1582181415417"></a><a name="p1582181415417"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p279716816396"><a name="p279716816396"></a><a name="p279716816396"></a>uploadChart</p>
</td>
</tr>
<tr id="row16310621113819"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p165182350390"><a name="p165182350390"></a><a name="p165182350390"></a>更新组件模板</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p83327201445"><a name="p83327201445"></a><a name="p83327201445"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p97972853914"><a name="p97972853914"></a><a name="p97972853914"></a>updateChart</p>
</td>
</tr>
<tr id="row1540921183816"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1751833516394"><a name="p1751833516394"></a><a name="p1751833516394"></a>删除组件模板</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p733262011411"><a name="p733262011411"></a><a name="p733262011411"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p879712816397"><a name="p879712816397"></a><a name="p879712816397"></a>deleteChart</p>
</td>
</tr>
<tr id="row912313616599"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1851853518391"><a name="p1851853518391"></a><a name="p1851853518391"></a>创建模板应用</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p153321220948"><a name="p153321220948"></a><a name="p153321220948"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p77971980392"><a name="p77971980392"></a><a name="p77971980392"></a>createRelease</p>
</td>
</tr>
<tr id="row161231136185917"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p15518163523911"><a name="p15518163523911"></a><a name="p15518163523911"></a>更新模板应用</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p733210201411"><a name="p733210201411"></a><a name="p733210201411"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p07971889398"><a name="p07971889398"></a><a name="p07971889398"></a>updateRelease</p>
</td>
</tr>
<tr id="row4919512193916"><td class="cellrowborder" valign="top" width="28.37%" headers="mcps1.2.4.1.1 "><p id="p1051813520394"><a name="p1051813520394"></a><a name="p1051813520394"></a>删除模板应用</p>
</td>
<td class="cellrowborder" valign="top" width="25.230000000000004%" headers="mcps1.2.4.1.2 "><p id="p533222017416"><a name="p533222017416"></a><a name="p533222017416"></a>K8S资源</p>
</td>
<td class="cellrowborder" valign="top" width="46.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p17919131216393"><a name="p17919131216393"></a><a name="p17919131216393"></a>deleteRelease</p>
</td>
</tr>
</tbody>
</table>

