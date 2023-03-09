# Service Annotations说明<a name="cce_10_0385"></a>

CCE提供一些使用Service的高级功能，这些功能使用时可以通过给YAML添加注解Annotation实现。具体的Annotation如下表所示。

Service的Annotation主要是Service对接ELB时需要指定的参数，详细的使用方法请参见[通过kubectl命令行创建-自动创建ELB](负载均衡(LoadBalancer).md#section12168131904611)。

**表 1**  Service Annotation

<a name="table133089105019"></a>
<table><thead align="left"><tr id="row11330199501"><th class="cellrowborder" valign="top" width="21%" id="mcps1.2.6.1.1"><p id="p173306915017"><a name="p173306915017"></a><a name="p173306915017"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="11.06%" id="mcps1.2.6.1.2"><p id="p1766813392229"><a name="p1766813392229"></a><a name="p1766813392229"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="35.44%" id="mcps1.2.6.1.3"><p id="p133301795508"><a name="p133301795508"></a><a name="p133301795508"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="19.52%" id="mcps1.2.6.1.4"><p id="p498113216229"><a name="p498113216229"></a><a name="p498113216229"></a>控制台默认取值</p>
</th>
<th class="cellrowborder" valign="top" width="12.98%" id="mcps1.2.6.1.5"><p id="p2060351510225"><a name="p2060351510225"></a><a name="p2060351510225"></a>支持的集群版本</p>
</th>
</tr>
</thead>
<tbody><tr id="row433017915509"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p17331159135017"><a name="p17331159135017"></a><a name="p17331159135017"></a>kubernetes.io/elb.class</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p9668133962219"><a name="p9668133962219"></a><a name="p9668133962219"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p17331169135014"><a name="p17331169135014"></a><a name="p17331169135014"></a>请根据不同的应用场景和功能需求选择合适的负载均衡器类型。</p>
<p id="p143311298508"><a name="p143311298508"></a><a name="p143311298508"></a>取值如下：</p>
<a name="ul3415201212612"></a><a name="ul3415201212612"></a><ul id="ul3415201212612"><li>union：共享型负载均衡。</li><li>performance：独享型负载均衡，仅支持1.17及以上集群，详情请参见<a href="https://support.huaweicloud.com/productdesc-elb/elb_pro_0004.html" target="_blank" rel="noopener noreferrer">共享型弹性负载均衡与独享型负载均衡的功能区别</a></li></ul>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p598114218226"><a name="p598114218226"></a><a name="p598114218226"></a>performance</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p156031515142220"><a name="p156031515142220"></a><a name="p156031515142220"></a>v1.9及以上</p>
</td>
</tr>
<tr id="row1616210113222"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p816218112216"><a name="p816218112216"></a><a name="p816218112216"></a>kubernetes.io/elb.id</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p18668163942216"><a name="p18668163942216"></a><a name="p18668163942216"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p1435464793910"><a name="p1435464793910"></a><a name="p1435464793910"></a>为负载均衡实例的ID，取值范围：1-100字符。</p>
<p id="p123611341161318"><a name="p123611341161318"></a><a name="p123611341161318"></a>在关联已有ELB时：必填。</p>
<p id="p735464753918"><a name="p735464753918"></a><a name="p735464753918"></a><strong id="b10354347133914"><a name="b10354347133914"></a><a name="b10354347133914"></a>获取方法：</strong></p>
<p id="p1335417476396"><a name="p1335417476396"></a><a name="p1335417476396"></a>在控制台的<span class="uicontrol" id="uicontrol1535474753911"><a name="uicontrol1535474753911"></a><a name="uicontrol1535474753911"></a>“服务列表”</span>中，单击<span class="uicontrol" id="uicontrol13541247103920"><a name="uicontrol13541247103920"></a><a name="uicontrol13541247103920"></a>“网络 &gt; 弹性负载均衡 ELB”</span>，单击ELB的名称，在ELB详情页的<span class="uicontrol" id="uicontrol1235454713918"><a name="uicontrol1235454713918"></a><a name="uicontrol1235454713918"></a>“基本信息”</span>页签下找到<span class="uicontrol" id="uicontrol735414773911"><a name="uicontrol735414773911"></a><a name="uicontrol735414773911"></a>“ID”</span>字段复制即可。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p179816242213"><a name="p179816242213"></a><a name="p179816242213"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p106034154225"><a name="p106034154225"></a><a name="p106034154225"></a>v1.9及以上</p>
</td>
</tr>
<tr id="row17461282217"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p1455852314214"><a name="p1455852314214"></a><a name="p1455852314214"></a>kubernetes.io/elb.protocol-port</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p14668143915226"><a name="p14668143915226"></a><a name="p14668143915226"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p955862311215"><a name="p955862311215"></a><a name="p955862311215"></a>Service使用7层能力配置端口。</p>
<p id="p4103673472"><a name="p4103673472"></a><a name="p4103673472"></a>详细使用请参见<a href="负载均衡(LoadBalancer).md#section833011453318">Service使用HTTP</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p189811021228"><a name="p189811021228"></a><a name="p189811021228"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p4603415122219"><a name="p4603415122219"></a><a name="p4603415122219"></a>v1.19.16及以上</p>
</td>
</tr>
<tr id="row161302114216"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p2558132317219"><a name="p2558132317219"></a><a name="p2558132317219"></a>kubernetes.io/elb.cert-id</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p366893952218"><a name="p366893952218"></a><a name="p366893952218"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p455812318218"><a name="p455812318218"></a><a name="p455812318218"></a>Service使用7层能力配置HTTPS证书。</p>
<p id="p241793516478"><a name="p241793516478"></a><a name="p241793516478"></a>详细使用请参见<a href="负载均衡(LoadBalancer).md#section833011453318">Service使用HTTP</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p59812216227"><a name="p59812216227"></a><a name="p59812216227"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p1960311516226"><a name="p1960311516226"></a><a name="p1960311516226"></a>v1.19.16及以上</p>
</td>
</tr>
<tr id="row790233013543"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p143324917501"><a name="p143324917501"></a><a name="p143324917501"></a>kubernetes.io/elb.subnet-id</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p1666833942211"><a name="p1666833942211"></a><a name="p1666833942211"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p7332119105010"><a name="p7332119105010"></a><a name="p7332119105010"></a>为集群所在子网的ID，取值范围：1-100字符。</p>
<a name="ul19332189145019"></a><a name="ul19332189145019"></a><ul id="ul19332189145019"><li>Kubernetes v1.11.7-r0及以下版本的集群自动创建时：必填</li><li>Kubernetes v1.11.7-r0以上版本的集群：可不填。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p398119212226"><a name="p398119212226"></a><a name="p398119212226"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p1760321518227"><a name="p1760321518227"></a><a name="p1760321518227"></a>v1.11.7-r0以下必填</p>
<p id="p137315821210"><a name="p137315821210"></a><a name="p137315821210"></a>v1.11.7-r0以上该字段废弃</p>
</td>
</tr>
<tr id="row523155017545"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p433229115017"><a name="p433229115017"></a><a name="p433229115017"></a>kubernetes.io/elb.enterpriseID</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p9668173910225"><a name="p9668173910225"></a><a name="p9668173910225"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p1833312925015"><a name="p1833312925015"></a><a name="p1833312925015"></a><strong id="b133314910503"><a name="b133314910503"></a><a name="b133314910503"></a>v1.15及以上版本的集群支持此字段，v1.15以下版本默认创建到default项目下。</strong></p>
<p id="p153331592508"><a name="p153331592508"></a><a name="p153331592508"></a>为ELB企业项目ID，选择后可以直接创建在具体的ELB企业项目下。</p>
<p id="p63331395501"><a name="p63331395501"></a><a name="p63331395501"></a>该字段不传（或传为字符串'0'），则将资源绑定给默认企业项目。</p>
<p id="p233313917501"><a name="p233313917501"></a><a name="p233313917501"></a><strong id="b733349135014"><a name="b733349135014"></a><a name="b733349135014"></a>获取方法：</strong></p>
<p id="p833389105013"><a name="p833389105013"></a><a name="p833389105013"></a>登录控制台后，单击顶部菜单右侧的<span class="uicontrol" id="uicontrol633319205011"><a name="uicontrol633319205011"></a><a name="uicontrol633319205011"></a>“企业 &gt; 项目管理”</span>，在打开的企业项目列表中单击要加入的企业项目名称，进入企业项目详情页，找到<span class="uicontrol" id="uicontrol633399135010"><a name="uicontrol633399135010"></a><a name="uicontrol633399135010"></a>“ID”</span>字段复制即可。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p139818202217"><a name="p139818202217"></a><a name="p139818202217"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p1760391512227"><a name="p1760391512227"></a><a name="p1760391512227"></a>v1.15及以上</p>
</td>
</tr>
<tr id="row8332096503"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p839452715462"><a name="p839452715462"></a><a name="p839452715462"></a>kubernetes.io/elb.autocreate</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p14668133910225"><a name="p14668133910225"></a><a name="p14668133910225"></a><a href="#table148341447193017">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p3394827134612"><a name="p3394827134612"></a><a name="p3394827134612"></a>自动创建service关联的ELB</p>
<p id="p113941527154613"><a name="p113941527154613"></a><a name="p113941527154613"></a><strong id="b8394327204611"><a name="b8394327204611"></a><a name="b8394327204611"></a>示例：</strong></p>
<a name="ul17394182711462"></a><a name="ul17394182711462"></a><ul id="ul17394182711462"><li>公网自动创建：<p id="p339413273467"><a name="p339413273467"></a><a name="p339413273467"></a>值为 '{"type":"public","bandwidth_name":"cce-bandwidth-1551163379627","bandwidth_chargemode":"bandwidth","bandwidth_size":5,"bandwidth_sharetype":"PER","eip_type":"5_bgp","name":"james"}'</p>
</li><li>私网自动创建：<p id="p14395132717468"><a name="p14395132717468"></a><a name="p14395132717468"></a>值为 '{"type":"inner", "name": "A-location-d-test"}'</p>
</li></ul>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p17981152122216"><a name="p17981152122216"></a><a name="p17981152122216"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p16603715192210"><a name="p16603715192210"></a><a name="p16603715192210"></a>v1.9及以上</p>
</td>
</tr>
<tr id="row19290194419413"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p1033915126419"><a name="p1033915126419"></a><a name="p1033915126419"></a>kubernetes.io/elb.adaptive-weight</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p16339121215419"><a name="p16339121215419"></a><a name="p16339121215419"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p94003246415"><a name="p94003246415"></a><a name="p94003246415"></a>根据Pod动态调整ELB后端云服务器的权重。每个Pod收到的负载请求更加均衡。</p>
<a name="ul74009241447"></a><a name="ul74009241447"></a><ul id="ul74009241447"><li>开启：true</li><li>关闭：false</li></ul>
<p id="p10400102420420"><a name="p10400102420420"></a><a name="p10400102420420"></a>该参数仅1.21及以上集群适用，且ELB直通Pod场景下无效。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p66761430349"><a name="p66761430349"></a><a name="p66761430349"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p163318141620"><a name="p163318141620"></a><a name="p163318141620"></a>v1.21及以上</p>
</td>
</tr>
<tr id="row1333313918508"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p1133339115016"><a name="p1133339115016"></a><a name="p1133339115016"></a>kubernetes.io/elb.lb-algorithm</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p76681739142217"><a name="p76681739142217"></a><a name="p76681739142217"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p0333699508"><a name="p0333699508"></a><a name="p0333699508"></a>后端云服务器组的负载均衡算法。</p>
<p id="p6333198503"><a name="p6333198503"></a><a name="p6333198503"></a>取值范围：</p>
<a name="ul13337919508"></a><a name="ul13337919508"></a><ul id="ul13337919508"><li>ROUND_ROBIN：加权轮询算法。</li><li>LEAST_CONNECTIONS：加权最少连接算法。</li><li>SOURCE_IP：源IP算法。</li></ul>
<p id="p833315910507"><a name="p833315910507"></a><a name="p833315910507"></a>当该字段的取值为SOURCE_IP时，后端云服务器组绑定的后端云服务器的weight字段无效。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p149811926226"><a name="p149811926226"></a><a name="p149811926226"></a>ROUND_ROBIN</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p8603151517229"><a name="p8603151517229"></a><a name="p8603151517229"></a>v1.9及以上</p>
</td>
</tr>
<tr id="row1533329185018"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p1533313905015"><a name="p1533313905015"></a><a name="p1533313905015"></a>kubernetes.io/elb.health-check-flag</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p156681639202214"><a name="p156681639202214"></a><a name="p156681639202214"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p1833315910509"><a name="p1833315910509"></a><a name="p1833315910509"></a>是否开启ELB健康检查功能。</p>
<a name="ul19333199205012"></a><a name="ul19333199205012"></a><ul id="ul19333199205012"><li>开启：“（空值）”或“on”</li><li>关闭：“off”</li></ul>
<p id="p144301330171416"><a name="p144301330171416"></a><a name="p144301330171416"></a>开启时需同时填写<a href="#table19192143412319">kubernetes.io/elb.health-check-option</a>字段。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p4981142142210"><a name="p4981142142210"></a><a name="p4981142142210"></a>off</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p1060391515223"><a name="p1060391515223"></a><a name="p1060391515223"></a>v1.9及以上</p>
</td>
</tr>
<tr id="row14334169195010"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p43341794509"><a name="p43341794509"></a><a name="p43341794509"></a>kubernetes.io/elb.health-check-option</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p866823915227"><a name="p866823915227"></a><a name="p866823915227"></a><a href="#table19192143412319">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p933489175020"><a name="p933489175020"></a><a name="p933489175020"></a>ELB健康检查配置选项。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p698117220226"><a name="p698117220226"></a><a name="p698117220226"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p56031815152216"><a name="p56031815152216"></a><a name="p56031815152216"></a>v1.9及以上</p>
</td>
</tr>
<tr id="row68561030194816"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p751093484811"><a name="p751093484811"></a><a name="p751093484811"></a>kubernetes.io/elb.pass-through</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p1566812397226"><a name="p1566812397226"></a><a name="p1566812397226"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p10510123411481"><a name="p10510123411481"></a><a name="p10510123411481"></a>集群内访问Service是否经过ELB。具体使用场景和说明请参见<a href="LoadBalancer类型Service使用pass-through能力.md">LoadBalancer类型Service使用pass-through能力</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p139821628225"><a name="p139821628225"></a><a name="p139821628225"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p196032155220"><a name="p196032155220"></a><a name="p196032155220"></a>v1.19及以上</p>
</td>
</tr>
<tr id="row638444875814"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p9331159155018"><a name="p9331159155018"></a><a name="p9331159155018"></a>kubernetes.io/elb.session-affinity-mode</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p5668113917226"><a name="p5668113917226"></a><a name="p5668113917226"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p533113915503"><a name="p533113915503"></a><a name="p533113915503"></a>负载均衡监听是基于IP地址的会话保持，即来自同一IP地址的访问请求转发到同一台后端服务器上。</p>
<a name="ul113311191508"></a><a name="ul113311191508"></a><ul id="ul113311191508"><li>不启用：不填写该参数。</li><li>开启会话保持：需增加该参数，取值“SOURCE_IP”，表示基于源IP地址。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p39821428221"><a name="p39821428221"></a><a name="p39821428221"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p1603215122213"><a name="p1603215122213"></a><a name="p1603215122213"></a>v1.9及以上</p>
</td>
</tr>
<tr id="row11233327102120"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p3108162817536"><a name="p3108162817536"></a><a name="p3108162817536"></a>kubernetes.io/elb.acl-id</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p444154814214"><a name="p444154814214"></a><a name="p444154814214"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p1944114852118"><a name="p1944114852118"></a><a name="p1944114852118"></a>为ELB设置IP地址黑名单或白名单时需填写，参数值为ELB的IP地址组ID，参见<a href="https://support.huaweicloud.com/usermanual-elb/elb_ug_ip_0000.html" target="_blank" rel="noopener noreferrer">IP地址组</a>。</p>
<p id="p11305142011715"><a name="p11305142011715"></a><a name="p11305142011715"></a><strong id="b186313322534"><a name="b186313322534"></a><a name="b186313322534"></a>该参数仅独享型ELB生效，且仅在新建Service或指定新的服务端口（监听器）时生效。</strong></p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p366117719221"><a name="p366117719221"></a><a name="p366117719221"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p534519162717"><a name="p534519162717"></a><a name="p534519162717"></a>v1.19.16</p>
<p id="p53459982715"><a name="p53459982715"></a><a name="p53459982715"></a>v1.21.4</p>
</td>
</tr>
<tr id="row6449193822114"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p10852147165310"><a name="p10852147165310"></a><a name="p10852147165310"></a>kubernetes.io/elb.acl-status</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p34411648142118"><a name="p34411648142118"></a><a name="p34411648142118"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p54411048122120"><a name="p54411048122120"></a><a name="p54411048122120"></a>为ELB设置IP地址黑名单或白名单时需填写，取值为'on'，表示开启访问控制。</p>
<p id="p122721832173816"><a name="p122721832173816"></a><a name="p122721832173816"></a><strong id="b537231114173"><a name="b537231114173"></a><a name="b537231114173"></a>该参数仅独享型ELB生效，且仅在新建Service或指定新的服务端口（监听器）时生效。</strong></p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p20901799225"><a name="p20901799225"></a><a name="p20901799225"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p10203141172716"><a name="p10203141172716"></a><a name="p10203141172716"></a>v1.19.16</p>
<p id="p720312111274"><a name="p720312111274"></a><a name="p720312111274"></a>v1.21.4</p>
</td>
</tr>
<tr id="row4780133515212"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p429616418547"><a name="p429616418547"></a><a name="p429616418547"></a>kubernetes.io/elb.acl-type</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p1744124852111"><a name="p1744124852111"></a><a name="p1744124852111"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p16441124842117"><a name="p16441124842117"></a><a name="p16441124842117"></a>为ELB设置IP地址黑名单或白名单时需填写。</p>
<a name="ul114418485212"></a><a name="ul114418485212"></a><ul id="ul114418485212"><li>black：表示黑名单，所选IP地址组无法访问ELB地址。</li><li>white：表示白名单，仅所选IP地址组可以访问ELB地址。</li></ul>
<p id="p1234783483819"><a name="p1234783483819"></a><a name="p1234783483819"></a><strong id="b7562124110533"><a name="b7562124110533"></a><a name="b7562124110533"></a>该参数仅独享型ELB生效，且仅在新建Service或指定新的服务端口（监听器）时生效。</strong></p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p1445417107220"><a name="p1445417107220"></a><a name="p1445417107220"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p11478171212717"><a name="p11478171212717"></a><a name="p11478171212717"></a>v1.19.16</p>
<p id="p104781712202713"><a name="p104781712202713"></a><a name="p104781712202713"></a>v1.21.4</p>
</td>
</tr>
<tr id="row1421317512156"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p12624252121514"><a name="p12624252121514"></a><a name="p12624252121514"></a>kubernetes.io/elb.session-affinity-option</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p19668123917228"><a name="p19668123917228"></a><a name="p19668123917228"></a><a href="#table3340195463412">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p5624145218150"><a name="p5624145218150"></a><a name="p5624145218150"></a>ELB会话保持配置选项，可设置会话保持的超时时间。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p9982727229"><a name="p9982727229"></a><a name="p9982727229"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p260320155223"><a name="p260320155223"></a><a name="p260320155223"></a>v1.9及以上</p>
</td>
</tr>
<tr id="row5492113210146"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.1 "><p id="p93349995013"><a name="p93349995013"></a><a name="p93349995013"></a>kubernetes.io/hws-hostNetwork</p>
</td>
<td class="cellrowborder" valign="top" width="11.06%" headers="mcps1.2.6.1.2 "><p id="p76688396226"><a name="p76688396226"></a><a name="p76688396226"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="35.44%" headers="mcps1.2.6.1.3 "><p id="p6334798502"><a name="p6334798502"></a><a name="p6334798502"></a>为标记工作负载服务是否使用主机网络模式。如果Pod使用的主机网络，开启这个annotation会ELB转发到主机网络的方式对接。</p>
<p id="p14334095506"><a name="p14334095506"></a><a name="p14334095506"></a>取值范围：“true”或者“false”</p>
<p id="p11863913162416"><a name="p11863913162416"></a><a name="p11863913162416"></a>默认是“false”，表示未使用主机网络。</p>
</td>
<td class="cellrowborder" valign="top" width="19.52%" headers="mcps1.2.6.1.4 "><p id="p698214232218"><a name="p698214232218"></a><a name="p698214232218"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="12.98%" headers="mcps1.2.6.1.5 "><p id="p1860331572220"><a name="p1860331572220"></a><a name="p1860331572220"></a>v1.9及以上</p>
</td>
</tr>
</tbody>
</table>

**表 2**  elb.autocreate字段数据结构说明

<a name="table148341447193017"></a>
<table><thead align="left"><tr id="cce_10_0014_row183958279468"><th class="cellrowborder" valign="top" width="25.069999999999997%" id="mcps1.2.5.1.1"><p id="cce_10_0014_p439572712466"><a name="cce_10_0014_p439572712466"></a><a name="cce_10_0014_p439572712466"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.29%" id="mcps1.2.5.1.2"><p id="cce_10_0014_p5395162716461"><a name="cce_10_0014_p5395162716461"></a><a name="cce_10_0014_p5395162716461"></a>是否必填</p>
</th>
<th class="cellrowborder" valign="top" width="13.56%" id="mcps1.2.5.1.3"><p id="cce_10_0014_p1839522764612"><a name="cce_10_0014_p1839522764612"></a><a name="cce_10_0014_p1839522764612"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="49.08%" id="mcps1.2.5.1.4"><p id="cce_10_0014_p13395182713462"><a name="cce_10_0014_p13395182713462"></a><a name="cce_10_0014_p13395182713462"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="cce_10_0014_row17395132744615"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p239612715462"><a name="cce_10_0014_p239612715462"></a><a name="cce_10_0014_p239612715462"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p939602714615"><a name="cce_10_0014_p939602714615"></a><a name="cce_10_0014_p939602714615"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p039672712468"><a name="cce_10_0014_p039672712468"></a><a name="cce_10_0014_p039672712468"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p1939611278467"><a name="cce_10_0014_p1939611278467"></a><a name="cce_10_0014_p1939611278467"></a>自动创建的负载均衡的名称。</p>
<p id="cce_10_0014_p1339672794620"><a name="cce_10_0014_p1339672794620"></a><a name="cce_10_0014_p1339672794620"></a>取值范围：1-64个字符，小写字母，数字，下划线，小写字母开头，小写字母或者数字结尾。</p>
<p id="cce_10_0014_p1039616277465"><a name="cce_10_0014_p1039616277465"></a><a name="cce_10_0014_p1039616277465"></a>默认名称：cce-lb+service.UID</p>
</td>
</tr>
<tr id="cce_10_0014_row153968276468"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p1939617273464"><a name="cce_10_0014_p1939617273464"></a><a name="cce_10_0014_p1939617273464"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p1739622713461"><a name="cce_10_0014_p1739622713461"></a><a name="cce_10_0014_p1739622713461"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p16396102784619"><a name="cce_10_0014_p16396102784619"></a><a name="cce_10_0014_p16396102784619"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p14396172764615"><a name="cce_10_0014_p14396172764615"></a><a name="cce_10_0014_p14396172764615"></a>负载均衡实例网络类型，公网或者私网。</p>
<a name="cce_10_0014_ul23961827154617"></a><a name="cce_10_0014_ul23961827154617"></a><ul id="cce_10_0014_ul23961827154617"><li>public：公网型负载均衡</li><li>inner：私网型负载均衡</li></ul>
<p id="cce_10_0014_p539752754611"><a name="cce_10_0014_p539752754611"></a><a name="cce_10_0014_p539752754611"></a>默认类型：inner</p>
</td>
</tr>
<tr id="cce_10_0014_row2397927194613"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p12397122718464"><a name="cce_10_0014_p12397122718464"></a><a name="cce_10_0014_p12397122718464"></a>bandwidth_name</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p1129745332217"><a name="cce_10_0014_p1129745332217"></a><a name="cce_10_0014_p1129745332217"></a>公网型负载均衡必填</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p16397182734610"><a name="cce_10_0014_p16397182734610"></a><a name="cce_10_0014_p16397182734610"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p113972278461"><a name="cce_10_0014_p113972278461"></a><a name="cce_10_0014_p113972278461"></a>带宽的名称，默认值为：cce-bandwidth-******。</p>
<p id="cce_10_0014_p1439717273462"><a name="cce_10_0014_p1439717273462"></a><a name="cce_10_0014_p1439717273462"></a>取值范围：1-64个字符，小写字母，数字，下划线，小写字母开头，小写字母或者数字结尾。</p>
</td>
</tr>
<tr id="cce_10_0014_row1439722794619"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p7397182720466"><a name="cce_10_0014_p7397182720466"></a><a name="cce_10_0014_p7397182720466"></a>bandwidth_chargemode</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p71019556225"><a name="cce_10_0014_p71019556225"></a><a name="cce_10_0014_p71019556225"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p193974278460"><a name="cce_10_0014_p193974278460"></a><a name="cce_10_0014_p193974278460"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p83981227124616"><a name="cce_10_0014_p83981227124616"></a><a name="cce_10_0014_p83981227124616"></a>带宽付费模式。</p>
<a name="cce_10_0014_ul33989277466"></a><a name="cce_10_0014_ul33989277466"></a><ul id="cce_10_0014_ul33989277466"><li>bandwidth：按带宽</li><li>traffic：按流量</li></ul>
<p id="cce_10_0014_p12711141632814"><a name="cce_10_0014_p12711141632814"></a><a name="cce_10_0014_p12711141632814"></a>默认类型：bandwidth</p>
</td>
</tr>
<tr id="cce_10_0014_row19398122716461"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p739892794619"><a name="cce_10_0014_p739892794619"></a><a name="cce_10_0014_p739892794619"></a>bandwidth_size</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p639862719463"><a name="cce_10_0014_p639862719463"></a><a name="cce_10_0014_p639862719463"></a>公网型负载均衡必填</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p439882734619"><a name="cce_10_0014_p439882734619"></a><a name="cce_10_0014_p439882734619"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p14398927134615"><a name="cce_10_0014_p14398927134615"></a><a name="cce_10_0014_p14398927134615"></a>带宽大小，<span>默认1Mbit/s~2000Mbit/s</span>，请根据Region带宽支持范围设置。</p>
</td>
</tr>
<tr id="cce_10_0014_row193991627164615"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p15399627174614"><a name="cce_10_0014_p15399627174614"></a><a name="cce_10_0014_p15399627174614"></a>bandwidth_sharetype</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p1239962754620"><a name="cce_10_0014_p1239962754620"></a><a name="cce_10_0014_p1239962754620"></a>公网型负载均衡必填</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p4399327124618"><a name="cce_10_0014_p4399327124618"></a><a name="cce_10_0014_p4399327124618"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p6399227154620"><a name="cce_10_0014_p6399227154620"></a><a name="cce_10_0014_p6399227154620"></a>带宽共享方式。</p>
<a name="cce_10_0014_ul1539932712464"></a><a name="cce_10_0014_ul1539932712464"></a><ul id="cce_10_0014_ul1539932712464"><li>PER：独享带宽</li></ul>
</td>
</tr>
<tr id="cce_10_0014_row139952712463"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p1139952764611"><a name="cce_10_0014_p1139952764611"></a><a name="cce_10_0014_p1139952764611"></a>eip_type</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p266247192314"><a name="cce_10_0014_p266247192314"></a><a name="cce_10_0014_p266247192314"></a>公网型负载均衡必填</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p84001027124612"><a name="cce_10_0014_p84001027124612"></a><a name="cce_10_0014_p84001027124612"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p440013273464"><a name="cce_10_0014_p440013273464"></a><a name="cce_10_0014_p440013273464"></a>弹性公网IP类型。</p>
<a name="cce_10_0014_ul18765175214406"></a><a name="cce_10_0014_ul18765175214406"></a><ul id="cce_10_0014_ul18765175214406"><li>5_telcom：电信</li><li>5_union：联通</li><li>5_bgp：全动态BGP</li><li>5_sbgp：静态BGP</li></ul>
</td>
</tr>
<tr id="cce_10_0014_row1387015112170"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p11871111191717"><a name="cce_10_0014_p11871111191717"></a><a name="cce_10_0014_p11871111191717"></a>vip_subnet_cidr_id</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p9871121112173"><a name="cce_10_0014_p9871121112173"></a><a name="cce_10_0014_p9871121112173"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p3871151131716"><a name="cce_10_0014_p3871151131716"></a><a name="cce_10_0014_p3871151131716"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p1687141121716"><a name="cce_10_0014_p1687141121716"></a><a name="cce_10_0014_p1687141121716"></a>指定ELB所在的子网。1.21及以上版本支持。</p>
<p id="cce_10_0014_p1579416343117"><a name="cce_10_0014_p1579416343117"></a><a name="cce_10_0014_p1579416343117"></a>如不指定，则ELB与集群在同一个子网。</p>
</td>
</tr>
<tr id="cce_10_0014_row20400102713466"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p140015271469"><a name="cce_10_0014_p140015271469"></a><a name="cce_10_0014_p140015271469"></a>available_zone</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p15400727164618"><a name="cce_10_0014_p15400727164618"></a><a name="cce_10_0014_p15400727164618"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p04001927144618"><a name="cce_10_0014_p04001927144618"></a><a name="cce_10_0014_p04001927144618"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p64001827194610"><a name="cce_10_0014_p64001827194610"></a><a name="cce_10_0014_p64001827194610"></a>负载均衡所在可用区。</p>
<p id="cce_10_0014_p81475267200"><a name="cce_10_0014_p81475267200"></a><a name="cce_10_0014_p81475267200"></a>可以通过<a href="https://support.huaweicloud.com/api-elb/ListAvailabilityZones.html" target="_blank" rel="noopener noreferrer">查询可用区列表</a>获取所有支持的可用区。</p>
<p id="cce_10_0014_p2040082784615"><a name="cce_10_0014_p2040082784615"></a><a name="cce_10_0014_p2040082784615"></a>独享型负载均衡器独有字段。</p>
</td>
</tr>
<tr id="cce_10_0014_row12400122734616"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p040102718464"><a name="cce_10_0014_p040102718464"></a><a name="cce_10_0014_p040102718464"></a>l4_flavor_name</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p74011327184614"><a name="cce_10_0014_p74011327184614"></a><a name="cce_10_0014_p74011327184614"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p4401227124615"><a name="cce_10_0014_p4401227124615"></a><a name="cce_10_0014_p4401227124615"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p3911190135911"><a name="cce_10_0014_p3911190135911"></a><a name="cce_10_0014_p3911190135911"></a>四层负载均衡实例规格名称。</p>
<p id="cce_10_0014_p124018276462"><a name="cce_10_0014_p124018276462"></a><a name="cce_10_0014_p124018276462"></a>可以通过<a href="https://support.huaweicloud.com/api-elb/ListFlavors.html" target="_blank" rel="noopener noreferrer">查询规格列表</a>获取所有支持的类型。</p>
<p id="cce_10_0014_p16615412105"><a name="cce_10_0014_p16615412105"></a><a name="cce_10_0014_p16615412105"></a>独享型负载均衡器独有字段。</p>
</td>
</tr>
<tr id="cce_10_0014_row64018274461"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p94015275467"><a name="cce_10_0014_p94015275467"></a><a name="cce_10_0014_p94015275467"></a>l7_flavor_name</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p1840182714466"><a name="cce_10_0014_p1840182714466"></a><a name="cce_10_0014_p1840182714466"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p5401132754612"><a name="cce_10_0014_p5401132754612"></a><a name="cce_10_0014_p5401132754612"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p540115278464"><a name="cce_10_0014_p540115278464"></a><a name="cce_10_0014_p540115278464"></a>七层负载均衡实例规格名称。</p>
<p id="cce_10_0014_p13981524241"><a name="cce_10_0014_p13981524241"></a><a name="cce_10_0014_p13981524241"></a>可以通过<a href="https://support.huaweicloud.com/api-elb/ListFlavors.html" target="_blank" rel="noopener noreferrer">查询规格列表</a>获取所有支持的类型。</p>
<p id="cce_10_0014_p439195851013"><a name="cce_10_0014_p439195851013"></a><a name="cce_10_0014_p439195851013"></a>独享型负载均衡器独有字段。</p>
</td>
</tr>
<tr id="cce_10_0014_row17401027104619"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p2040112275467"><a name="cce_10_0014_p2040112275467"></a><a name="cce_10_0014_p2040112275467"></a>elb_virsubnet_ids</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p040262754619"><a name="cce_10_0014_p040262754619"></a><a name="cce_10_0014_p040262754619"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.56%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p1540222710464"><a name="cce_10_0014_p1540222710464"></a><a name="cce_10_0014_p1540222710464"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="49.08%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p1840292719463"><a name="cce_10_0014_p1840292719463"></a><a name="cce_10_0014_p1840292719463"></a>负载均衡后端所在子网，不填默认集群子网。不同实例规格将占用不同数量子网IP，不建议使用其他资源（如集群，节点等）的子网网段。</p>
<p id="cce_10_0014_p3476173161118"><a name="cce_10_0014_p3476173161118"></a><a name="cce_10_0014_p3476173161118"></a>独享型负载均衡器独有字段。</p>
<p id="cce_10_0014_p6628139141015"><a name="cce_10_0014_p6628139141015"></a><a name="cce_10_0014_p6628139141015"></a>示例：</p>
<pre class="screen" id="cce_10_0014_screen18587145018263"><a name="cce_10_0014_screen18587145018263"></a><a name="cce_10_0014_screen18587145018263"></a>"elb_virsubnet_ids": [
   "14567f27-8ae4-42b8-ae47-9f847a4690dd"
 ]</pre>
</td>
</tr>
</tbody>
</table>

**表 3**  elb.health-check-option字段数据结构说明

<a name="table19192143412319"></a>
<table><thead align="left"><tr id="cce_10_0014_row336018475396"><th class="cellrowborder" valign="top" width="24.95%" id="mcps1.2.5.1.1"><p id="cce_10_0014_p15360184723911"><a name="cce_10_0014_p15360184723911"></a><a name="cce_10_0014_p15360184723911"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.32%" id="mcps1.2.5.1.2"><p id="cce_10_0014_p139932420145"><a name="cce_10_0014_p139932420145"></a><a name="cce_10_0014_p139932420145"></a>是否必填</p>
</th>
<th class="cellrowborder" valign="top" width="13.5%" id="mcps1.2.5.1.3"><p id="cce_10_0014_p1036074715392"><a name="cce_10_0014_p1036074715392"></a><a name="cce_10_0014_p1036074715392"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="49.230000000000004%" id="mcps1.2.5.1.4"><p id="cce_10_0014_p036084733912"><a name="cce_10_0014_p036084733912"></a><a name="cce_10_0014_p036084733912"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="cce_10_0014_row1136012478397"><td class="cellrowborder" valign="top" width="24.95%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p1736074717393"><a name="cce_10_0014_p1736074717393"></a><a name="cce_10_0014_p1736074717393"></a>delay</p>
</td>
<td class="cellrowborder" valign="top" width="12.32%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p2099132416147"><a name="cce_10_0014_p2099132416147"></a><a name="cce_10_0014_p2099132416147"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.5%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p1360144773911"><a name="cce_10_0014_p1360144773911"></a><a name="cce_10_0014_p1360144773911"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.230000000000004%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p7361154710397"><a name="cce_10_0014_p7361154710397"></a><a name="cce_10_0014_p7361154710397"></a>开始健康检查的初始等待时间（秒）</p>
<p id="cce_10_0014_p17361184715394"><a name="cce_10_0014_p17361184715394"></a><a name="cce_10_0014_p17361184715394"></a>默认值：5，取值范围：1-50</p>
</td>
</tr>
<tr id="cce_10_0014_row163618473395"><td class="cellrowborder" valign="top" width="24.95%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p636114763916"><a name="cce_10_0014_p636114763916"></a><a name="cce_10_0014_p636114763916"></a>timeout</p>
</td>
<td class="cellrowborder" valign="top" width="12.32%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p69919246147"><a name="cce_10_0014_p69919246147"></a><a name="cce_10_0014_p69919246147"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.5%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p103611347123914"><a name="cce_10_0014_p103611347123914"></a><a name="cce_10_0014_p103611347123914"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.230000000000004%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p113611447183912"><a name="cce_10_0014_p113611447183912"></a><a name="cce_10_0014_p113611447183912"></a>健康检查的超时时间（秒）</p>
<p id="cce_10_0014_p143612047133913"><a name="cce_10_0014_p143612047133913"></a><a name="cce_10_0014_p143612047133913"></a>默认值：10，取值范围1-50</p>
</td>
</tr>
<tr id="cce_10_0014_row18361154723913"><td class="cellrowborder" valign="top" width="24.95%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p136144716396"><a name="cce_10_0014_p136144716396"></a><a name="cce_10_0014_p136144716396"></a>max_retries</p>
</td>
<td class="cellrowborder" valign="top" width="12.32%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p166343581149"><a name="cce_10_0014_p166343581149"></a><a name="cce_10_0014_p166343581149"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.5%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p17361114717395"><a name="cce_10_0014_p17361114717395"></a><a name="cce_10_0014_p17361114717395"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.230000000000004%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p14361114712397"><a name="cce_10_0014_p14361114712397"></a><a name="cce_10_0014_p14361114712397"></a>健康检查的最大重试次数</p>
<p id="cce_10_0014_p6361114733910"><a name="cce_10_0014_p6361114733910"></a><a name="cce_10_0014_p6361114733910"></a>默认值：3，取值范围1-10</p>
</td>
</tr>
<tr id="cce_10_0014_row9361104720394"><td class="cellrowborder" valign="top" width="24.95%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p1636111476395"><a name="cce_10_0014_p1636111476395"></a><a name="cce_10_0014_p1636111476395"></a>protocol</p>
</td>
<td class="cellrowborder" valign="top" width="12.32%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p763495881417"><a name="cce_10_0014_p763495881417"></a><a name="cce_10_0014_p763495881417"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.5%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p14361144716395"><a name="cce_10_0014_p14361144716395"></a><a name="cce_10_0014_p14361144716395"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.230000000000004%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p15361164723916"><a name="cce_10_0014_p15361164723916"></a><a name="cce_10_0014_p15361164723916"></a>健康检查的协议</p>
<p id="cce_10_0014_p2361204719390"><a name="cce_10_0014_p2361204719390"></a><a name="cce_10_0014_p2361204719390"></a>默认值：取关联服务的协议</p>
<p id="cce_10_0014_p143617474391"><a name="cce_10_0014_p143617474391"></a><a name="cce_10_0014_p143617474391"></a>取值范围：“TCP”、“UDP”或者“HTTP”</p>
</td>
</tr>
<tr id="cce_10_0014_row036113475395"><td class="cellrowborder" valign="top" width="24.95%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p93612047133915"><a name="cce_10_0014_p93612047133915"></a><a name="cce_10_0014_p93612047133915"></a>path</p>
</td>
<td class="cellrowborder" valign="top" width="12.32%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p159952471418"><a name="cce_10_0014_p159952471418"></a><a name="cce_10_0014_p159952471418"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.5%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p13361747173915"><a name="cce_10_0014_p13361747173915"></a><a name="cce_10_0014_p13361747173915"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.230000000000004%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p6361647183913"><a name="cce_10_0014_p6361647183913"></a><a name="cce_10_0014_p6361647183913"></a>健康检查的URL，协议是“HTTP”时配置</p>
<p id="cce_10_0014_p636184753911"><a name="cce_10_0014_p636184753911"></a><a name="cce_10_0014_p636184753911"></a>默认值：“/”</p>
<p id="cce_10_0014_p8361847153910"><a name="cce_10_0014_p8361847153910"></a><a name="cce_10_0014_p8361847153910"></a>取值范围：1-10000字符</p>
</td>
</tr>
</tbody>
</table>

**表 4**  elb.session-affinity-option字段数据结构说明

<a name="table3340195463412"></a>
<table><thead align="left"><tr id="cce_10_0014_row23591547163913"><th class="cellrowborder" valign="top" width="24.95%" id="mcps1.2.5.1.1"><p id="cce_10_0014_p6359124763911"><a name="cce_10_0014_p6359124763911"></a><a name="cce_10_0014_p6359124763911"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.139999999999999%" id="mcps1.2.5.1.2"><p id="cce_10_0014_p8442205011314"><a name="cce_10_0014_p8442205011314"></a><a name="cce_10_0014_p8442205011314"></a>是否必填</p>
</th>
<th class="cellrowborder" valign="top" width="13.69%" id="mcps1.2.5.1.3"><p id="cce_10_0014_p23601947173914"><a name="cce_10_0014_p23601947173914"></a><a name="cce_10_0014_p23601947173914"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="49.220000000000006%" id="mcps1.2.5.1.4"><p id="cce_10_0014_p19360647113911"><a name="cce_10_0014_p19360647113911"></a><a name="cce_10_0014_p19360647113911"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="cce_10_0014_row1236084719399"><td class="cellrowborder" valign="top" width="24.95%" headers="mcps1.2.5.1.1 "><p id="cce_10_0014_p1636019470393"><a name="cce_10_0014_p1636019470393"></a><a name="cce_10_0014_p1636019470393"></a>persistence_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="12.139999999999999%" headers="mcps1.2.5.1.2 "><p id="cce_10_0014_p164427503134"><a name="cce_10_0014_p164427503134"></a><a name="cce_10_0014_p164427503134"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.69%" headers="mcps1.2.5.1.3 "><p id="cce_10_0014_p1236084793919"><a name="cce_10_0014_p1236084793919"></a><a name="cce_10_0014_p1236084793919"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="49.220000000000006%" headers="mcps1.2.5.1.4 "><p id="cce_10_0014_p12360147143917"><a name="cce_10_0014_p12360147143917"></a><a name="cce_10_0014_p12360147143917"></a>当elb.session-affinity-mode是“SOURCE_IP”时生效，设置会话保持的超时时间（分钟）。</p>
<p id="cce_10_0014_p0360204713398"><a name="cce_10_0014_p0360204713398"></a><a name="cce_10_0014_p0360204713398"></a>默认值为：60，取值范围：1-60。</p>
</td>
</tr>
</tbody>
</table>

