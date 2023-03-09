# CCE发布Kubernetes 1.21版本说明<a name="cce_10_0469"></a>

云容器引擎（CCE）严格遵循社区一致性认证。本文介绍CCE发布Kubernetes 1.21版本所做的变更说明。

## 版本升级说明<a name="zh-cn_topic_0000001177935088_section1323276466"></a>

CCE针对Kubernetes 1.21版本提供了全链路的组件优化和升级。

**表 1**  核心组件及说明

<a name="zh-cn_topic_0000001177935088_table155741450207"></a>
<table><thead align="left"><tr id="zh-cn_topic_0000001177935088_row155743501202"><th class="cellrowborder" valign="top" width="15.518448155184483%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0000001177935088_p53290168478"><a name="zh-cn_topic_0000001177935088_p53290168478"></a><a name="zh-cn_topic_0000001177935088_p53290168478"></a>集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.147685231476853%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0000001177935088_p175741050209"><a name="zh-cn_topic_0000001177935088_p175741050209"></a><a name="zh-cn_topic_0000001177935088_p175741050209"></a>核心组件</p>
</th>
<th class="cellrowborder" valign="top" width="28.517148285171483%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0000001177935088_p157416501403"><a name="zh-cn_topic_0000001177935088_p157416501403"></a><a name="zh-cn_topic_0000001177935088_p157416501403"></a>版本号</p>
</th>
<th class="cellrowborder" valign="top" width="32.816718328167184%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0000001177935088_p657425016011"><a name="zh-cn_topic_0000001177935088_p657425016011"></a><a name="zh-cn_topic_0000001177935088_p657425016011"></a>升级注意事项</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0000001177935088_row357411506015"><td class="cellrowborder" rowspan="6" valign="top" width="15.518448155184483%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p15329181615474"><a name="zh-cn_topic_0000001177935088_p15329181615474"></a><a name="zh-cn_topic_0000001177935088_p15329181615474"></a>CCE集群</p>
</td>
<td class="cellrowborder" valign="top" width="23.147685231476853%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p15741450109"><a name="zh-cn_topic_0000001177935088_p15741450109"></a><a name="zh-cn_topic_0000001177935088_p15741450109"></a>Kubernetes</p>
</td>
<td class="cellrowborder" valign="top" width="28.517148285171483%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001177935088_p1857416501305"><a name="zh-cn_topic_0000001177935088_p1857416501305"></a><a name="zh-cn_topic_0000001177935088_p1857416501305"></a>1.21</p>
</td>
<td class="cellrowborder" valign="top" width="32.816718328167184%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0000001177935088_p4574250009"><a name="zh-cn_topic_0000001177935088_p4574250009"></a><a name="zh-cn_topic_0000001177935088_p4574250009"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row18141164895219"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p18141848105216"><a name="zh-cn_topic_0000001177935088_p18141848105216"></a><a name="zh-cn_topic_0000001177935088_p18141848105216"></a>Docker</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p9141184815214"><a name="zh-cn_topic_0000001177935088_p9141184815214"></a><a name="zh-cn_topic_0000001177935088_p9141184815214"></a>EulerOS/CentOS：18.9.0</p>
<p id="zh-cn_topic_0000001177935088_p9790113195019"><a name="zh-cn_topic_0000001177935088_p9790113195019"></a><a name="zh-cn_topic_0000001177935088_p9790113195019"></a>Ubuntu：18.09.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001177935088_p19469152035512"><a name="zh-cn_topic_0000001177935088_p19469152035512"></a><a name="zh-cn_topic_0000001177935088_p19469152035512"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row20122846135210"><td class="cellrowborder" rowspan="4" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p1512213462520"><a name="zh-cn_topic_0000001177935088_p1512213462520"></a><a name="zh-cn_topic_0000001177935088_p1512213462520"></a>操作系统</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p11122134655210"><a name="zh-cn_topic_0000001177935088_p11122134655210"></a><a name="zh-cn_topic_0000001177935088_p11122134655210"></a>CentOS Linux release 7.6</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001177935088_p2122184611526"><a name="zh-cn_topic_0000001177935088_p2122184611526"></a><a name="zh-cn_topic_0000001177935088_p2122184611526"></a>1.21版本开始CCE集群 Centos7.6节点 docker存储模式使用overlayfs</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row234011112134"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p10341111161310"><a name="zh-cn_topic_0000001177935088_p10341111161310"></a><a name="zh-cn_topic_0000001177935088_p10341111161310"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p2034111113134"><a name="zh-cn_topic_0000001177935088_p2034111113134"></a><a name="zh-cn_topic_0000001177935088_p2034111113134"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row1415162785517"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p215152755511"><a name="zh-cn_topic_0000001177935088_p215152755511"></a><a name="zh-cn_topic_0000001177935088_p215152755511"></a>EulerOS release 2.5</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p1036022555516"><a name="zh-cn_topic_0000001177935088_p1036022555516"></a><a name="zh-cn_topic_0000001177935088_p1036022555516"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row1656414245556"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p17565124165517"><a name="zh-cn_topic_0000001177935088_p17565124165517"></a><a name="zh-cn_topic_0000001177935088_p17565124165517"></a>Ubuntu 18.04 server 64bit</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p113601325155511"><a name="zh-cn_topic_0000001177935088_p113601325155511"></a><a name="zh-cn_topic_0000001177935088_p113601325155511"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row115743505013"><td class="cellrowborder" rowspan="5" valign="top" width="15.518448155184483%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p232914164473"><a name="zh-cn_topic_0000001177935088_p232914164473"></a><a name="zh-cn_topic_0000001177935088_p232914164473"></a>CCE Turbo集群</p>
</td>
<td class="cellrowborder" valign="top" width="23.147685231476853%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p13574105017010"><a name="zh-cn_topic_0000001177935088_p13574105017010"></a><a name="zh-cn_topic_0000001177935088_p13574105017010"></a>Kubernetes</p>
</td>
<td class="cellrowborder" valign="top" width="28.517148285171483%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001177935088_p65748508018"><a name="zh-cn_topic_0000001177935088_p65748508018"></a><a name="zh-cn_topic_0000001177935088_p65748508018"></a>1.21</p>
</td>
<td class="cellrowborder" valign="top" width="32.816718328167184%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0000001177935088_p155744507011"><a name="zh-cn_topic_0000001177935088_p155744507011"></a><a name="zh-cn_topic_0000001177935088_p155744507011"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row11789592554"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p47985985513"><a name="zh-cn_topic_0000001177935088_p47985985513"></a><a name="zh-cn_topic_0000001177935088_p47985985513"></a>Docker</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p15914171311536"><a name="zh-cn_topic_0000001177935088_p15914171311536"></a><a name="zh-cn_topic_0000001177935088_p15914171311536"></a>EulerOS/CentOS：18.9.0</p>
<p id="zh-cn_topic_0000001177935088_p139141013135315"><a name="zh-cn_topic_0000001177935088_p139141013135315"></a><a name="zh-cn_topic_0000001177935088_p139141013135315"></a>Ubuntu：18.09.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001177935088_p191831128185517"><a name="zh-cn_topic_0000001177935088_p191831128185517"></a><a name="zh-cn_topic_0000001177935088_p191831128185517"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row45741250801"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p5101192295316"><a name="zh-cn_topic_0000001177935088_p5101192295316"></a><a name="zh-cn_topic_0000001177935088_p5101192295316"></a>Containerd</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p3100822105319"><a name="zh-cn_topic_0000001177935088_p3100822105319"></a><a name="zh-cn_topic_0000001177935088_p3100822105319"></a>1.4.1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001177935088_p218362812559"><a name="zh-cn_topic_0000001177935088_p218362812559"></a><a name="zh-cn_topic_0000001177935088_p218362812559"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row857455010018"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p1199122212532"><a name="zh-cn_topic_0000001177935088_p1199122212532"></a><a name="zh-cn_topic_0000001177935088_p1199122212532"></a>操作系统（弹性云服务器）</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p1898422195312"><a name="zh-cn_topic_0000001177935088_p1898422195312"></a><a name="zh-cn_topic_0000001177935088_p1898422195312"></a>CentOS Linux release 7.6</p>
<p id="zh-cn_topic_0000001177935088_p125615545549"><a name="zh-cn_topic_0000001177935088_p125615545549"></a><a name="zh-cn_topic_0000001177935088_p125615545549"></a>Ubuntu 18.04 server 64bit</p>
<p id="zh-cn_topic_0000001177935088_p1964342312134"><a name="zh-cn_topic_0000001177935088_p1964342312134"></a><a name="zh-cn_topic_0000001177935088_p1964342312134"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001177935088_p1341042914552"><a name="zh-cn_topic_0000001177935088_p1341042914552"></a><a name="zh-cn_topic_0000001177935088_p1341042914552"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001177935088_row107813265418"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001177935088_p7781729546"><a name="zh-cn_topic_0000001177935088_p7781729546"></a><a name="zh-cn_topic_0000001177935088_p7781729546"></a>操作系统（弹性裸金属服务器）</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001177935088_p129702413242"><a name="zh-cn_topic_0000001177935088_p129702413242"></a><a name="zh-cn_topic_0000001177935088_p129702413242"></a>CentOS Linux release 7.6</p>
<p id="zh-cn_topic_0000001177935088_p1997020482418"><a name="zh-cn_topic_0000001177935088_p1997020482418"></a><a name="zh-cn_topic_0000001177935088_p1997020482418"></a>Ubuntu 18.04 server 64bit</p>
<p id="zh-cn_topic_0000001177935088_p193557201107"><a name="zh-cn_topic_0000001177935088_p193557201107"></a><a name="zh-cn_topic_0000001177935088_p193557201107"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001177935088_p441072920559"><a name="zh-cn_topic_0000001177935088_p441072920559"></a><a name="zh-cn_topic_0000001177935088_p441072920559"></a>无</p>
</td>
</tr>
</tbody>
</table>

## 资源变更与弃用<a name="zh-cn_topic_0000001177935088_zh-cn_topic_0000001072975092_section51381161799"></a>

**社区1.21 ReleaseNotes**

-   CronJob现在已毕业到稳定状态，版本号变为batch/v1。
-   不可变的Secret和ConfigMap现在已升级到稳定状态。向这些对象添加了一个新的不可变字段，以拒绝更改。此拒绝可保护集群免受可能无意中中断应用程序的更新。因为这些资源是不可变的，kubelet不会监视或轮询更改。这减少了kube-apiserver的负载，提高了可扩展性和性能。更多信息，请参见[Immutable ConfigMaps](https://kubernetes.io/docs/concepts/configuration/configmap/#configmap-immutable)。
-   优雅节点关闭现在已升级到测试状态。通过此更新，kubelet可以感知节点关闭，并可以优雅地终止该节点的Pod。在此更新之前，当节点关闭时，其Pod没有遵循预期的终止生命周期，这导致了工作负载问题。现在kubelet可以通过systemd检测即将关闭的系统，并通知正在运行的Pod，使它们优雅地终止。
-   具有多个容器的Pod现在可以使用kubectl.kubernetes.io/默认容器注释为kubectl命令预选容器。
-   PodSecurityPolicy废弃，详情请参见[https://kubernetes.io/blog/2021/04/06/podsecuritypolicy-deprecation-past-present-and-future/](https://kubernetes.io/blog/2021/04/06/podsecuritypolicy-deprecation-past-present-and-future/)。
-   [BoundServiceAccountTokenVolume](https://kubernetes.io/zh-cn/docs/reference/access-authn-authz/service-accounts-admin/#bound-service-account-token-volume)特性进入Beta，该特性能够提升服务帐号（ServiceAccount）Token的安全性，改变了Pod挂载Token的方式，Kubernetes 1.21及以上版本的集群中会默认开启。

**社区1.20 ReleaseNotes**

-   API优先级和公平性已达到测试状态，默认启用。这允许kube-apiserver按优先级对传入请求进行分类。更多信息，请参见[API Priority and Fairness](https://kubernetes.io/docs/concepts/cluster-administration/flow-control/)。
-   修复 exec probe timeouts不生效的BUG，在此修复之前，exec 探测器不考虑 timeoutSeconds 字段。相反，探测将无限期运行，甚至超过其配置的截止日期，直到返回结果。 通过此更改，如果未指定值，将使用默认值，默认值为1秒。如果探测时间超过一秒，可能会导致应用健康检查失败。请再升级时确定使用该特性的应用更新timeoutSeconds字段。新引入的 ExecProbeTimeout 特性门控所提供的修复使集群操作员能够恢复到以前的行为，但这种行为将在后续版本中锁定并删除。
-   RuntimeClass已达到稳定状态。RuntimeClass资源提供了一种机制，用于支持集群中的多个运行时，并将有关该容器运行时的信息公开到控制平面。
-   kubectl调试已达到测试状态。kubectl调试直接从kubectl提供对常见调试工作流的支持。
-   Dockershim在1.20被标记为废弃，目前您可以继续在集群中使用Docker。该变动与集群所使用的容器镜像（Image）无关。您依然可以使用Docker构建您的镜像。更多信息，请参见[Dockershim Deprecation FAQ](https://kubernetes.io/blog/2020/12/02/dockershim-faq/)。

## 参考链接<a name="zh-cn_topic_0000001177935088_zh-cn_topic_0000001072975092_zh-cn_topic_0261805759_zh-cn_topic_0261793154_section1272182810583"></a>

关于Kubernetes 1.21与其他版本的性能对比和功能演进的更多信息，请参考：

-   [Kubernetes v1.21 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.21.md)
-   [Kubernetes v1.20 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.20.md)

