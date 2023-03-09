# log-agent<a name="cce_10_0416"></a>

## 插件简介<a name="section25311744154917"></a>

log-agent是基于开源fluent-bit和opentelemetry构建的云原生日志采集插件。log-agent支持基于CRD的日志采集策略，可以根据您配置的策略规则，对集群中的容器标准输出日志、容器文件日志、节点日志及K8s事件日志进行采集与转发。

安装log-agent插件后，默认采集容器标准输出日志和集群内 K8s 事件。

log-agent采集日志的详细使用方法请参见[使用log-agent采集容器日志](使用log-agent采集容器日志.md)。

## 约束与限制<a name="section486591843510"></a>

log-agent有如下限制：

-   仅支持1.17及以上版本CCE集群。
-   每个集群限制20条日志规则。
-   不采集.gz .tar .zip后缀类型的日志文件。
-   采集容器文件日志时，若节点存储模式为deviceMapper模式，路径配置必须为节点数据盘挂载路径。
-   若容器运行时为containerd模式，容器标准输出日志中的多行配置暂不生效。

## 安装插件<a name="section186134814119"></a>

1.  登录CCE控制台，单击集群名称进入集群，在左侧导航栏中选择“插件管理“，在右侧找到**log-agent**，单击“安装“。
2.  在安装插件页面，根据需求选择插件规格。
    -   fluent-bit：日志收集器，以DaemonSet形式安装在每个节点。
    -   cop-logs：负责采集侧配置文件生成及更新的组件。
    -   log-operator：负责解析及更新日志规则的组件。
    -   otel-collector：负责集中式日志转发的组件，将fluent-bit收集的日志转发到LTS。

3.  完成参数配置。

    插件默认创建名称为 k8s-log-\{集群 ID\} 的日志组和相关采集日志流，并根据用户配置的采集规则进行日志采集与上报。

    -   默认日志规则：插件默认采集容器标准输出日志和集群内K8s事件，该设置不可自定义。
    -   访问密钥（AK/SK）：访问密钥获取方法请参见[访问密钥](https://support.huaweicloud.com/usermanual-ca/ca_01_0003.html)。

4.  完成以上配置后，单击“安装“。

## 版本记录<a name="section183121449435"></a>

**表 1**  CCE插件版本记录

<a name="table545952314179"></a>
<table><thead align="left"><tr id="row13459112313176"><th class="cellrowborder" valign="top" width="45.391061452513966%" id="mcps1.2.3.1.1"><p id="p206369328181"><a name="p206369328181"></a><a name="p206369328181"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="54.60893854748604%" id="mcps1.2.3.1.2"><p id="p1663653221810"><a name="p1663653221810"></a><a name="p1663653221810"></a>支持的集群版本</p>
</th>
</tr>
</thead>
<tbody><tr id="row174592023121714"><td class="cellrowborder" valign="top" width="45.391061452513966%" headers="mcps1.2.3.1.1 "><p id="p7545102620314"><a name="p7545102620314"></a><a name="p7545102620314"></a>1.2.2</p>
</td>
<td class="cellrowborder" valign="top" width="54.60893854748604%" headers="mcps1.2.3.1.2 "><p id="p82125510466"><a name="p82125510466"></a><a name="p82125510466"></a>/v1.17.*|v1.19.*|v1.21.*|v1.23.*/</p>
</td>
</tr>
</tbody>
</table>

