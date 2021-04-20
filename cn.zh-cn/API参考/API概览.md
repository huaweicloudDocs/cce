# API概览<a name="cce_02_0098"></a>

云容器引擎所提供的接口分为CCE接口与Kubernetes原生接口。通过配合使用CCE接口和Kubernetes原生接口，您可以完整的使用云容器引擎的所有功能，包括创建集群和节点，使用Kubernetes接口创建容器工作负载，使用CCE接口监控工作负载的使用数据等。

<a name="table42321788145910"></a>
<table><thead align="left"><tr id="row23622030145910"><th class="cellrowborder" valign="top" width="19.8%" id="mcps1.1.4.1.1"><p id="p29998296145910"><a name="p29998296145910"></a><a name="p29998296145910"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="21.78%" id="mcps1.1.4.1.2"><p id="p11535905145910"><a name="p11535905145910"></a><a name="p11535905145910"></a>子类型</p>
</th>
<th class="cellrowborder" valign="top" width="58.42%" id="mcps1.1.4.1.3"><p id="p26159182145910"><a name="p26159182145910"></a><a name="p26159182145910"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row46758134145910"><td class="cellrowborder" rowspan="3" valign="top" width="19.8%" headers="mcps1.1.4.1.1 "><p id="p1772819209011"><a name="p1772819209011"></a><a name="p1772819209011"></a>CCE接口</p>
</td>
<td class="cellrowborder" valign="top" width="21.78%" headers="mcps1.1.4.1.2 "><p id="p19868352442"><a name="p19868352442"></a><a name="p19868352442"></a><a href="集群管理.md">集群管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="58.42%" headers="mcps1.1.4.1.3 "><p id="p44662802145910"><a name="p44662802145910"></a><a name="p44662802145910"></a>集群和节点管理接口，包括创建、删除集群和节点的接口等。</p>
<p id="p3384875145910"><a name="p3384875145910"></a><a name="p3384875145910"></a>通过这些接口，您可以创建集群、为集群添加节点、获取已创建集群和节点的信息。</p>
<div class="notice" id="note613187134219"><a name="note613187134219"></a><a name="note613187134219"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><p id="p16761103512440"><a name="p16761103512440"></a><a name="p16761103512440"></a>在创建、删除、扩容和缩容集群的操作中，请不要在统一身份认证服务（IAM）中执行权限变更或修改的操作，可能会导致创建、删除、扩容和缩容集群执行失败。</p>
</div></div>
</td>
</tr>
<tr id="row85396435151"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7970931652"><a name="p7970931652"></a><a name="p7970931652"></a><a href="存储管理.md">存储管理</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p854044313156"><a name="p854044313156"></a><a name="p854044313156"></a>存储管理接口，包括PersistentVolumeClaim、PersistentVolume的创建、删除。</p>
</td>
</tr>
<tr id="row17928112575213"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p14435181417519"><a name="p14435181417519"></a><a name="p14435181417519"></a><a href="插件管理.md">插件管理</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1492918251523"><a name="p1492918251523"></a><a name="p1492918251523"></a>插件管理接口，包括AddonTemplates的查询，AddonInstance的创建、更新、删除和获取。</p>
</td>
</tr>
<tr id="row33762552145910"><td class="cellrowborder" rowspan="22" valign="top" width="19.8%" headers="mcps1.1.4.1.1 "><p id="p11594550145910"><a name="p11594550145910"></a><a name="p11594550145910"></a>Kubernetes原生接口</p>
</td>
<td class="cellrowborder" valign="top" width="21.78%" headers="mcps1.1.4.1.2 "><p id="p5699090519278"><a name="p5699090519278"></a><a name="p5699090519278"></a><a href="Node.md">Node</a></p>
</td>
<td class="cellrowborder" valign="top" width="58.42%" headers="mcps1.1.4.1.3 "><p id="p4572971519278"><a name="p4572971519278"></a><a name="p4572971519278"></a>Node对象管理接口，包括Node对象的获取，查询和更新。</p>
<div class="note" id="note18462175954313"><a name="note18462175954313"></a><a name="note18462175954313"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p18866114810316"><a name="p18866114810316"></a><a name="p18866114810316"></a>CCE仅支持使用<a href="集群管理.md">集群管理</a>中的接口创建、删除节点，不能使用Kubernetes原生接口来创建、删除节点。</p>
</div></div>
</td>
</tr>
<tr id="row127941236152711"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p44725375145910"><a name="p44725375145910"></a><a name="p44725375145910"></a><a href="Namespace.md">Namespace</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p66449515145910"><a name="p66449515145910"></a><a name="p66449515145910"></a>Namespace对象管理接口，包括Namespace对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row124231810172813"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1542341010280"><a name="p1542341010280"></a><a name="p1542341010280"></a><a href="Resourcequotas.md">Resourcequotas</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p942381092810"><a name="p942381092810"></a><a name="p942381092810"></a>ResourceQuotas资源配额接口，包括查询接口。</p>
</td>
</tr>
<tr id="row205721428203112"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p49554995145910"><a name="p49554995145910"></a><a name="p49554995145910"></a><a href="Pod.md">Pod</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p26187931145910"><a name="p26187931145910"></a><a name="p26187931145910"></a>Pod对象管理接口，包括Pod对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row19515163917311"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p379336831112"><a name="p379336831112"></a><a name="p379336831112"></a><a href="Deployment.md">Deployment</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p48033961112"><a name="p48033961112"></a><a name="p48033961112"></a>Deployment对象管理接口，包括Deployment对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row7980195320316"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1267985011044"><a name="p1267985011044"></a><a name="p1267985011044"></a><a href="StatefulSet.md">Statefulset</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p4969678411044"><a name="p4969678411044"></a><a name="p4969678411044"></a>Statefulset对象管理接口，包括Statefulset对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row1949954320"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p4671625719274"><a name="p4671625719274"></a><a name="p4671625719274"></a><a href="DaemonSet.md">Daemonset</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p6664593719274"><a name="p6664593719274"></a><a name="p6664593719274"></a>Daemonset对象管理接口，包括Daemonset对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row10260164310320"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p3094168219276"><a name="p3094168219276"></a><a name="p3094168219276"></a><a href="Job.md">Job</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p3689587219276"><a name="p3689587219276"></a><a name="p3689587219276"></a>Job对象管理接口，包括Job对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row152602043143211"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p995412315275"><a name="p995412315275"></a><a name="p995412315275"></a><a href="CronJob.md">CronJob</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1195415319277"><a name="p1195415319277"></a><a name="p1195415319277"></a>CronJob对象管理接口，包括CronJob对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row1419213219339"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p6028906019279"><a name="p6028906019279"></a><a name="p6028906019279"></a><a href="ReplicaSet.md">ReplicaSet</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p5915636019279"><a name="p5915636019279"></a><a name="p5915636019279"></a>ReplicaSet对象的查询。</p>
</td>
</tr>
<tr id="row10957421145910"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p30771534145910"><a name="p30771534145910"></a><a name="p30771534145910"></a><a href="ReplicationController.md">ReplicationController</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p61441166145910"><a name="p61441166145910"></a><a name="p61441166145910"></a>ReplicationController对象管理接口，包括ReplicationController对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row45945772145910"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p46200155145910"><a name="p46200155145910"></a><a name="p46200155145910"></a><a href="Endpoints.md">Endpoints</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p60436584145910"><a name="p60436584145910"></a><a name="p60436584145910"></a>Endpoint对象管理接口，包括Endpoint对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row2032595553314"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p28882047145910"><a name="p28882047145910"></a><a name="p28882047145910"></a><a href="Service.md">Service</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p27305587145910"><a name="p27305587145910"></a><a name="p27305587145910"></a>Service对象管理接口，包括Service对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row1643488143411"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p191324141413"><a name="p191324141413"></a><a name="p191324141413"></a><a href="Ingress.md">Ingress</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1991324101413"><a name="p1991324101413"></a><a name="p1991324101413"></a>Ingress对象管理接口，包括Ingress对象的创建，更新，删除等接口。</p>
</td>
</tr>
<tr id="row17767622163414"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p15974819191220"><a name="p15974819191220"></a><a name="p15974819191220"></a><a href="NetworkPolicy.md">NetworkPolicy</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p7975141920121"><a name="p7975141920121"></a><a name="p7975141920121"></a>NetworkPolicy对象管理接口，包括NetworkPolicy对象的创建，更新，删除等接口。</p>
</td>
</tr>
<tr id="row14719244145910"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p6643479711057"><a name="p6643479711057"></a><a name="p6643479711057"></a><a href="PersistentVolume.md">PersistentVolume</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p4547635511057"><a name="p4547635511057"></a><a name="p4547635511057"></a>PersistentVolume对象管理接口，包括PersistentVolume对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row16808163913413"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p4151121811057"><a name="p4151121811057"></a><a name="p4151121811057"></a><a href="PersistentVolumeClaim.md">PersistentVolumeClaim</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p6268924811057"><a name="p6268924811057"></a><a name="p6268924811057"></a>PersistentVolumeClaim对象管理接口，包括PersistentVolumeClaim对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row785542119277"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p2163363219277"><a name="p2163363219277"></a><a name="p2163363219277"></a><a href="ConfigMap.md">ConfigMap</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p3197595019277"><a name="p3197595019277"></a><a name="p3197595019277"></a>ConfigMap对象管理接口，包括ConfigMap对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row4534259183411"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p10599255145910"><a name="p10599255145910"></a><a name="p10599255145910"></a><a href="Secret.md">Secret</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p44056569145910"><a name="p44056569145910"></a><a name="p44056569145910"></a>Secret对象管理接口，包括Sercret对象的创建，查询，修改，删除等接口。</p>
</td>
</tr>
<tr id="row0570056103410"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p18959115215129"><a name="p18959115215129"></a><a name="p18959115215129"></a><a href="RBAC.md">RBAC</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1795945216128"><a name="p1795945216128"></a><a name="p1795945216128"></a>通过权限设置可以让不同的用户或用户组拥有操作不同Kubernetes资源的权限。</p>
</td>
</tr>
<tr id="row9621141015358"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p22396136193538"><a name="p22396136193538"></a><a name="p22396136193538"></a><a href="API-groups.md">API groups</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p65344911193538"><a name="p65344911193538"></a><a name="p65344911193538"></a>API group对象管理接口，包括列出API group和APIVersion。</p>
</td>
</tr>
<tr id="row65712929193538"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p32547626193538"><a name="p32547626193538"></a><a name="p32547626193538"></a><a href="Event.md">Event</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p35799742193538"><a name="p35799742193538"></a><a name="p35799742193538"></a>Event对象管理的查询。</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：** 
>当前版本调用Kubernetes接口不支持HTTP长链接。

## 集群管理<a name="section1921916017577"></a>

**表 1**  集群管理

<a name="table20874152514599"></a>
<table><thead align="left"><tr id="row1875112565915"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p387562517593"><a name="p387562517593"></a><a name="p387562517593"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p941484217597"><a name="p941484217597"></a><a name="p941484217597"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row0876112555912"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p98764259594"><a name="p98764259594"></a><a name="p98764259594"></a><a href="创建集群.md">创建集群</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1487662565913"><a name="p1487662565913"></a><a name="p1487662565913"></a>创建一个空集群（即只有控制节点Master，没有工作节点Node）。</p>
</td>
</tr>
<tr id="row735511161162"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p43562161363"><a name="p43562161363"></a><a name="p43562161363"></a><a href="获取指定的集群.md">获取指定的集群</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p4356151610612"><a name="p4356151610612"></a><a name="p4356151610612"></a>获取指定集群的详细信息。</p>
</td>
</tr>
<tr id="row10521820763"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1952116203619"><a name="p1952116203619"></a><a name="p1952116203619"></a><a href="获取指定项目下的集群.md">获取指定项目下的集群</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p145223201965"><a name="p145223201965"></a><a name="p145223201965"></a>获取指定项目下所有集群的详细信息。</p>
</td>
</tr>
<tr id="row1915318211161"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1015392118613"><a name="p1015392118613"></a><a name="p1015392118613"></a><a href="更新指定的集群.md">更新指定的集群</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p515310211467"><a name="p515310211467"></a><a name="p515310211467"></a>更新指定的集群。</p>
</td>
</tr>
<tr id="row651019219614"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p105101421263"><a name="p105101421263"></a><a name="p105101421263"></a><a href="删除集群.md">删除集群</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9510182110610"><a name="p9510182110610"></a><a name="p9510182110610"></a>删除一个指定的集群。</p>
</td>
</tr>
<tr id="row433972018146"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p733917204144"><a name="p733917204144"></a><a name="p733917204144"></a><a href="集群休眠.md">集群休眠</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p5340122016140"><a name="p5340122016140"></a><a name="p5340122016140"></a>休眠一个指定的集群。</p>
</td>
</tr>
<tr id="row5413123710145"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p441393717143"><a name="p441393717143"></a><a name="p441393717143"></a><a href="集群唤醒.md">集群唤醒</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18413163718147"><a name="p18413163718147"></a><a name="p18413163718147"></a>唤醒一个指定的已休眠集群。</p>
</td>
</tr>
<tr id="row1268164714123"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p18430134931216"><a name="p18430134931216"></a><a name="p18430134931216"></a><a href="集群唤醒.md">获取集群证书</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p194305493127"><a name="p194305493127"></a><a name="p194305493127"></a><span>获取指定集群的证书信息。</span></p>
</td>
</tr>
<tr id="row2985204221018"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2985142131017"><a name="p2985142131017"></a><a name="p2985142131017"></a><a href="创建节点.md">创建节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1198544215108"><a name="p1198544215108"></a><a name="p1198544215108"></a>在指定集群下创建节点。</p>
</td>
</tr>
<tr id="row72181343191012"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1218184351019"><a name="p1218184351019"></a><a name="p1218184351019"></a><a href="获取指定的节点.md">获取指定的节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p162181432102"><a name="p162181432102"></a><a name="p162181432102"></a>通过节点ID获取指定节点的详细信息。</p>
</td>
</tr>
<tr id="row64371543161013"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p443824316107"><a name="p443824316107"></a><a name="p443824316107"></a><a href="获取集群下所有节点.md">获取集群下所有节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1643817436103"><a name="p1643817436103"></a><a name="p1643817436103"></a>通过集群ID获取指定集群下所有节点的详细信息。</p>
</td>
</tr>
<tr id="row261644318105"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p86161943171015"><a name="p86161943171015"></a><a name="p86161943171015"></a><a href="更新指定的节点.md">更新指定的节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p561694310106"><a name="p561694310106"></a><a name="p561694310106"></a>更新指定的节点。</p>
</td>
</tr>
<tr id="row58991443201010"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1589912437109"><a name="p1589912437109"></a><a name="p1589912437109"></a><a href="删除节点.md">删除节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p12900174319104"><a name="p12900174319104"></a><a name="p12900174319104"></a>删除指定的节点。</p>
</td>
</tr>
<tr id="row55115292153"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p55218293153"><a name="p55218293153"></a><a name="p55218293153"></a><a href="创建节点池.md">创建节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1521929191511"><a name="p1521929191511"></a><a name="p1521929191511"></a>在指定集群下创建节点池。</p>
</td>
</tr>
<tr id="row652112901511"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p85222912158"><a name="p85222912158"></a><a name="p85222912158"></a><a href="获取指定的节点池.md">获取指定的节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p17521296154"><a name="p17521296154"></a><a name="p17521296154"></a>获取指定节点池的详细信息。</p>
</td>
</tr>
<tr id="row4527299155"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p25282919156"><a name="p25282919156"></a><a name="p25282919156"></a><a href="获取集群下所有节点池.md">获取集群下所有节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1052229111514"><a name="p1052229111514"></a><a name="p1052229111514"></a>获取集群下所有节点池。</p>
</td>
</tr>
<tr id="row155232931510"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p352142918155"><a name="p352142918155"></a><a name="p352142918155"></a><a href="更新指定节点池.md">更新指定节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1552529161518"><a name="p1552529161518"></a><a name="p1552529161518"></a>更新指定的节点池。</p>
</td>
</tr>
<tr id="row8521629141518"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p7521229191510"><a name="p7521229191510"></a><a name="p7521229191510"></a><a href="删除节点池.md">删除节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p12521029171516"><a name="p12521029171516"></a><a name="p12521029171516"></a>删除指定的节点池。</p>
</td>
</tr>
<tr id="row3198154021214"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p14611442592"><a name="p14611442592"></a><a name="p14611442592"></a><a href="获取任务信息.md">获取任务信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11873644161010"><a name="p11873644161010"></a><a name="p11873644161010"></a>查询作业进度，通过某一作业请求下发后返回的jobID来查询指定作业的进度。</p>
</td>
</tr>
</tbody>
</table>

## 存储管理<a name="section7558510185812"></a>

**表 2**  存储管理

<a name="table7642161835811"></a>
<table><thead align="left"><tr id="row96431718185811"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p5643118145819"><a name="p5643118145819"></a><a name="p5643118145819"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p18643191885815"><a name="p18643191885815"></a><a name="p18643191885815"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row2643518165810"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p10643171815819"><a name="p10643171815819"></a><a name="p10643171815819"></a><a href="创建PVC.md">创建PVC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p264311865818"><a name="p264311865818"></a><a name="p264311865818"></a>在指定的Namespace下通过华为云存储服务中的云存储（EVS、SFS、OBS）去创建PersistentVolumeClaim。</p>
</td>
</tr>
<tr id="row176431418185819"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p66435189586"><a name="p66435189586"></a><a name="p66435189586"></a><a href="删除PVC.md">删除PVC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p7644218105810"><a name="p7644218105810"></a><a name="p7644218105810"></a>删除指定Namespace下的PersistentVolumeClaim对象，并可以选择保留后端的云存储。</p>
</td>
</tr>
</tbody>
</table>

## 插件管理<a name="section146435191572"></a>

**表 3**  插件管理

<a name="table45364351772"></a>
<table><thead align="left"><tr id="row1553718351171"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p397312401879"><a name="p397312401879"></a><a name="p397312401879"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p29731640478"><a name="p29731640478"></a><a name="p29731640478"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row11537153515711"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11537193510719"><a name="p11537193510719"></a><a name="p11537193510719"></a><a href="创建AddonInstance.md">创建AddonInstance</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p8537635871"><a name="p8537635871"></a><a name="p8537635871"></a>根据提供的插件模板，安装插件实例。</p>
</td>
</tr>
<tr id="row21741529172314"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p85371735571"><a name="p85371735571"></a><a name="p85371735571"></a><a href="查询AddonTemplates列表.md">查询AddonTemplates列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p55370351476"><a name="p55370351476"></a><a name="p55370351476"></a>插件模板查询接口，查询插件信息。</p>
</td>
</tr>
<tr id="row205377354718"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p165376358713"><a name="p165376358713"></a><a name="p165376358713"></a><a href="更新AddonInstance.md">更新AddonInstance</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9537113517712"><a name="p9537113517712"></a><a name="p9537113517712"></a>更新插件实例的功能。</p>
</td>
</tr>
<tr id="row1353703510718"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p753817356719"><a name="p753817356719"></a><a name="p753817356719"></a><a href="删除AddonInstance.md">删除AddonInstance</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p8538123517718"><a name="p8538123517718"></a><a name="p8538123517718"></a>删除插件实例的功能。</p>
</td>
</tr>
<tr id="row353818357710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1353811351874"><a name="p1353811351874"></a><a name="p1353811351874"></a><a href="获取AddonInstance详情.md">获取AddonInstance详情</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1553813351177"><a name="p1553813351177"></a><a name="p1553813351177"></a>获取插件实例详情。</p>
</td>
</tr>
<tr id="row5538035573"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p18538535971"><a name="p18538535971"></a><a name="p18538535971"></a><a href="获取AddonInstance列表.md">获取AddonInstance列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p165381435671"><a name="p165381435671"></a><a name="p165381435671"></a>获取集群所有已安装插件实例。</p>
</td>
</tr>
</tbody>
</table>

## Node<a name="section45001632162618"></a>

**表 4**  Node

<a name="table73818402263"></a>
<table><thead align="left"><tr id="row7382640182612"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p5101556263"><a name="p5101556263"></a><a name="p5101556263"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p910185516260"><a name="p910185516260"></a><a name="p910185516260"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row83821040102618"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p163821440182616"><a name="p163821440182616"></a><a name="p163821440182616"></a><a href="获取指定的Node.md">获取指定的Node</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18382194013267"><a name="p18382194013267"></a><a name="p18382194013267"></a>获取指定的Node。</p>
</td>
</tr>
<tr id="row10382140132618"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p338216408263"><a name="p338216408263"></a><a name="p338216408263"></a><a href="列出所有的Node.md">列出指定的Node</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p20382144062619"><a name="p20382144062619"></a><a name="p20382144062619"></a>获取指定的Node列表。</p>
</td>
</tr>
<tr id="row33831404263"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p53833400267"><a name="p53833400267"></a><a name="p53833400267"></a><a href="更新指定的Node.md">更新指定的Node</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1438374032619"><a name="p1438374032619"></a><a name="p1438374032619"></a>更新指定的Node。</p>
</td>
</tr>
</tbody>
</table>

## Namespace<a name="section5670526195718"></a>

**表 5**  Namespace

<a name="table557663355712"></a>
<table><thead align="left"><tr id="row4577113314579"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p14311242105712"><a name="p14311242105712"></a><a name="p14311242105712"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p131104210577"><a name="p131104210577"></a><a name="p131104210577"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row957773375714"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p457783395710"><a name="p457783395710"></a><a name="p457783395710"></a><a href="创建Namespace.md">创建Namespace</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p145773337575"><a name="p145773337575"></a><a name="p145773337575"></a>创建一个Namespace。</p>
</td>
</tr>
<tr id="row85770333571"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p6577113315711"><a name="p6577113315711"></a><a name="p6577113315711"></a><a href="删除Namespace.md">删除Namespace</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615060_p976457"><a name="zh-cn_topic_0079615060_p976457"></a><a name="zh-cn_topic_0079615060_p976457"></a>删除一个Namespace。</p>
</td>
</tr>
<tr id="row95776336570"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p16577153319579"><a name="p16577153319579"></a><a name="p16577153319579"></a><a href="获取指定的Namespace.md">获取指定的Namespace</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p5577533145715"><a name="p5577533145715"></a><a name="p5577533145715"></a>获取指定的Namespace的详细信息。</p>
</td>
</tr>
<tr id="row557783313574"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p18577193315717"><a name="p18577193315717"></a><a name="p18577193315717"></a><a href="替换指定的Namespace.md">替换指定的Namespace</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9578133355719"><a name="p9578133355719"></a><a name="p9578133355719"></a>替换指定的Namespace的部分信息。</p>
</td>
</tr>
<tr id="row957833355716"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p8578103355715"><a name="p8578103355715"></a><a name="p8578103355715"></a><a href="替换指定的Namespace的状态.md">替换指定的Namespace的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1057873318577"><a name="p1057873318577"></a><a name="p1057873318577"></a>更新指定Namespace的状态信息，即修改namespace对象status各字段的值。</p>
</td>
</tr>
<tr id="row95781233155710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1578143345717"><a name="p1578143345717"></a><a name="p1578143345717"></a><a href="替换指定的Namespace的Finalize值.md">替换指定的Namespace的Finalize值</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p75781338577"><a name="p75781338577"></a><a name="p75781338577"></a>替换指定Namespce的finalize的值。</p>
</td>
</tr>
<tr id="row11833145152014"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p88341851192018"><a name="p88341851192018"></a><a name="p88341851192018"></a><a href="列出Namespace.md">列出Namespace</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18834155142018"><a name="p18834155142018"></a><a name="p18834155142018"></a>获取集群中所有Namespace的详细信息。</p>
</td>
</tr>
<tr id="row760445692014"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1760414568206"><a name="p1760414568206"></a><a name="p1760414568206"></a><a href="更新指定的Namespace.md">更新指定的Namespace</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18604556152017"><a name="p18604556152017"></a><a name="p18604556152017"></a>更新指定Namespace部分信息。</p>
</td>
</tr>
</tbody>
</table>

## Resourcequotas<a name="section117341227528"></a>

**表 6**  Resourcequotas

<a name="table13734202135211"></a>
<table><thead align="left"><tr id="row17354219523"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p1173510245214"><a name="p1173510245214"></a><a name="p1173510245214"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p573511219526"><a name="p573511219526"></a><a name="p573511219526"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row177351421524"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p43071355125211"><a name="p43071355125211"></a><a name="p43071355125211"></a><a href="获取Resourcequotas.md">获取Resourcequotas</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p77351121529"><a name="p77351121529"></a><a name="p77351121529"></a>列出或查询Resourcequotas的详细信息。</p>
</td>
</tr>
</tbody>
</table>

## Pod<a name="section16809427204612"></a>

**表 7**  Pod

<a name="table17286173704617"></a>
<table><thead align="left"><tr id="row02881637174620"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p88778451466"><a name="p88778451466"></a><a name="p88778451466"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1587784504613"><a name="p1587784504613"></a><a name="p1587784504613"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row11288123712462"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1228853774614"><a name="p1228853774614"></a><a name="p1228853774614"></a><a href="创建Pod.md">创建Pod</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p6288183712462"><a name="p6288183712462"></a><a name="p6288183712462"></a>在指定Namespace下创建一个Pod对象。</p>
</td>
</tr>
<tr id="row728819376462"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1128843720461"><a name="p1128843720461"></a><a name="p1128843720461"></a><a href="删除Pod.md">删除Pod</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p228883794616"><a name="p228883794616"></a><a name="p228883794616"></a>删除指定Namespace下的某个Pod对象。</p>
</td>
</tr>
<tr id="row20288133719466"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p32881437194612"><a name="p32881437194612"></a><a name="p32881437194612"></a><a href="删除所有的Pod.md">删除所有的Pod</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p142881379465"><a name="p142881379465"></a><a name="p142881379465"></a>删除所有Pod对象。</p>
</td>
</tr>
<tr id="row15288173714462"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p42881037114619"><a name="p42881037114619"></a><a name="p42881037114619"></a><a href="获取指定的Pod.md">获取指定的Pod</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1288193718467"><a name="p1288193718467"></a><a name="p1288193718467"></a>获取指定Namespace下指定Pod的详细信息。</p>
</td>
</tr>
<tr id="row928843724615"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p928883734616"><a name="p928883734616"></a><a name="p928883734616"></a><a href="替换指定的Pod.md">替换指定的Pod</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1228863724614"><a name="p1228863724614"></a><a name="p1228863724614"></a>替换指定Namespace下的一个Pod对象。</p>
</td>
</tr>
<tr id="row92888375465"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p172881437104615"><a name="p172881437104615"></a><a name="p172881437104615"></a><a href="替换指定的Pod的状态.md">替换指定的Pod的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p8288153714610"><a name="p8288153714610"></a><a name="p8288153714610"></a>替换指定Namespace下的一个Pod对象的status，即修改Pod对象status各字段的值。</p>
</td>
</tr>
<tr id="row1448014120501"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p3481161225011"><a name="p3481161225011"></a><a name="p3481161225011"></a><a href="列出指定Namespaces下的所有Pod.md">列出指定Namespaces下的所有Pod</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p19481112125013"><a name="p19481112125013"></a><a name="p19481112125013"></a>列出指定Namespaces下面的所有Pod资源对象。</p>
</td>
</tr>
<tr id="row32631139509"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p82631213185014"><a name="p82631213185014"></a><a name="p82631213185014"></a><a href="列出Pod.md">列出Pod</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1626381315503"><a name="p1626381315503"></a><a name="p1626381315503"></a>获取一个Pod列表。</p>
</td>
</tr>
<tr id="row1983419154501"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p583418157505"><a name="p583418157505"></a><a name="p583418157505"></a><a href="更新指定的Pod.md">更新指定的Pod</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p168355155507"><a name="p168355155507"></a><a name="p168355155507"></a>更新指定Namespace下一个Pod对象。</p>
</td>
</tr>
</tbody>
</table>

## Deployment<a name="section1861515491505"></a>

**表 8**  Deployment

<a name="table1465775418016"></a>
<table><thead align="left"><tr id="row13658165414018"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p174111052112"><a name="p174111052112"></a><a name="p174111052112"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p441118510119"><a name="p441118510119"></a><a name="p441118510119"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row165885412010"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1265817546017"><a name="p1265817546017"></a><a name="p1265817546017"></a><a href="创建Deployment.md">创建Deployment</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16658354301"><a name="p16658354301"></a><a name="p16658354301"></a>创建一个Deployment资源对象。</p>
</td>
</tr>
<tr id="row1665818541302"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p165820540015"><a name="p165820540015"></a><a name="p165820540015"></a><a href="创建Deployment的回滚操作.md">创建Deployment的回滚操作</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1165814549016"><a name="p1165814549016"></a><a name="p1165814549016"></a>创建一个Deployment资源对象的回滚操作。</p>
</td>
</tr>
<tr id="row19658454209"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1565812548010"><a name="p1565812548010"></a><a name="p1565812548010"></a><a href="删除Deployment.md">删除Deployment</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1465817542017"><a name="p1465817542017"></a><a name="p1465817542017"></a>删除一个Deployment资源对象。</p>
</td>
</tr>
<tr id="row126586541709"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p19659054403"><a name="p19659054403"></a><a name="p19659054403"></a><a href="删除所有的Deployment.md">删除所有的Deployment</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p17659754303"><a name="p17659754303"></a><a name="p17659754303"></a>删除所有的Deployment资源对象。</p>
</td>
</tr>
<tr id="row146597541803"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p156594541509"><a name="p156594541509"></a><a name="p156594541509"></a><a href="获取指定的Deployment.md">获取指定的Deployment</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16659135413013"><a name="p16659135413013"></a><a name="p16659135413013"></a>获取某个Namespace下指定的Deployment对象。</p>
</td>
</tr>
<tr id="row1865916544016"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p106596544019"><a name="p106596544019"></a><a name="p106596544019"></a><a href="获取指定的Deployment的状态.md">获取指定的Deployment的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p186594548016"><a name="p186594548016"></a><a name="p186594548016"></a>获取某个Namespace下指定的Deployment对象的状态。</p>
</td>
</tr>
<tr id="row156591754600"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p765912549015"><a name="p765912549015"></a><a name="p765912549015"></a><a href="获取指定的Deployment的伸缩操作.md">获取指定的Deployment的伸缩操作</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p147913171810"><a name="p147913171810"></a><a name="p147913171810"></a>获取指定的Deployment的伸缩操作。</p>
</td>
</tr>
<tr id="row105245261335"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1952513265316"><a name="p1952513265316"></a><a name="p1952513265316"></a><a href="替换指定的Deployment.md">替换指定的Deployment</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p135258261031"><a name="p135258261031"></a><a name="p135258261031"></a>替换指定的Deployment对象。</p>
</td>
</tr>
<tr id="row645310301314"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p19453123011317"><a name="p19453123011317"></a><a name="p19453123011317"></a><a href="替换指定的Deployment的状态.md">替换指定的Deployment的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1732015719245"><a name="p1732015719245"></a><a name="p1732015719245"></a>替换指定命名空间下指定Deployment的状态，即修改Deployment的status字段的值。</p>
</td>
</tr>
<tr id="row1894633011314"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p29463301732"><a name="p29463301732"></a><a name="p29463301732"></a><a href="替换指定的Deployment的伸缩操作.md">替换指定的Deployment的伸缩操作</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1994693016318"><a name="p1994693016318"></a><a name="p1994693016318"></a>替换指定的Deployment的伸缩操作。</p>
</td>
</tr>
<tr id="row04369311318"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1043613319316"><a name="p1043613319316"></a><a name="p1043613319316"></a><a href="列出指定Namespace下的Deployment.md">列出指定Namespace下的Deployment</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p144365311311"><a name="p144365311311"></a><a name="p144365311311"></a>列出指定命名空间下的所有Deployment资源对象。</p>
</td>
</tr>
<tr id="row1687517313315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p8875131336"><a name="p8875131336"></a><a name="p8875131336"></a><a href="列出所有的Deployment.md">列出指定的Deployment</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1875163119318"><a name="p1875163119318"></a><a name="p1875163119318"></a>列出指定的Deployment资源对象。</p>
</td>
</tr>
<tr id="row143005321439"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11300163211313"><a name="p11300163211313"></a><a name="p11300163211313"></a><a href="更新指定的Deployment.md">更新指定的Deployment</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1830010327313"><a name="p1830010327313"></a><a name="p1830010327313"></a>更新指定Namespace下的Deployment对象。</p>
</td>
</tr>
<tr id="row77441532835"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p47441432335"><a name="p47441432335"></a><a name="p47441432335"></a><a href="更新指定的Deployment的状态.md">更新指定的Deployment的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p674417321834"><a name="p674417321834"></a><a name="p674417321834"></a>更新指定Namespace下指定Deployment 对象的状态。</p>
</td>
</tr>
<tr id="row321010339320"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p122101433338"><a name="p122101433338"></a><a name="p122101433338"></a><a href="更新指定的Deployment的伸缩操作.md">更新指定的Deployment的伸缩操作</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p172101933832"><a name="p172101933832"></a><a name="p172101933832"></a>更新指定的Deployment的伸缩操作。</p>
</td>
</tr>
</tbody>
</table>

## StatefulSet<a name="section3492103213420"></a>

**表 9**  StatefulSet

<a name="table33414017423"></a>
<table><thead align="left"><tr id="row53684074215"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p13545448194218"><a name="p13545448194218"></a><a name="p13545448194218"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1854594813425"><a name="p1854594813425"></a><a name="p1854594813425"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row236140134219"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p23611402427"><a name="p23611402427"></a><a name="p23611402427"></a><a href="创建StatefulSet.md">创建StatefulSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p143624044214"><a name="p143624044214"></a><a name="p143624044214"></a>创建一个StatefulSet资源对象。</p>
</td>
</tr>
<tr id="row113664015429"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p10361740154218"><a name="p10361740154218"></a><a name="p10361740154218"></a><a href="删除指定的StatefulSet.md">删除StatefulSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p43664010429"><a name="p43664010429"></a><a name="p43664010429"></a>删除一个StatefulSet资源对象。</p>
</td>
</tr>
<tr id="row1036540194210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p536140124210"><a name="p536140124210"></a><a name="p536140124210"></a><a href="删除所有的StatefulSet.md">删除所有的StatefulSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p636134016423"><a name="p636134016423"></a><a name="p636134016423"></a>删除所有的StatefulSet资源对象。</p>
</td>
</tr>
<tr id="row133712401424"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1137154024212"><a name="p1137154024212"></a><a name="p1137154024212"></a><a href="获取指定的StatefulSet.md">获取指定的StatefulSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p13764094219"><a name="p13764094219"></a><a name="p13764094219"></a>获取指定Namespace下的StatefulSet对象。</p>
</td>
</tr>
<tr id="row1337144024215"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p14371840194219"><a name="p14371840194219"></a><a name="p14371840194219"></a><a href="获取指定的StatefulSet的状态.md">获取指定的StatefulSet的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p123744074216"><a name="p123744074216"></a><a name="p123744074216"></a>获取指定Namespace下指定StatefulSet对象的状态。</p>
</td>
</tr>
<tr id="row1137340114215"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1537104015421"><a name="p1537104015421"></a><a name="p1537104015421"></a><a href="替换指定的StatefulSet.md">替换指定的StatefulSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p537184034218"><a name="p537184034218"></a><a name="p537184034218"></a>替换指定Namespace下的StatefulSet对象。</p>
</td>
</tr>
<tr id="row637840114213"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1137114094215"><a name="p1137114094215"></a><a name="p1137114094215"></a><a href="替换指定的StatefulSet的状态.md">替换指定的StatefulSet的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p203754010423"><a name="p203754010423"></a><a name="p203754010423"></a>替换指定Namespace下指定StatefulSet对象的状态，即修改StatefulSet对象的status字段的值。</p>
</td>
</tr>
<tr id="row161261528178"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p191271128975"><a name="p191271128975"></a><a name="p191271128975"></a><a href="列出指定Namespace下的StatefulSet.md">列出指定Namespace下的StatefulSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11271928176"><a name="p11271928176"></a><a name="p11271928176"></a>列出指定Namespace下的所有StatefulSet资源对象。</p>
</td>
</tr>
<tr id="row419811311774"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1819903118712"><a name="p1819903118712"></a><a name="p1819903118712"></a><a href="列出所有的StatefulSet.md">列出指定的StatefulSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p919923112711"><a name="p919923112711"></a><a name="p919923112711"></a>列出所有的StatefulSet资源对象。</p>
</td>
</tr>
<tr id="row062839679"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p262239978"><a name="p262239978"></a><a name="p262239978"></a><a href="更新指定的StatefulSet.md">更新指定的StatefulSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p15621039171"><a name="p15621039171"></a><a name="p15621039171"></a>更新指定Namespace下的StatefulSet对象。</p>
</td>
</tr>
<tr id="row891912416710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1919541172"><a name="p1919541172"></a><a name="p1919541172"></a><a href="更新指定的StatefulSet的状态.md">更新指定的StatefulSet的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p10919194112719"><a name="p10919194112719"></a><a name="p10919194112719"></a>更新指定Namespace下指定StatefulSet对象的状态。</p>
</td>
</tr>
</tbody>
</table>

## DaemonSet<a name="section6431713133319"></a>

**表 10**  DaemonSet

<a name="table741312332346"></a>
<table><thead align="left"><tr id="row241653313346"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p1453185115343"><a name="p1453185115343"></a><a name="p1453185115343"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1545318512342"><a name="p1545318512342"></a><a name="p1545318512342"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row174164337342"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p14161333113411"><a name="p14161333113411"></a><a name="p14161333113411"></a><a href="创建DaemonSet.md">创建DaemonSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p241673310344"><a name="p241673310344"></a><a name="p241673310344"></a>创建一个DaemonSet资源对象。</p>
</td>
</tr>
<tr id="row4416183310348"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p5417103363410"><a name="p5417103363410"></a><a name="p5417103363410"></a><a href="删除指定的DaemonSet.md">删除DaemonSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p74171933143413"><a name="p74171933143413"></a><a name="p74171933143413"></a>删除一个DaemonSet资源对象。</p>
</td>
</tr>
<tr id="row1441733310344"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1441733373414"><a name="p1441733373414"></a><a name="p1441733373414"></a><a href="删除所有的Daemonset.md">删除所有的Daemonset</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16417833153420"><a name="p16417833153420"></a><a name="p16417833153420"></a>删除所有DaemonSet资源对象。</p>
</td>
</tr>
<tr id="row1841763314343"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p9417533183410"><a name="p9417533183410"></a><a name="p9417533183410"></a><a href="获取指定的DaemonSet.md">获取指定的DaemonSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16417183353416"><a name="p16417183353416"></a><a name="p16417183353416"></a>读取指定Namespace下的DaemonSet对象。</p>
</td>
</tr>
<tr id="row5417633183415"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p341719332349"><a name="p341719332349"></a><a name="p341719332349"></a><a href="获取指定的DaemonSet的状态.md">获取指定的DaemonSet的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1941712336348"><a name="p1941712336348"></a><a name="p1941712336348"></a>读取指定Namespace下指定DaemonSet对象的状态。</p>
</td>
</tr>
<tr id="row1441753333410"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p9418113319348"><a name="p9418113319348"></a><a name="p9418113319348"></a><a href="更新指定的DaemonSet.md">更新指定的DaemonSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9418103383417"><a name="p9418103383417"></a><a name="p9418103383417"></a>更新指定Namespace下的DaemonSet对象。</p>
</td>
</tr>
<tr id="row16418203319342"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p741810336341"><a name="p741810336341"></a><a name="p741810336341"></a><a href="更新指定的DaemonSet的状态.md">更新指定的DaemonSet的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p641813316340"><a name="p641813316340"></a><a name="p641813316340"></a>更新指定Namespace下指定DaemonSet对象的状态。</p>
</td>
</tr>
<tr id="row393544218367"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1893611421362"><a name="p1893611421362"></a><a name="p1893611421362"></a><a href="列出所有的DaemonSet.md">列出指定的DaemonSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p19936154212363"><a name="p19936154212363"></a><a name="p19936154212363"></a>列出所有DemonSet资源对象。</p>
</td>
</tr>
<tr id="row1426194615369"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p642794615366"><a name="p642794615366"></a><a name="p642794615366"></a><a href="列出指定Namespace下的DaemonSet.md">列出指定Namespace下的DaemonSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1142724618360"><a name="p1142724618360"></a><a name="p1142724618360"></a>列出指定Namespace下的所有DaemonSet资源对象。</p>
</td>
</tr>
<tr id="row5700114916365"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1701194915368"><a name="p1701194915368"></a><a name="p1701194915368"></a><a href="替换指定的DaemonSet.md">替换指定的DaemonSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p17701449153620"><a name="p17701449153620"></a><a name="p17701449153620"></a>替换指定Namespace下的DaemonSet对象。</p>
</td>
</tr>
<tr id="row16291855133620"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p132911553364"><a name="p132911553364"></a><a name="p132911553364"></a><a href="替换指定的DaemonSet的状态.md">替换指定的DaemonSet的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p929655113613"><a name="p929655113613"></a><a name="p929655113613"></a>替换指定Namespace下指定DaemonSet对象的状态，即修改DaemonSet对象的status字段的值。</p>
</td>
</tr>
</tbody>
</table>

## Job<a name="section4614175410203"></a>

**表 11**  Job

<a name="table8653422152114"></a>
<table><thead align="left"><tr id="row1565511225219"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p20146738192118"><a name="p20146738192118"></a><a name="p20146738192118"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p61471138152117"><a name="p61471138152117"></a><a name="p61471138152117"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row9655102202116"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p5655222142112"><a name="p5655222142112"></a><a name="p5655222142112"></a><a href="创建Job.md">创建Job</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p46551122192115"><a name="p46551122192115"></a><a name="p46551122192115"></a>创建Job资源对象。</p>
</td>
</tr>
<tr id="row16553228218"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p18655192220217"><a name="p18655192220217"></a><a name="p18655192220217"></a><a href="删除Job.md">删除Job</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p665572217211"><a name="p665572217211"></a><a name="p665572217211"></a>删除Job资源对象。</p>
</td>
</tr>
<tr id="row13655822132117"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p965511224212"><a name="p965511224212"></a><a name="p965511224212"></a><a href="删除所有的Job.md">删除所有的Job</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p065532222116"><a name="p065532222116"></a><a name="p065532222116"></a>删除所有的Job资源对象。</p>
</td>
</tr>
<tr id="row1265532218217"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p196551022162116"><a name="p196551022162116"></a><a name="p196551022162116"></a><a href="获取指定的Job.md">获取指定的Job</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p15655182210219"><a name="p15655182210219"></a><a name="p15655182210219"></a>获取指定的Job资源对象。</p>
</td>
</tr>
<tr id="row136551224215"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p12655192212118"><a name="p12655192212118"></a><a name="p12655192212118"></a><a href="获取指定的Job的状态.md">获取指定的Job的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p6655122252110"><a name="p6655122252110"></a><a name="p6655122252110"></a>获取指定Job的状态信息。</p>
</td>
</tr>
<tr id="row106554227211"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1665592214216"><a name="p1665592214216"></a><a name="p1665592214216"></a><a href="替换指定的Job.md">替换指定的Job</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p865518223216"><a name="p865518223216"></a><a name="p865518223216"></a>替换指定Job。</p>
</td>
</tr>
<tr id="row11655152292114"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1565562218217"><a name="p1565562218217"></a><a name="p1565562218217"></a><a href="替换指定的Job的状态.md">替换指定的Job的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16655132292112"><a name="p16655132292112"></a><a name="p16655132292112"></a>替换指定Job的状态。</p>
</td>
</tr>
<tr id="row747158241"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2048115182417"><a name="p2048115182417"></a><a name="p2048115182417"></a><a href="列出指定Namespace下的Job.md">列出指定Namespace下的Job</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1648455242"><a name="p1648455242"></a><a name="p1648455242"></a>列出指定Namespace下的所有Jod资源对象。</p>
</td>
</tr>
<tr id="row18180161218247"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1018018128249"><a name="p1018018128249"></a><a name="p1018018128249"></a><a href="列出所有Job.md">列出所有Job</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p5180121217248"><a name="p5180121217248"></a><a name="p5180121217248"></a>用于获取Job列表。</p>
</td>
</tr>
<tr id="row16627149172414"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p5627393245"><a name="p5627393245"></a><a name="p5627393245"></a><a href="更新指定的Job的状态.md">更新指定的Job的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p12628189182420"><a name="p12628189182420"></a><a name="p12628189182420"></a>更新指定Namespace下指定Job的状态。</p>
</td>
</tr>
<tr id="row2127176241"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p41276713244"><a name="p41276713244"></a><a name="p41276713244"></a><a href="更新指定的Job.md">更新指定的Job</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p10127972246"><a name="p10127972246"></a><a name="p10127972246"></a>更新指定的Job。</p>
</td>
</tr>
</tbody>
</table>

## CronJob<a name="section6473758192314"></a>

**表 12**  CronJob

<a name="table21132315244"></a>
<table><thead align="left"><tr id="row911413362418"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p695771010248"><a name="p695771010248"></a><a name="p695771010248"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p9957510102415"><a name="p9957510102415"></a><a name="p9957510102415"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1711515315243"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1711543152412"><a name="p1711543152412"></a><a name="p1711543152412"></a><a href="创建CronJob.md">创建CronJob</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1511553102418"><a name="p1511553102418"></a><a name="p1511553102418"></a>创建CronJob资源对象。</p>
</td>
</tr>
<tr id="row611513192413"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p13115434244"><a name="p13115434244"></a><a name="p13115434244"></a><a href="删除CronJob.md">删除CronJob</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p161152313246"><a name="p161152313246"></a><a name="p161152313246"></a>删除CronJob资源对象。</p>
</td>
</tr>
<tr id="row17115639240"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p61151439240"><a name="p61151439240"></a><a name="p61151439240"></a><a href="删除所有的CronJob.md">删除所有的CronJob</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p131151137246"><a name="p131151137246"></a><a name="p131151137246"></a>删除所有CronJob资源对象。</p>
</td>
</tr>
<tr id="row11153382417"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p181151835241"><a name="p181151835241"></a><a name="p181151835241"></a><a href="获取指定的CronJob.md">获取指定的CronJob</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p131161333242"><a name="p131161333242"></a><a name="p131161333242"></a>获取指定的CronJob资源对象。</p>
</td>
</tr>
<tr id="row41165392415"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1511613322411"><a name="p1511613322411"></a><a name="p1511613322411"></a><a href="获取指定的CronJob的状态.md">获取指定的CronJob的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p335590173210"><a name="p335590173210"></a><a name="p335590173210"></a>获取指定的CronJob的状态。</p>
</td>
</tr>
<tr id="row151167314247"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p811615302413"><a name="p811615302413"></a><a name="p811615302413"></a><a href="替换指定的CronJob.md">替换指定的CronJob</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1711683122415"><a name="p1711683122415"></a><a name="p1711683122415"></a>替换指定的CronJob资源对象。</p>
</td>
</tr>
<tr id="row101161938244"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p20116183162416"><a name="p20116183162416"></a><a name="p20116183162416"></a><a href="替换指定的CronJob的状态.md">替换指定的CronJob的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p4116133182414"><a name="p4116133182414"></a><a name="p4116133182414"></a>替换指定CronJob的状态。</p>
</td>
</tr>
<tr id="row133721432718"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p23395148272"><a name="p23395148272"></a><a name="p23395148272"></a><a href="列出指定Namespace下的CronJob.md">列出指定Namespace下的CronJob</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p433951411279"><a name="p433951411279"></a><a name="p433951411279"></a>列出指定Namespace下的所有CronJod资源对象。</p>
</td>
</tr>
<tr id="row7240524112714"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p7240124112715"><a name="p7240124112715"></a><a name="p7240124112715"></a><a href="列出所有的CronJob.md">列出所有的CronJob</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p14240182472720"><a name="p14240182472720"></a><a name="p14240182472720"></a>列出所有的CronJob资源对象。</p>
</td>
</tr>
<tr id="row2077102717276"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p10782272279"><a name="p10782272279"></a><a name="p10782272279"></a><a href="更新指定的CronJob的状态.md">更新指定的CronJob的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1878182772718"><a name="p1878182772718"></a><a name="p1878182772718"></a>更新指定Namespace下指定CronJob的状态。</p>
</td>
</tr>
<tr id="row950122117273"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p145011021162719"><a name="p145011021162719"></a><a name="p145011021162719"></a><a href="更新指定的CronJob.md">更新指定的CronJob</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p15501152122719"><a name="p15501152122719"></a><a name="p15501152122719"></a>更新指定的CronJob资源对象。</p>
</td>
</tr>
</tbody>
</table>

## ReplicaSet<a name="section1136381210362"></a>

**表 13**  ReplicaSet

<a name="table11215101815365"></a>
<table><thead align="left"><tr id="row1721810186364"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p101766339367"><a name="p101766339367"></a><a name="p101766339367"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1617673323615"><a name="p1617673323615"></a><a name="p1617673323615"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1721811811368"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p3218518183614"><a name="p3218518183614"></a><a name="p3218518183614"></a><a href="列出指定的ReplicaSet.md">列出指定的ReplicaSet</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9218818163615"><a name="p9218818163615"></a><a name="p9218818163615"></a>列出指定Namespace下的所有ReplicaSet资源对象。</p>
</td>
</tr>
</tbody>
</table>

## ReplicationController<a name="section19743501453"></a>

**表 14**  ReplicationController

<a name="table12457630134518"></a>
<table><thead align="left"><tr id="row1845863084518"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p631833944517"><a name="p631833944517"></a><a name="p631833944517"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p931813911450"><a name="p931813911450"></a><a name="p931813911450"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row145813301454"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p84583308455"><a name="p84583308455"></a><a name="p84583308455"></a><a href="创建ReplicationController.md">创建ReplicationController</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16458143016451"><a name="p16458143016451"></a><a name="p16458143016451"></a>创建ReplicationController资源类型。</p>
</td>
</tr>
<tr id="row1145810302453"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p74581430144520"><a name="p74581430144520"></a><a name="p74581430144520"></a><a href="删除ReplicationController.md">删除ReplicationController</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1545813074514"><a name="p1545813074514"></a><a name="p1545813074514"></a>删除一个ReplicationController对象。</p>
</td>
</tr>
<tr id="row7458143015453"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11458113014456"><a name="p11458113014456"></a><a name="p11458113014456"></a><a href="删除所有的ReplicationController.md">删除所有的ReplicationController</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p945883084513"><a name="p945883084513"></a><a name="p945883084513"></a>批量删除ReplicationController。</p>
</td>
</tr>
<tr id="row7458103017458"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p34583309457"><a name="p34583309457"></a><a name="p34583309457"></a><a href="获取指定Namespace下的ReplicationController.md">获取指定Namespace下的ReplicationController</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1545813304457"><a name="p1545813304457"></a><a name="p1545813304457"></a>获取指定Namespace下的ReplicationController对象。</p>
</td>
</tr>
<tr id="row17458430174517"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p345893034511"><a name="p345893034511"></a><a name="p345893034511"></a><a href="替换指定Namespace下的ReplicationController.md">替换指定Namespace下的ReplicationController</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p945833014457"><a name="p945833014457"></a><a name="p945833014457"></a>替换指定Namespace下的ReplicationController对象。</p>
</td>
</tr>
<tr id="row745920302450"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p24591430164516"><a name="p24591430164516"></a><a name="p24591430164516"></a><a href="替换指定Namespace下的ReplicationController状态.md">替换指定Namespace下的ReplicationController状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p3459530114518"><a name="p3459530114518"></a><a name="p3459530114518"></a>替换指定Namespace下的某个ReplicationController对象的状态，即修改ReplicationController对象status各字段的值。</p>
</td>
</tr>
<tr id="row1545917308450"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p164592306459"><a name="p164592306459"></a><a name="p164592306459"></a><a href="列出指定Namespace下的ReplicationController.md">列出指定Namespace下的ReplicationController</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615054_p19352287"><a name="zh-cn_topic_0079615054_p19352287"></a><a name="zh-cn_topic_0079615054_p19352287"></a>列出指定Namespace下的所有ReplicationController。</p>
</td>
</tr>
<tr id="row17156194074710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p13157174094720"><a name="p13157174094720"></a><a name="p13157174094720"></a><a href="列出ReplicationController.md">列出ReplicationController</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p2157154014714"><a name="p2157154014714"></a><a name="p2157154014714"></a>获取ReplicationController列表。</p>
</td>
</tr>
<tr id="row212744464712"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p15127134418479"><a name="p15127134418479"></a><a name="p15127134418479"></a><a href="更新指定的ReplicationController.md">更新指定的ReplicationController</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1812715447477"><a name="p1812715447477"></a><a name="p1812715447477"></a>更新指定Namespace下的ReplicationController对象。</p>
</td>
</tr>
</tbody>
</table>

## Endpoints<a name="section19711239392"></a>

**表 15**  Endpoints

<a name="table962485015406"></a>
<table><thead align="left"><tr id="row66243503405"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p7939359134015"><a name="p7939359134015"></a><a name="p7939359134015"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p893918595407"><a name="p893918595407"></a><a name="p893918595407"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1662485018401"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p262495012404"><a name="p262495012404"></a><a name="p262495012404"></a><a href="创建Endpoints.md">创建Endpoints</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1462416507409"><a name="p1462416507409"></a><a name="p1462416507409"></a>创建一个Endpoints资源对象。</p>
</td>
</tr>
<tr id="row12624950134013"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1162435044011"><a name="p1162435044011"></a><a name="p1162435044011"></a><a href="删除Endpoints.md">删除Endpoints</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p15624165019409"><a name="p15624165019409"></a><a name="p15624165019409"></a>删除一个Endpoints资源对象。</p>
</td>
</tr>
<tr id="row17624450134015"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1624050154013"><a name="p1624050154013"></a><a name="p1624050154013"></a><a href="删除所有的Endpoints.md">删除所有的Endpoints</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p146251850164016"><a name="p146251850164016"></a><a name="p146251850164016"></a>删除所有Endpoints资源对象。</p>
</td>
</tr>
<tr id="row762585034015"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p66251550134010"><a name="p66251550134010"></a><a name="p66251550134010"></a><a href="获取指定的Endpoints.md">获取指定的Endpoints</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p562545019405"><a name="p562545019405"></a><a name="p562545019405"></a>获取某个Namespace下指定的Endpoints对象。</p>
</td>
</tr>
<tr id="row11625175084014"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p262525011406"><a name="p262525011406"></a><a name="p262525011406"></a><a href="替换指定的Endpoints.md">替换指定的Endpoints</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p8625350184012"><a name="p8625350184012"></a><a name="p8625350184012"></a>替换指定Namespace下指定的Endpoints资源对象。</p>
</td>
</tr>
<tr id="row96259501408"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p18625105084015"><a name="p18625105084015"></a><a name="p18625105084015"></a><a href="列出Endpoints.md">列出Endpoints</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1262595017402"><a name="p1262595017402"></a><a name="p1262595017402"></a>列出所有的Endpoints资源对象。</p>
</td>
</tr>
<tr id="row9625145013406"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1562515064018"><a name="p1562515064018"></a><a name="p1562515064018"></a><a href="列出指定Namespace下的Endpoints.md">列出指定Namespace下的Endpoints</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16625145013406"><a name="p16625145013406"></a><a name="p16625145013406"></a>获取指定Namespace下的所有Endpoints对象。</p>
</td>
</tr>
<tr id="row193705016447"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p4371190204412"><a name="p4371190204412"></a><a name="p4371190204412"></a><a href="更新指定的Endpoints.md">更新指定的Endpoints</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p83718034414"><a name="p83718034414"></a><a name="p83718034414"></a>更新指定Namespace下的Endpoints对象。</p>
</td>
</tr>
</tbody>
</table>

## Service<a name="section22031373168"></a>

**表 16**  Service

<a name="table13943613191610"></a>
<table><thead align="left"><tr id="row16944713191618"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p172071120151617"><a name="p172071120151617"></a><a name="p172071120151617"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p4207820141610"><a name="p4207820141610"></a><a name="p4207820141610"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row20944101351610"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p179441113131618"><a name="p179441113131618"></a><a name="p179441113131618"></a><a href="创建Service.md">创建Service</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18944913121611"><a name="p18944913121611"></a><a name="p18944913121611"></a>创建一个Service对象。</p>
</td>
</tr>
<tr id="row7944131381618"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p094413136165"><a name="p094413136165"></a><a name="p094413136165"></a><a href="删除指定的Service.md">删除Service</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p294401319169"><a name="p294401319169"></a><a name="p294401319169"></a>删除一个Service对象。</p>
</td>
</tr>
<tr id="row2944413141616"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1944111310166"><a name="p1944111310166"></a><a name="p1944111310166"></a><a href="获取指定的Service.md">获取指定的Service</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p159448135160"><a name="p159448135160"></a><a name="p159448135160"></a>获取指定的Service对象。</p>
</td>
</tr>
<tr id="row169441513151610"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p19944013191611"><a name="p19944013191611"></a><a name="p19944013191611"></a><a href="替换指定的Service.md">替换指定的Service</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p6944161316161"><a name="p6944161316161"></a><a name="p6944161316161"></a>替换指定的Service对象。</p>
</td>
</tr>
<tr id="row1694491313169"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1994511137160"><a name="p1994511137160"></a><a name="p1994511137160"></a><a href="列出指定Namespace下的Service.md">列出指定Namespace下的Service</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16945413101620"><a name="p16945413101620"></a><a name="p16945413101620"></a>列出指定Namespace下的Service对象。</p>
</td>
</tr>
<tr id="row294512136163"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1594517139164"><a name="p1594517139164"></a><a name="p1594517139164"></a><a href="列出Service.md">列出Service</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p094521301618"><a name="p094521301618"></a><a name="p094521301618"></a>获取集群中的Service列表。</p>
</td>
</tr>
<tr id="row1694581361619"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1694551317164"><a name="p1694551317164"></a><a name="p1694551317164"></a><a href="更新指定的Service.md">更新指定的Service</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p209452013181617"><a name="p209452013181617"></a><a name="p209452013181617"></a>替换指定的Service对象。</p>
</td>
</tr>
</tbody>
</table>

## Ingress<a name="section59746191731"></a>

**表 17**  Ingress

<a name="table210410261331"></a>
<table><thead align="left"><tr id="row41059267311"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p93241635934"><a name="p93241635934"></a><a name="p93241635934"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p113252035336"><a name="p113252035336"></a><a name="p113252035336"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row131055261311"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p71059262033"><a name="p71059262033"></a><a name="p71059262033"></a><a href="创建Ingress.md">创建Ingress</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1210517261236"><a name="p1210517261236"></a><a name="p1210517261236"></a>创建一个Ingress。</p>
</td>
</tr>
<tr id="row16105142619314"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p121051926535"><a name="p121051926535"></a><a name="p121051926535"></a><a href="更新指定的Ingress.md">更新指定的Ingress</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1410512267314"><a name="p1410512267314"></a><a name="p1410512267314"></a>对指定的Ingress进行局部更新。</p>
</td>
</tr>
<tr id="row510510261138"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p61051526138"><a name="p61051526138"></a><a name="p61051526138"></a><a href="替换指定的Ingress.md">替换指定的Ingress</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p101051926933"><a name="p101051926933"></a><a name="p101051926933"></a>替换指定的Ingress。</p>
</td>
</tr>
<tr id="row3105826831"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p610542620318"><a name="p610542620318"></a><a name="p610542620318"></a><a href="删除Ingress.md">删除Ingress</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1589411332712"><a name="p1589411332712"></a><a name="p1589411332712"></a>删除Ingress。</p>
</td>
</tr>
<tr id="row1210612268310"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11106172611314"><a name="p11106172611314"></a><a name="p11106172611314"></a><a href="删除所有的Ingress.md">删除所有的Ingress</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p191065261132"><a name="p191065261132"></a><a name="p191065261132"></a>删除所有的Ingress。</p>
</td>
</tr>
<tr id="row910618261637"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p610672616320"><a name="p610672616320"></a><a name="p610672616320"></a><a href="获取指定的Ingress.md">获取指定的Ingress</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1410662614312"><a name="p1410662614312"></a><a name="p1410662614312"></a>获取指定的Ingress。</p>
</td>
</tr>
<tr id="row7106162611315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p010662617314"><a name="p010662617314"></a><a name="p010662617314"></a><a href="列出指定Namespace下的Ingress.md">列出指定Namespace下的Ingress</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1210692619320"><a name="p1210692619320"></a><a name="p1210692619320"></a>列出指定Namespace下的Ingress。</p>
</td>
</tr>
<tr id="row1852517191951"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2052512198512"><a name="p2052512198512"></a><a name="p2052512198512"></a><a href="获取Ingress列表.md">获取Ingress列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p15128934118"><a name="p15128934118"></a><a name="p15128934118"></a>获取Ingress列表。</p>
</td>
</tr>
<tr id="row13655203513"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p5651220357"><a name="p5651220357"></a><a name="p5651220357"></a><a href="获取指定Namespace下的某个Ingress对象的状态.md">获取指定Namespace下的某个Ingress对象的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p85097546713"><a name="p85097546713"></a><a name="p85097546713"></a>获取指定Namespace下的某个Ingress对象的状态。</p>
</td>
</tr>
<tr id="row56003201511"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1860017201058"><a name="p1860017201058"></a><a name="p1860017201058"></a><a href="替换指定Namespace下的某个Ingress对象的状态.md">替换指定Namespace下的某个Ingress对象的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p060010206515"><a name="p060010206515"></a><a name="p060010206515"></a>替换指定Namespace下的某个Ingress对象的状态。</p>
</td>
</tr>
<tr id="row13237132115513"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p32371721458"><a name="p32371721458"></a><a name="p32371721458"></a><a href="更新指定Namespace下的某个Ingress对象的状态.md">更新指定Namespace下的某个Ingress对象的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1423752110514"><a name="p1423752110514"></a><a name="p1423752110514"></a>更新指定Namespace下的某个Ingress对象的状态。</p>
</td>
</tr>
</tbody>
</table>

## NetworkPolicy<a name="section3512167169"></a>

**表 18**  NetworkPolicy

<a name="table877821191612"></a>
<table><thead align="left"><tr id="row9781101116163"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p12033224166"><a name="p12033224166"></a><a name="p12033224166"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p20203522111612"><a name="p20203522111612"></a><a name="p20203522111612"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row478131141613"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p47811911171618"><a name="p47811911171618"></a><a name="p47811911171618"></a><a href="创建networkpolicy.md">创建networkpolicy</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1578117117162"><a name="p1578117117162"></a><a name="p1578117117162"></a>创建networkpolicy。</p>
</td>
</tr>
<tr id="row37814118163"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p117812011151616"><a name="p117812011151616"></a><a name="p117812011151616"></a><a href="更新指定的networkpolicy.md">更新指定的networkpolicy</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1478191131614"><a name="p1478191131614"></a><a name="p1478191131614"></a>部分更新指定的NetworkPolicy。</p>
</td>
</tr>
<tr id="row8781111119164"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1578118113168"><a name="p1578118113168"></a><a name="p1578118113168"></a><a href="替换指定的networkpolicy.md">替换指定的networkpolicy</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p13781111161611"><a name="p13781111161611"></a><a name="p13781111161611"></a>替换指定的networkpolicy。</p>
</td>
</tr>
<tr id="row178115116167"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11781111141610"><a name="p11781111141610"></a><a name="p11781111141610"></a><a href="删除networkpolicy.md">删除networkpolicy</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p978241151610"><a name="p978241151610"></a><a name="p978241151610"></a>删除networkpolicy。</p>
</td>
</tr>
<tr id="row167821311191619"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p87821911191619"><a name="p87821911191619"></a><a name="p87821911191619"></a><a href="批量删除networkpolicy.md">批量删除networkpolicy</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1278211119169"><a name="p1278211119169"></a><a name="p1278211119169"></a>批量删除networkpolicy。</p>
</td>
</tr>
<tr id="row478214117164"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p578281116166"><a name="p578281116166"></a><a name="p578281116166"></a><a href="获取指定的networkpolicy.md">获取指定的networkpolicy</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11398111312010"><a name="p11398111312010"></a><a name="p11398111312010"></a>获取指定的networkpolicy。</p>
</td>
</tr>
<tr id="row9782411141611"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1778221116161"><a name="p1778221116161"></a><a name="p1778221116161"></a><a href="列出指定namespace下的networkpolicy.md">列出指定namespace下的networkpolicy</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p6782611161614"><a name="p6782611161614"></a><a name="p6782611161614"></a>列出指定namespace下的networkpolicy。</p>
</td>
</tr>
<tr id="row16931528181819"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p4932162815181"><a name="p4932162815181"></a><a name="p4932162815181"></a><a href="获取networkpolicy列表.md">获取networkpolicy列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p893218285186"><a name="p893218285186"></a><a name="p893218285186"></a>获取networkpolicy列表。</p>
</td>
</tr>
</tbody>
</table>

## PersistentVolume<a name="section2877714125317"></a>

**表 19**  PersistentVolume

<a name="table15768102015318"></a>
<table><thead align="left"><tr id="row57691120155314"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p137637316537"><a name="p137637316537"></a><a name="p137637316537"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1076316319537"><a name="p1076316319537"></a><a name="p1076316319537"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row167701020205316"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p7770152095314"><a name="p7770152095314"></a><a name="p7770152095314"></a><a href="创建PersistentVolume.md">创建PersistentVolume</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1770320205319"><a name="p1770320205319"></a><a name="p1770320205319"></a>创建一个PersistentVolume。</p>
</td>
</tr>
<tr id="row197701220125313"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11770102019533"><a name="p11770102019533"></a><a name="p11770102019533"></a><a href="删除指定的PersistentVolume.md">删除指定的PersistentVolume</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9770192013532"><a name="p9770192013532"></a><a name="p9770192013532"></a>删除指定的PersistentVolume对象。</p>
</td>
</tr>
<tr id="row6770192018538"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p87701720185320"><a name="p87701720185320"></a><a name="p87701720185320"></a><a href="删除所有的PersistentVolume.md">删除所有的PersistentVolume</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11770182010532"><a name="p11770182010532"></a><a name="p11770182010532"></a>删除所有的PersistentVolume对象。</p>
</td>
</tr>
<tr id="row16770192017531"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2770202012531"><a name="p2770202012531"></a><a name="p2770202012531"></a><a href="获取指定的PersistentVolume.md">获取指定的PersistentVolume</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p137706206536"><a name="p137706206536"></a><a name="p137706206536"></a>获取指定的PersistentVolume对象。</p>
</td>
</tr>
<tr id="row117701320115316"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p077072018536"><a name="p077072018536"></a><a name="p077072018536"></a><a href="替换指定的PersistentVolume.md">替换指定的PersistentVolume</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p7771132045320"><a name="p7771132045320"></a><a name="p7771132045320"></a>替换指定的PersistentVolume对象。</p>
</td>
</tr>
<tr id="row127711820165316"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p577122012533"><a name="p577122012533"></a><a name="p577122012533"></a><a href="替换指定的PersistentVolume的状态.md">替换指定的PersistentVolume的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p0771152005310"><a name="p0771152005310"></a><a name="p0771152005310"></a>替换指定的PersistentVolume对象的状态。</p>
</td>
</tr>
<tr id="row167711920125310"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p677152015318"><a name="p677152015318"></a><a name="p677152015318"></a><a href="列出所有的PersistentVolume.md">列出所有的PersistentVolume</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p8771220185315"><a name="p8771220185315"></a><a name="p8771220185315"></a>列出所有PersistentVolume资源对象。</p>
</td>
</tr>
<tr id="row1896213294569"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p3962629125610"><a name="p3962629125610"></a><a name="p3962629125610"></a><a href="更新指定的PersistentVolume.md">更新指定的PersistentVolume</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p189621329205610"><a name="p189621329205610"></a><a name="p189621329205610"></a>更新PersistentVolume对象。</p>
</td>
</tr>
</tbody>
</table>

## PersistentVolumeClaim<a name="section1213813510476"></a>

**表 20**  PersistentVolumeClaim

<a name="table2480151244711"></a>
<table><thead align="left"><tr id="row948015124473"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p1722218273471"><a name="p1722218273471"></a><a name="p1722218273471"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1822262716470"><a name="p1822262716470"></a><a name="p1822262716470"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row348010121475"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1948041216475"><a name="p1948041216475"></a><a name="p1948041216475"></a><a href="创建PersistentVolumeClaim.md">创建PersistentVolumeClaim</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="a863b97964c8f46c382c223f924027de7"><a name="a863b97964c8f46c382c223f924027de7"></a><a name="a863b97964c8f46c382c223f924027de7"></a>在指定的Namespace下创建PersistentVolumeClaim。</p>
</td>
</tr>
<tr id="row9480912204717"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p648151210475"><a name="p648151210475"></a><a name="p648151210475"></a><a href="删除指定的PersistentVolumeClaim.md">删除指定的PersistentVolumeClaim</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p64814121472"><a name="p64814121472"></a><a name="p64814121472"></a>删除指定Namespace下的PersistentVolumeClaim对象。</p>
</td>
</tr>
<tr id="row048111234711"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p948112123474"><a name="p948112123474"></a><a name="p948112123474"></a><a href="删除所有的PersistentVolumeClaim.md">删除所有的PersistentVolumeClaim</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1448181213479"><a name="p1448181213479"></a><a name="p1448181213479"></a>删除所有的PersistentVolumeClaim资源对象。</p>
</td>
</tr>
<tr id="row14481012174718"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1248119125473"><a name="p1248119125473"></a><a name="p1248119125473"></a><a href="获取指定的PersistentVolumeClaim.md">获取指定的PersistentVolumeClaim</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p19481131218479"><a name="p19481131218479"></a><a name="p19481131218479"></a>获取指定Namespace下的PersistentVolumeClaim对象。</p>
</td>
</tr>
<tr id="row1948141220479"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p9481151244713"><a name="p9481151244713"></a><a name="p9481151244713"></a><a href="替换指定的PersistentVolumeClaim.md">替换指定的PersistentVolumeClaim</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p44811412124720"><a name="p44811412124720"></a><a name="p44811412124720"></a>替换指定Namespace下的PersistentVolumeClaim对象。</p>
</td>
</tr>
<tr id="row14481111224711"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p10481121216475"><a name="p10481121216475"></a><a name="p10481121216475"></a><a href="替换指定的PersistentVolumeClaim的状态.md">替换指定的PersistentVolumeClaim的状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p174811412104714"><a name="p174811412104714"></a><a name="p174811412104714"></a>替换指定的Namespace下指定的PersistentVolumeClaim对象的状态。</p>
</td>
</tr>
<tr id="row11481112174710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p648181211472"><a name="p648181211472"></a><a name="p648181211472"></a><a href="列出指定的Namespace下的PersistentVolumeClaim.md">列出指定的Namespace下的PersistentVolumeClaim</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p34813127474"><a name="p34813127474"></a><a name="p34813127474"></a>列出指定Namespace下的所有PersistentVolumeClaim资源对象。</p>
</td>
</tr>
<tr id="row12239758114914"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p19240758104916"><a name="p19240758104916"></a><a name="p19240758104916"></a><a href="列出所有的PersistentVolumeClaim.md">列出所有的PersistentVolumeClaim</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18241165818498"><a name="p18241165818498"></a><a name="p18241165818498"></a>列出所有PersistentVolumeClaim资源对象。</p>
</td>
</tr>
<tr id="row1694514045015"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p189451608508"><a name="p189451608508"></a><a name="p189451608508"></a><a href="更新指定的PersistentVolumeClaim.md">更新指定的PersistentVolumeClaim</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p129461508505"><a name="p129461508505"></a><a name="p129461508505"></a>更新PersistentVolumeClaim对象。</p>
</td>
</tr>
</tbody>
</table>

## ConfigMap<a name="section3536121119448"></a>

**表 21**  ConfigMap

<a name="table116555196444"></a>
<table><thead align="left"><tr id="row165916194446"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p1557713412445"><a name="p1557713412445"></a><a name="p1557713412445"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p11577154119441"><a name="p11577154119441"></a><a name="p11577154119441"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row13659101914447"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1565921915448"><a name="p1565921915448"></a><a name="p1565921915448"></a><a href="创建ConfigMap.md">创建ConfigMap</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11660161911446"><a name="p11660161911446"></a><a name="p11660161911446"></a>创建ConfigMap资源对象。</p>
</td>
</tr>
<tr id="row8660319114412"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p15660151974415"><a name="p15660151974415"></a><a name="p15660151974415"></a><a href="删除ConfigMap.md">删除ConfigMap</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11660121904411"><a name="p11660121904411"></a><a name="p11660121904411"></a>删除ConfigMap资源对象。</p>
</td>
</tr>
<tr id="row566013191445"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1166016193442"><a name="p1166016193442"></a><a name="p1166016193442"></a><a href="删除所有的ConfigMap.md">删除所有的ConfigMap</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11660101917441"><a name="p11660101917441"></a><a name="p11660101917441"></a>删除所有ConfigMap资源对象。</p>
</td>
</tr>
<tr id="row1366018198442"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p7660181924417"><a name="p7660181924417"></a><a name="p7660181924417"></a><a href="获取指定的ConfigMap.md">获取指定的ConfigMap</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p7660219164411"><a name="p7660219164411"></a><a name="p7660219164411"></a>获取指定的ConfigMap资源对象。</p>
</td>
</tr>
<tr id="row186601819164410"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p16604192444"><a name="p16604192444"></a><a name="p16604192444"></a><a href="替换指定ConfigMap.md">替换指定ConfigMap</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p52696176"><a name="p52696176"></a><a name="p52696176"></a>替换指定的ConfigMap资源对象。</p>
</td>
</tr>
<tr id="row10660181910445"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11660519184413"><a name="p11660519184413"></a><a name="p11660519184413"></a><a href="列出指定Namespace下的ConfigMap.md">列出指定Namespace下的ConfigMap</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p0660171914413"><a name="p0660171914413"></a><a name="p0660171914413"></a>列出指定Namespace下的所有ConfigMap资源对象。</p>
</td>
</tr>
<tr id="row9660219104410"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p566019194444"><a name="p566019194444"></a><a name="p566019194444"></a><a href="列出所有的ConfigMap.md">列出指定的ConfigMap</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p126600195445"><a name="p126600195445"></a><a name="p126600195445"></a>获取ConfigMap列表。</p>
</td>
</tr>
<tr id="row182401734174620"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p3241133444613"><a name="p3241133444613"></a><a name="p3241133444613"></a><a href="更新指定的ConfigMap.md">更新指定的ConfigMap</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1724116347466"><a name="p1724116347466"></a><a name="p1724116347466"></a>更新指定的ConfigMap资源对象。</p>
</td>
</tr>
</tbody>
</table>

## Secret<a name="section179302618111"></a>

**表 22**  Secret

<a name="table846494691712"></a>
<table><thead align="left"><tr id="row246494631719"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p7286553131710"><a name="p7286553131710"></a><a name="p7286553131710"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p328615381711"><a name="p328615381711"></a><a name="p328615381711"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row154651646101710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p946504619171"><a name="p946504619171"></a><a name="p946504619171"></a><a href="创建Secret.md">创建Secret</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9465194631716"><a name="p9465194631716"></a><a name="p9465194631716"></a>创建Secret资源类型。</p>
</td>
</tr>
<tr id="row14651046111716"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p0465446101711"><a name="p0465446101711"></a><a name="p0465446101711"></a><a href="删除Secret.md">删除Secret</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p346517462177"><a name="p346517462177"></a><a name="p346517462177"></a>删除指定Namespace下的Secret对象。</p>
</td>
</tr>
<tr id="row18465646141713"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p18465204631717"><a name="p18465204631717"></a><a name="p18465204631717"></a><a href="删除指定命名空间下所有的Secret.md">删除所有的Secret</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p17466144631718"><a name="p17466144631718"></a><a name="p17466144631718"></a>批量删除Secret。</p>
</td>
</tr>
<tr id="row246634631711"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1446664611171"><a name="p1446664611171"></a><a name="p1446664611171"></a><a href="获取Secret信息.md">获取Secret信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1346615466173"><a name="p1346615466173"></a><a name="p1346615466173"></a>获取指定Secret的详细信息。</p>
</td>
</tr>
<tr id="row646618468172"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p8466546171712"><a name="p8466546171712"></a><a name="p8466546171712"></a><a href="替换指定的Secret.md">替换指定的Secret</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9466154618172"><a name="p9466154618172"></a><a name="p9466154618172"></a>替换指定Namespace下的Secret对象。</p>
</td>
</tr>
<tr id="row1846611461178"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p546614614174"><a name="p546614614174"></a><a name="p546614614174"></a><a href="列出指定Namespace下的Secret.md">列出指定Namespace下的Secret</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614896_p20437785"><a name="zh-cn_topic_0079614896_p20437785"></a><a name="zh-cn_topic_0079614896_p20437785"></a>在指定的Namespace下列出Secret对象。</p>
</td>
</tr>
<tr id="row8466174616177"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p746634619177"><a name="p746634619177"></a><a name="p746634619177"></a><a href="列出集群下的Secret.md">列出集群下的Secret</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p846684610172"><a name="p846684610172"></a><a name="p846684610172"></a>列出集群中的所有Secret对象。</p>
</td>
</tr>
</tbody>
</table>

## RBAC<a name="section1279014445266"></a>

**表 23**  RBAC

<a name="table9795194911260"></a>
<table><thead align="left"><tr id="row5796549112610"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p102791555192715"><a name="p102791555192715"></a><a name="p102791555192715"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p92808553276"><a name="p92808553276"></a><a name="p92808553276"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row17961149162615"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p18796749112610"><a name="p18796749112610"></a><a name="p18796749112610"></a><a href="创建ClusterRole.md">创建ClusterRole</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1644811402911"><a name="p1644811402911"></a><a name="p1644811402911"></a>创建ClusterRole。</p>
</td>
</tr>
<tr id="row7796164918261"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p77960499269"><a name="p77960499269"></a><a name="p77960499269"></a><a href="更新指定的ClusterRole.md">更新指定的ClusterRole</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1444818148299"><a name="p1444818148299"></a><a name="p1444818148299"></a>部分更新指定的ClusterRole。</p>
</td>
</tr>
<tr id="row9796164916265"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p16796114916262"><a name="p16796114916262"></a><a name="p16796114916262"></a><a href="替换指定的ClusterRole.md">替换指定的ClusterRole</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p844821482910"><a name="p844821482910"></a><a name="p844821482910"></a>替换指定的ClusterRole。</p>
</td>
</tr>
<tr id="row379624910264"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p5796134962618"><a name="p5796134962618"></a><a name="p5796134962618"></a><a href="删除指定的ClusterRole.md">删除指定的ClusterRole</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p5449171402913"><a name="p5449171402913"></a><a name="p5449171402913"></a>删除指定的ClusterRole。</p>
</td>
</tr>
<tr id="row1479613491261"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1279684972611"><a name="p1279684972611"></a><a name="p1279684972611"></a><a href="批量删除ClusterRole.md">批量删除ClusterRole</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p10449171422918"><a name="p10449171422918"></a><a name="p10449171422918"></a>批量删除ClusterRole。</p>
</td>
</tr>
<tr id="row3796749172618"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p197971649162614"><a name="p197971649162614"></a><a name="p197971649162614"></a><a href="获取指定的ClusterRole.md">获取指定的ClusterRole</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p14449814192918"><a name="p14449814192918"></a><a name="p14449814192918"></a>获取指定的ClusterRole。</p>
</td>
</tr>
<tr id="row1879714496265"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p17974494267"><a name="p17974494267"></a><a name="p17974494267"></a><a href="获取ClusterRole列表.md">获取ClusterRole列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1644931416297"><a name="p1644931416297"></a><a name="p1644931416297"></a>获取ClusterRole列表。</p>
</td>
</tr>
<tr id="row12385152113416"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p15386102193417"><a name="p15386102193417"></a><a name="p15386102193417"></a><a href="创建ClusterRoleBinding.md">创建ClusterRoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9347617204114"><a name="p9347617204114"></a><a name="p9347617204114"></a>创建ClusterRoleBinding。</p>
</td>
</tr>
<tr id="row169598203419"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p12960192183411"><a name="p12960192183411"></a><a name="p12960192183411"></a><a href="更新指定的ClusterRoleBinding.md">更新指定的ClusterRoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p834761774111"><a name="p834761774111"></a><a name="p834761774111"></a>部分更新指定的ClusterRoleBinding。</p>
</td>
</tr>
<tr id="row13376066343"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11376196113417"><a name="p11376196113417"></a><a name="p11376196113417"></a><a href="替换指定的ClusterRoleBinding.md">替换指定的ClusterRoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p134871716413"><a name="p134871716413"></a><a name="p134871716413"></a>替换指定的ClusterRoleBinding。</p>
</td>
</tr>
<tr id="row5798186203411"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p879811613410"><a name="p879811613410"></a><a name="p879811613410"></a><a href="删除指定的ClusterRoleBinding.md">删除指定的ClusterRoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p83481170411"><a name="p83481170411"></a><a name="p83481170411"></a>删除指定的ClusterRoleBinding。</p>
</td>
</tr>
<tr id="row138620893416"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p108618143410"><a name="p108618143410"></a><a name="p108618143410"></a><a href="批量删除ClusterRoleBinding.md">批量删除ClusterRoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1534816175417"><a name="p1534816175417"></a><a name="p1534816175417"></a>批量删除ClusterRoleBinding。</p>
</td>
</tr>
<tr id="row159207817347"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p139206816345"><a name="p139206816345"></a><a name="p139206816345"></a><a href="获取指定的ClusterRoleBinding.md">获取指定的ClusterRoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p734801744117"><a name="p734801744117"></a><a name="p734801744117"></a>获取指定的ClusterRoleBinding。</p>
</td>
</tr>
<tr id="row57308919344"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p17306910347"><a name="p17306910347"></a><a name="p17306910347"></a><a href="获取ClusterRoleBinding列表.md">获取ClusterRoleBinding列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1734961712412"><a name="p1734961712412"></a><a name="p1734961712412"></a>获取ClusterRoleBinding列表。</p>
</td>
</tr>
<tr id="row10503110163419"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p105031110203418"><a name="p105031110203418"></a><a name="p105031110203418"></a><a href="创建Role.md">创建Role</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p4873131316421"><a name="p4873131316421"></a><a name="p4873131316421"></a>创建Role。</p>
</td>
</tr>
<tr id="row20188101116343"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p918918113347"><a name="p918918113347"></a><a name="p918918113347"></a><a href="更新指定的Role.md">更新指定的Role</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9874213174211"><a name="p9874213174211"></a><a name="p9874213174211"></a>部分更新指定的Role。</p>
</td>
</tr>
<tr id="row68933115347"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p13893121111344"><a name="p13893121111344"></a><a name="p13893121111344"></a><a href="替换指定的Role.md">替换指定的Role</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18874181318420"><a name="p18874181318420"></a><a name="p18874181318420"></a>替换指定的Role。</p>
</td>
</tr>
<tr id="row157771283413"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p14577101253416"><a name="p14577101253416"></a><a name="p14577101253416"></a><a href="删除指定的Role.md">删除指定的Role</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p687515138420"><a name="p687515138420"></a><a name="p687515138420"></a>删除指定的Role。</p>
</td>
</tr>
<tr id="row1130311133342"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p4304101316344"><a name="p4304101316344"></a><a name="p4304101316344"></a><a href="批量删除Role.md">批量删除Role</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p20875113114215"><a name="p20875113114215"></a><a name="p20875113114215"></a>批量删除Role。</p>
</td>
</tr>
<tr id="row16950813123418"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p895012137341"><a name="p895012137341"></a><a name="p895012137341"></a><a href="获取指定的Role.md">获取指定的Role</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9875713124214"><a name="p9875713124214"></a><a name="p9875713124214"></a>获取指定的Role。</p>
</td>
</tr>
<tr id="row3625191433416"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p17626171412343"><a name="p17626171412343"></a><a name="p17626171412343"></a><a href="获取指定namespace下的Role列表.md">获取指定namespace下的Role列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1787581312422"><a name="p1787581312422"></a><a name="p1787581312422"></a>列出指定namespace下的Role列表。</p>
</td>
</tr>
<tr id="row3428815103412"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p12428141518346"><a name="p12428141518346"></a><a name="p12428141518346"></a><a href="获取Role列表.md">获取Role列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p487601312421"><a name="p487601312421"></a><a name="p487601312421"></a>获取Role列表。</p>
</td>
</tr>
<tr id="row9850164414386"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p12850104493811"><a name="p12850104493811"></a><a name="p12850104493811"></a><a href="创建RoleBinding.md">创建RoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p14790163819435"><a name="p14790163819435"></a><a name="p14790163819435"></a>创建RoleBinding。</p>
</td>
</tr>
<tr id="row12422184518384"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p7422645113819"><a name="p7422645113819"></a><a name="p7422645113819"></a><a href="更新指定的RoleBinding.md">更新指定的RoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11790163814431"><a name="p11790163814431"></a><a name="p11790163814431"></a>部分更新指定的RoleBinding。</p>
</td>
</tr>
<tr id="row1299824517389"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p13998144533811"><a name="p13998144533811"></a><a name="p13998144533811"></a><a href="替换指定的RoleBinding.md">替换指定的RoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p187901538164315"><a name="p187901538164315"></a><a name="p187901538164315"></a>替换指定的RoleBinding。</p>
</td>
</tr>
<tr id="row553474623820"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p12534144643816"><a name="p12534144643816"></a><a name="p12534144643816"></a><a href="删除指定的RoleBinding.md">删除指定的RoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p8791113884313"><a name="p8791113884313"></a><a name="p8791113884313"></a>删除指定的RoleBinding。</p>
</td>
</tr>
<tr id="row13415476382"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1941347123811"><a name="p1941347123811"></a><a name="p1941347123811"></a><a href="批量删除RoleBinding.md">批量删除RoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p15792123811436"><a name="p15792123811436"></a><a name="p15792123811436"></a>批量删除RoleBinding。</p>
</td>
</tr>
<tr id="row96408470383"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p15640194712381"><a name="p15640194712381"></a><a name="p15640194712381"></a><a href="获取指定的RoleBinding.md">获取指定的RoleBinding</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p8792138144316"><a name="p8792138144316"></a><a name="p8792138144316"></a>获取指定的RoleBinding。</p>
</td>
</tr>
<tr id="row4230124883810"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p323110487381"><a name="p323110487381"></a><a name="p323110487381"></a><a href="获取指定namespace下RoleBinding列表.md">获取指定namespace下RoleBinding列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p7792938134311"><a name="p7792938134311"></a><a name="p7792938134311"></a>列出指定namespace下的RoleBinding列表。</p>
</td>
</tr>
<tr id="row895614819382"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1956748153814"><a name="p1956748153814"></a><a name="p1956748153814"></a><a href="获取RoleBinding列表.md">获取RoleBinding列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p20793938164315"><a name="p20793938164315"></a><a name="p20793938164315"></a>获取RoleBinding列表。</p>
</td>
</tr>
</tbody>
</table>

## API groups<a name="section16132195617408"></a>

**表 24**  API groups

<a name="table526181134119"></a>
<table><thead align="left"><tr id="row1426219118416"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p16575181116417"><a name="p16575181116417"></a><a name="p16575181116417"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p7575121120417"><a name="p7575121120417"></a><a name="p7575121120417"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row132622124111"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p62621915418"><a name="p62621915418"></a><a name="p62621915418"></a><a href="列出APIVersions.md">列出APIVersions</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p626241184110"><a name="p626241184110"></a><a name="p626241184110"></a>列出APIVersions。</p>
</td>
</tr>
<tr id="row192628113417"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p6262101144117"><a name="p6262101144117"></a><a name="p6262101144117"></a><a href="列出APIGroups.md">列出APIGroups</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p92621118417"><a name="p92621118417"></a><a name="p92621118417"></a>列出 APIGroups。</p>
</td>
</tr>
<tr id="row7262171134111"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p152621814416"><a name="p152621814416"></a><a name="p152621814416"></a><a href="listing-APIResources-of-GroupVersion-apiregistration-k8s-io-v1beta1.md">listing APIResources of GroupVersion apiregistration.k8s.io/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p52627154114"><a name="p52627154114"></a><a name="p52627154114"></a>列出 APIGroups。</p>
</td>
</tr>
<tr id="row15263111124117"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p20263819417"><a name="p20263819417"></a><a name="p20263819417"></a><a href="listing-APIResources-of-GroupVersion-extensions-v1beta1.md">listing APIResources of GroupVersion extensions/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1026319116412"><a name="p1026319116412"></a><a name="p1026319116412"></a>列出 APIGroups。</p>
</td>
</tr>
<tr id="row726361104119"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p162631817413"><a name="p162631817413"></a><a name="p162631817413"></a><a href="listing-APIResources-of-GroupVersion-apps-v1-apps-v1beta1.md">listing APIResources of GroupVersion apps/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1726313114119"><a name="p1726313114119"></a><a name="p1726313114119"></a>列出APIResources of Group Version "apps/v1beta1"。</p>
</td>
</tr>
<tr id="row126312116419"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1726381134119"><a name="p1726381134119"></a><a name="p1726381134119"></a><a href="listing-APIResources-of-GroupVersion-authentication-k8s-io-v1.md">listing APIResources of GroupVersion authentication.k8s.io/v1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p32635114413"><a name="p32635114413"></a><a name="p32635114413"></a>列出APIResources of GroupVersion "authentication.kubernetes.io/v1"</p>
</td>
</tr>
<tr id="row626315117412"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p82631112416"><a name="p82631112416"></a><a name="p82631112416"></a><a href="listing-APIResources-of-GroupVersion-authentication-k8s-io-v1beta1.md">listing APIResources of GroupVersion authentication.k8s.io/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p52631610416"><a name="p52631610416"></a><a name="p52631610416"></a>列出APIResources of GroupVersion "authentication.k8s.io/v1beta1"。</p>
</td>
</tr>
<tr id="row148841646134319"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1488504624319"><a name="p1488504624319"></a><a name="p1488504624319"></a><a href="listing-APIResources-of-GroupVersion-authorization-k8s-io-v1.md">listing APIResources of GroupVersion authorization.k8s.io/v1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1886134664314"><a name="p1886134664314"></a><a name="p1886134664314"></a>列出APIResources of GroupVersion "authorization.k8s.io/v1"。</p>
</td>
</tr>
<tr id="row1735315254313"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p17353175215435"><a name="p17353175215435"></a><a name="p17353175215435"></a><a href="listing-APIResources-of-GroupVersion-authorization-k8s-io-v1beta1.md">listing APIResources of GroupVersion authorization.k8s.io/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1435355214437"><a name="p1435355214437"></a><a name="p1435355214437"></a>列出APIResources of GroupVersion "authorization.k8s.io/v1beta1"。</p>
</td>
</tr>
<tr id="row1191055104317"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p179105518435"><a name="p179105518435"></a><a name="p179105518435"></a><a href="listing-APIResources-of-GroupVersion-autoscaling-v1.md">listing APIResources of GroupVersion autoscaling/v1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p2098552434"><a name="p2098552434"></a><a name="p2098552434"></a>列出APIResources of GroupVersion "autoscaling/v1"。</p>
</td>
</tr>
<tr id="row1382117493437"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p8821184984313"><a name="p8821184984313"></a><a name="p8821184984313"></a><a href="listing-APIResources-of-GroupVersion-batch-v1.md">listing APIResources of GroupVersion batch/v1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p3821164918435"><a name="p3821164918435"></a><a name="p3821164918435"></a>列出APIResources of GroupVersion "batch/v1"。</p>
</td>
</tr>
<tr id="row12872690444"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p9872189204415"><a name="p9872189204415"></a><a name="p9872189204415"></a><a href="listing-APIResources-of-GroupVersion-certificates-k8s-io-v1beta1.md">listing APIResources of GroupVersion certificates.k8s.io/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p187212910446"><a name="p187212910446"></a><a name="p187212910446"></a>列出GroupVersion "certificates.k8s.io/v1beta1"。</p>
</td>
</tr>
<tr id="row95601910104416"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p556151019446"><a name="p556151019446"></a><a name="p556151019446"></a><a href="listing-APIResources-of-GroupVersion-networking-k8s-io-v1.md">listing APIResources of GroupVersion networking.k8s.io/v1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1356161084419"><a name="p1356161084419"></a><a name="p1356161084419"></a>列出APIResources of GroupVersion "networking.k8s.io/v1"。</p>
</td>
</tr>
<tr id="row1317451134410"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11175511164417"><a name="p11175511164417"></a><a name="p11175511164417"></a><a href="listing-APIResources-of-GroupVersion-policy-v1beta1.md">listing APIResources of GroupVersion policy/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p517581112442"><a name="p517581112442"></a><a name="p517581112442"></a>列出APIResources of GroupVersion "policy/v1beta1"。</p>
</td>
</tr>
<tr id="row1977431110443"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p197741011194419"><a name="p197741011194419"></a><a name="p197741011194419"></a><a href="listing-APIResources-of-GroupVersion-rbac-authorization-k8s-io-v1beta1.md">listing APIResources of GroupVersion rbac.authorization.k8s.io/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p43091357135318"><a name="p43091357135318"></a><a name="p43091357135318"></a>列出APIResources of GroupVersion "rbac.authorization.k8s.io/v1beta1"。</p>
</td>
</tr>
<tr id="row53341124442"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p6334812134412"><a name="p6334812134412"></a><a name="p6334812134412"></a><a href="listing-APIResources-of-GroupVersion-storage-k8s-io-v1.md">listing APIResources of GroupVersion storage.k8s.io/v1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p13347123441"><a name="p13347123441"></a><a name="p13347123441"></a>列出APIResources of GroupVersion "storage.k8s.io/v1"。</p>
</td>
</tr>
<tr id="row1197831212448"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p17978212134418"><a name="p17978212134418"></a><a name="p17978212134418"></a><a href="listing-APIResources-of-GroupVersion-storage-k8s-io-v1beta1.md">listing APIResources of GroupVersion storage.k8s.io/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p097817124440"><a name="p097817124440"></a><a name="p097817124440"></a>列出APIResources of GroupVersion "storage.k8s.io/v1beta1"。</p>
</td>
</tr>
<tr id="row12580121314415"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p558120138445"><a name="p558120138445"></a><a name="p558120138445"></a><a href="listing-APIResources-of-GroupVersion-apiextensions-k8s-io-v1beta1.md">listing APIResources of GroupVersion apiextensions.k8s.io/v1beta1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1581141318442"><a name="p1581141318442"></a><a name="p1581141318442"></a>列出APIResources of GroupVersion "apiextensions.k8s.io/v1beta1"。</p>
</td>
</tr>
<tr id="row42641114164414"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p172651514154414"><a name="p172651514154414"></a><a name="p172651514154414"></a><a href="listing-APIResources-of-GroupVersion-v1.md">listing APIResources of GroupVersion v1</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p826511494414"><a name="p826511494414"></a><a name="p826511494414"></a>列出APIResources of GroupVersion "v1"。</p>
</td>
</tr>
</tbody>
</table>

## Event<a name="section1177391011383"></a>

**表 25**  Event

<a name="table97521615163812"></a>
<table><thead align="left"><tr id="row675351519389"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p1843227173815"><a name="p1843227173815"></a><a name="p1843227173815"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p0843192723813"><a name="p0843192723813"></a><a name="p0843192723813"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1575491519386"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p177541215193813"><a name="p177541215193813"></a><a name="p177541215193813"></a><a href="列出指定命名空间下的Event.md">列出指定的Event</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p19754181513388"><a name="p19754181513388"></a><a name="p19754181513388"></a>列出指定Namespace下的所有Event资源对象。</p>
</td>
</tr>
</tbody>
</table>

