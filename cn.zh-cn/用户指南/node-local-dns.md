# node-local-dns<a name="cce_10_0404"></a>

## 插件简介<a name="section25311744154917"></a>

NodeLocal DNSCache通过在集群节点上作为守护程序集运行DNS缓存代理，提高集群DNS性能。

开源社区地址：[https://github.com/kubernetes/dns](https://github.com/kubernetes/dns)

**图 1**  NodeLocal DNSCache查询路径<a name="fig36421622164815"></a>  
![](figures/NodeLocal-DNSCache查询路径-9.png "NodeLocal-DNSCache查询路径-9")

## 约束与限制<a name="section10849134521812"></a>

-   仅支持1.19及以上版本集群。

## 安装插件<a name="section186134814119"></a>

1.  登录CCE控制台，单击集群名称进入集群，在左侧导航栏中选择“插件管理“，在右侧找到**node-local-dns**，单击“安装“。
2.  在安装插件页面，选择插件规格，并配置相关参数。

    **规格配置**

    -   实例数：选择自定义规格时，请根据业务需求选择合适的实例数。
    -   容器：选择自定义规格时，请根据业务需求选择合适的容器配额。

    **参数配置**

    -   启用DNS config注入：启用DNS Config注入功能可以自动将node-local-dns地址注入到新建的 pod 中，无需手动注入。开启该功能后，将会创建node-local-dns-admission-controller容器以提供自动注入功能，不开启则不会创建该容器。

3.  完成以上配置后，单击“安装“。

## 相关链接<a name="section342243017471"></a>

[使用NodeLocal DNSCache提升DNS性能](使用NodeLocal-DNSCache提升DNS性能.md)

## 版本记录<a name="section183121449435"></a>

**表 1**  CCE插件版本记录

<a name="table88489551792"></a>
<table><thead align="left"><tr id="row139251455994"><th class="cellrowborder" valign="top" width="33.525061626951526%" id="mcps1.2.4.1.1"><p id="p13601510205420"><a name="p13601510205420"></a><a name="p13601510205420"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="34.470008216926864%" id="mcps1.2.4.1.2"><p id="p156011107542"><a name="p156011107542"></a><a name="p156011107542"></a>支持的集群版本</p>
</th>
<th class="cellrowborder" valign="top" width="32.00493015612161%" id="mcps1.2.4.1.3"><p id="p10989641123817"><a name="p10989641123817"></a><a name="p10989641123817"></a>社区版本（仅1.17及以上版本集群支持）</p>
</th>
</tr>
</thead>
<tbody><tr id="row202451645914"><td class="cellrowborder" valign="top" width="33.525061626951526%" headers="mcps1.2.4.1.1 "><p id="p4186672914"><a name="p4186672914"></a><a name="p4186672914"></a>1.2.4</p>
</td>
<td class="cellrowborder" valign="top" width="34.470008216926864%" headers="mcps1.2.4.1.2 "><p id="p161867713919"><a name="p161867713919"></a><a name="p161867713919"></a>/v1.(19|21|23|25).*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.00493015612161%" headers="mcps1.2.4.1.3 "><p id="p17015199915"><a name="p17015199915"></a><a name="p17015199915"></a>1.21.1</p>
</td>
</tr>
<tr id="row8757710175517"><td class="cellrowborder" valign="top" width="33.525061626951526%" headers="mcps1.2.4.1.1 "><p id="p14191153825616"><a name="p14191153825616"></a><a name="p14191153825616"></a>1.2.2</p>
</td>
<td class="cellrowborder" valign="top" width="34.470008216926864%" headers="mcps1.2.4.1.2 "><p id="p165917162594"><a name="p165917162594"></a><a name="p165917162594"></a>/v1.(19|21|23).*/</p>
</td>
<td class="cellrowborder" valign="top" width="32.00493015612161%" headers="mcps1.2.4.1.3 "><p id="p11951944124016"><a name="p11951944124016"></a><a name="p11951944124016"></a>1.21.1</p>
</td>
</tr>
</tbody>
</table>

