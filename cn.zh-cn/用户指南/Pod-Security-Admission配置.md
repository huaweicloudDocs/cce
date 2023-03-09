# Pod Security Admission配置<a name="cce_10_0466"></a>

在使用[Pod Security Admission](https://kubernetes.io/zh-cn/docs/concepts/security/pod-security-admission/)前，需要先了解Kubernetes的[Pod安全性标准（Security Standards）](https://kubernetes.io/zh-cn/docs/concepts/security/pod-security-standards/)。Pod安全性标准（Security Standards） 为 Pod 定义了不同的安全性策略级别。这些标准能够让你以一种清晰、一致的方式定义如何限制Pod行为。而Pod Security Admission则是这些安全性标准的控制器，用于在创建Pod时执行定义好的安全限制。

Pod安全性标准定义了三种安全性策略级别：

**表 1**  Pod安全性策略级别

<a name="table0547553318"></a>
<table><thead align="left"><tr id="row8576251317"><th class="cellrowborder" valign="top" width="22.5%" id="mcps1.2.3.1.1"><p id="p0576185113113"><a name="p0576185113113"></a><a name="p0576185113113"></a>策略级别（level）</p>
</th>
<th class="cellrowborder" valign="top" width="77.5%" id="mcps1.2.3.1.2"><p id="p145763510317"><a name="p145763510317"></a><a name="p145763510317"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2576155103114"><td class="cellrowborder" valign="top" width="22.5%" headers="mcps1.2.3.1.1 "><p id="p1457695183116"><a name="p1457695183116"></a><a name="p1457695183116"></a>privileged</p>
</td>
<td class="cellrowborder" valign="top" width="77.5%" headers="mcps1.2.3.1.2 "><p id="p25771655312"><a name="p25771655312"></a><a name="p25771655312"></a>不受限制，通常适用于特权较高、受信任的用户所管理的系统级或基础设施级负载，例如CNI、存储驱动等。</p>
</td>
</tr>
<tr id="row957745203113"><td class="cellrowborder" valign="top" width="22.5%" headers="mcps1.2.3.1.1 "><p id="p135770517313"><a name="p135770517313"></a><a name="p135770517313"></a>baseline</p>
</td>
<td class="cellrowborder" valign="top" width="77.5%" headers="mcps1.2.3.1.2 "><p id="p257765173110"><a name="p257765173110"></a><a name="p257765173110"></a>限制较弱但防止已知的特权提升（Privilege Escalation），通常适用于部署常用的非关键性应用负载，该策略将禁止使用hostNetwork、hostPID等能力。</p>
</td>
</tr>
<tr id="row6577115133114"><td class="cellrowborder" valign="top" width="22.5%" headers="mcps1.2.3.1.1 "><p id="p1857775163110"><a name="p1857775163110"></a><a name="p1857775163110"></a>restricted</p>
</td>
<td class="cellrowborder" valign="top" width="77.5%" headers="mcps1.2.3.1.2 "><p id="p75779513312"><a name="p75779513312"></a><a name="p75779513312"></a>严格限制，遵循Pod防护的最佳实践。</p>
</td>
</tr>
</tbody>
</table>

[Pod Security Admission配置](#section4761636371)是命名空间级别的，控制器将会对该命名空间下Pod或容器中的安全上下文（Security Context）以及其他参数进行限制。其中，privileged策略将不会对Pod和Container配置中的securityContext字段有任何校验，而Baseline和Restricted则会对securityContext字段有不同的取值要求，具体规范请参见[Pod安全性标准（Security Standards）](https://kubernetes.io/zh-cn/docs/concepts/security/pod-security-standards/)。

关于如何在Pod或容器中设置Security Context，请参见[为Pod或容器配置Security Context](https://kubernetes.io/zh-cn/docs/tasks/configure-pod-container/security-context/)。

## Pod Security Admission标签<a name="section5799112914313"></a>

Kubernetes为Pod Security Admission定义了三种标签，如[表2](#table198561415448)，您可以在某个命名空间中设置这些标签来定义需要使用的Pod安全性标准级别，但请勿在kube-system等系统命名空间修改Pod安全性标准级别，否则可能导致系统命名空间下Pod故障。

**表 2**  Pod Security Admission标签

<a name="table198561415448"></a>
<table><thead align="left"><tr id="row9151615174411"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p915171516445"><a name="p915171516445"></a><a name="p915171516445"></a>隔离模式（mode）</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.2"><p id="p6348919151310"><a name="p6348919151310"></a><a name="p6348919151310"></a>生效对象</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p41571504419"><a name="p41571504419"></a><a name="p41571504419"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row515141520440"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p91515151447"><a name="p91515151447"></a><a name="p91515151447"></a>enforce</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p3348171912132"><a name="p3348171912132"></a><a name="p3348171912132"></a>Pod</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p1115151514413"><a name="p1115151514413"></a><a name="p1115151514413"></a>违反指定策略会导致Pod无法创建。</p>
</td>
</tr>
<tr id="row6159155449"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p121541514417"><a name="p121541514417"></a><a name="p121541514417"></a>audit</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p834818193135"><a name="p834818193135"></a><a name="p834818193135"></a>工作负载（例如Deployment、Job等）</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p7151115194412"><a name="p7151115194412"></a><a name="p7151115194412"></a>违反指定策略会在审计日志（audit log）中添加新的审计事件，Pod可以被创建。</p>
</td>
</tr>
<tr id="row1415315164416"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p51591511449"><a name="p51591511449"></a><a name="p51591511449"></a>warn</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p434818194133"><a name="p434818194133"></a><a name="p434818194133"></a>工作负载（例如Deployment、Job等）</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p215215104419"><a name="p215215104419"></a><a name="p215215104419"></a>违反指定策略会返回用户可见的告警信息，Pod可以被创建。</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：** 
>Pod通常是通过创建Deployment或Job这类工作负载对象来间接创建的。在使用Pod Security Admission时，audit或warn模式的隔离都将在工作负载级别生效，而enforce模式并不会应用到工作负载，仅在Pod上生效。

## 使用命名空间标签进行Pod Security Admission配置<a name="section4761636371"></a>

您可以在不同的隔离模式中应用不同的策略，由于Pod安全性准入能力是在命名空间（Namespace）级别实现的，因此假设某个Namespace配置如下：

```
apiVersion: v1
kind: Namespace
metadata:
  name: my-baseline-namespace
  labels:
    pod-security.kubernetes.io/enforce: privileged
    pod-security.kubernetes.io/enforce-version: v1.25
    pod-security.kubernetes.io/audit: baseline
    pod-security.kubernetes.io/audit-version: v1.25
    pod-security.kubernetes.io/warn: restricted
    pod-security.kubernetes.io/warn-version: v1.25

    # 标签有以下两种格式：
    # pod-security.kubernetes.io/<MODE>: <LEVEL> 
    # pod-security.kubernetes.io/<MODE>-version: <VERSION>  
    # audit和warn模式的作用主要在于提供相应信息供用户排查负载违反了哪些安全行为
```

命名空间的标签用来表示不同的模式所应用的安全策略级别，存在以下两种格式：

-   pod-security.kubernetes.io/<MODE\>: <LEVEL\>
    -   <MODE\>：必须是enforce、audit或warn之一，关于标签详情请参见[表2](#table198561415448)。
    -   <LEVEL\>：必须是privileged、baseline或restricted之一，关于安全性策略级别详情请参见[表1](#table0547553318)。

-   pod-security.kubernetes.io/<MODE\>-version: <VERSION\>

    该标签为可选，可以将安全性策略锁定到Kubernetes版本号。

    -   <MODE\>：必须是enforce、audit或warn之一，关于标签详情请参见[表2](#table198561415448)。
    -   <VERSION\>：Kubernetes版本号。例如 v1.25，也可以使用latest。


若在上述Namespace中部署Pod，则会有以下安全性限制：

1.  设置了enforce隔离模式对应的策略为privileged，将会跳过enforce阶段的校验。
2.  设置了audit隔离模式对应的策略为baseline，将会校验baseline策略相关限制，即如果Pod或Container违反了该策略，审计日志中将添加相应事件。
3.  设置了warn隔离模式对应的策略为restricted，将会校验restricted策略相关限制，即如果Pod或Container违反了该策略，用户将会在创建pod时收到告警信息。

## 从PodSecurityPolicy迁移到Pod Security Admission<a name="section7164192319226"></a>

如您在1.25之前版本的集群中使用了PodSecurityPolicy，且需要在1.25及以后版本集群中继续使用Pod Security Admission来替代PodSecurityPolicy的用户，请参见[从PodSecurityPolicy迁移到内置的Pod Security Admission](https://kubernetes.io/zh-cn/docs/tasks/configure-pod-container/migrate-from-psp/#eliminating-mutaging-fields)。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>1.  由于Pod Security Admission仅支持三种隔离模式，因此灵活性相比于PodSecurityPolicy较差，部分场景下需要用户自行定义验证准入Webhook来实施更精准的策略。
>2.  由于PodSecurityPolicy具有变更能力，而Pod Security Admission并不具备该能力，因此之前依赖该能力的用户需要自行定义变更准入Webhook或修改Pod中的securityContext字段。
>3.  PodSecurityPolicy允许为不同的服务帐号（Service Account）绑定不同策略（Kubernetes社区不建议使用该能力）。如果您有使用该能力的诉求，在迁移至Pod Security Admission后，需要自行定义第三方Webhook。
>4.  请勿将Pod Security Admission能力应用于kube-system、kube-public和kube-node-lease等一些CCE组件部署的Namespace中，否则会导致CCE组件、插件功能异常。

## 参考文档<a name="section164185819161"></a>

-   [Pod安全性准入](https://kubernetes.io/zh-cn/docs/concepts/security/pod-security-admission/)
-   [从PodSecurityPolicy映射到Pod安全性标准](https://kubernetes.io/zh-cn/docs/reference/access-authn-authz/psp-to-pod-security-standards/)
-   [使用命名空间标签来实施Pod安全性标准](https://kubernetes.io/zh-cn/docs/tasks/configure-pod-container/enforce-standards-namespace-labels/)
-   [通过配置内置准入控制器实施Pod安全标准](https://kubernetes.io/zh-cn/docs/tasks/configure-pod-container/enforce-standards-admission-controller/)

