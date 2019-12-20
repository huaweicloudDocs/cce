# prometheus<a name="cce_01_0221"></a>

## 插件简介<a name="section173631312185614"></a>

Prometheus是一套开源的系统监控报警框架。它启发于Google的borgmon监控系统，由工作在SoundCloud的google前员工在2012年创建，作为社区开源项目进行开发，并于2015年正式发布。2016年，Prometheus正式加入Cloud Native Computing Foundation，成为受欢迎度仅次于Kubernetes的项目。

在云容器引擎CCE中，支持以插件的方式快捷安装Prometheus。

作为新一代的监控框架，Prometheus具有以下特点：

-   强大的多维度数据模型：
    1.  时间序列数据通过metric名和键值对来区分。
    2.  所有的metrics都可以设置任意的多维标签。
    3.  数据模型更随意，不需要刻意设置为以点分隔的字符串。
    4.  可以对数据模型进行聚合，切割和切片操作。
    5.  支持双精度浮点类型，标签可以设为全unicode。


-   灵活而强大的查询语句（PromQL）：在同一个查询语句，可以对多个metrics进行乘法、加法、连接、取分数位等操作。
-   易于管理：Prometheus server是一个单独的二进制文件，可直接在本地工作，不依赖于分布式存储。
-   高效：平均每个采样点仅占 3.5 bytes，且一个Prometheus server可以处理数百万的metrics。
-   使用pull模式采集时间序列数据，这样不仅有利于本机测试而且可以避免有问题的服务器推送坏的metrics。
-   可以采用push gateway的方式把时间序列数据推送至Prometheus server端。
-   可以通过服务发现或者静态配置去获取监控的targets。
-   有多种可视化图形界面。
-   易于伸缩。

需要指出的是，由于数据采集可能会有丢失，所以Prometheus不适用对采集数据要100%准确的情形。但如果用于记录时间序列数据，Prometheus具有很大的查询优势，此外，Prometheus适用于微服务的体系架构。

## 使用约束<a name="section11172124718374"></a>

仅在1.13以上版本的混合集群和裸金属集群中支持此插件功能。

## 安装插件<a name="section189463341114"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“页签中，单击**Prometheus**下的“安装插件“按钮。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置“。
3.  在“规格配置“步骤中，配置以下参数：

    **表 1**  Prometheus配置参数说明

    <a name="table16321825732"></a>
    <table><thead align="left"><tr id="row173212251235"><th class="cellrowborder" valign="top" width="28.000000000000004%" id="mcps1.2.3.1.1"><p id="p43211725338"><a name="p43211725338"></a><a name="p43211725338"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="72%" id="mcps1.2.3.1.2"><p id="p0322102516320"><a name="p0322102516320"></a><a name="p0322102516320"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row163229255313"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p1232219251339"><a name="p1232219251339"></a><a name="p1232219251339"></a>插件规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p173227259312"><a name="p173227259312"></a><a name="p173227259312"></a>根据业务需求，选择插件的规格，包含如下选项：</p>
    <a name="ul53876450305"></a><a name="ul53876450305"></a><ul id="ul53876450305"><li>演示规格（100容器以内）：适用于体验和功能演示环境，该规模下prometheus占用资源较少，但处理能力有限。建议在集群内容器数目不超过100时使用。</li><li>小规格（2000容器以内）：建议在集群中的容器数目不超过2000时使用。</li><li>中规格（5000容器以内）：建议在集群中的容器数目不超过5000时使用。</li><li>大规格（超过5000容器）：建议集群中容器数目超过5000时使用此规格。</li></ul>
    </td>
    </tr>
    <tr id="row6334727910"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p233592498"><a name="p233592498"></a><a name="p233592498"></a>实例数</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p93701640145120"><a name="p93701640145120"></a><a name="p93701640145120"></a>选择上方插件规格后，显示插件中的实例数，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row111551253912"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p51551451293"><a name="p51551451293"></a><a name="p51551451293"></a>容器</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p1437014065110"><a name="p1437014065110"></a><a name="p1437014065110"></a>选择插件规格后，显示插件容器的CPU和内存配额，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row1535723154615"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p83591731124620"><a name="p83591731124620"></a><a name="p83591731124620"></a>监控数据保留期</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p1736012314462"><a name="p1736012314462"></a><a name="p1736012314462"></a>自定义监控数据需要保留的天数，默认为15天。</p>
    </td>
    </tr>
    <tr id="row133224252315"><td class="cellrowborder" valign="top" width="28.000000000000004%" headers="mcps1.2.3.1.1 "><p id="p23228259314"><a name="p23228259314"></a><a name="p23228259314"></a>存储</p>
    </td>
    <td class="cellrowborder" valign="top" width="72%" headers="mcps1.2.3.1.2 "><p id="p13325193219477"><a name="p13325193219477"></a><a name="p13325193219477"></a>按照界面提示配置如下参数：</p>
    <a name="ul14470191614487"></a><a name="ul14470191614487"></a><ul id="ul14470191614487"><li>类型：支持云硬盘。</li><li>可用区：请根据业务需要进行选择。可用区是在同一区域下，电力、网络隔离的物理区域，可用区之间内网互通，不同可用区之间物理隔离。</li><li>子类型：支持普通IO、高IO和超高IO三种类型。各类型对比请参见<a href="重置节点.md#li17544101419177">系统盘和数据盘</a>。</li><li>容量：请根据业务需要输入存储容量，默认10G。</li></ul>
    <div class="note" id="note132861729114815"><a name="note132861729114815"></a><a name="note132861729114815"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1328618298481"><a name="p1328618298481"></a><a name="p1328618298481"></a>若命名空间monitoring下已存在pvc，将使用此存储作为存储源。</p>
    </div></div>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“安装“。

    待插件安装完成后，单击“返回插件管理“，在“插件实例“页签中，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群的各节点中安装。

5.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例”中，点击“Prometheus”进入详情页，可以查看插件实例的详细情况。

## 卸载插件<a name="section1395073191112"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签中，选择对应的集群，单击**Prometheus**下的“卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

## 参考资源<a name="section16331426191116"></a>

-   Prometheus 概念及详细配置请参阅  [Prometheus 官方文档](https://prometheus.io/docs/introduction/overview/)
-   Node exporter 安装请参考  [node\_exporter github 仓库](https://github.com/prometheus/node_exporter)
-   Slack 信息发送请参考  [Incoming Webhooks](https://api.slack.com/incoming-webhooks)

