# 节点Ready检查<a name="cce_10_0455"></a>

## 检查项内容<a name="section4309457255"></a>

检查集群内节点是否Ready。

## 解决方案<a name="section5587191111250"></a>

-   **问题场景一：节点状态显示不可用**

    请登录CCE控制台，单击集群名称进入集群控制台，前往“节点管理”，筛选出状态不可用的节点后，请参照控制台提供的“修复建议”修复该节点后重试检查。


-   **问题场景二：节点状态与实际不符**

    节点状态与实际不符可能存在两种情况：

    1.  控制台“节点管理”处显示正常，但检查结果仍然提示该节点NotReady。请重试检查。
    2.  控制台“节点管理”处无该节点，但检查结果显示集群中仍然存在该节点。请联系技术人员支持。


