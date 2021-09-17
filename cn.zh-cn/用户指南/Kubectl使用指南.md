# Kubectl使用指南<a name="cce_01_0023"></a>

使用Kubectl命令时，您需要具备Kubectl相关开发技能，了解Kubectl相关操作。详细请参考[Kubernetes API](https://kubernetes.io/docs/concepts/overview/kubernetes-api/)、[kubectl CLI](https://kubernetes.io/docs/reference/kubectl/overview/)。

请到[kubernetes版本发布页面](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/README.md)下载与集群版本对应的或者更新的kubectl。

## 连接集群<a name="section223415528535"></a>

-   [通过Kubectl连接集群](通过kubectl连接集群.md)
-   [通过web-terminal插件连接集群](web-terminal.md)

## CoreDNS高可用<a name="section4965217185418"></a>

-   [通过kubectl配置kube-dns高可用](通过kubectl配置kube-dns-CoreDNS高可用.md)

## 创建工作负载<a name="section81661268550"></a>

-   [通过Kubectl创建无状态工作负载](创建无状态负载(Deployment).md#section155246177178)
-   [通过kubectl创建有状态工作负载](创建有状态负载(StatefulSet).md#section113441881214)

## 工作负载亲和/反亲和调度<a name="section1294518341552"></a>

-   [工作负载与节点亲和-yaml示例](工作负载和节点的亲和性.md#section711574271117)
-   [工作负载与节点反亲和-yaml示例](工作负载和节点的反亲和性.md#section1361482522712)
-   [工作负载间亲和-yaml示例](工作负载间的亲和性.md#section5140193643912)
-   [工作负载间反亲和-yaml示例](工作负载间的反亲和性.md#section1894310152317)
-   [工作负载与可用区亲和-yaml示例](工作负载和可用区的亲和性.md#section4201420133117)
-   [工作负载与可用区反亲和-yaml示例](工作负载和可用区的反亲和性.md#section102822029173111)

## 工作负载访问方式设置<a name="section557132035713"></a>

-   [通过kubectl命令实现集群内访问](集群内访问(ClusterIP).md#section9813121512319)
-   [通过kubectl命令实现节点访问](节点访问(NodePort).md#section7114174773118)
-   [通过kubectl命令行实现四层负载均衡](负载均衡(LoadBalancer).md#section1984211714368)
-   [通过kubectl命令行实现DNAT网关](DNAT网关(DNAT).md#section646312404363)
-   [通过kubectl命令实现七层负载均衡](通过Kubectl命令行添加ELB型Ingress.md)

## 工作负载高级设置<a name="section927251814582"></a>

-   [设置容器生命周期-Yaml样例](设置容器生命周期.md#section151181981167)

## 任务管理<a name="section1660674011584"></a>

-   [使用kubectl创建Job](创建普通任务(Job).md#section450152719412)
-   [使用kubectl创建CronJob](创建定时任务(CronJob).md#section13519162224919)

## 配置中心<a name="section12376151215916"></a>

-   [使用kubectl创建配置项](创建配置项.md#section639712716372)
-   [使用kubectl创建密钥](创建密钥.md#section821112149514)

## 存储管理<a name="section274418453590"></a>

-   [使用kubectl创建云硬盘](使用kubectl自动创建云硬盘.md)
-   [使用kubectl挂载云硬盘](使用kubectl部署带云硬盘存储卷的工作负载.md)
-   [使用kubectl创建对象存储](使用kubectl自动创建对象存储.md)
-   [使用kubectl挂载对象存储](使用kubectl部署带对象存储卷的无状态工作负载.md)
-   [使用kubectl创建文件存储](使用kubectl自动创建文件存储.md)
-   [使用kubectl挂载文件存储](使用kubectl部署带文件存储卷的无状态工作负载.md)

