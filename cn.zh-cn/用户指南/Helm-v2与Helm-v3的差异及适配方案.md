# Helm v2与Helm v3的差异及适配方案<a name="cce_10_0421"></a>

随着Helm v2 发布最终版本Helm 2.17.0，Helm v3 现在已是 Helm 开发者社区支持的唯一标准。为便于管理，建议用户尽快将模板切换至[Helm v3格式](https://v3.helm.sh/docs/topics/charts/)。

当前社区从Helm v2演进到Helm v3，主要有以下变化：

1.  **移除tiller**

    Helm v3 使用更加简单和灵活的架构，移除了 tiller，直接通过kubeconfig连接apiserver，简化安全模块，降低了用户的使用壁垒。

2.  **改进了升级策略，采用三路策略合并补丁**

    Helm v2 使用双路策略合并补丁。在升级过程中，会对比最近一次发布的chart manifest和本次发布的chart manifest的差异，来决定哪些更改会应用到Kubernetes资源中。如果更改是集群外带的（比如通过kubectl edit），则修改不会被Helm识别和考虑。结果就是资源不会回滚到之前的状态。

    Helm v3 使用三路策略来合并补丁，Helm在生成一个补丁时，会考虑之前老的manifest的活动状态。因此，Helm在使用老的chart manifest生成新补丁时会考虑当前活动状态，并将其与之前老的 manifest 进行比对，并再比对新的 manifest 是否有改动，并进行自动补全，以此来生成最终的更新补丁。

    详情及示例请见Helm官方文档：[https://v3.helm.sh/docs/faq/changes\_since\_helm2](https://v3.helm.sh/docs/faq/changes_since_helm2)

3.  **默认存储驱动程序更改为secrets**

    Helm v2 默认情况下使用 ConfigMaps 存储发行信息，而在 Helm v3 中默认使用 Secrets。

4.  **发布名称限制在namespace范围内**

    Helm v2 只使用tiller 的namespace 作为release信息的存储，这样全集群的release名字都不能重复。Helm v3只会在release安装的所在namespace记录对应的信息，这样release名称可在不同命名空间重用。应用和release命名空间一致。

5.  **校验方式改变**

    Helm v3 对模板格式的校验更加严格，如Helm v3 将chart.yaml的apiVersion从v1切换到v2，针对Helm v2的chart.yaml，强要求指定apiVersion为v1。可安装Helm v3客户端后，通过执行helm lint命令校验模板格式是否符合v3规范。

    **适配方案**：根据Helm官方文档  [https://helm.sh/docs/topics/charts/](https://helm.sh/docs/topics/charts/)适配Helm v3模板，apiVersion字段必填。

6.  **废弃crd-install**

    Helm v3删除了crd-install hook， 并用chart中的crds目录替换。需要注意的是，crds目录中的资源只有在release安装时会部署，升级时不会更新，删除时不会卸载crds目录中的资源。若crd已存在，则重复安装不会报错。

    **适配方案**：根据Helm官方文档  [https://helm.sh/docs/chart\_best\_practices/custom\_resource\_definitions/](https://helm.sh/docs/chart_best_practices/custom_resource_definitions/), 当前可使用crds目录或者将crd定义单独放入chart。考虑到目前不支持使用Helm升级或删除CRD，推荐分隔chart，将CRD定义放入chart中，然后将所有使用该CRD的资源放到另一个 chart中进行管理。

7.  **未通过helm创建的资源不强制update，releaes默认不强制升级**

    Helm v3强制升级逻辑变化，不再是升级失败后走删除重建，而是直接走put更新逻辑。因此当前CCE release升级默认使用非强制更新逻辑，无法通过Patch更新的资源将导致release升级失败。若环境存在同名资源且无Helm V3的归属标记app.kubernetes.io/managed-by: Helm，则会提示资源冲突。

    **适配方案**：删除相关资源，并通过Helm创建。

8.  **Release history数量限制更新**

    为避免release 历史版本无限增加，当前release升级默认只保留最近10个历史版本。


**更多变化和详细说明请参见Helm官方文档**

-   Helm v2与Helm v3的区别：[https://v3.helm.sh/docs/faq/changes\_since\_helm2](https://v3.helm.sh/docs/faq/changes_since_helm2)
-   Helm v2如何迁移到Helm v3：[https://helm.sh/docs/topics/v2\_v3\_migration](https://helm.sh/docs/topics/v2_v3_migration)

