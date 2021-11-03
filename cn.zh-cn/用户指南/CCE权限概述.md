# CCE权限概述<a name="cce_01_0187"></a>

CCE权限管理是在统一身份认证服务（IAM）与Kubernetes的角色访问控制（RBAC）的能力基础上，打造的细粒度权限管理功能，支持基于IAM的细粒度权限控制和IAM Token认证，支持集群级别、命名空间级别的权限控制，帮助用户便捷灵活的对租户下的IAM用户、用户组设定不同的操作权限。

如果您需要对华为云上购买的CCE集群及相关资源进行精细的权限管理，例如限制不同部门的员工拥有部门内资源的细粒度权限，您可以使用CCE权限管理提供的增强能力进行多维度的权限管理。

本章节将介绍CCE权限管理机制及其涉及到的基本概念。如果当前华为云帐号已经能满足您的要求，您可以跳过本章节，不影响您使用CCE服务的其它功能。

## CCE支持的权限管理能力<a name="section3911182131810"></a>

CCE的权限管理包括“集群权限”和“命名空间权限”两种能力，能够从集群和命名空间层面对用户组或用户进行细粒度授权，具体解释如下：

-   **[集群权限](集群权限（IAM授权）.md)：**是基于IAM系统策略的授权，可以通过用户组功能实现IAM用户的授权。用户组是用户的集合，通过集群权限设置可以让某些用户组操作集群（如创建/删除集群、节点、节点池、模板、插件等），而让某些用户组仅能查看集群。

    集群权限涉及CCE非Kubernetes API，支持IAM细粒度策略、企业项目管理相关能力。

-   **[命名空间权限](命名空间权限（Kubernetes-RBAC授权）.md)：**是基于Kubernetes RBAC（Role-Based Access Control，基于角色的访问控制）能力的授权，通过权限设置可以让不同的用户或用户组拥有操作不同Kubernetes资源的权限。同时CCE基于开源能力进行了增强，可以支持基于IAM用户或用户组粒度进行RBAC授权、IAM token直接访问API进行RBAC认证鉴权。

    命名空间权限涉及CCE Kubernetes API，基于Kubernetes RBAC能力进行增强，支持对接IAM用户/用户组进行授权和认证鉴权，但与IAM细粒度策略独立。

    CCE从v1.11.7-r2版本起的集群支持配置命名空间权限，1.11.7-r2之前的版本默认拥有全部命名空间权限。


CCE的权限可以从使用的阶段分为两个阶段来看，第一个阶段是创建和管理集群的权限，也就是拥有创建/删除集群、节点等资源的权限。第二个阶段是使用集群Kubernetes资源（如工作负载、Service等）的权限。

**图 1**  权限示例图<a name="fig11818185173613"></a>  
![](figures/权限示例图.png "权限示例图")

清楚了集群权限和命名空间权限后，您就可以通过这两步授权，做到精细化的权限控制。

## 集群权限（IAM授权）与命名空间权限（Kubernetes RBAC授权）的关系<a name="section1464135853519"></a>

拥有不同集群权限（IAM授权）的用户，其拥有的命名空间权限（Kubernetes RBAC授权）不同。[表1](#table886210176509)给出了不同用户拥有的命名空间权限详情。

**表 1**  不同用户拥有的命名空间权限

<a name="table886210176509"></a>
<table><thead align="left"><tr id="row14863201719502"><th class="cellrowborder" valign="top" width="31.91752577319587%" id="mcps1.2.4.1.1"><p id="p14863111718502"><a name="p14863111718502"></a><a name="p14863111718502"></a>用户类型</p>
</th>
<th class="cellrowborder" valign="top" width="31.422680412371136%" id="mcps1.2.4.1.2"><p id="p18636175506"><a name="p18636175506"></a><a name="p18636175506"></a>1.11.7-r2以下版本的集群</p>
</th>
<th class="cellrowborder" valign="top" width="36.65979381443299%" id="mcps1.2.4.1.3"><p id="p10295153183913"><a name="p10295153183913"></a><a name="p10295153183913"></a>1.13及以上版本的集群</p>
</th>
</tr>
</thead>
<tbody><tr id="row138631617185012"><td class="cellrowborder" valign="top" width="31.91752577319587%" headers="mcps1.2.4.1.1 "><p id="p1787744075015"><a name="p1787744075015"></a><a name="p1787744075015"></a>拥有Tenant Administrator权限的用户（例如华为云账号）</p>
</td>
<td class="cellrowborder" valign="top" width="31.422680412371136%" headers="mcps1.2.4.1.2 "><p id="p14863717165019"><a name="p14863717165019"></a><a name="p14863717165019"></a>全部命名空间权限</p>
</td>
<td class="cellrowborder" valign="top" width="36.65979381443299%" headers="mcps1.2.4.1.3 "><p id="p1829523133913"><a name="p1829523133913"></a><a name="p1829523133913"></a>全部命名空间权限</p>
</td>
</tr>
<tr id="row138631317205019"><td class="cellrowborder" valign="top" width="31.91752577319587%" headers="mcps1.2.4.1.1 "><p id="p3878104075018"><a name="p3878104075018"></a><a name="p3878104075018"></a>拥有CCE Administrator权限的IAM用户</p>
</td>
<td class="cellrowborder" valign="top" width="31.422680412371136%" headers="mcps1.2.4.1.2 "><p id="p270032114512"><a name="p270032114512"></a><a name="p270032114512"></a>全部命名空间权限</p>
</td>
<td class="cellrowborder" valign="top" width="36.65979381443299%" headers="mcps1.2.4.1.3 "><p id="p172951435393"><a name="p172951435393"></a><a name="p172951435393"></a>全部命名空间权限</p>
</td>
</tr>
<tr id="row1386412176506"><td class="cellrowborder" valign="top" width="31.91752577319587%" headers="mcps1.2.4.1.1 "><p id="p187854025013"><a name="p187854025013"></a><a name="p187854025013"></a>拥有CCE&nbsp;FullAccess或者CCE&nbsp;ReadOnlyAccess权限的IAM用户</p>
</td>
<td class="cellrowborder" valign="top" width="31.422680412371136%" headers="mcps1.2.4.1.2 "><p id="p12703172316516"><a name="p12703172316516"></a><a name="p12703172316516"></a>全部命名空间权限</p>
</td>
<td class="cellrowborder" valign="top" width="36.65979381443299%" headers="mcps1.2.4.1.3 "><p id="p7321956194312"><a name="p7321956194312"></a><a name="p7321956194312"></a>按Kubernetes RBAC授权</p>
</td>
</tr>
<tr id="row28641117145019"><td class="cellrowborder" valign="top" width="31.91752577319587%" headers="mcps1.2.4.1.1 "><p id="p11879440195014"><a name="p11879440195014"></a><a name="p11879440195014"></a>拥有Tenant Guest权限的IAM用户</p>
</td>
<td class="cellrowborder" valign="top" width="31.422680412371136%" headers="mcps1.2.4.1.2 "><p id="p1490645915120"><a name="p1490645915120"></a><a name="p1490645915120"></a>全部命名空间权限</p>
</td>
<td class="cellrowborder" valign="top" width="36.65979381443299%" headers="mcps1.2.4.1.3 "><p id="p1932115664317"><a name="p1932115664317"></a><a name="p1932115664317"></a>按Kubernetes RBAC授权</p>
</td>
</tr>
</tbody>
</table>

## kubectl权限说明<a name="section118521730124516"></a>

您可以通过[kubectl访问集群](通过kubectl连接集群.md)的Kubernetes资源，那kubectl拥有哪些Kubernetes资源的权限呢？

kubectl访问CCE集群是通过集群上生成的配置文件（kubeconfig.json）进行认证，kubeconfig.json文件内包含用户信息，CCE根据用户信息的权限判断kubectl有权限访问哪些Kubernetes资源。即哪个用户获取的kubeconfig.json文件，kubeconfig.json就拥有哪个用户的信息，这样使用kubectl访问时就拥有这个用户的权限。而用户拥有的权限就是[表1](#table886210176509)所示的权限。

