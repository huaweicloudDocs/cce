# 通过Kubectl命令行添加ELB型Ingress<a name="cce_01_0252"></a>

## 操作场景<a name="section12681123215510"></a>

本节以[nginx工作负载](创建无状态负载(Deployment).md#section155246177178)为例，说明kubectl命令添加ELB型Ingress的方法。

## 前提条件<a name="section16541428173911"></a>

-   Ingress为后端工作负载提供网络访问，因此集群中需提前部署可用的工作负载。若您无可用工作负载，可参考[创建无状态负载\(Deployment\)](创建无状态负载(Deployment).md)、[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)或[创建守护进程集\(DaemonSet\)](创建守护进程集(DaemonSet).md)部署示例nginx工作负载。
-   为上述工作负载配置NodePort类型的Service，可参考[节点访问\(NodePort\)](节点访问(NodePort).md)部署示例Service。

## 添加Ingress-自动创建ELB<a name="section12426658105015"></a>

下面介绍如何通过kubectl命令在添加Ingress时自动创建ELB。

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，创建名为“**ingress-test.yaml**”的yaml文件。

    **vi ingress-test.yaml**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   1.15及以上集群版本中的apiVersion为: networking.k8s.io/v1beta1
    >-   1.13及以下集群版本中的apiVersion为: extensions/v1beta1

    **yaml文件配置如下：**

    共享型负载均衡（公网访问）实例：

    ```
    apiVersion: networking.k8s.io/v1beta1
    kind: Ingress 
    metadata: 
      name: ingress-test
      annotations: 
        kubernetes.io/elb.class: union
        kubernetes.io/ingress.class: cce
        kubernetes.io/elb.port: '80'
        kubernetes.io/elb.subnet-id: <your_subnet_id>  #替换为您的子网所在ID
        kubernetes.io/elb.enterpriseID: <your_enterprise_id>  #替换为您的企业项目ID
        kubernetes.io/elb.autocreate: 
          '{
              "type":"public",
              "bandwidth_name":"cce-bandwidth-******",
              "bandwidth_chargemode":"bandwidth",
              "bandwidth_size":5,
              "bandwidth_sharetype":"PER",
              "eip_type":"5_bgp",
              "name":"james"
            }'
    spec:
      rules: 
      - host: ''
        http: 
          paths: 
          - path: '/'
            backend: 
              serviceName: <your_service_name>  #替换为您的目标服务名称
              servicePort: 80
            property:
              ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
    ```

    独享型负载均衡（公网访问）实例：

    ```
    apiVersion: networking.k8s.io/v1beta1
    kind: Ingress
    metadata:
      name: ingress-test
      namespace: default
      annotations:
        kubernetes.io/elb.class: performance
        kubernetes.io/ingress.class: cce
        kubernetes.io/elb.port: '80'
        kubernetes.io/elb.subnet-id: <your_subnet_id>  #替换为您的子网所在ID
        kubernetes.io/elb.enterpriseID: <your_enterprise_id>  #替换为您的企业项目ID
        kubernetes.io/elb.autocreate: 
          '{
              "type": "public",
              "bandwidth_name": "cce-bandwidth-******",
              "bandwidth_chargemode": "bandwidth",
              "bandwidth_size": 1,
              "bandwidth_sharetype": "PER",
              "eip_type": "5_bgp",
              "available_zone": [
                  "cn-south-2b"
              ],
              "l7_flavor_name": "L7_flavor.elb.s1.small",
              "elb_virsubnet_ids": [
                  "14567f27-8ae4-42b8-ae47-9f847a4690**"
              ]
           }'
    spec:
      rules:
      - host: ''
        http:
          paths:
          - path: '/'
            backend: 
              serviceName: <your_service_name>  #替换为您的目标服务名称
              servicePort: 80
            property:
              ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
    ```

    **表 1**  关键参数说明

    <a name="table1504183735111"></a>
    <table><thead align="left"><tr id="row1850419373512"><th class="cellrowborder" valign="top" width="24.542454245424544%" id="mcps1.2.5.1.1"><p id="p1050463713516"><a name="p1050463713516"></a><a name="p1050463713516"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="14.331433143314332%" id="mcps1.2.5.1.2"><p id="p1550433755112"><a name="p1550433755112"></a><a name="p1550433755112"></a>是否必填</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.461746174617463%" id="mcps1.2.5.1.3"><p id="p450410371517"><a name="p450410371517"></a><a name="p450410371517"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="43.66436643664366%" id="mcps1.2.5.1.4"><p id="p750416377512"><a name="p750416377512"></a><a name="p750416377512"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row185043375516"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p135051037125119"><a name="p135051037125119"></a><a name="p135051037125119"></a>kubernetes.io/elb.class</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p10505437115114"><a name="p10505437115114"></a><a name="p10505437115114"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p17505163711518"><a name="p17505163711518"></a><a name="p17505163711518"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p1250512375516"><a name="p1250512375516"></a><a name="p1250512375516"></a>请根据不同的应用场景和功能需求选择合适的负载均衡器类型。</p>
    <p id="p55055378511"><a name="p55055378511"></a><a name="p55055378511"></a>取值如下：</p>
    <a name="ul1850583735116"></a><a name="ul1850583735116"></a><ul id="ul1850583735116"><li>union：共享型负载均衡。</li><li>performance：独享型负载均衡，详情请参见<a href="https://support.huaweicloud.com/productdesc-elb/elb_pro_0004.html" target="_blank" rel="noopener noreferrer">共享型弹性负载均衡与独享型负载均衡的功能区别</a>。</li></ul>
    <p id="p1350553725119"><a name="p1350553725119"></a><a name="p1350553725119"></a>默认值：union</p>
    </td>
    </tr>
    <tr id="row185051237105112"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p4505037165119"><a name="p4505037165119"></a><a name="p4505037165119"></a>kubernetes.io/ingress.class</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p16505937115119"><a name="p16505937115119"></a><a name="p16505937115119"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p6505203725114"><a name="p6505203725114"></a><a name="p6505203725114"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p128891910135120"><a name="p128891910135120"></a><a name="p128891910135120"></a>cce：表示使用自研ELB型Ingress。</p>
    <p id="p5505173745116"><a name="p5505173745116"></a><a name="p5505173745116"></a>通过API接口创建Ingress时必须增加该参数。</p>
    </td>
    </tr>
    <tr id="row550520379517"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p1650563711514"><a name="p1650563711514"></a><a name="p1650563711514"></a>kubernetes.io/elb.port</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p12505163715111"><a name="p12505163715111"></a><a name="p12505163715111"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p35051037195115"><a name="p35051037195115"></a><a name="p35051037195115"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p13505537155117"><a name="p13505537155117"></a><a name="p13505537155117"></a>界面上的对外端口，为注册到负载均衡服务地址上的端口。</p>
    <p id="p1050563714514"><a name="p1050563714514"></a><a name="p1050563714514"></a>取值范围：1-65535。</p>
    </td>
    </tr>
    <tr id="row2505183765119"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p9505837115112"><a name="p9505837115112"></a><a name="p9505837115112"></a>kubernetes.io/elb.subnet-id</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p1750543785115"><a name="p1750543785115"></a><a name="p1750543785115"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p350518377519"><a name="p350518377519"></a><a name="p350518377519"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p11505143795119"><a name="p11505143795119"></a><a name="p11505143795119"></a>为集群所在子网的ID，取值范围：1-100字符。</p>
    <a name="ul8505113765119"></a><a name="ul8505113765119"></a><ul id="ul8505113765119"><li>Kubernetes v1.11.7-r0及以下版本的集群自动创建时：必填。</li><li>Kubernetes v1.11.7-r0以上版本的集群：可不填，默认为空。</li></ul>
    <p id="p185055377518"><a name="p185055377518"></a><a name="p185055377518"></a>获取方法请参见：<a href="https://support.huaweicloud.com/api-vpc/vpc_api_0005.html" target="_blank" rel="noopener noreferrer">VPC子网接口与OpenStack Neutron子网接口的区别是什么？</a></p>
    </td>
    </tr>
    <tr id="row2505153755115"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p19505173715517"><a name="p19505173715517"></a><a name="p19505173715517"></a>kubernetes.io/elb.enterpriseID</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p1250513376516"><a name="p1250513376516"></a><a name="p1250513376516"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p13505173755118"><a name="p13505173755118"></a><a name="p13505173755118"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p1950513765117"><a name="p1950513765117"></a><a name="p1950513765117"></a><strong id="b125021043438"><a name="b125021043438"></a><a name="b125021043438"></a>v1.15及以上版本的集群支持此字段，v1.15以下版本默认创建到default项目下。</strong></p>
    <p id="p19505133711516"><a name="p19505133711516"></a><a name="p19505133711516"></a>ELB企业项目ID，选择后可以直接创建在具体的ELB企业项目下。</p>
    <p id="p115052371513"><a name="p115052371513"></a><a name="p115052371513"></a>取值范围：1-100字符。</p>
    <p id="p450519373515"><a name="p450519373515"></a><a name="p450519373515"></a><strong id="b1511111014437"><a name="b1511111014437"></a><a name="b1511111014437"></a>获取方法：</strong></p>
    <p id="p65061737165120"><a name="p65061737165120"></a><a name="p65061737165120"></a>登录控制台后，单击顶部菜单右侧的“企业 &gt; 项目管理”，在打开的企业项目列表中单击要加入的企业项目名称，进入企业项目详情页，找到“ID”字段复制即可。</p>
    </td>
    </tr>
    <tr id="row65069370510"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p1650683710513"><a name="p1650683710513"></a><a name="p1650683710513"></a>kubernetes.io/elb.autocreate</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p4506137165110"><a name="p4506137165110"></a><a name="p4506137165110"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p9506203765114"><a name="p9506203765114"></a><a name="p9506203765114"></a>elb.autocreate object</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p2506183765112"><a name="p2506183765112"></a><a name="p2506183765112"></a>自动创建Ingress关联的ELB，详细字段说明参见<a href="#table16506637185112">表2</a>。</p>
    <p id="p85061037165120"><a name="p85061037165120"></a><a name="p85061037165120"></a><strong id="b1050616373517"><a name="b1050616373517"></a><a name="b1050616373517"></a>示例：</strong></p>
    <a name="ul1650653735110"></a><a name="ul1650653735110"></a><ul id="ul1650653735110"><li>公网自动创建：<p id="p11506133716513"><a name="p11506133716513"></a><a name="p11506133716513"></a>值为 '{"type":"public","bandwidth_name":"cce-bandwidth-******","bandwidth_chargemode":"bandwidth","bandwidth_size":5,"bandwidth_sharetype":"PER","eip_type":"5_bgp","name":"james"}'</p>
    </li><li>私网自动创建：<p id="p55061537125114"><a name="p55061537125114"></a><a name="p55061537125114"></a>值为 '{"type":"inner", "name": "A-location-d-test"}'</p>
    </li></ul>
    </td>
    </tr>
    <tr id="row943591661614"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p58888361111"><a name="p58888361111"></a><a name="p58888361111"></a>host</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p16888193619116"><a name="p16888193619116"></a><a name="p16888193619116"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p58882367112"><a name="p58882367112"></a><a name="p58882367112"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p988818361116"><a name="p988818361116"></a><a name="p988818361116"></a>为服务访问域名配置，默认为空，表示域名全匹配。</p>
    </td>
    </tr>
    <tr id="row895301831610"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p97579834510"><a name="p97579834510"></a><a name="p97579834510"></a>path</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p275814819458"><a name="p275814819458"></a><a name="p275814819458"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p675816818458"><a name="p675816818458"></a><a name="p675816818458"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p197581185455"><a name="p197581185455"></a><a name="p197581185455"></a>为路由路径，用户自定义设置。所有外部访问请求需要匹配host和path。</p>
    </td>
    </tr>
    <tr id="row157551028134412"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p57571985454"><a name="p57571985454"></a><a name="p57571985454"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p18757984457"><a name="p18757984457"></a><a name="p18757984457"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p175715810452"><a name="p175715810452"></a><a name="p175715810452"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p167571884513"><a name="p167571884513"></a><a name="p167571884513"></a>Ingress绑定的目标Service名称。</p>
    </td>
    </tr>
    <tr id="row1219320434446"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p775728124518"><a name="p775728124518"></a><a name="p775728124518"></a>servicePort</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p975714815455"><a name="p975714815455"></a><a name="p975714815455"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p1175713864513"><a name="p1175713864513"></a><a name="p1175713864513"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p375718854514"><a name="p375718854514"></a><a name="p375718854514"></a>目标Service的访问端口。</p>
    </td>
    </tr>
    <tr id="row1427105984414"><td class="cellrowborder" valign="top" width="24.542454245424544%" headers="mcps1.2.5.1.1 "><p id="p1757984452"><a name="p1757984452"></a><a name="p1757984452"></a>ingress.beta.kubernetes.io/url-match-mode</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.331433143314332%" headers="mcps1.2.5.1.2 "><p id="p1575788154510"><a name="p1575788154510"></a><a name="p1575788154510"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.461746174617463%" headers="mcps1.2.5.1.3 "><p id="p10757588450"><a name="p10757588450"></a><a name="p10757588450"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.66436643664366%" headers="mcps1.2.5.1.4 "><p id="p675717816454"><a name="p675717816454"></a><a name="p675717816454"></a>路由匹配策略。</p>
    <p id="p275712813456"><a name="p275712813456"></a><a name="p275712813456"></a>默认值：STARTS_WITH(前缀匹配)。</p>
    <p id="p12757138184518"><a name="p12757138184518"></a><a name="p12757138184518"></a>取值范围：</p>
    <a name="ul1175716811459"></a><a name="ul1175716811459"></a><ul id="ul1175716811459"><li>EQUAL_TO：精确匹配</li><li>STARTS_WITH：前缀匹配</li><li>REGEX：正则匹配</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  elb.autocreate字段数据结构说明

    <a name="table16506637185112"></a>
    <table><thead align="left"><tr id="row2050623765112"><th class="cellrowborder" valign="top" width="24.612461246124614%" id="mcps1.2.5.1.1"><p id="p150643718512"><a name="p150643718512"></a><a name="p150643718512"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="14.471447144714473%" id="mcps1.2.5.1.2"><p id="p10506237155119"><a name="p10506237155119"></a><a name="p10506237155119"></a>是否必填</p>
    </th>
    <th class="cellrowborder" valign="top" width="15.781578157815781%" id="mcps1.2.5.1.3"><p id="p135061837115111"><a name="p135061837115111"></a><a name="p135061837115111"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="45.13451345134513%" id="mcps1.2.5.1.4"><p id="p17506137145113"><a name="p17506137145113"></a><a name="p17506137145113"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row125065373511"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p1750693775120"><a name="p1750693775120"></a><a name="p1750693775120"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p25065377517"><a name="p25065377517"></a><a name="p25065377517"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p8506103715114"><a name="p8506103715114"></a><a name="p8506103715114"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p0506163719514"><a name="p0506163719514"></a><a name="p0506163719514"></a>负载均衡实例网络类型，公网或者私网。</p>
    <a name="ul050623710510"></a><a name="ul050623710510"></a><ul id="ul050623710510"><li>public：公网型负载均衡</li><li>inner：私网型负载均衡</li></ul>
    <p id="p185061137105118"><a name="p185061137105118"></a><a name="p185061137105118"></a>默认值：inner</p>
    </td>
    </tr>
    <tr id="row1350611372510"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p125061337135114"><a name="p125061337135114"></a><a name="p125061337135114"></a>bandwidth_name</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p1950613795114"><a name="p1950613795114"></a><a name="p1950613795114"></a>公网型负载均衡必填</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p155071337165110"><a name="p155071337165110"></a><a name="p155071337165110"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p13507103712516"><a name="p13507103712516"></a><a name="p13507103712516"></a>带宽的名称，默认值为：cce-bandwidth-******。</p>
    <p id="p12507737155120"><a name="p12507737155120"></a><a name="p12507737155120"></a>取值范围：1-64个字符，小写字母，数字，下划线，小写字母开头，小写字母或者数字结尾。</p>
    </td>
    </tr>
    <tr id="row115075378519"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p1950703714517"><a name="p1950703714517"></a><a name="p1950703714517"></a>bandwidth_chargemode</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p350711377513"><a name="p350711377513"></a><a name="p350711377513"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p1150715373512"><a name="p1150715373512"></a><a name="p1150715373512"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p35071337125116"><a name="p35071337125116"></a><a name="p35071337125116"></a>带宽付费模式。</p>
    <a name="ul15507737175114"></a><a name="ul15507737175114"></a><ul id="ul15507737175114"><li>bandwidth：按带宽计费</li><li>traffic：按流量计费</li></ul>
    <p id="p6473347426"><a name="p6473347426"></a><a name="p6473347426"></a>默认值：bandwidth</p>
    </td>
    </tr>
    <tr id="row1650773718518"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p19507153718517"><a name="p19507153718517"></a><a name="p19507153718517"></a>bandwidth_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p1250783785118"><a name="p1250783785118"></a><a name="p1250783785118"></a>公网型负载均衡必填</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p55071837115117"><a name="p55071837115117"></a><a name="p55071837115117"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p6507153735115"><a name="p6507153735115"></a><a name="p6507153735115"></a>带宽大小，默认取值范围为1Mbit/s~2000Mbit/s，具体范围请根据各Region配置为准。</p>
    <a name="ul751320276014"></a><a name="ul751320276014"></a><ul id="ul751320276014"><li>注意：调整带宽时的最小单位会根据带宽范围不同存在差异。<a name="ul95134272011"></a><a name="ul95134272011"></a><ul id="ul95134272011"><li>小于等于300Mbit/s：默认最小单位为1Mbit/s。</li><li>300Mbit/s~1000Mbit/s：默认最小单位为50Mbit/s。</li><li>大于1000Mbit/s：默认最小单位为500Mbit/s。</li></ul>
    </li></ul>
    </td>
    </tr>
    <tr id="row2050743716519"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p65071937195115"><a name="p65071937195115"></a><a name="p65071937195115"></a>bandwidth_sharetype</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p1850793715120"><a name="p1850793715120"></a><a name="p1850793715120"></a>公网型负载均衡必填</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p105071937185111"><a name="p105071937185111"></a><a name="p105071937185111"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p125077372515"><a name="p125077372515"></a><a name="p125077372515"></a>带宽类型。</p>
    <a name="ul85073373515"></a><a name="ul85073373515"></a><ul id="ul85073373515"><li>PER：独享带宽</li></ul>
    </td>
    </tr>
    <tr id="row1250703712518"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p105077373513"><a name="p105077373513"></a><a name="p105077373513"></a>eip_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p95078375516"><a name="p95078375516"></a><a name="p95078375516"></a>公网型负载均衡必填</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p15507937155113"><a name="p15507937155113"></a><a name="p15507937155113"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p5507337195110"><a name="p5507337195110"></a><a name="p5507337195110"></a>弹性公网IP类型。</p>
    <a name="ul550719375516"></a><a name="ul550719375516"></a><ul id="ul550719375516"><li>5_telcom：电信</li><li>5_union：联通</li><li>5_bgp：全动态BGP</li><li>5_sbgp：静态BGP</li></ul>
    </td>
    </tr>
    <tr id="row194917913265"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p209611962610"><a name="p209611962610"></a><a name="p209611962610"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p196115910262"><a name="p196115910262"></a><a name="p196115910262"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p69611890269"><a name="p69611890269"></a><a name="p69611890269"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p1996110992612"><a name="p1996110992612"></a><a name="p1996110992612"></a>自动创建的负载均衡的名称。</p>
    <p id="p1496112982611"><a name="p1496112982611"></a><a name="p1496112982611"></a>取值范围：1-64个字符，小写字母，数字，下划线，小写字母开头，小写字母或者数字结尾。</p>
    <p id="p1696112912269"><a name="p1696112912269"></a><a name="p1696112912269"></a>默认值：cce-lb+ingress.UID</p>
    </td>
    </tr>
    <tr id="row0137103719206"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p11871111191717"><a name="p11871111191717"></a><a name="p11871111191717"></a>vip_subnet_cidr_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p9871121112173"><a name="p9871121112173"></a><a name="p9871121112173"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p3871151131716"><a name="p3871151131716"></a><a name="p3871151131716"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p1687141121716"><a name="p1687141121716"></a><a name="p1687141121716"></a>指定ELB所在的子网。</p>
    <p id="p1579416343117"><a name="p1579416343117"></a><a name="p1579416343117"></a>如不指定，则ELB与集群在同一个子网。</p>
    </td>
    </tr>
    <tr id="row119615269436"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p1621154554316"><a name="p1621154554316"></a><a name="p1621154554316"></a>available_zone</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p56211945184314"><a name="p56211945184314"></a><a name="p56211945184314"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p1262194504316"><a name="p1262194504316"></a><a name="p1262194504316"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p17621114516437"><a name="p17621114516437"></a><a name="p17621114516437"></a>负载均衡所在可用区，必填项。</p>
    <p id="p662116457436"><a name="p662116457436"></a><a name="p662116457436"></a>独享型负载均衡器独有字段。</p>
    </td>
    </tr>
    <tr id="row29101738204312"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p1962144584315"><a name="p1962144584315"></a><a name="p1962144584315"></a>l4_flavor_name</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p20621194524315"><a name="p20621194524315"></a><a name="p20621194524315"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p8621545164313"><a name="p8621545164313"></a><a name="p8621545164313"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p116211455432"><a name="p116211455432"></a><a name="p116211455432"></a>四层负载均衡实例名称。</p>
    <p id="p15621164504310"><a name="p15621164504310"></a><a name="p15621164504310"></a>独享型负载均衡器独有字段。</p>
    </td>
    </tr>
    <tr id="row3201342184318"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p0622174510434"><a name="p0622174510434"></a><a name="p0622174510434"></a>l7_flavor_name</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p66221145124315"><a name="p66221145124315"></a><a name="p66221145124315"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p1862216457432"><a name="p1862216457432"></a><a name="p1862216457432"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p1662213454436"><a name="p1662213454436"></a><a name="p1662213454436"></a>七层负载均衡实例名称，必填项。</p>
    <p id="p762215452435"><a name="p762215452435"></a><a name="p762215452435"></a>独享型负载均衡器独有字段。</p>
    </td>
    </tr>
    <tr id="row5152644104313"><td class="cellrowborder" valign="top" width="24.612461246124614%" headers="mcps1.2.5.1.1 "><p id="p12622104584315"><a name="p12622104584315"></a><a name="p12622104584315"></a>ElbVirSubnetIDs</p>
    </td>
    <td class="cellrowborder" valign="top" width="14.471447144714473%" headers="mcps1.2.5.1.2 "><p id="p146225456438"><a name="p146225456438"></a><a name="p146225456438"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.781578157815781%" headers="mcps1.2.5.1.3 "><p id="p36221145174313"><a name="p36221145174313"></a><a name="p36221145174313"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.13451345134513%" headers="mcps1.2.5.1.4 "><p id="p2622114574311"><a name="p2622114574311"></a><a name="p2622114574311"></a>负载均衡后端所在子网，不填默认集群子网。不同实例规格将占用不同数量子网IP，不建议使用其他资源（如集群，节点等）的子网网段。</p>
    <p id="p10622645114312"><a name="p10622645114312"></a><a name="p10622645114312"></a>默认值：集群所在子网</p>
    <p id="p18622845134315"><a name="p18622845134315"></a><a name="p18622845134315"></a>独享型负载均衡器独有字段。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  执行如下命令创建Ingress。

    **kubectl create -f ingress-test.yaml**

    回显如下，表示Ingress服务已创建。

    ```
    ingress/ingress-test created
    ```

    **kubectl get ingress**

    回显如下，表示Ingress服务创建成功，工作负载可访问。

    ```
    NAME             HOSTS     ADDRESS          PORTS   AGE
    ingress-test     *         121.**.**.**     80      10s
    ```

4.  访问工作负载（例如[nginx工作负载](创建无状态负载(Deployment).md#section155246177178)），在浏览器中输入访问地址http://121.\*\*.\*\*.\*\*:80进行验证。

    其中，121.\*\*.\*\*.\*\*为统一负载均衡实例的IP地址。


## 添加Ingress-对接已有ELB<a name="section32300431736"></a>

使用如下的YAML文件在添加Ingress时对接已有的ELB。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   1.15及以上集群版本中的apiVersion为: networking.k8s.io/v1beta1
>-   1.13及以下集群版本中的apiVersion为: extensions/v1beta1

**以1.15及以上集群版本为例，yaml文件配置如下：**

```
apiVersion: networking.k8s.io/v1beta1
kind: Ingress 
metadata: 
  name: ingress-test
  annotations: 
    kubernetes.io/elb.id: <your_elb_id>  #替换为您已有的ELB ID
    kubernetes.io/elb.ip: <your_elb_ip>  #替换为您已有的ELB IP
    kubernetes.io/elb.port: '80'
    kubernetes.io/ingress.class: cce
spec:
  rules: 
  - host: ''
    http: 
      paths: 
      - path: '/'
        backend: 
          serviceName: <your_service_name>  #替换为您的目标服务名称
          servicePort: 80
        property:
          ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
```

**表 3**  关键参数说明

<a name="table1892373611597"></a>
<table><thead align="left"><tr id="row16921123616594"><th class="cellrowborder" valign="top" width="24.772477247724773%" id="mcps1.2.5.1.1"><p id="p092111361598"><a name="p092111361598"></a><a name="p092111361598"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13.691369136913693%" id="mcps1.2.5.1.2"><p id="p4921736125920"><a name="p4921736125920"></a><a name="p4921736125920"></a>是否必填</p>
</th>
<th class="cellrowborder" valign="top" width="13.821382138213819%" id="mcps1.2.5.1.3"><p id="p992173615594"><a name="p992173615594"></a><a name="p992173615594"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.714771477147714%" id="mcps1.2.5.1.4"><p id="p15921143625917"><a name="p15921143625917"></a><a name="p15921143625917"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row892173675917"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p1292133635910"><a name="p1292133635910"></a><a name="p1292133635910"></a>kubernetes.io/elb.id</p>
</td>
<td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p8921936145914"><a name="p8921936145914"></a><a name="p8921936145914"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p09214367590"><a name="p09214367590"></a><a name="p09214367590"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p692133675916"><a name="p692133675916"></a><a name="p692133675916"></a>为负载均衡实例的ID，取值范围：1-100字符。</p>
<p id="p1892183614596"><a name="p1892183614596"></a><a name="p1892183614596"></a><strong id="b092111362592"><a name="b092111362592"></a><a name="b092111362592"></a>获取方法：</strong></p>
<p id="p1092183616594"><a name="p1092183616594"></a><a name="p1092183616594"></a>在控制台的<span class="uicontrol" id="uicontrol192111362595"><a name="uicontrol192111362595"></a><a name="uicontrol192111362595"></a>“服务列表”</span>中，单击<span class="uicontrol" id="uicontrol1192113619595"><a name="uicontrol1192113619595"></a><a name="uicontrol1192113619595"></a>“网络 &gt; 弹性负载均衡 ELB”</span>，单击ELB的名称，在ELB详情页的<span class="uicontrol" id="uicontrol1392113368595"><a name="uicontrol1392113368595"></a><a name="uicontrol1392113368595"></a>“基本信息”</span>页签下找到<span class="uicontrol" id="uicontrol092183619596"><a name="uicontrol092183619596"></a><a name="uicontrol092183619596"></a>“ID”</span>字段复制即可。</p>
</td>
</tr>
<tr id="row2921183614593"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p159212365592"><a name="p159212365592"></a><a name="p159212365592"></a>kubernetes.io/elb.ip</p>
</td>
<td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p492116364592"><a name="p492116364592"></a><a name="p492116364592"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p79211436195917"><a name="p79211436195917"></a><a name="p79211436195917"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p4921183685915"><a name="p4921183685915"></a><a name="p4921183685915"></a>为负载均衡实例的服务地址，公网ELB配置为公网IP，私网ELB配置为私网IP。</p>
</td>
</tr>
</tbody>
</table>

## 配置HTTPS证书<a name="section36631016135518"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   服务需要以HTTPS协议的方式对外暴露时，需要在Ingress中配置TLS密钥证书。创建密钥的方法请参见[创建密钥](创建密钥.md)。
>-   同一个ELB实例的同一个端口配置HTTPS时，需要选择一样的证书。

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，创建名为“**ingress-test-secret.yaml**”的yaml文件。

    **vi ingress-test-secret.yaml**

    **yaml文件配置如下：**

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

3.  执行如下命令创建密钥：

    **kubectl create -f  **ingress-test-secret.yaml****

    回显如下，表明密钥已创建。

    ```
    secret/ingress-test-secret created
    ```

    **kubectl get secrets**

    回显如下，表明密钥创建成功。

    ```
    NAME                         TYPE                                  DATA      AGE
    ingress-test-secret          IngressTLS                            2         13s
    ```

4.  执行如下命令，创建名为“**ingress-test.yaml**”的yaml文件。

    **vi ingress-test.yaml**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   安全策略选择（kubernetes.io/elb.tls-ciphers-policy）仅在1.17.11及以上版本的集群中支持。

    **以自动创建关联ELB为例，yaml文件配置如下：**

    ```
    apiVersion: networking.k8s.io/v1beta1
    kind: Ingress 
    metadata: 
      name: ingress-test
      annotations: 
        kubernetes.io/elb.class: union
        kubernetes.io/ingress.class: cce
        kubernetes.io/elb.port: '443'
        kubernetes.io/elb.subnet-id: <your_subnet_id>  #替换为您的子网所在ID
        kubernetes.io/elb.enterpriseID: <your_enterprise_id>  #替换为您的企业项目ID
        kubernetes.io/elb.autocreate: 
          '{
              "type":"public",
              "bandwidth_name":"cce-bandwidth-15511633796**",
              "bandwidth_chargemode":"bandwidth",
              "bandwidth_size":5,
              "bandwidth_sharetype":"PER",
              "eip_type":"5_bgp",
              "name":"james"
            }'
        kubernetes.io/elb.tls-ciphers-policy: tls-1-2
    spec:
      tls: 
      - secretName: ingress-test-secret
      rules: 
      - host: ''
        http: 
          paths: 
          - path: '/'
            backend: 
              serviceName: <your_service_name>  #替换为您的目标服务名称
              servicePort: 80
            property:
              ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
    ```

    **表 4**  关键参数说明

    <a name="table1863255917310"></a>
    <table><thead align="left"><tr id="row186321759239"><th class="cellrowborder" valign="top" width="24.71247124712471%" id="mcps1.2.5.1.1"><p id="p1263235917316"><a name="p1263235917316"></a><a name="p1263235917316"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="13.751375137513753%" id="mcps1.2.5.1.2"><p id="p963214591737"><a name="p963214591737"></a><a name="p963214591737"></a>是否必填</p>
    </th>
    <th class="cellrowborder" valign="top" width="13.821382138213819%" id="mcps1.2.5.1.3"><p id="p1363265910318"><a name="p1363265910318"></a><a name="p1363265910318"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="47.714771477147714%" id="mcps1.2.5.1.4"><p id="p76329592316"><a name="p76329592316"></a><a name="p76329592316"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row10633135911311"><td class="cellrowborder" valign="top" width="24.71247124712471%" headers="mcps1.2.5.1.1 "><p id="p106331259333"><a name="p106331259333"></a><a name="p106331259333"></a>kubernetes.io/elb.tls-ciphers-policy</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.751375137513753%" headers="mcps1.2.5.1.2 "><p id="p13633135920314"><a name="p13633135920314"></a><a name="p13633135920314"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p15633105915316"><a name="p15633105915316"></a><a name="p15633105915316"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p063325911310"><a name="p063325911310"></a><a name="p063325911310"></a>默认值：“tls-1-2”，为监听器使用的安全策略，仅在HTTPS协议下生效。</p>
    <p id="p166332591835"><a name="p166332591835"></a><a name="p166332591835"></a>取值范围：</p>
    <a name="ul86338598319"></a><a name="ul86338598319"></a><ul id="ul86338598319"><li>tls-1-0</li><li>tls-1-1</li><li>tls-1-2</li><li>tls-1-2-strict</li></ul>
    <p id="p166331559238"><a name="p166331559238"></a><a name="p166331559238"></a>各安全策略使用的加密套件列表详细参见<a href="#table29246363592">表5</a>。</p>
    </td>
    </tr>
    <tr id="row7634559238"><td class="cellrowborder" valign="top" width="24.71247124712471%" headers="mcps1.2.5.1.1 "><p id="p26341859831"><a name="p26341859831"></a><a name="p26341859831"></a>tls</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.751375137513753%" headers="mcps1.2.5.1.2 "><p id="p1163445920314"><a name="p1163445920314"></a><a name="p1163445920314"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p136345594315"><a name="p136345594315"></a><a name="p136345594315"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p163416591030"><a name="p163416591030"></a><a name="p163416591030"></a>HTTPS协议时，需添加此字段。该字段可添加多项独立的域名和证书，详见<a href="#section521123214343">配置服务器名称指示（SNI）</a>。</p>
    </td>
    </tr>
    <tr id="row186348591130"><td class="cellrowborder" valign="top" width="24.71247124712471%" headers="mcps1.2.5.1.1 "><p id="p36349599310"><a name="p36349599310"></a><a name="p36349599310"></a>secretName</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.751375137513753%" headers="mcps1.2.5.1.2 "><p id="p1463415591936"><a name="p1463415591936"></a><a name="p1463415591936"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p1163414591139"><a name="p1163414591139"></a><a name="p1163414591139"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p12634105916314"><a name="p12634105916314"></a><a name="p12634105916314"></a>HTTPS协议时添加，配置为创建的密钥证书名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 5**  tls\_ciphers\_policy取值说明

    <a name="table29246363592"></a>
    <table><thead align="left"><tr id="row18923113675911"><th class="cellrowborder" valign="top" width="16.37%" id="mcps1.2.4.1.1"><p id="p7923173605914"><a name="p7923173605914"></a><a name="p7923173605914"></a>安全策略</p>
    </th>
    <th class="cellrowborder" valign="top" width="25.71%" id="mcps1.2.4.1.2"><p id="p092303685911"><a name="p092303685911"></a><a name="p092303685911"></a>支持的TLS版本类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="57.92%" id="mcps1.2.4.1.3"><p id="p169231236165913"><a name="p169231236165913"></a><a name="p169231236165913"></a>使用的加密套件列表</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row11924183612598"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p1592320365598"><a name="p1592320365598"></a><a name="p1592320365598"></a>tls-1-0</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p1192373665915"><a name="p1192373665915"></a><a name="p1192373665915"></a>TLS 1.2</p>
    <p id="p7924143619597"><a name="p7924143619597"></a><a name="p7924143619597"></a>TLS 1.1</p>
    <p id="p159241036195915"><a name="p159241036195915"></a><a name="p159241036195915"></a>TLS 1.0</p>
    </td>
    <td class="cellrowborder" rowspan="3" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p3924133625919"><a name="p3924133625919"></a><a name="p3924133625919"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:AES128-GCM-SHA256:AES256-GCM-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES128-SHA256:AES256-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA:ECDHE-RSA-AES128-SHA:ECDHE-RSA-AES256-SHA:ECDHE-ECDSA-AES256-SHA:AES128-SHA:AES256-SHA</p>
    </td>
    </tr>
    <tr id="row169241436155919"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p20924636195917"><a name="p20924636195917"></a><a name="p20924636195917"></a>tls-1-1</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1992419369590"><a name="p1992419369590"></a><a name="p1992419369590"></a>TLS 1.2</p>
    <p id="p4924163611593"><a name="p4924163611593"></a><a name="p4924163611593"></a>TLS 1.1</p>
    </td>
    </tr>
    <tr id="row14924193610599"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p3924236145917"><a name="p3924236145917"></a><a name="p3924236145917"></a>tls-1-2</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p13924436145917"><a name="p13924436145917"></a><a name="p13924436145917"></a>TLS 1.2</p>
    </td>
    </tr>
    <tr id="row19241736135916"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p15924103617596"><a name="p15924103617596"></a><a name="p15924103617596"></a>tls-1-2-strict</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p1292433613597"><a name="p1292433613597"></a><a name="p1292433613597"></a>TLS 1.2</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p1692413685915"><a name="p1692413685915"></a><a name="p1692413685915"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:AES128-GCM-SHA256:AES256-GCM-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES128-SHA256:AES256-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384</p>
    </td>
    </tr>
    <tr id="row119241736105915"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p192493605915"><a name="p192493605915"></a><a name="p192493605915"></a>TLS-1-0-WITH-1-3（独享型实例）</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p6924203635910"><a name="p6924203635910"></a><a name="p6924203635910"></a>TLS 1.3</p>
    <p id="p192412369599"><a name="p192412369599"></a><a name="p192412369599"></a>TLS 1.2</p>
    <p id="p1892493675912"><a name="p1892493675912"></a><a name="p1892493675912"></a>TLS 1.1</p>
    <p id="p209249369599"><a name="p209249369599"></a><a name="p209249369599"></a>TLS 1.0</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p892433605916"><a name="p892433605916"></a><a name="p892433605916"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:AES128-GCM-SHA256:AES256-GCM-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:AES128-SHA256:AES256-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA:ECDHE-RSA-AES128-SHA:ECDHE-RSA-AES256-SHA:ECDHE-ECDSA-AES256-SHA:AES128-SHA:AES256-SHA:TLS_AES_256_GCM_SHA384:TLS_CHACHA20_POLY1305_SHA256:TLS_AES_128_GCM_SHA256:TLS_AES_128_CCM_8_SHA256:TLS_AES_128_CCM_SHA256</p>
    </td>
    </tr>
    <tr id="row6924336155912"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p1692493616591"><a name="p1692493616591"></a><a name="p1692493616591"></a>TLS-1-2-FS（独享型实例）</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p15924113665912"><a name="p15924113665912"></a><a name="p15924113665912"></a>TLS 1.3</p>
    <p id="p492453695917"><a name="p492453695917"></a><a name="p492453695917"></a>TLS 1.2</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p16924113635914"><a name="p16924113635914"></a><a name="p16924113635914"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384</p>
    </td>
    </tr>
    <tr id="row79249365599"><td class="cellrowborder" valign="top" width="16.37%" headers="mcps1.2.4.1.1 "><p id="p6924183612594"><a name="p6924183612594"></a><a name="p6924183612594"></a>TLS-1-2-FS-WITH-1-3（独享型实例）</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.71%" headers="mcps1.2.4.1.2 "><p id="p17924136155912"><a name="p17924136155912"></a><a name="p17924136155912"></a>TLS 1.3</p>
    <p id="p492415366598"><a name="p492415366598"></a><a name="p492415366598"></a>TLS 1.2</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.92%" headers="mcps1.2.4.1.3 "><p id="p16924153616596"><a name="p16924153616596"></a><a name="p16924153616596"></a>ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:TLS_AES_256_GCM_SHA384:TLS_CHACHA20_POLY1305_SHA256:TLS_AES_128_GCM_SHA256:TLS_AES_128_CCM_8_SHA256:TLS_AES_128_CCM_SHA256</p>
    </td>
    </tr>
    </tbody>
    </table>

5.  执行如下命令创建Ingress。

    **kubectl create -f ingress-test.yaml**

    回显如下，表示Ingress服务已创建。

    ```
    ingress/ingress-test created
    ```

    **kubectl get ingress**

    回显如下，表示Ingress服务创建成功，工作负载可访问。

    ```
    NAME             HOSTS     ADDRESS          PORTS   AGE
    ingress-test     *         121.**.**.**     80      10s
    ```

6.  访问工作负载（例如[nginx工作负载](创建无状态负载(Deployment).md#section155246177178)），在浏览器中输入安全访问地址https://121.\*\*.\*\*.\*\*:443进行验证。

    其中，121.\*\*.\*\*.\*\*为统一负载均衡实例的IP地址。


## 配置服务器名称指示（SNI）<a name="section521123214343"></a>

SNI允许同一个IP地址和端口号下对外提供多个基于TLS的访问域名，且不同的域名可以使用不同的安全证书。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   用于SNI的证书需要指定域名，每个证书只能指定一个域名。支持泛域名证书。
>-   安全策略选择（kubernetes.io/elb.tls-ciphers-policy）仅在1.17.11及以上版本的集群中支持。

满足以上条件时可进行SNI配置，以自动创建关联ELB为例，yaml文件配置如下，本例中**sni-test-secret-1**、**sni-test-secret-2**为SNI证书，该证书指定的域名必须与证书中的域名一致。

```
apiVersion: networking.k8s.io/v1beta1
kind: Ingress 
metadata: 
  name: ingress-test
  annotations: 
    kubernetes.io/elb.class: union
    kubernetes.io/ingress.class: cce
    kubernetes.io/elb.port: '443'
    kubernetes.io/elb.subnet-id: <your_subnet_id>  #替换为您的子网所在ID
    kubernetes.io/elb.enterpriseID: <your_enterprise_id>  #替换为您的企业项目ID
    kubernetes.io/elb.autocreate: 
      '{
          "type":"public",
          "bandwidth_name":"cce-bandwidth-******",
          "bandwidth_chargemode":"bandwidth",
          "bandwidth_size":5,
          "bandwidth_sharetype":"PER",
          "eip_type":"5_bgp",
          "name":"james"
        }'
    kubernetes.io/elb.tls-ciphers-policy: tls-1-2
spec:
  tls: 
  - secretName: ingress-test-secret
  - hosts:
      - example.top  #签发证书时指定域名为example.top
    secretName: sni-test-secret-1  
  - hosts:
      - example.com  #签发证书时指定域名为example.com
    secretName: sni-test-secret-2
  rules: 
  - host: ''
    http: 
      paths: 
      - path: '/'
        backend: 
          serviceName: <your_service_name>  #替换为您的目标服务名称
          servicePort: 80
        property:
          ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
```

## 路由到多个服务<a name="section191179210715"></a>

Ingress可通过不同的匹配策略同时路由到多个后端服务，yaml文件中spec字段设置如下，通过访问“www.example.com/foo”、“www.example.com/bar”、“foo.example.com/”即可分别路由到三个不同的后端Service。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>Ingress转发策略中注册的URL需与后端应用暴露的URL一致，否则将返回404错误。

```
spec:
  rules: 
  - host: 'www.example.com'
    http: 
      paths: 
      - path: '/foo'
        backend: 
          serviceName: <your_service_name>  #替换为您的目标服务名称
          servicePort: 80
        property:
          ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
      - path: '/bar'
        backend:
          serviceName: <your_service_name>  #替换为您的目标服务名称
          servicePort: 80
        property:
          ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
  - host: 'foo.example.com'
    http:
      paths:
      - path: '/'
        backend:
          serviceName: <your_service_name>  #替换为您的目标服务名称
          servicePort: 80
        property:
          ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
```

