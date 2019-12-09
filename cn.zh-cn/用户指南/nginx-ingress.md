# nginx-ingress<a name="cce_01_0034"></a>

## 插件简介<a name="section26181722164712"></a>

Nginx Ingress Controller插件是一款围绕Kubernetes Ingress资源构建的Nginx控制器，通过和kubernetes api交互，动态的去感知集群中ingress规则变化，根据规则生成一段nginx配置，控制器会把生成的nginx配置写入/etc/nginx.conf文件中。通过该插件您可以获得基本的负载平衡，SSL/TLS termination，对URI重写的支持以及上游SSL/TLS加密等，也可以在安装插件时，修改默认的配置信息来增强插件的功能。

## 使用约束<a name="section3200193614201"></a>

-   集群为1.13以上版本时，才支持此功能。
-   通过api调接口创建的Ingress annotation必须添加kubernetes.io/ingress.class: "nginx"，如果是对接老的Ingress，annotation需添加为kubernetes.io/ingress.class: "cce"。

## 安装插件<a name="section107137401254"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件市场“中，单击nginx-ingress插件下的“安装插件“。
2.  在安装插件页面，在“基本信息“步骤中选择集群和插件版本，单击“下一步“。
3.  在“规格配置“步骤中，参照[表1](#table924319911495)设置服务选型参数，其中带“\*”的参数为必填参数。

    **表 1**  Nginx Ingress插件参数配置

    <a name="table924319911495"></a>
    <table><thead align="left"><tr id="row42442974913"><th class="cellrowborder" valign="top" width="24%" id="mcps1.2.3.1.1"><p id="p17244793496"><a name="p17244793496"></a><a name="p17244793496"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="76%" id="mcps1.2.3.1.2"><p id="p42441596495"><a name="p42441596495"></a><a name="p42441596495"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1137014404511"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p11370134095120"><a name="p11370134095120"></a><a name="p11370134095120"></a>插件规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p937064085113"><a name="p937064085113"></a><a name="p937064085113"></a>请根据业务需求选择插件规格，可单实例部署、多实例部署或自定义资源规格部署。</p>
    </td>
    </tr>
    <tr id="row83701240105118"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p3370040165116"><a name="p3370040165116"></a><a name="p3370040165116"></a>实例数</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p93701640145120"><a name="p93701640145120"></a><a name="p93701640145120"></a>选择上方插件规格后，显示插件中的实例数，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row4370840165119"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p937054045117"><a name="p937054045117"></a><a name="p937054045117"></a>容器</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1437014065110"><a name="p1437014065110"></a><a name="p1437014065110"></a>选择插件规格后，显示插件容器的CPU和内存配额，此处仅作显示。</p>
    </td>
    </tr>
    <tr id="row12370940175116"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p237044095117"><a name="p237044095117"></a><a name="p237044095117"></a>Worker进程数</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1493852310547"><a name="p1493852310547"></a><a name="p1493852310547"></a>定义了nginx对外提供web服务时的worker进程数，默认 auto。</p>
    <p id="p103701340145120"><a name="p103701340145120"></a><a name="p103701340145120"></a>此参数的最优值取决于许多因素，包括（但不限于）CPU核的数量、存储数据的硬盘数量及负载模式。不能确定时，可将其设置为可用的CPU内核数（设置为“auto”将尝试自动检测它）。</p>
    </td>
    </tr>
    <tr id="row53701440125116"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p8370124035118"><a name="p8370124035118"></a><a name="p8370124035118"></a>最大并发数</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1837104015118"><a name="p1837104015118"></a><a name="p1837104015118"></a>单个后台Worker进程的最大并发链接数，默认 16384。</p>
    </td>
    </tr>
    <tr id="row142421934205112"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p1024423435112"><a name="p1024423435112"></a><a name="p1024423435112"></a>长连接超时</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p456484345710"><a name="p456484345710"></a><a name="p456484345710"></a>长连接超时时间，单位秒，默认 60s。</p>
    <p id="p1324473455114"><a name="p1324473455114"></a><a name="p1324473455114"></a>该功能是使客户端到服务器端的连接在设定的时间内持续有效，当出现对服务器的后继请求时，该功能避免了建立或者重新建立连接。切记这个参数也不能设置过大！否则会导致许多无效的http连接占据着nginx的连接数，终nginx崩溃。</p>
    </td>
    </tr>
    <tr id="row152444346519"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p6244334185118"><a name="p6244334185118"></a><a name="p6244334185118"></a>全局白名单</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p124311408416"><a name="p124311408416"></a><a name="p124311408416"></a>Console中暂不支持该参数设置，将于近期开放。</p>
    <p id="p1853818487471"><a name="p1853818487471"></a><a name="p1853818487471"></a>如果您需要添加白名单功能，请自行安装TOA插件。安装方法请参见<a href="https://support.huaweicloud.com/usermanual-elb/zh_cn_elb_06_0001.html" target="_blank" rel="noopener noreferrer">TOA插件配置</a>。</p>
    </td>
    </tr>
    <tr id="row524420346511"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p112449344512"><a name="p112449344512"></a><a name="p112449344512"></a>定义nginx配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p9731184313503"><a name="p9731184313503"></a><a name="p9731184313503"></a>Nginx Ingress Controller通过ConfigMap来修改更新nginx.conf里的配置，全局的设置，直接配置nginx.conf的生成，影响管理的全部Ingress，如需配置可通过<a href="https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/" target="_blank" rel="noopener noreferrer">configmap</a>查找。</p>
    </td>
    </tr>
    <tr id="row1624493410514"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p824503418518"><a name="p824503418518"></a><a name="p824503418518"></a>自定义请求头</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p1591191619135"><a name="p1591191619135"></a><a name="p1591191619135"></a>nginx默认会将用户自定义的header过滤掉，此参数允许重新定义或者添加发往后端服务器的请求头。</p>
    </td>
    </tr>
    <tr id="row224517348516"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p162453345514"><a name="p162453345514"></a><a name="p162453345514"></a>开启默认404服务</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p192451534175116"><a name="p192451534175116"></a><a name="p192451534175116"></a>该插件默认提供了404后端服务，如果是用户自定义的404服务，输入格式示例如下：&lt;namespace/serviceName&gt;。</p>
    </td>
    </tr>
    <tr id="row1824419144917"><td class="cellrowborder" valign="top" width="24%" headers="mcps1.2.3.1.1 "><p id="p4244298493"><a name="p4244298493"></a><a name="p4244298493"></a>负载均衡服务</p>
    </td>
    <td class="cellrowborder" valign="top" width="76%" headers="mcps1.2.3.1.2 "><p id="p624411914915"><a name="p624411914915"></a><a name="p624411914915"></a>该功能可让公网或者私网的流量能转发到该插件的service上。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  完成配置后单击“安装“按钮，待插件安装完成后，单击“返回插件管理“。

    **图 1**  安装nginx-ingress插件成功<a name="fig1676613108517"></a>  
    ![](figures/安装nginx-ingress插件成功.png "安装nginx-ingress插件成功")

5.  在“插件实例“页签中单击右上角的集群选择框，选择安装的集群后可查看到运行中的插件，这表明该插件已在当前集群中安装成功。

    **图 2**  查看安装的插件<a name="fig3673101918710"></a>  
    ![](figures/查看安装的插件.png "查看安装的插件")


## 卸载插件<a name="section610455514114"></a>

1.  在[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)中，单击左侧导航栏的“插件管理“，在“插件实例“页签中，选择对应的集群，单击nginx-ingress下的“卸载“。
2.  在弹出的窗口中，单击“确认“，可卸载该插件。

