# CCE发布Kubernetes 1.23版本说明<a name="cce_10_0468"></a>

云容器引擎（CCE）严格遵循社区一致性认证。本文介绍CCE发布Kubernetes 1.23版本所做的变更说明。

## 版本升级说明<a name="zh-cn_topic_0000001212381758_section1323276466"></a>

CCE针对Kubernetes 1.23版本提供了全链路的组件优化和升级。

**表 1**  核心组件及说明

<a name="zh-cn_topic_0000001212381758_table155741450207"></a>
<table><thead align="left"><tr id="zh-cn_topic_0000001212381758_row155743501202"><th class="cellrowborder" valign="top" width="15.518448155184483%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0000001212381758_p53290168478"><a name="zh-cn_topic_0000001212381758_p53290168478"></a><a name="zh-cn_topic_0000001212381758_p53290168478"></a>集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.127687231276873%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0000001212381758_p175741050209"><a name="zh-cn_topic_0000001212381758_p175741050209"></a><a name="zh-cn_topic_0000001212381758_p175741050209"></a>核心组件</p>
</th>
<th class="cellrowborder" valign="top" width="28.537146285371463%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0000001212381758_p157416501403"><a name="zh-cn_topic_0000001212381758_p157416501403"></a><a name="zh-cn_topic_0000001212381758_p157416501403"></a>版本号</p>
</th>
<th class="cellrowborder" valign="top" width="32.816718328167184%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0000001212381758_p657425016011"><a name="zh-cn_topic_0000001212381758_p657425016011"></a><a name="zh-cn_topic_0000001212381758_p657425016011"></a>升级注意事项</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0000001212381758_row357411506015"><td class="cellrowborder" rowspan="7" valign="top" width="15.518448155184483%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p15329181615474"><a name="zh-cn_topic_0000001212381758_p15329181615474"></a><a name="zh-cn_topic_0000001212381758_p15329181615474"></a>CCE集群</p>
</td>
<td class="cellrowborder" valign="top" width="23.127687231276873%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p15741450109"><a name="zh-cn_topic_0000001212381758_p15741450109"></a><a name="zh-cn_topic_0000001212381758_p15741450109"></a>Kubernetes</p>
</td>
<td class="cellrowborder" valign="top" width="28.537146285371463%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001212381758_p1857416501305"><a name="zh-cn_topic_0000001212381758_p1857416501305"></a><a name="zh-cn_topic_0000001212381758_p1857416501305"></a>1.23</p>
</td>
<td class="cellrowborder" valign="top" width="32.816718328167184%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0000001212381758_p4574250009"><a name="zh-cn_topic_0000001212381758_p4574250009"></a><a name="zh-cn_topic_0000001212381758_p4574250009"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row18141164895219"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p18141848105216"><a name="zh-cn_topic_0000001212381758_p18141848105216"></a><a name="zh-cn_topic_0000001212381758_p18141848105216"></a>Docker</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p9141184815214"><a name="zh-cn_topic_0000001212381758_p9141184815214"></a><a name="zh-cn_topic_0000001212381758_p9141184815214"></a>EulerOS/CentOS：18.9.0</p>
<p id="zh-cn_topic_0000001212381758_p9790113195019"><a name="zh-cn_topic_0000001212381758_p9790113195019"></a><a name="zh-cn_topic_0000001212381758_p9790113195019"></a>Ubuntu：18.09.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001212381758_p19469152035512"><a name="zh-cn_topic_0000001212381758_p19469152035512"></a><a name="zh-cn_topic_0000001212381758_p19469152035512"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row62151598506"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p139911405110"><a name="zh-cn_topic_0000001212381758_p139911405110"></a><a name="zh-cn_topic_0000001212381758_p139911405110"></a>Containerd</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p839919495110"><a name="zh-cn_topic_0000001212381758_p839919495110"></a><a name="zh-cn_topic_0000001212381758_p839919495110"></a>1.4.1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001212381758_p1839914135115"><a name="zh-cn_topic_0000001212381758_p1839914135115"></a><a name="zh-cn_topic_0000001212381758_p1839914135115"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row20122846135210"><td class="cellrowborder" rowspan="4" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p1512213462520"><a name="zh-cn_topic_0000001212381758_p1512213462520"></a><a name="zh-cn_topic_0000001212381758_p1512213462520"></a>操作系统</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p11122134655210"><a name="zh-cn_topic_0000001212381758_p11122134655210"></a><a name="zh-cn_topic_0000001212381758_p11122134655210"></a>CentOS Linux release 7.6</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001212381758_p2122184611526"><a name="zh-cn_topic_0000001212381758_p2122184611526"></a><a name="zh-cn_topic_0000001212381758_p2122184611526"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row234011112134"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p10341111161310"><a name="zh-cn_topic_0000001212381758_p10341111161310"></a><a name="zh-cn_topic_0000001212381758_p10341111161310"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p2034111113134"><a name="zh-cn_topic_0000001212381758_p2034111113134"></a><a name="zh-cn_topic_0000001212381758_p2034111113134"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row1415162785517"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p215152755511"><a name="zh-cn_topic_0000001212381758_p215152755511"></a><a name="zh-cn_topic_0000001212381758_p215152755511"></a>EulerOS release 2.5</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p1036022555516"><a name="zh-cn_topic_0000001212381758_p1036022555516"></a><a name="zh-cn_topic_0000001212381758_p1036022555516"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row1656414245556"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p17565124165517"><a name="zh-cn_topic_0000001212381758_p17565124165517"></a><a name="zh-cn_topic_0000001212381758_p17565124165517"></a>Ubuntu 18.04 server 64bit</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p113601325155511"><a name="zh-cn_topic_0000001212381758_p113601325155511"></a><a name="zh-cn_topic_0000001212381758_p113601325155511"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row115743505013"><td class="cellrowborder" rowspan="5" valign="top" width="15.518448155184483%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p232914164473"><a name="zh-cn_topic_0000001212381758_p232914164473"></a><a name="zh-cn_topic_0000001212381758_p232914164473"></a>CCE Turbo集群</p>
</td>
<td class="cellrowborder" valign="top" width="23.127687231276873%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p13574105017010"><a name="zh-cn_topic_0000001212381758_p13574105017010"></a><a name="zh-cn_topic_0000001212381758_p13574105017010"></a>Kubernetes</p>
</td>
<td class="cellrowborder" valign="top" width="28.537146285371463%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001212381758_p65748508018"><a name="zh-cn_topic_0000001212381758_p65748508018"></a><a name="zh-cn_topic_0000001212381758_p65748508018"></a>1.23</p>
</td>
<td class="cellrowborder" valign="top" width="32.816718328167184%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0000001212381758_p155744507011"><a name="zh-cn_topic_0000001212381758_p155744507011"></a><a name="zh-cn_topic_0000001212381758_p155744507011"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row11789592554"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p47985985513"><a name="zh-cn_topic_0000001212381758_p47985985513"></a><a name="zh-cn_topic_0000001212381758_p47985985513"></a>Docker</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p15914171311536"><a name="zh-cn_topic_0000001212381758_p15914171311536"></a><a name="zh-cn_topic_0000001212381758_p15914171311536"></a>EulerOS/CentOS：18.9.0</p>
<p id="zh-cn_topic_0000001212381758_p139141013135315"><a name="zh-cn_topic_0000001212381758_p139141013135315"></a><a name="zh-cn_topic_0000001212381758_p139141013135315"></a>Ubuntu：18.09.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001212381758_p191831128185517"><a name="zh-cn_topic_0000001212381758_p191831128185517"></a><a name="zh-cn_topic_0000001212381758_p191831128185517"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row45741250801"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p5101192295316"><a name="zh-cn_topic_0000001212381758_p5101192295316"></a><a name="zh-cn_topic_0000001212381758_p5101192295316"></a>Containerd</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p3100822105319"><a name="zh-cn_topic_0000001212381758_p3100822105319"></a><a name="zh-cn_topic_0000001212381758_p3100822105319"></a>1.4.1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001212381758_p218362812559"><a name="zh-cn_topic_0000001212381758_p218362812559"></a><a name="zh-cn_topic_0000001212381758_p218362812559"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row857455010018"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p1199122212532"><a name="zh-cn_topic_0000001212381758_p1199122212532"></a><a name="zh-cn_topic_0000001212381758_p1199122212532"></a>操作系统（弹性云服务器）</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p1898422195312"><a name="zh-cn_topic_0000001212381758_p1898422195312"></a><a name="zh-cn_topic_0000001212381758_p1898422195312"></a>CentOS Linux release 7.6</p>
<p id="zh-cn_topic_0000001212381758_p125615545549"><a name="zh-cn_topic_0000001212381758_p125615545549"></a><a name="zh-cn_topic_0000001212381758_p125615545549"></a>Ubuntu 18.04 server 64bit</p>
<p id="zh-cn_topic_0000001212381758_p168017277139"><a name="zh-cn_topic_0000001212381758_p168017277139"></a><a name="zh-cn_topic_0000001212381758_p168017277139"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001212381758_p1341042914552"><a name="zh-cn_topic_0000001212381758_p1341042914552"></a><a name="zh-cn_topic_0000001212381758_p1341042914552"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001212381758_row107813265418"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001212381758_p7781729546"><a name="zh-cn_topic_0000001212381758_p7781729546"></a><a name="zh-cn_topic_0000001212381758_p7781729546"></a>操作系统（弹性裸金属服务器）</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001212381758_p35751818245"><a name="zh-cn_topic_0000001212381758_p35751818245"></a><a name="zh-cn_topic_0000001212381758_p35751818245"></a>CentOS Linux release 7.6</p>
<p id="zh-cn_topic_0000001212381758_p14575380249"><a name="zh-cn_topic_0000001212381758_p14575380249"></a><a name="zh-cn_topic_0000001212381758_p14575380249"></a>Ubuntu 18.04 server 64bit</p>
<p id="zh-cn_topic_0000001212381758_p193557201107"><a name="zh-cn_topic_0000001212381758_p193557201107"></a><a name="zh-cn_topic_0000001212381758_p193557201107"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001212381758_p441072920559"><a name="zh-cn_topic_0000001212381758_p441072920559"></a><a name="zh-cn_topic_0000001212381758_p441072920559"></a>无</p>
</td>
</tr>
</tbody>
</table>

## 资源变更与弃用<a name="zh-cn_topic_0000001212381758_zh-cn_topic_0000001072975092_section51381161799"></a>

**CCE 1.23变更说明**

-   不再支持web-terminal插件，使用cloudshell或直接kubectl对接代替。

**社区1.23 ReleaseNotes**

-   FlexVolume废弃，建议使用CSI。
-   HorizontalPodAutoscaler v2版本GA，HorizontalPodAutoscaler API v2在1.23版本中逐渐稳定。不建议使用HorizontalPodAutoscaler v2beta2 API，建议使用新的v2版本API。
-   [PodSecurity](https://kubernetes.io/docs/concepts/security/pod-security-admission/)支持beta，PodSecurity替代废弃的PodSecurityPolicy，PodSecurity是一个准入控制器，它根据设置实施级别的特定命名空间标签在命名空间中的Pod上实施Pod安全标准。在1.23中PodSecurity默认启用。

**社区1.22 ReleaseNotes**

-   Ingress资源不再支持networking.k8s.io/v1beta1和extensions/v1beta1 API。如果使用旧版本API管理Ingress，会影响应用对外暴露服务，请尽快使用networking.k8s.io/v1替代。
-   CustomResourceDefinition资源不再支持apiextensions.k8s.io/v1beta1 API。如果使用旧版本API创建自定义资源定义，会导致定义创建失败，进而影响调和（reconcile）该自定资源的控制器，请尽快使用apiextensions.k8s.io/v1替代
-   ClusterRole、ClusterRoleBinding、Role和RoleBinding资源不再支持rbac.authorization.k8s.io/v1beta1 API。如果使用旧版本API管理RBAC资源，会影响应用的权限服务，甚至无法在集群内正常使用，请尽快使用rbac.authorization.k8s.io/v1替代。
-   Kubernetes版本发布周期由一年4个版本变为一年3个版本。
-   StatefulSets 支持minReadySeconds。
-   缩容时默认根据Pod uid排序随机选择删除Pod（LogarithmicScaleDown）。基于该特性，可以增强Pod被缩容的随机性，缓解由于Pod拓扑分布约束带来的问题。更多信息，请参见[KEP-2185](https://github.com/kubernetes/enhancements/tree/master/keps/sig-apps/2185-random-pod-select-on-replicaset-downscale)和[issues 96748](https://github.com/kubernetes/kubernetes/issues/96748?spm=a2c4g.11186623.0.0.1de23edc3yorUN)。
-   [BoundServiceAccountTokenVolume](https://kubernetes.io/zh-cn/docs/reference/access-authn-authz/service-accounts-admin/#bound-service-account-token-volume)特性已稳定，该特性能够提升服务帐号（ServiceAccount）Token的安全性，改变了Pod挂载Token的方式，Kubernetes 1.21及以上版本的集群中会默认开启。

## 参考链接<a name="zh-cn_topic_0000001212381758_zh-cn_topic_0000001072975092_zh-cn_topic_0261805759_zh-cn_topic_0261793154_section1272182810583"></a>

关于Kubernetes 1.23与其他版本的性能对比和功能演进的更多信息，请参考：

-   [Kubernetes v1.23 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.23.md)
-   [Kubernetes v1.22 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.22.md)

