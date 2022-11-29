# （停止维护）CCE发布Kubernetes 1.13版本说明<a name="cce_10_0473"></a>

云容器引擎（CCE）严格遵循社区一致性认证。本文介绍CCE发布Kubernetes 1.13版本所做的变更说明。

**表 1**  v1.13版本集群说明

<a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_table14450940866"></a>
<table><thead align="left"><tr id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_row145024011618"><th class="cellrowborder" valign="top" width="29.12%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p3450154019612"><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p3450154019612"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p3450154019612"></a>Kubernetes版本（CCE增强版）</p>
</th>
<th class="cellrowborder" valign="top" width="70.88%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p19450184018614"><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p19450184018614"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p19450184018614"></a>版本说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_row445115408610"><td class="cellrowborder" valign="top" width="29.12%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p845119408613"><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p845119408613"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p845119408613"></a>v1.13.10-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.88%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p84511140467"><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p84511140467"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p84511140467"></a><strong id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_b1472184316246"><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_b1472184316246"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_b1472184316246"></a>主要特性：</strong></p>
<a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul1745134011611"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul1745134011611"></a><ul id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul1745134011611"><li>CCE集群支持添加ARM节点</li><li>负载均衡支持设置名称</li><li>4层负载均衡支持健康检查，7层负载均衡支持健康检查/分配策略/会话保持</li><li>CCE集群支持创建裸金属节点（容器隧道网络）</li><li>支持AI加速型节点（搭载海思Ascend 310 AI处理器），适用于图像识别、视频处理、推理计算以及机器学习等场景</li><li>支持配置docker baseSize</li><li>支持命名空间亲和调度</li><li>支持节点数据盘划分用户空间</li><li>支持集群cpu管理策略</li><li>支持集群下的节点跨子网（容器隧道网络）</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_row119478492200"><td class="cellrowborder" valign="top" width="29.12%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p1994784972010"><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p1994784972010"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p1994784972010"></a>v1.13.7-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.88%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_p8619136162417"><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_p8619136162417"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_p8619136162417"></a><strong id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_b02647401243"><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_b02647401243"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_b02647401243"></a>主要特性：</strong></p>
<a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul770414515210"></a><a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul770414515210"></a><ul id="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul770414515210"><li>Kubernetes同步社区1.13.7版本</li><li>支持网络平面（NetworkAttachmentDefinition）</li></ul>
</td>
</tr>
</tbody>
</table>

## 参考链接<a name="zh-cn_topic_0000001088786546_zh-cn_topic_0263124532_section2800204810402"></a>

社区v1.11与v1.13版本之间的CHANGELOG

-   v1.12到v1.13的变化：

    [https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.13.md](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.13.md)

-   v1.11到v1.12的变化：

    [https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.12.md](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.12.md)


