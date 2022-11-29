# （停止维护）CCE发布Kubernetes 1.11版本说明<a name="cce_10_0474"></a>

云容器引擎（CCE）严格遵循社区一致性认证。本文介绍CCE发布Kubernetes 1.11版本所做的变更说明。

**表 1**  v1.11版本集群说明

<a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_table7445114645410"></a>
<table><thead align="left"><tr id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_row244694645413"><th class="cellrowborder" valign="top" width="29.03%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p174461846165411"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p174461846165411"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p174461846165411"></a>Kubernetes版本（CCE增强版）</p>
</th>
<th class="cellrowborder" valign="top" width="70.97%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p1446154614545"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p1446154614545"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p1446154614545"></a>版本说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_row2023116441905"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p863710461905"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p863710461905"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p863710461905"></a>v1.11.7-r2</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p17637174616018"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p17637174616018"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p17637174616018"></a><strong id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b897775518242"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b897775518242"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b897775518242"></a>主要特性：</strong></p>
<a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul963719461905"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul963719461905"></a><ul id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul963719461905"><li>GPU支持V100类型</li><li>集群支持权限管理</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_row190113461164"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p15901194614161"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p15901194614161"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p15901194614161"></a>v1.11.7-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p10901164618166"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p10901164618166"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p10901164618166"></a><strong id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b1541155912247"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b1541155912247"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b1541155912247"></a>主要特性：</strong></p>
<a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul1513752874712"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul1513752874712"></a><ul id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul1513752874712"><li>Kubernetes同步社区1.11.7版本</li><li>支持创建节点池（<span>nodepool</span>），虚拟机/鲲鹏ARM集群均支持</li><li>CCE集群支持创建裸金属节点（VPC网络），支持裸金属和虚机混合部署</li><li>GPU支持V100类型</li><li>1.11集群对接AOM告警通知机制</li><li>Service支持访问类型切换</li><li>支持服务网段</li><li>集群支持自定义每个节点分配的IP数（IP分配）</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_row1760182091416"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p15760320151412"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p15760320151412"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p15760320151412"></a>v1.11.3-r2</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p87608204144"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p87608204144"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p87608204144"></a><strong id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b7275114182512"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b7275114182512"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b7275114182512"></a>主要特性：</strong></p>
<a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul184061349161515"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul184061349161515"></a><ul id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul184061349161515"><li>集群支持IPv6双栈</li><li>ELB负载均衡支持源IP跟后端服务会话保持</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_row13751104313019"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p177511443701"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p177511443701"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p177511443701"></a>v1.11.3-r1</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p1775154314015"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p1775154314015"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p1775154314015"></a><strong id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b1522018713253"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b1522018713253"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b1522018713253"></a>主要特性：</strong></p>
<a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul1999017372616"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul1999017372616"></a><ul id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul1999017372616"><li>Ingress的URL匹配支持Perl语法的正则表达式</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_row0226111212582"><td class="cellrowborder" valign="top" width="29.03%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p822671216588"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p822671216588"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p822671216588"></a>v1.11.3-r0</p>
</td>
<td class="cellrowborder" valign="top" width="70.97%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p20226181211581"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p20226181211581"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_p20226181211581"></a><strong id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b38471794255"><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b38471794255"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_b38471794255"></a>主要特性：</strong></p>
<a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul169031946461"></a><a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul169031946461"></a><ul id="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_zh-cn_topic_0261805758_zh-cn_topic_0205664480_ul169031946461"><li>Kubernetes同步社区1.11.3版本</li><li>集群控制节点支持多可用区</li><li>容器存储支持对接SFS Turbo极速文件存储</li></ul>
</td>
</tr>
</tbody>
</table>

## 参考链接<a name="zh-cn_topic_0000001135694053_zh-cn_topic_0263268025_section2800204810402"></a>

社区v1.9与v1.11版本之间的CHANGELOG

-   v1.10到v1.11的变化：

    [https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.11.md](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.11.md)

-   v1.9到v1.10的变化：

    [https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.10.md](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.10.md)


