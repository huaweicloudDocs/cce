# 工作负载的DNS配置实践<a name="cce_01_0137"></a>

前面介绍了Linux系统域名解析文件以及Kubernetes为工作负载提供的DNS相关配置项，下面将举例介绍工作负载如何进行DNS配置。

## 场景1 对接kubernetes内置的Kube-DNS/CoreDNS<a name="section843102914412"></a>

**场景说明：**

这种方式适用于工作负载中的域名解析只涉及集群内部域名，或者集群内部域名+外部域名两种方式，工作负载默认采用这种配置。

**示例：**

```
apiVersion: v1
kind: Pod
metadata:
  namespace: default
  name: dns-example
spec:
  containers:
  - name: test
    image: nginx
  dnsPolicy: ClusterFirst
```

该配置下容器的域名解析文件将如下所示：

```
nameserver 10.247.3.10
search default.svc.cluster.local svc.cluster.local cluster.local
options ndots:5
```

## 场景2 直接对接华为云DNS<a name="section1083210344518"></a>

**场景说明：**

这种方式适用于工作负载只访问注册到互联网的外部域名，该场景不能解析集群内部域名。

**示例：**

```
apiVersion: v1
kind: Pod
metadata:
  namespace: default
  name: dns-example
spec:
  containers:
  - name: test
    image: nginx
  dnsPolicy: Default //使用kubelet的“--resolv-conf”参数指向的域名解析文件（CCE集群在该配置下对接华为云DNS）
```

该配置下容器的域名解析文件将如下所示：

```
nameserver 100.125.x.x
```

## 场景3 主机网络模式的工作负载对接Kube-DNS/CoreDNS<a name="section3376240154520"></a>

**场景说明：**

对于配置主机网络模式的工作负载，默认对接华为云DNS，如果工作负载需要对接Kube-DNS/CoreDNS，需将dnsPolicy设置为“ClusterFirstWithHostNet”。

**示例：**

```
apiVersion: extensions/v1beta1
kind: Deployment
metadata:
  name: nginx
spec:
  template:
    metadata:
      labels:
        app: nginx
    spec:
      hostNetwork: true
      dnsPolicy: ClusterFirstWithHostNet
      containers:
      - name: nginx
        image: nginx:1.7.9
        ports:
        - containerPort: 80
```

该配置下容器的域名解析文件将如下所示：

```
nameserver 10.247.3.10
search default.svc.cluster.local svc.cluster.local cluster.local
options ndots:5
```

## 场景4 自定义工作负载的域名配置<a name="section639801718479"></a>

**场景说明：**

用户可以完全自定义配置工作负载的域名解析文件，这种方式非常灵活，dnsPolicy和dnsConfig配合使用，几乎能够满足所有使用场景，如对接用户自建DNS的场景、串联多个DNS的场景以及优化DNS配置选项的场景等等。

**示例1：对接用户自建DNS**

_该配置下，dnsPolicy为“None”，工作负载的域名解析文件完全根据dnsConfig配置生成_。

```
apiVersion: v1
kind: Pod
metadata:
  namespace: default
  name: dns-example
spec:
  containers:
  - name: test
    image: nginx
  dnsPolicy: "None"
  dnsConfig:
    nameservers:
    - 1.2.3.4 //用户自建DNS的IP地址
    searches:
    - ns1.svc.cluster.local
    - my.dns.search.suffix
    options:
    - name: ndots
      value: "2"
    - name: timeout
      value: "3"
```

该配置下容器的域名解析文件将如下所示：

```
nameserver 1.2.3.4
search ns1.svc.cluster.local my.dns.search.suffix
options timeout:3 ndots:2
```

**示例2：修改域名解析文件的ndots选项，减少无效的DNS查询**

_该配置下，dnsPolicy不为“None”，会在基于dnsPolicy生成的域名解析文件的基础上，追加dnsConfig中配置的dns参数。_

```
apiVersion: v1
kind: Pod
metadata:
  namespace: default
  name: dns-example
spec:
  containers:
  - name: test
    image: nginx
  dnsPolicy: "ClusterFirst"
  dnsConfig:
    options:
    - name: ndots
      value: "2" //该配置会将基于ClusterFirst策略生成的域名解析文件的ndots:5参数改写为ndots:2
```

该配置下容器的域名解析文件将如下所示：

```
nameserver 10.247.3.10
search default.svc.cluster.local svc.cluster.local cluster.local
options ndots:2
```

