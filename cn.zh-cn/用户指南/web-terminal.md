# web-terminal<a name="cce_10_0134"></a>

web-terminal是一款非常轻巧的终端服务器，支持在Web界面上使用Kubectl命令。它支持通过标准的Web浏览器和HTTP协议提供远程CLI，提供灵活的接口便于集成到独立系统中，可直接作为一个服务连接，通过cmdb获取信息并登录服务器。

web-terminal可以在Node.js支持的所有操作系统上运行，而不依赖于本机模块，快速且易于安装，支持多会话。

开源社区地址：[https://github.com/rabchev/web-terminal](https://github.com/rabchev/web-terminal)

## 约束与限制<a name="section628693291119"></a>

-   仅支持在1.21及以下版本的集群中安装此插件，暂不支持ARM集群。
-   web-terminal插件当前版本处于beta阶段中，后续将使用cloudshell方案代替，请根据实际场景选择体验。
-   web-terminal中kubectl具有高级别操作权限，限帐号以及具有CCE Administrator权限的IAM用户安装此插件，如需收缩插件中kubectl权限，请参见[收缩web-terminal权限](#section62000142412)操作。
-   集群必须安装CoreDNS才能使用web-terminal。

## 注意事项<a name="section1357919311966"></a>

web-terminal插件能够对CCE集群进行管理，请用户妥善保管好登录密码，避免密码泄漏造成损失。

## 安装插件<a name="section41861311141210"></a>

1.  登录CCE控制台，单击集群名称进入集群，单击左侧导航栏的“ 插件管理“，在右侧找到**web-terminal**，单击“安装“。
2.  配置以下参数。
    -   访问类型：固定为节点访问，该插件默认以NodePort形式提供访问，需为集群任意一个节点绑定弹性IP才能使用。若集群没有绑定弹性IP，需绑定弹性IP。
    -   用户名：默认为root，不可修改。
    -   密码：登录web-terminal的密码，请务必记住该密码。web-terminal插件能够对CCE集群进行管理，请用户妥善保管好登录密码，避免密码泄漏造成损失。
    -   确认密码：重新准确输入该密码。

3.  单击“安装“。

## 使用web-terminal插件连接集群<a name="section115151890220"></a>

1.  登录CCE控制台，单击集群名称进入集群，单击左侧导航栏的“插件管理“。
2.  在右侧找到web-terminal，单击“访问“。

## 收缩web-terminal权限<a name="section62000142412"></a>

web-terminal插件安装后，其kubectl默认使用cluster-admin ClusterRole权限，能够操作该集群K8s资源，若需手动配置为其他类型权限，可通过kubectl edit clusterrolebinding web-terminal修改web-terminal ServiceAccount绑定其他权限的ClusterRole。

ClusterRole、ClusterRoleBinding相关配置说明请参见[命名空间权限（Kubernetes RBAC授权）](命名空间权限（Kubernetes-RBAC授权）.md)。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>-   手动配置的web-terminal权限在web-terminal插件升级时存在被重置风险，需注意做好备份在插件升级后重新配置。
>-   使用kubectl修改clusterrolebinding配置需确保当前kubectl有修改clusterrolebinding资源操作权限。

## 版本记录<a name="section183121449435"></a>

**表 1**  CCE插件版本记录

<a name="table545952314179"></a>
<table><thead align="left"><tr id="row13459112313176"><th class="cellrowborder" valign="top" width="26.697353279631752%" id="mcps1.2.4.1.1"><p id="p206369328181"><a name="p206369328181"></a><a name="p206369328181"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="34.94438051400076%" id="mcps1.2.4.1.2"><p id="p1663653221810"><a name="p1663653221810"></a><a name="p1663653221810"></a>支持的集群版本</p>
</th>
<th class="cellrowborder" valign="top" width="38.35826620636747%" id="mcps1.2.4.1.3"><p id="p445992311174"><a name="p445992311174"></a><a name="p445992311174"></a>社区版本（仅1.17及以上版本集群支持）</p>
</th>
</tr>
</thead>
<tbody><tr id="row174592023121714"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p1182674212811"><a name="p1182674212811"></a><a name="p1182674212811"></a>1.1.12</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p58261742132811"><a name="p58261742132811"></a><a name="p58261742132811"></a>/v1.(15|17|19|21).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p1989010143288"><a name="p1989010143288"></a><a name="p1989010143288"></a><a href="https://github.com/rabchev/web-terminal/releases/tag/0.6.6" target="_blank" rel="noopener noreferrer">0.6.6</a></p>
</td>
</tr>
<tr id="row10459723151716"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p8827042142810"><a name="p8827042142810"></a><a name="p8827042142810"></a>1.1.6</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p382754216287"><a name="p382754216287"></a><a name="p382754216287"></a>/v1.(15|17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p1589015146289"><a name="p1589015146289"></a><a name="p1589015146289"></a><a href="https://github.com/rabchev/web-terminal/releases/tag/0.6.6" target="_blank" rel="noopener noreferrer">0.6.6</a></p>
</td>
</tr>
<tr id="row3459112341718"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p16827842202812"><a name="p16827842202812"></a><a name="p16827842202812"></a>1.1.5</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p11827942102817"><a name="p11827942102817"></a><a name="p11827942102817"></a>/v1.(15|17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p19890181492816"><a name="p19890181492816"></a><a name="p19890181492816"></a><a href="https://github.com/rabchev/web-terminal/releases/tag/0.6.6" target="_blank" rel="noopener noreferrer">0.6.6</a></p>
</td>
</tr>
<tr id="row114591523181710"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p68271342112814"><a name="p68271342112814"></a><a name="p68271342112814"></a>1.1.3</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p882794252818"><a name="p882794252818"></a><a name="p882794252818"></a>/v1.(17|19).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p2890514132814"><a name="p2890514132814"></a><a name="p2890514132814"></a><a href="https://github.com/rabchev/web-terminal/releases/tag/0.6.6" target="_blank" rel="noopener noreferrer">0.6.6</a></p>
</td>
</tr>
<tr id="row646042319177"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p182724292819"><a name="p182724292819"></a><a name="p182724292819"></a>1.0.6</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p2827164262813"><a name="p2827164262813"></a><a name="p2827164262813"></a>/v1.(15|17).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p1289011147289"><a name="p1289011147289"></a><a name="p1289011147289"></a><a href="https://github.com/rabchev/web-terminal/releases/tag/0.6.6" target="_blank" rel="noopener noreferrer">0.6.6</a></p>
</td>
</tr>
<tr id="row13757134401715"><td class="cellrowborder" valign="top" width="26.697353279631752%" headers="mcps1.2.4.1.1 "><p id="p8827242122811"><a name="p8827242122811"></a><a name="p8827242122811"></a>1.0.5</p>
</td>
<td class="cellrowborder" valign="top" width="34.94438051400076%" headers="mcps1.2.4.1.2 "><p id="p5827184222810"><a name="p5827184222810"></a><a name="p5827184222810"></a>/v1.(9|11|13|15|17).*/</p>
</td>
<td class="cellrowborder" valign="top" width="38.35826620636747%" headers="mcps1.2.4.1.3 "><p id="p989010146280"><a name="p989010146280"></a><a name="p989010146280"></a><a href="https://github.com/rabchev/web-terminal/releases/tag/0.6.6" target="_blank" rel="noopener noreferrer">0.6.6</a></p>
</td>
</tr>
</tbody>
</table>

