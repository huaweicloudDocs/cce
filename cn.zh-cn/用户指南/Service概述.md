# Service概述<a name="cce_01_0249"></a>

Service是将运行在一组Pods上的应用程序公开为网络服务的抽象方法。

使用Kubernetes，您无需修改应用程序即可使用不熟悉的服务发现机制。 Kubernetes为Pods提供自己的IP地址和一组Pod的单个DNS名称，并且可以在它们之间进行负载平衡。

Kubernetes允许指定一个需要的类型的Service，类型的取值以及行为如下：

-   [集群内访问\(ClusterIP\)](集群内访问(ClusterIP).md)

    集群内访问表示工作负载暴露给同一集群内其他工作负载访问的方式，可以通过“集群内部域名”访问。


-   [节点访问\(NodePort\)](节点访问(NodePort).md)

    节点访问 \( NodePort \)是指在每个节点的IP上开放一个静态端口，通过静态端口对外暴露服务。节点访问 \( NodePort \)会路由到ClusterIP服务，这个ClusterIP服务会自动创建。通过请求<NodeIP\>:<NodePort\>，可以从集群的外部访问一个NodePort服务。

-   [负载均衡\(LoadBalancer\)](cce_01_0114.md)

    负载均衡\( LoadBalancer \)可以通过弹性负载均衡从公网访问到工作负载，与弹性IP方式相比提供了高可靠的保障，一般用于系统中需要暴露到公网的服务。

-   [DNAT网关\(DNAT\)](DNAT网关(DNAT).md)

    可以为集群节点提供网络地址转换服务，使多个节点可以共享使用弹性IP。与弹性IP方式相比增强了可靠性，弹性IP无需与单个节点绑定，任何节点状态的异常不影响其访问。


## 添加Service<a name="section1150318179359"></a>

若工作负载需要和其它服务互访，或需要被公网访问，您需要添加服务，设置工作负载的访问方式。

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“资源管理 \> 网络管理”，在工作负载列表页单击要设置Service的工作负载名称。
2.  在“Service“页签，单击“添加Service”。
3.  您可根据实际选择工作负载的访问方式，执行对应的操作。
    -   [集群内访问\(ClusterIP\)](集群内访问(ClusterIP).md)
    -   [节点访问\(NodePort\)](节点访问(NodePort).md)
    -   [负载均衡\(LoadBalancer\)](cce_01_0114.md)
    -   [DNAT网关\(DNAT\)](DNAT网关(DNAT).md)


## 删除Service<a name="section5959462326"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“资源管理 \> 网络管理”。
2.  在“Service“页签，勾选服务名称，单击“删除Service”。也可在服务名称后的“操作列”，单击“删除”
3.  在弹出的窗口，单击“是”。

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >-   删除操作无法恢复，请谨慎操作。
    >-   服务关联的自动创建的ELB实例和EIP也会被删除。


## 查看事件<a name="section932032011188"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“资源管理 \> 网络管理”。
2.  在“Service“页签，勾选服务名称，单击“删除Service”。

## 更多操作<a name="section11985163132117"></a>

**表 1**  更多操作

<a name="table1796194117217"></a>
<table><thead align="left"><tr id="row18962104182116"><th class="cellrowborder" valign="top" width="31.900000000000002%" id="mcps1.2.3.1.1"><p id="p19962841142119"><a name="p19962841142119"></a><a name="p19962841142119"></a>操作</p>
</th>
<th class="cellrowborder" valign="top" width="68.10000000000001%" id="mcps1.2.3.1.2"><p id="p15962241132111"><a name="p15962241132111"></a><a name="p15962241132111"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row396244114219"><td class="cellrowborder" valign="top" width="31.900000000000002%" headers="mcps1.2.3.1.1 "><p id="p189624419212"><a name="p189624419212"></a><a name="p189624419212"></a><span>编辑YAML</span></p>
</td>
<td class="cellrowborder" valign="top" width="68.10000000000001%" headers="mcps1.2.3.1.2 "><p id="p99624411219"><a name="p99624411219"></a><a name="p99624411219"></a><span>单击服务名称后的</span><span>“编辑YAML”</span><span>，可查看、修改和下载到当前服务的YAML文件。</span></p>
</td>
</tr>
<tr id="row14962174142113"><td class="cellrowborder" valign="top" width="31.900000000000002%" headers="mcps1.2.3.1.1 "><p id="p9962114112215"><a name="p9962114112215"></a><a name="p9962114112215"></a>更新</p>
</td>
<td class="cellrowborder" valign="top" width="68.10000000000001%" headers="mcps1.2.3.1.2 "><a name="ol435223014297"></a><a name="ol435223014297"></a><ol id="ol435223014297"><li>选择需要更新的服务名称，单击“更新”。</li><li>更改信息后，单击“更新”。</li></ol>
</td>
</tr>
</tbody>
</table>

