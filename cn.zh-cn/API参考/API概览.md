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
<tbody><tr id="row46758134145910"><td class="cellrowborder" rowspan="6" valign="top" width="19.8%" headers="mcps1.1.4.1.1 "><p id="p1772819209011"><a name="p1772819209011"></a><a name="p1772819209011"></a>CCE接口</p>
<p id="p1360114922520"><a name="p1360114922520"></a><a name="p1360114922520"></a></p>
</td>
<td class="cellrowborder" valign="top" width="21.78%" headers="mcps1.1.4.1.2 "><p id="p19868352442"><a name="p19868352442"></a><a name="p19868352442"></a><a href="#section1921916017577">集群管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="58.42%" headers="mcps1.1.4.1.3 "><p id="p44662802145910"><a name="p44662802145910"></a><a name="p44662802145910"></a>集群管理接口，包括创建、删除集群的接口等。</p>
<p id="p3384875145910"><a name="p3384875145910"></a><a name="p3384875145910"></a>通过这些接口，您可以创建集群、获取已创建集群的信息。</p>
</td>
</tr>
<tr id="row79150261205"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7916426202013"><a name="p7916426202013"></a><a name="p7916426202013"></a><a href="#section559991319280">节点管理</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p6630122311237"><a name="p6630122311237"></a><a name="p6630122311237"></a>节点管理接口，包括创建、删除节点的接口等。</p>
<p id="p1163042313239"><a name="p1163042313239"></a><a name="p1163042313239"></a>通过这些接口，您可以为集群添加节点、获取已创建节点的信息。</p>
</td>
</tr>
<tr id="row952715513225"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1352735512217"><a name="p1352735512217"></a><a name="p1352735512217"></a><a href="#section56971705342">节点池管理</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1814325132316"><a name="p1814325132316"></a><a name="p1814325132316"></a>节点池管理接口，包括创建、删除节点池的接口等。</p>
<p id="p181422518234"><a name="p181422518234"></a><a name="p181422518234"></a>通过这些接口，您可以创建节点池、获取已创建节点池的信息。</p>
</td>
</tr>
<tr id="row85396435151"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7970931652"><a name="p7970931652"></a><a name="p7970931652"></a><a href="#section7558510185812">存储管理</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p854044313156"><a name="p854044313156"></a><a name="p854044313156"></a>存储管理接口，包括PersistentVolumeClaim的创建、删除。</p>
</td>
</tr>
<tr id="row17928112575213"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p14435181417519"><a name="p14435181417519"></a><a name="p14435181417519"></a><a href="#section146435191572">插件管理</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1492918251523"><a name="p1492918251523"></a><a name="p1492918251523"></a>插件管理接口，包括AddonTemplates的查询，AddonInstance的创建、更新、删除和获取。</p>
</td>
</tr>
<tr id="row136001495256"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p146010912516"><a name="p146010912516"></a><a name="p146010912516"></a><a href="#section13810125012265">配额管理</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1360149172518"><a name="p1360149172518"></a><a name="p1360149172518"></a>配额管理接口，支持查询CCE服务下资源配额。</p>
</td>
</tr>
<tr id="row33762552145910"><td class="cellrowborder" valign="top" width="19.8%" headers="mcps1.1.4.1.1 "><p id="p11594550145910"><a name="p11594550145910"></a><a name="p11594550145910"></a>Kubernetes原生接口</p>
</td>
<td class="cellrowborder" valign="top" width="21.78%" headers="mcps1.1.4.1.2 "><p id="p5699090519278"><a name="p5699090519278"></a><a name="p5699090519278"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="58.42%" headers="mcps1.1.4.1.3 "><p id="p4572971519278"><a name="p4572971519278"></a><a name="p4572971519278"></a>Kubernetes原生接口。</p>
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
<tr id="row1268164714123"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p18430134931216"><a name="p18430134931216"></a><a name="p18430134931216"></a><a href="获取集群证书.md">获取集群证书</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p194305493127"><a name="p194305493127"></a><a name="p194305493127"></a><span>获取指定集群的证书信息。</span></p>
</td>
</tr>
<tr id="row3198154021214"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p14611442592"><a name="p14611442592"></a><a name="p14611442592"></a><a href="获取任务信息.md">获取任务信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11873644161010"><a name="p11873644161010"></a><a name="p11873644161010"></a>查询作业进度，通过某一作业请求下发后返回的jobID来查询指定作业的进度。</p>
</td>
</tr>
</tbody>
</table>

## 节点管理<a name="section559991319280"></a>

**表 2**  节点管理

<a name="table759910133286"></a>
<table><thead align="left"><tr id="row259931322817"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p13599161332817"><a name="p13599161332817"></a><a name="p13599161332817"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p16599913182811"><a name="p16599913182811"></a><a name="p16599913182811"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row186001713112814"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p6600413172815"><a name="p6600413172815"></a><a name="p6600413172815"></a><a href="创建节点.md">创建节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p760012134281"><a name="p760012134281"></a><a name="p760012134281"></a>在指定集群下创建节点。</p>
</td>
</tr>
<tr id="row160021317281"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p9600013152817"><a name="p9600013152817"></a><a name="p9600013152817"></a><a href="获取指定的节点.md">获取指定的节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1960115132283"><a name="p1960115132283"></a><a name="p1960115132283"></a>通过节点ID获取指定节点的详细信息。</p>
</td>
</tr>
<tr id="row18601713152813"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1960111318288"><a name="p1960111318288"></a><a name="p1960111318288"></a><a href="获取集群下所有节点.md">获取集群下所有节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p116017134283"><a name="p116017134283"></a><a name="p116017134283"></a>通过集群ID获取指定集群下所有节点的详细信息。</p>
</td>
</tr>
<tr id="row16011613162815"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p20601111313286"><a name="p20601111313286"></a><a name="p20601111313286"></a><a href="更新指定的节点.md">更新指定的节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p860151302815"><a name="p860151302815"></a><a name="p860151302815"></a>更新指定的节点。</p>
</td>
</tr>
<tr id="row260191302814"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p9601131313286"><a name="p9601131313286"></a><a name="p9601131313286"></a><a href="删除节点.md">删除节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p8601141316280"><a name="p8601141316280"></a><a name="p8601141316280"></a>删除指定的节点。</p>
</td>
</tr>
<tr id="row166011313172813"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2654041122911"><a name="p2654041122911"></a><a name="p2654041122911"></a><a href="纳管节点.md">纳管节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p365411414299"><a name="p365411414299"></a><a name="p365411414299"></a><span>在指定集群下纳管节点</span>。</p>
</td>
</tr>
<tr id="row13601141322810"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p156543417292"><a name="p156543417292"></a><a name="p156543417292"></a><a href="重置节点.md">重置节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11653134111297"><a name="p11653134111297"></a><a name="p11653134111297"></a><span>在指定集群下重置节点。</span></p>
</td>
</tr>
<tr id="row1560181313289"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1465364142911"><a name="p1465364142911"></a><a name="p1465364142911"></a><a href="节点移除.md">移除节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p2652134117298"><a name="p2652134117298"></a><a name="p2652134117298"></a><span>将节点从指定集群中移除。</span></p>
</td>
</tr>
<tr id="row16601201312283"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p965274117299"><a name="p965274117299"></a><a name="p965274117299"></a><a href="节点迁移.md">迁移节点</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p14651164116294"><a name="p14651164116294"></a><a name="p14651164116294"></a><span>将节点从指定集群下迁移到另一集群</span>。</p>
</td>
</tr>
</tbody>
</table>

## 节点池管理<a name="section56971705342"></a>

**表 3**  节点池管理

<a name="table1969710103419"></a>
<table><thead align="left"><tr id="row1669811011346"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p196983053411"><a name="p196983053411"></a><a name="p196983053411"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1269815013348"><a name="p1269815013348"></a><a name="p1269815013348"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row2069816018347"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p469850163412"><a name="p469850163412"></a><a name="p469850163412"></a><a href="创建节点池.md">创建节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1969860133415"><a name="p1969860133415"></a><a name="p1969860133415"></a>在指定集群下创建节点池。</p>
</td>
</tr>
<tr id="row13698130153414"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2069830163420"><a name="p2069830163420"></a><a name="p2069830163420"></a><a href="获取指定的节点池.md">获取指定的节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p56981604348"><a name="p56981604348"></a><a name="p56981604348"></a>通过节点ID获取指定节点池的详细信息。</p>
</td>
</tr>
<tr id="row06983018348"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p146981106349"><a name="p146981106349"></a><a name="p146981106349"></a><a href="获取集群下所有节点池.md">获取集群下所有节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1869814003411"><a name="p1869814003411"></a><a name="p1869814003411"></a>通过集群ID获取指定集群下所有节点池的详细信息。</p>
</td>
</tr>
<tr id="row1869860113417"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p169811033410"><a name="p169811033410"></a><a name="p169811033410"></a><a href="更新指定节点池.md">更新指定的节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p369820113411"><a name="p369820113411"></a><a name="p369820113411"></a>更新指定的节点池。</p>
</td>
</tr>
<tr id="row96981209341"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1269812073415"><a name="p1269812073415"></a><a name="p1269812073415"></a><a href="删除节点池.md">删除节点池</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p19698804342"><a name="p19698804342"></a><a name="p19698804342"></a>删除指定的节点池。</p>
</td>
</tr>
</tbody>
</table>

## 存储管理<a name="section7558510185812"></a>

**表 4**  存储管理

<a name="table7642161835811"></a>
<table><thead align="left"><tr id="row96431718185811"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p5643118145819"><a name="p5643118145819"></a><a name="p5643118145819"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p18643191885815"><a name="p18643191885815"></a><a name="p18643191885815"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row2643518165810"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p10643171815819"><a name="p10643171815819"></a><a name="p10643171815819"></a><a href="创建PVC（待废弃）.md">创建PVC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p264311865818"><a name="p264311865818"></a><a name="p264311865818"></a>在指定的Namespace下通过云存储服务中的云存储（EVS、SFS、OBS）去创建PersistentVolumeClaim。</p>
</td>
</tr>
<tr id="row176431418185819"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p66435189586"><a name="p66435189586"></a><a name="p66435189586"></a><a href="删除PVC（待废弃）.md">删除PVC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p7644218105810"><a name="p7644218105810"></a><a name="p7644218105810"></a>删除指定Namespace下的PersistentVolumeClaim对象，并可以选择保留后端的云存储。</p>
</td>
</tr>
</tbody>
</table>

## 插件管理<a name="section146435191572"></a>

**表 5**  插件管理

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

## 配额管理<a name="section13810125012265"></a>

**表 6**  配额管理

<a name="table13235201142713"></a>
<table><thead align="left"><tr id="row1023691182712"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p18236101162714"><a name="p18236101162714"></a><a name="p18236101162714"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1236181182712"><a name="p1236181182712"></a><a name="p1236181182712"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row13236811279"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p202366118278"><a name="p202366118278"></a><a name="p202366118278"></a><a href="查询CCE服务下的资源配额.md">查询CCE服务下的资源配额</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p52362152712"><a name="p52362152712"></a><a name="p52362152712"></a><span>查询CCE服务下的资源配额。</span></p>
</td>
</tr>
</tbody>
</table>

## Kubernetes API<a name="section996118115215"></a>

<a name="table1134184152518"></a>
<table><thead align="left"><tr id="row134115442516"><th class="cellrowborder" valign="top" width="13.278672132786722%" id="mcps1.1.4.1.1"><p id="p4444714451"><a name="p4444714451"></a><a name="p4444714451"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="31.286871312868712%" id="mcps1.1.4.1.2"><p id="p108591245164418"><a name="p108591245164418"></a><a name="p108591245164418"></a>功能</p>
</th>
<th class="cellrowborder" valign="top" width="55.43445655434457%" id="mcps1.1.4.1.3"><p id="p3306134164016"><a name="p3306134164016"></a><a name="p3306134164016"></a>URI</p>
</th>
</tr>
</thead>
<tbody><tr id="row034234192519"><td class="cellrowborder" rowspan="3" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p734220410259"><a name="p734220410259"></a><a name="p734220410259"></a>Node</p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p518611332409"><a name="p518611332409"></a><a name="p518611332409"></a>获取指定的Node</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p5356962"><a name="p5356962"></a><a name="p5356962"></a>GET /api/v1/nodes/{name}</p>
</td>
</tr>
<tr id="row11801191615470"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p2080112165472"><a name="p2080112165472"></a><a name="p2080112165472"></a>列出所有的Node</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p7801141612471"><a name="p7801141612471"></a><a name="p7801141612471"></a>GET /api/v1/nodes</p>
</td>
</tr>
<tr id="row6011146472"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p41101484712"><a name="p41101484712"></a><a name="p41101484712"></a>更新指定的Node</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p65340500"><a name="p65340500"></a><a name="p65340500"></a>PATCH /api/v1/nodes/{name}</p>
</td>
</tr>
<tr id="row127941236152711"><td class="cellrowborder" rowspan="8" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p44725375145910"><a name="p44725375145910"></a><a name="p44725375145910"></a>Namespace</p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p101861933104012"><a name="p101861933104012"></a><a name="p101861933104012"></a>创建Namespace</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p13307144184015"><a name="p13307144184015"></a><a name="p13307144184015"></a>POST /api/v1/namespaces</p>
</td>
</tr>
<tr id="row176921440185710"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p269685816582"><a name="p269685816582"></a><a name="p269685816582"></a>删除Namespace</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p19693740135712"><a name="p19693740135712"></a><a name="p19693740135712"></a>DELETE /api/v1/namespaces/{name}</p>
</td>
</tr>
<tr id="row1443812111585"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p164392116588"><a name="p164392116588"></a><a name="p164392116588"></a>获取指定的Namespace</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614931_p5973303"><a name="zh-cn_topic_0079614931_p5973303"></a><a name="zh-cn_topic_0079614931_p5973303"></a>GET /api/v1/namespaces/{name}</p>
</td>
</tr>
<tr id="row1844789586"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p98452865816"><a name="p98452865816"></a><a name="p98452865816"></a>替换指定的Namespace</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1884511819588"><a name="p1884511819588"></a><a name="p1884511819588"></a>PUT /api/v1/namespaces/{name}</p>
</td>
</tr>
<tr id="row153801843587"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p8380249583"><a name="p8380249583"></a><a name="p8380249583"></a>替换指定的Namespace的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p7380847585"><a name="p7380847585"></a><a name="p7380847585"></a>PUT /api/v1/namespaces/{name}/status</p>
</td>
</tr>
<tr id="row1273231915817"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p9227131016016"><a name="p9227131016016"></a><a name="p9227131016016"></a>替换指定的Namespace的Finalize值</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615020_p1565979"><a name="zh-cn_topic_0079615020_p1565979"></a><a name="zh-cn_topic_0079615020_p1565979"></a>PUT /api/v1/namespaces/{name}/finalize</p>
</td>
</tr>
<tr id="row68671215145810"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1274319241013"><a name="p1274319241013"></a><a name="p1274319241013"></a>列出Namespace</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614949_p15165719"><a name="zh-cn_topic_0079614949_p15165719"></a><a name="zh-cn_topic_0079614949_p15165719"></a>GET /api/v1/namespaces</p>
</td>
</tr>
<tr id="row34191412145811"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1894210391003"><a name="p1894210391003"></a><a name="p1894210391003"></a>更新指定的Namespace</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614923_p19521038"><a name="zh-cn_topic_0079614923_p19521038"></a><a name="zh-cn_topic_0079614923_p19521038"></a>PATCH /api/v1/namespaces/{name}</p>
</td>
</tr>
<tr id="row124231810172813"><td class="cellrowborder" rowspan="4" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p1542341010280"><a name="p1542341010280"></a><a name="p1542341010280"></a>Resourcequotas</p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p141868338408"><a name="p141868338408"></a><a name="p141868338408"></a>获取Resourcequotas</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p13071541184015"><a name="p13071541184015"></a><a name="p13071541184015"></a>GET /api/v1/resourcequotas</p>
</td>
</tr>
<tr id="row137201859133016"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p4720205993013"><a name="p4720205993013"></a><a name="p4720205993013"></a>创建Resourcequota</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p12720459163010"><a name="p12720459163010"></a><a name="p12720459163010"></a>POST /api/v1/namespaces/{namespace}/resourcequotas</p>
</td>
</tr>
<tr id="row178101757123012"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1781025718306"><a name="p1781025718306"></a><a name="p1781025718306"></a>更新Resourcequota</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p15822047104910"><a name="p15822047104910"></a><a name="p15822047104910"></a>PUT /api/v1/namespaces/{namespace}/resourcequotas/{name}</p>
</td>
</tr>
<tr id="row520275212305"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p720335263012"><a name="p720335263012"></a><a name="p720335263012"></a>删除Resourcequota</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p946914519320"><a name="p946914519320"></a><a name="p946914519320"></a>DELETE /api/v1/namespaces/{namespace}/resourcequotas/{name}</p>
</td>
</tr>
<tr id="row205721428203112"><td class="cellrowborder" rowspan="9" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p49554995145910"><a name="p49554995145910"></a><a name="p49554995145910"></a>Pod</p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p14246348131"><a name="p14246348131"></a><a name="p14246348131"></a>创建Pod</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0079615001_p23885112"><a name="zh-cn_topic_0079615001_p23885112"></a><a name="zh-cn_topic_0079615001_p23885112"></a>POST /api/v1/namespaces/{namespace}/pods</p>
</td>
</tr>
<tr id="row8696165319318"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p18696753734"><a name="p18696753734"></a><a name="p18696753734"></a>删除Pod</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p769665320320"><a name="p769665320320"></a><a name="p769665320320"></a>DELETE /api/v1/namespaces/{namespace}/pods/{name}</p>
</td>
</tr>
<tr id="row8831175615317"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p163531038518"><a name="p163531038518"></a><a name="p163531038518"></a>删除所有的Pod</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1083112561238"><a name="p1083112561238"></a><a name="p1083112561238"></a>DELETE /api/v1/namespaces/{namespace}/pods</p>
</td>
</tr>
<tr id="row41761192413"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p71761598410"><a name="p71761598410"></a><a name="p71761598410"></a>获取指定的Pod</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p3176591420"><a name="p3176591420"></a><a name="p3176591420"></a>GET /api/v1/namespaces/{namespace}/pods/{name}</p>
</td>
</tr>
<tr id="row1079111112411"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p76188421057"><a name="p76188421057"></a><a name="p76188421057"></a>替换指定的Pod</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1779111111041"><a name="p1779111111041"></a><a name="p1779111111041"></a>PUT /api/v1/namespaces/{namespace}/pods/{name}</p>
</td>
</tr>
<tr id="row1673111410419"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p156733141648"><a name="p156733141648"></a><a name="p156733141648"></a>替换指定的Pod的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614908_p16802851"><a name="zh-cn_topic_0079614908_p16802851"></a><a name="zh-cn_topic_0079614908_p16802851"></a>PUT /api/v1/namespaces/{namespace}/pods/{name}/status</p>
</td>
</tr>
<tr id="row019961718413"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p619918171140"><a name="p619918171140"></a><a name="p619918171140"></a>列出指定Namespaces下的所有Pod</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615024_p25896589"><a name="zh-cn_topic_0079615024_p25896589"></a><a name="zh-cn_topic_0079615024_p25896589"></a>GET /api/v1/namespaces/{namespace}/pods</p>
</td>
</tr>
<tr id="row1387152219414"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1787114222415"><a name="p1787114222415"></a><a name="p1787114222415"></a>列出Pod</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614951_p225290"><a name="zh-cn_topic_0079614951_p225290"></a><a name="zh-cn_topic_0079614951_p225290"></a>GET /api/v1/pods</p>
</td>
</tr>
<tr id="row2016817201411"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p61688202415"><a name="p61688202415"></a><a name="p61688202415"></a>更新指定的Pod</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614948_p2556583"><a name="zh-cn_topic_0079614948_p2556583"></a><a name="zh-cn_topic_0079614948_p2556583"></a>PATCH /api/v1/namespaces/{namespace}/pods/{name}</p>
</td>
</tr>
<tr id="row19515163917311"><td class="cellrowborder" rowspan="15" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p379336831112"><a name="p379336831112"></a><a name="p379336831112"></a>Deployment</p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p121861033164015"><a name="p121861033164015"></a><a name="p121861033164015"></a>创建Deployment</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p11307114144010"><a name="p11307114144010"></a><a name="p11307114144010"></a>POST /apis/apps/v1/namespaces/{namespace}/deployments</p>
</td>
</tr>
<tr id="row641862313119"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p24184231111"><a name="p24184231111"></a><a name="p24184231111"></a>创建Deployment的回滚操作</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p10863195414914"><a name="p10863195414914"></a><a name="p10863195414914"></a>PATCH /apis/apps/v1/namespaces/{namespace}/deployments/{name} （仅适用于1.17及以上版本的集群）</p>
<p id="p13496002"><a name="p13496002"></a><a name="p13496002"></a>POST /apis/apps/v1beta1/namespaces/{namespace}/deployments/{name}/rollback （仅适用于1.15及以下版本的集群）</p>
<p id="p1499555"><a name="p1499555"></a><a name="p1499555"></a>POST /apis/extensions/v1beta1/namespaces/{namespace}/deployments/{name}/rollback （仅适用于1.15及以下版本的集群）</p>
</td>
</tr>
<tr id="row481413251113"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p9814173210117"><a name="p9814173210117"></a><a name="p9814173210117"></a>删除Deployment</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1781463218110"><a name="p1781463218110"></a><a name="p1781463218110"></a>DELETE /apis/apps/v1/namespaces/{namespace}/deployments/{name}</p>
</td>
</tr>
<tr id="row3449330131116"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1450830101118"><a name="p1450830101118"></a><a name="p1450830101118"></a>删除所有的Deployment</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p204502301113"><a name="p204502301113"></a><a name="p204502301113"></a>DELETE /apis/apps/v1/namespaces/{namespace}/deployments</p>
</td>
</tr>
<tr id="row192971028191120"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p16564853131411"><a name="p16564853131411"></a><a name="p16564853131411"></a>获取指定的Deployment</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p029732812119"><a name="p029732812119"></a><a name="p029732812119"></a>GET /apis/apps/v1/namespaces/{namespace}/deployments/{name}</p>
</td>
</tr>
<tr id="row1416864716108"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1816920479102"><a name="p1816920479102"></a><a name="p1816920479102"></a>获取指定的Deployment的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p2169144721020"><a name="p2169144721020"></a><a name="p2169144721020"></a>GET /apis/apps/v1/namespaces/{namespace}/deployments/{name}/status</p>
</td>
</tr>
<tr id="row2306518131120"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p330619181118"><a name="p330619181118"></a><a name="p330619181118"></a>获取指定的Deployment的伸缩操作</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p330631851112"><a name="p330631851112"></a><a name="p330631851112"></a>GET /apis/apps/v1/namespaces/{namespace}/deployments/{name}/scale</p>
</td>
</tr>
<tr id="row252102114118"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p85342111112"><a name="p85342111112"></a><a name="p85342111112"></a>替换指定的Deployment</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p125352111116"><a name="p125352111116"></a><a name="p125352111116"></a>PUT /apis/apps/v1/namespaces/{namespace}/deployments/{name}</p>
</td>
</tr>
<tr id="row4864192171118"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p68645261119"><a name="p68645261119"></a><a name="p68645261119"></a>替换指定的Deployment的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1027875518326"><a name="p1027875518326"></a><a name="p1027875518326"></a>PUT /apis/apps/v1/namespaces/{namespace}/deployments/{name}/status</p>
</td>
</tr>
<tr id="row9564151381119"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p115647136119"><a name="p115647136119"></a><a name="p115647136119"></a>替换指定的Deployment的伸缩操作</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p8155161363313"><a name="p8155161363313"></a><a name="p8155161363313"></a>PUT /apis/apps/v1/namespaces/{namespace}/deployments/{name}/scale</p>
</td>
</tr>
<tr id="row9915175917109"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p49151759111016"><a name="p49151759111016"></a><a name="p49151759111016"></a>列出指定Namespace下的Deployment</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p22991240163317"><a name="p22991240163317"></a><a name="p22991240163317"></a>GET /apis/apps/v1/namespaces/{namespace}/deployments</p>
</td>
</tr>
<tr id="row948925720103"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p19489357111019"><a name="p19489357111019"></a><a name="p19489357111019"></a>列出所有的Deployment</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p153111593332"><a name="p153111593332"></a><a name="p153111593332"></a>GET /apis/apps/v1/deployments</p>
</td>
</tr>
<tr id="row189121654161017"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p49121954101013"><a name="p49121954101013"></a><a name="p49121954101013"></a>更新指定的Deployment</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p139121254121011"><a name="p139121254121011"></a><a name="p139121254121011"></a>PATCH /apis/apps/v1/namespaces/{namespace}/deployments/{name}</p>
</td>
</tr>
<tr id="row1630752181014"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p93045210101"><a name="p93045210101"></a><a name="p93045210101"></a>更新指定的Deployment的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p23035221017"><a name="p23035221017"></a><a name="p23035221017"></a>PATCH /apis/apps/v1/namespaces/{namespace}/deployments/{name}/status</p>
</td>
</tr>
<tr id="row166589185"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p031018132189"><a name="p031018132189"></a><a name="p031018132189"></a>更新指定的Deployment的伸缩操作</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p868810189"><a name="p868810189"></a><a name="p868810189"></a>PATCH /apis/apps/v1/namespaces/{namespace}/deployments/{name}/scale</p>
</td>
</tr>
<tr id="row7980195320316"><td class="cellrowborder" rowspan="11" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p1267985011044"><a name="p1267985011044"></a><a name="p1267985011044"></a>Statefulset</p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p93272602315"><a name="p93272602315"></a><a name="p93272602315"></a>创建StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p16372123412277"><a name="p16372123412277"></a><a name="p16372123412277"></a>POST /apis/apps/v1/namespaces/{namespace}/statefulsets</p>
</td>
</tr>
<tr id="row148641428132216"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1986462819229"><a name="p1986462819229"></a><a name="p1986462819229"></a>删除指定的StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p198641228132215"><a name="p198641228132215"></a><a name="p198641228132215"></a>DELETE /apis/apps/v1/namespaces/{namespace}/statefulsets/{name}</p>
</td>
</tr>
<tr id="row1869731562213"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1969731572219"><a name="p1969731572219"></a><a name="p1969731572219"></a>删除所有的StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p5697121512229"><a name="p5697121512229"></a><a name="p5697121512229"></a>DELETE /apis/apps/v1/namespaces/{namespace}/statefulsets</p>
</td>
</tr>
<tr id="row17289114715226"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1128994710224"><a name="p1128994710224"></a><a name="p1128994710224"></a>获取指定的StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1228964762214"><a name="p1228964762214"></a><a name="p1228964762214"></a>GET /apis/apps/v1/namespaces/{namespace}/statefulsets/{name}</p>
</td>
</tr>
<tr id="row131922506221"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p4192105072217"><a name="p4192105072217"></a><a name="p4192105072217"></a>获取指定的StatefulSet的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p133631931122413"><a name="p133631931122413"></a><a name="p133631931122413"></a>GET /apis/apps/v1/namespaces/{namespace}/statefulsets/{name}/status</p>
</td>
</tr>
<tr id="row12336153672220"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p0336123632216"><a name="p0336123632216"></a><a name="p0336123632216"></a>替换指定的StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1133653617228"><a name="p1133653617228"></a><a name="p1133653617228"></a>PUT /apis/apps/v1/namespaces/{namespace}/statefulsets/{name}</p>
</td>
</tr>
<tr id="row78906332221"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p28905338224"><a name="p28905338224"></a><a name="p28905338224"></a>替换指定的StatefulSet的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p789023312228"><a name="p789023312228"></a><a name="p789023312228"></a>PUT /apis/apps/v1/namespaces/{namespace}/statefulsets/{name}/status</p>
</td>
</tr>
<tr id="row135351658132213"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p253512581226"><a name="p253512581226"></a><a name="p253512581226"></a>列出指定Namespace下的StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p17535175817225"><a name="p17535175817225"></a><a name="p17535175817225"></a>GET /apis/apps/v1/namespaces/{namespace}/statefulsets</p>
</td>
</tr>
<tr id="row2606183132215"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p10784105772510"><a name="p10784105772510"></a><a name="p10784105772510"></a>列出所有的StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1030971092611"><a name="p1030971092611"></a><a name="p1030971092611"></a>GET /apis/apps/v1/statefulsets</p>
</td>
</tr>
<tr id="row9360823102216"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7460815142614"><a name="p7460815142614"></a><a name="p7460815142614"></a>更新指定的StatefulSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p13360192310225"><a name="p13360192310225"></a><a name="p13360192310225"></a>PATCH /apis/apps/v1/namespaces/{namespace}/statefulsets/{name}</p>
</td>
</tr>
<tr id="row14289102617221"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1696283622618"><a name="p1696283622618"></a><a name="p1696283622618"></a>更新指定的StatefulSet的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p842824917268"><a name="p842824917268"></a><a name="p842824917268"></a>PATCH /apis/apps/v1/namespaces/{namespace}/statefulsets/{name}/status</p>
</td>
</tr>
<tr id="row1949954320"><td class="cellrowborder" rowspan="11" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p4671625719274"><a name="p4671625719274"></a><a name="p4671625719274"></a>Daemonset</p>
<p id="p43674211290"><a name="p43674211290"></a><a name="p43674211290"></a></p>
<p id="p1161219453290"><a name="p1161219453290"></a><a name="p1161219453290"></a></p>
<p id="p7541204814291"><a name="p7541204814291"></a><a name="p7541204814291"></a></p>
<p id="p94196531298"><a name="p94196531298"></a><a name="p94196531298"></a></p>
<p id="p893155612910"><a name="p893155612910"></a><a name="p893155612910"></a></p>
<p id="p1675195932915"><a name="p1675195932915"></a><a name="p1675195932915"></a></p>
<p id="p156341313018"><a name="p156341313018"></a><a name="p156341313018"></a></p>
<p id="p1922918673014"><a name="p1922918673014"></a><a name="p1922918673014"></a></p>
<p id="p161120516295"><a name="p161120516295"></a><a name="p161120516295"></a></p>
<p id="p1561683719295"><a name="p1561683719295"></a><a name="p1561683719295"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p3186033114010"><a name="p3186033114010"></a><a name="p3186033114010"></a>创建DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p1030754174016"><a name="p1030754174016"></a><a name="p1030754174016"></a>POST /apis/apps/v1/namespaces/{namespace}/daemonsets</p>
</td>
</tr>
<tr id="row53616428296"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p91791836183017"><a name="p91791836183017"></a><a name="p91791836183017"></a>删除指定的DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p041125020307"><a name="p041125020307"></a><a name="p041125020307"></a>DELETE /apis/apps/v1/namespaces/{namespace}/daemonsets/{name}</p>
</td>
</tr>
<tr id="row1561213454291"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p4612134512291"><a name="p4612134512291"></a><a name="p4612134512291"></a>删除所有的Daemonset</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p111115911337"><a name="p111115911337"></a><a name="p111115911337"></a>DELETE /apis/apps/v1/namespaces/{namespace}/daemonsets</p>
</td>
</tr>
<tr id="row6541248112919"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p876811493320"><a name="p876811493320"></a><a name="p876811493320"></a>获取指定的DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p19111133373312"><a name="p19111133373312"></a><a name="p19111133373312"></a>GET /apis/apps/v1/namespaces/{namespace}/daemonsets/{name}</p>
</td>
</tr>
<tr id="row144191453102911"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7419185362915"><a name="p7419185362915"></a><a name="p7419185362915"></a>获取指定的DaemonSet的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1964015718333"><a name="p1964015718333"></a><a name="p1964015718333"></a>GET /apis/apps/v1/namespaces/{namespace}/daemonsets/{name}/status</p>
</td>
</tr>
<tr id="row2931756152918"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p193205642916"><a name="p193205642916"></a><a name="p193205642916"></a>更新指定的DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p14925137343"><a name="p14925137343"></a><a name="p14925137343"></a>PATCH /apis/apps/v1/namespaces/{namespace}/daemonsets/{name}</p>
</td>
</tr>
<tr id="row18757596293"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p475115992918"><a name="p475115992918"></a><a name="p475115992918"></a>更新指定的DaemonSet的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p175359192914"><a name="p175359192914"></a><a name="p175359192914"></a>PATCH /apis/apps/v1/namespaces/{namespace}/daemonsets/{name}/status</p>
</td>
</tr>
<tr id="row363419303010"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1963410312305"><a name="p1963410312305"></a><a name="p1963410312305"></a>列出所有的DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p863413315307"><a name="p863413315307"></a><a name="p863413315307"></a>GET /apis/apps/v1/daemonsets</p>
</td>
</tr>
<tr id="row1229966304"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p222920612308"><a name="p222920612308"></a><a name="p222920612308"></a>列出指定Namespace下的DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1462477133516"><a name="p1462477133516"></a><a name="p1462477133516"></a>GET /apis/apps/v1/namespaces/{namespace}/daemonsets</p>
</td>
</tr>
<tr id="row1111513297"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1311105118298"><a name="p1311105118298"></a><a name="p1311105118298"></a>替换指定的DaemonSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p311151182916"><a name="p311151182916"></a><a name="p311151182916"></a>PUT /apis/apps/v1/namespaces/{namespace}/daemonsets/{name}</p>
</td>
</tr>
<tr id="row7616153716293"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1361643713294"><a name="p1361643713294"></a><a name="p1361643713294"></a>替换指定的DaemonSet的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p196162375291"><a name="p196162375291"></a><a name="p196162375291"></a>PUT /apis/apps/v1/namespaces/{namespace}/daemonsets/{name}/status</p>
</td>
</tr>
<tr id="row10260164310320"><td class="cellrowborder" rowspan="11" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p3094168219276"><a name="p3094168219276"></a><a name="p3094168219276"></a>Job</p>
<p id="p1396162510575"><a name="p1396162510575"></a><a name="p1396162510575"></a></p>
<p id="p17593728205714"><a name="p17593728205714"></a><a name="p17593728205714"></a></p>
<p id="p1962533113577"><a name="p1962533113577"></a><a name="p1962533113577"></a></p>
<p id="p18183618572"><a name="p18183618572"></a><a name="p18183618572"></a></p>
<p id="p1354320411918"><a name="p1354320411918"></a><a name="p1354320411918"></a></p>
<p id="p1951511441912"><a name="p1951511441912"></a><a name="p1951511441912"></a></p>
<p id="p12349120220"><a name="p12349120220"></a><a name="p12349120220"></a></p>
<p id="p3105245217"><a name="p3105245217"></a><a name="p3105245217"></a></p>
<p id="p63478348210"><a name="p63478348210"></a><a name="p63478348210"></a></p>
<p id="p316214475214"><a name="p316214475214"></a><a name="p316214475214"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p1518673313403"><a name="p1518673313403"></a><a name="p1518673313403"></a>创建Job</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p12307184154018"><a name="p12307184154018"></a><a name="p12307184154018"></a>POST /apis/batch/v1/namespaces/{namespace}/jobs</p>
</td>
</tr>
<tr id="row83964259571"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1418314389016"><a name="p1418314389016"></a><a name="p1418314389016"></a>删除Job</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p979713225313"><a name="p979713225313"></a><a name="p979713225313"></a>DELETE /apis/batch/v1/namespaces/{namespace}/jobs/{name}</p>
</td>
</tr>
<tr id="row8593172845713"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1859372814579"><a name="p1859372814579"></a><a name="p1859372814579"></a>删除所有的Job</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p134611361320"><a name="p134611361320"></a><a name="p134611361320"></a>DELETE /apis/batch/v1/namespaces/{namespace}/jobs</p>
</td>
</tr>
<tr id="row6624143119579"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p136251731185717"><a name="p136251731185717"></a><a name="p136251731185717"></a>获取指定的Job</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p56251331145713"><a name="p56251331145713"></a><a name="p56251331145713"></a>GET /apis/batch/v1/namespaces/{namespace}/jobs/{name}</p>
</td>
</tr>
<tr id="row1381113617578"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1681103615579"><a name="p1681103615579"></a><a name="p1681103615579"></a>获取指定的Job的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p10364359239"><a name="p10364359239"></a><a name="p10364359239"></a>GET /apis/batch/v1/namespaces/{namespace}/jobs/{name}/status</p>
</td>
</tr>
<tr id="row1154214411113"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p13543441818"><a name="p13543441818"></a><a name="p13543441818"></a>替换指定的Job</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p25229347"><a name="p25229347"></a><a name="p25229347"></a>PUT /apis/batch/v1/namespaces/{namespace}/jobs/{name}</p>
</td>
</tr>
<tr id="row175155441614"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p205151441312"><a name="p205151441312"></a><a name="p205151441312"></a>替换指定的Job的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p18407324544"><a name="p18407324544"></a><a name="p18407324544"></a>PUT /apis/batch/v1/namespaces/{namespace}/jobs/{name}/status</p>
</td>
</tr>
<tr id="row1923414121628"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p18234101219210"><a name="p18234101219210"></a><a name="p18234101219210"></a>列出指定Namespace下的Job</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p92343121925"><a name="p92343121925"></a><a name="p92343121925"></a>GET /apis/batch/v1/namespaces/{namespace}/jobs</p>
</td>
</tr>
<tr id="row210924825"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p37351129523"><a name="p37351129523"></a><a name="p37351129523"></a>列出所有Job</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p33414562"><a name="p33414562"></a><a name="p33414562"></a>GET /apis/batch/v1/jobs</p>
</td>
</tr>
<tr id="row1834718341326"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p113471534329"><a name="p113471534329"></a><a name="p113471534329"></a>更新指定的Job的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p47779422"><a name="p47779422"></a><a name="p47779422"></a>PATCH /apis/batch/v1/namespaces/{namespace}/jobs/{name}/status</p>
</td>
</tr>
<tr id="row161611147223"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1416264719218"><a name="p1416264719218"></a><a name="p1416264719218"></a>更新指定的Job</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p14624719"><a name="p14624719"></a><a name="p14624719"></a>PATCH /apis/batch/v1/namespaces/{namespace}/jobs/{name}</p>
</td>
</tr>
<tr id="row175471579568"><td class="cellrowborder" rowspan="11" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p184360125719"><a name="p184360125719"></a><a name="p184360125719"></a>CronJob</p>
<p id="p1173612583369"><a name="p1173612583369"></a><a name="p1173612583369"></a></p>
<p id="p1791122120366"><a name="p1791122120366"></a><a name="p1791122120366"></a></p>
<p id="p19791151833612"><a name="p19791151833612"></a><a name="p19791151833612"></a></p>
<p id="p1682862412363"><a name="p1682862412363"></a><a name="p1682862412363"></a></p>
<p id="p61931028183618"><a name="p61931028183618"></a><a name="p61931028183618"></a></p>
<p id="p148712407369"><a name="p148712407369"></a><a name="p148712407369"></a></p>
<p id="p89027388362"><a name="p89027388362"></a><a name="p89027388362"></a></p>
<p id="p176944353362"><a name="p176944353362"></a><a name="p176944353362"></a></p>
<p id="p10381133117369"><a name="p10381133117369"></a><a name="p10381133117369"></a></p>
<p id="p6417151633618"><a name="p6417151633618"></a><a name="p6417151633618"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p1443306571"><a name="p1443306571"></a><a name="p1443306571"></a>创建CronJob</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p443200125718"><a name="p443200125718"></a><a name="p443200125718"></a>POST /apis/batch/v1beta1/namespaces/{namespace}/cronjobs</p>
</td>
</tr>
<tr id="row177361586366"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1051981213401"><a name="p1051981213401"></a><a name="p1051981213401"></a>删除CronJob</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p14722502"><a name="p14722502"></a><a name="p14722502"></a>DELETE /apis/batch/v1beta1/namespaces/{namespace}/cronjobs/{name}</p>
</td>
</tr>
<tr id="row13791152116361"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p4791132163619"><a name="p4791132163619"></a><a name="p4791132163619"></a>删除所有的CronJob</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p17217497"><a name="p17217497"></a><a name="p17217497"></a>DELETE /apis/batch/v1beta1/namespaces/{namespace}/cronjobs</p>
</td>
</tr>
<tr id="row57911818153617"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p193531451104014"><a name="p193531451104014"></a><a name="p193531451104014"></a>获取指定的CronJob</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p5525626"><a name="p5525626"></a><a name="p5525626"></a>GET /apis/batch/v1beta1/namespaces/{namespace}/cronjobs/{name}</p>
</td>
</tr>
<tr id="row1182811242363"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1946318784118"><a name="p1946318784118"></a><a name="p1946318784118"></a>获取指定的CronJob的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p59499602"><a name="p59499602"></a><a name="p59499602"></a>GET /apis/batch/v1beta1/namespaces/{namespace}/cronjobs/{name}/status</p>
</td>
</tr>
<tr id="row111931128123619"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p19821025154114"><a name="p19821025154114"></a><a name="p19821025154114"></a>替换指定的CronJob</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p51931028153610"><a name="p51931028153610"></a><a name="p51931028153610"></a>PUT /apis/batch/v1beta1/namespaces/{namespace}/cronjobs/{name}</p>
</td>
</tr>
<tr id="row1387094013363"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7871104013365"><a name="p7871104013365"></a><a name="p7871104013365"></a>替换指定的CronJob的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1482944"><a name="p1482944"></a><a name="p1482944"></a>PUT /apis/batch/v1beta1/namespaces/{namespace}/cronjobs/{name}/status</p>
</td>
</tr>
<tr id="row790123863614"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p167531711427"><a name="p167531711427"></a><a name="p167531711427"></a>列出指定Namespace下的CronJob</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p19528317"><a name="p19528317"></a><a name="p19528317"></a>GET /apis/batch/v1beta1/namespaces/{namespace}/cronjobs</p>
</td>
</tr>
<tr id="row56936351369"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p14694133503613"><a name="p14694133503613"></a><a name="p14694133503613"></a>列出所有的CronJob</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1669419357365"><a name="p1669419357365"></a><a name="p1669419357365"></a>GET /apis/batch/v1beta1/cronjobs</p>
</td>
</tr>
<tr id="row12381143116368"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p438212316369"><a name="p438212316369"></a><a name="p438212316369"></a>更新指定的CronJob的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p6382153123613"><a name="p6382153123613"></a><a name="p6382153123613"></a>PATCH /apis/batch/v1beta1/namespaces/{namespace}/cronjobs/{name}/status</p>
</td>
</tr>
<tr id="row10416181673610"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p184172162360"><a name="p184172162360"></a><a name="p184172162360"></a>更新指定的CronJob</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p341761610368"><a name="p341761610368"></a><a name="p341761610368"></a>PATCH /apis/batch/v1beta1/namespaces/{namespace}/cronjobs/{name}</p>
</td>
</tr>
<tr id="row1419213219339"><td class="cellrowborder" rowspan="3" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p6028906019279"><a name="p6028906019279"></a><a name="p6028906019279"></a>ReplicaSet</p>
<p id="p13551801968"><a name="p13551801968"></a><a name="p13551801968"></a></p>
<p id="p1838143465"><a name="p1838143465"></a><a name="p1838143465"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p625919448514"><a name="p625919448514"></a><a name="p625919448514"></a>列出指定的ReplicaSet</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p14307194174018"><a name="p14307194174018"></a><a name="p14307194174018"></a>GET /apis/apps/v1/namespaces/{namespace}/replicasets</p>
</td>
</tr>
<tr id="row8355901064"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p935570868"><a name="p935570868"></a><a name="p935570868"></a>获取指定的ReplicaSet</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p6355501260"><a name="p6355501260"></a><a name="p6355501260"></a>GET /apis/apps/v1/namespaces/{namespace}/replicasets/{name}</p>
</td>
</tr>
<tr id="row1738531768"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p107813262612"><a name="p107813262612"></a><a name="p107813262612"></a>获取Replicasets</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1474617321187"><a name="p1474617321187"></a><a name="p1474617321187"></a>GET /apis/apps/v1/replicasets</p>
</td>
</tr>
<tr id="row10957421145910"><td class="cellrowborder" rowspan="9" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p30771534145910"><a name="p30771534145910"></a><a name="p30771534145910"></a>ReplicationController</p>
<p id="p623819131718"><a name="p623819131718"></a><a name="p623819131718"></a></p>
<p id="p151491817372"><a name="p151491817372"></a><a name="p151491817372"></a></p>
<p id="p9662023876"><a name="p9662023876"></a><a name="p9662023876"></a></p>
<p id="p1596782613718"><a name="p1596782613718"></a><a name="p1596782613718"></a></p>
<p id="p48942331977"><a name="p48942331977"></a><a name="p48942331977"></a></p>
<p id="p17758163619717"><a name="p17758163619717"></a><a name="p17758163619717"></a></p>
<p id="p43445391670"><a name="p43445391670"></a><a name="p43445391670"></a></p>
<p id="p166720201572"><a name="p166720201572"></a><a name="p166720201572"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p11867334406"><a name="p11867334406"></a><a name="p11867334406"></a>创建ReplicationController</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0079615078_p66883292"><a name="zh-cn_topic_0079615078_p66883292"></a><a name="zh-cn_topic_0079615078_p66883292"></a>POST /api/v1/namespaces/{namespace}/replicationcontrollers</p>
</td>
</tr>
<tr id="row16238131320712"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p52387132710"><a name="p52387132710"></a><a name="p52387132710"></a>删除ReplicationController</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p142382013774"><a name="p142382013774"></a><a name="p142382013774"></a>DELETE /api/v1/namespaces/{namespace}/replicationcontrollers/{name}</p>
</td>
</tr>
<tr id="row6149917376"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p141495171777"><a name="p141495171777"></a><a name="p141495171777"></a>删除所有的ReplicationController</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p31949389"><a name="p31949389"></a><a name="p31949389"></a>DELETE /api/v1/namespaces/{namespace}/replicationcontrollers</p>
</td>
</tr>
<tr id="row866210231278"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p86621423976"><a name="p86621423976"></a><a name="p86621423976"></a>获取指定Namespace下的ReplicationController</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614960_p23141731"><a name="zh-cn_topic_0079614960_p23141731"></a><a name="zh-cn_topic_0079614960_p23141731"></a>GET /api/v1/namespaces/{namespace}/replicationcontrollers/{name}</p>
</td>
</tr>
<tr id="row1596715261075"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p596719263715"><a name="p596719263715"></a><a name="p596719263715"></a>替换指定Namespace下的ReplicationController</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615034_p37094046"><a name="zh-cn_topic_0079615034_p37094046"></a><a name="zh-cn_topic_0079615034_p37094046"></a>PUT /api/v1/namespaces/{namespace}/replicationcontrollers/{name}</p>
</td>
</tr>
<tr id="row118941733872"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1548191481318"><a name="p1548191481318"></a><a name="p1548191481318"></a>替换指定Namespace下的ReplicationController状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1689413332718"><a name="p1689413332718"></a><a name="p1689413332718"></a>PUT /api/v1/namespaces/{namespace}/replicationcontrollers/{name}/status</p>
</td>
</tr>
<tr id="row15758193620716"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p193253616131"><a name="p193253616131"></a><a name="p193253616131"></a>列出指定Namespace下的ReplicationController</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615054_p24031405"><a name="zh-cn_topic_0079615054_p24031405"></a><a name="zh-cn_topic_0079615054_p24031405"></a>GET /api/v1/namespaces/{namespace}/replicationcontrollers</p>
</td>
</tr>
<tr id="row834312391174"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p289651131313"><a name="p289651131313"></a><a name="p289651131313"></a>列出ReplicationController</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614978_p17977942"><a name="zh-cn_topic_0079614978_p17977942"></a><a name="zh-cn_topic_0079614978_p17977942"></a>GET /api/v1/replicationcontrollers</p>
</td>
</tr>
<tr id="row9672520674"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p5825621412"><a name="p5825621412"></a><a name="p5825621412"></a>更新指定的ReplicationController</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615044_p66090286"><a name="zh-cn_topic_0079615044_p66090286"></a><a name="zh-cn_topic_0079615044_p66090286"></a>PATCH /api/v1/namespaces/{namespace}/replicationcontrollers/{name}</p>
</td>
</tr>
<tr id="row68481325181518"><td class="cellrowborder" rowspan="8" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p1412513962011"><a name="p1412513962011"></a><a name="p1412513962011"></a>Endpoints</p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p025425441618"><a name="p025425441618"></a><a name="p025425441618"></a>创建Endpoints</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0079614955_p55629438"><a name="zh-cn_topic_0079614955_p55629438"></a><a name="zh-cn_topic_0079614955_p55629438"></a>POST /api/v1/namespaces/{namespace}/endpoints</p>
</td>
</tr>
<tr id="row592033915159"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1164217651712"><a name="p1164217651712"></a><a name="p1164217651712"></a>删除Endpoints</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614926_p38742975"><a name="zh-cn_topic_0079614926_p38742975"></a><a name="zh-cn_topic_0079614926_p38742975"></a>DELETE /api/v1/namespaces/{namespace}/endpoints/{name}</p>
</td>
</tr>
<tr id="row1722615127169"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1299310425171"><a name="p1299310425171"></a><a name="p1299310425171"></a>删除所有的Endpoints</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p14226121211163"><a name="p14226121211163"></a><a name="p14226121211163"></a>DELETE /api/v1/namespaces/{namespace}/endpoints</p>
</td>
</tr>
<tr id="row6537917181617"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p10167117186"><a name="p10167117186"></a><a name="p10167117186"></a>获取指定的Endpoints</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615072_p9185002"><a name="zh-cn_topic_0079615072_p9185002"></a><a name="zh-cn_topic_0079615072_p9185002"></a>GET /api/v1/namespaces/{namespace}/endpoints/{name}</p>
</td>
</tr>
<tr id="row1833672111166"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p144682316184"><a name="p144682316184"></a><a name="p144682316184"></a>替换指定的Endpoints</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p633614210165"><a name="p633614210165"></a><a name="p633614210165"></a>PUT /api/v1/namespaces/{namespace}/endpoints/{name}</p>
</td>
</tr>
<tr id="row1280102631614"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p4280126111614"><a name="p4280126111614"></a><a name="p4280126111614"></a>列出Endpoints</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614910_p53121653"><a name="zh-cn_topic_0079614910_p53121653"></a><a name="zh-cn_topic_0079614910_p53121653"></a>GET /api/v1/endpoints</p>
</td>
</tr>
<tr id="row117034280163"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p14703102831617"><a name="p14703102831617"></a><a name="p14703102831617"></a>列出指定Namespace下的Endpoints</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615068_p3825860"><a name="zh-cn_topic_0079615068_p3825860"></a><a name="zh-cn_topic_0079615068_p3825860"></a>GET /api/v1/namespaces/{namespace}/endpoints</p>
</td>
</tr>
<tr id="row02001434161614"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1320043416161"><a name="p1320043416161"></a><a name="p1320043416161"></a>更新指定的Endpoints</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p220063410163"><a name="p220063410163"></a><a name="p220063410163"></a>PATCH /api/v1/namespaces/{namespace}/endpoints/{name}</p>
</td>
</tr>
<tr id="row19649141632016"><td class="cellrowborder" rowspan="7" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p1858061573212"><a name="p1858061573212"></a><a name="p1858061573212"></a>Service</p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p20945157172816"><a name="p20945157172816"></a><a name="p20945157172816"></a>创建Service</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p9649141632014"><a name="p9649141632014"></a><a name="p9649141632014"></a>POST /api/v1/namespaces/{namespace}/services</p>
</td>
</tr>
<tr id="row12947142042019"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p63823394298"><a name="p63823394298"></a><a name="p63823394298"></a>删除指定的Service</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615016_p16764692"><a name="zh-cn_topic_0079615016_p16764692"></a><a name="zh-cn_topic_0079615016_p16764692"></a>DELETE /api/v1/namespaces/{namespace}/services/{name}</p>
</td>
</tr>
<tr id="row285902352011"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p142725173019"><a name="p142725173019"></a><a name="p142725173019"></a>获取指定的Service</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614941_p26666169"><a name="zh-cn_topic_0079614941_p26666169"></a><a name="zh-cn_topic_0079614941_p26666169"></a>GET /api/v1/namespaces/{namespace}/services/{name}</p>
</td>
</tr>
<tr id="row15913141918292"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p89133193291"><a name="p89133193291"></a><a name="p89133193291"></a>替换指定的Service</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615066_p22860275"><a name="zh-cn_topic_0079615066_p22860275"></a><a name="zh-cn_topic_0079615066_p22860275"></a>PUT /api/v1/namespaces/{namespace}/services/{name}</p>
</td>
</tr>
<tr id="row17312141713298"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p11312151716299"><a name="p11312151716299"></a><a name="p11312151716299"></a>列出指定Namespace下的Service</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614912_p44847908"><a name="zh-cn_topic_0079614912_p44847908"></a><a name="zh-cn_topic_0079614912_p44847908"></a>GET /api/v1/namespaces/{namespace}/services</p>
</td>
</tr>
<tr id="row148711112122912"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p124886663120"><a name="p124886663120"></a><a name="p124886663120"></a>列出Service</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615003_p39571321"><a name="zh-cn_topic_0079615003_p39571321"></a><a name="zh-cn_topic_0079615003_p39571321"></a>GET /api/v1/services</p>
</td>
</tr>
<tr id="row8187193182010"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1718773142014"><a name="p1718773142014"></a><a name="p1718773142014"></a>更新指定的Service</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079614894_p61872932"><a name="zh-cn_topic_0079614894_p61872932"></a><a name="zh-cn_topic_0079614894_p61872932"></a>PATCH /api/v1/namespaces/{namespace}/services/{name}</p>
</td>
</tr>
<tr id="row4542922133210"><td class="cellrowborder" rowspan="11" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p10774165353310"><a name="p10774165353310"></a><a name="p10774165353310"></a>Ingress</p>
<p id="p177397301370"><a name="p177397301370"></a><a name="p177397301370"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p5450137203414"><a name="p5450137203414"></a><a name="p5450137203414"></a>创建Ingress</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p937713588515"><a name="p937713588515"></a><a name="p937713588515"></a>POST /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses (仅适用于1.15及以上版本)</p>
<p id="p27723259"><a name="p27723259"></a><a name="p27723259"></a>POST /apis/extensions/v1beta1/namespaces/{namespace}/ingresses (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row15314192833211"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1586728163420"><a name="p1586728163420"></a><a name="p1586728163420"></a>更新指定的Ingress</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p10852105019143"><a name="p10852105019143"></a><a name="p10852105019143"></a>PATCH /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name} (仅适用于1.15及以上版本)</p>
<p id="p76611638133414"><a name="p76611638133414"></a><a name="p76611638133414"></a>PATCH /apis/extensions/v1beta1/namespaces/{namespace}/ingresses/{name} (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row896015335329"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p496015331325"><a name="p496015331325"></a><a name="p496015331325"></a>替换指定的Ingress</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1755574141515"><a name="p1755574141515"></a><a name="p1755574141515"></a>PUT /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name} (仅适用于1.15及以上版本)</p>
<p id="p35216193515"><a name="p35216193515"></a><a name="p35216193515"></a>PUT /apis/extensions/v1beta1/namespaces/{namespace}/ingresses/{name} (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row18258810113311"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p19197390353"><a name="p19197390353"></a><a name="p19197390353"></a>删除Ingress</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p3286191113151"><a name="p3286191113151"></a><a name="p3286191113151"></a>DELETE /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name} (仅适用于1.15及以上版本)</p>
<p id="p14262192356"><a name="p14262192356"></a><a name="p14262192356"></a>DELETE /apis/extensions/v1beta1/namespaces/{namespace}/ingresses/{name} (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row1061784017329"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p19618194011327"><a name="p19618194011327"></a><a name="p19618194011327"></a>删除所有的Ingress</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p14964823131514"><a name="p14964823131514"></a><a name="p14964823131514"></a>DELETE /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses (仅适用于1.15及以上版本)</p>
<p id="p4670123620353"><a name="p4670123620353"></a><a name="p4670123620353"></a>DELETE /apis/extensions/v1beta1/namespaces/{namespace}/ingresses (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row209082183312"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p14915219334"><a name="p14915219334"></a><a name="p14915219334"></a>获取指定的Ingress</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p892143110152"><a name="p892143110152"></a><a name="p892143110152"></a>GET /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name} (仅适用于1.15及以上版本)</p>
<p id="p54711156193519"><a name="p54711156193519"></a><a name="p54711156193519"></a>GET /apis/extensions/v1beta1/namespaces/{namespace}/ingresses/{name} (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row31514130339"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p115121343311"><a name="p115121343311"></a><a name="p115121343311"></a>列出指定Namespace下的Ingress</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p6213103712157"><a name="p6213103712157"></a><a name="p6213103712157"></a>GET /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses (仅适用于1.15及以上版本)</p>
<p id="p9498812163612"><a name="p9498812163612"></a><a name="p9498812163612"></a>GET /apis/extensions/v1beta1/namespaces/{namespace}/ingresses (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row680916333317"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p168091234339"><a name="p168091234339"></a><a name="p168091234339"></a>获取Ingress列表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p0725124317153"><a name="p0725124317153"></a><a name="p0725124317153"></a>GET /apis/networking.k8s.io/v1beta1/ingresses (仅适用于1.15及以上版本)</p>
<p id="p39740330364"><a name="p39740330364"></a><a name="p39740330364"></a>GET /apis/extensions/v1beta1/ingresses (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row1830485663214"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p63041056133216"><a name="p63041056133216"></a><a name="p63041056133216"></a>获取指定Namespace下的某个Ingress对象的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1594774921516"><a name="p1594774921516"></a><a name="p1594774921516"></a>GET /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name}/status (仅适用于1.15及以上版本)</p>
<p id="p14124653193615"><a name="p14124653193615"></a><a name="p14124653193615"></a>GET /apis/extensions/v1beta1/namespaces/{namespace}/ingresses/{name}/status (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row103521859183215"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1035285913327"><a name="p1035285913327"></a><a name="p1035285913327"></a>替换指定Namespace下的某个Ingress对象的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p10500859141510"><a name="p10500859141510"></a><a name="p10500859141510"></a>PUT /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name}/status (仅适用于1.15及以上版本)</p>
<p id="p880362510371"><a name="p880362510371"></a><a name="p880362510371"></a>PUT /apis/extensions/v1beta1/namespaces/{namespace}/ingresses/{name}/status (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row1073913043712"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p145011377377"><a name="p145011377377"></a><a name="p145011377377"></a>更新指定Namespace下的某个Ingress对象的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p56628551611"><a name="p56628551611"></a><a name="p56628551611"></a>PATCH /apis/networking.k8s.io/v1beta1/namespaces/{namespace}/ingresses/{name}/status (仅适用于1.15及以上版本)</p>
<p id="p35682485373"><a name="p35682485373"></a><a name="p35682485373"></a>PATCH /apis/extensions/v1beta1/namespaces/{namespace}/ingresses/{name}/status (仅适用于1.15以下版本)</p>
</td>
</tr>
<tr id="row27081713134118"><td class="cellrowborder" rowspan="8" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p14708213134116"><a name="p14708213134116"></a><a name="p14708213134116"></a>NetworkPolicy</p>
<p id="p17142134144111"><a name="p17142134144111"></a><a name="p17142134144111"></a></p>
<p id="p164868172412"><a name="p164868172412"></a><a name="p164868172412"></a></p>
<p id="p1471133874110"><a name="p1471133874110"></a><a name="p1471133874110"></a></p>
<p id="p1423943618416"><a name="p1423943618416"></a><a name="p1423943618416"></a></p>
<p id="p13661163210419"><a name="p13661163210419"></a><a name="p13661163210419"></a></p>
<p id="p59445210416"><a name="p59445210416"></a><a name="p59445210416"></a></p>
<p id="p19415112517418"><a name="p19415112517418"></a><a name="p19415112517418"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p118913413421"><a name="p118913413421"></a><a name="p118913413421"></a>创建networkpolicy</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p127081813184112"><a name="p127081813184112"></a><a name="p127081813184112"></a>POST /apis/networking.k8s.io/v1/namespaces/{namespace}/networkpolicies</p>
</td>
</tr>
<tr id="row6142164112413"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p13142174124119"><a name="p13142174124119"></a><a name="p13142174124119"></a>更新指定的networkpolicy</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1214211411414"><a name="p1214211411414"></a><a name="p1214211411414"></a>PATCH /apis/networking.k8s.io/v1/namespaces/{namespace}/networkpolicies/{name}</p>
</td>
</tr>
<tr id="row14486181720412"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p19486817194116"><a name="p19486817194116"></a><a name="p19486817194116"></a>替换指定的networkpolicy</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p44862175417"><a name="p44862175417"></a><a name="p44862175417"></a>PUT /apis/networking.k8s.io/v1/namespaces/{namespace}/networkpolicies/{name}</p>
</td>
</tr>
<tr id="row2470193854119"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p144710388415"><a name="p144710388415"></a><a name="p144710388415"></a>删除networkpolicy</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p711353142614"><a name="p711353142614"></a><a name="p711353142614"></a>DELETE /apis/networking.k8s.io/v1/namespaces/{namespace}/networkpolicies/{name}</p>
</td>
</tr>
<tr id="row5239636154111"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1622923111430"><a name="p1622923111430"></a><a name="p1622923111430"></a>批量删除networkpolicy</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p88712574268"><a name="p88712574268"></a><a name="p88712574268"></a>DELETE /apis/networking.k8s.io/v1/namespaces/{namespace}/networkpolicies</p>
</td>
</tr>
<tr id="row1566111326411"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p8989145494318"><a name="p8989145494318"></a><a name="p8989145494318"></a>获取指定的networkpolicy</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p11661173284119"><a name="p11661173284119"></a><a name="p11661173284119"></a>GET /apis/networking.k8s.io/v1/namespaces/{namespace}/networkpolicies/{name}</p>
</td>
</tr>
<tr id="row1294332117415"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1530611251449"><a name="p1530611251449"></a><a name="p1530611251449"></a>列出指定namespace下的networkpolicy</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p694412120418"><a name="p694412120418"></a><a name="p694412120418"></a>GET /apis/networking.k8s.io/v1/namespaces/{namespace}/networkpolicies</p>
</td>
</tr>
<tr id="row1541462512411"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p5658640124418"><a name="p5658640124418"></a><a name="p5658640124418"></a>获取networkpolicy列表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p6221175673610"><a name="p6221175673610"></a><a name="p6221175673610"></a>GET /apis/networking.k8s.io/v1/networkpolicies</p>
</td>
</tr>
<tr id="row577671014452"><td class="cellrowborder" rowspan="8" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p4627145474516"><a name="p4627145474516"></a><a name="p4627145474516"></a>PersistentVolume</p>
<p id="p9878101314515"><a name="p9878101314515"></a><a name="p9878101314515"></a></p>
<p id="p1240716161454"><a name="p1240716161454"></a><a name="p1240716161454"></a></p>
<p id="p1173819144514"><a name="p1173819144514"></a><a name="p1173819144514"></a></p>
<p id="p12966249452"><a name="p12966249452"></a><a name="p12966249452"></a></p>
<p id="p376912213451"><a name="p376912213451"></a><a name="p376912213451"></a></p>
<p id="p92771757455"><a name="p92771757455"></a><a name="p92771757455"></a></p>
<p id="p649478164511"><a name="p649478164511"></a><a name="p649478164511"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p1356017613463"><a name="p1356017613463"></a><a name="p1356017613463"></a>创建PersistentVolume</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p97761810114518"><a name="p97761810114518"></a><a name="p97761810114518"></a>POST /api/v1/persistentvolumes</p>
</td>
</tr>
<tr id="row9878161312457"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1287801317459"><a name="p1287801317459"></a><a name="p1287801317459"></a>删除指定的PersistentVolume</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a607cd13c3be24cc5aaab13586448e055"><a name="a607cd13c3be24cc5aaab13586448e055"></a><a name="a607cd13c3be24cc5aaab13586448e055"></a>DELETE /api/v1/persistentvolumes/{name}</p>
</td>
</tr>
<tr id="row640771644513"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p3407201618457"><a name="p3407201618457"></a><a name="p3407201618457"></a>删除所有的PersistentVolume</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p47592738"><a name="p47592738"></a><a name="p47592738"></a>DELETE /api/v1/persistentvolumes</p>
</td>
</tr>
<tr id="row1273919144518"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p573131917458"><a name="p573131917458"></a><a name="p573131917458"></a>获取指定的PersistentVolume</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="adeead686cd374b1ba05c94288ad41cd2"><a name="adeead686cd374b1ba05c94288ad41cd2"></a><a name="adeead686cd374b1ba05c94288ad41cd2"></a>GET /api/v1/persistentvolumes/{name}</p>
</td>
</tr>
<tr id="row62969247451"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p33882313477"><a name="p33882313477"></a><a name="p33882313477"></a>替换指定的PersistentVolume</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="add50420526264a00b7755b79ff1c6d94"><a name="add50420526264a00b7755b79ff1c6d94"></a><a name="add50420526264a00b7755b79ff1c6d94"></a>PUT /api/v1/persistentvolumes/{name}</p>
</td>
</tr>
<tr id="row2076913216453"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p147691921134511"><a name="p147691921134511"></a><a name="p147691921134511"></a>替换指定的PersistentVolume的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a6c88517788d546da915f31aa6ebfeab9"><a name="a6c88517788d546da915f31aa6ebfeab9"></a><a name="a6c88517788d546da915f31aa6ebfeab9"></a>PUT /api/v1/persistentvolumes/{name}/status</p>
</td>
</tr>
<tr id="row1827611513453"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7750135654715"><a name="p7750135654715"></a><a name="p7750135654715"></a>列出所有的PersistentVolume</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a6d192ef136004c88a1c29ad7364a15f7"><a name="a6d192ef136004c88a1c29ad7364a15f7"></a><a name="a6d192ef136004c88a1c29ad7364a15f7"></a>GET /api/v1/persistentvolumes</p>
</td>
</tr>
<tr id="row204931882458"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p16233101104810"><a name="p16233101104810"></a><a name="p16233101104810"></a>更新指定的PersistentVolume</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="aa05c77c94be74794a5e4e7b578a02525"><a name="aa05c77c94be74794a5e4e7b578a02525"></a><a name="aa05c77c94be74794a5e4e7b578a02525"></a>PATCH /api/v1/persistentvolumes/{name}</p>
</td>
</tr>
<tr id="row1496918390482"><td class="cellrowborder" rowspan="9" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p410473995016"><a name="p410473995016"></a><a name="p410473995016"></a>PersistentVolumeClaim</p>
<p id="p12623145524810"><a name="p12623145524810"></a><a name="p12623145524810"></a></p>
<p id="p1336103174910"><a name="p1336103174910"></a><a name="p1336103174910"></a></p>
<p id="p8286114914"><a name="p8286114914"></a><a name="p8286114914"></a></p>
<p id="p15297118174911"><a name="p15297118174911"></a><a name="p15297118174911"></a></p>
<p id="p1015221120492"><a name="p1015221120492"></a><a name="p1015221120492"></a></p>
<p id="p314661444918"><a name="p314661444918"></a><a name="p314661444918"></a></p>
<p id="p14145058114815"><a name="p14145058114815"></a><a name="p14145058114815"></a></p>
<p id="p1687150204917"><a name="p1687150204917"></a><a name="p1687150204917"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p3357450125018"><a name="p3357450125018"></a><a name="p3357450125018"></a>创建PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="aed55e8b758cb44f1abaf8ccb8dcf1083"><a name="aed55e8b758cb44f1abaf8ccb8dcf1083"></a><a name="aed55e8b758cb44f1abaf8ccb8dcf1083"></a>POST /api/v1/namespaces/{namespace}/persistentvolumeclaims</p>
</td>
</tr>
<tr id="row19623135516484"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p862319555481"><a name="p862319555481"></a><a name="p862319555481"></a>删除指定的PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a9e09191bad1c47a9abbd50d527678f69"><a name="a9e09191bad1c47a9abbd50d527678f69"></a><a name="a9e09191bad1c47a9abbd50d527678f69"></a>DELETE  /api/v1/namespaces/{namespace}/persistentvolumeclaims/{name}</p>
</td>
</tr>
<tr id="row11361134493"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p23611438492"><a name="p23611438492"></a><a name="p23611438492"></a>删除所有的PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p14361837499"><a name="p14361837499"></a><a name="p14361837499"></a>DELETE /api/v1/namespaces/{namespace}/persistentvolumeclaims</p>
</td>
</tr>
<tr id="row18213654916"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7216114914"><a name="p7216114914"></a><a name="p7216114914"></a>获取指定的PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a71ee18eeb9624100822b748e8490f956"><a name="a71ee18eeb9624100822b748e8490f956"></a><a name="a71ee18eeb9624100822b748e8490f956"></a>GET /api/v1/namespaces/{namespace}/persistentvolumeclaims/{name}</p>
</td>
</tr>
<tr id="row122977814910"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p53413435211"><a name="p53413435211"></a><a name="p53413435211"></a>替换指定的PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a1d5ba595c39745c2b0c3c838ad95f9b4"><a name="a1d5ba595c39745c2b0c3c838ad95f9b4"></a><a name="a1d5ba595c39745c2b0c3c838ad95f9b4"></a>PUT /api/v1/namespaces/{namespace}/persistentvolumeclaims/{name}</p>
</td>
</tr>
<tr id="row161521011104917"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p9935172012523"><a name="p9935172012523"></a><a name="p9935172012523"></a>替换指定的PersistentVolumeClaim的状态</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="aa715d4d56074416686788a7fde239df0"><a name="aa715d4d56074416686788a7fde239df0"></a><a name="aa715d4d56074416686788a7fde239df0"></a>PUT /api/v1/namespaces/{namespace}/persistentvolumeclaims/{name}/status</p>
</td>
</tr>
<tr id="row18146181417496"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p10881538105212"><a name="p10881538105212"></a><a name="p10881538105212"></a>列出指定的Namespace下的PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a740e303a205d467d8bf611b955dd139f"><a name="a740e303a205d467d8bf611b955dd139f"></a><a name="a740e303a205d467d8bf611b955dd139f"></a>GET /api/v1/namespaces/{namespace}/persistentvolumeclaims</p>
</td>
</tr>
<tr id="row13145758184820"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p957990205311"><a name="p957990205311"></a><a name="p957990205311"></a>列出所有的PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a06f45a66ebf341b39f990962ac1f5c08"><a name="a06f45a66ebf341b39f990962ac1f5c08"></a><a name="a06f45a66ebf341b39f990962ac1f5c08"></a>GET /api/v1/persistentvolumeclaims</p>
</td>
</tr>
<tr id="row188718017492"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p108719018494"><a name="p108719018494"></a><a name="p108719018494"></a>更新指定的PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a4060049f545d48b58a9ed6b10609ee3a"><a name="a4060049f545d48b58a9ed6b10609ee3a"></a><a name="a4060049f545d48b58a9ed6b10609ee3a"></a>PATCH /api/v1/namespaces/{namespace}/persistentvolumeclaims/{name}</p>
</td>
</tr>
<tr id="row1243918521537"><td class="cellrowborder" rowspan="8" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p043925215312"><a name="p043925215312"></a><a name="p043925215312"></a>ConfigMap</p>
<p id="p1810895517538"><a name="p1810895517538"></a><a name="p1810895517538"></a></p>
<p id="p11231059145310"><a name="p11231059145310"></a><a name="p11231059145310"></a></p>
<p id="p6917101105412"><a name="p6917101105412"></a><a name="p6917101105412"></a></p>
<p id="p1451162035412"><a name="p1451162035412"></a><a name="p1451162035412"></a></p>
<p id="p59721623175415"><a name="p59721623175415"></a><a name="p59721623175415"></a></p>
<p id="p185801826135410"><a name="p185801826135410"></a><a name="p185801826135410"></a></p>
<p id="p335102955410"><a name="p335102955410"></a><a name="p335102955410"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p126241712125511"><a name="p126241712125511"></a><a name="p126241712125511"></a>创建ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p35772102"><a name="p35772102"></a><a name="p35772102"></a>POST /api/v1/namespaces/{namespace}/configmaps</p>
</td>
</tr>
<tr id="row41086553537"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1922622825514"><a name="p1922622825514"></a><a name="p1922622825514"></a>删除ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p64518786"><a name="p64518786"></a><a name="p64518786"></a>DELETE /api/v1/namespaces/{namespace}/configmaps/{name}</p>
</td>
</tr>
<tr id="row15123175913537"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p2123175915313"><a name="p2123175915313"></a><a name="p2123175915313"></a>删除所有的ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p111232592530"><a name="p111232592530"></a><a name="p111232592530"></a>DELETE /api/v1/namespaces/{namespace}/configmaps</p>
</td>
</tr>
<tr id="row1191611195418"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p191710114545"><a name="p191710114545"></a><a name="p191710114545"></a>获取指定的ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p45968213"><a name="p45968213"></a><a name="p45968213"></a>GET /api/v1/namespaces/{namespace}/configmaps/{name}</p>
</td>
</tr>
<tr id="row8451152018544"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p16501124155617"><a name="p16501124155617"></a><a name="p16501124155617"></a>替换指定ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p10451420205419"><a name="p10451420205419"></a><a name="p10451420205419"></a>PUT /api/v1/namespaces/{namespace}/configmaps/{name}</p>
</td>
</tr>
<tr id="row1497212325419"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p154634295617"><a name="p154634295617"></a><a name="p154634295617"></a>列出指定Namespace下的ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p997222313540"><a name="p997222313540"></a><a name="p997222313540"></a>GET /api/v1/namespaces/{namespace}/configmaps</p>
</td>
</tr>
<tr id="row75801826185416"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p19580122695410"><a name="p19580122695410"></a><a name="p19580122695410"></a>列出所有的ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p75801026145413"><a name="p75801026145413"></a><a name="p75801026145413"></a>GET /api/v1/configmaps</p>
</td>
</tr>
<tr id="row1835329195413"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p8362296541"><a name="p8362296541"></a><a name="p8362296541"></a>更新指定的ConfigMap</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p93692916542"><a name="p93692916542"></a><a name="p93692916542"></a>PATCH /api/v1/namespaces/{namespace}/configmaps/{name}</p>
</td>
</tr>
<tr id="row13373352594"><td class="cellrowborder" rowspan="7" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p10618859115810"><a name="p10618859115810"></a><a name="p10618859115810"></a>Secret</p>
<p id="p3141181085917"><a name="p3141181085917"></a><a name="p3141181085917"></a></p>
<p id="p962216150591"><a name="p962216150591"></a><a name="p962216150591"></a></p>
<p id="p5740836135915"><a name="p5740836135915"></a><a name="p5740836135915"></a></p>
<p id="p1074073665917"><a name="p1074073665917"></a><a name="p1074073665917"></a></p>
<p id="p8541145915916"><a name="p8541145915916"></a><a name="p8541145915916"></a></p>
<p id="p45414593591"><a name="p45414593591"></a><a name="p45414593591"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p17277484013"><a name="p17277484013"></a><a name="p17277484013"></a>创建Secret</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p5373105105914"><a name="p5373105105914"></a><a name="p5373105105914"></a>POST /api/v1/namespaces/{namespace}/secrets</p>
</td>
</tr>
<tr id="row21419101597"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p2050213261701"><a name="p2050213261701"></a><a name="p2050213261701"></a>删除Secret</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0079615047_p59567086"><a name="zh-cn_topic_0079615047_p59567086"></a><a name="zh-cn_topic_0079615047_p59567086"></a>DELETE /api/v1/namespaces/{namespace}/secrets/{name}</p>
</td>
</tr>
<tr id="row186223155595"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p250017421404"><a name="p250017421404"></a><a name="p250017421404"></a>删除指定命名空间下所有的Secret</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p64597705"><a name="p64597705"></a><a name="p64597705"></a>DELETE /api/v1/namespaces/{namespace}/secrets</p>
</td>
</tr>
<tr id="row2075115366599"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p141751157113"><a name="p141751157113"></a><a name="p141751157113"></a>获取Secret信息</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1274033645910"><a name="p1274033645910"></a><a name="p1274033645910"></a>GET /api/v1/namespaces/{namespace}/secrets/{name}</p>
</td>
</tr>
<tr id="row475013617597"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1379713213117"><a name="p1379713213117"></a><a name="p1379713213117"></a>替换指定的Secret</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p14740183614596"><a name="p14740183614596"></a><a name="p14740183614596"></a>PUT /api/v1/namespaces/{namespace}/secrets/{name}</p>
</td>
</tr>
<tr id="row3546205915915"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1541259185913"><a name="p1541259185913"></a><a name="p1541259185913"></a>列出指定Namespace下的Secret</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="ad089adbf03904cbbac75ae62e80eda8a"><a name="ad089adbf03904cbbac75ae62e80eda8a"></a><a name="ad089adbf03904cbbac75ae62e80eda8a"></a>GET /api/v1/namespaces/{namespace}/secrets</p>
</td>
</tr>
<tr id="row17545145975912"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p388020571511"><a name="p388020571511"></a><a name="p388020571511"></a>列出集群下的Secret</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="a2fab34208467472e8bfb5f9e53c702fb"><a name="a2fab34208467472e8bfb5f9e53c702fb"></a><a name="a2fab34208467472e8bfb5f9e53c702fb"></a>GET /api/v1/secrets</p>
</td>
</tr>
<tr id="row9787549329"><td class="cellrowborder" rowspan="7" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p764591511518"><a name="p764591511518"></a><a name="p764591511518"></a>RBAC/</p>
<p id="p172838518203"><a name="p172838518203"></a><a name="p172838518203"></a>ClusterRole</p>
<p id="p1776584910210"><a name="p1776584910210"></a><a name="p1776584910210"></a></p>
<p id="p376519491526"><a name="p376519491526"></a><a name="p376519491526"></a></p>
<p id="p117661349926"><a name="p117661349926"></a><a name="p117661349926"></a></p>
<p id="p194545231553"><a name="p194545231553"></a><a name="p194545231553"></a></p>
<p id="p6431181612193"><a name="p6431181612193"></a><a name="p6431181612193"></a></p>
<p id="p1031121719196"><a name="p1031121719196"></a><a name="p1031121719196"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p13643121513511"><a name="p13643121513511"></a><a name="p13643121513511"></a>创建ClusterRole</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p81091853315"><a name="p81091853315"></a><a name="p81091853315"></a>POST /apis/rbac.authorization.k8s.io/v1/clusterroles</p>
</td>
</tr>
<tr id="row167861249528"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p18108851732"><a name="p18108851732"></a><a name="p18108851732"></a>更新指定的ClusterRole</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p19305545113910"><a name="p19305545113910"></a><a name="p19305545113910"></a>PATCH /apis/rbac.authorization.k8s.io/v1/clusterroles/{name}</p>
</td>
</tr>
<tr id="row1278615491820"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p13695111722115"><a name="p13695111722115"></a><a name="p13695111722115"></a>替换指定的ClusterRole</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p17499735154117"><a name="p17499735154117"></a><a name="p17499735154117"></a>PUT /apis/rbac.authorization.k8s.io/v1/clusterroles/{name}</p>
</td>
</tr>
<tr id="row97859491827"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p5846103010212"><a name="p5846103010212"></a><a name="p5846103010212"></a>删除指定的ClusterRole</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1216694064219"><a name="p1216694064219"></a><a name="p1216694064219"></a>DELETE /apis/rbac.authorization.k8s.io/v1/clusterroles/{name}</p>
</td>
</tr>
<tr id="row1746052316518"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1856714742114"><a name="p1856714742114"></a><a name="p1856714742114"></a>批量删除ClusterRole</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1587116386438"><a name="p1587116386438"></a><a name="p1587116386438"></a>DELETE /apis/rbac.authorization.k8s.io/v1/clusterroles</p>
</td>
</tr>
<tr id="row84311316101911"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1072711114229"><a name="p1072711114229"></a><a name="p1072711114229"></a>获取指定的ClusterRole</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p843161641919"><a name="p843161641919"></a><a name="p843161641919"></a>GET /apis/rbac.authorization.k8s.io/v1/clusterroles/{name}</p>
</td>
</tr>
<tr id="row18310017181910"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p43111817171919"><a name="p43111817171919"></a><a name="p43111817171919"></a>获取ClusterRole列表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p63111177192"><a name="p63111177192"></a><a name="p63111177192"></a>GET /apis/rbac.authorization.k8s.io/v1/clusterroles</p>
</td>
</tr>
<tr id="row69410181197"><td class="cellrowborder" rowspan="7" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p51939082316"><a name="p51939082316"></a><a name="p51939082316"></a>RBAC/</p>
<p id="p112901120192313"><a name="p112901120192313"></a><a name="p112901120192313"></a>ClusterRoleBinding</p>
<p id="p357391911191"><a name="p357391911191"></a><a name="p357391911191"></a></p>
<p id="p245412310510"><a name="p245412310510"></a><a name="p245412310510"></a></p>
<p id="p34543234518"><a name="p34543234518"></a><a name="p34543234518"></a></p>
<p id="p114551523655"><a name="p114551523655"></a><a name="p114551523655"></a></p>
<p id="p4742183311510"><a name="p4742183311510"></a><a name="p4742183311510"></a></p>
<p id="p77421433657"><a name="p77421433657"></a><a name="p77421433657"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p8941818101920"><a name="p8941818101920"></a><a name="p8941818101920"></a>创建ClusterRoleBinding</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p11423202118591"><a name="p11423202118591"></a><a name="p11423202118591"></a>POST /apis/rbac.authorization.k8s.io/v1/clusterrolebindings</p>
</td>
</tr>
<tr id="row0573161915193"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p19915184652318"><a name="p19915184652318"></a><a name="p19915184652318"></a>更新指定的ClusterRoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p86043476597"><a name="p86043476597"></a><a name="p86043476597"></a>PATCH /apis/rbac.authorization.k8s.io/v1/clusterrolebindings/{name}</p>
</td>
</tr>
<tr id="row346012237512"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p154541231455"><a name="p154541231455"></a><a name="p154541231455"></a>替换指定的ClusterRoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p345419231358"><a name="p345419231358"></a><a name="p345419231358"></a>PUT /apis/rbac.authorization.k8s.io/v1/clusterrolebindings/{name}</p>
</td>
</tr>
<tr id="row6459112312519"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p445414231512"><a name="p445414231512"></a><a name="p445414231512"></a>删除指定的ClusterRoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p15948827005"><a name="p15948827005"></a><a name="p15948827005"></a>DELETE /apis/rbac.authorization.k8s.io/v1/clusterrolebindings/{name}</p>
</td>
</tr>
<tr id="row2459123153"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p5455102312515"><a name="p5455102312515"></a><a name="p5455102312515"></a>批量删除ClusterRoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p3455122317520"><a name="p3455122317520"></a><a name="p3455122317520"></a>DELETE /apis/rbac.authorization.k8s.io/v1/clusterrolebindings</p>
</td>
</tr>
<tr id="row87491233755"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p274210331250"><a name="p274210331250"></a><a name="p274210331250"></a>获取指定的ClusterRoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p177018411112"><a name="p177018411112"></a><a name="p177018411112"></a>GET /apis/rbac.authorization.k8s.io/v1/clusterrolebindings/{name}</p>
</td>
</tr>
<tr id="row1474915333516"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p208984862515"><a name="p208984862515"></a><a name="p208984862515"></a>获取ClusterRoleBinding列表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p11578286115"><a name="p11578286115"></a><a name="p11578286115"></a>GET /apis/rbac.authorization.k8s.io/v1/clusterrolebindings</p>
</td>
</tr>
<tr id="row574918336513"><td class="cellrowborder" rowspan="8" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p199091526265"><a name="p199091526265"></a><a name="p199091526265"></a>RBAC/Role</p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p97439332512"><a name="p97439332512"></a><a name="p97439332512"></a>创建Role</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p1986715316175"><a name="p1986715316175"></a><a name="p1986715316175"></a>POST /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/roles</p>
</td>
</tr>
<tr id="row174916337512"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p20754932152618"><a name="p20754932152618"></a><a name="p20754932152618"></a>更新指定的Role</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p62523721719"><a name="p62523721719"></a><a name="p62523721719"></a>PATCH /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/roles/{name}</p>
</td>
</tr>
<tr id="row770518371152"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p16528345274"><a name="p16528345274"></a><a name="p16528345274"></a>替换指定的Role</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1891516567174"><a name="p1891516567174"></a><a name="p1891516567174"></a>PUT /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/roles/{name}</p>
</td>
</tr>
<tr id="row117051037959"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p16961237857"><a name="p16961237857"></a><a name="p16961237857"></a>删除指定的Role</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p5998111611185"><a name="p5998111611185"></a><a name="p5998111611185"></a>DELETE /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/roles/{name}</p>
</td>
</tr>
<tr id="row27058371453"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p106964371751"><a name="p106964371751"></a><a name="p106964371751"></a>批量删除Role</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p6631194181814"><a name="p6631194181814"></a><a name="p6631194181814"></a>DELETE /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/roles</p>
</td>
</tr>
<tr id="row107057371451"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p19234153102716"><a name="p19234153102716"></a><a name="p19234153102716"></a>获取指定的Role</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p114781061916"><a name="p114781061916"></a><a name="p114781061916"></a>GET /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/roles/{name}</p>
</td>
</tr>
<tr id="row5682840851"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1571347192810"><a name="p1571347192810"></a><a name="p1571347192810"></a>获取指定namespace下的Role列表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p32291375314"><a name="p32291375314"></a><a name="p32291375314"></a>GET /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/roles</p>
</td>
</tr>
<tr id="row136811940752"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p8667520132816"><a name="p8667520132816"></a><a name="p8667520132816"></a>获取Role列表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1826614282531"><a name="p1826614282531"></a><a name="p1826614282531"></a>GET /apis/rbac.authorization.k8s.io/v1/roles</p>
</td>
</tr>
<tr id="row1468113401511"><td class="cellrowborder" rowspan="8" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p12674204012515"><a name="p12674204012515"></a><a name="p12674204012515"></a>RBAC/RoleBinding</p>
<p id="p6675240453"><a name="p6675240453"></a><a name="p6675240453"></a></p>
<p id="p1019694313515"><a name="p1019694313515"></a><a name="p1019694313515"></a></p>
<p id="p201977432512"><a name="p201977432512"></a><a name="p201977432512"></a></p>
<p id="p519717431150"><a name="p519717431150"></a><a name="p519717431150"></a></p>
<p id="p7197204319512"><a name="p7197204319512"></a><a name="p7197204319512"></a></p>
<p id="p83776451959"><a name="p83776451959"></a><a name="p83776451959"></a></p>
<p id="p133770451953"><a name="p133770451953"></a><a name="p133770451953"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p4741133612293"><a name="p4741133612293"></a><a name="p4741133612293"></a>创建RoleBinding</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p15865118542"><a name="p15865118542"></a><a name="p15865118542"></a>POST /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/rolebindings</p>
</td>
</tr>
<tr id="row196816401656"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p86755401257"><a name="p86755401257"></a><a name="p86755401257"></a>更新指定的RoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p15675840151"><a name="p15675840151"></a><a name="p15675840151"></a>PATCH /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/rolebindings/{name}</p>
</td>
</tr>
<tr id="row18205843552"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1197743752"><a name="p1197743752"></a><a name="p1197743752"></a>替换指定的RoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1119784310517"><a name="p1119784310517"></a><a name="p1119784310517"></a>PUT /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/rolebindings/{name}</p>
</td>
</tr>
<tr id="row1420517431754"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7117102818306"><a name="p7117102818306"></a><a name="p7117102818306"></a>删除指定的RoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1319719433515"><a name="p1319719433515"></a><a name="p1319719433515"></a>DELETE /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/rolebindings/{name}</p>
</td>
</tr>
<tr id="row920554314512"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p168531426304"><a name="p168531426304"></a><a name="p168531426304"></a>批量删除RoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p12545274555"><a name="p12545274555"></a><a name="p12545274555"></a>DELETE /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/rolebindings</p>
</td>
</tr>
<tr id="row12041043352"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p18752057183016"><a name="p18752057183016"></a><a name="p18752057183016"></a>获取指定的RoleBinding</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p161978431651"><a name="p161978431651"></a><a name="p161978431651"></a>GET /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/rolebindings/{name}</p>
</td>
</tr>
<tr id="row113861845155"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p6377845452"><a name="p6377845452"></a><a name="p6377845452"></a>获取指定namespace下RoleBinding列表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1245412216565"><a name="p1245412216565"></a><a name="p1245412216565"></a>GET /apis/rbac.authorization.k8s.io/v1/namespaces/{namespace}/rolebindings</p>
</td>
</tr>
<tr id="row138610451453"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1589812338319"><a name="p1589812338319"></a><a name="p1589812338319"></a>获取RoleBinding列表</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p0356172010568"><a name="p0356172010568"></a><a name="p0356172010568"></a>GET /apis/rbac.authorization.k8s.io/v1/rolebindings</p>
</td>
</tr>
<tr id="row2038617456513"><td class="cellrowborder" rowspan="19" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p6752553218"><a name="p6752553218"></a><a name="p6752553218"></a>API groups</p>
<p id="p53778455510"><a name="p53778455510"></a><a name="p53778455510"></a></p>
<p id="p1175155311514"><a name="p1175155311514"></a><a name="p1175155311514"></a></p>
<p id="p37525539513"><a name="p37525539513"></a><a name="p37525539513"></a></p>
<p id="p117531453052"><a name="p117531453052"></a><a name="p117531453052"></a></p>
<p id="p12753753458"><a name="p12753753458"></a><a name="p12753753458"></a></p>
<p id="p15245165619512"><a name="p15245165619512"></a><a name="p15245165619512"></a></p>
<p id="p1724514561352"><a name="p1724514561352"></a><a name="p1724514561352"></a></p>
<p id="p524513561553"><a name="p524513561553"></a><a name="p524513561553"></a></p>
<p id="p524545614511"><a name="p524545614511"></a><a name="p524545614511"></a></p>
<p id="p10983202611198"><a name="p10983202611198"></a><a name="p10983202611198"></a></p>
<p id="p373883191912"><a name="p373883191912"></a><a name="p373883191912"></a></p>
<p id="p131825285194"><a name="p131825285194"></a><a name="p131825285194"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p0575717133918"><a name="p0575717133918"></a><a name="p0575717133918"></a>列出APIVersions</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p8211143411399"><a name="p8211143411399"></a><a name="p8211143411399"></a>GET /api</p>
</td>
</tr>
<tr id="row18385134514520"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p147031739163918"><a name="p147031739163918"></a><a name="p147031739163918"></a>列出APIGroups</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p91991048051"><a name="p91991048051"></a><a name="p91991048051"></a>GET /apis</p>
</td>
</tr>
<tr id="row117658535520"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p57527531754"><a name="p57527531754"></a><a name="p57527531754"></a>listing APIResources of GroupVersion apiregistration.k8s.io/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p8752453351"><a name="p8752453351"></a><a name="p8752453351"></a>GET /apis/apiregistration.k8s.io/v1beta1</p>
</td>
</tr>
<tr id="row1076517537510"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p210212924015"><a name="p210212924015"></a><a name="p210212924015"></a>listing APIResources of GroupVersion extensions/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1775215531752"><a name="p1775215531752"></a><a name="p1775215531752"></a>GET /apis/extensions/v1beta1</p>
</td>
</tr>
<tr id="row1376511531952"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p3753753651"><a name="p3753753651"></a><a name="p3753753651"></a>listing APIResources of GroupVersion apps/v1&amp;apps/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p1219419165171"><a name="p1219419165171"></a><a name="p1219419165171"></a>GET /apis/apps/v1（适用于1.15以上版本的集群）</p>
<p id="p44307368"><a name="p44307368"></a><a name="p44307368"></a>GET /apis/apps/v1beta1（仅适用于1.15及以下版本的集群）</p>
</td>
</tr>
<tr id="row676417531451"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p7858166194117"><a name="p7858166194117"></a><a name="p7858166194117"></a>listing APIResources of GroupVersion authentication.k8s.io/v1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p59255157"><a name="p59255157"></a><a name="p59255157"></a>GET /apis/authentication.k8s.io/v1</p>
</td>
</tr>
<tr id="row132581356254"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1024518566517"><a name="p1024518566517"></a><a name="p1024518566517"></a>listing APIResources of GroupVersion authentication.k8s.io/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p61978487"><a name="p61978487"></a><a name="p61978487"></a>GET /apis/authentication.k8s.io/v1beta1</p>
</td>
</tr>
<tr id="row162587565514"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p171951343184114"><a name="p171951343184114"></a><a name="p171951343184114"></a>listing APIResources of GroupVersion authorization.k8s.io/v1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p61148946"><a name="p61148946"></a><a name="p61148946"></a>GET /apis/authorization.k8s.io/v1</p>
</td>
</tr>
<tr id="row22582561355"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1324517567512"><a name="p1324517567512"></a><a name="p1324517567512"></a>listing APIResources of GroupVersion authorization.k8s.io/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p49070508"><a name="p49070508"></a><a name="p49070508"></a>GET /apis/authorization.k8s.io/v1beta1</p>
</td>
</tr>
<tr id="row2258105614511"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p461016194426"><a name="p461016194426"></a><a name="p461016194426"></a>listing APIResources of GroupVersion autoscaling/v1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p42009373"><a name="p42009373"></a><a name="p42009373"></a>GET /apis/autoscaling/v1</p>
</td>
</tr>
<tr id="row1198332618191"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p145054367422"><a name="p145054367422"></a><a name="p145054367422"></a>listing APIResources of GroupVersion batch/v1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p18291833"><a name="p18291833"></a><a name="p18291833"></a>GET /apis/batch/v1</p>
</td>
</tr>
<tr id="row3738113161914"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p5524150104219"><a name="p5524150104219"></a><a name="p5524150104219"></a>listing APIResources of GroupVersion certificates.k8s.io/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p57469819"><a name="p57469819"></a><a name="p57469819"></a>GET /apis/certificates.k8s.io/v1beta1</p>
</td>
</tr>
<tr id="row2668752203217"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p67317644318"><a name="p67317644318"></a><a name="p67317644318"></a>listing APIResources of GroupVersion networking.k8s.io/v1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p36473072"><a name="p36473072"></a><a name="p36473072"></a>GET /apis/networking.k8s.io/v1</p>
</td>
</tr>
<tr id="row03101420337"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p2263230164314"><a name="p2263230164314"></a><a name="p2263230164314"></a>listing APIResources of GroupVersion policy/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p183111325333"><a name="p183111325333"></a><a name="p183111325333"></a>GET /apis/policy/v1beta1</p>
</td>
</tr>
<tr id="row1022216112335"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p104176498436"><a name="p104176498436"></a><a name="p104176498436"></a>listing APIResources of GroupVersion rbac.authorization.k8s.io/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p34832013"><a name="p34832013"></a><a name="p34832013"></a>GET /apis/rbac.authorization.k8s.io/v1beta1</p>
</td>
</tr>
<tr id="row77756883310"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p17752863316"><a name="p17752863316"></a><a name="p17752863316"></a>listing APIResources of GroupVersion storage.k8s.io/v1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p50088692"><a name="p50088692"></a><a name="p50088692"></a>GET /apis/storage.k8s.io/v1</p>
</td>
</tr>
<tr id="row9992114163319"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p115385267445"><a name="p115385267445"></a><a name="p115385267445"></a>listing APIResources of GroupVersion storage.k8s.io/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p39188142"><a name="p39188142"></a><a name="p39188142"></a>GET /apis/storage.k8s.io/v1beta1</p>
</td>
</tr>
<tr id="row84151659123219"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p44159593325"><a name="p44159593325"></a><a name="p44159593325"></a>listing APIResources of GroupVersion apiextensions.k8s.io/v1beta1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p21965084"><a name="p21965084"></a><a name="p21965084"></a>GET /apis/apiextensions.k8s.io/v1beta1</p>
</td>
</tr>
<tr id="row1018272813193"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p829210598443"><a name="p829210598443"></a><a name="p829210598443"></a>listing APIResources of GroupVersion v1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p41785475"><a name="p41785475"></a><a name="p41785475"></a>GET /api/v1</p>
</td>
</tr>
<tr id="row20777132554513"><td class="cellrowborder" rowspan="2" valign="top" width="13.278672132786722%" headers="mcps1.1.4.1.1 "><p id="p6777225154512"><a name="p6777225154512"></a><a name="p6777225154512"></a>Event</p>
<p id="p367516264456"><a name="p367516264456"></a><a name="p367516264456"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.286871312868712%" headers="mcps1.1.4.1.2 "><p id="p2777182554515"><a name="p2777182554515"></a><a name="p2777182554515"></a>获取Event</p>
</td>
<td class="cellrowborder" valign="top" width="55.43445655434457%" headers="mcps1.1.4.1.3 "><p id="p37777259457"><a name="p37777259457"></a><a name="p37777259457"></a>GET /api/v1/events</p>
</td>
</tr>
<tr id="row667562613453"><td class="cellrowborder" valign="top" headers="mcps1.1.4.1.1 "><p id="p1370245411452"><a name="p1370245411452"></a><a name="p1370245411452"></a>列出指定命名空间下的Event</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.4.1.2 "><p id="p15374686"><a name="p15374686"></a><a name="p15374686"></a>GET /api/v1/namespaces/{namespace}/events</p>
</td>
</tr>
</tbody>
</table>

