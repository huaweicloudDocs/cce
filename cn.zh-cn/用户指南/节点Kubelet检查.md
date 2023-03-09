# 节点Kubelet检查<a name="cce_10_0448"></a>

## 检查项内容<a name="section696875418551"></a>

检查节点kubelet服务是否运行正常。

## 解决方案<a name="section10591195810550"></a>

-   **问题场景一：kubelet状态异常**

    kubelet异常时，节点显示不可用，请参考[集群可用，但节点状态为“不可用”](https://support.huaweicloud.com/cce_faq/cce_faq_00120.html)修复节点后，重试检查任务。

-   **问题场景二：cce-pause版本异常**

    检测到当前kubelet依赖的pause容器镜像版本非cce-pause:3.1，继续升级将会导致批量Pod重启，当前暂不支持升级，请联系技术支持人员。


