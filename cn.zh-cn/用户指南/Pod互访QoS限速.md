# Pod互访QoS限速<a name="cce_10_0382"></a>

## 操作场景<a name="section1329214638"></a>

部署在同一节点上的不同业务容器之间存在带宽抢占，容易造成业务抖动。您可以通过对Pod间互访进行QoS限速来解决这个问题。

## 约束与限制<a name="section58481435943"></a>

Pod间互访设置QoS限速支持容器隧道网络模型、VPC网络模型和云原生2.0网络模型，其中**VPC网络模型**和**云原生2.0模型**在使用Pod网络限速时需遵循以下约束：

-   仅支持1.19.10以上的集群版本。
-   仅支持普通容器（容器运行时为runc），不支持安全容器（容器运行时为kata）。
-   仅支持限制Pod访问Pod的场景限速，不对访问节点，对外访问产生影响。
-   带宽限速上限值为机型带宽上限和4.3G两者之间的最小值。
-   目前仅支持兆（M）级别以上的限速。

## 操作步骤<a name="section069116421443"></a>

您可以通过对Pod添加annotations指定Pod出口带宽和入口带宽，如下所示。

```
apiVersion: v1
kind: Pod
metadata:
  annotations:
    kubernetes.io/ingress-bandwidth: 100M
    kubernetes.io/egress-bandwidth: 100M
...
```

-   kubernetes.io/ingress-bandwidth：Pod的入口带宽
-   kubernetes.io/egress-bandwidth：Pod的出口带宽

如果不设置这两个参数，则表示不限制带宽。

