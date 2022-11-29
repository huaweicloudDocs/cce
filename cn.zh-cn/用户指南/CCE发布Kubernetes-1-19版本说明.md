# CCE发布Kubernetes 1.19版本说明<a name="cce_10_0470"></a>

云容器引擎（CCE）严格遵循社区一致性认证。本文介绍CCE发布Kubernetes 1.19版本所做的变更说明。

## 版本升级说明<a name="zh-cn_topic_0000001088754632_section1323276466"></a>

CCE针对Kubernetes 1.19版本提供了全链路的组件优化和升级。

**表 1**  核心组件及说明

<a name="zh-cn_topic_0000001088754632_table155741450207"></a>
<table><thead align="left"><tr id="zh-cn_topic_0000001088754632_row155743501202"><th class="cellrowborder" valign="top" width="15.518448155184483%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0000001088754632_p53290168478"><a name="zh-cn_topic_0000001088754632_p53290168478"></a><a name="zh-cn_topic_0000001088754632_p53290168478"></a>集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.147685231476853%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0000001088754632_p175741050209"><a name="zh-cn_topic_0000001088754632_p175741050209"></a><a name="zh-cn_topic_0000001088754632_p175741050209"></a>核心组件</p>
</th>
<th class="cellrowborder" valign="top" width="28.517148285171483%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0000001088754632_p157416501403"><a name="zh-cn_topic_0000001088754632_p157416501403"></a><a name="zh-cn_topic_0000001088754632_p157416501403"></a>版本号</p>
</th>
<th class="cellrowborder" valign="top" width="32.816718328167184%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0000001088754632_p657425016011"><a name="zh-cn_topic_0000001088754632_p657425016011"></a><a name="zh-cn_topic_0000001088754632_p657425016011"></a>升级注意事项</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0000001088754632_row357411506015"><td class="cellrowborder" rowspan="5" valign="top" width="15.518448155184483%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p15329181615474"><a name="zh-cn_topic_0000001088754632_p15329181615474"></a><a name="zh-cn_topic_0000001088754632_p15329181615474"></a>CCE集群</p>
</td>
<td class="cellrowborder" valign="top" width="23.147685231476853%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p15741450109"><a name="zh-cn_topic_0000001088754632_p15741450109"></a><a name="zh-cn_topic_0000001088754632_p15741450109"></a>Kubernetes</p>
</td>
<td class="cellrowborder" valign="top" width="28.517148285171483%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001088754632_p1857416501305"><a name="zh-cn_topic_0000001088754632_p1857416501305"></a><a name="zh-cn_topic_0000001088754632_p1857416501305"></a>1.19.10</p>
</td>
<td class="cellrowborder" valign="top" width="32.816718328167184%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0000001088754632_p4574250009"><a name="zh-cn_topic_0000001088754632_p4574250009"></a><a name="zh-cn_topic_0000001088754632_p4574250009"></a>Kubernetes 1.19版本弃用部分常用的APIVersion。建议您在升级集群前对本文档中所列举的弃用APIVersion进行相应升级。</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001088754632_row18141164895219"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p18141848105216"><a name="zh-cn_topic_0000001088754632_p18141848105216"></a><a name="zh-cn_topic_0000001088754632_p18141848105216"></a>Docker</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p9141184815214"><a name="zh-cn_topic_0000001088754632_p9141184815214"></a><a name="zh-cn_topic_0000001088754632_p9141184815214"></a>EulerOS/CentOS：18.09.0.100</p>
<p id="zh-cn_topic_0000001088754632_p9790113195019"><a name="zh-cn_topic_0000001088754632_p9790113195019"></a><a name="zh-cn_topic_0000001088754632_p9790113195019"></a>Ubuntu：18.09.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001088754632_p19469152035512"><a name="zh-cn_topic_0000001088754632_p19469152035512"></a><a name="zh-cn_topic_0000001088754632_p19469152035512"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001088754632_row20122846135210"><td class="cellrowborder" rowspan="3" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p1512213462520"><a name="zh-cn_topic_0000001088754632_p1512213462520"></a><a name="zh-cn_topic_0000001088754632_p1512213462520"></a>操作系统</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p11122134655210"><a name="zh-cn_topic_0000001088754632_p11122134655210"></a><a name="zh-cn_topic_0000001088754632_p11122134655210"></a>CentOS Linux release 7.6</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001088754632_p2122184611526"><a name="zh-cn_topic_0000001088754632_p2122184611526"></a><a name="zh-cn_topic_0000001088754632_p2122184611526"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001088754632_row1415162785517"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p215152755511"><a name="zh-cn_topic_0000001088754632_p215152755511"></a><a name="zh-cn_topic_0000001088754632_p215152755511"></a>EulerOS release 2.5</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p1036022555516"><a name="zh-cn_topic_0000001088754632_p1036022555516"></a><a name="zh-cn_topic_0000001088754632_p1036022555516"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001088754632_row1656414245556"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p17565124165517"><a name="zh-cn_topic_0000001088754632_p17565124165517"></a><a name="zh-cn_topic_0000001088754632_p17565124165517"></a>Ubuntu 18.04 server 64bit</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p113601325155511"><a name="zh-cn_topic_0000001088754632_p113601325155511"></a><a name="zh-cn_topic_0000001088754632_p113601325155511"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001088754632_row115743505013"><td class="cellrowborder" rowspan="5" valign="top" width="15.518448155184483%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p232914164473"><a name="zh-cn_topic_0000001088754632_p232914164473"></a><a name="zh-cn_topic_0000001088754632_p232914164473"></a>CCE Turbo集群</p>
</td>
<td class="cellrowborder" valign="top" width="23.147685231476853%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p13574105017010"><a name="zh-cn_topic_0000001088754632_p13574105017010"></a><a name="zh-cn_topic_0000001088754632_p13574105017010"></a>Kubernetes</p>
</td>
<td class="cellrowborder" valign="top" width="28.517148285171483%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001088754632_p65748508018"><a name="zh-cn_topic_0000001088754632_p65748508018"></a><a name="zh-cn_topic_0000001088754632_p65748508018"></a>1.19.10</p>
</td>
<td class="cellrowborder" valign="top" width="32.816718328167184%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0000001088754632_p155744507011"><a name="zh-cn_topic_0000001088754632_p155744507011"></a><a name="zh-cn_topic_0000001088754632_p155744507011"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001088754632_row11789592554"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p47985985513"><a name="zh-cn_topic_0000001088754632_p47985985513"></a><a name="zh-cn_topic_0000001088754632_p47985985513"></a>Docker</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p15914171311536"><a name="zh-cn_topic_0000001088754632_p15914171311536"></a><a name="zh-cn_topic_0000001088754632_p15914171311536"></a>EulerOS/CentOS：18.09.0</p>
<p id="zh-cn_topic_0000001088754632_p139141013135315"><a name="zh-cn_topic_0000001088754632_p139141013135315"></a><a name="zh-cn_topic_0000001088754632_p139141013135315"></a>Ubuntu：18.09.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001088754632_p191831128185517"><a name="zh-cn_topic_0000001088754632_p191831128185517"></a><a name="zh-cn_topic_0000001088754632_p191831128185517"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001088754632_row45741250801"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p5101192295316"><a name="zh-cn_topic_0000001088754632_p5101192295316"></a><a name="zh-cn_topic_0000001088754632_p5101192295316"></a>Containerd</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p3100822105319"><a name="zh-cn_topic_0000001088754632_p3100822105319"></a><a name="zh-cn_topic_0000001088754632_p3100822105319"></a>1.4.1</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001088754632_p218362812559"><a name="zh-cn_topic_0000001088754632_p218362812559"></a><a name="zh-cn_topic_0000001088754632_p218362812559"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001088754632_row857455010018"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p1199122212532"><a name="zh-cn_topic_0000001088754632_p1199122212532"></a><a name="zh-cn_topic_0000001088754632_p1199122212532"></a>操作系统（弹性云服务器）</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p1898422195312"><a name="zh-cn_topic_0000001088754632_p1898422195312"></a><a name="zh-cn_topic_0000001088754632_p1898422195312"></a>CentOS Linux release 7.6</p>
<p id="zh-cn_topic_0000001088754632_p125615545549"><a name="zh-cn_topic_0000001088754632_p125615545549"></a><a name="zh-cn_topic_0000001088754632_p125615545549"></a>Ubuntu 18.04 server 64bit</p>
<p id="zh-cn_topic_0000001088754632_p193557201107"><a name="zh-cn_topic_0000001088754632_p193557201107"></a><a name="zh-cn_topic_0000001088754632_p193557201107"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001088754632_p1341042914552"><a name="zh-cn_topic_0000001088754632_p1341042914552"></a><a name="zh-cn_topic_0000001088754632_p1341042914552"></a>无</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001088754632_row107813265418"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0000001088754632_p7781729546"><a name="zh-cn_topic_0000001088754632_p7781729546"></a><a name="zh-cn_topic_0000001088754632_p7781729546"></a>操作系统（弹性裸金属服务器）</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0000001088754632_p0948458172317"><a name="zh-cn_topic_0000001088754632_p0948458172317"></a><a name="zh-cn_topic_0000001088754632_p0948458172317"></a>CentOS Linux release 7.6</p>
<p id="zh-cn_topic_0000001088754632_p1194815820232"><a name="zh-cn_topic_0000001088754632_p1194815820232"></a><a name="zh-cn_topic_0000001088754632_p1194815820232"></a>Ubuntu 18.04 server 64bit</p>
<p id="zh-cn_topic_0000001088754632_p7948358172317"><a name="zh-cn_topic_0000001088754632_p7948358172317"></a><a name="zh-cn_topic_0000001088754632_p7948358172317"></a>EulerOS release 2.9</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0000001088754632_p441072920559"><a name="zh-cn_topic_0000001088754632_p441072920559"></a><a name="zh-cn_topic_0000001088754632_p441072920559"></a>无</p>
</td>
</tr>
</tbody>
</table>

## 资源变更与弃用<a name="zh-cn_topic_0000001088754632_zh-cn_topic_0000001072975092_section51381161799"></a>

**社区1.19 ReleaseNotes**

-   增加对vSphere in-tree卷迁移至vSphere CSI驱动的支持。in-tree vSphere Volume插件将不再使用，并在将来的版本中删除。
-   apiextensions.k8s.io/v1beta1已弃用，推荐使用apiextensions.k8s.io/v1。
-   apiregistration.k8s.io/v1beta1已弃用，推荐使用apiregistration.k8s.io/v1。
-   authentication.k8s.io/v1beta1、authorization.k8s.io/v1beta1已弃用，1.22将移除，推荐使用authentication.k8s.io/v1、authorization.k8s.io/v1。
-   autoscaling/v2beta1已弃用，推荐使用autoscaling/v2beta2。
-   coordination.k8s.io/v1beta1在1.19中已弃用，1.22将移除，推荐使用v1。
-   Kube-apiserver: componentstatus API已弃用。
-   Kubeadm：kubeadm config view命令已被弃用，并将在未来版本中删除，请使用kubectl get cm -o yaml -n kube-system kubeadm-config来直接获取kubeadm配置。
-   Kubeadm：弃用kubeadm alpha kubelet config enable-dynamic命令。
-   Kubeadm：kubeadm alpha certs renew命令--use-api参数已弃用。
-   Kubernetes不再支持构建hyperkube镜像。
-   Remove --export flag from kubectl get command - kubectl get中移除 --export参数。
-   alpha特性“ResourceLimitsPriorityFunction”已完全删除。
-   storage.k8s.io/v1beta1已弃用，推荐使用storage.k8s.io/v1。

**社区1.18 ReleaseNotes**

-   kube-apiserver
    -   apps/v1beta1 and apps/v1beta2下所有资源不再提供服务，使用apps/v1替代。
    -   extensions/v1beta1下daemonsets，deployments，replicasets不再提供服务，使用apps/v1替代。
    -   extensions/v1beta1下networkpolicies不再提供服务，使用networking.k8s.io/v1替代。
    -   extensions/v1beta1下podsecuritypolicies不再提供服务，使用policy/v1beta1替代。


-   kubelet
    -   --redirect-container-streaming不推荐使用，v1.20会正式废弃。
    -   资源度量端点 /metrics/resource/v1alpha1以及此端点下的所有度量标准均已弃用。请转换为端点 /metrics/resource下的度量标准：
        -   scrape\_error --\> scrape\_error
        -   node\_cpu\_usage\_seconds\_total --\> node\_cpu\_usage\_seconds
        -   node\_memory\_working\_set\_bytes --\> node\_memory\_working\_set\_bytes
        -   container\_cpu\_usage\_seconds\_total --\> container\_cpu\_usage\_seconds
        -   container\_memory\_working\_set\_bytes --\> container\_memory\_working\_set\_bytes
        -   scrape\_error --\> scrape\_error

    -   在将来的发行版中，kubelet将不再根据CSI规范创建CSI NodePublishVolume目标目录。可能需要相应地更新CSI驱动程序，以正确创建和处理目标路径。


-   kube-proxy
    -   --healthz-port和--metrics-port参数不建议使用，请使用--healthz-bind-address和--metrics-bind-address。
    -   增加EndpointSliceProxying功能选项以控制kube-proxy中EndpointSlices的使用，默认情况下已禁用此功能。


-   kubeadm
    -   kubeadm upgrade node的--kubelet-version参数已弃用，将在后续版本中删除。
    -   kubeadm alpha certs renew命令中--use-api参数已弃用。
    -   kube-dns已弃用，在将来的版本中将不再受支持。
    -   kubeadm-config ConfigMap中存在的ClusterStatus结构体已废弃，将在后续版本中删除。


-   kubectl
    -   --dry-run不建议使用boolean和unset values，新版本中server|client|none会被使用。
    -   kubectl apply --server-dry-run已弃用，替换为--dry-run=server。


-   add-ons

删除cluster-monitoring插件。

-   kube-scheduler
    -   scheduling\_duration\_seconds指标已弃用。
    -   scheduling\_algorithm\_predicate\_evaluation\_seconds和scheduling\_algorithm\_priority\_evaluation\_seconds指标已弃用，使用framework\_extension\_point\_duration\_seconds\[extension\_point="Filter"\]和framework\_extension\_point\_duration\_seconds\[extension\_point="Score"\]替代。
    -   调度器策略AlwaysCheckAllPredicates已弃用。


-   其他变化
    -   k8s.io/node-api组件不再更新。作为替代，可以使用位于k8s.io/api中的RuntimeClass类型和位于k8s.io/client-go中的generated clients。
    -   已从apiserver\_request\_total中删除“client”标签。


## 参考链接<a name="zh-cn_topic_0000001088754632_zh-cn_topic_0000001072975092_zh-cn_topic_0261805759_zh-cn_topic_0261793154_section1272182810583"></a>

关于Kubernetes 1.19与其他版本的性能对比和功能演进的更多信息，请参考：

-   [Kubernetes v1.19.0 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.19.md#changes)
-   [Kubernetes v1.18.0 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.18.md#changes)

