# ASM网格版本检查<a name="cce_10_0454"></a>

## 检查项内容<a name="section133971951102318"></a>

当前检查项包括以下内容：

-   检查集群是否使用ASM网格服务
-   检查当前ASM版本是否支持目标集群版本

## 解决方案<a name="section7380405246"></a>

-   先升级对应的ASM网格版本，再进行集群升级，ASM网格版本与集群版本适配规则如下表。

    **表 1**  ASM网格版本与集群版本适配规则

    <a name="table1495413335343"></a>
    <table><thead align="left"><tr id="row17955233113416"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p89551933153417"><a name="p89551933153417"></a><a name="p89551933153417"></a>ASM网格版本</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1495510331349"><a name="p1495510331349"></a><a name="p1495510331349"></a>集群版本</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row0955333193410"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1095593315349"><a name="p1095593315349"></a><a name="p1095593315349"></a>1.3</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p209552337347"><a name="p209552337347"></a><a name="p209552337347"></a>v1.13  v1.15  v1.17  v1.19</p>
    </td>
    </tr>
    <tr id="row1955113363415"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p129557339343"><a name="p129557339343"></a><a name="p129557339343"></a>1.6</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1495510330346"><a name="p1495510330346"></a><a name="p1495510330346"></a>v1.15  v1.17  v1.19  v1.21</p>
    </td>
    </tr>
    <tr id="row189551933183412"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1295514334342"><a name="p1295514334342"></a><a name="p1295514334342"></a>1.8</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p209551333123416"><a name="p209551333123416"></a><a name="p209551333123416"></a>v1.15  v1.17  v1.19  v1.21</p>
    </td>
    </tr>
    <tr id="row12955153393414"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11955153314342"><a name="p11955153314342"></a><a name="p11955153314342"></a>1.13</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p12955143310348"><a name="p12955143310348"></a><a name="p12955143310348"></a>v1.21  v1.23</p>
    </td>
    </tr>
    </tbody>
    </table>


-   若不需要使用ASM网格，可删除ASM网格后再进行升级，升级后集群不能绑定与表中不匹配的ASM网格版本。例如，使用v1.21版本集群与1.8版本ASM网格，若要升级至v1.23版本集群时，请先升级ASM网格至1.13版本后再进行v1.23版本集群升级。

