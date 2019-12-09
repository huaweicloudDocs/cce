# kubernetes RBAC授权（命名空间权限）<a name="cce_01_0167"></a>

Kubernetes RBAC API定义了四种类型：Role、ClusterRole、RoleBinding与ClusterRoleBinding，这四种类型之间的关系和简要说明如下：

-   **Role和ClusterRole：**描述角色和权限的关系。在Kubernetes的RBAC API中，一个角色定义了一组特定权限的规则。命名空间范围内的角色由Role对象定义，而整个Kubernetes集群范围内有效的角色则通过ClusterRole对象实现。
-   **RoleBinding和ClusterRoleBinding：**描述 subjects （包含users, groups, service accounts）和 角色的关系。角色绑定将一个角色中定义的各种权限授予一个或者一组用户，则该用户或用户组则具有对应绑定的Role或ClusterRole定义的权限。

**表 1**  RBAC API所定义的四种类型

<a name="table7143142111614"></a>
<table><thead align="left"><tr id="row1914410211164"><th class="cellrowborder" valign="top" width="30.620000000000005%" id="mcps1.2.3.1.1"><p id="p614452101611"><a name="p614452101611"></a><a name="p614452101611"></a>类型名称</p>
</th>
<th class="cellrowborder" valign="top" width="69.38%" id="mcps1.2.3.1.2"><p id="p12144622163"><a name="p12144622163"></a><a name="p12144622163"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1014417217164"><td class="cellrowborder" valign="top" width="30.620000000000005%" headers="mcps1.2.3.1.1 "><p id="p153732040131712"><a name="p153732040131712"></a><a name="p153732040131712"></a>Role</p>
</td>
<td class="cellrowborder" valign="top" width="69.38%" headers="mcps1.2.3.1.2 "><p id="p714414221614"><a name="p714414221614"></a><a name="p714414221614"></a>Role对象只能用于授予对某一namespace中资源的访问权限。</p>
</td>
</tr>
<tr id="row2014418219161"><td class="cellrowborder" valign="top" width="30.620000000000005%" headers="mcps1.2.3.1.1 "><p id="p4498748131713"><a name="p4498748131713"></a><a name="p4498748131713"></a>ClusterRole</p>
</td>
<td class="cellrowborder" valign="top" width="69.38%" headers="mcps1.2.3.1.2 "><p id="p176330155212"><a name="p176330155212"></a><a name="p176330155212"></a>ClusterRole对象可以授予整个集群范围内资源访问权限， 也可以对以下几种资源的授予访问权限：</p>
<a name="ul11279114152116"></a><a name="ul11279114152116"></a><ul id="ul11279114152116"><li>集群范围资源（例如节点，即node）。</li><li>非资源类型endpoint（例如”/healthz”）。</li><li>跨所有namespaces的范围资源（例如pod，需要运行命令kubectl get pods --all-namespaces来查询集群中所有的pod)。</li></ul>
</td>
</tr>
<tr id="row16145329168"><td class="cellrowborder" valign="top" width="30.620000000000005%" headers="mcps1.2.3.1.1 "><p id="p13145527161"><a name="p13145527161"></a><a name="p13145527161"></a>RoleBinding</p>
</td>
<td class="cellrowborder" valign="top" width="69.38%" headers="mcps1.2.3.1.2 "><p id="p1214572201610"><a name="p1214572201610"></a><a name="p1214572201610"></a>RoleBinding可以将同一namespace中的subject（用户）绑定到某个具有特定权限的Role下，则此subject即具有该Role定义的权限。</p>
</td>
</tr>
<tr id="row121452211165"><td class="cellrowborder" valign="top" width="30.620000000000005%" headers="mcps1.2.3.1.1 "><p id="p81450211617"><a name="p81450211617"></a><a name="p81450211617"></a>ClusterRoleBinding</p>
</td>
<td class="cellrowborder" valign="top" width="69.38%" headers="mcps1.2.3.1.2 "><p id="p10145525168"><a name="p10145525168"></a><a name="p10145525168"></a>ClusterRoleBinding在整个集群级别和所有namespaces将特定的subject与ClusterRole绑定，授予权限。</p>
</td>
</tr>
</tbody>
</table>

更多Kubernetes RBAC授权的内容可以参考[Kubernetes RBAC官方文档](https://kubernetes.io/docs/admin/authorization/rbac/)。

## CCE命名空间权限<a name="section562824112461"></a>

命名空间权限是基于Kubernetes RBAC能力的授权，通过权限设置可以让不同的用户或用户组拥有操作不同Kubernetes资源的权限。

CCE的kubernetes资源通过命名空间进行权限设置，目前包含**admin**、**edit**、**view**三种角色，详见[表2](#table174765455252)。

**表 2**  用户/用户组角色说明

<a name="table174765455252"></a>
<table><thead align="left"><tr id="row19540194512257"><th class="cellrowborder" valign="top" width="34.300000000000004%" id="mcps1.2.3.1.1"><p id="p1654017455258"><a name="p1654017455258"></a><a name="p1654017455258"></a>默认的ClusterRole</p>
</th>
<th class="cellrowborder" valign="top" width="65.7%" id="mcps1.2.3.1.2"><p id="p0540144517258"><a name="p0540144517258"></a><a name="p0540144517258"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row195412454251"><td class="cellrowborder" valign="top" width="34.300000000000004%" headers="mcps1.2.3.1.1 "><p id="p4541104518251"><a name="p4541104518251"></a><a name="p4541104518251"></a>admin</p>
</td>
<td class="cellrowborder" valign="top" width="65.7%" headers="mcps1.2.3.1.2 "><p id="p154117452251"><a name="p154117452251"></a><a name="p154117452251"></a>允许admin访问，可以限制在一个namespace中使用RoleBinding。如果在RoleBinding中使用，则允许对namespace中大多数资源进行读写访问，其中包含创建角色和角色绑定的能力。这一角色不允许操作namespace本身，也不能写入资源限额。</p>
</td>
</tr>
<tr id="row12541445182514"><td class="cellrowborder" valign="top" width="34.300000000000004%" headers="mcps1.2.3.1.1 "><p id="p55415459252"><a name="p55415459252"></a><a name="p55415459252"></a>edit</p>
</td>
<td class="cellrowborder" valign="top" width="65.7%" headers="mcps1.2.3.1.2 "><p id="p20541545152519"><a name="p20541545152519"></a><a name="p20541545152519"></a>允许对命名空间内的大多数资源进行读写操作，不允许查看或修改角色，以及角色绑定。</p>
</td>
</tr>
<tr id="row15541154516259"><td class="cellrowborder" valign="top" width="34.300000000000004%" headers="mcps1.2.3.1.1 "><p id="p20541194582515"><a name="p20541194582515"></a><a name="p20541194582515"></a>view</p>
</td>
<td class="cellrowborder" valign="top" width="65.7%" headers="mcps1.2.3.1.2 "><p id="p65420455258"><a name="p65420455258"></a><a name="p65420455258"></a>允许对多数对象进行只读操作，但是对角色、角色绑定及secret是不可访问的。</p>
</td>
</tr>
</tbody>
</table>

