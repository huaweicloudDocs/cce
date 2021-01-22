# p2paddon<a name="cce_01_0065"></a>

P2P插件用于加速镜像下载的p2p镜像下载服务插件。

-   [什么是P2P镜像分发](#section2108141723819)
-   [约束与限制](#section760916919226)
-   [使用推荐](#section1666222134117)
-   [安装插件](#section168262264114)
-   [升级插件](#section23441939916)
-   [卸载插件](#section941314272594)
-   [版本记录](#section144262219109)

## 什么是P2P镜像分发<a name="section2108141723819"></a>

在使用Docker运行容器时，宿主机通常先要从Registry服务（如Docker Hub）下载镜像。当大量主机需要同时从Registry下载镜像运行容器应用时（比如发布新版本等情形），Registry服务往往会成为镜像分发的瓶颈，镜像需要较长时间才能传送到所有主机上，使得应用发布的周期大大延长。

针对这种瓶颈，有用户采取了下载镜像的方法，使各节点事先分批获取镜像，然后在预定时刻统一启动应用。这种办法在一定程度上缓解了问题，但实质上并没有解决Registry分发的瓶颈。

为解决此瓶颈，SWR容器镜像服务设计了一种利用P2P协议来加速镜像分发的插件，其主要思路是允许在集群的node之间共享镜像，形成分布式的P2P下载网络，提高网络吞吐量。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>此插件安装时会重启Docker，请谨慎使用。

## 约束与限制<a name="section760916919226"></a>

仅支持在1.13及以下版本的集群中安装本插件。

## 使用推荐<a name="section1666222134117"></a>

推荐集群中节点规模超过50个节点时使用。

## 安装插件<a name="section168262264114"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签下，单击**p2paddon**下的“安装插件“。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  镜像分发插件暂未开放可配置参数，直接单击“安装“。

    待插件安装完成后，单击“返回“，在“插件实例“页签下可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装，新增节点时插件会自动安装。

    您可以正常创建工作负载，在拉取镜像时会更快速。


## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“p2paddon“下的“ 升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“p2paddon“插件时，会替换原先节点上的旧版本的“p2paddon“插件，安装最新版本的“p2paddon“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  单击“升级“即可升级“p2paddon“插件。

## 卸载插件<a name="section941314272594"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签下，选择对应的集群，单击**p2paddon**下的“卸载“。
2.  在弹出的窗口中，单击“是“，可卸载该插件。

## 版本记录<a name="section144262219109"></a>

**表 1**  p2paddon版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="24%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row152684214528"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p81363344546"><a name="p81363344546"></a><a name="p81363344546"></a>1.0.6</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p7136634195411"><a name="p7136634195411"></a><a name="p7136634195411"></a>混合集群 v1.9.*|v1.11.*|v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1213616344544"><a name="p1213616344544"></a><a name="p1213616344544"></a>2020/02/12</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p32491411121010"><a name="p32491411121010"></a><a name="p32491411121010"></a>修复插件运行过程中异常退出</p>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p17136034145420"><a name="p17136034145420"></a><a name="p17136034145420"></a>1.0.5</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p12136153411542"><a name="p12136153411542"></a><a name="p12136153411542"></a>混合集群 v1.9.*|v1.11.*|v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p13136183475410"><a name="p13136183475410"></a><a name="p13136183475410"></a>2020/02/12</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p5250101115109"><a name="p5250101115109"></a><a name="p5250101115109"></a>修复插件运行过程中异常退出</p>
</td>
</tr>
<tr id="row97875912317"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p1613733411544"><a name="p1613733411544"></a><a name="p1613733411544"></a>1.0.4</p>
</td>
<td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.5.1.2 "><p id="p1513763485416"><a name="p1513763485416"></a><a name="p1513763485416"></a>混合集群 v1.9.*|v1.11.*|v1.13.*</p>
<p id="p1713773415410"><a name="p1713773415410"></a><a name="p1713773415410"></a>鲲鹏集群 v1.13.*</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p113763425412"><a name="p113763425412"></a><a name="p113763425412"></a>2020/02/12</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p172512116106"><a name="p172512116106"></a><a name="p172512116106"></a>修复插件运行过程中异常退出</p>
</td>
</tr>
</tbody>
</table>

