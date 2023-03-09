# CCE发布Kubernetes 1.25版本说明<a name="cce_10_0467"></a>

云容器引擎（CCE）严格遵循社区一致性认证。本文介绍CCE发布Kubernetes 1.25版本所做的变更说明。

## 版本升级说明<a name="zh-cn_topic_0000001430891141_section1323276466"></a>

CCE针对Kubernetes 1.25版本提供了全链路的组件优化和升级。

**表 1**  核心组件及说明

<a name="zh-cn_topic_0000001430891141_table155741450207"></a>
<table><thead align="left"><tr id="zh-cn_topic_0000001430891141_row155743501202"><th class="cellrowborder" valign="top" width="15.518448155184483%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0000001430891141_p53290168478"><a name="zh-cn_topic_0000001430891141_p53290168478"></a><a name="zh-cn_topic_0000001430891141_p53290168478"></a>集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.127687231276873%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0000001430891141_p175741050209"><a name="zh-cn_topic_0000001430891141_p175741050209"></a><a name="zh-cn_topic_0000001430891141_p175741050209"></a>核心组件</p>
</th>
<th class="cellrowborder" valign="top" width="28.537146285371463%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0000001430891141_p157416501403"><a name="zh-cn_topic_0000001430891141_p157416501403"></a><a name="zh-cn_topic_0000001430891141_p157416501403"></a>版本号</p>
</th>
<th class="cellrowborder" valign="top" width="32.816718328167184%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0000001430891141_p657425016011"><a name="zh-cn_topic_0000001430891141_p657425016011"></a><a name="zh-cn_topic_0000001430891141_p657425016011"></a>升级注意事项</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0000001430891141_row357411506015"><td class="cellrowborder" rowspan="8" valign="top" width="15.518448155184483%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p15329181615474"><a name="zh-cn_topic_0000001430891141_p15329181615474"></a><a name="zh-cn_topic_0000001430891141_p15329181615474"></a>CCE集群</p>
</td>
<td class="cellrowborder" valign="top" width="23.127687231276873%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p15741450109"><a name="zh-cn_topic_0000001430891141_p15741450109"></a><a name="zh-cn_topic_0000001430891141_p15741450109"></a>Kubernetes</p>
</td>
<td class="cellrowborder" valign="top" width="28.537146285371463%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001430891141_p1857416501305"><a name="zh-cn_topic_0000001430891141_p1857416501305"></a><a name="zh-cn_topic_0000001430891141_p1857416501305"></a>1.25</p>
</td>
<td class="cellrowborder" valign="top" width="32.816718328167184%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0000001430891141_p4574250009"><a name="zh-cn_topic_0000001430891141_p4574250009"></a><a name="zh-cn_topic_0000001430891141_p4574250009"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row18141164895219"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p18141848105216"><a name="zh-cn_topic_0000001430891141_p18141848105216"></a><a name="zh-cn_topic_0000001430891141_p18141848105216"></a>Docker</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p9141184815214"><a name="zh-cn_topic_0000001430891141_p9141184815214"></a><a name="zh-cn_topic_0000001430891141_p9141184815214"></a>EulerOS/CentOS：18.9.0</p>
<p id="zh-cn_topic_0000001430891141_p9790113195019"><a name="zh-cn_topic_0000001430891141_p9790113195019"></a><a name="zh-cn_topic_0000001430891141_p9790113195019"></a>Ubuntu：18.09.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001430891141_p19469152035512"><a name="zh-cn_topic_0000001430891141_p19469152035512"></a><a name="zh-cn_topic_0000001430891141_p19469152035512"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row62151598506"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p139911405110"><a name="zh-cn_topic_0000001430891141_p139911405110"></a><a name="zh-cn_topic_0000001430891141_p139911405110"></a>Containerd</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p839919495110"><a name="zh-cn_topic_0000001430891141_p839919495110"></a><a name="zh-cn_topic_0000001430891141_p839919495110"></a>1.4.1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001430891141_p1839914135115"><a name="zh-cn_topic_0000001430891141_p1839914135115"></a><a name="zh-cn_topic_0000001430891141_p1839914135115"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row20122846135210"><td class="cellrowborder" rowspan="5" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p1512213462520"><a name="zh-cn_topic_0000001430891141_p1512213462520"></a><a name="zh-cn_topic_0000001430891141_p1512213462520"></a>操作系统</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p11122134655210"><a name="zh-cn_topic_0000001430891141_p11122134655210"></a><a name="zh-cn_topic_0000001430891141_p11122134655210"></a>CentOS Linux release 7.6</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001430891141_p2122184611526"><a name="zh-cn_topic_0000001430891141_p2122184611526"></a><a name="zh-cn_topic_0000001430891141_p2122184611526"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row234011112134"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p10341111161310"><a name="zh-cn_topic_0000001430891141_p10341111161310"></a><a name="zh-cn_topic_0000001430891141_p10341111161310"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p2034111113134"><a name="zh-cn_topic_0000001430891141_p2034111113134"></a><a name="zh-cn_topic_0000001430891141_p2034111113134"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row1415162785517"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p215152755511"><a name="zh-cn_topic_0000001430891141_p215152755511"></a><a name="zh-cn_topic_0000001430891141_p215152755511"></a>EulerOS release 2.5</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p1036022555516"><a name="zh-cn_topic_0000001430891141_p1036022555516"></a><a name="zh-cn_topic_0000001430891141_p1036022555516"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row1656414245556"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p17565124165517"><a name="zh-cn_topic_0000001430891141_p17565124165517"></a><a name="zh-cn_topic_0000001430891141_p17565124165517"></a>Ubuntu 18.04 server 64bit</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p113601325155511"><a name="zh-cn_topic_0000001430891141_p113601325155511"></a><a name="zh-cn_topic_0000001430891141_p113601325155511"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row1679934764813"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p1580064754819"><a name="zh-cn_topic_0000001430891141_p1580064754819"></a><a name="zh-cn_topic_0000001430891141_p1580064754819"></a>Huawei Cloud EulerOS 2.0</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p7800144744810"><a name="zh-cn_topic_0000001430891141_p7800144744810"></a><a name="zh-cn_topic_0000001430891141_p7800144744810"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row115743505013"><td class="cellrowborder" rowspan="5" valign="top" width="15.518448155184483%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p232914164473"><a name="zh-cn_topic_0000001430891141_p232914164473"></a><a name="zh-cn_topic_0000001430891141_p232914164473"></a>CCE Turbo集群</p>
</td>
<td class="cellrowborder" valign="top" width="23.127687231276873%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p13574105017010"><a name="zh-cn_topic_0000001430891141_p13574105017010"></a><a name="zh-cn_topic_0000001430891141_p13574105017010"></a>Kubernetes</p>
</td>
<td class="cellrowborder" valign="top" width="28.537146285371463%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001430891141_p65748508018"><a name="zh-cn_topic_0000001430891141_p65748508018"></a><a name="zh-cn_topic_0000001430891141_p65748508018"></a>1.25</p>
</td>
<td class="cellrowborder" valign="top" width="32.816718328167184%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0000001430891141_p155744507011"><a name="zh-cn_topic_0000001430891141_p155744507011"></a><a name="zh-cn_topic_0000001430891141_p155744507011"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row11789592554"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p47985985513"><a name="zh-cn_topic_0000001430891141_p47985985513"></a><a name="zh-cn_topic_0000001430891141_p47985985513"></a>Docker</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p15914171311536"><a name="zh-cn_topic_0000001430891141_p15914171311536"></a><a name="zh-cn_topic_0000001430891141_p15914171311536"></a>EulerOS/CentOS：18.9.0</p>
<p id="zh-cn_topic_0000001430891141_p139141013135315"><a name="zh-cn_topic_0000001430891141_p139141013135315"></a><a name="zh-cn_topic_0000001430891141_p139141013135315"></a>Ubuntu：18.09.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001430891141_p191831128185517"><a name="zh-cn_topic_0000001430891141_p191831128185517"></a><a name="zh-cn_topic_0000001430891141_p191831128185517"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row45741250801"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p5101192295316"><a name="zh-cn_topic_0000001430891141_p5101192295316"></a><a name="zh-cn_topic_0000001430891141_p5101192295316"></a>Containerd</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p3100822105319"><a name="zh-cn_topic_0000001430891141_p3100822105319"></a><a name="zh-cn_topic_0000001430891141_p3100822105319"></a>1.4.1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001430891141_p218362812559"><a name="zh-cn_topic_0000001430891141_p218362812559"></a><a name="zh-cn_topic_0000001430891141_p218362812559"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row857455010018"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p1199122212532"><a name="zh-cn_topic_0000001430891141_p1199122212532"></a><a name="zh-cn_topic_0000001430891141_p1199122212532"></a>操作系统（弹性云服务器）</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p1898422195312"><a name="zh-cn_topic_0000001430891141_p1898422195312"></a><a name="zh-cn_topic_0000001430891141_p1898422195312"></a>CentOS Linux release 7.6</p>
<p id="zh-cn_topic_0000001430891141_p125615545549"><a name="zh-cn_topic_0000001430891141_p125615545549"></a><a name="zh-cn_topic_0000001430891141_p125615545549"></a>Ubuntu 18.04 server 64bit</p>
<p id="zh-cn_topic_0000001430891141_p168017277139"><a name="zh-cn_topic_0000001430891141_p168017277139"></a><a name="zh-cn_topic_0000001430891141_p168017277139"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001430891141_p1341042914552"><a name="zh-cn_topic_0000001430891141_p1341042914552"></a><a name="zh-cn_topic_0000001430891141_p1341042914552"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001430891141_row107813265418"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001430891141_p7781729546"><a name="zh-cn_topic_0000001430891141_p7781729546"></a><a name="zh-cn_topic_0000001430891141_p7781729546"></a>操作系统（弹性裸金属服务器）</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001430891141_p35751818245"><a name="zh-cn_topic_0000001430891141_p35751818245"></a><a name="zh-cn_topic_0000001430891141_p35751818245"></a>CentOS Linux release 7.6</p>
<p id="zh-cn_topic_0000001430891141_p14575380249"><a name="zh-cn_topic_0000001430891141_p14575380249"></a><a name="zh-cn_topic_0000001430891141_p14575380249"></a>Ubuntu 18.04 server 64bit</p>
<p id="zh-cn_topic_0000001430891141_p193557201107"><a name="zh-cn_topic_0000001430891141_p193557201107"></a><a name="zh-cn_topic_0000001430891141_p193557201107"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001430891141_p441072920559"><a name="zh-cn_topic_0000001430891141_p441072920559"></a><a name="zh-cn_topic_0000001430891141_p441072920559"></a>无</p>
</td>
</tr>
</tbody>
</table>

## 资源变更与弃用<a name="zh-cn_topic_0000001430891141_zh-cn_topic_0000001072975092_section51381161799"></a>

**CCE 1.25变更说明**

除EulerOS 2.5操作系统外，1.25集群的CCE节点均默认采用containerd运行时。

**社区1.25 ReleaseNotes**

-   PodSecurityPolicy被废弃，并提供Pod Security Admission取代，具体的迁移方法可参见[从PodSecurityPolicy迁移到内置的PodSecurity准入控制器](https://kubernetes.io/zh-cn/docs/tasks/configure-pod-container/migrate-from-psp/)。
-   SeccompDefault提升到Beta状态，如果要开启该特性，需要给kubelet增加启动参数为--seccomp-default=true，这样会默认开启seccomp为RuntimeDefault，提升整个系统的安全。1.25集群将不再支持使用注解“seccomp.security.alpha.kubernetes.io/pod“和“container.seccomp.security.alpha.kubernetes.io/annotation“来使用seccomp，请使用pod或container中“securityContext.seccompProfile“字段替代，详情请参见[为Pod或容器配置安全上下文](https://kubernetes.io/zh-cn/docs/tasks/configure-pod-container/security-context/)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >特性开启后可能应用所需的系统调用会被runtime限制，所以开启后应确保在测试环境调试，不会对应用造成影响。

-   Network Policy中的EndPort已进入稳定状态，该特性于1.21版本合入。主要是在NetworkPolicy新增EndPort，可以指定一个Port范围，避免声明每一个Port。
-   从1.25版本集群开始，Kubernetes不再支持使用SHA1WithRSA、ECDSAWithSHA1算法生成的证书认证，推荐使用SHA256算法生成的证书进行认证。

**社区1.24 ReleaseNotes**

-   Dockershim自1.20版本被标废弃以来，在1.24版本正式从Kubelet代码中移除。如果还想使用Docker作为容器运行时的话，需要切换到cri-dockerd，或者使用其他支持CRI的运行时比如Containerd/CRI-O等。

    从Docker Engine 切换到Containerd的流程请参见[将节点容器引擎从Docker迁移到Containerd](将节点容器引擎从Docker迁移到Containerd.md)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >您需要注意排查是否有agent或者应用强依赖Docker Engine的，比如在代码中使用docker ps，docker run， docker inspect等，需要注意兼容多种runtime，以及切换到标准cri接口。

-   Beta APIs默认关闭，在社区移除一些长期beta API的过程中发现，90%的集群管理员并没有关心beta API默认开始，其实beta 特性是不推荐在生产环境中使用，但是因为默认的打开策略，导致这些API在生产环境中都被默认开启，这样会因为beta特性的bug带来一些风险，以及升级的迁移的风险。所以在1.24版本开始，beta API默认关闭，之前已经默认开启的beta API会保持默认开启。
-   LegacyServiceAccountTokenNoAutoGeneration特性门控进入beta状态，默认为开启状态，开启后将不再为Service Account自动生成Secret Token。如果需要使用永不过期的Token，需要自己新建Secrets并挂载，详情请参见[服务帐号令牌Secret](https://kubernetes.io/zh-cn/docs/concepts/configuration/secret/#service-account-token-secrets)。
-   Service废弃service.alpha.kubernetes.io/tolerate-unready-endpoints, 统一使用Service.spec.publishNotReadyAddresses。
-   Service.Spec.LoadBalancerIP标记deprecated，可能在未来版本中移除，请使用自定义annotation。

## 参考链接<a name="zh-cn_topic_0000001430891141_zh-cn_topic_0000001072975092_zh-cn_topic_0261805759_zh-cn_topic_0261793154_section1272182810583"></a>

关于Kubernetes 1.25与其他版本的性能对比和功能演进的更多信息，请参考：

-   [Kubernetes v1.25 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.25.md)
-   [Kubernetes v1.24 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.24.md)

