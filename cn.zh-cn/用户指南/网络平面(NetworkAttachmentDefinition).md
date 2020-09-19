# 网络平面\(NetworkAttachmentDefinition\)<a name="cce_01_0196"></a>

网络平面（NetworkAttachmentDefinition）是集群的一种crd资源，为容器对接ENI（Elastic Network Interface，弹性网络接口）提供配置项，如VPC，子网等。关联网络平面的工作负载支持对接弹性网卡服务，容器能直接绑定弹性网卡，并对外提供服务。

**图 1**  网络平面<a name="fig8117226195717"></a>  
![](figures/网络平面.png "网络平面")

## 约束与限制<a name="section332285584912"></a>

-   仅网络模型为VPC网络（未开启IPv6）和Yangtse的集群支持创建网络平面；网络模型为容器隧道网络时列表中仅显示“default-network“，不能新增或修改。
-   VPC Router网络模型不支持NetworkPolicy。
-   需v1.13.7-r0及以上版本的集群才能启用，v1.13.7-r0以下版本集群需要升级到最新版本后才能启用。

## 通过界面创建<a name="section1231151981314"></a>

1.  单击CCE左侧导航栏的“资源管理 \> 网络管理”。
2.  在“网络平面（NetworkAttachmentDefinition）“页签下，在右上角选择框中点选要操作的集群，单击“添加网络平面“。

    **图 2**  添加网络平面<a name="fig1778184810539"></a>  
    ![](figures/添加网络平面.png "添加网络平面")

    集群默认创建一个“default-network“，默认的network资源包含了tenant\_id、vpc\_id、subnet等等信息。

    **图 3**  默认网络平面<a name="fig684420255312"></a>  
    ![](figures/默认网络平面.png "默认网络平面")

3.  在添加网络平面页面，设置基本信息。

    -   网络平面名称：自定义名称，请输入长度范围为4-63的字符。

        default-network、default、mgnt0、mgnt1四个名称为系统预留，请勿使用。

    -   集群名称：请选择要添加网络平面的集群。
    -   安全组：安全组给弹性网卡提供访问策略，最多可以选择5条，安全组必选，不可缺省。
    -   子网：请选择子网。若无子网可选请单击后方的“创建子网“进行创建，创建完成后单击刷新按钮。

    **图 4**  填写网络平面参数<a name="fig177965497231"></a>  
    ![](figures/填写网络平面参数.png "填写网络平面参数")

4.  完成基本配置后单击“创建“，创建完成后页面将自动返回到网络平面列表页，可以看到新添加的网络平面已在列表中。

    **图 5**  添加网络平面成功<a name="fig14288182152314"></a>  
    ![](figures/添加网络平面成功.png "添加网络平面成功")


## 通过kubectl命令行创建<a name="section1111120232202"></a>

1.  登录已配置好kubectl命令的弹性云服务器。登录方法请参见[登录Linux弹性云服务器](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0013771089.html)。
2.  创建networkattachment-test.yaml

    **vi networkattachment-test.yaml**

    ```
    apiVersion: k8s.cni.cncf.io/v1
    kind: NetworkAttachmentDefinition
    metadata:
      annotations:
        tenant_id: 052fd975a300d31e2f90c01ab87e5839
      generation: 3
      name: networkattach
      namespace: kube-system
    spec:
      config: >-
        {"cniVersion":"0.2.0","name":"networkattach","type":"eni-neutron","bridge":"br0","args":{"phynet":"phy_net2","vpc_id":"7a4d731e-fe17-4b72-aa17-962b8363b2d3","securityGroups":"3289d598-8e05-40d8-b726-1f2c425d4935","subnetID":"2945a96b-03a0-4e11-9012-746fe09f714d","cidr":"192.168.1.0/24","availableZone":"cn-north-7b","region":"cn-north-7"}}
    status:
      state: Active
    ```

    **表 1**  关键参数说明

    <a name="table81905502536"></a>
    <table><thead align="left"><tr id="row1219065015536"><th class="cellrowborder" valign="top" width="30.316968303169684%" id="mcps1.2.4.1.1"><p id="p10190125025311"><a name="p10190125025311"></a><a name="p10190125025311"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.088191180881914%" id="mcps1.2.4.1.2"><p id="p2190175085316"><a name="p2190175085316"></a><a name="p2190175085316"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="51.594840515948405%" id="mcps1.2.4.1.3"><p id="p14190650125319"><a name="p14190650125319"></a><a name="p14190650125319"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row181901450105314"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p1190250175319"><a name="p1190250175319"></a><a name="p1190250175319"></a>tenant_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p519065016538"><a name="p519065016538"></a><a name="p519065016538"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p14190850165311"><a name="p14190850165311"></a><a name="p14190850165311"></a>租户ID</p>
    </td>
    </tr>
    <tr id="row1190185013533"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p2019111500531"><a name="p2019111500531"></a><a name="p2019111500531"></a>config</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p1019115502535"><a name="p1019115502535"></a><a name="p1019115502535"></a><a href="#table4439454105314">表2 config字段数据结构说明</a>Object</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p17191150135310"><a name="p17191150135310"></a><a name="p17191150135310"></a>网络平面配置参数</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  config字段数据结构说明

    <a name="table4439454105314"></a>
    <table><thead align="left"><tr id="row19439165415312"><th class="cellrowborder" valign="top" width="30.316968303169684%" id="mcps1.2.4.1.1"><p id="p9439165416538"><a name="p9439165416538"></a><a name="p9439165416538"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.088191180881914%" id="mcps1.2.4.1.2"><p id="p15439175410531"><a name="p15439175410531"></a><a name="p15439175410531"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="51.594840515948405%" id="mcps1.2.4.1.3"><p id="p19439454105314"><a name="p19439454105314"></a><a name="p19439454105314"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row17439165411537"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p1243955405320"><a name="p1243955405320"></a><a name="p1243955405320"></a>cniVersion</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p10439105495317"><a name="p10439105495317"></a><a name="p10439105495317"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p134391054155313"><a name="p134391054155313"></a><a name="p134391054155313"></a>cni版本</p>
    </td>
    </tr>
    <tr id="row743916543538"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p660861418561"><a name="p660861418561"></a><a name="p660861418561"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p1643935475311"><a name="p1643935475311"></a><a name="p1643935475311"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p7439135435312"><a name="p7439135435312"></a><a name="p7439135435312"></a>网络平面的名称。</p>
    <p id="p1126448113215"><a name="p1126448113215"></a><a name="p1126448113215"></a>取值范围：1-64个字符，小写字母，数字，下划线，小写字母开头，小写字母或者数字结尾。</p>
    </td>
    </tr>
    <tr id="row14439854155320"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p1644075419532"><a name="p1644075419532"></a><a name="p1644075419532"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p1544020545533"><a name="p1544020545533"></a><a name="p1544020545533"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p444019541535"><a name="p444019541535"></a><a name="p444019541535"></a>网络平面类型：</p>
    <a name="ul13582136163317"></a><a name="ul13582136163317"></a><ul id="ul13582136163317"><li>eni-neutron ： eni网络模式</li><li>vpc-router ： VPC路由网络模式</li><li>overlay_l2 ：容器隧道网络模式</li></ul>
    </td>
    </tr>
    <tr id="row1944085405311"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p124401544538"><a name="p124401544538"></a><a name="p124401544538"></a>bridge</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p124402054185318"><a name="p124402054185318"></a><a name="p124402054185318"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p10440175455315"><a name="p10440175455315"></a><a name="p10440175455315"></a>网桥</p>
    </td>
    </tr>
    <tr id="row7440145465316"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p15440175414534"><a name="p15440175414534"></a><a name="p15440175414534"></a>args</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p1544010545534"><a name="p1544010545534"></a><a name="p1544010545534"></a><a href="#table166983186418">表3 args字段数据结构说明</a></p>
    <p id="p15895635541"><a name="p15895635541"></a><a name="p15895635541"></a>Object</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p13440154115316"><a name="p13440154115316"></a><a name="p13440154115316"></a>网络平面的配置参数</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 3**  args字段数据结构说明

    <a name="table166983186418"></a>
    <table><thead align="left"><tr id="row76982189416"><th class="cellrowborder" valign="top" width="30.316968303169684%" id="mcps1.2.4.1.1"><p id="p156987182045"><a name="p156987182045"></a><a name="p156987182045"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.088191180881914%" id="mcps1.2.4.1.2"><p id="p206983182417"><a name="p206983182417"></a><a name="p206983182417"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="51.594840515948405%" id="mcps1.2.4.1.3"><p id="p869811812411"><a name="p869811812411"></a><a name="p869811812411"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1969815181443"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p269810181419"><a name="p269810181419"></a><a name="p269810181419"></a>phynet</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p1169811815411"><a name="p1169811815411"></a><a name="p1169811815411"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p20145115201915"><a name="p20145115201915"></a><a name="p20145115201915"></a>物理网络平面</p>
    </td>
    </tr>
    <tr id="row146989181347"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p86983189411"><a name="p86983189411"></a><a name="p86983189411"></a>vpc_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p1569813189420"><a name="p1569813189420"></a><a name="p1569813189420"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p3698918946"><a name="p3698918946"></a><a name="p3698918946"></a>虚拟私有云ID</p>
    </td>
    </tr>
    <tr id="row126981918346"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p206986181540"><a name="p206986181540"></a><a name="p206986181540"></a>securityGroups</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p206981218044"><a name="p206981218044"></a><a name="p206981218044"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1169841811412"><a name="p1169841811412"></a><a name="p1169841811412"></a>安全组ID，取值范围：1-100字符。</p>
    <p id="p67014121615"><a name="p67014121615"></a><a name="p67014121615"></a>获取方式：</p>
    <p id="p112261971615"><a name="p112261971615"></a><a name="p112261971615"></a>在控制台的<span class="uicontrol" id="uicontrol8385124317594"><a name="uicontrol8385124317594"></a><a name="uicontrol8385124317594"></a>“服务列表”</span>中，单击<span class="uicontrol" id="uicontrol12432719902"><a name="uicontrol12432719902"></a><a name="uicontrol12432719902"></a>“网络 &gt; 弹性负载均衡 ELB”</span>，单击“访问控制 &gt; 安全组”，单击安全组名称，在安全组详情页的<span class="uicontrol" id="uicontrol762734213311"><a name="uicontrol762734213311"></a><a name="uicontrol762734213311"></a>“基本信息”</span>页签下找到<span class="uicontrol" id="uicontrol1139664010108"><a name="uicontrol1139664010108"></a><a name="uicontrol1139664010108"></a>“ID”</span>字段复制即可。</p>
    </td>
    </tr>
    <tr id="row2069815189415"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p869811811412"><a name="p869811811412"></a><a name="p869811811412"></a>subnetID</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p3698618645"><a name="p3698618645"></a><a name="p3698618645"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p869813182419"><a name="p869813182419"></a><a name="p869813182419"></a>子网ID，取值范围：1-100字符。</p>
    <p id="p1458517992217"><a name="p1458517992217"></a><a name="p1458517992217"></a>获取方式：</p>
    <p id="p8194415162211"><a name="p8194415162211"></a><a name="p8194415162211"></a>在控制台的<span class="uicontrol" id="uicontrol16592112613227"><a name="uicontrol16592112613227"></a><a name="uicontrol16592112613227"></a>“服务列表”</span>中，单击<span class="uicontrol" id="uicontrol14592326192217"><a name="uicontrol14592326192217"></a><a name="uicontrol14592326192217"></a>“网络 &gt; 弹性负载均衡 ELB”</span>，单击“子网”，单击子网名称，在子网详情页的<span class="uicontrol" id="uicontrol13592122672214"><a name="uicontrol13592122672214"></a><a name="uicontrol13592122672214"></a>“基本信息”</span>页签下找到<span class="uicontrol" id="uicontrol7592132692220"><a name="uicontrol7592132692220"></a><a name="uicontrol7592132692220"></a>“子网ID”</span>字段复制即可。</p>
    </td>
    </tr>
    <tr id="row136986181340"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p10698118342"><a name="p10698118342"></a><a name="p10698118342"></a>cidr</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p1769814181043"><a name="p1769814181043"></a><a name="p1769814181043"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1269818185412"><a name="p1269818185412"></a><a name="p1269818185412"></a>无类别域间路由</p>
    </td>
    </tr>
    <tr id="row580942914514"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p13809529252"><a name="p13809529252"></a><a name="p13809529252"></a>availableZone</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p148091429152"><a name="p148091429152"></a><a name="p148091429152"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1809202914513"><a name="p1809202914513"></a><a name="p1809202914513"></a>可用区。</p>
    <p id="p1375465855018"><a name="p1375465855018"></a><a name="p1375465855018"></a>可用区是同一服务区内，电力和网络互相独立的地理区域，一般是一个独立的物理机房，这样可以保证可用区的独立性。</p>
    </td>
    </tr>
    <tr id="row54478441752"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p204479447511"><a name="p204479447511"></a><a name="p204479447511"></a>region</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p1447174413518"><a name="p1447174413518"></a><a name="p1447174413518"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p154473442050"><a name="p154473442050"></a><a name="p154473442050"></a>区域。</p>
    <p id="p185052119514"><a name="p185052119514"></a><a name="p185052119514"></a>不同区域的资源之间内网不互通。请选择靠近您客户的区域，可以降低网络时延、提高访问速度。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 其他操作<a name="section2314125415245"></a>

您可以查看新添加网络平面的YAML，也可以对新添加的网络平面进行“删除“操作。

>![](public_sys-resources/icon-note.gif) **说明：** 
>如果网络平面已经被工作负载绑定且在使用中，则不能被删除。如需删除该网络平面，请先删除绑定的工作负载。

**图 6**  管理网络平面<a name="fig29028593411"></a>  
![](figures/管理网络平面.png "管理网络平面")

