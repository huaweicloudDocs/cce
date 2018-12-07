# API授权项列表<a name="cce_02_0272"></a>

<a name="table57616162812"></a>
<table><tbody><tr id="row676916172812"><td class="cellrowborder" valign="top" width="10.11101110111011%"><p id="p477220110287"><a name="p477220110287"></a><a name="p477220110287"></a><strong id="b47734112817"><a name="b47734112817"></a><a name="b47734112817"></a>模块</strong></p>
</td>
<td class="cellrowborder" valign="top" width="44.504450445044505%"><p id="p477317111282"><a name="p477317111282"></a><a name="p477317111282"></a><strong id="b177561152816"><a name="b177561152816"></a><a name="b177561152816"></a>API</strong></p>
</td>
<td class="cellrowborder" valign="top" width="23.2023202320232%"><p id="p477961192812"><a name="p477961192812"></a><a name="p477961192812"></a><strong id="b1177911182812"><a name="b1177911182812"></a><a name="b1177911182812"></a>API功能</strong></p>
</td>
<td class="cellrowborder" valign="top" width="22.182218221822183%"><p id="p20781719288"><a name="p20781719288"></a><a name="p20781719288"></a><strong id="b478216162815"><a name="b478216162815"></a><a name="b478216162815"></a>授权项</strong></p>
</td>
</tr>
<tr id="row1878371162815"><td class="cellrowborder" rowspan="13" valign="top" width="10.11101110111011%"><p id="p187841113288"><a name="p187841113288"></a><a name="p187841113288"></a>集群管理</p>
</td>
<td class="cellrowborder" valign="top" width="44.504450445044505%"><p id="p7785712287"><a name="p7785712287"></a><a name="p7785712287"></a>GET /api/v3/projects/{project_id}/clusters</p>
</td>
<td class="cellrowborder" valign="top" width="23.2023202320232%"><p id="p978915119287"><a name="p978915119287"></a><a name="p978915119287"></a>获取指定项目下的集群</p>
</td>
<td class="cellrowborder" valign="top" width="22.182218221822183%"><p id="p1791111162819"><a name="p1791111162819"></a><a name="p1791111162819"></a>cce:cluster:list</p>
</td>
</tr>
<tr id="row179691192818"><td class="cellrowborder" valign="top"><p id="p6797912287"><a name="p6797912287"></a><a name="p6797912287"></a>POST /api/v3/projects/{project_id}/clusters</p>
</td>
<td class="cellrowborder" valign="top"><p id="p2800719288"><a name="p2800719288"></a><a name="p2800719288"></a>创建集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="p980151182816"><a name="p980151182816"></a><a name="p980151182816"></a>cce:cluster:create</p>
</td>
</tr>
<tr id="row108051117287"><td class="cellrowborder" valign="top"><p id="p180721202810"><a name="p180721202810"></a><a name="p180721202810"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top"><p id="p580971172812"><a name="p580971172812"></a><a name="p580971172812"></a>获取指定的集群</p>
</td>
<td class="cellrowborder" rowspan="2" valign="top"><p id="p1081116152817"><a name="p1081116152817"></a><a name="p1081116152817"></a>cce:cluster:get</p>
</td>
</tr>
<tr id="row1182221152814"><td class="cellrowborder" valign="top"><p id="p18823914288"><a name="p18823914288"></a><a name="p18823914288"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}/clustercert</p>
</td>
<td class="cellrowborder" valign="top"><p id="p982513119286"><a name="p982513119286"></a><a name="p982513119286"></a>获取集群证书</p>
</td>
</tr>
<tr id="row182616152813"><td class="cellrowborder" valign="top"><p id="p18281118282"><a name="p18281118282"></a><a name="p18281118282"></a>PUT /api/v3/projects/{project_id}/clusters/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top"><p id="p48302018287"><a name="p48302018287"></a><a name="p48302018287"></a>更新指定的集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="p18318114282"><a name="p18318114282"></a><a name="p18318114282"></a>cce:cluster:update</p>
</td>
</tr>
<tr id="row083210119282"><td class="cellrowborder" valign="top"><p id="p178332015284"><a name="p178332015284"></a><a name="p178332015284"></a>DELETE /api/v3/projects/{project_id}/clusters/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top"><p id="p183510182818"><a name="p183510182818"></a><a name="p183510182818"></a>删除集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="p148385142814"><a name="p148385142814"></a><a name="p148385142814"></a>cce:cluster:delete</p>
</td>
</tr>
<tr id="row2086814192816"><td class="cellrowborder" valign="top"><p id="p168693122820"><a name="p168693122820"></a><a name="p168693122820"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes</p>
</td>
<td class="cellrowborder" valign="top"><p id="p687214113287"><a name="p687214113287"></a><a name="p687214113287"></a>获取集群下所有节点</p>
</td>
<td class="cellrowborder" valign="top"><p id="p12874121172813"><a name="p12874121172813"></a><a name="p12874121172813"></a>cce:node:list</p>
</td>
</tr>
<tr id="row287551112816"><td class="cellrowborder" valign="top"><p id="p20877011286"><a name="p20877011286"></a><a name="p20877011286"></a>POST /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes</p>
</td>
<td class="cellrowborder" valign="top"><p id="p16880119288"><a name="p16880119288"></a><a name="p16880119288"></a>创建节点</p>
</td>
<td class="cellrowborder" valign="top"><p id="p1388212114289"><a name="p1388212114289"></a><a name="p1388212114289"></a>cce:node:create</p>
</td>
</tr>
<tr id="row118951152810"><td class="cellrowborder" valign="top"><p id="p1189719117285"><a name="p1189719117285"></a><a name="p1189719117285"></a>PUT /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes/{node_id}</p>
</td>
<td class="cellrowborder" valign="top"><p id="p198986117287"><a name="p198986117287"></a><a name="p198986117287"></a>更新指定的节点</p>
</td>
<td class="cellrowborder" valign="top"><p id="p690010119281"><a name="p690010119281"></a><a name="p690010119281"></a>cce:node:update</p>
</td>
</tr>
<tr id="row9905111102812"><td class="cellrowborder" valign="top"><p id="p13905618285"><a name="p13905618285"></a><a name="p13905618285"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes/{node_id}</p>
</td>
<td class="cellrowborder" valign="top"><p id="p6909915288"><a name="p6909915288"></a><a name="p6909915288"></a>获取指定的节点</p>
</td>
<td class="cellrowborder" valign="top"><p id="p1891091162811"><a name="p1891091162811"></a><a name="p1891091162811"></a>cce:node:get</p>
</td>
</tr>
<tr id="row89111414286"><td class="cellrowborder" valign="top"><p id="p20912514281"><a name="p20912514281"></a><a name="p20912514281"></a>DELETE /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes/{node_id}</p>
</td>
<td class="cellrowborder" valign="top"><p id="p1591501162813"><a name="p1591501162813"></a><a name="p1591501162813"></a>删除节点</p>
</td>
<td class="cellrowborder" valign="top"><p id="p091731192810"><a name="p091731192810"></a><a name="p091731192810"></a>cce:node:delete</p>
</td>
</tr>
<tr id="row18929201172814"><td class="cellrowborder" valign="top"><p id="p493017132817"><a name="p493017132817"></a><a name="p493017132817"></a>GET /api/v3/projects/{project_id}/jobs/{job_id}</p>
</td>
<td class="cellrowborder" valign="top"><p id="p109339162810"><a name="p109339162810"></a><a name="p109339162810"></a>查询作业进度</p>
</td>
<td class="cellrowborder" valign="top"><p id="p9935317288"><a name="p9935317288"></a><a name="p9935317288"></a>cce:job:get</p>
</td>
</tr>
<tr id="row15944101192816"><td class="cellrowborder" valign="top"><p id="p1694691162815"><a name="p1694691162815"></a><a name="p1694691162815"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}/nodepools</p>
</td>
<td class="cellrowborder" valign="top"><p id="p29481111284"><a name="p29481111284"></a><a name="p29481111284"></a>获取集群下所有节点池</p>
</td>
<td class="cellrowborder" valign="top"><p id="p1194912142818"><a name="p1194912142818"></a><a name="p1194912142818"></a>cce:nodepool:list</p>
</td>
</tr>
<tr id="row179501315287"><td class="cellrowborder" rowspan="4" valign="top" width="10.11101110111011%"><p id="p195116114285"><a name="p195116114285"></a><a name="p195116114285"></a>存储管理</p>
</td>
<td class="cellrowborder" valign="top" width="44.504450445044505%"><p id="p1095313162818"><a name="p1095313162818"></a><a name="p1095313162818"></a>POST /api/v1/namespaces/{namespace}/cloudpersistentvolumeclaims</p>
</td>
<td class="cellrowborder" valign="top" width="23.2023202320232%"><p id="p795510118286"><a name="p795510118286"></a><a name="p795510118286"></a>创建PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" rowspan="2" valign="top" width="22.182218221822183%"><p id="p5955111162811"><a name="p5955111162811"></a><a name="p5955111162811"></a>cce:storage:create</p>
</td>
</tr>
<tr id="row199561217280"><td class="cellrowborder" valign="top"><p id="p18958414280"><a name="p18958414280"></a><a name="p18958414280"></a>POST /api/v1/cloudpersistentvolumes</p>
</td>
<td class="cellrowborder" valign="top"><p id="p4959519289"><a name="p4959519289"></a><a name="p4959519289"></a>创建PersistentVolume</p>
</td>
</tr>
<tr id="row1495961182814"><td class="cellrowborder" valign="top"><p id="p1496161162815"><a name="p1496161162815"></a><a name="p1496161162815"></a>DELETE /api/v1/namespaces/{namespace}/cloudpersistentvolumeclaims/{name}</p>
</td>
<td class="cellrowborder" valign="top"><p id="p6963916288"><a name="p6963916288"></a><a name="p6963916288"></a>删除PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" rowspan="2" valign="top"><p id="p6965101192820"><a name="p6965101192820"></a><a name="p6965101192820"></a>cce:storage:delete</p>
</td>
</tr>
<tr id="row7966131192813"><td class="cellrowborder" valign="top"><p id="p09687117282"><a name="p09687117282"></a><a name="p09687117282"></a>DELETE /api/v1/cloudpersistentvolumes/{name}</p>
</td>
<td class="cellrowborder" valign="top"><p id="p1097071152810"><a name="p1097071152810"></a><a name="p1097071152810"></a>删除PersistentVolume</p>
</td>
</tr>
<tr id="row9970191112811"><td class="cellrowborder" rowspan="2" valign="top" width="10.11101110111011%"><p id="p9971101102813"><a name="p9971101102813"></a><a name="p9971101102813"></a>kubernetes原生接口</p>
</td>
<td class="cellrowborder" valign="top" width="44.504450445044505%"><p id="p59712132814"><a name="p59712132814"></a><a name="p59712132814"></a>/api/*</p>
</td>
<td class="cellrowborder" rowspan="2" valign="top" width="23.2023202320232%"><p id="p1897411132811"><a name="p1897411132811"></a><a name="p1897411132811"></a>操作kubernetes资源</p>
</td>
<td class="cellrowborder" rowspan="2" valign="top" width="22.182218221822183%"><p id="p1297421192810"><a name="p1297421192810"></a><a name="p1297421192810"></a>cce:kubernetes:*</p>
</td>
</tr>
<tr id="row2976161142817"><td class="cellrowborder" valign="top"><p id="p1398016113281"><a name="p1398016113281"></a><a name="p1398016113281"></a>/apis/*</p>
</td>
</tr>
</tbody>
</table>

