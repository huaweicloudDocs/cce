# 创建无状态负载\(Deployment\)<a name="cce_10_0047"></a>

## 操作场景<a name="section686591217411"></a>

在运行中始终不保存任何数据或状态的工作负载称为“无状态负载 Deployment”，例如nginx。您可以通过控制台或kubectl命令行创建无状态负载。

## 前提条件<a name="section7271245481"></a>

-   在创建容器工作负载前，您需要存在一个可用集群。若没有可用集群 ，请参照[购买CCE集群](购买CCE集群.md)中内容创建。
-   若工作负载需要被外网访问，请确保集群中至少有一个节点已绑定弹性IP，或已创建负载均衡实例。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >单个实例（Pod）内如果有多个容器，请确保容器使用的端口不冲突 ，否则部署会失败。


## 通过控制台创建<a name="section1996635141916"></a>

1.  登录CCE控制台。
2.  进入集群，在左侧选择“工作负载“，在右上角单击“创建负载“。
3.  配置工作负载的信息。

    **基本信息**

    -   负载类型：选择无状态工作负载Deployment。工作负载类型的介绍请参见[工作负载概述](工作负载概述.md)。
    -   负载名称：填写工作负载的名称。
    -   命名空间：选择工作负载的命名空间，默认为default。您可以单击后面的“创建命名空间“，命名空间的详细介绍请参见[创建命名空间](创建命名空间.md)。
    -   实例数量：填写实例的数量，也就是Pod的数量。
    -   容器运行时：CCE集群默认使用普通运行时，CCE Turbo集群可以使用普通运行时或安全运行时。具体区别请参见[安全容器与普通容器](安全容器与普通容器.md)。
    -   时区同步：选择是否开启时区同步。开启后容器与节点使用相同时区（时区同步功能依赖容器中挂载的本地磁盘，请勿修改删除），时区同步详细介绍请参见[时区同步](时区同步.md)。

    **容器配置**

    -   容器信息

        Pod中可以配置多个容器，您可以单击右侧“添加容器“为Pod配置多个容器。

        -   基本信息：[容器基本信息](容器基本信息.md)
        -   生命周期：[设置容器生命周期](设置容器生命周期.md)
        -   健康检查：[设置容器健康检查](设置容器健康检查.md)
        -   环境变量：[设置环境变量](设置环境变量.md)
        -   数据存储：[存储概述](存储概述.md)

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >负载实例数大于1时，不支持挂载云硬盘类型的存储。

        -   安全设置：对容器权限进行设置，保护系统和其他容器不受其影响。请输入用户ID，容器将以当前用户权限运行。
        -   容器日志：[容器日志](容器日志.md)

    -   镜像访问凭证：用于访问镜像仓库的凭证，默认取值为default-secret，使用default-secret可访问SWR镜像仓库的镜像。default-secret详细说明请参见[default-secret](集群系统密钥说明.md#section11760122012591)。
    -   GPU显卡：默认为不限制。当集群中存在GPU节点时，工作负载实例可以调度到指定GPU显卡类型的节点上。

    **服务配置**

    服务（Service）是用来解决Pod访问问题的。每个Service有一个固定IP地址，Service将访问流量转发给Pod，而且Service可以给这些Pod做负载均衡。

    您也可以在创建完工作负载之后再创建Service，Service的概念和使用方法请参见[Service概述](Service概述.md)。

    **高级配置**

    -   升级策略：[工作负载升级配置](工作负载升级配置.md)
    -   调度策略：[调度策略（亲和与反亲和）](调度策略（亲和与反亲和）.md)
    -   标签与注解：[Pod标签与注解](Pod标签与注解.md)
    -   容忍策略：当工作负载实例所在的节点不可用时，系统将实例重新调度到其它可用节点的时间窗。迁移时间窗 \(s\)：请输入时间，默认为300秒。容忍与污点相关，请参见[容忍度（Toleration）](管理节点污点（taint）.md#section2047442210417)。
    -   DNS配置：[工作负载DNS配置说明](工作负载DNS配置说明.md)
    -   性能管理配置：[性能管理配置（性能瓶颈分析）](性能管理配置（性能瓶颈分析）.md)

4.  单击右下角“创建工作负载“。

## 通过kubectl命令行创建<a name="section155246177178"></a>

本节以nginx工作负载为例，说明kubectl命令创建工作负载的方法。

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  创建一个名为nginx-deployment.yaml的描述文件。其中，nginx-deployment.yaml为自定义名称，您可以随意命名。

    **vi nginx-deployment.yaml**

    描述文件内容如下。此处仅为示例，deployment的详细说明请参见[kubernetes官方文档](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)。

    ```
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: nginx
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: nginx
      strategy:
        type: RollingUpdate
      template:
        metadata:
          labels:
            app: nginx
        spec:
          containers:
          - image: nginx    #若使用“开源镜像中心”的镜像，可直接填写镜像名称；若使用“我的镜像”中的镜像，请在SWR中获取具体镜像地址。
            imagePullPolicy: Always
            name: nginx
          imagePullSecrets:
          - name: default-secret
    ```

    以上yaml字段解释如[表1](#table132326831016)。

    **表 1**  deployment字段详解

    <a name="table132326831016"></a>
    <table><thead align="left"><tr id="row523318817104"><th class="cellrowborder" valign="top" width="37%" id="mcps1.2.4.1.1"><p id="p162344817100"><a name="p162344817100"></a><a name="p162344817100"></a>字段名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="47%" id="mcps1.2.4.1.2"><p id="p16234138161012"><a name="p16234138161012"></a><a name="p16234138161012"></a>字段说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="16%" id="mcps1.2.4.1.3"><p id="p102881159151016"><a name="p102881159151016"></a><a name="p102881159151016"></a>必选/可选</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row112346841018"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p182345811107"><a name="p182345811107"></a><a name="p182345811107"></a>apiVersion</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p2023458141014"><a name="p2023458141014"></a><a name="p2023458141014"></a>表示API的版本号。</p>
    <div class="note" id="note143305521379"><a name="note143305521379"></a><a name="note143305521379"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1819911527102"><a name="p1819911527102"></a><a name="p1819911527102"></a>请根据集群版本输入：</p>
    <a name="ul1823483313109"></a><a name="ul1823483313109"></a><ul id="ul1823483313109"><li>1.17及以上版本的集群中无状态应用apiVersion格式为<strong id="b19984186775"><a name="b19984186775"></a><a name="b19984186775"></a>apps/v1</strong></li><li>1.15及以下版本的集群中无状态应用apiVersion格式为<strong id="b620619367112"><a name="b620619367112"></a><a name="b620619367112"></a>extensions/v1beta1</strong></li></ul>
    </div></div>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p6234158101019"><a name="p6234158101019"></a><a name="p6234158101019"></a>必选</p>
    </td>
    </tr>
    <tr id="row202347814100"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p172342815109"><a name="p172342815109"></a><a name="p172342815109"></a>kind</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p142346871019"><a name="p142346871019"></a><a name="p142346871019"></a>创建的对象类别。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p2023416841019"><a name="p2023416841019"></a><a name="p2023416841019"></a>必选</p>
    </td>
    </tr>
    <tr id="row1459172931315"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p1659232941311"><a name="p1659232941311"></a><a name="p1659232941311"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p165932298137"><a name="p165932298137"></a><a name="p165932298137"></a>资源对象的元数据定义。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p16593112941310"><a name="p16593112941310"></a><a name="p16593112941310"></a>必选</p>
    </td>
    </tr>
    <tr id="row33638545115"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p036575412114"><a name="p036575412114"></a><a name="p036575412114"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p1036510541116"><a name="p1036510541116"></a><a name="p1036510541116"></a>deployment的名称。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1936585415110"><a name="p1936585415110"></a><a name="p1936585415110"></a>必选</p>
    </td>
    </tr>
    <tr id="row52341382109"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p2234188171017"><a name="p2234188171017"></a><a name="p2234188171017"></a>Spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p1023414811012"><a name="p1023414811012"></a><a name="p1023414811012"></a>用户对deployment的详细描述的主体部分都在spec中给出。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p92341186101"><a name="p92341186101"></a><a name="p92341186101"></a>必选</p>
    </td>
    </tr>
    <tr id="row490820516139"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p99089513134"><a name="p99089513134"></a><a name="p99089513134"></a>replicas</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p1890815551313"><a name="p1890815551313"></a><a name="p1890815551313"></a>实例数量。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1390895141312"><a name="p1390895141312"></a><a name="p1390895141312"></a>必选</p>
    </td>
    </tr>
    <tr id="row29372135139"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p1493821315132"><a name="p1493821315132"></a><a name="p1493821315132"></a>selector</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p10938171341312"><a name="p10938171341312"></a><a name="p10938171341312"></a>定义Deployment可管理的容器实例。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p5939181320135"><a name="p5939181320135"></a><a name="p5939181320135"></a>必选</p>
    </td>
    </tr>
    <tr id="row393931310133"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p8731714131517"><a name="p8731714131517"></a><a name="p8731714131517"></a>strategy</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p18939313201310"><a name="p18939313201310"></a><a name="p18939313201310"></a>升级类型。当前支持两种升级方式，默认为滚动升级。</p>
    <a name="ul20636151912336"></a><a name="ul20636151912336"></a><ul id="ul20636151912336"><li>RollingUpdate：滚动升级。</li><li>ReplaceUpdate：替换升级。</li></ul>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p169393137138"><a name="p169393137138"></a><a name="p169393137138"></a>可选</p>
    </td>
    </tr>
    <tr id="row793916134135"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p14939131391317"><a name="p14939131391317"></a><a name="p14939131391317"></a>template</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p993921331312"><a name="p993921331312"></a><a name="p993921331312"></a>描述创建的容器实例详细信息。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1193919138132"><a name="p1193919138132"></a><a name="p1193919138132"></a>必选</p>
    </td>
    </tr>
    <tr id="row69398139139"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p132126496218"><a name="p132126496218"></a><a name="p132126496218"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p10939121391317"><a name="p10939121391317"></a><a name="p10939121391317"></a>元数据。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p4939161321314"><a name="p4939161321314"></a><a name="p4939161321314"></a>必选</p>
    </td>
    </tr>
    <tr id="row1479918372441"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p67994378445"><a name="p67994378445"></a><a name="p67994378445"></a>labels</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p1680012377440"><a name="p1680012377440"></a><a name="p1680012377440"></a>metadata.labels定义容器标签。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p180033714449"><a name="p180033714449"></a><a name="p180033714449"></a>可选</p>
    </td>
    </tr>
    <tr id="row6939151316138"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p793911361316"><a name="p793911361316"></a><a name="p793911361316"></a>spec:</p>
    <p id="p17330235102212"><a name="p17330235102212"></a><a name="p17330235102212"></a>containers</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><a name="ul48282256265"></a><a name="ul48282256265"></a><ul id="ul48282256265"><li>image（必选）：容器镜像名称。</li><li>imagePullPolicy（可选）：获取镜像的策略，可选值包括Always（每次都尝试重新下载镜像）、Never（仅使用本地镜像）、IfNotPresent（如果本地有该镜像，则使用本地镜像，本地不存在时下载镜像），默认为Always。</li><li>name（必选）：容器名称。</li></ul>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1193991381318"><a name="p1193991381318"></a><a name="p1193991381318"></a>必选</p>
    </td>
    </tr>
    <tr id="row18939013161315"><td class="cellrowborder" valign="top" width="37%" headers="mcps1.2.4.1.1 "><p id="p159394135139"><a name="p159394135139"></a><a name="p159394135139"></a>imagePullSecrets</p>
    </td>
    <td class="cellrowborder" valign="top" width="47%" headers="mcps1.2.4.1.2 "><p id="p49391813131318"><a name="p49391813131318"></a><a name="p49391813131318"></a>Pull镜像时使用的secret名称。若使用私有镜像，该参数为必选。</p>
    <a name="ul125550172614"></a><a name="ul125550172614"></a><ul id="ul125550172614"><li>需要Pull SWR容器镜像仓库的镜像时，参数值固定为default-secret。</li><li>当Pull第三方镜像仓库的镜像时，需设置为创建的secret名称。</li></ul>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1193981391318"><a name="p1193981391318"></a><a name="p1193981391318"></a>可选</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  创建deployment。

    **kubectl create -f nginx-deployment.yaml**

    回显如下表示已开始创建deployment。

    ```
    deployment "nginx" created
    ```

4.  查看deployment状态。

    **kubectl get deployment**

    deployment状态显示为Running，表示deployment已创建成功。

    ```
    NAME           READY     UP-TO-DATE   AVAILABLE   AGE 
    nginx          1/1       1            1           4m5s
    ```

    **参数解析：**

    -   NAME：工作负载名称。
    -   READY：表示工作负载的可用状态，显示为“可用Pod个数/期望Pod个数”。
    -   UP-TO-DATE：指当前已经完成更新的副本数。
    -   AVAILABLE：可用的Pod个数。
    -   AGE：已经运行的时间。

5.  若工作负载（即deployment）需要被访问（集群内访问或节点访问），您需要设置访问方式，具体请参见[网络管理](网络管理.md)创建对应服务。

