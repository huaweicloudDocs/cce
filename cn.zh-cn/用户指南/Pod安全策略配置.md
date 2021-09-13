# Pod安全策略配置<a name="cce_01_0275"></a>

Pod安全策略（Pod Security Policy） 是集群级别的资源，它能够控制Pod规约中与安全性相关的各个方面。  [PodSecurityPolicy](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.19/#podsecuritypolicy-v1beta1-policy)对象定义了一组Pod运行时必须遵循的条件及相关字段的默认值，只有Pod满足这些条件才会被系统接受。

v1.17.17版本的集群默认启用Pod安全策略准入控制组件，并创建名为**psp-global**的全局默认安全策略，您可根据自身业务需要修改全局策略（请勿直接删除默认策略），也可新建自己的Pod安全策略并绑定RBAC配置。

>![](public_sys-resources/icon-note.gif) **说明：** 
>除全局默认安全策略外，系统为kube-system命名空间下的系统组件配置了独立的Pod安全策略，修改psp-global配置不影响kube-system下Pod创建。

## 修改全局默认Pod安全策略<a name="section1077811013599"></a>

修改全局默认Pod安全策略前，请确保已创建CCE集群，并且通过kubectl连接集群成功。

1.  执行如下命令：

    **kubectl edit psp psp-global**

2.  修改所需的参数，请参考[PodSecurityPolicy](https://kubernetes.io/zh/docs/tasks/administer-cluster/sysctl-cluster/#podsecuritypolicy)。

## Pod安全策略开放非安全系统配置示例<a name="section155111941177"></a>

节点池管理中可以为相应的节点池配置allowed-unsafe-sysctls，CCE从**1.17.17**集群版本开始，需要在pod安全策略的allowedUnsafeSysctls中增加相应的配置才能生效，详情请参见[PodSecurityPolicy](https://kubernetes.io/zh/docs/tasks/administer-cluster/sysctl-cluster/#podsecuritypolicy)。

除修改全局Pod安全策略外，也可增加新的Pod安全策略，如开放net.core.somaxconn非安全系统配置，新增Pod安全策略示例参考如下：

```
apiVersion: policy/v1beta1
kind: PodSecurityPolicy
metadata:
  annotations:
    seccomp.security.alpha.kubernetes.io/allowedProfileNames: '*'
  name: sysctl-psp
spec:
  allowedUnsafeSysctls:
  - net.core.somaxconn
  allowPrivilegeEscalation: true
  allowedCapabilities:
  - '*'
  fsGroup:
    rule: RunAsAny
  hostIPC: true
  hostNetwork: true
  hostPID: true
  hostPorts:
  - max: 65535
    min: 0
  privileged: true
  runAsGroup:
    rule: RunAsAny
  runAsUser:
    rule: RunAsAny
  seLinux:
    rule: RunAsAny
  supplementalGroups:
    rule: RunAsAny
  volumes:
  - '*'
---
kind: ClusterRole
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: sysctl-psp
rules:
  - apiGroups:
      - "*"
    resources:
      - podsecuritypolicies
    resourceNames:
      - sysctl-psp
    verbs:
      - use

---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: sysctl-psp
roleRef:
  kind: ClusterRole
  name: sysctl-psp
  apiGroup: rbac.authorization.k8s.io
subjects:
- kind: Group
  name: system:authenticated
  apiGroup: rbac.authorization.k8s.io
```

## 恢复原始Pod安全策略<a name="section86008121714"></a>

如果您已经修改默认Pod安全策略后，想恢复原始Pod安全策略，请执行以下操作。

1.  创建一个名为policy.yaml的描述文件。其中，policy.yaml为自定义名称，您可以随意命名。

    **vi policy.yaml**

    描述文件内容如下。

    ```
    apiVersion: policy/v1beta1
    kind: PodSecurityPolicy
    metadata:
      name: psp-global
      annotations:
        seccomp.security.alpha.kubernetes.io/allowedProfileNames: '*'
    spec:
      privileged: true
      allowPrivilegeEscalation: true
      allowedCapabilities:
        - '*'
      volumes:
        - '*'
      hostNetwork: true
      hostPorts:
        - min: 0
          max: 65535
      hostIPC: true
      hostPID: true
      runAsUser:
        rule: 'RunAsAny'
      seLinux:
        rule: 'RunAsAny'
      supplementalGroups:
        rule: 'RunAsAny'
      fsGroup:
        rule: 'RunAsAny'
     
    ---
    kind: ClusterRole
    apiVersion: rbac.authorization.k8s.io/v1
    metadata:
      name: psp-global
    rules:
      - apiGroups:
          - "*"
        resources:
          - podsecuritypolicies
        resourceNames:
          - psp-global
        verbs:
          - use
     
    ---
    apiVersion: rbac.authorization.k8s.io/v1
    kind: ClusterRoleBinding
    metadata:
      name: psp-global
    roleRef:
      kind: ClusterRole
      name: psp-global
      apiGroup: rbac.authorization.k8s.io
    subjects:
    - kind: Group
      name: system:authenticated
      apiGroup: rbac.authorization.k8s.io
    ```

2.  执行如下命令：

    **kubectl apply -f policy.yaml**


