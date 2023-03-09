# Service Annotations说明<a name="cce_01_0385"></a>

CCE提供一些使用Service的高级功能，这些功能使用时可以通过给YAML添加注解Annotation实现。具体的Annotation如下表所示。

Service的Annotation主要是Service对接ELB时需要指定的参数，详细的使用方法请参见[通过kubectl命令行创建-自动创建ELB](负载均衡(LoadBalancer)-72.md#section12168131904611)。

**表 1**  Service Annotation

<a name="table133089105019"></a>
<table><thead align="left"><tr id="row11330199501"><th class="cellrowborder" valign="top" width="37.08%" id="mcps1.2.3.1.1"><p id="p173306915017"><a name="p173306915017"></a><a name="p173306915017"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="62.92%" id="mcps1.2.3.1.2"><p id="p133301795508"><a name="p133301795508"></a><a name="p133301795508"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row433017915509"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p17331159135017"><a name="p17331159135017"></a><a name="p17331159135017"></a>kubernetes.io/elb.class</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p17331169135014"><a name="p17331169135014"></a><a name="p17331169135014"></a>请根据不同的应用场景和功能需求选择合适的负载均衡器类型。</p>
<p id="p143311298508"><a name="p143311298508"></a><a name="p143311298508"></a>取值如下：</p>
<a name="ul3415201212612"></a><a name="ul3415201212612"></a><ul id="ul3415201212612"><li>union：共享型负载均衡。</li><li>performance：独享型负载均衡，详情请参见<a href="https://support.huaweicloud.com/productdesc-elb/elb_pro_0004.html" target="_blank" rel="noopener noreferrer">共享型弹性负载均衡与独享型负载均衡的功能区别</a></li></ul>
<p id="p733118975010"><a name="p733118975010"></a><a name="p733118975010"></a>默认值：union</p>
</td>
</tr>
<tr id="row1616210113222"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p816218112216"><a name="p816218112216"></a><a name="p816218112216"></a>kubernetes.io/elb.id</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p1435464793910"><a name="p1435464793910"></a><a name="p1435464793910"></a>为负载均衡实例的ID，取值范围：1-100字符。</p>
<p id="p123611341161318"><a name="p123611341161318"></a><a name="p123611341161318"></a>在关联已有ELB时：必填。</p>
<p id="p735464753918"><a name="p735464753918"></a><a name="p735464753918"></a><strong id="b10354347133914"><a name="b10354347133914"></a><a name="b10354347133914"></a>获取方法：</strong></p>
<p id="p1335417476396"><a name="p1335417476396"></a><a name="p1335417476396"></a>在控制台的<span class="uicontrol" id="uicontrol1535474753911"><a name="uicontrol1535474753911"></a><a name="uicontrol1535474753911"></a>“服务列表”</span>中，单击<span class="uicontrol" id="uicontrol13541247103920"><a name="uicontrol13541247103920"></a><a name="uicontrol13541247103920"></a>“网络 &gt; 弹性负载均衡 ELB”</span>，单击ELB的名称，在ELB详情页的<span class="uicontrol" id="uicontrol1235454713918"><a name="uicontrol1235454713918"></a><a name="uicontrol1235454713918"></a>“基本信息”</span>页签下找到<span class="uicontrol" id="uicontrol735414773911"><a name="uicontrol735414773911"></a><a name="uicontrol735414773911"></a>“ID”</span>字段复制即可。</p>
</td>
</tr>
<tr id="row17461282217"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p1455852314214"><a name="p1455852314214"></a><a name="p1455852314214"></a>kubernetes.io/elb.protocol-port</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p955862311215"><a name="p955862311215"></a><a name="p955862311215"></a>Service使用7层能力配置端口。</p>
</td>
</tr>
<tr id="row161302114216"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p2558132317219"><a name="p2558132317219"></a><a name="p2558132317219"></a>kubernetes.io/elb.cert-id</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p455812318218"><a name="p455812318218"></a><a name="p455812318218"></a>Service使用7层能力配置HTTPS证书。</p>
</td>
</tr>
<tr id="row790233013543"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p143324917501"><a name="p143324917501"></a><a name="p143324917501"></a>kubernetes.io/elb.subnet-id</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p7332119105010"><a name="p7332119105010"></a><a name="p7332119105010"></a>为集群所在子网的ID，取值范围：1-100字符。</p>
<a name="ul19332189145019"></a><a name="ul19332189145019"></a><ul id="ul19332189145019"><li>Kubernetes v1.11.7-r0及以下版本的集群自动创建时：必填，</li><li>Kubernetes v1.11.7-r0以上版本的集群：可不填。</li></ul>
</td>
</tr>
<tr id="row523155017545"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p433229115017"><a name="p433229115017"></a><a name="p433229115017"></a>kubernetes.io/elb.enterpriseID</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p1833312925015"><a name="p1833312925015"></a><a name="p1833312925015"></a><strong id="b133314910503"><a name="b133314910503"></a><a name="b133314910503"></a>v1.15及以上版本的集群支持此字段，v1.15以下版本默认创建到default项目下。</strong></p>
<p id="p153331592508"><a name="p153331592508"></a><a name="p153331592508"></a>为ELB企业项目ID，选择后可以直接创建在具体的ELB企业项目下。</p>
<p id="p63331395501"><a name="p63331395501"></a><a name="p63331395501"></a>该字段不传（或传为字符串'0'），则将资源绑定给默认企业项目。</p>
<p id="p233313917501"><a name="p233313917501"></a><a name="p233313917501"></a><strong id="b733349135014"><a name="b733349135014"></a><a name="b733349135014"></a>获取方法：</strong></p>
<p id="p833389105013"><a name="p833389105013"></a><a name="p833389105013"></a>登录控制台后，单击顶部菜单右侧的<span class="uicontrol" id="uicontrol633319205011"><a name="uicontrol633319205011"></a><a name="uicontrol633319205011"></a>“企业 &gt; 项目管理”</span>，在打开的企业项目列表中单击要加入的企业项目名称，进入企业项目详情页，找到<span class="uicontrol" id="uicontrol633399135010"><a name="uicontrol633399135010"></a><a name="uicontrol633399135010"></a>“ID”</span>字段复制即可。</p>
</td>
</tr>
<tr id="row8332096503"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p839452715462"><a name="p839452715462"></a><a name="p839452715462"></a>kubernetes.io/elb.autocreate</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p3394827134612"><a name="p3394827134612"></a><a name="p3394827134612"></a>自动创建service关联的ELB</p>
<p id="p113941527154613"><a name="p113941527154613"></a><a name="p113941527154613"></a><strong id="b8394327204611"><a name="b8394327204611"></a><a name="b8394327204611"></a>示例：</strong></p>
<a name="ul17394182711462"></a><a name="ul17394182711462"></a><ul id="ul17394182711462"><li>公网自动创建：<p id="p339413273467"><a name="p339413273467"></a><a name="p339413273467"></a>值为 '{"type":"public","bandwidth_name":"cce-bandwidth-1551163379627","bandwidth_chargemode":"traffic","bandwidth_size":5,"bandwidth_sharetype":"PER","eip_type":"5_bgp","name":"james"}'</p>
</li><li>私网自动创建：<p id="p14395132717468"><a name="p14395132717468"></a><a name="p14395132717468"></a>值为 '{"type":"inner", "name": "A-location-d-test"}'</p>
</li></ul>
</td>
</tr>
<tr id="row1333313918508"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p1133339115016"><a name="p1133339115016"></a><a name="p1133339115016"></a>kubernetes.io/elb.lb-algorithm</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p0333699508"><a name="p0333699508"></a><a name="p0333699508"></a>默认值：“ROUND_ROBIN”，为后端云服务器组的负载均衡算法。</p>
<p id="p6333198503"><a name="p6333198503"></a><a name="p6333198503"></a>取值范围：</p>
<a name="ul13337919508"></a><a name="ul13337919508"></a><ul id="ul13337919508"><li>ROUND_ROBIN：加权轮询算法。</li><li>LEAST_CONNECTIONS：加权最少连接算法。</li><li>SOURCE_IP：源IP算法。</li></ul>
<p id="p833315910507"><a name="p833315910507"></a><a name="p833315910507"></a>当该字段的取值为SOURCE_IP时，后端云服务器组绑定的后端云服务器的weight字段无效。</p>
</td>
</tr>
<tr id="row1533329185018"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p1533313905015"><a name="p1533313905015"></a><a name="p1533313905015"></a>kubernetes.io/elb.health-check-flag</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p1833315910509"><a name="p1833315910509"></a><a name="p1833315910509"></a>是否开启ELB健康检查功能。</p>
<p id="p1233320913508"><a name="p1233320913508"></a><a name="p1233320913508"></a>默认关闭。</p>
<a name="ul19333199205012"></a><a name="ul19333199205012"></a><ul id="ul19333199205012"><li>开启：“（空值）”或“on”</li><li>关闭：“off”</li></ul>
</td>
</tr>
<tr id="row14334169195010"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p43341794509"><a name="p43341794509"></a><a name="p43341794509"></a>kubernetes.io/elb.health-check-option</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p933489175020"><a name="p933489175020"></a><a name="p933489175020"></a>ELB健康检查配置选项。</p>
</td>
</tr>
<tr id="row68561030194816"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p751093484811"><a name="p751093484811"></a><a name="p751093484811"></a>kubernetes.io/elb.pass-through</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p10510123411481"><a name="p10510123411481"></a><a name="p10510123411481"></a>集群内访问Service是否经过ELB。具体使用场景和说明请参见<a href="LoadBalancer类型Service使用pass-through能力-74.md">LoadBalancer类型Service使用pass-through能力</a>。</p>
</td>
</tr>
<tr id="row638444875814"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p9331159155018"><a name="p9331159155018"></a><a name="p9331159155018"></a>kubernetes.io/elb.session-affinity-mode</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p533113915503"><a name="p533113915503"></a><a name="p533113915503"></a>负载均衡监听是基于IP地址的会话保持，即来自同一IP地址的访问请求转发到同一台后端服务器上。</p>
<a name="ul113311191508"></a><a name="ul113311191508"></a><ul id="ul113311191508"><li>不启用：不填写该参数。</li><li>开启会话保持：需增加该参数，取值“SOURCE_IP”，表示基于源IP地址。</li></ul>
</td>
</tr>
<tr id="row1421317512156"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p12624252121514"><a name="p12624252121514"></a><a name="p12624252121514"></a>kubernetes.io/elb.session-affinity-option</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p5624145218150"><a name="p5624145218150"></a><a name="p5624145218150"></a>ELB会话保持配置选项，可设置会话保持的超时时间。</p>
</td>
</tr>
<tr id="row5492113210146"><td class="cellrowborder" valign="top" width="37.08%" headers="mcps1.2.3.1.1 "><p id="p93349995013"><a name="p93349995013"></a><a name="p93349995013"></a>kubernetes.io/hws-hostNetwork</p>
</td>
<td class="cellrowborder" valign="top" width="62.92%" headers="mcps1.2.3.1.2 "><p id="p6334798502"><a name="p6334798502"></a><a name="p6334798502"></a>为标记工作负载服务是否使用主机网络模式。如果Pod使用的主机网络，开启这个annotation会ELB转发到主机网络的方式对接。</p>
<p id="p14334095506"><a name="p14334095506"></a><a name="p14334095506"></a>默认是未使用主机网络，取值范围：“true”或者“false”</p>
</td>
</tr>
</tbody>
</table>

