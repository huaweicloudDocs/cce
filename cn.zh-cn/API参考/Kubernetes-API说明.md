# Kubernetes API说明<a name="kubernetesapi"></a>

## Kubernetes API 说明<a name="section3701731155417"></a>

Kubernetes集群提供Kubernetes原生API，相关概念请参见[Kubernetes API 概念](https://kubernetes.io/zh-cn/docs/reference/using-api/api-concepts/)。

Kubernetes API定义您可以参见Kubernetes网站，具体链接如下：

-   1.19：[https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.19/](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.19/)
-   1.21：[https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.21/](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.21/)
-   1.23：[https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.23/](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.23/)

CCE在开源Kubernetes API基础上，通过添加annotation的方式做了功能增强与适配，主要涉及Pod、Service、Ingress、PV、PVC等对象，具体如下。

-   Pod annotation：请参见[Pod标签与注解](https://support.huaweicloud.com/usermanual-cce/cce_10_0386.html)。
-   Service：请参见[Service Annotations说明](https://support.huaweicloud.com/usermanual-cce/cce_10_0385.html)。
-   Ingress：请参见[通过Kubectl命令行添加ELB Ingress](https://support.huaweicloud.com/usermanual-cce/cce_10_0252.html#section3)。
-   PV：请参见[存储卷PV](https://support.huaweicloud.com/usermanual-cce/cce_10_0379.html)。
-   PVC：请参见[存储卷声明PVC](https://support.huaweicloud.com/usermanual-cce/cce_10_0378.html)。

## 通过API网关调用Kubernetes API<a name="section41207155509"></a>

Kubernetes原生API，可以通过API网关调用，其URL格式为：**https://\{clusterid\}.Endpoint/uri**。其中**\{clusterid\}**为集群ID，**uri**为资源路径，也即API访问的路径。

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
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0092901339_p4957181017553"><a name="zh-cn_topic_0092901339_p4957181017553"></a><a name="zh-cn_topic_0092901339_p4957181017553"></a>Web服务入口点的URL，可以从<a href="终端节点（Endpoint）.md">终端节点（Endpoint）</a>中获取。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092901339_row0957191065512"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0092901339_p179581410115511"><a name="zh-cn_topic_0092901339_p179581410115511"></a><a name="zh-cn_topic_0092901339_p179581410115511"></a>uri</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0092901339_p149587102555"><a name="zh-cn_topic_0092901339_p149587102555"></a><a name="zh-cn_topic_0092901339_p149587102555"></a>资源路径，也即API访问路径。从具体接口的URI模块获取。</p>
</td>
</tr>
</tbody>
</table>

## 通过API Server调用Kubernetes API<a name="section114491615579"></a>

通过Kubernetes集群的API Server可以调用Kubernetes原生API。

1.  调用[获取集群证书](获取集群证书.md)API，获取集群证书。

    共如下三个证书。

    -   ca.crt
    -   client.crt
    -   client.key

2.  进入集群，在集群详情页获取API Server地址（内网地址或公网地址）。

    有了证书和API Server地址，您就可以调用Kubernetes原生API。

    例如使用curl命令调用接口查看Pod信息，只需将证书携带上，如下所示。

    **curl --cert ./client.crt --key ./client.key  https://192.168.0.198:5443/api/v1/namespaces/default/pods/**


