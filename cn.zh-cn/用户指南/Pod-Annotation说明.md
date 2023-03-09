# Pod Annotation说明<a name="cce_01_0386"></a>

CCE提供一些使用Pod的高级功能，这些功能使用时可以通过给YAML添加注解Annotation实现。具体的Annotation如下表所示。

**表 1**  Pod Annotation

<a name="table194691458405"></a>
<table><thead align="left"><tr id="row247019514406"><th class="cellrowborder" valign="top" width="29.849999999999998%" id="mcps1.2.4.1.1"><p id="p10470205174015"><a name="p10470205174015"></a><a name="p10470205174015"></a>注解</p>
</th>
<th class="cellrowborder" valign="top" width="43.65%" id="mcps1.2.4.1.2"><p id="p1847015134012"><a name="p1847015134012"></a><a name="p1847015134012"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="26.5%" id="mcps1.2.4.1.3"><p id="p14707510401"><a name="p14707510401"></a><a name="p14707510401"></a>默认值</p>
</th>
</tr>
</thead>
<tbody><tr id="row9470558404"><td class="cellrowborder" valign="top" width="29.849999999999998%" headers="mcps1.2.4.1.1 "><p id="p174705519404"><a name="p174705519404"></a><a name="p174705519404"></a>kubernetes.AOM.log.stdout</p>
</td>
<td class="cellrowborder" valign="top" width="43.65%" headers="mcps1.2.4.1.2 "><p id="p88891553155817"><a name="p88891553155817"></a><a name="p88891553155817"></a>容器标准输出采集参数，不配置默认将全部容器的标准输出上报至AOM，可配置采集指定容器或全部不采集。</p>
<p id="p1941418503333"><a name="p1941418503333"></a><a name="p1941418503333"></a>示例：</p>
<a name="ul12635112733519"></a><a name="ul12635112733519"></a><ul id="ul12635112733519"><li>全部不采集<p id="p17572143063518"><a name="p17572143063518"></a><a name="p17572143063518"></a>kubernetes.AOM.log.stdout: '[]'</p>
</li><li>采集container-1和container-2容器。<p id="p10842193220352"><a name="p10842193220352"></a><a name="p10842193220352"></a>kubernetes.AOM.log.stdout: '["container-1","container-2"]'</p>
</li></ul>
</td>
<td class="cellrowborder" valign="top" width="26.5%" headers="mcps1.2.4.1.3 "><p id="p1447085164020"><a name="p1447085164020"></a><a name="p1447085164020"></a>-</p>
</td>
</tr>
<tr id="row82408107499"><td class="cellrowborder" valign="top" width="29.849999999999998%" headers="mcps1.2.4.1.1 "><p id="p1324081064915"><a name="p1324081064915"></a><a name="p1324081064915"></a>metrics.alpha.kubernetes.io/custom-endpoints</p>
</td>
<td class="cellrowborder" valign="top" width="43.65%" headers="mcps1.2.4.1.2 "><p id="p11240101012499"><a name="p11240101012499"></a><a name="p11240101012499"></a>AOM监控指标上报参数，可将指定指标上报是AOM服务。</p>
<p id="p1360142835113"><a name="p1360142835113"></a><a name="p1360142835113"></a>具体使用请参见<a href="自定义监控-136.md">自定义监控</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="26.5%" headers="mcps1.2.4.1.3 "><p id="p8240181024910"><a name="p8240181024910"></a><a name="p8240181024910"></a>-</p>
</td>
</tr>
<tr id="row14932101084916"><td class="cellrowborder" valign="top" width="29.849999999999998%" headers="mcps1.2.4.1.1 "><p id="p159322010144911"><a name="p159322010144911"></a><a name="p159322010144911"></a>prometheus.io/scrape</p>
</td>
<td class="cellrowborder" valign="top" width="43.65%" headers="mcps1.2.4.1.2 "><p id="p129321010134918"><a name="p129321010134918"></a><a name="p129321010134918"></a>Prometheus指标上报参数，值为true表示当前负载开启上报。</p>
<p id="p17921144025110"><a name="p17921144025110"></a><a name="p17921144025110"></a>具体使用请参见<a href="使用Prometheus插件监控-137.md">使用Prometheus插件监控</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="26.5%" headers="mcps1.2.4.1.3 "><p id="p12932141017492"><a name="p12932141017492"></a><a name="p12932141017492"></a>-</p>
</td>
</tr>
<tr id="row715915119490"><td class="cellrowborder" valign="top" width="29.849999999999998%" headers="mcps1.2.4.1.1 "><p id="p1315911110496"><a name="p1315911110496"></a><a name="p1315911110496"></a>prometheus.io/path</p>
</td>
<td class="cellrowborder" valign="top" width="43.65%" headers="mcps1.2.4.1.2 "><p id="p20159131117499"><a name="p20159131117499"></a><a name="p20159131117499"></a>Prometheus采集的url路径。</p>
<p id="p375212817529"><a name="p375212817529"></a><a name="p375212817529"></a>具体使用请参见<a href="使用Prometheus插件监控-137.md">使用Prometheus插件监控</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="26.5%" headers="mcps1.2.4.1.3 "><p id="p10159111114916"><a name="p10159111114916"></a><a name="p10159111114916"></a>/metrics</p>
</td>
</tr>
<tr id="row3369171119493"><td class="cellrowborder" valign="top" width="29.849999999999998%" headers="mcps1.2.4.1.1 "><p id="p15369131111499"><a name="p15369131111499"></a><a name="p15369131111499"></a>prometheus.io/port</p>
</td>
<td class="cellrowborder" valign="top" width="43.65%" headers="mcps1.2.4.1.2 "><p id="p17369191111490"><a name="p17369191111490"></a><a name="p17369191111490"></a>Prometheus采集的endpoint端口号。</p>
<p id="p11268239529"><a name="p11268239529"></a><a name="p11268239529"></a>具体使用请参见<a href="使用Prometheus插件监控-137.md">使用Prometheus插件监控</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="26.5%" headers="mcps1.2.4.1.3 "><p id="p15369711204910"><a name="p15369711204910"></a><a name="p15369711204910"></a>-</p>
</td>
</tr>
<tr id="row101571749134910"><td class="cellrowborder" valign="top" width="29.849999999999998%" headers="mcps1.2.4.1.1 "><p id="p3157154914493"><a name="p3157154914493"></a><a name="p3157154914493"></a>prometheus.io/scheme</p>
</td>
<td class="cellrowborder" valign="top" width="43.65%" headers="mcps1.2.4.1.2 "><p id="p13158124964917"><a name="p13158124964917"></a><a name="p13158124964917"></a>Prometheus采集协议，值可以填写http或https</p>
<p id="p155412241529"><a name="p155412241529"></a><a name="p155412241529"></a>具体使用请参见<a href="使用Prometheus插件监控-137.md">使用Prometheus插件监控</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="26.5%" headers="mcps1.2.4.1.3 "><p id="p615854919493"><a name="p615854919493"></a><a name="p615854919493"></a>-</p>
</td>
</tr>
<tr id="row2708819172011"><td class="cellrowborder" valign="top" width="29.849999999999998%" headers="mcps1.2.4.1.1 "><p id="p47091619152015"><a name="p47091619152015"></a><a name="p47091619152015"></a>kubernetes.io/ingress-bandwidth</p>
</td>
<td class="cellrowborder" valign="top" width="43.65%" headers="mcps1.2.4.1.2 "><p id="p5709191942014"><a name="p5709191942014"></a><a name="p5709191942014"></a>Pod的入口带宽</p>
<p id="p1319719176212"><a name="p1319719176212"></a><a name="p1319719176212"></a>具体使用请参见<a href="Pod-Annotation说明.md">Pod Annotation说明</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="26.5%" headers="mcps1.2.4.1.3 "><p id="p197099199209"><a name="p197099199209"></a><a name="p197099199209"></a>-</p>
</td>
</tr>
<tr id="row15470924172013"><td class="cellrowborder" valign="top" width="29.849999999999998%" headers="mcps1.2.4.1.1 "><p id="p1047022452012"><a name="p1047022452012"></a><a name="p1047022452012"></a>kubernetes.io/egress-bandwidth</p>
</td>
<td class="cellrowborder" valign="top" width="43.65%" headers="mcps1.2.4.1.2 "><p id="p1470162416204"><a name="p1470162416204"></a><a name="p1470162416204"></a>Pod的出口带宽</p>
<p id="p1250963211215"><a name="p1250963211215"></a><a name="p1250963211215"></a>具体使用请参见<a href="Pod-Annotation说明.md">Pod Annotation说明</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="26.5%" headers="mcps1.2.4.1.3 "><p id="p347016245203"><a name="p347016245203"></a><a name="p347016245203"></a>-</p>
</td>
</tr>
</tbody>
</table>

