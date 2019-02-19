# Kubectl使用指南<a name="cce_01_0023"></a>

使用Kubectl命令时，您需要具备Kubectl相关开发技能，了解Kubectl相关操作。详细请参考[Kubernetes API](https://kubernetes.io/docs/concepts/overview/kubernetes-api/)、[Kubetl CLI](https://kubernetes.io/docs/reference/kubectl/overview/)。

**表 1**  Kubectl使用指南

<a name="table4373319566"></a>
<table><thead align="left"><tr id="row939163115620"><th class="cellrowborder" valign="top" width="21%" id="mcps1.2.3.1.1"><p id="p1353119199565"><a name="p1353119199565"></a><a name="p1353119199565"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="79%" id="mcps1.2.3.1.2"><p id="p53917335610"><a name="p53917335610"></a><a name="p53917335610"></a>Kubectl使用一览</p>
</th>
</tr>
</thead>
<tbody><tr id="row123917316569"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p8531919135617"><a name="p8531919135617"></a><a name="p8531919135617"></a>连接<span class="keyword" id="keyword1041217520260"><a name="keyword1041217520260"></a><a name="keyword1041217520260"></a>集群</span></p>
</td>
<td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p1239183205611"><a name="p1239183205611"></a><a name="p1239183205611"></a><a href="通过Kubectl连接集群.md">通过Kubectl连接集群</a></p>
</td>
</tr>
<tr id="row891519223810"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p491622211811"><a name="p491622211811"></a><a name="p491622211811"></a><span class="keyword" id="keyword1443215012618"><a name="keyword1443215012618"></a><a name="keyword1443215012618"></a>kube-dns</span><span class="keyword" id="keyword6339193122618"><a name="keyword6339193122618"></a><a name="keyword6339193122618"></a>高可用</span></p>
</td>
<td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p7916162220816"><a name="p7916162220816"></a><a name="p7916162220816"></a><a href="通过kubectl配置kube-dns-CoreDNS高可用.md">通过kubectl配置kube-dns高可用</a></p>
</td>
</tr>
<tr id="row183953145614"><td class="cellrowborder" rowspan="2" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p19239401986"><a name="p19239401986"></a><a name="p19239401986"></a>创建工作负载</p>
</td>
<td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p53918315564"><a name="p53918315564"></a><a name="p53918315564"></a><a href="创建无状态工作负载.md#section155246177178">通过Kubectl创建无状态工作负载</a></p>
</td>
</tr>
<tr id="row9391730563"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p103917345612"><a name="p103917345612"></a><a name="p103917345612"></a><a href="创建有状态工作负载.md#section113441881214">通过kubectl创建有状态工作负载</a></p>
</td>
</tr>
<tr id="row1339233567"><td class="cellrowborder" rowspan="6" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p104807404911"><a name="p104807404911"></a><a name="p104807404911"></a>工作负载<span class="keyword" id="keyword4354754102512"><a name="keyword4354754102512"></a><a name="keyword4354754102512"></a>亲和</span>/<span class="keyword" id="keyword36383566255"><a name="keyword36383566255"></a><a name="keyword36383566255"></a>反亲和</span>调度</p>
</td>
<td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p1641153105613"><a name="p1641153105613"></a><a name="p1641153105613"></a><a href="亲和-反亲和性调度.md#section711574271117">工作负载部署到指定节点-yaml示例</a></p>
</td>
</tr>
<tr id="row1341103105616"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p641183115613"><a name="p641183115613"></a><a name="p641183115613"></a><a href="亲和-反亲和性调度.md#section1361482522712">工作负载不部署到指定节点-yaml示例</a></p>
</td>
</tr>
<tr id="row1141113135619"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p94173185614"><a name="p94173185614"></a><a name="p94173185614"></a><a href="亲和-反亲和性调度.md#section5140193643912">指定工作负载部署在相同节点-yaml示例</a></p>
</td>
</tr>
<tr id="row5179024686"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1818120241088"><a name="p1818120241088"></a><a name="p1818120241088"></a><a href="亲和-反亲和性调度.md#section1894310152317">指定工作负载部署在不同节点-yaml示例</a></p>
</td>
</tr>
<tr id="row41820243812"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1018212418818"><a name="p1018212418818"></a><a name="p1018212418818"></a><a href="亲和-反亲和性调度.md#section4201420133117">工作负载部署在指定可用区-yaml示例</a></p>
</td>
</tr>
<tr id="row17182122410811"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1718232418812"><a name="p1718232418812"></a><a name="p1718232418812"></a><a href="亲和-反亲和性调度.md#section102822029173111">工作负载不部署在指定可用区-yaml示例</a></p>
</td>
</tr>
<tr id="row131821224183"><td class="cellrowborder" rowspan="6" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p137511352171111"><a name="p137511352171111"></a><a name="p137511352171111"></a><span class="keyword" id="keyword3382195172513"><a name="keyword3382195172513"></a><a name="keyword3382195172513"></a>工作负载访问方式</span>设置</p>
</td>
<td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p4182624982"><a name="p4182624982"></a><a name="p4182624982"></a><a href="集群内访问.md#section212517910573">通过kubectl命令实现集群内访问</a></p>
</td>
</tr>
<tr id="row19182224388"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1018213241681"><a name="p1018213241681"></a><a name="p1018213241681"></a><a href="VPC内网访问.md#section1234016392534">通过kubectl命令实现VPC内访问</a></p>
</td>
</tr>
<tr id="row466132092816"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p266212204289"><a name="p266212204289"></a><a name="p266212204289"></a><a href="公网访问-四层负载均衡.md#section1944313158364">通过kubectl命令行实现四层负载均衡</a></p>
</td>
</tr>
<tr id="row1126165612109"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1312915681012"><a name="p1312915681012"></a><a name="p1312915681012"></a><a href="公网访问-弹性IP.md#section1944313158364">通过kubectl命令实现弹性IP访问</a></p>
</td>
</tr>
<tr id="row1160716228301"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1560712212307"><a name="p1560712212307"></a><a name="p1560712212307"></a><a href="公网访问-NAT网关.md#section1944313158364">通过kubectl命令行实现NAT网关</a></p>
</td>
</tr>
<tr id="row18129145691015"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p912935641014"><a name="p912935641014"></a><a name="p912935641014"></a><a href="七层负载均衡（Ingress）.md#section1944313158364">通过kubectl命令实现七层负载均衡</a></p>
</td>
</tr>
<tr id="row612955614108"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p171821246813"><a name="p171821246813"></a><a name="p171821246813"></a><span class="keyword" id="keyword763883513251"><a name="keyword763883513251"></a><a name="keyword763883513251"></a>工作负载高级设置</span></p>
</td>
<td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p201821924182"><a name="p201821924182"></a><a name="p201821924182"></a><a href="设置容器生命周期.md#section151181981167">设置容器生命周期-Yaml样例</a></p>
</td>
</tr>
<tr id="row1151169125"><td class="cellrowborder" rowspan="2" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p96316171219"><a name="p96316171219"></a><a name="p96316171219"></a><span class="keyword" id="keyword176433212251"><a name="keyword176433212251"></a><a name="keyword176433212251"></a>任务管理</span></p>
</td>
<td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p961016191214"><a name="p961016191214"></a><a name="p961016191214"></a><a href="创建普通任务.md#section450152719412">使用kubectl创建Job</a></p>
</td>
</tr>
<tr id="row143011122131214"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p83011622121215"><a name="p83011622121215"></a><a name="p83011622121215"></a><a href="创建定时任务.md#section13519162224919">使用kubectl创建CronJob</a></p>
</td>
</tr>
<tr id="row9301132271214"><td class="cellrowborder" rowspan="2" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p10301122121214"><a name="p10301122121214"></a><a name="p10301122121214"></a><span class="keyword" id="keyword73118308259"><a name="keyword73118308259"></a><a name="keyword73118308259"></a>配置中心</span></p>
</td>
<td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p193011222120"><a name="p193011222120"></a><a name="p193011222120"></a><a href="创建配置项.md#section639712716372">使用kubectl创建配置项</a></p>
</td>
</tr>
<tr id="row193016226127"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p113035222125"><a name="p113035222125"></a><a name="p113035222125"></a><a href="创建密钥.md#section821112149514">使用kubectl创建密钥</a></p>
</td>
</tr>
<tr id="row330382213129"><td class="cellrowborder" rowspan="6" valign="top" width="21%" headers="mcps1.2.3.1.1 "><p id="p3303122213127"><a name="p3303122213127"></a><a name="p3303122213127"></a><span class="keyword" id="keyword18525444172517"><a name="keyword18525444172517"></a><a name="keyword18525444172517"></a>存储管理</span></p>
</td>
<td class="cellrowborder" valign="top" width="79%" headers="mcps1.2.3.1.2 "><p id="p230382281218"><a name="p230382281218"></a><a name="p230382281218"></a><a href="使用云硬盘存储卷.md#section198505107598">使用kubectl创建云硬盘</a></p>
</td>
</tr>
<tr id="row63031222191210"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1530316221124"><a name="p1530316221124"></a><a name="p1530316221124"></a><a href="使用云硬盘存储卷.md#section1996254515127">使用kubectl挂载云硬盘</a></p>
</td>
</tr>
<tr id="row83032227128"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p10303132241217"><a name="p10303132241217"></a><a name="p10303132241217"></a><a href="使用文件存储卷.md#section5806637172015">使用kubectl创建文件存储</a></p>
</td>
</tr>
<tr id="row141561920171419"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p2015614205145"><a name="p2015614205145"></a><a name="p2015614205145"></a><a href="使用文件存储卷.md#section1094712153215">使用kubectl挂载文件存储</a></p>
</td>
</tr>
<tr id="row1156920181411"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p17156520121413"><a name="p17156520121413"></a><a name="p17156520121413"></a><a href="使用对象存储卷.md#section102883211413">使用kubectl创建对象存储</a></p>
</td>
</tr>
<tr id="row5156320151417"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1315614209147"><a name="p1315614209147"></a><a name="p1315614209147"></a><a href="使用对象存储卷.md#section83940541116">使用kubectl挂载对象存储</a></p>
</td>
</tr>
</tbody>
</table>

