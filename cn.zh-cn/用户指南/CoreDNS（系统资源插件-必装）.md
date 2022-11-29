# CoreDNS（系统资源插件，必装）<a name="cce_10_0129"></a>

## 插件简介<a name="section25311744154917"></a>

CoreDNS插件是一款通过链式插件的方式为Kubernetes提供域名解析服务的DNS服务器。

CoreDNS是由CNCF孵化的开源软件，用于Cloud-Native环境下的DNS服务器和服务发现解决方案。CoreDNS实现了插件链式架构，能够按需组合插件，运行效率高、配置灵活。在kubernetes集群中使用CoreDNS能够自动发现集群内的服务，并为这些服务提供域名解析。同时，通过级联云上DNS服务器，还能够为集群内的工作负载提供外部域名的解析服务。

**该插件为系统资源插件，kubernetes 1.11及以上版本的集群在创建时默认安装。**

目前CoreDNS已经成为社区kubernetes 1.11及以上版本集群推荐的DNS服务器解决方案。

CoreDNS官网：[https://coredns.io/](https://coredns.io/)

开源社区地址：[https://github.com/coredns/coredns](https://github.com/coredns/coredns)

>![](public_sys-resources/icon-note.gif) **说明：** 
>DNS详细使用方法请参见[DNS](DNS.md)。

## 约束与限制<a name="section10849134521812"></a>

CoreDNS正常运行或升级时，请确保集群中的可用节点数大于等于CoreDNS的实例数，且CoreDNS的所有实例都处于运行状态，否则将导致插件异常或升级失败。

## 安装插件<a name="section776571919194"></a>

本插件为系统默认安装，若因特殊情况卸载后，可参照如下步骤重新安装。

1.  登录CCE控制台，进入集群，在左侧导航栏中选择“插件管理“，在右侧找到**coredns**，单击“安装“。
2.  在安装插件页面，选择插件规格，并配置相关参数。

    **表 1**  coredns插件参数配置

    <a name="table924319911495"></a>
    <table><thead align="left"><tr id="row42442974913"><th class="cellrowborder" valign="top" width="24%" id="mcps1.2.3.1.1"><p id="p17244793496"><a name="p17244793496"></a><a name="p17244793496"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="76%" id="mcps1.2.3.1.2"><p id="p42441596495"><a name="p42441596495"></a><a name="p42441596495"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1137014404511"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p11370134095120"><a name="p11370134095120"></a><a name="p11370134095120"></a>插件规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p937064085113"><a name="p937064085113"></a><a name="p937064085113"></a>并发域名解析能力，请根据业务需求选择插件规格。</p>
    </td>
    </tr>
    <tr id="row83701240105118"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p3370040165116"><a name="p3370040165116"></a><a name="p3370040165116"></a>实例数</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p93701640145120"><a name="p93701640145120"></a><a name="p93701640145120"></a>选择上方插件规格后，显示插件中的实例数。</p>
    </td>
    </tr>
    <tr id="row4370840165119"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p937054045117"><a name="p937054045117"></a><a name="p937054045117"></a>容器</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1437014065110"><a name="p1437014065110"></a><a name="p1437014065110"></a>选择插件规格后，显示插件容器的CPU和内存配额，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row53701440125116"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p8370124035118"><a name="p8370124035118"></a><a name="p8370124035118"></a>参数配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><a name="ul221832131618"></a><a name="ul221832131618"></a><ul id="ul221832131618"><li>parameterSyncStrategy：插件升级时是否配置一致性检查。<a name="ul9522414615"></a><a name="ul9522414615"></a><ul id="ul9522414615"><li>ensureConsistent：表示启用配置一致性检查，如果集群中记录的配置和实际生效配置不一致，插件将无法升级。</li><li>force：表示升级时忽略配置一致性检查。请您自行确保当前生效配置和原配置一致。插件升级完毕后，需恢复parameterSyncStrategy值为ensureConsistent，重新启用配置一致性检查。</li></ul>
    </li><li>stub_domains：存根域，您可对自定义的域名配置域名服务器，格式为一个键值对，键为DNS后缀域名，值为一个或一组DNS IP地址。</li><li>upstream_nameservers：上游域名服务器地址。</li><li>servers: coredns 1.23.1插件版本开始开放servers配置，用户可对servers做定制化配置，参见<a href="https://kubernetes.io/zh/docs/tasks/administer-cluster/dns-custom-nameservers" target="_blank" rel="noopener noreferrer">dns-custom-nameservers</a>，其中plugins为coredns中各组件配置（参考https://coredns.io/manual/plugins/，一般场景建议保持默认配置，以免出现配置错误而导致coredns整体不可用），每个plugin组件可包含"name"、"parameters"(可选)、"configBlock"(可选)配置，对应生成的Corefile配置文件中格式如下:<p id="p17731113172317"><a name="p17731113172317"></a><a name="p17731113172317"></a>$name  $parameters {</p>
    <p id="p1122616245232"><a name="p1122616245232"></a><a name="p1122616245232"></a>$configBlock</p>
    <p id="p2035773019227"><a name="p2035773019227"></a><a name="p2035773019227"></a>}</p>
    <p id="p187693475389"><a name="p187693475389"></a><a name="p187693475389"></a>常用plugin的说明请参见<a href="#table1420814384015">表2</a>。</p>
    </li></ul>
    <p id="p13671111141717"><a name="p13671111141717"></a><a name="p13671111141717"></a>示例：</p>
    <pre class="screen" id="screen9635912141719"><a name="screen9635912141719"></a><a name="screen9635912141719"></a>{
         "servers": [
    		   {
    			"plugins": [
    				{
    					"name": "bind",
    					"parameters": "{$POD_IP}"
    				},
    				{
    					"name": "cache",
    					"parameters": 30
    				},
    				{
    					"name": "errors"
    				},
    				{
    					"name": "health",
    					"parameters": "{$POD_IP}:8080"
    				},
    				{
    					"configBlock": "pods insecure\nfallthrough in-addr.arpa ip6.arpa",
    					"name": "kubernetes",
    					"parameters": "cluster.local in-addr.arpa ip6.arpa"
    				},
    				{
    					"name": "loadbalance",
    					"parameters": "round_robin"
    				},
    				{
    					"name": "prometheus",
    					"parameters": "{$POD_IP}:9153"
    				},
    				{
    					"configBlock": "policy random",
    					"name": "forward",
    					"parameters": ". /etc/resolv.conf"
    				},
    				{
    					"name": "reload"
    				},
    				{
    					"name": "log"
    				}
    			],
    			"port": 5353,
    			"zones": [
    				{
    					"zone": "."
    				}
    			]
    		}
    	],
    	"stub_domains": {
    		"acme.local": [
    			"1.2.3.4",
    			"6.7.8.9"
    		]
    	},
    	"upstream_nameservers": ["8.8.8.8", "8.8.4.4"]
    }</pre>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  coredns主zone默认plugin配置说明

    <a name="table1420814384015"></a>
    <table><thead align="left"><tr id="row122089381904"><th class="cellrowborder" valign="top" width="24.93%" id="mcps1.2.3.1.1"><p id="p42081738709"><a name="p42081738709"></a><a name="p42081738709"></a>plugin名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="75.07000000000001%" id="mcps1.2.3.1.2"><p id="p02081938205"><a name="p02081938205"></a><a name="p02081938205"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row192083386015"><td class="cellrowborder" valign="top" width="24.93%" headers="mcps1.2.3.1.1 "><p id="p1020814381709"><a name="p1020814381709"></a><a name="p1020814381709"></a>bind</p>
    </td>
    <td class="cellrowborder" valign="top" width="75.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p1020813385019"><a name="p1020813385019"></a><a name="p1020813385019"></a>coredns 侦听的hostIP配置，建议保持当前默认值{$POD_IP}。</p>
    </td>
    </tr>
    <tr id="row72085381200"><td class="cellrowborder" valign="top" width="24.93%" headers="mcps1.2.3.1.1 "><p id="p17208738008"><a name="p17208738008"></a><a name="p17208738008"></a>cache</p>
    </td>
    <td class="cellrowborder" valign="top" width="75.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p122081381708"><a name="p122081381708"></a><a name="p122081381708"></a><span>启用</span>DNS缓存。</p>
    </td>
    </tr>
    <tr id="row20208338609"><td class="cellrowborder" valign="top" width="24.93%" headers="mcps1.2.3.1.1 "><p id="p13208163819018"><a name="p13208163819018"></a><a name="p13208163819018"></a>errors</p>
    </td>
    <td class="cellrowborder" valign="top" width="75.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p2208838309"><a name="p2208838309"></a><a name="p2208838309"></a>错误信息到标准输出。</p>
    </td>
    </tr>
    <tr id="row320816381009"><td class="cellrowborder" valign="top" width="24.93%" headers="mcps1.2.3.1.1 "><p id="p1420810386014"><a name="p1420810386014"></a><a name="p1420810386014"></a>health</p>
    </td>
    <td class="cellrowborder" valign="top" width="75.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p19208153819010"><a name="p19208153819010"></a><a name="p19208153819010"></a>coredns健康检查配置，当前侦听{$POD_IP}:8080，<span>请保持此默认值，否则导致coredns健康检查失败而不断重启</span></p>
    </td>
    </tr>
    <tr id="row320883811017"><td class="cellrowborder" valign="top" width="24.93%" headers="mcps1.2.3.1.1 "><p id="p82081381506"><a name="p82081381506"></a><a name="p82081381506"></a>kubernetes</p>
    </td>
    <td class="cellrowborder" valign="top" width="75.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p480645417412"><a name="p480645417412"></a><a name="p480645417412"></a>CoreDNS Kubernetes插件，提供集群内服务解析能力。</p>
    </td>
    </tr>
    <tr id="row420811381012"><td class="cellrowborder" valign="top" width="24.93%" headers="mcps1.2.3.1.1 "><p id="p1220893817011"><a name="p1220893817011"></a><a name="p1220893817011"></a>loadbalance</p>
    </td>
    <td class="cellrowborder" valign="top" width="75.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p4208143817017"><a name="p4208143817017"></a><a name="p4208143817017"></a><span>轮转式 DNS 负载均衡器， 在应答中随机分配 A、AAAA 和 MX 记录的顺序</span>。</p>
    </td>
    </tr>
    <tr id="row204781431659"><td class="cellrowborder" valign="top" width="24.93%" headers="mcps1.2.3.1.1 "><p id="p04781133513"><a name="p04781133513"></a><a name="p04781133513"></a>prometheus</p>
    </td>
    <td class="cellrowborder" valign="top" width="75.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p10970514661"><a name="p10970514661"></a><a name="p10970514661"></a>CoreDNS自身metrics数据接口, 默认zone侦听{$POD_IP}:9153，<span>请保持此默认值，否则普罗无法采集coredns metrics数据。</span></p>
    </td>
    </tr>
    <tr id="row4820791651"><td class="cellrowborder" valign="top" width="24.93%" headers="mcps1.2.3.1.1 "><p id="p2820899511"><a name="p2820899511"></a><a name="p2820899511"></a>forward</p>
    </td>
    <td class="cellrowborder" valign="top" width="75.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p78211391652"><a name="p78211391652"></a><a name="p78211391652"></a><span>不在 Kubernetes 集群域内的任何查询都将转发到默认的解析器 (/etc/resolv.conf)。</span></p>
    </td>
    </tr>
    <tr id="row6126137245"><td class="cellrowborder" valign="top" width="24.93%" headers="mcps1.2.3.1.1 "><p id="p181260314249"><a name="p181260314249"></a><a name="p181260314249"></a>reload</p>
    </td>
    <td class="cellrowborder" valign="top" width="75.07000000000001%" headers="mcps1.2.3.1.2 "><p id="p1812620312244"><a name="p1812620312244"></a><a name="p1812620312244"></a>允许自动重新加载已更改的 Corefile。 编辑 ConfigMap 配置后，请等待两分钟，以使更改生效。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  完成以上配置后，单击“安装“。

## kubernetes中的域名解析逻辑<a name="section1860523212152"></a>

DNS策略可以在每个pod基础上进行设置，目前，Kubernetes支持**Default、ClusterFirst、ClusterFirstWithHostNet和None**四种DNS策略，具体请参见[https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/](https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/)。这些策略在pod-specific的**dnsPolicy**字段中指定。

-   **“Default”**：如果dnsPolicy被设置为“Default”，则名称解析配置将从pod运行的节点继承。 自定义上游域名服务器和存根域不能够与这个策略一起使用。
-   **“ClusterFirst”：**如果dnsPolicy被设置为“ClusterFirst”，任何与配置的集群域后缀不匹配的DNS查询（例如，www.kubernetes.io）将转发到从该节点继承的上游名称服务器。集群管理员可能配置了额外的存根域和上游DNS服务器。
-   **“ClusterFirstWithHostNet”：**对于使用hostNetwork运行的Pod，您应该明确设置其DNS策略“ClusterFirstWithHostNet”。
-   **“None”：**它允许Pod忽略Kubernetes环境中的DNS设置。应使用dnsConfigPod规范中的字段提供所有DNS设置 。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   Kubernetes 1.10及以上版本，支持Default、ClusterFirst、ClusterFirstWithHostNet和None四种策略；低于Kubernetes 1.10版本，仅支持default、ClusterFirst和ClusterFirstWithHostNet三种。
>-   “Default”不是默认的DNS策略。如果dnsPolicy的Flag没有特别指明，则默认使用“**ClusterFirst**”。

**路由请求流程：**

未配置存根域：没有匹配上配置的集群域名后缀的任何请求，例如 “www.kubernetes.io”，将会被转发到继承自节点的上游域名服务器。

已配置存根域：如果配置了存根域和上游DNS服务器，DNS查询将基于下面的流程对请求进行路由：

1.  查询首先被发送到coredns中的DNS缓存层。
2.  从缓存层，检查请求的后缀，并根据下面的情况转发到对应的DNS上：
    -   具有集群后缀的名字（例如“.cluster.local”）：请求被发送到coredns。

    -   具有存根域后缀的名字（例如“.acme.local”）：请求被发送到配置的自定义DNS解析器（例如：监听在 1.2.3.4）。
    -   未能匹配上后缀的名字（例如“widget.com”）：请求被转发到上游DNS。


**图 1**  路由请求流程<a name="fig7582181514118"></a>  
![](figures/路由请求流程.png "路由请求流程")

## 自定义CoreDNS规格<a name="section4821153719377"></a>

CoreDNS在插件界面仅支持按预设规格配置，通常情况下，这满足绝大多数使用场景。但在一些少数对CoreDNS资源用量有要求的场景下，不能根据需要灵活配置。

下面介绍CoreDNS参数自定义配置方法，包括副本数量、CPU/内存的大小等。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>-   CoreDNS修改配置需额外谨慎，因为CoreDNS负责集群的域名解析任务，修改不当可能会导致集群解析出现异常。请做好修改前后的测试验证。
>-   CoreDNS使用资源的规格与解析能力相关，修改CoreDNS副本数量、CPU/内存的大小会对影响解析性能，请经过评估后再做修改。
>-   CoreDNS插件默认配置了podAntiAffinity（Pod反亲和），当一个节点已有一个CoreDNS Pod时无法再添加新的Pod，即一个节点上只能运行一个CoreDNS Pod。如果您配置的CoreDNS副本数量大于集群节点数量，会导致多出的Pod无法调度。建议Pod的副本数量不大于节点的数量。

1.  调用[插件查询接口](https://support.huaweicloud.com/api-cce/cce_02_0326.html)查看已安装CoreDNS的插件ID。

    GET https://\{cluster\_id\}.\{endpoint\}/api/v3/addons?cluster\_id=\{cluster\_id\}

    接口调用方法请参见[如何调用API](https://support.huaweicloud.com/api-cce/cce_02_0099.html)，其中\{cluster\_id\}为集群的ID，集群ID可以在控制台的集群详情页面中查看；\{endpoint\}为CCE的访问地址，可以从[地区和终端节点](https://developer.huaweicloud.com/endpoint?CCE)获取，例如上海一区域为cce.east-3.myhuaweicloud.com。

    在响应中查看CoreDNS的uid，和spec定义，如下所示。

    ```
    {
        "kind": "Addon",
        "apiVersion": "v3",
        "items": [
            {
                "kind": "Addon",
                "apiVersion": "v3",
                "metadata": {
                    "uid": "2083381d-46ae-11ec-91a8-0255ac1000c5",
                    "name": "coredns",
                    "creationTimestamp": "2021-11-16T07:23:42Z",
                    "updateTimestamp": "2021-11-16T07:27:35Z"
                },
                "spec": {
                    "clusterID": "15d748b4-3de1-11ec-9199-0255ac1000c9",
                    "version": "1.17.9",
                    "addonTemplateName": "coredns",
                    "addonTemplateType": "helm",
    ...
    ```

2.  调用[修改插件接口](https://support.huaweicloud.com/api-cce/cce_02_0323.html)修改插件的规格。

    PUT https://\{cluster\_id\}.\{endpoint\}/api/v3/addons/\{uid\}

    其中\{cluster\_id\}为集群的ID；\{endpoint\}为CCE的访问地址，可以从[地区和终端节点](https://developer.huaweicloud.com/endpoint?CCE)获取；\{uid\}为上一步查询到的插件ID。

    请求Body示例如下，spec定义从上一步中查询到的内容，根据需求修改其中replicas（副本数量），resources（单个Pod的CPU/内存的使用量配置）；clusterID、version保持不变，addon.upgrade/type的取值必须为patch。

    ```
    {
        "metadata": {
            "annotations": {
                "addon.upgrade/type": "patch"
            }
        },
        "spec": {
            "clusterID": "15d748b4-3de1-11ec-9199-0255ac1000c9",
            "version": "1.17.9",
            "addonTemplateName": "coredns",
            "values": {
                "flavor": {
                    "replicas": 2,
                    "resources": [
                        {
                            "limitsCpu": "500m",
                            "limitsMem": "512Mi",
                            "requestsCpu": "500m",
                            "requestsMem": "512Mi"
                        }
                    ]
                }
            }
        }
    }
    ```


