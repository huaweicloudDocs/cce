# 七层负载均衡（Ingress）<a name="cce_01_0094"></a>

七层负载均衡是采用了增强型弹性负载均衡，在四层负载均衡访问方式的基础上支持了URI配置，通过对应的URI将访问流量分发到对应的服务。同时，服务根据不同URI实现不同的功能。

七层负载均衡访问方式由弹性负载均衡ELB服务地址、设置的访问端口、定义的URI组成，例如：10.117.117.117:80/helloworld。

通过配置公网类型和私网类型的负载均衡实例可以实现公网的七层路由转发和内网（同一VPC内）的七层路由转发。

## 准备工作<a name="section2042610683912"></a>

已在管理控制台中创建“弹性负载均衡“实例。

1.  登录管理控制台首页，在服务列表中选择“网络  \> 弹性负载均衡 ELB“。
2.  单击右上角的“购买增强型负载均衡“，详细操作步骤请参见[创建增强型负载均衡器](https://support.huaweicloud.com/usermanual-elb/zh-cn_topic_0015479967.html)。

>![](public_sys-resources/icon-note.gif) **说明：**   
>CCE中的负载均衡 \( LoadBalancer \)访问类型使用[弹性负载均衡 ELB](https://support.huaweicloud.com/productdesc-elb/zh-cn_topic_0015479966.html)提供网络访问，存在如下产品约束：  
>-   自动创建的ELB实例建议不要被其他资源使用，否则会在删除时被占用，导致资源残留。  
>-   正在使用的ELB实例请不要修改监听器名称，否则可能导致无法正常访问。  
>-   正在使用的ELB实例，其监听器请不要在ELB控制台中添加自定义转发规则，未通过CCE“网络管理“中的Ingress所管理的转发规则，将在更新ingress的时被清理掉。  

## 通过控制台操作<a name="section744117150366"></a>

您可以在创建工作负载时通过CCE控制台设置访问方式，本节以ingress-test工作负载为例进行说明。

1.  创建工作负载，详细步骤请参见[创建无状态负载\(Deployment\)](创建无状态负载(Deployment).md)或[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)。
    -   若创建工作负载时，配置了工作负载访问方式，且设置为“节点访问 \( NodePort \)”，请直接执行[3](#li45981923161059)。
    -   若创建工作负载未设置访问方式，请先执行[2](#li248013365354)。

2.  <a name="li248013365354"></a>（可选）若创建工作负载时，未配置“节点访问 \( NodePort \)”，请执行如下操作。
    1.  登录CCE控制台，在左侧导航栏中选择“资源管理 \> 网络管理”。
    2.  在Service页签下，单击“添加Service”。选择类型为“节点访问 \( NodePort \)”。
        -   **服务名称：**自定义服务名称，可与工作负载名称保持一致。
        -   **集群名称：**选择需要添加Service的集群。
        -   **命名空间：**选择需要添加Service的命名空间。
        -   **关联工作负载：**单击“选择工作负载”，选择需要配置节点访问 \( NodePort \)的工作负载名称，单击“确定”。
        -   **服务亲和：**
            -   集群级别：集群下所有节点的IP+访问端口均可以访问到此服务关联的负载，服务访问会因路由跳转导致一定性能损失，且无法获取到客户端源IP。
            -   节点级别：只有通过负载所在节点的IP+访问端口才可以访问此服务关联的负载，服务访问没有因路由跳转导致的性能损失，且可以获取到客户端源IP。

        -   **端口配置：**
            -   协议：请根据业务的协议类型选择。
            -   容器端口：容器镜像中工作负载实际监听的端口，需用户确定。nginx程序实际监听的端口为80。
            -   访问端口：容器端口映射到节点私有IP上的端口，用私有IP访问工作负载时使用，端口范围为30000-32767，建议选择“自动生成”。
                -   自动生成：系统会自动分配端口号。
                -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。


    3.  单击“创建”，节点访问方式设置成功。

3.  <a name="li45981923161059"></a>添加Ingress类型的Service。
    1.  单击CCE左侧导航栏的“资源管理 \>  网络管理”。
    2.  在Ingress页签下，单击“添加Ingress”。

        **图 1**  添加Ingress<a name="fig1625112413916"></a>  
        ![](figures/添加Ingress.png "添加Ingress")

        -   **Ingress名称：**自定义Ingress名称，例如ingress-demo。
        -   **集群名称：**选择需要添加Ingress的集群。
        -   **命名空间：**选择需要添加Ingress的命名空间。
        -   <a name="li17417517134"></a>**对接Nginx插件：**集群中已安装[nginx-ingress](nginx-ingress.md)插件后显示此参数，若未安装[nginx-ingress](nginx-ingress.md)插件本参数不显示。

            单击![](figures/zh-cn_image_0183600214.png)开启后可配置如下Nginx参数：

            **表 1**  Nginx配置

            <a name="table05328482472"></a>
            <table><thead align="left"><tr id="row14537184814714"><th class="cellrowborder" valign="top" width="23.400000000000002%" id="mcps1.2.3.1.1"><p id="p453714481473"><a name="p453714481473"></a><a name="p453714481473"></a>参数</p>
            </th>
            <th class="cellrowborder" valign="top" width="76.6%" id="mcps1.2.3.1.2"><p id="p553714824714"><a name="p553714824714"></a><a name="p553714824714"></a>参数说明</p>
            </th>
            </tr>
            </thead>
            <tbody><tr id="row642311116124"><td class="cellrowborder" valign="top" width="23.400000000000002%" headers="mcps1.2.3.1.1 "><p id="p1242371171212"><a name="p1242371171212"></a><a name="p1242371171212"></a>对外协议</p>
            </td>
            <td class="cellrowborder" valign="top" width="76.6%" headers="mcps1.2.3.1.2 "><p id="p042318171215"><a name="p042318171215"></a><a name="p042318171215"></a>支持<span class="uicontrol" id="uicontrol1712440191315"><a name="uicontrol1712440191315"></a><a name="uicontrol1712440191315"></a>“HTTP”</span>和<span class="uicontrol" id="uicontrol192534211138"><a name="uicontrol192534211138"></a><a name="uicontrol192534211138"></a>“HTTPS”</span>两种协议。</p>
            </td>
            </tr>
            <tr id="row826304681311"><td class="cellrowborder" valign="top" width="23.400000000000002%" headers="mcps1.2.3.1.1 "><p id="p7263946111315"><a name="p7263946111315"></a><a name="p7263946111315"></a>对外端口</p>
            </td>
            <td class="cellrowborder" valign="top" width="76.6%" headers="mcps1.2.3.1.2 "><p id="p162631846111312"><a name="p162631846111312"></a><a name="p162631846111312"></a>安装nginx-ingress插件时预留的监听端口，HTTP为80，HTTPS为443。</p>
            </td>
            </tr>
            <tr id="row205371848144711"><td class="cellrowborder" valign="top" width="23.400000000000002%" headers="mcps1.2.3.1.1 "><p id="p195381848164718"><a name="p195381848164718"></a><a name="p195381848164718"></a>超时时间</p>
            </td>
            <td class="cellrowborder" valign="top" width="76.6%" headers="mcps1.2.3.1.2 "><p id="p253884810475"><a name="p253884810475"></a><a name="p253884810475"></a>描述客户端与代理服务器建立连接的超时时间。</p>
            </td>
            </tr>
            <tr id="row25383486478"><td class="cellrowborder" valign="top" width="23.400000000000002%" headers="mcps1.2.3.1.1 "><p id="p5538194844713"><a name="p5538194844713"></a><a name="p5538194844713"></a>重定向地址</p>
            </td>
            <td class="cellrowborder" valign="top" width="76.6%" headers="mcps1.2.3.1.2 "><p id="p75381148174713"><a name="p75381148174713"></a><a name="p75381148174713"></a>将所有的内容重定向到指定地址，例如输入"https://www.huaweicloud.com/"。</p>
            </td>
            </tr>
            <tr id="row1153816485478"><td class="cellrowborder" valign="top" width="23.400000000000002%" headers="mcps1.2.3.1.1 "><p id="p453864864712"><a name="p453864864712"></a><a name="p453864864712"></a>自定义配置</p>
            </td>
            <td class="cellrowborder" valign="top" width="76.6%" headers="mcps1.2.3.1.2 "><p id="p1642633205019"><a name="p1642633205019"></a><a name="p1642633205019"></a>Ingress通过Annotations设置来修改nginx.conf里面的配置，如需设置key: value，可通过<a href="https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/" target="_blank" rel="noopener noreferrer">Annotations</a>查询。</p>
            </td>
            </tr>
            </tbody>
            </table>

        -   **负载均衡配置：**Ingress使用弹性负载均衡服务（ELB）的负载均衡器提供七层网络访问。

            **开启“对接Nginx插件“后，将使用Nginx插件中配置的负载均衡设置，该配置区域将不显示。**

            负载均衡：可以将互联网访问流量自动分发到工作负载所在的多个节点上。负载均衡实例需与当前集群处于相同VPC且为相同公私网类型。

            请根据业务需求选择“公网“或“私网“，具体请参见[公网和私网负载均衡器](https://support.huaweicloud.com/productdesc-elb/zh_cn_elb_01_0004.html)。

            -   公网：支持自动创建和使用已有负载均衡实例两种方式。增强型负载均衡配额不足时，请通过新建[增强型弹性负载均衡](https://console.huaweicloud.com/vpc/#/ulb/createUlb)创建，完成后点击刷新按钮。
                -   更改配置：选择“公网 \> 自动创建“时，单击规格配置下的“更改配置”，可修改待创建的负载均衡实例的名称、规格、计费模式和带宽。
                -   企业项目：对接ELB的企业项目，可以选择直接创建在具体的ELB企业项目下。

            -   私网：支持自动创建和使用已有负载均衡实例两种方式。
                -   企业项目：对接ELB的企业项目，可以选择直接创建在具体的ELB企业项目下。

        -   **监听器配置：**Ingress为负载均衡器配置监听器，监听器对负载均衡器上的请求进行监听，并分发流量。

            **开启“对接Nginx插件“后将不显示该配置。**

            -   对外协议：支持HTTP和HTTPS。若选择HTTPS，请选择密钥证书，格式说明请参见[证书格式](https://support.huaweicloud.com/usermanual-elb/zh-cn_topic_0092382555.html)。

                >![](public_sys-resources/icon-note.gif) **说明：**   
                >-   选择HTTPS协议时，才需要创建密钥证书ingress-test-secret.yaml。创建密钥的方法请参见[创建密钥](创建密钥.md)。  
                >-   同一个ELB实例的同一个端口配置HTTPS时，一个监听器只支持配置一个密钥证书。若使用两个不同的密钥证书将两个Ingress添加到同一个ELB下的同一个监听器，ELB侧实际只生效最初的证书。  

            -   对外端口：开放在负载均衡服务地址的端口，可任意指定。

                若选择启用“对接Nginx插件“后，将默认开启80和443端口，此处“对外端口“参数项将不显示。

        -   **转发策略配置：**请求的访问地址与转发规则匹配时（转发规则由域名、URL组成），此请求将被转发到对应的目标Service处理。

            -   域名：实际访问的域名地址。请确保所填写的域名已注册并备案，在Ingress创建完成后，将域名与自动创建的负载均衡实例的IP（即Ingress访问地址的IP部分）绑定。一旦配置了域名规则，则必须使用域名访问。
            -   URL匹配规则：
                -   前缀匹配：例如映射URL为/healthz，只要符合此前缀的URL均可访问。例如/healthz/v1，/healthz/v2。
                -   精确匹配：表示精准匹配，只有完全匹配上才能生效。例如映射URL为/healthz，则必须为此URL才能访问。
                -   正则匹配：可设定映射URL规范，例如规范为**/\[A-Za-z0-9\_.-\]+/test**。只要符合此规则的URL均可访问，例如/abcA9/test，/v1-Ab/test。正则匹配规则支持POSIX与Perl两种标准。

            -   URL：需要注册的访问路径，例如：/healthz。
            -   目标Service：请选择已有Service或新建Service。页面列表中仅支持选择“节点访问 \( NodePort \)“  类型的Service，该查询结果已自动过滤。若您[开启了Nginx插件](#li17417517134)，可以通过页面右侧的“YAML创建“功能对接“集群内访问 \( ClusterIP \)“类型的Service。
            -   Service访问端口：可选择目标Service的访问端口。
            -   服务负载均衡配置：该配置是基于服务的配置，若有多条路由使用当前服务，这些路由将使用相同的服务负载均衡配置。详细配置请参见[负载均衡配置](负载均衡-(-LoadBalancer-).md#li1242315120217)。
            -   操作：可单击“删除“按钮删除该配置。

            单击“添加转发策略“按钮可添加多条转发策略。


4.  配置完成后，单击“创建“。

    创建完成后，在Ingress列表可查看到已创建成功的Ingress。

5.  访问工作负载（例如名称为defaultbackend）的“/healthz”接口。

    方式一：负载均衡IP访问（需负载均衡访问的服务不能配置域名）

    1.  获取defaultbackend“/healthz”接口的访问地址，访问地址有负载均衡实例、对外端口、映射URL组成，例如：10.154.73.151:80/healthz。

        **图 2**  获取访问地址<a name="fig911562743620"></a>  
        ![](figures/获取访问地址-8.png "获取访问地址-8")

    2.  在浏览器中输入“/healthz”接口的访问地址，如：http://10.154.73.151:80/healthz，即可成功访问工作负载，如[图3](#fig17115192714367)。

        **图 3**  访问defaultbackend“/healthz”接口<a name="fig17115192714367"></a>  
        ![](figures/访问defaultbackend-healthz-接口.png "访问defaultbackend-healthz-接口")

    方式二：域名访问

    以ingress中已配置域名ingress.com为例。

    1.  获取ingress-demo“/james”接口的域名与访问地址的IP与端口。

        **图 4**  获取域名与访问地址<a name="fig1992172383117"></a>  
        ![](figures/获取域名与访问地址.png "获取域名与访问地址")

    2.  在本地主机的  C:\\Windows\\System32\\drivers\\etc\\hosts中配置访问地址的IP和域名。
    3.  在浏览器中输入http://域名:访问地址端口/映射url，如：http://ingress.com:81/james。


## 通过kubectl命令行创建<a name="section1944313158364"></a>

本节以nginx为例，说明kubectl命令实现ingress访问的方法。

**前提条件**

请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令，使弹性云服务器连接集群。

**操作步骤**

1.  登录已配置好kubectl命令的弹性云服务器。登录方法请参见[登录Linux弹性云服务器](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0013771089.html)。
2.  创建ingress-test-deployment.yaml、ingress-test-svc.yaml、ingress-test-ingress.yaml以及ingress-test-secret.yaml文件。

    ingress-test-deployment.yaml、ingress-test-svc.yaml、ingress-test-ingress.yaml、ingress-test-secret.yaml为自定义名称，您可以随意命名。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   选择HTTPS协议时，才需要创建密钥证书ingress-test-secret.yaml。创建密钥的方法请参见[创建密钥](创建密钥.md)。  
    >-   同一个ELB实例的同一个端口配置HTTPS时，选择的证书需要是一样的。  

    **vi ingress-test-deployment.yaml**

    ```
    apiVersion: extensions/v1beta1
    kind: Deployment
    metadata:
      name: ingress-test-deployment
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: ingress-test-deployment
      strategy:
        type: RollingUpdate
      template:
        metadata:
          labels:
            app: ingress-test-deployment
        spec:
          containers:
            #第三方公开镜像，可以参见描述获取地址，也可以使用自己的镜像
          - image: ingress  
            imagePullPolicy: Always
            name: ingress
            imagePullSecrets:
            - name: default-secret
    ```

    **vi ingress-test-svc.yaml**

    ```
    apiVersion: v1 
    kind: Service 
    metadata: 
      labels: 
        app: ingress-test-svc
      name: ingress-test-svc
    spec: 
      ports: 
      - name: service0 
        port: 8888
        protocol: TCP 
        targetPort: 8888       #若需要设置多个端口，可依次填写，如下展示
      - name: service1 
        port: 8081 
        protocol: TCP 
        targetPort: 8081
      selector: 
        app: ingress-test-deployment
      type:  NodePort
    ```

    **表 2**  关键参数说明

    <a name="table1819001615355"></a>
    <table><thead align="left"><tr id="row1519121663519"><th class="cellrowborder" valign="top" width="30.316968303169684%" id="mcps1.2.4.1.1"><p id="p18191161619356"><a name="p18191161619356"></a><a name="p18191161619356"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.088191180881914%" id="mcps1.2.4.1.2"><p id="p1191141613357"><a name="p1191141613357"></a><a name="p1191141613357"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="51.594840515948405%" id="mcps1.2.4.1.3"><p id="p1919116161353"><a name="p1919116161353"></a><a name="p1919116161353"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row15191171618357"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p5788113218236"><a name="p5788113218236"></a><a name="p5788113218236"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p54093956"><a name="zh-cn_topic_0079615000_p54093956"></a><a name="zh-cn_topic_0079615000_p54093956"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p167881320237"><a name="p167881320237"></a><a name="p167881320237"></a>集群虚拟IP的访问端口，取值范围为1 ~ 65535。</p>
    </td>
    </tr>
    <tr id="row81941516153513"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615000_p11039195"><a name="zh-cn_topic_0079615000_p11039195"></a><a name="zh-cn_topic_0079615000_p11039195"></a>protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p17699892"><a name="zh-cn_topic_0079615000_p17699892"></a><a name="zh-cn_topic_0079615000_p17699892"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p835181810259"><a name="p835181810259"></a><a name="p835181810259"></a>该端口的IP协议，支持“TCP”和“UDP”。</p>
    </td>
    </tr>
    <tr id="row201957167350"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615000_p53639231"><a name="zh-cn_topic_0079615000_p53639231"></a><a name="zh-cn_topic_0079615000_p53639231"></a>targetPort</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p8117426"><a name="zh-cn_topic_0079615000_p8117426"></a><a name="zh-cn_topic_0079615000_p8117426"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1262218433513"><a name="p1262218433513"></a><a name="p1262218433513"></a>对应界面上的容器端口，应用程序实际监听的端口，取值范围为1 ~ 65535。</p>
    </td>
    </tr>
    <tr id="row02694357138"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p6716134816295"><a name="p6716134816295"></a><a name="p6716134816295"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p18968549"><a name="zh-cn_topic_0079615000_p18968549"></a><a name="zh-cn_topic_0079615000_p18968549"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p13717148202913"><a name="p13717148202913"></a><a name="p13717148202913"></a>采用Nodeport的访问类型连接负载均衡，NodePort表示“节点私有IP”。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **vi ingress-test-ingress.yaml**

    -   自动创建ELB

        ```
        apiVersion: extensions/v1beta1 
        kind: Ingress 
        metadata: 
          annotations: 
            kubernetes.io/elb.subnet-id: 29a0567e-96f1-4227-91cc-64f54d0b064d
            kubernetes.io/elb.enterpriseID: f6b9fffc-a9b7-4a50-a25e-364f587abe44
            kubernetes.io/elb.autocreate: '{"type":"public","bandwidth_name":"cce-bandwidth-1551163379627","bandwidth_chargemode":"bandwidth","bandwidth_size":5,"bandwidth_sharetype":"PER","eip_type":"5_bgp","name":"james"}'
            kubernetes.io/elb.port: "80"
            kubernetes.io/ingress.class: cce
          name: ingress-test-ingress
        spec:
          tls:
          - secretName: ingress-test-secret
          rules: 
          - http: 
              paths: 
              - backend: 
                  serviceName: ingress-test-svc
                  servicePort: 8888
                property:
                  ingress.beta.kubernetes.io/url-match-mode: EQUAL_TO
                path: "/healthz"
            host: ingress.com
        ```

    -   使用已有ELB

        ```
        apiVersion: extensions/v1beta1 
        kind: Ingress 
        metadata: 
          annotations: 
            kubernetes.io/elb.id: f7891f9a-49f2-4ee2-b1ae-f019cd84eb4f
            kubernetes.io/elb.ip: 192.168.0.39
            kubernetes.io/elb.subnet-id: 29a0567e-96f1-4227-91cc-64f54d0b064d
            kubernetes.io/elb.port: "80"
            kubernetes.io/ingress.class: cce
          name: ingress-test-ingress
        spec:
          tls:
          - secretName: ingress-test-secret
          rules: 
          - http: 
              paths: 
              - backend: 
                  serviceName: ingress-test-svc
                  servicePort: 8888
                property:
                  ingress.beta.kubernetes.io/url-match-mode: EQUAL_TO
                path: "/healthz"
            host: ingress.com
        ```

        **表 3**  关键参数说明

        <a name="table1732315519222"></a>
        <table><thead align="left"><tr id="row43239510228"><th class="cellrowborder" valign="top" width="29.727027297270276%" id="mcps1.2.4.1.1"><p id="p3323185142214"><a name="p3323185142214"></a><a name="p3323185142214"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="18.678132186781323%" id="mcps1.2.4.1.2"><p id="p1632315162219"><a name="p1632315162219"></a><a name="p1632315162219"></a>参数类型</p>
        </th>
        <th class="cellrowborder" valign="top" width="51.594840515948405%" id="mcps1.2.4.1.3"><p id="p2323105202212"><a name="p2323105202212"></a><a name="p2323105202212"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1932315519221"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p11323551220"><a name="p11323551220"></a><a name="p11323551220"></a>kubernetes.io/elb.id</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p43232502212"><a name="p43232502212"></a><a name="p43232502212"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1532419502210"><a name="p1532419502210"></a><a name="p1532419502210"></a>可选，但使用已有ELB时必填。</p>
        <p id="p1832435142216"><a name="p1832435142216"></a><a name="p1832435142216"></a>为增强型负载均衡实例的ID。</p>
        </td>
        </tr>
        <tr id="row19324185132210"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p143241054227"><a name="p143241054227"></a><a name="p143241054227"></a>kubernetes.io/elb.ip</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p63241755223"><a name="p63241755223"></a><a name="p63241755223"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1232410519221"><a name="p1232410519221"></a><a name="p1232410519221"></a>可选，但当elb自动创建时不填。</p>
        <p id="p123246513225"><a name="p123246513225"></a><a name="p123246513225"></a>为负载均衡增强型实例的服务地址，公网ELB配置为公网IP，私网ELB配置为私网IP。</p>
        </td>
        </tr>
        <tr id="row113242512217"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p1332415102211"><a name="p1332415102211"></a><a name="p1332415102211"></a>kubernetes.io/elb.subnet-id</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p16324185192216"><a name="p16324185192216"></a><a name="p16324185192216"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p6324185202213"><a name="p6324185202213"></a><a name="p6324185202213"></a>可选，但自动创建时必填，Kubernetes v1.11.7-r0以上版本的集群可不填。</p>
        </td>
        </tr>
        <tr id="row135515812311"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p443916465535"><a name="p443916465535"></a><a name="p443916465535"></a>kubernetes.io/elb.enterpriseID</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p164393463532"><a name="p164393463532"></a><a name="p164393463532"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1843954617535"><a name="p1843954617535"></a><a name="p1843954617535"></a>可选，但公网或私网自动创建时必填。</p>
        <p id="p439419360561"><a name="p439419360561"></a><a name="p439419360561"></a>为ELB企业项目名称，选择后可以直接创建在具体的ELB企业项目下。</p>
        </td>
        </tr>
        <tr id="row14324115112219"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p163241552218"><a name="p163241552218"></a><a name="p163241552218"></a>kubernetes.io/elb.autocreate</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p163247517229"><a name="p163247517229"></a><a name="p163247517229"></a><a href="#table19417184671919">elb.autocreate</a> object</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p03246532210"><a name="p03246532210"></a><a name="p03246532210"></a>可选，但公网自动创建时必填，将自动创建ELB所绑定的EIP。私网自动创建时必填，将自动创建ELB。</p>
        <p id="p13324858222"><a name="p13324858222"></a><a name="p13324858222"></a><strong id="b932418520225"><a name="b932418520225"></a><a name="b932418520225"></a>示例：</strong></p>
        <a name="ul16324853220"></a><a name="ul16324853220"></a><ul id="ul16324853220"><li>公网自动创建：<p id="p1675515917379"><a name="p1675515917379"></a><a name="p1675515917379"></a>值为 '{"type":"public","bandwidth_name":"cce-bandwidth-1551163379627","bandwidth_chargemode":"bandwidth","bandwidth_size":5,"bandwidth_sharetype":"PER","eip_type":"5_bgp","name":"james"}'</p>
        </li><li>私网自动创建：<p id="p15211191416376"><a name="p15211191416376"></a><a name="p15211191416376"></a>值为 '{"type":"inner", "name": "A-location-d-test"}'</p>
        </li></ul>
        </td>
        </tr>
        <tr id="row332514515229"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p232519512211"><a name="p232519512211"></a><a name="p232519512211"></a>kubernetes.io/elb.port</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p173251458226"><a name="p173251458226"></a><a name="p173251458226"></a>Integer</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p93251554223"><a name="p93251554223"></a><a name="p93251554223"></a>必填，界面上的对外端口，为注册到负载均衡服务地址上的端口。</p>
        </td>
        </tr>
        <tr id="row1432518511224"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p1432565182214"><a name="p1432565182214"></a><a name="p1432565182214"></a>kubernetes.io/ingress.class</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1232514542215"><a name="p1232514542215"></a><a name="p1232514542215"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p13251456223"><a name="p13251456223"></a><a name="p13251456223"></a>默认，cce时表示使用增强型负载均衡实例，nginx时表示启用nginx-ingress插件。但通过API接口创建Ingress时必须增加该参数。</p>
        </td>
        </tr>
        <tr id="row143251551229"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p18325951228"><a name="p18325951228"></a><a name="p18325951228"></a>tls</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1832513582216"><a name="p1832513582216"></a><a name="p1832513582216"></a>Array of strings</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p53262562220"><a name="p53262562220"></a><a name="p53262562220"></a>可选，HTTPS协议时，需添加此参数。</p>
        </td>
        </tr>
        <tr id="row6326185152213"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p5326145202219"><a name="p5326145202219"></a><a name="p5326145202219"></a>secretName</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p5326135162216"><a name="p5326135162216"></a><a name="p5326135162216"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1732645172213"><a name="p1732645172213"></a><a name="p1732645172213"></a>可选，HTTPS协议时添加，配置为创建的密钥证书名称。</p>
        </td>
        </tr>
        <tr id="row33265552211"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p1432685102213"><a name="p1432685102213"></a><a name="p1432685102213"></a>serviceName</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1632617511229"><a name="p1632617511229"></a><a name="p1632617511229"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p17326135102219"><a name="p17326135102219"></a><a name="p17326135102219"></a>为ingress-test-svc.yaml的服务名称。</p>
        </td>
        </tr>
        <tr id="row1232616516229"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p16326052225"><a name="p16326052225"></a><a name="p16326052225"></a>servicePort</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p23264582215"><a name="p23264582215"></a><a name="p23264582215"></a>Integer</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p53261152221"><a name="p53261152221"></a><a name="p53261152221"></a>为ingress-test-svc.yaml的Port。</p>
        </td>
        </tr>
        <tr id="row1732620510228"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p12326195152216"><a name="p12326195152216"></a><a name="p12326195152216"></a>ingress.beta.kubernetes.io/url-match-mode</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1232675172211"><a name="p1232675172211"></a><a name="p1232675172211"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p16327755228"><a name="p16327755228"></a><a name="p16327755228"></a>路由匹配策略，可选值为EQUAL_TO（精确匹配）、STARTS_WITH(前缀匹配)、REGEX（正则匹配）。</p>
        </td>
        </tr>
        <tr id="row19327205202214"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p83279511221"><a name="p83279511221"></a><a name="p83279511221"></a>path</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p932711582211"><a name="p932711582211"></a><a name="p932711582211"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p173278515229"><a name="p173278515229"></a><a name="p173278515229"></a>为路由，用户自定义设置。</p>
        </td>
        </tr>
        <tr id="row16327451221"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p832714513227"><a name="p832714513227"></a><a name="p832714513227"></a>host</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1532718517223"><a name="p1532718517223"></a><a name="p1532718517223"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p53272572218"><a name="p53272572218"></a><a name="p53272572218"></a>可选，域名配置。</p>
        </td>
        </tr>
        </tbody>
        </table>

        **表 4**  elb.autocreate字段数据结构说明

        <a name="table19417184671919"></a>
        <table><thead align="left"><tr id="row14418174611912"><th class="cellrowborder" valign="top" width="29.727027297270276%" id="mcps1.2.4.1.1"><p id="p1141924611199"><a name="p1141924611199"></a><a name="p1141924611199"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="18.678132186781323%" id="mcps1.2.4.1.2"><p id="p1641911466191"><a name="p1641911466191"></a><a name="p1641911466191"></a>参数类型</p>
        </th>
        <th class="cellrowborder" valign="top" width="51.594840515948405%" id="mcps1.2.4.1.3"><p id="p1941920463197"><a name="p1941920463197"></a><a name="p1941920463197"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row194191846181915"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p152321411112318"><a name="p152321411112318"></a><a name="p152321411112318"></a>name</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p7419646171920"><a name="p7419646171920"></a><a name="p7419646171920"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p87791494919"><a name="p87791494919"></a><a name="p87791494919"></a>自动创建的负载均衡的名称。</p>
        <p id="p9912132016296"><a name="p9912132016296"></a><a name="p9912132016296"></a>取值范围：1-64个字符，中英文，数字，下划线，中划线。</p>
        </td>
        </tr>
        <tr id="row142064681919"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p20862285225"><a name="p20862285225"></a><a name="p20862285225"></a>type</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p8420746101918"><a name="p8420746101918"></a><a name="p8420746101918"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p4703183013491"><a name="p4703183013491"></a><a name="p4703183013491"></a>负载均衡实例网络类型，公网或者私网。</p>
        <a name="ul152311045124913"></a><a name="ul152311045124913"></a><ul id="ul152311045124913"><li>public：公网型负载均衡</li><li>inner：私网型负载均衡</li></ul>
        </td>
        </tr>
        <tr id="row194201046151910"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p128042817221"><a name="p128042817221"></a><a name="p128042817221"></a>bandwidth_name</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1142084619195"><a name="p1142084619195"></a><a name="p1142084619195"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p6964103318220"><a name="p6964103318220"></a><a name="p6964103318220"></a>带宽的名称，默认值为：cce-bandwidth-******。</p>
        <p id="p1236952875020"><a name="p1236952875020"></a><a name="p1236952875020"></a>1-64 字符，中文、英文字符、数字、下划线、中划线或点组成。</p>
        </td>
        </tr>
        <tr id="row942194619199"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p77502811221"><a name="p77502811221"></a><a name="p77502811221"></a>bandwidth_chargemode</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p11421446191914"><a name="p11421446191914"></a><a name="p11421446191914"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p3178181495216"><a name="p3178181495216"></a><a name="p3178181495216"></a>带宽付费模式。</p>
        <a name="ul567215235528"></a><a name="ul567215235528"></a><ul id="ul567215235528"><li>bandwidth：按带宽计费</li><li>traffic：按流量计费</li></ul>
        </td>
        </tr>
        <tr id="row124211046101910"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p187492819229"><a name="p187492819229"></a><a name="p187492819229"></a>bandwidth_size</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p114229463196"><a name="p114229463196"></a><a name="p114229463196"></a>Integer</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p12958233152218"><a name="p12958233152218"></a><a name="p12958233152218"></a>带宽大小，请根据Region带宽支持范围设置，具体请参见<a href="https://support.huaweicloud.com/api-vpc/zh-cn_topic_0020090596.html#ZH-CN_TOPIC_0020090596__table11041789" target="_blank" rel="noopener noreferrer">申请弹性公网IP</a>中<strong id="b198591928137"><a name="b198591928137"></a><a name="b198591928137"></a>表4 bandwidth字段说明中size字段</strong>。</p>
        </td>
        </tr>
        <tr id="row1942224601917"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p16731228202214"><a name="p16731228202214"></a><a name="p16731228202214"></a>bandwidth_sharetype</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p84221246111913"><a name="p84221246111913"></a><a name="p84221246111913"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p188864421731"><a name="p188864421731"></a><a name="p188864421731"></a>带宽共享方式。</p>
        <a name="ul51872412"></a><a name="ul51872412"></a><ul id="ul51872412"><li>PER：共享带宽</li><li>WHOLE：共享带宽</li></ul>
        </td>
        </tr>
        <tr id="row1242219461193"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p1972102872220"><a name="p1972102872220"></a><a name="p1972102872220"></a>eip_type</p>
        </td>
        <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p132201811174611"><a name="p132201811174611"></a><a name="p132201811174611"></a>String</p>
        </td>
        <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p11956103372218"><a name="p11956103372218"></a><a name="p11956103372218"></a>弹性公网IP类型，请参考ELB支持的弹性公网IP类型，具体请参见<a href="https://support.huaweicloud.com/api-vpc/zh-cn_topic_0020090596.html#ZH-CN_TOPIC_0020090596__table11041789" target="_blank" rel="noopener noreferrer">申请弹性公网IP</a>中<strong id="b11814520410"><a name="b11814520410"></a><a name="b11814520410"></a>表3 publicip字段说明type字段</strong>。</p>
        </td>
        </tr>
        </tbody>
        </table>

        **vi ingress-test-secret.yaml**

        ```
        apiVersion: v1
        data:
          tls.crt: LS0******tLS0tCg==
          tls.key: LS0tL******0tLS0K
        kind: Secret
        metadata:
          annotations:
            description: test for ingressTLS secrets
          name: ingress-test-secret
          namespace: default
        type: IngressTLS
        ```

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >此处tls.crt和tls.key为示例，请获取真实密钥进行替换。  


3.  创建工作负载。

    **kubectl create -f  ingress-test-deployment.yaml**

    回显如下，表明工作负载已创建。

    ```
    deployment "ingress-test-deployment" created
    ```

    **kubectl get po**

    回显如下，表明工作负载创建成功。

    ```
    NAME                            READY     STATUS             RESTARTS   AGE
    ingress-test-1627801589-r64pk   1/1       Running            0          6s
    ```

4.  创建密钥。

    **kubectl create -f  **ingress-test-secret.yaml****

    回显如下，表明密钥已创建。

    ```
    secret "ingress-test-secret" created
    ```

    **kubectl get secrets**

    回显如下，表明密钥创建成功。

    ```
    NAME                         TYPE                                  DATA      AGE
    dash-dashboard               Opaque                                0         7d
    dash-dashboard-token-f2nbk   kubernetes.io/service-account-token   3         7d
    default-secret               kubernetes.io/dockerconfigjson        1         8d
    default-token-wfn4l          kubernetes.io/service-account-token   3         8d
    paas.elb                     cfe/secure-opaque                     2         8d
    ingress-test-secret          IngressTLS                            2         13s
    ```

5.  创建服务。

    **kubectl create -f ingress-test-svc.yaml**

    回显如下，表示服务已创建。

    ```
    service "ingress-test-svc" created
    ```

    **kubectl get svc**

    回显如下，表示服务创建成功。

    ```
    NAME            TYPE          CLUSTER-IP        EXTERNAL-IP   PORT(S)          AGE
    ingress-test    NodePort      10.247.189.207    <none>       8080:30532/TCP   5s
    kubernetes      ClusterIP     10.247.0.1        <none>        443/TCP          3d
    ```

    **kubectl create -f ingress-test-ingress.yaml**

    回显如下，表示ingress服务已创建。

    ```
    ingress "ingress-test-ingress" created
    ```

    **kubectl get ingress**

    回显如下，表示ingress服务创建成功，工作负载可访问。

    ```
    NAME             HOSTS     ADDRESS          PORTS   AGE
    ingress-test     *         10.154.76.63     80      10s
    ```

6.  在浏览器中输入访问地址http://10.154.76.63/healthz。

    其中，10.154.76.63为统一负载均衡实例的IP地址。

    **图 5**  访问healthz<a name="fig1526153112115"></a>  
    ![](figures/访问healthz.png "访问healthz")


## 更新Ingress<a name="section1071722525415"></a>

您可以在添加完Ingress后，更新此Ingress的端口、域名和路由配置。操作如下：

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“资源管理 \> 网络管理”。在**Ingress**页签下，选择对应的集群和命名空间，单击待更新Ingress后方的“更新”。
2.  在“更新Ingress“页面，更新如下参数：
    -   **对外端口：**开放在负载均衡服务地址的端口，可任意指定。
    -   **域名：**可选填。实际访问的域名地址，该域名需用户购买并备案，并确保所填域名能解析到所选负载均衡实例的服务地址。一旦配置了域名规则，则必须使用域名访问。
    -   **路由配置：**可单击“添加映射”增加新的路由配置。
        -   路由匹配规则：前缀匹配、精确匹配、正则匹配。
            -   前缀匹配：例如映射URL为/healthz，只要符合此前缀的URL均可访问。例如/healthz/v1，/healthz/v2。
            -   精确匹配：表示精准匹配，只有完全匹配上才能生效。例如映射URL为/healthz，则必须为此URL才能访问。
            -   正则匹配：可设定映射URL规范，例如规范为**/\[A-Za-z0-9\_.-\]+/test**。只要符合此规则的URL均可访问，例如/abcA9/test，/v1-Ab/test。正则匹配规则支持POSIX与Perl两种标准。

        -   映射URL：需要注册的访问路径，例如：/healthz。
        -   服务名称：选择需要添加Ingress的服务，该服务访问类型为VPC内网服务。
        -   容器端口：容器镜像中容器实际监听端口，需用户确定。例如：defaultbackend程序实际监听的端口为8080。

3.  单击“提交”。工作负载已更新Ingress。

## 相关操作<a name="section132063911129"></a>

由于社区Ingress结构体中没有property属性，用户使用client-go调用创建ingress的api接口时，创建的Ingress中没有property属性。为了与社区的client-go兼容，CCE提供了相关解决方案，具体请参见[Ingress中的property字段与社区client-go兼容](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_0042.html)。

