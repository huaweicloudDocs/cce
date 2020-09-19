# 通过Kubectl命令行创建Ingress<a name="cce_01_0252"></a>

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
          - image: nginx 
            imagePullPolicy: Always
            name: nginx
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

    **表 1**  关键参数说明

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

    -   1.15及以上集群版本中的apiVersion为: networking.k8s.io/v1beta1
    -   1.13及以下集群版本中的apiVersion为: extensions/v1beta1

    自动创建ELB

    ```
    apiVersion: networking.k8s.io/v1beta1
    kind: Ingress 
    metadata: 
      annotations: 
        kubernetes.io/elb.subnet-id: 29a0567e-96f1-4227-91cc-64f54d0b064d
        kubernetes.io/elb.enterpriseID: f6b9fffc-a9b7-4a50-a25e-364f587abe44
        kubernetes.io/elb.autocreate: '{"type":"public","bandwidth_name":"cce-bandwidth-1551163379627","bandwidth_chargemode":"bandwidth","bandwidth_size":5,"bandwidth_sharetype":"PER","eip_type":"5_bgp","name":"james"}'
        kubernetes.io/elb.tls-ciphers-policy: tls-1-2
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

    使用已有ELB

    ```
    apiVersion: networking.k8s.io/v1beta1
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

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >安全策略选择（kubernetes.io/elb.tls-ciphers-policy）将在近期上线。

    **表 2**  关键参数说明

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
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1532419502210"><a name="p1532419502210"></a><a name="p1532419502210"></a>为共享型负载均衡实例的ID，取值范围：1-100字符。</p>
    <a name="ul18514172511463"></a><a name="ul18514172511463"></a><ul id="ul18514172511463"><li>在自动创建时：可选。</li><li>在关联已有ELB时：必填。</li></ul>
    <p id="p14913235171018"><a name="p14913235171018"></a><a name="p14913235171018"></a><strong id="b533215484103"><a name="b533215484103"></a><a name="b533215484103"></a>获取方法：</strong></p>
    <p id="p1832435142216"><a name="p1832435142216"></a><a name="p1832435142216"></a>在控制台的<span class="uicontrol" id="uicontrol8385124317594"><a name="uicontrol8385124317594"></a><a name="uicontrol8385124317594"></a>“服务列表”</span>中，单击<span class="uicontrol" id="uicontrol12432719902"><a name="uicontrol12432719902"></a><a name="uicontrol12432719902"></a>“网络 &gt; 弹性负载均衡 ELB”</span>，单击ELB的名称，在ELB详情页的<span class="uicontrol" id="uicontrol762734213311"><a name="uicontrol762734213311"></a><a name="uicontrol762734213311"></a>“基本信息”</span>页签下找到<span class="uicontrol" id="uicontrol1139664010108"><a name="uicontrol1139664010108"></a><a name="uicontrol1139664010108"></a>“ID”</span>字段复制即可。</p>
    </td>
    </tr>
    <tr id="row19324185132210"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p143241054227"><a name="p143241054227"></a><a name="p143241054227"></a>kubernetes.io/elb.ip</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p63241755223"><a name="p63241755223"></a><a name="p63241755223"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1232410519221"><a name="p1232410519221"></a><a name="p1232410519221"></a>可选，但当elb自动创建时不填。</p>
    <p id="p123246513225"><a name="p123246513225"></a><a name="p123246513225"></a>为共享型负载均衡实例的服务地址，公网ELB配置为公网IP，私网ELB配置为私网IP。</p>
    </td>
    </tr>
    <tr id="row113242512217"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p1332415102211"><a name="p1332415102211"></a><a name="p1332415102211"></a>kubernetes.io/elb.subnet-id</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p16324185192216"><a name="p16324185192216"></a><a name="p16324185192216"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p9695142617472"><a name="p9695142617472"></a><a name="p9695142617472"></a>为子网的ID，取值范围：1-100字符。</p>
    <a name="ul17340104499"></a><a name="ul17340104499"></a><ul id="ul17340104499"><li>Kubernetes v1.11.7-r0及以下版本的集群自动创建时：必填，</li><li>Kubernetes v1.11.7-r0以上版本的集群：可不填。</li></ul>
    <p id="p6324185202213"><a name="p6324185202213"></a><a name="p6324185202213"></a>获取方法请参见：<a href="https://support.huaweicloud.com/api-vpc/vpc_api_0005.html" target="_blank" rel="noopener noreferrer">VPC子网接口与OpenStack Neutron子网接口的区别是什么？</a></p>
    </td>
    </tr>
    <tr id="row87776149020"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p1577817142004"><a name="p1577817142004"></a><a name="p1577817142004"></a>kubernetes.io/elb.eip-id</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p97788148014"><a name="p97788148014"></a><a name="p97788148014"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p10958226114910"><a name="p10958226114910"></a><a name="p10958226114910"></a>为弹性公网的ID，取值范围：1-100字符。</p>
    <a name="ul1459701465115"></a><a name="ul1459701465115"></a><ul id="ul1459701465115"><li>非自动创建elb时：可选。</li><li>自动创建elb时：不填。</li></ul>
    <p id="p98341426575"><a name="p98341426575"></a><a name="p98341426575"></a><strong id="b1350019315539"><a name="b1350019315539"></a><a name="b1350019315539"></a>获取方法：</strong></p>
    <p id="p217113461975"><a name="p217113461975"></a><a name="p217113461975"></a>在控制台的“服务列表”中，单击“网络 &gt; 弹性公网IP EIP”，单击EIP的名称，在EIP详情页的“基本信息”中找到“ID”字段复制即可。</p>
    </td>
    </tr>
    <tr id="row135515812311"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p443916465535"><a name="p443916465535"></a><a name="p443916465535"></a>kubernetes.io/elb.enterpriseID</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p164393463532"><a name="p164393463532"></a><a name="p164393463532"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p16861422181410"><a name="p16861422181410"></a><a name="p16861422181410"></a>可选，为ELB企业项目ID，选择后可以直接创建在具体的ELB企业项目下。</p>
    <p id="p86261431205112"><a name="p86261431205112"></a><a name="p86261431205112"></a>取值范围：1-100字符。</p>
    <p id="p9823163591414"><a name="p9823163591414"></a><a name="p9823163591414"></a><strong id="b646493811412"><a name="b646493811412"></a><a name="b646493811412"></a>获取方法：</strong></p>
    <p id="p439419360561"><a name="p439419360561"></a><a name="p439419360561"></a>在CCE控制台中，单击<span class="uicontrol" id="uicontrol115051445181018"><a name="uicontrol115051445181018"></a><a name="uicontrol115051445181018"></a>“资源管理 &gt; 集群管理”</span>，单击集群名称进入集群详情页，在左侧的基本信息中单击企业项目的名称，进入企业项目详情页，找到<span class="uicontrol" id="uicontrol7221153491020"><a name="uicontrol7221153491020"></a><a name="uicontrol7221153491020"></a>“ID”</span>字段复制即可。</p>
    </td>
    </tr>
    <tr id="row895420391888"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p18244154711811"><a name="p18244154711811"></a><a name="p18244154711811"></a>kubernetes.io/elb.session-affinity-mode</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p024434718814"><a name="p024434718814"></a><a name="p024434718814"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p10253947153813"><a name="p10253947153813"></a><a name="p10253947153813"></a>可选，负载均衡监听是基于IP地址的会话保持，即来自同一IP地址的访问请求转发到同一台后端服务器上。</p>
    <a name="ul75841719426"></a><a name="ul75841719426"></a><ul id="ul75841719426"><li>不启用：不填写该参数。</li><li>开启会话保持：需增加该参数，取值“SOURCE_IP”，表示基于源IP地址。</li></ul>
    </td>
    </tr>
    <tr id="row11167337989"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p12244124711810"><a name="p12244124711810"></a><a name="p12244124711810"></a>kubernetes.io/elb.session-affinity-option</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p024414476811"><a name="p024414476811"></a><a name="p024414476811"></a><a href="#table1920573716128">表4</a> Object</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p102448476816"><a name="p102448476816"></a><a name="p102448476816"></a>可选，七层负载均衡会话保持配置选项。</p>
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
    <tr id="row12156124511919"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p7499172101013"><a name="p7499172101013"></a><a name="p7499172101013"></a>kubernetes.io/elb.lb-algorithm</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p649915218108"><a name="p649915218108"></a><a name="p649915218108"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p54991723102"><a name="p54991723102"></a><a name="p54991723102"></a>可选，默认值：“ROUND_ROBIN”，为后端云服务器组的负载均衡算法。</p>
    <p id="p2243151782218"><a name="p2243151782218"></a><a name="p2243151782218"></a>取值范围：</p>
    <a name="ul103391736202217"></a><a name="ul103391736202217"></a><ul id="ul103391736202217"><li>ROUND_ROBIN：加权轮询算法。</li><li>LEAST_CONNECTIONS：加权最少连接算法。</li><li>SOURCE_IP：源IP算法。</li></ul>
    <p id="p15243917162217"><a name="p15243917162217"></a><a name="p15243917162217"></a>当该字段的取值为SOURCE_IP时，后端云服务器组绑定的后端云服务器的weight字段无效。</p>
    </td>
    </tr>
    <tr id="row25968422094"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p44993217106"><a name="p44993217106"></a><a name="p44993217106"></a>kubernetes.io/elb.health-check-flag</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1249992101014"><a name="p1249992101014"></a><a name="p1249992101014"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p177202225524"><a name="p177202225524"></a><a name="p177202225524"></a>可选，默认开启，为是否开启ELB健康检查功能。</p>
    <a name="ul141265119581"></a><a name="ul141265119581"></a><ul id="ul141265119581"><li>开启：“”（空值）或“on”</li><li>关闭：“off”</li></ul>
    </td>
    </tr>
    <tr id="row68009391914"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p15499152161017"><a name="p15499152161017"></a><a name="p15499152161017"></a>kubernetes.io/elb.health-check-option</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p5499822109"><a name="p5499822109"></a><a name="p5499822109"></a><a href="#table329102513130">表5</a> Object</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p114991826105"><a name="p114991826105"></a><a name="p114991826105"></a>可选，ELB健康检查配置选项。</p>
    </td>
    </tr>
    <tr id="row2077834792815"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p91694415438"><a name="p91694415438"></a><a name="p91694415438"></a>kubernetes.io/elb.tls-ciphers-policy</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1778447202813"><a name="p1778447202813"></a><a name="p1778447202813"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p11778147112810"><a name="p11778147112810"></a><a name="p11778147112810"></a>可选，默认值：“tls-1-2”, 为监听器使用的安全策略，仅在HTTPS协议下生效。</p>
    <p id="p1624920113387"><a name="p1624920113387"></a><a name="p1624920113387"></a>取值范围：</p>
    <a name="ul2055451911387"></a><a name="ul2055451911387"></a><ul id="ul2055451911387"><li>tls-1-0-inherit</li><li>tls-1-0</li><li>tls-1-</li><li>tls-1-2</li><li>tls-1-2-strict</li></ul>
    <p id="p17848163214417"><a name="p17848163214417"></a><a name="p17848163214417"></a>各安全策略使用的加密套件列表详细参见<a href="#table315082934512">表6</a></p>
    </td>
    </tr>
    <tr id="row332514515229"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p232519512211"><a name="p232519512211"></a><a name="p232519512211"></a>kubernetes.io/elb.port</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p173251458226"><a name="p173251458226"></a><a name="p173251458226"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p93251554223"><a name="p93251554223"></a><a name="p93251554223"></a>必填，界面上的对外端口，为注册到负载均衡服务地址上的端口。</p>
    <p id="p24291925171020"><a name="p24291925171020"></a><a name="p24291925171020"></a>取值范围：1-65535。</p>
    </td>
    </tr>
    <tr id="row1432518511224"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p1432565182214"><a name="p1432565182214"></a><a name="p1432565182214"></a>kubernetes.io/ingress.class</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1232514542215"><a name="p1232514542215"></a><a name="p1232514542215"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p4738183193916"><a name="p4738183193916"></a><a name="p4738183193916"></a>是否开启nginx-ingress插件。</p>
    <a name="ul20247158154013"></a><a name="ul20247158154013"></a><ul id="ul20247158154013"><li>cce：表示不开启nginx-ingress插件，将默认使用共享型负载均衡实例。</li><li>nginx：表示开启nginx-ingress插件。</li></ul>
    <p id="p13251456223"><a name="p13251456223"></a><a name="p13251456223"></a>通过API接口创建Ingress时必须增加该参数。</p>
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
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1017425211255"><a name="p1017425211255"></a><a name="p1017425211255"></a>可选，路由匹配策略。</p>
    <p id="p552354022316"><a name="p552354022316"></a><a name="p552354022316"></a>默认值：STARTS_WITH(前缀匹配)。</p>
    <p id="p18550124318232"><a name="p18550124318232"></a><a name="p18550124318232"></a>取值范围：</p>
    <a name="ul5804181111244"></a><a name="ul5804181111244"></a><ul id="ul5804181111244"><li>EQUAL_TO：精确匹配</li><li>STARTS_WITH：前缀匹配</li><li>REGEX：正则匹配</li></ul>
    </td>
    </tr>
    <tr id="row19327205202214"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p83279511221"><a name="p83279511221"></a><a name="p83279511221"></a>path</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p932711582211"><a name="p932711582211"></a><a name="p932711582211"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p173278515229"><a name="p173278515229"></a><a name="p173278515229"></a>必填，为路由路径，用户自定义设置。</p>
    </td>
    </tr>
    <tr id="row16327451221"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p832714513227"><a name="p832714513227"></a><a name="p832714513227"></a>host</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1532718517223"><a name="p1532718517223"></a><a name="p1532718517223"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p53272572218"><a name="p53272572218"></a><a name="p53272572218"></a>可选，为域名配置。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 3**  elb.autocreate字段数据结构说明

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
    <p id="p9912132016296"><a name="p9912132016296"></a><a name="p9912132016296"></a>取值范围：1-64个字符，小写字母，数字，下划线，小写字母开头，小写字母或者数字结尾。</p>
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
    <p id="p1236952875020"><a name="p1236952875020"></a><a name="p1236952875020"></a>取值范围：1-64个字符，小写字母，数字，下划线，小写字母开头，小写字母或者数字结尾。</p>
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
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p12958233152218"><a name="p12958233152218"></a><a name="p12958233152218"></a>带宽大小，请根据Region带宽支持范围设置，具体请参见<a href="https://support.huaweicloud.com/api-eip/eip_api_0001.html" target="_blank" rel="noopener noreferrer">申请弹性公网IP</a>中<strong id="b198591928137"><a name="b198591928137"></a><a name="b198591928137"></a>表4 bandwidth字段说明中size字段</strong>。</p>
    </td>
    </tr>
    <tr id="row1942224601917"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p16731228202214"><a name="p16731228202214"></a><a name="p16731228202214"></a>bandwidth_sharetype</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p84221246111913"><a name="p84221246111913"></a><a name="p84221246111913"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p59311192057"><a name="p59311192057"></a><a name="p59311192057"></a>带宽类型，标识是否是共享带宽。</p>
    <p id="p188864421731"><a name="p188864421731"></a><a name="p188864421731"></a>取值范围：</p>
    <a name="ul51872412"></a><a name="ul51872412"></a><ul id="ul51872412"><li>WHOLE：共享带宽</li><li>PER：独享带宽</li></ul>
    </td>
    </tr>
    <tr id="row1242219461193"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p1972102872220"><a name="p1972102872220"></a><a name="p1972102872220"></a>eip_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p132201811174611"><a name="p132201811174611"></a><a name="p132201811174611"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p11956103372218"><a name="p11956103372218"></a><a name="p11956103372218"></a>弹性公网IP类型，请参考ELB支持的弹性公网IP类型，具体请参见<a href="https://support.huaweicloud.com/api-eip/eip_api_0001.html" target="_blank" rel="noopener noreferrer">申请弹性公网IP</a>中<strong id="b11814520410"><a name="b11814520410"></a><a name="b11814520410"></a>表3 publicip字段说明type字段</strong>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 4**  elb.session-affinity-option字段数据结构说明

    <a name="table1920573716128"></a>
    <table><thead align="left"><tr id="row18242183711210"><th class="cellrowborder" valign="top" width="29.59%" id="mcps1.2.4.1.1"><p id="p132427378126"><a name="p132427378126"></a><a name="p132427378126"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.37%" id="mcps1.2.4.1.2"><p id="p142422376126"><a name="p142422376126"></a><a name="p142422376126"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="52.04%" id="mcps1.2.4.1.3"><p id="p122422371126"><a name="p122422371126"></a><a name="p122422371126"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row52427371121"><td class="cellrowborder" valign="top" width="29.59%" headers="mcps1.2.4.1.1 "><p id="p12242937101214"><a name="p12242937101214"></a><a name="p12242937101214"></a>persistence_timeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p20242837141216"><a name="p20242837141216"></a><a name="p20242837141216"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.04%" headers="mcps1.2.4.1.3 "><p id="p82427374122"><a name="p82427374122"></a><a name="p82427374122"></a>当elb.session-affinity-mode是“HTTP_COOKIE”时生效，设置会话保持的超时时间（秒）。</p>
    <p id="p20242837171210"><a name="p20242837171210"></a><a name="p20242837171210"></a>默认值为：1440，取值范围：1-1440。</p>
    </td>
    </tr>
    <tr id="row15242113720127"><td class="cellrowborder" valign="top" width="29.59%" headers="mcps1.2.4.1.1 "><p id="p13242203711215"><a name="p13242203711215"></a><a name="p13242203711215"></a>app_cookie_name</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p1242133731211"><a name="p1242133731211"></a><a name="p1242133731211"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.04%" headers="mcps1.2.4.1.3 "><p id="p024283711122"><a name="p024283711122"></a><a name="p024283711122"></a>当elb.session-affinity-mode是“APP_COOKIE”时生效，设置会话保持的超时时间（秒）。</p>
    <p id="p16242183761210"><a name="p16242183761210"></a><a name="p16242183761210"></a>取值范围：1-10000字符。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 5**  elb.health-check-option字段数据结构说明

    <a name="table329102513130"></a>
    <table><thead align="left"><tr id="row682132520131"><th class="cellrowborder" valign="top" width="29.59%" id="mcps1.2.4.1.1"><p id="p108210257139"><a name="p108210257139"></a><a name="p108210257139"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.37%" id="mcps1.2.4.1.2"><p id="p1182325201318"><a name="p1182325201318"></a><a name="p1182325201318"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="52.04%" id="mcps1.2.4.1.3"><p id="p1821825151312"><a name="p1821825151312"></a><a name="p1821825151312"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row38212257136"><td class="cellrowborder" valign="top" width="29.59%" headers="mcps1.2.4.1.1 "><p id="p18262501315"><a name="p18262501315"></a><a name="p18262501315"></a>delay</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p17821525191319"><a name="p17821525191319"></a><a name="p17821525191319"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.04%" headers="mcps1.2.4.1.3 "><p id="p198272515131"><a name="p198272515131"></a><a name="p198272515131"></a>开始健康检查的初始等待时间（秒），可选</p>
    <p id="p1282625141318"><a name="p1282625141318"></a><a name="p1282625141318"></a>默认值：5，取值范围：1-50</p>
    </td>
    </tr>
    <tr id="row118282511139"><td class="cellrowborder" valign="top" width="29.59%" headers="mcps1.2.4.1.1 "><p id="p1582122531317"><a name="p1582122531317"></a><a name="p1582122531317"></a>timeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p58242515132"><a name="p58242515132"></a><a name="p58242515132"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.04%" headers="mcps1.2.4.1.3 "><p id="p48210254133"><a name="p48210254133"></a><a name="p48210254133"></a>健康检查的超时时间（秒），可选</p>
    <p id="p482182513132"><a name="p482182513132"></a><a name="p482182513132"></a>默认值：10，取值范围1-50</p>
    </td>
    </tr>
    <tr id="row982825181310"><td class="cellrowborder" valign="top" width="29.59%" headers="mcps1.2.4.1.1 "><p id="p382182517136"><a name="p382182517136"></a><a name="p382182517136"></a>max_retries</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p1082122541314"><a name="p1082122541314"></a><a name="p1082122541314"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.04%" headers="mcps1.2.4.1.3 "><p id="p1882425121317"><a name="p1882425121317"></a><a name="p1882425121317"></a>健康检查的最大重试次数，可选</p>
    <p id="p8821425151313"><a name="p8821425151313"></a><a name="p8821425151313"></a>默认值：3，取值范围1-10</p>
    </td>
    </tr>
    <tr id="row10821625131313"><td class="cellrowborder" valign="top" width="29.59%" headers="mcps1.2.4.1.1 "><p id="p1182025131315"><a name="p1182025131315"></a><a name="p1182025131315"></a>protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p1082192581314"><a name="p1082192581314"></a><a name="p1082192581314"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.04%" headers="mcps1.2.4.1.3 "><p id="p15821525131310"><a name="p15821525131310"></a><a name="p15821525131310"></a>健康检查的协议，可选</p>
    <p id="p208292512130"><a name="p208292512130"></a><a name="p208292512130"></a>默认值：取关联服务的协议</p>
    <p id="p5821125151320"><a name="p5821125151320"></a><a name="p5821125151320"></a>取值范围：“TCP”或者“HTTP”</p>
    </td>
    </tr>
    <tr id="row14820253132"><td class="cellrowborder" valign="top" width="29.59%" headers="mcps1.2.4.1.1 "><p id="p4821725161319"><a name="p4821725161319"></a><a name="p4821725161319"></a>path</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.37%" headers="mcps1.2.4.1.2 "><p id="p1482152517132"><a name="p1482152517132"></a><a name="p1482152517132"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.04%" headers="mcps1.2.4.1.3 "><p id="p1882525121316"><a name="p1882525121316"></a><a name="p1882525121316"></a>健康检查的URL，协议是“HTTP”时配置，可选</p>
    <p id="p1882152561310"><a name="p1882152561310"></a><a name="p1882152561310"></a>默认值：“/”</p>
    <p id="p28213251131"><a name="p28213251131"></a><a name="p28213251131"></a>取值范围：1-10000字符</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 6**  tls\_ciphers\_policy取值说明

    <a name="table315082934512"></a>
    <table><thead align="left"><tr id="row615092919459"><th class="cellrowborder" valign="top" width="16.37%" id="mcps1.2.4.1.1"><p id="p18150122917459"><a name="p18150122917459"></a><a name="p18150122917459"></a>安全策略</p>
    </th>
    <th class="cellrowborder" valign="top" width="25.71%" id="mcps1.2.4.1.2"><p id="p1915092918458"><a name="p1915092918458"></a><a name="p1915092918458"></a>支持的TLS版本类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="57.92%" id="mcps1.2.4.1.3"><p id="p8150629134515"><a name="p8150629134515"></a><a name="p8150629134515"></a>使用的加密套件列表</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row101504293456"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p63758145478"><a name="p63758145478"></a><a name="p63758145478"></a>tls-1-0-inherit</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p884111261473"><a name="p884111261473"></a><a name="p884111261473"></a>TLSv1.2 TLSv1.1 TLSv1</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p2841122619472"><a name="p2841122619472"></a><a name="p2841122619472"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:AES128-GCM-SHA256:AES256-GCM-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES128-SHA256:AES256-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA:ECDHE-RSA-AES128-SHA:DHE-RSA-AES128-SHA:ECDHE-RSA-AES256-SHA:ECDHE-ECDSA-AES256-SHA:AES128-SHA:AES256-SHA:DHE-DSS-AES128-SHA:CAMELLIA128-SHA:EDH-RSA-DES-CBC3-SHA:DES-CBC3-SHA:ECDHE-RSA-RC4-SHA:RC4-SHA:DHE-RSA-AES256-SHA:DHE-DSS-AES256-SHA:DHE-RSA-CAMELLIA256-SHA:DHE-DSS-CAMELLIA256-SHA:CAMELLIA256-SHA:EDH-DSS-DES-CBC3-SHA:DHE-RSA-CAMELLIA128-SHA:DHE-DSS-CAMELLIA128-SHA</p>
    </td>
    </tr>
    <tr id="row11150122911454"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p11150629194512"><a name="p11150629194512"></a><a name="p11150629194512"></a>tls-1-0</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p131501029114519"><a name="p131501029114519"></a><a name="p131501029114519"></a>TLS1v1.2 TLSv1.1 TLSv1</p>
    </td>
    <td class="cellrowborder" rowspan="3" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p131519291455"><a name="p131519291455"></a><a name="p131519291455"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:AES128-GCM-SHA256:AES256-GCM-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES128-SHA256:AES256-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA:ECDHE-RSA-AES128-SHA:ECDHE-RSA-AES256-SHA:ECDHE-ECDSA-AES256-SHA:AES128-SHA:AES256-SHA</p>
    </td>
    </tr>
    <tr id="row13150129194510"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1615042915451"><a name="p1615042915451"></a><a name="p1615042915451"></a>tls1-1</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p21507299451"><a name="p21507299451"></a><a name="p21507299451"></a>TLSv1.2 TLSv1.1</p>
    </td>
    </tr>
    <tr id="row171506297455"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2150122994517"><a name="p2150122994517"></a><a name="p2150122994517"></a>tls-1-2</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p3151529134514"><a name="p3151529134514"></a><a name="p3151529134514"></a>TLSv1.2</p>
    </td>
    </tr>
    <tr id="row1415122915452"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p715152917452"><a name="p715152917452"></a><a name="p715152917452"></a>tls-1-2-strict</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p91511029194513"><a name="p91511029194513"></a><a name="p91511029194513"></a>TLSv1.2</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p8151429144512"><a name="p8151429144512"></a><a name="p8151429144512"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:AES128-GCM-SHA256:AES256-GCM-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES128-SHA256:AES256-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384</p>
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
    >此处tls.crt和tls.key为示例，请获取真实密钥进行替换。tls.crt和tls.key的值为Base64加密后的内容。

3.  创建工作负载。

    **kubectl create -f  ingress-test-deployment.yaml**

    回显如下，表明工作负载已创建。

    ```
    deployment/ingress-test-deployment created
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
    secret/ingress-test-secret created
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
    service/ingress-test-svc created
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
    ingress/ingress-test-ingress created
    ```

    **kubectl get ingress**

    回显如下，表示ingress服务创建成功，工作负载可访问。

    ```
    NAME             HOSTS     ADDRESS          PORTS   AGE
    ingress-test     *         10.154.76.63     80      10s
    ```

6.  在浏览器中输入访问地址http://10.154.76.63/healthz。

    其中，10.154.76.63为统一负载均衡实例的IP地址。

    **图 1**  访问healthz<a name="fig1526153112115"></a>  
    ![](figures/访问healthz.png "访问healthz")


