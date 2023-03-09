# AOM弹性伸缩切换至HPA/CustomedHPA说明<a name="cce_01_0395"></a>

CCE在1.15及以下版本集群支持根据AOM监控数据做工作负载弹性伸缩，该方法在1.17及以上版本集群不再支持。

如果您使用了AOM弹性伸缩方法，当集群升级到1.17后，可以切换至[HPA](创建工作负载弹性伸缩（HPA）-169.md)/[CustomedHPA](创建工作负载弹性伸缩（CustomedHPA）-170.md)弹性伸缩方法，在切换时需要注意如下差异：

-   AOM弹性伸缩的利用率计算基于工作负载的limit，利用率区间为0%\~100%
-   HPA/CustomedHPA的利用率基于request计算，其区间能够大于100%

例如某个工作负载的内存request是2G, limit是16G，AOM的弹性伸缩策略是利用率达到limit的50%就扩容（即8G）；使用HPA/CustomedHPA按照request计算，同样控制内存使用到8G，需要把利用率调整为16×50%/2=400%。

