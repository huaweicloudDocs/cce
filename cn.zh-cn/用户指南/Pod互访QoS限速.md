# Pod互访QoS限速<a name="cce_10_0382"></a>

## 操作场景<a name="section1329214638"></a>

部署在同一节点上的不同业务容器之间存在带宽抢占，容易造成业务抖动。您可以通过对Pod间互访进行QoS限速来解决这个问题。

## 约束与限制<a name="section58481435943"></a>

Pod互访限速设置需遵循以下约束：

<a name="table197051355175516"></a>
<table><thead align="left"><tr id="row1273055511557"><th class="cellrowborder" valign="top" width="10%" id="mcps1.1.5.1.1"><p id="p173005585516"><a name="p173005585516"></a><a name="p173005585516"></a>约束类别</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.1.5.1.2"><p id="p8730655195520"><a name="p8730655195520"></a><a name="p8730655195520"></a>容器隧道网络模式</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.1.5.1.3"><p id="p973015565513"><a name="p973015565513"></a><a name="p973015565513"></a>VPC网络模式</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.1.5.1.4"><p id="p37308556559"><a name="p37308556559"></a><a name="p37308556559"></a>云原生2.0网络模式</p>
</th>
</tr>
</thead>
<tbody><tr id="row1173015518558"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.1.5.1.1 "><p id="p1173055517557"><a name="p1173055517557"></a><a name="p1173055517557"></a>支持的版本</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.2 "><p id="p6730255125520"><a name="p6730255125520"></a><a name="p6730255125520"></a>所有版本都支持</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.3 "><p id="p20731195516552"><a name="p20731195516552"></a><a name="p20731195516552"></a>v1.19.10以上集群版本</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.4 "><p id="p473105517551"><a name="p473105517551"></a><a name="p473105517551"></a>v1.19.10以上集群版本</p>
</td>
</tr>
<tr id="row10731145525520"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.1.5.1.1 "><p id="p18731135505515"><a name="p18731135505515"></a><a name="p18731135505515"></a>支持的运行时类型</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.2 "><p id="p137317550553"><a name="p137317550553"></a><a name="p137317550553"></a>仅支持普通容器（容器运行时为runC）</p>
<p id="p373116556552"><a name="p373116556552"></a><a name="p373116556552"></a>容器隧道网络模式不支持安全容器</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.3 "><p id="p1562810461471"><a name="p1562810461471"></a><a name="p1562810461471"></a>仅支持普通容器（容器运行时为runC）</p>
<p id="p3731185515517"><a name="p3731185515517"></a><a name="p3731185515517"></a>不支持安全容器（容器运行时为Kata）</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.4 "><p id="p18651124817712"><a name="p18651124817712"></a><a name="p18651124817712"></a>仅支持普通容器（容器运行时为runC）</p>
<p id="p20731105585510"><a name="p20731105585510"></a><a name="p20731105585510"></a>不支持安全容器（容器运行时为Kata）</p>
</td>
</tr>
<tr id="row8268101012419"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p1268171012419"><a name="p1268171012419"></a><a name="p1268171012419"></a>支持的Pod类型</p>
</td>
<td class="cellrowborder" colspan="3" valign="top" headers="mcps1.1.5.1.2 mcps1.1.5.1.3 mcps1.1.5.1.4 "><p id="p13359142116418"><a name="p13359142116418"></a><a name="p13359142116418"></a>仅支持非<a href="主机网络hostNetwork.md">HostNetwork</a>类型Pod</p>
</td>
</tr>
<tr id="row10731165535520"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p18731125545511"><a name="p18731125545511"></a><a name="p18731125545511"></a>支持的场景</p>
</td>
<td class="cellrowborder" colspan="3" valign="top" headers="mcps1.1.5.1.2 mcps1.1.5.1.3 mcps1.1.5.1.4 "><p id="p117751937538"><a name="p117751937538"></a><a name="p117751937538"></a>支持Pod间互访、Pod访问Node、Pod访问Service的场景限速</p>
</td>
</tr>
<tr id="row47311555115519"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.1.5.1.1 "><p id="p97311655115519"><a name="p97311655115519"></a><a name="p97311655115519"></a>限制的场景</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.2 "><p id="p124892011558"><a name="p124892011558"></a><a name="p124892011558"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.3 "><p id="p11658161112518"><a name="p11658161112518"></a><a name="p11658161112518"></a>无</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.4 "><a name="ul19731455115513"></a><a name="ul19731455115513"></a><ul id="ul19731455115513"><li>不支持Pod访问100.64.0.0/10和214.0.0.0/8外部云服务网段的限速场景</li><li>不支持健康检查的流量限速场景</li></ul>
</td>
</tr>
<tr id="row18731135518554"><td class="cellrowborder" valign="top" width="10%" headers="mcps1.1.5.1.1 "><p id="p7731055105510"><a name="p7731055105510"></a><a name="p7731055105510"></a>限速值上限</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.2 "><p id="p5731555105516"><a name="p5731555105516"></a><a name="p5731555105516"></a>机型带宽上限和34G两者之间的最小值</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.3 "><p id="p6731155155520"><a name="p6731155155520"></a><a name="p6731155155520"></a>机型带宽上限和4.3G两者之间的最小值</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.5.1.4 "><p id="p1731105585514"><a name="p1731105585514"></a><a name="p1731105585514"></a>机型带宽上限和4.3G两者之间的最小值</p>
</td>
</tr>
<tr id="row2073145595517"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p673111558550"><a name="p673111558550"></a><a name="p673111558550"></a>限速值下限</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p673114554557"><a name="p673114554557"></a><a name="p673114554557"></a>大于0</p>
</td>
<td class="cellrowborder" colspan="2" valign="top" headers="mcps1.1.5.1.3 mcps1.1.5.1.4 "><p id="p2731195575512"><a name="p2731195575512"></a><a name="p2731195575512"></a>目前仅支持兆（M）级别以上的限速</p>
</td>
</tr>
</tbody>
</table>

## 通过kubectl命令行设置<a name="section069116421443"></a>

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

