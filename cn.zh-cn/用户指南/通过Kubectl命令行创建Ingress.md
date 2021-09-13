# 通过Kubectl命令行创建Ingress<a name="cce_01_0252"></a>

## 操作场景<a name="section12681123215510"></a>

本节以nginx为例，说明kubectl命令实现ingress访问的方法。

## 创建Ingress-对接已有ELB<a name="section88349576517"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  创建ingress-test-deployment.yaml、ingress-test-svc.yaml、ingress-test-ingress.yaml以及ingress-test-secret.yaml文件。

    ingress-test-deployment.yaml、ingress-test-svc.yaml、ingress-test-ingress.yaml、ingress-test-secret.yaml为自定义名称，您可以随意命名。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   选择HTTPS协议时，才需要创建密钥证书ingress-test-secret.yaml。创建密钥的方法请参见[创建密钥](创建密钥.md)。
    >-   同一个ELB实例的同一个端口配置HTTPS时，选择的证书需要是一样的。

    **vi ingress-test-deployment.yaml**

    ```
    apiVersion: apps/v1
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
    <table><thead align="left"><tr id="row1519121663519"><th class="cellrowborder" valign="top" width="16.41%" id="mcps1.2.5.1.1"><p id="p18191161619356"><a name="p18191161619356"></a><a name="p18191161619356"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="13.450000000000001%" id="mcps1.2.5.1.2"><p id="p025814516207"><a name="p025814516207"></a><a name="p025814516207"></a>是否必填</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.189999999999998%" id="mcps1.2.5.1.3"><p id="p1191141613357"><a name="p1191141613357"></a><a name="p1191141613357"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.949999999999996%" id="mcps1.2.5.1.4"><p id="p1919116161353"><a name="p1919116161353"></a><a name="p1919116161353"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row15191171618357"><td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.1 "><p id="p5788113218236"><a name="p5788113218236"></a><a name="p5788113218236"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p525811519209"><a name="p525811519209"></a><a name="p525811519209"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.189999999999998%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p54093956"><a name="zh-cn_topic_0079615000_p54093956"></a><a name="zh-cn_topic_0079615000_p54093956"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p167881320237"><a name="p167881320237"></a><a name="p167881320237"></a>集群虚拟IP的访问端口，取值范围为1 ~ 65535。</p>
    </td>
    </tr>
    <tr id="row81941516153513"><td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p11039195"><a name="zh-cn_topic_0079615000_p11039195"></a><a name="zh-cn_topic_0079615000_p11039195"></a>protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p82581651209"><a name="p82581651209"></a><a name="p82581651209"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.189999999999998%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p17699892"><a name="zh-cn_topic_0079615000_p17699892"></a><a name="zh-cn_topic_0079615000_p17699892"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p835181810259"><a name="p835181810259"></a><a name="p835181810259"></a>该端口的IP协议，支持“TCP”和“UDP”。</p>
    </td>
    </tr>
    <tr id="row201957167350"><td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p53639231"><a name="zh-cn_topic_0079615000_p53639231"></a><a name="zh-cn_topic_0079615000_p53639231"></a>targetPort</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p325812516203"><a name="p325812516203"></a><a name="p325812516203"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.189999999999998%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p8117426"><a name="zh-cn_topic_0079615000_p8117426"></a><a name="zh-cn_topic_0079615000_p8117426"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1262218433513"><a name="p1262218433513"></a><a name="p1262218433513"></a>对应界面上的容器端口，应用程序实际监听的端口，取值范围为1 ~ 65535。</p>
    </td>
    </tr>
    <tr id="row02694357138"><td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.1 "><p id="p6716134816295"><a name="p6716134816295"></a><a name="p6716134816295"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p7258850209"><a name="p7258850209"></a><a name="p7258850209"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.189999999999998%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p18968549"><a name="zh-cn_topic_0079615000_p18968549"></a><a name="zh-cn_topic_0079615000_p18968549"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p13717148202913"><a name="p13717148202913"></a><a name="p13717148202913"></a>采用Nodeport的访问类型连接负载均衡，NodePort表示“节点私有IP”。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **vi ingress-test-ingress.yaml**

    -   1.15及以上集群版本中的apiVersion为: networking.k8s.io/v1beta1
    -   1.13及以下集群版本中的apiVersion为: extensions/v1beta1

    ```
    apiVersion: networking.k8s.io/v1beta1
    kind: Ingress 
    metadata: 
      annotations: 
        kubernetes.io/elb.class: union
        kubernetes.io/elb.id: f7891f9a-49f2-4ee2-b1ae-f019cd84eb4f
        kubernetes.io/elb.ip: 192.168.0.39
        kubernetes.io/elb.subnet-id: 29a0567e-96f1-4227-91cc-64f54d0b064d
        kubernetes.io/elb.port: "80"
        kubernetes.io/ingress.class: cce
        kubernetes.io/elb.tls-ciphers-policy: tls-1-2
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
    >安全策略选择（kubernetes.io/elb.tls-ciphers-policy）仅在1.17.11及以上版本的集群中支持。

    **表 2**  关键参数说明

    <a name="table52211185119"></a>
    <table><thead align="left"><tr id="row7221389119"><th class="cellrowborder" valign="top" width="24.772477247724773%" id="mcps1.2.5.1.1"><p id="p12221208219"><a name="p12221208219"></a><a name="p12221208219"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="13.691369136913693%" id="mcps1.2.5.1.2"><p id="p6119114516205"><a name="p6119114516205"></a><a name="p6119114516205"></a>是否必填</p>
    </th>
    <th class="cellrowborder" valign="top" width="13.821382138213819%" id="mcps1.2.5.1.3"><p id="p92211989115"><a name="p92211989115"></a><a name="p92211989115"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="47.714771477147714%" id="mcps1.2.5.1.4"><p id="p1422228818"><a name="p1422228818"></a><a name="p1422228818"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row14541091256"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p525294417518"><a name="p525294417518"></a><a name="p525294417518"></a>kubernetes.io/elb.class</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p122523442518"><a name="p122523442518"></a><a name="p122523442518"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p192520443516"><a name="p192520443516"></a><a name="p192520443516"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p10252154410511"><a name="p10252154410511"></a><a name="p10252154410511"></a>请根据不同的应用场景和功能需求选择合适的负载均衡器类型。</p>
    <p id="p425215441856"><a name="p425215441856"></a><a name="p425215441856"></a>取值如下：</p>
    <a name="ul15252194413518"></a><a name="ul15252194413518"></a><ul id="ul15252194413518"><li>union：共享型负载均衡。</li><li>performance：独享型负载均衡，仅支持1.17及以上集群，详情请参见<a href="https://support.huaweicloud.com/productdesc-elb/elb_pro_0004.html" target="_blank" rel="noopener noreferrer">共享型弹性负载均衡与独享型负载均衡的功能区别</a></li></ul>
    </td>
    </tr>
    <tr id="row192222810118"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p162221781112"><a name="p162221781112"></a><a name="p162221781112"></a>kubernetes.io/elb.id</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p17119245132016"><a name="p17119245132016"></a><a name="p17119245132016"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p192221682111"><a name="p192221682111"></a><a name="p192221682111"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p12221680112"><a name="p12221680112"></a><a name="p12221680112"></a>为负载均衡实例的ID，取值范围：1-100字符。</p>
    <p id="p152221981915"><a name="p152221981915"></a><a name="p152221981915"></a><strong id="b1622288318"><a name="b1622288318"></a><a name="b1622288318"></a>获取方法：</strong></p>
    <p id="p14222581716"><a name="p14222581716"></a><a name="p14222581716"></a>在控制台的<span class="uicontrol" id="uicontrol1122298610"><a name="uicontrol1122298610"></a><a name="uicontrol1122298610"></a>“服务列表”</span>中，单击<span class="uicontrol" id="uicontrol1222218013"><a name="uicontrol1222218013"></a><a name="uicontrol1222218013"></a>“网络 &gt; 弹性负载均衡 ELB”</span>，单击ELB的名称，在ELB详情页的<span class="uicontrol" id="uicontrol42222081120"><a name="uicontrol42222081120"></a><a name="uicontrol42222081120"></a>“基本信息”</span>页签下找到<span class="uicontrol" id="uicontrol1322213815114"><a name="uicontrol1322213815114"></a><a name="uicontrol1322213815114"></a>“ID”</span>字段复制即可。</p>
    </td>
    </tr>
    <tr id="row1322218810115"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p20222482013"><a name="p20222482013"></a><a name="p20222482013"></a>kubernetes.io/elb.ip</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p71191345192016"><a name="p71191345192016"></a><a name="p71191345192016"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p422219812110"><a name="p422219812110"></a><a name="p422219812110"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p1422216818115"><a name="p1422216818115"></a><a name="p1422216818115"></a>为负载均衡实例的服务地址，公网ELB配置为公网IP，私网ELB配置为私网IP。</p>
    </td>
    </tr>
    <tr id="row16222783113"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p0222286110"><a name="p0222286110"></a><a name="p0222286110"></a>kubernetes.io/elb.subnet-id</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p41191645112019"><a name="p41191645112019"></a><a name="p41191645112019"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p172221881413"><a name="p172221881413"></a><a name="p172221881413"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p52226812119"><a name="p52226812119"></a><a name="p52226812119"></a>为集群所在子网的ID，取值范围：1-100字符。</p>
    <a name="ul1822214810112"></a><a name="ul1822214810112"></a><ul id="ul1822214810112"><li>Kubernetes v1.11.7-r0及以下版本的集群自动创建时：必填，</li><li>Kubernetes v1.11.7-r0以上版本的集群：可不填。</li></ul>
    <p id="p2222158718"><a name="p2222158718"></a><a name="p2222158718"></a>获取方法请参见：<a href="https://support.huaweicloud.com/api-vpc/vpc_api_0005.html" target="_blank" rel="noopener noreferrer">VPC子网接口与OpenStack Neutron子网接口的区别是什么？</a></p>
    </td>
    </tr>
    <tr id="row32221282014"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p22221181311"><a name="p22221181311"></a><a name="p22221181311"></a>kubernetes.io/elb.eip-id</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p1611912459201"><a name="p1611912459201"></a><a name="p1611912459201"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p622216815116"><a name="p622216815116"></a><a name="p622216815116"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p10222984111"><a name="p10222984111"></a><a name="p10222984111"></a>为弹性公网的ID，取值范围：1-100字符。</p>
    <p id="p522319816120"><a name="p522319816120"></a><a name="p522319816120"></a><strong id="b6223581819"><a name="b6223581819"></a><a name="b6223581819"></a>获取方法：</strong></p>
    <p id="p52231381810"><a name="p52231381810"></a><a name="p52231381810"></a>在控制台的“服务列表”中，单击“网络 &gt; 弹性公网IP EIP”，单击EIP的名称，在EIP详情页的“基本信息”中找到“ID”字段复制即可。</p>
    </td>
    </tr>
    <tr id="row202232081016"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p202231181312"><a name="p202231181312"></a><a name="p202231181312"></a>kubernetes.io/elb.enterpriseID</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p811944519204"><a name="p811944519204"></a><a name="p811944519204"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p322378511"><a name="p322378511"></a><a name="p322378511"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p622398912"><a name="p622398912"></a><a name="p622398912"></a><strong id="b4223181011"><a name="b4223181011"></a><a name="b4223181011"></a>v1.15及以上版本的集群支持此字段，v1.15以下版本默认创建到default项目下。</strong></p>
    <p id="p72231484118"><a name="p72231484118"></a><a name="p72231484118"></a>ELB企业项目ID，选择后可以直接创建在具体的ELB企业项目下。</p>
    <p id="p22231689120"><a name="p22231689120"></a><a name="p22231689120"></a>取值范围：1-100字符。</p>
    <p id="p19223285111"><a name="p19223285111"></a><a name="p19223285111"></a><strong id="b2223587111"><a name="b2223587111"></a><a name="b2223587111"></a>获取方法：</strong></p>
    <p id="p152231081216"><a name="p152231081216"></a><a name="p152231081216"></a>登录控制台后，单击顶部菜单右侧的<span class="uicontrol" id="uicontrol322315818114"><a name="uicontrol322315818114"></a><a name="uicontrol322315818114"></a>“企业 &gt; 项目管理”</span>，在打开的企业项目列表中单击要加入的企业项目名称，进入企业项目详情页，找到<span class="uicontrol" id="uicontrol822313810110"><a name="uicontrol822313810110"></a><a name="uicontrol822313810110"></a>“ID”</span>字段复制即可。</p>
    </td>
    </tr>
    <tr id="row16224118014"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p102241581812"><a name="p102241581812"></a><a name="p102241581812"></a>kubernetes.io/elb.tls-ciphers-policy</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p5119144511205"><a name="p5119144511205"></a><a name="p5119144511205"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p112248816110"><a name="p112248816110"></a><a name="p112248816110"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p162241781615"><a name="p162241781615"></a><a name="p162241781615"></a>默认值：“tls-1-2”，为监听器使用的安全策略，仅在HTTPS协议下生效。</p>
    <p id="p7224198017"><a name="p7224198017"></a><a name="p7224198017"></a>取值范围：</p>
    <a name="ul8224481318"></a><a name="ul8224481318"></a><ul id="ul8224481318"><li>tls-1-0</li><li>tls-1-1</li><li>tls-1-2</li><li>tls-1-2-strict</li></ul>
    <p id="p1822511820114"><a name="p1822511820114"></a><a name="p1822511820114"></a>各安全策略使用的加密套件列表详细参见<a href="#table16769442022">表3</a>。</p>
    </td>
    </tr>
    <tr id="row4225581518"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p1122519817112"><a name="p1122519817112"></a><a name="p1122519817112"></a>kubernetes.io/elb.port</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p151199453202"><a name="p151199453202"></a><a name="p151199453202"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p32255818117"><a name="p32255818117"></a><a name="p32255818117"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p32257819119"><a name="p32257819119"></a><a name="p32257819119"></a>界面上的对外端口，为注册到负载均衡服务地址上的端口。</p>
    <p id="p192253817115"><a name="p192253817115"></a><a name="p192253817115"></a>取值范围：1-65535。</p>
    </td>
    </tr>
    <tr id="row822517815119"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p1422514816110"><a name="p1422514816110"></a><a name="p1422514816110"></a>kubernetes.io/ingress.class</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p1119174542014"><a name="p1119174542014"></a><a name="p1119174542014"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p192251581511"><a name="p192251581511"></a><a name="p192251581511"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p13225148314"><a name="p13225148314"></a><a name="p13225148314"></a>是否开启nginx-ingress插件。</p>
    <a name="ul19225168617"></a><a name="ul19225168617"></a><ul id="ul19225168617"><li>cce：表示不开启nginx-ingress插件，将默认使用负载均衡实例。</li><li>nginx：表示开启nginx-ingress插件。</li></ul>
    <p id="p222520819118"><a name="p222520819118"></a><a name="p222520819118"></a>通过API接口创建Ingress时必须增加该参数。</p>
    </td>
    </tr>
    <tr id="row92251481316"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p122251889112"><a name="p122251889112"></a><a name="p122251889112"></a>tls</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p1611915453205"><a name="p1611915453205"></a><a name="p1611915453205"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p102251481915"><a name="p102251481915"></a><a name="p102251481915"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p102251581312"><a name="p102251581312"></a><a name="p102251581312"></a>HTTPS协议时，需添加此参数。</p>
    </td>
    </tr>
    <tr id="row1222514819116"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p102251089113"><a name="p102251089113"></a><a name="p102251089113"></a>secretName</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p2119154517207"><a name="p2119154517207"></a><a name="p2119154517207"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p8225281114"><a name="p8225281114"></a><a name="p8225281114"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p222588816"><a name="p222588816"></a><a name="p222588816"></a>HTTPS协议时添加，配置为创建的密钥证书名称。</p>
    </td>
    </tr>
    <tr id="row132254812116"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p14225889111"><a name="p14225889111"></a><a name="p14225889111"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p61191745152017"><a name="p61191745152017"></a><a name="p61191745152017"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p1225187117"><a name="p1225187117"></a><a name="p1225187117"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p192251883114"><a name="p192251883114"></a><a name="p192251883114"></a>为ingress-test-svc.yaml的服务名称。</p>
    </td>
    </tr>
    <tr id="row0225881112"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p6225281912"><a name="p6225281912"></a><a name="p6225281912"></a>servicePort</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p12119045192012"><a name="p12119045192012"></a><a name="p12119045192012"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p1822516810116"><a name="p1822516810116"></a><a name="p1822516810116"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p3225984112"><a name="p3225984112"></a><a name="p3225984112"></a>为ingress-test-svc.yaml的Port。</p>
    </td>
    </tr>
    <tr id="row2226148310"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p1522688715"><a name="p1522688715"></a><a name="p1522688715"></a>ingress.beta.kubernetes.io/url-match-mode</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p1811934572013"><a name="p1811934572013"></a><a name="p1811934572013"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p22261585119"><a name="p22261585119"></a><a name="p22261585119"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p422619815110"><a name="p422619815110"></a><a name="p422619815110"></a>路由匹配策略。</p>
    <p id="p0226387120"><a name="p0226387120"></a><a name="p0226387120"></a>默认值：STARTS_WITH(前缀匹配)。</p>
    <p id="p1122638514"><a name="p1122638514"></a><a name="p1122638514"></a>取值范围：</p>
    <a name="ul2226178716"></a><a name="ul2226178716"></a><ul id="ul2226178716"><li>EQUAL_TO：精确匹配</li><li>STARTS_WITH：前缀匹配</li><li>REGEX：正则匹配</li></ul>
    </td>
    </tr>
    <tr id="row152268818116"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p622610819110"><a name="p622610819110"></a><a name="p622610819110"></a>path</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p2119104511205"><a name="p2119104511205"></a><a name="p2119104511205"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p1422619819120"><a name="p1422619819120"></a><a name="p1422619819120"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p822688517"><a name="p822688517"></a><a name="p822688517"></a>为路由路径，用户自定义设置。</p>
    </td>
    </tr>
    <tr id="row622615812115"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p19226208115"><a name="p19226208115"></a><a name="p19226208115"></a>host</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p1119104532020"><a name="p1119104532020"></a><a name="p1119104532020"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p102261184112"><a name="p102261184112"></a><a name="p102261184112"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p6226087112"><a name="p6226087112"></a><a name="p6226087112"></a>为域名配置，默认为空，域名全匹配。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 3**  tls\_ciphers\_policy取值说明

    <a name="table16769442022"></a>
    <table><thead align="left"><tr id="row18769942424"><th class="cellrowborder" valign="top" width="16.37%" id="mcps1.2.4.1.1"><p id="p276914210214"><a name="p276914210214"></a><a name="p276914210214"></a>安全策略</p>
    </th>
    <th class="cellrowborder" valign="top" width="25.71%" id="mcps1.2.4.1.2"><p id="p1576924211210"><a name="p1576924211210"></a><a name="p1576924211210"></a>支持的TLS版本类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="57.92%" id="mcps1.2.4.1.3"><p id="p1277019421726"><a name="p1277019421726"></a><a name="p1277019421726"></a>使用的加密套件列表</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row87703425210"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p187701942625"><a name="p187701942625"></a><a name="p187701942625"></a>tls-1-0</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p168701954115516"><a name="p168701954115516"></a><a name="p168701954115516"></a>TLS 1.2</p>
    <p id="p1087016543552"><a name="p1087016543552"></a><a name="p1087016543552"></a>TLS 1.1</p>
    <p id="p387075417554"><a name="p387075417554"></a><a name="p387075417554"></a>TLS 1.0</p>
    </td>
    <td class="cellrowborder" rowspan="3" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p10770742828"><a name="p10770742828"></a><a name="p10770742828"></a><span>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:AES128-GCM-SHA256:AES256-GCM-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES128-SHA256:AES256-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA:ECDHE-RSA-AES128-SHA:ECDHE-RSA-AES256-SHA:ECDHE-ECDSA-AES256-SHA:AES128-SHA:AES256-SHA</span></p>
    </td>
    </tr>
    <tr id="row1377014424215"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p977054212216"><a name="p977054212216"></a><a name="p977054212216"></a>tls-1-1</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p116451934568"><a name="p116451934568"></a><a name="p116451934568"></a>TLS 1.2</p>
    <p id="p1564573185618"><a name="p1564573185618"></a><a name="p1564573185618"></a>TLS 1.1</p>
    </td>
    </tr>
    <tr id="row1377015421029"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1177034220220"><a name="p1177034220220"></a><a name="p1177034220220"></a>tls-1-2</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16341141215567"><a name="p16341141215567"></a><a name="p16341141215567"></a>TLS 1.2</p>
    </td>
    </tr>
    <tr id="row2770442324"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p277017421229"><a name="p277017421229"></a><a name="p277017421229"></a>tls-1-2-strict</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p2770442822"><a name="p2770442822"></a><a name="p2770442822"></a>TLS 1.2</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p1577019424219"><a name="p1577019424219"></a><a name="p1577019424219"></a><span>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:AES128-GCM-SHA256:AES256-GCM-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES128-SHA256:AES256-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384</span></p>
    </td>
    </tr>
    <tr id="row15646102519104"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p1649125415134"><a name="p1649125415134"></a><a name="p1649125415134"></a>TLS-1-0-WITH-1-3（独享型实例）</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p0649115451320"><a name="p0649115451320"></a><a name="p0649115451320"></a>TLS 1.3</p>
    <p id="p126496547139"><a name="p126496547139"></a><a name="p126496547139"></a>TLS 1.2</p>
    <p id="p46491254131312"><a name="p46491254131312"></a><a name="p46491254131312"></a>TLS 1.1</p>
    <p id="p1464915545138"><a name="p1464915545138"></a><a name="p1464915545138"></a>TLS 1.0</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p1064915431315"><a name="p1064915431315"></a><a name="p1064915431315"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:AES128-GCM-SHA256:AES256-GCM-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES128-SHA256:AES256-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA:ECDHE-RSA-AES128-SHA:ECDHE-RSA-AES256-SHA:ECDHE-ECDSA-AES256-SHA:AES128-SHA:AES256-SHA:TLS_AES_256_GCM_SHA384:TLS_CHACHA20_POLY1305_SHA256:TLS_AES_128_GCM_SHA256:TLS_AES_128_CCM_8_SHA256:TLS_AES_128_CCM_SHA256</p>
    </td>
    </tr>
    <tr id="row1551216281107"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p1289313318144"><a name="p1289313318144"></a><a name="p1289313318144"></a>TLS-1-2-FS（独享型实例）</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p98931336142"><a name="p98931336142"></a><a name="p98931336142"></a>TLS 1.3</p>
    <p id="p3613240191410"><a name="p3613240191410"></a><a name="p3613240191410"></a>TLS 1.2</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p19893133315143"><a name="p19893133315143"></a><a name="p19893133315143"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384</p>
    </td>
    </tr>
    <tr id="row15734123418101"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p137120161510"><a name="p137120161510"></a><a name="p137120161510"></a>TLS-1-2-FS-WITH-1-3（独享型实例）</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p13371141131513"><a name="p13371141131513"></a><a name="p13371141131513"></a>TLS 1.3</p>
    <p id="p137115181516"><a name="p137115181516"></a><a name="p137115181516"></a>TLS 1.2</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p4371714154"><a name="p4371714154"></a><a name="p4371714154"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:TLS_AES_256_GCM_SHA384:TLS_CHACHA20_POLY1305_SHA256:TLS_AES_128_GCM_SHA256:TLS_AES_128_CCM_8_SHA256:TLS_AES_128_CCM_SHA256</p>
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


## 创建Ingress-自动创建ELB<a name="section12426658105015"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  创建ingress-test-deployment.yaml、ingress-test-svc.yaml、ingress-test-ingress.yaml以及ingress-test-secret.yaml文件。

    ingress-test-deployment.yaml、ingress-test-svc.yaml、ingress-test-ingress.yaml、ingress-test-secret.yaml为自定义名称，您可以随意命名。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   选择HTTPS协议时，才需要创建密钥证书ingress-test-secret.yaml。创建密钥的方法请参见[创建密钥](创建密钥.md)。
    >-   同一个ELB实例的同一个端口配置HTTPS时，选择的证书需要是一样的。

    **vi ingress-test-deployment.yaml**

    ```
    apiVersion: apps/v1
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

    **表 4**  关键参数说明

    <a name="table121443135514"></a>
    <table><thead align="left"><tr id="row114415131513"><th class="cellrowborder" valign="top" width="16.41%" id="mcps1.2.5.1.1"><p id="p111441013135116"><a name="p111441013135116"></a><a name="p111441013135116"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="13.450000000000001%" id="mcps1.2.5.1.2"><p id="p1144201311519"><a name="p1144201311519"></a><a name="p1144201311519"></a>是否必填</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.189999999999998%" id="mcps1.2.5.1.3"><p id="p1714441318519"><a name="p1714441318519"></a><a name="p1714441318519"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.949999999999996%" id="mcps1.2.5.1.4"><p id="p31448132515"><a name="p31448132515"></a><a name="p31448132515"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row614551313516"><td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.1 "><p id="p1145213135113"><a name="p1145213135113"></a><a name="p1145213135113"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p11452137514"><a name="p11452137514"></a><a name="p11452137514"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.189999999999998%" headers="mcps1.2.5.1.3 "><p id="p1914571315115"><a name="p1914571315115"></a><a name="p1914571315115"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p2145813165111"><a name="p2145813165111"></a><a name="p2145813165111"></a>集群虚拟IP的访问端口，取值范围为1 ~ 65535。</p>
    </td>
    </tr>
    <tr id="row5145201314513"><td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.1 "><p id="p814511319510"><a name="p814511319510"></a><a name="p814511319510"></a>protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p614581345111"><a name="p614581345111"></a><a name="p614581345111"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.189999999999998%" headers="mcps1.2.5.1.3 "><p id="p101451139512"><a name="p101451139512"></a><a name="p101451139512"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p121454137518"><a name="p121454137518"></a><a name="p121454137518"></a>该端口的IP协议，支持“TCP”和“UDP”。</p>
    </td>
    </tr>
    <tr id="row17145713195115"><td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.1 "><p id="p414541315111"><a name="p414541315111"></a><a name="p414541315111"></a>targetPort</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p1914517130516"><a name="p1914517130516"></a><a name="p1914517130516"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.189999999999998%" headers="mcps1.2.5.1.3 "><p id="p114571385110"><a name="p114571385110"></a><a name="p114571385110"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1714501315516"><a name="p1714501315516"></a><a name="p1714501315516"></a>对应界面上的容器端口，应用程序实际监听的端口，取值范围为1 ~ 65535。</p>
    </td>
    </tr>
    <tr id="row51451213165118"><td class="cellrowborder" valign="top" width="16.41%" headers="mcps1.2.5.1.1 "><p id="p191457130517"><a name="p191457130517"></a><a name="p191457130517"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.450000000000001%" headers="mcps1.2.5.1.2 "><p id="p5145113125113"><a name="p5145113125113"></a><a name="p5145113125113"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.189999999999998%" headers="mcps1.2.5.1.3 "><p id="p1145213115111"><a name="p1145213115111"></a><a name="p1145213115111"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1514621310513"><a name="p1514621310513"></a><a name="p1514621310513"></a>采用Nodeport的访问类型连接负载均衡，NodePort表示“节点私有IP”。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **vi ingress-test-ingress.yaml**

    -   1.15及以上集群版本中的apiVersion为: networking.k8s.io/v1beta1
    -   1.13及以下集群版本中的apiVersion为: apps/v1

    共享型负载均衡（公网访问）实例：

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
        kubernetes.io/elb.class: union
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

    独享型负载均衡（公网访问）实例 - 仅支持1.17及以上集群：

    ```
    apiVersion: networking.k8s.io/v1beta1
    kind: Ingress
    metadata:
      labels:
        zone: data
        isExternal: 'true'
      name: test2
      namespace: default
      annotations:
        kubernetes.io/ingress.class: cce
        kubernetes.io/elb.port: '80'
        kubernetes.io/elb.subnet-id: ''
        kubernetes.io/elb.autocreate: 
          ' {
              "type": "public",
              "bandwidth_name": "cce-bandwidth-1626751177680",
              "bandwidth_chargemode": "bandwidth",
              "bandwidth_size": 1,
              "bandwidth_sharetype": "PER",
              "eip_type": "5_gray",
              "available_zone": [
                  "cn-south-2b"
              ],
              "l7_flavor_name": "L7_flavor.elb.s1.small",
              "elb_virsubnet_ids": [
                  "14567f27-8ae4-42b8-ae47-9f847a4690dd"
              ]
           }
          '
        kubernetes.io/elb.enterpriseID: '0'
        kubernetes.io/elb.class: performance
    spec:
      rules:
      - host: ''
        http:
          paths:
          - backend:
              serviceName: test
              servicePort: 80
            path: "/"
            property:
              ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
    ```

    **表 5**  关键参数说明

    <a name="table41732137512"></a>
    <table><thead align="left"><tr id="row1417311136515"><th class="cellrowborder" valign="top" width="24.542454245424544%" id="mcps1.2.5.1.1"><p id="p13173131318516"><a name="p13173131318516"></a><a name="p13173131318516"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="14.331433143314332%" id="mcps1.2.5.1.2"><p id="p21737134510"><a name="p21737134510"></a><a name="p21737134510"></a>是否必填</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.461746174617463%" id="mcps1.2.5.1.3"><p id="p6174413195111"><a name="p6174413195111"></a><a name="p6174413195111"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="43.66436643664366%" id="mcps1.2.5.1.4"><p id="p141741113175115"><a name="p141741113175115"></a><a name="p141741113175115"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3622527038"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p8622162715319"><a name="p8622162715319"></a><a name="p8622162715319"></a>kubernetes.io/elb.class</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p16229277315"><a name="p16229277315"></a><a name="p16229277315"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p362214271032"><a name="p362214271032"></a><a name="p362214271032"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p193521947123917"><a name="p193521947123917"></a><a name="p193521947123917"></a>请根据不同的应用场景和功能需求选择合适的负载均衡器类型。</p>
    <p id="p163524473399"><a name="p163524473399"></a><a name="p163524473399"></a>取值如下：</p>
    <a name="ul16352114763920"></a><a name="ul16352114763920"></a><ul id="ul16352114763920"><li>union：共享型负载均衡。</li><li>performance：独享型负载均衡，仅支持1.17及以上集群，详情请参见<a href="https://support.huaweicloud.com/productdesc-elb/elb_pro_0004.html" target="_blank" rel="noopener noreferrer">共享型弹性负载均衡与独享型负载均衡的功能区别</a></li></ul>
    <p id="p861911425283"><a name="p861911425283"></a><a name="p861911425283"></a>默认值：union</p>
    </td>
    </tr>
    <tr id="row1195518515113"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p139550517114"><a name="p139550517114"></a><a name="p139550517114"></a>kubernetes.io/ingress.class</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p18955175118115"><a name="p18955175118115"></a><a name="p18955175118115"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p189562511514"><a name="p189562511514"></a><a name="p189562511514"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p120519291569"><a name="p120519291569"></a><a name="p120519291569"></a>是否开启nginx-ingress插件。</p>
    <a name="ul1206182914619"></a><a name="ul1206182914619"></a><ul id="ul1206182914619"><li>cce：表示不开启nginx-ingress插件，将默认使用负载均衡实例。</li><li>nginx：表示开启nginx-ingress插件。</li></ul>
    <p id="p132063290619"><a name="p132063290619"></a><a name="p132063290619"></a>通过API接口创建Ingress时必须增加该参数。</p>
    </td>
    </tr>
    <tr id="row1152275720218"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p1952213571628"><a name="p1952213571628"></a><a name="p1952213571628"></a>kubernetes.io/elb.port</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p1248419201818"><a name="p1248419201818"></a><a name="p1248419201818"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p7248171931814"><a name="p7248171931814"></a><a name="p7248171931814"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p13248141915180"><a name="p13248141915180"></a><a name="p13248141915180"></a>界面上的对外端口，为注册到负载均衡服务地址上的端口。</p>
    <p id="p18248519121814"><a name="p18248519121814"></a><a name="p18248519121814"></a>取值范围：1-65535。</p>
    </td>
    </tr>
    <tr id="row17281581528"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p12281058628"><a name="p12281058628"></a><a name="p12281058628"></a>kubernetes.io/elb.subnet-id</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p13282058028"><a name="p13282058028"></a><a name="p13282058028"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p12815582210"><a name="p12815582210"></a><a name="p12815582210"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p3626184011176"><a name="p3626184011176"></a><a name="p3626184011176"></a>为集群所在子网的ID，取值范围：1-100字符。</p>
    <a name="ul4626184018172"></a><a name="ul4626184018172"></a><ul id="ul4626184018172"><li>Kubernetes v1.11.7-r0及以下版本的集群自动创建时：必填，</li><li>Kubernetes v1.11.7-r0以上版本的集群：可不填。</li></ul>
    <p id="p1627104016174"><a name="p1627104016174"></a><a name="p1627104016174"></a>获取方法请参见：<a href="https://support.huaweicloud.com/api-vpc/vpc_api_0005.html" target="_blank" rel="noopener noreferrer">VPC子网接口与OpenStack Neutron子网接口的区别是什么？</a></p>
    </td>
    </tr>
    <tr id="row5434105820220"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p24347581625"><a name="p24347581625"></a><a name="p24347581625"></a>kubernetes.io/elb.enterpriseID</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p17434125820215"><a name="p17434125820215"></a><a name="p17434125820215"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p154346581422"><a name="p154346581422"></a><a name="p154346581422"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p18733493813"><a name="p18733493813"></a><a name="p18733493813"></a><strong id="b19411721131619"><a name="b19411721131619"></a><a name="b19411721131619"></a>v1.15及以上版本的集群支持此字段，v1.15以下版本默认创建到default项目下。</strong></p>
    <p id="p88731149287"><a name="p88731149287"></a><a name="p88731149287"></a>ELB企业项目ID，选择后可以直接创建在具体的ELB企业项目下。</p>
    <p id="p138732491080"><a name="p138732491080"></a><a name="p138732491080"></a>取值范围：1-100字符。</p>
    <p id="p687394914819"><a name="p687394914819"></a><a name="p687394914819"></a><strong id="b987115277160"><a name="b987115277160"></a><a name="b987115277160"></a>获取方法：</strong></p>
    <p id="p108732496817"><a name="p108732496817"></a><a name="p108732496817"></a>登录控制台后，单击顶部菜单右侧的“企业 &gt; 项目管理”，在打开的企业项目列表中单击要加入的企业项目名称，进入企业项目详情页，找到“ID”字段复制即可。</p>
    </td>
    </tr>
    <tr id="row91747132518"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p9174613125118"><a name="p9174613125118"></a><a name="p9174613125118"></a>kubernetes.io/elb.autocreate</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p8174131365119"><a name="p8174131365119"></a><a name="p8174131365119"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p171741813165118"><a name="p171741813165118"></a><a name="p171741813165118"></a><a href="#table16175413105111">elb.autocreate</a> object</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p517481305117"><a name="p517481305117"></a><a name="p517481305117"></a>自动创建Ingress关联的ELB</p>
    <p id="p4175191315514"><a name="p4175191315514"></a><a name="p4175191315514"></a><strong id="b617561318519"><a name="b617561318519"></a><a name="b617561318519"></a>示例：</strong></p>
    <a name="ul19175313125118"></a><a name="ul19175313125118"></a><ul id="ul19175313125118"><li>公网自动创建：<p id="p1417561316511"><a name="p1417561316511"></a><a name="p1417561316511"></a>值为 '{"type":"public","bandwidth_name":"cce-bandwidth-1551163379627","bandwidth_chargemode":"bandwidth","bandwidth_size":5,"bandwidth_sharetype":"PER","eip_type":"5_bgp","name":"james"}'</p>
    </li><li>私网自动创建：<p id="p7175181365113"><a name="p7175181365113"></a><a name="p7175181365113"></a>值为 '{"type":"inner", "name": "A-location-d-test"}'</p>
    </li></ul>
    </td>
    </tr>
    </tbody>
    </table>

    **表 6**  elb.autocreate字段数据结构说明

    <a name="table16175413105111"></a>
    <table><thead align="left"><tr id="row13176151385120"><th class="cellrowborder" valign="top" width="24.612461246124614%" id="mcps1.2.5.1.1"><p id="p81761613175120"><a name="p81761613175120"></a><a name="p81761613175120"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="14.481448144814483%" id="mcps1.2.5.1.2"><p id="p117661365112"><a name="p117661365112"></a><a name="p117661365112"></a>是否必填</p>
    </th>
    <th class="cellrowborder" valign="top" width="15.771577157715772%" id="mcps1.2.5.1.3"><p id="p0176113135111"><a name="p0176113135111"></a><a name="p0176113135111"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="45.13451345134513%" id="mcps1.2.5.1.4"><p id="p10176913185115"><a name="p10176913185115"></a><a name="p10176913185115"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row51763139516"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p11177131311514"><a name="p11177131311514"></a><a name="p11177131311514"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p1217751355117"><a name="p1217751355117"></a><a name="p1217751355117"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p191771613195113"><a name="p191771613195113"></a><a name="p191771613195113"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p917716137519"><a name="p917716137519"></a><a name="p917716137519"></a>自动创建的负载均衡的名称。</p>
    <p id="p7177713105111"><a name="p7177713105111"></a><a name="p7177713105111"></a>取值范围：1-64个字符，小写字母，数字，下划线，小写字母开头，小写字母或者数字结尾。</p>
    <p id="p151771613175115"><a name="p151771613175115"></a><a name="p151771613175115"></a>默认值：cce-lb+ingress.UID</p>
    </td>
    </tr>
    <tr id="row3177141355119"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p151776137510"><a name="p151776137510"></a><a name="p151776137510"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p4177131305114"><a name="p4177131305114"></a><a name="p4177131305114"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p1617714132516"><a name="p1617714132516"></a><a name="p1617714132516"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p917851325115"><a name="p917851325115"></a><a name="p917851325115"></a>负载均衡实例网络类型，公网或者私网。</p>
    <a name="ul12178191315517"></a><a name="ul12178191315517"></a><ul id="ul12178191315517"><li>public：公网型负载均衡</li><li>inner：私网型负载均衡</li></ul>
    <p id="p1017821315516"><a name="p1017821315516"></a><a name="p1017821315516"></a>默认值：inner</p>
    </td>
    </tr>
    <tr id="row41781713185112"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p111786131511"><a name="p111786131511"></a><a name="p111786131511"></a>bandwidth_name</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p1717891345118"><a name="p1717891345118"></a><a name="p1717891345118"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p13178111312514"><a name="p13178111312514"></a><a name="p13178111312514"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p217931385113"><a name="p217931385113"></a><a name="p217931385113"></a>带宽的名称，默认值为：cce-bandwidth-******。</p>
    <p id="p4179151316512"><a name="p4179151316512"></a><a name="p4179151316512"></a>取值范围：1-64个字符，小写字母，数字，下划线，小写字母开头，小写字母或者数字结尾。</p>
    </td>
    </tr>
    <tr id="row017917135517"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p217941385118"><a name="p217941385118"></a><a name="p217941385118"></a>bandwidth_chargemode</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p3179191318513"><a name="p3179191318513"></a><a name="p3179191318513"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p10179111317513"><a name="p10179111317513"></a><a name="p10179111317513"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p31791213105119"><a name="p31791213105119"></a><a name="p31791213105119"></a>带宽付费模式。</p>
    <a name="ul517951317514"></a><a name="ul517951317514"></a><ul id="ul517951317514"><li>bandwidth：按带宽计费</li><li>traffic：按流量计费</li></ul>
    </td>
    </tr>
    <tr id="row71803132519"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p818017136511"><a name="p818017136511"></a><a name="p818017136511"></a>bandwidth_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p12180181316517"><a name="p12180181316517"></a><a name="p12180181316517"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p15180131320518"><a name="p15180131320518"></a><a name="p15180131320518"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p518015136514"><a name="p518015136514"></a><a name="p518015136514"></a>带宽大小，默认1Mbit/s~2000Mbit/s，请根据Region带宽支持范围设置。</p>
    </td>
    </tr>
    <tr id="row13180201325115"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p121811713115113"><a name="p121811713115113"></a><a name="p121811713115113"></a>bandwidth_sharetype</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p12181111355117"><a name="p12181111355117"></a><a name="p12181111355117"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p131817138512"><a name="p131817138512"></a><a name="p131817138512"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p12181131315510"><a name="p12181131315510"></a><a name="p12181131315510"></a>带宽类型，标识是否是共享带宽。</p>
    <p id="p1181121315517"><a name="p1181121315517"></a><a name="p1181121315517"></a>取值范围：</p>
    <a name="ul1618118138517"></a><a name="ul1618118138517"></a><ul id="ul1618118138517"><li>PER：独享带宽</li></ul>
    </td>
    </tr>
    <tr id="row4182101315113"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p4182181355113"><a name="p4182181355113"></a><a name="p4182181355113"></a>eip_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p1718271325110"><a name="p1718271325110"></a><a name="p1718271325110"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p121821113105112"><a name="p121821113105112"></a><a name="p121821113105112"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p118281305116"><a name="p118281305116"></a><a name="p118281305116"></a>弹性公网IP类型。</p>
    <a name="ul18765175214406"></a><a name="ul18765175214406"></a><ul id="ul18765175214406"><li>5_telcom：电信</li><li>5_union：联通</li><li>5_bgp：全动态BGP</li><li>5_sbgp：静态BGP</li></ul>
    <p id="p154114328298"><a name="p154114328298"></a><a name="p154114328298"></a>独享型负载均衡的类型请填<span class="uicontrol" id="uicontrol9881125856"><a name="uicontrol9881125856"></a><a name="uicontrol9881125856"></a>“5_gray”</span>。</p>
    </td>
    </tr>
    <tr id="row1918281319512"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p1182161355113"><a name="p1182161355113"></a><a name="p1182161355113"></a>available_zone</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p13183313175111"><a name="p13183313175111"></a><a name="p13183313175111"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p15183141316510"><a name="p15183141316510"></a><a name="p15183141316510"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p61838132512"><a name="p61838132512"></a><a name="p61838132512"></a>负载均衡所在可用区，必填项。</p>
    <p id="p1418315135518"><a name="p1418315135518"></a><a name="p1418315135518"></a>独享型负载均衡器独有字段。</p>
    </td>
    </tr>
    <tr id="row718318132518"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p111831013145111"><a name="p111831013145111"></a><a name="p111831013145111"></a>l4_flavor_name</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p12183213175115"><a name="p12183213175115"></a><a name="p12183213175115"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p101831613115114"><a name="p101831613115114"></a><a name="p101831613115114"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p818341365117"><a name="p818341365117"></a><a name="p818341365117"></a>四层负载均衡实例名称。</p>
    <p id="p13800313675"><a name="p13800313675"></a><a name="p13800313675"></a>独享型负载均衡器独有字段。</p>
    </td>
    </tr>
    <tr id="row20184113155118"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p11844139513"><a name="p11844139513"></a><a name="p11844139513"></a>l7_flavor_name</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p41846134515"><a name="p41846134515"></a><a name="p41846134515"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p181845136518"><a name="p181845136518"></a><a name="p181845136518"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p418515139519"><a name="p418515139519"></a><a name="p418515139519"></a>七层负载均衡实例名称，必填项。</p>
    <p id="p672610163718"><a name="p672610163718"></a><a name="p672610163718"></a>独享型负载均衡器独有字段。</p>
    </td>
    </tr>
    <tr id="row1518621313519"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p1418681318513"><a name="p1418681318513"></a><a name="p1418681318513"></a>ElbVirSubnetIDs</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.481448144814483%" headers="mcps1.2.5.1.2 "><p id="p518681345117"><a name="p518681345117"></a><a name="p518681345117"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.771577157715772%" headers="mcps1.2.5.1.3 "><p id="p15186111335119"><a name="p15186111335119"></a><a name="p15186111335119"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p618616131513"><a name="p618616131513"></a><a name="p618616131513"></a>负载均衡后端所在子网，不填默认集群子网。不同实例规格将占用不同数量子网IP，不建议使用其他资源（如集群，节点等）的子网网段。</p>
    <p id="p0186713115112"><a name="p0186713115112"></a><a name="p0186713115112"></a>默认值：集群所在子网</p>
    <p id="p112773201713"><a name="p112773201713"></a><a name="p112773201713"></a>独享型负载均衡器独有字段。</p>
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

    **图 2**  访问healthz<a name="fig17193181335118"></a>  
    ![](figures/访问healthz-22.png "访问healthz-22")


