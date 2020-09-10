# Kubernetes API URL说明<a name="cce_02_0362"></a>

Kubernetes原生接口的URL格式为：**https://\{clusterid\}.Endpoint/uri**。其中\{clusterid\}为集群ID，uri为资源路径，也即API访问的路径。

**表 1**  URL中的参数说明

<a name="table7272144324912"></a>
<table><thead align="left"><tr id="zh-cn_topic_0092901339_row12957510145518"><th class="cellrowborder" valign="top" width="24.529999999999998%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0092901339_p195751012559"><a name="zh-cn_topic_0092901339_p195751012559"></a><a name="zh-cn_topic_0092901339_p195751012559"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="75.47%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0092901339_p5957810135511"><a name="zh-cn_topic_0092901339_p5957810135511"></a><a name="zh-cn_topic_0092901339_p5957810135511"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0092901339_row12957210115515"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0092901339_p20957181010553"><a name="zh-cn_topic_0092901339_p20957181010553"></a><a name="zh-cn_topic_0092901339_p20957181010553"></a>{clusterid}</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0092901339_p19571410195516"><a name="zh-cn_topic_0092901339_p19571410195516"></a><a name="zh-cn_topic_0092901339_p19571410195516"></a>集群ID，创建集群后，调用<a href="获取指定项目下的集群.md">获取指定项目下的集群</a>接口获取。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092901339_row195716107550"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0092901339_p119571610115515"><a name="zh-cn_topic_0092901339_p119571610115515"></a><a name="zh-cn_topic_0092901339_p119571610115515"></a>Endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0092901339_p4957181017553"><a name="zh-cn_topic_0092901339_p4957181017553"></a><a name="zh-cn_topic_0092901339_p4957181017553"></a>Web服务入口点的URL，可以从<a href="https://developer.huaweicloud.com/endpoint?cce" target="_blank" rel="noopener noreferrer">地区和终端节点</a>中获取。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092901339_row0957191065512"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0092901339_p179581410115511"><a name="zh-cn_topic_0092901339_p179581410115511"></a><a name="zh-cn_topic_0092901339_p179581410115511"></a>uri</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0092901339_p149587102555"><a name="zh-cn_topic_0092901339_p149587102555"></a><a name="zh-cn_topic_0092901339_p149587102555"></a>资源路径，也即API访问路径。从具体接口的URI模块获取，例如“<strong id="zh-cn_topic_0092901339_b19958151018554"><a name="zh-cn_topic_0092901339_b19958151018554"></a><a name="zh-cn_topic_0092901339_b19958151018554"></a>获取用户Token</strong>”API的resource-path为“v3/auth/tokens”。</p>
</td>
</tr>
</tbody>
</table>

## 如何调用API<a name="section28643518411"></a>

-   [构造请求](构造请求.md)
-   [认证鉴权](认证鉴权.md)
-   [返回结果](返回结果.md)

