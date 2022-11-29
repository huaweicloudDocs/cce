# CCE发布Kubernetes 1.17版本说明<a name="cce_10_0471"></a>

云容器引擎（CCE）严格遵循社区一致性认证。本文介绍CCE发布Kubernetes 1.17版本所做的变更说明。

## 资源变更与弃用<a name="zh-cn_topic_0000001088435034_zh-cn_topic_0263124530_section51381161799"></a>

-   apps/v1beta1和apps/v1beta2下所有资源不再提供服务，使用apps/v1替代。
-   extensions/v1beta1下daemonsets、deployments、replicasets不再提供服务，使用apps/v1替代。
-   extensions/v1beta1下networkpolicies不再提供服务，使用networking.k8s.io/v1替代。
-   extensions/v1beta1下podsecuritypolicies不再提供服务，使用policy/v1beta1替代。
-   extensions/v1beta1 ingress v1.20版本不再提供服务，当前可使用networking.k8s.io/v1beta1。
-   scheduling.k8s.io/v1beta1 and scheduling.k8s.io/v1alpha1下的PriorityClass计划在1.17不再提供服务，迁移至scheduling.k8s.io/v1。
-   events.k8s.io/v1beta1中event series.state字段已废弃，将在1.18版本中移除。
-   apiextensions.k8s.io/v1beta1下CustomResourceDefinition已废弃，将再1.19不在提供服务，使用apiextensions.k8s.io/v1。
-   admissionregistration.k8s.io/v1beta1 MutatingWebhookConfiguration和ValidatingWebhookConfiguration已废弃，将在1.19不在提供服务，使用admissionregistration.k8s.io/v1替换。
-   rbac.authorization.k8s.io/v1alpha1 and rbac.authorization.k8s.io/v1beta1被废弃，使用rbac.authorization.k8s.io/v1替代，v1.20会正式停止服务。
-   storage.k8s.io/v1beta1 CSINode object废弃并会在未来版本中移除。

## 其他废弃和移除<a name="zh-cn_topic_0000001088435034_zh-cn_topic_0263124530_section17271659191217"></a>

-   移除OutOfDisk node condition，改为使用DiskPressure。
-   scheduler.alpha.kubernetes.io/critical-pod annotation已被移除，如需要改为设置priorityClassName。
-   beta.kubernetes.io/os和beta.kubernetes.io/arch在1.14版本中已经废弃，计划在1.18版本中移除。
-   禁止通过--node-labels设置kubernetes.io和k8s.io为前缀的标签，老版本中kubernetes.io/availablezone该label在1.17中移除，整改为failure-domain.beta.kubernetes.io/zone获取AZ信息。
-   beta.kubernetes.io/instance-type被废弃，使用node.kubernetes.io/instance-type替代。
-   移除\{kubelet\_root\_dir\}/plugins路径。
-   移除内置集群角色system:csi-external-provisioner和system:csi-external-attacher。

## 参考链接<a name="zh-cn_topic_0000001088435034_zh-cn_topic_0263124530_zh-cn_topic_0261805759_zh-cn_topic_0261793154_section1272182810583"></a>

关于Kubernetes 1.17与其他版本的性能对比和功能演进的更多信息，请参考：

-   [Kubernetes v1.17.0 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.17.md#changes)
-   [Kubernetes v1.16.0 Release Notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.16.md#kubernetes-v1160-release-notes)

