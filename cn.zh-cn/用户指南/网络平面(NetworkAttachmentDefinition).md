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
    -   安全组：安全组给弹性网卡提供访问策略，最多可以选择5条，未选择时默认使用缺省安全组。
    -   子网：请选择子网。若无子网可选请单击后方的“创建子网“进行创建，创建完成后单击刷新按钮。

    **图 4**  填写网络平面参数<a name="fig177965497231"></a>  
    ![](figures/填写网络平面参数.png "填写网络平面参数")

4.  完成基本配置后单击“创建“，创建完成后页面将自动返回到网络平面列表页，可以看到新添加的网络平面已在列表中。

    **图 5**  添加网络平面成功<a name="fig14288182152314"></a>  
    ![](figures/添加网络平面成功.png "添加网络平面成功")


## 通过kubectl命令行创建<a name="section1111120232202"></a>

**操作步骤**

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

<a name="table1819001615355"></a>
<table><thead align="left"><tr id="row1519121663519"><th class="cellrowborder" valign="top" width="30.316968303169684%" id="mcps1.2.4.1.1"><p id="p18191161619356"><a name="p18191161619356"></a><a name="p18191161619356"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.088191180881914%" id="mcps1.2.4.1.2"><p id="p1191141613357"><a name="p1191141613357"></a><a name="p1191141613357"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="51.594840515948405%" id="mcps1.2.4.1.3"><p id="p1919116161353"><a name="p1919116161353"></a><a name="p1919116161353"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15191171618357"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p5788113218236"><a name="p5788113218236"></a><a name="p5788113218236"></a>tenant_id</p>
</td>
<td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p54093956"><a name="zh-cn_topic_0079615000_p54093956"></a><a name="zh-cn_topic_0079615000_p54093956"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p167881320237"><a name="p167881320237"></a><a name="p167881320237"></a>租户ID</p>
</td>
</tr>
<tr id="row02694357138"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p6716134816295"><a name="p6716134816295"></a><a name="p6716134816295"></a>config</p>
</td>
<td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p18968549"><a name="zh-cn_topic_0079615000_p18968549"></a><a name="zh-cn_topic_0079615000_p18968549"></a><a href="#table4439454105314">表2 config字段数据结构说明</a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1135018115411"><a name="p1135018115411"></a><a name="p1135018115411"></a>网络平面配置参数</p>
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
<a name="ul13582136163317"></a><a name="ul13582136163317"></a><ul id="ul13582136163317"><li>eni-neutron</li></ul>
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
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 ">&nbsp;&nbsp;</td>
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
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1809202914513"><a name="p1809202914513"></a><a name="p1809202914513"></a>可用区域</p>
</td>
</tr>
<tr id="row54478441752"><td class="cellrowborder" valign="top" width="30.316968303169684%" headers="mcps1.2.4.1.1 "><p id="p204479447511"><a name="p204479447511"></a><a name="p204479447511"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="18.088191180881914%" headers="mcps1.2.4.1.2 "><p id="p1447174413518"><a name="p1447174413518"></a><a name="p1447174413518"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p154473442050"><a name="p154473442050"></a><a name="p154473442050"></a>地区</p>
</td>
</tr>
</tbody>
</table>

## Pod中指定网络能力<a name="section17897104515244"></a>

创建Pod时，在annotations中指定“_**k8s.v1.cni.cncf.io/networks**_”字段即可指定网络相关能力。暂不支持更新操作。“_**k8s.v1.cni.cncf.io/networks**_”数组中每个元素的数据结构说明请参考[表4](#table157916567165)。

**表 4** **k8s.v1.cni.cncf.io/networks**元素数据结构说明

<a name="table157916567165"></a>
<table><thead align="left"><tr id="row19798568161"><th class="cellrowborder" valign="top" width="16.798320167983203%" id="mcps1.2.5.1.1"><p id="p17935681612"><a name="p17935681612"></a><a name="p17935681612"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="9.42905709429057%" id="mcps1.2.5.1.2"><p id="p97965691615"><a name="p97965691615"></a><a name="p97965691615"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="42.94570542945706%" id="mcps1.2.5.1.3"><p id="p979256131620"><a name="p979256131620"></a><a name="p979256131620"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="30.826917308269174%" id="mcps1.2.5.1.4"><p id="p579165621613"><a name="p579165621613"></a><a name="p579165621613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1779105621610"><td class="cellrowborder" valign="top" width="16.798320167983203%" headers="mcps1.2.5.1.1 "><p id="p107965613162"><a name="p107965613162"></a><a name="p107965613162"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="9.42905709429057%" headers="mcps1.2.5.1.2 "><p id="p11791456151613"><a name="p11791456151613"></a><a name="p11791456151613"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="42.94570542945706%" headers="mcps1.2.5.1.3 "><p id="p187955614164"><a name="p187955614164"></a><a name="p187955614164"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="30.826917308269174%" headers="mcps1.2.5.1.4 "><p id="p17985610167"><a name="p17985610167"></a><a name="p17985610167"></a>Pod实例所在network名称</p>
</td>
</tr>
<tr id="row4791456171619"><td class="cellrowborder" valign="top" width="16.798320167983203%" headers="mcps1.2.5.1.1 "><p id="p07955615162"><a name="p07955615162"></a><a name="p07955615162"></a>pniPool</p>
</td>
<td class="cellrowborder" valign="top" width="9.42905709429057%" headers="mcps1.2.5.1.2 "><p id="p279165618164"><a name="p279165618164"></a><a name="p279165618164"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="42.94570542945706%" headers="mcps1.2.5.1.3 "><p id="p1179145612169"><a name="p1179145612169"></a><a name="p1179145612169"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="30.826917308269174%" headers="mcps1.2.5.1.4 "><p id="p13791156141612"><a name="p13791156141612"></a><a name="p13791156141612"></a>Pod实例对应PNI所在的PNIPool名称<strong id="b67975681618"><a name="b67975681618"></a><a name="b67975681618"></a>注意</strong>：</p>
<a name="ul1479056161617"></a><a name="ul1479056161617"></a><ul id="ul1479056161617"><li>pniPool在network下，两者强相关。</li><li>更新name或pnipool时，必须保证pnipool在network下</li></ul>
</td>
</tr>
</tbody>
</table>

请求示例：

```
{
    "apiVersion":"v1",
    "kind":"Pod",
    "metadata":{
        "annotations":{
            "k8s.v1.cni.cncf.io/networks":"[{\"pniPool\": \"pool1\",\"name\": \"network1\"}]"
        },
        "labels":{
            "name":"test-pod"
        },
        "name":"test-pod"
    },
    "spec":{
        "containers":[
            {
                "image":"test-image",
                "imagePullPolicy":"IfNotPresent",
                "name":"test",
                "resources":{
                    "requests":{
                        "cpu":"100m"
                    }
                }
            }
        ],
        "imagePullSecrets":[
            {
                "name":"default-secret"
            }
        ],
        "restartPolicy":"Always"
    }
}
```

查看Pod时，网络相关属性将回写在annotations中“_**k8s.v1.cni.cncf.io/network-status**_”字段下。详情请参考[表5](#table42941427162412)

**表 5** **k8s.v1.cni.cncf.io/network-status**字段数据结构说明

<a name="table42941427162412"></a>
<table><thead align="left"><tr id="row20295127112412"><th class="cellrowborder" valign="top" width="11.77117711771177%" id="mcps1.2.4.1.1"><p id="p9777922205616"><a name="p9777922205616"></a><a name="p9777922205616"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.842084208420843%" id="mcps1.2.4.1.2"><p id="p1777717223565"><a name="p1777717223565"></a><a name="p1777717223565"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="67.38673867386738%" id="mcps1.2.4.1.3"><p id="p157771522195616"><a name="p157771522195616"></a><a name="p157771522195616"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row429512715241"><td class="cellrowborder" valign="top" width="11.77117711771177%" headers="mcps1.2.4.1.1 "><p id="p22954273245"><a name="p22954273245"></a><a name="p22954273245"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20.842084208420843%" headers="mcps1.2.4.1.2 "><p id="p1829512274243"><a name="p1829512274243"></a><a name="p1829512274243"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="67.38673867386738%" headers="mcps1.2.4.1.3 "><p id="p1729516278248"><a name="p1729516278248"></a><a name="p1729516278248"></a>Pod实例所在的网络名称</p>
</td>
</tr>
<tr id="row176242402611"><td class="cellrowborder" valign="top" width="11.77117711771177%" headers="mcps1.2.4.1.1 "><p id="p1163112419267"><a name="p1163112419267"></a><a name="p1163112419267"></a>ips</p>
</td>
<td class="cellrowborder" valign="top" width="20.842084208420843%" headers="mcps1.2.4.1.2 "><p id="p20631924132612"><a name="p20631924132612"></a><a name="p20631924132612"></a>Array</p>
</td>
<td class="cellrowborder" valign="top" width="67.38673867386738%" headers="mcps1.2.4.1.3 "><p id="p11631224192619"><a name="p11631224192619"></a><a name="p11631224192619"></a>Pod实例的内网地址</p>
</td>
</tr>
<tr id="row16790172618265"><td class="cellrowborder" valign="top" width="11.77117711771177%" headers="mcps1.2.4.1.1 "><p id="p779062619262"><a name="p779062619262"></a><a name="p779062619262"></a>mac</p>
</td>
<td class="cellrowborder" valign="top" width="20.842084208420843%" headers="mcps1.2.4.1.2 "><p id="p1779012269263"><a name="p1779012269263"></a><a name="p1779012269263"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="67.38673867386738%" headers="mcps1.2.4.1.3 "><p id="p11790122642617"><a name="p11790122642617"></a><a name="p11790122642617"></a>ENI网卡的Mac地址</p>
</td>
</tr>
<tr id="row45473312267"><td class="cellrowborder" valign="top" width="11.77117711771177%" headers="mcps1.2.4.1.1 "><p id="p654710317267"><a name="p654710317267"></a><a name="p654710317267"></a>publicip</p>
</td>
<td class="cellrowborder" valign="top" width="20.842084208420843%" headers="mcps1.2.4.1.2 "><p id="p75475315267"><a name="p75475315267"></a><a name="p75475315267"></a><a href="#table1041701517289">publicip</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="67.38673867386738%" headers="mcps1.2.4.1.3 "><p id="p5547131102616"><a name="p5547131102616"></a><a name="p5547131102616"></a>Pod实例关联的弹性公网IP相关属性。详情请参考<a href="#table1041701517289">表2 publicip字段数据结构说明</a></p>
</td>
</tr>
</tbody>
</table>

**表 6**  publicip字段数据结构说明

<a name="table1041701517289"></a>
<table><thead align="left"><tr id="row5417515132816"><th class="cellrowborder" valign="top" width="11.941194119411943%" id="mcps1.2.4.1.1"><p id="p9464144814288"><a name="p9464144814288"></a><a name="p9464144814288"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.842084208420843%" id="mcps1.2.4.1.2"><p id="p184641648182814"><a name="p184641648182814"></a><a name="p184641648182814"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="67.21672167216722%" id="mcps1.2.4.1.3"><p id="p8464154862812"><a name="p8464154862812"></a><a name="p8464154862812"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row441781562810"><td class="cellrowborder" valign="top" width="11.941194119411943%" headers="mcps1.2.4.1.1 "><p id="p44176158282"><a name="p44176158282"></a><a name="p44176158282"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20.842084208420843%" headers="mcps1.2.4.1.2 "><p id="p18417121522815"><a name="p18417121522815"></a><a name="p18417121522815"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="67.21672167216722%" headers="mcps1.2.4.1.3 "><p id="p14417151518284"><a name="p14417151518284"></a><a name="p14417151518284"></a>EIP的id</p>
</td>
</tr>
<tr id="row11879812202912"><td class="cellrowborder" valign="top" width="11.941194119411943%" headers="mcps1.2.4.1.1 "><p id="p16880712102916"><a name="p16880712102916"></a><a name="p16880712102916"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20.842084208420843%" headers="mcps1.2.4.1.2 "><p id="p1188071218294"><a name="p1188071218294"></a><a name="p1188071218294"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="67.21672167216722%" headers="mcps1.2.4.1.3 "><p id="p1588019121293"><a name="p1588019121293"></a><a name="p1588019121293"></a>EIP当前的状态，详情请参考<a href="https://support.huaweicloud.com/api-eip/eip_api_0002.html" target="_blank" rel="noopener noreferrer">查看弹性公网IP</a>的<strong id="b10516121693615"><a name="b10516121693615"></a><a name="b10516121693615"></a>表3</strong>中<em id="i062301943615"><a name="i062301943615"></a><a name="i062301943615"></a><strong id="b192102190361"><a name="b192102190361"></a><a name="b192102190361"></a>status</strong></em>字段</p>
</td>
</tr>
<tr id="row553218176291"><td class="cellrowborder" valign="top" width="11.941194119411943%" headers="mcps1.2.4.1.1 "><p id="p13532181712915"><a name="p13532181712915"></a><a name="p13532181712915"></a>ipv4</p>
</td>
<td class="cellrowborder" valign="top" width="20.842084208420843%" headers="mcps1.2.4.1.2 "><p id="p19532917132912"><a name="p19532917132912"></a><a name="p19532917132912"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="67.21672167216722%" headers="mcps1.2.4.1.3 "><p id="p19532151719298"><a name="p19532151719298"></a><a name="p19532151719298"></a>EIP的IPV4地址</p>
</td>
</tr>
<tr id="row127621419122917"><td class="cellrowborder" valign="top" width="11.941194119411943%" headers="mcps1.2.4.1.1 "><p id="p576291912292"><a name="p576291912292"></a><a name="p576291912292"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20.842084208420843%" headers="mcps1.2.4.1.2 "><p id="p137621819202919"><a name="p137621819202919"></a><a name="p137621819202919"></a><a href="#table2681265326">PublicIPSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="67.21672167216722%" headers="mcps1.2.4.1.3 "><p id="p1876221911294"><a name="p1876221911294"></a><a name="p1876221911294"></a>EIP的详情。详情请参考<a href="#table2681265326">表3 spec字段数据结构说明</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 7**  spec字段数据结构说明

<a name="table2681265326"></a>
<table><thead align="left"><tr id="row196811168328"><th class="cellrowborder" valign="top" width="12.030000000000001%" id="mcps1.2.4.1.1"><p id="p588921815332"><a name="p588921815332"></a><a name="p588921815332"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.75%" id="mcps1.2.4.1.2"><p id="p888991815336"><a name="p888991815336"></a><a name="p888991815336"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="67.22%" id="mcps1.2.4.1.3"><p id="p17889518143312"><a name="p17889518143312"></a><a name="p17889518143312"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row206811169328"><td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.4.1.1 "><p id="p568111614324"><a name="p568111614324"></a><a name="p568111614324"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.4.1.2 "><p id="p06813611324"><a name="p06813611324"></a><a name="p06813611324"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="67.22%" headers="mcps1.2.4.1.3 "><p id="p18614734111510"><a name="p18614734111510"></a><a name="p18614734111510"></a>EIP类型，可选值：</p>
<a name="ul113476222328"></a><a name="ul113476222328"></a><ul id="ul113476222328"><li>5_telcom：电信</li><li>5_union：联通</li><li>5_bgp：全动态BGP</li><li>5_sbgp：静态BGP<p id="p18347183515408"><a name="p18347183515408"></a><a name="p18347183515408"></a><strong id="b847417410448"><a name="b847417410448"></a><a name="b847417410448"></a>注意</strong>：不同region支持的EIP类型有所差异，具体请参考：<a href="https://support.huaweicloud.com/api-eip/eip_api_0002.html" target="_blank" rel="noopener noreferrer">查询弹性公网IP</a>中<strong id="b15933149432"><a name="b15933149432"></a><a name="b15933149432"></a>表3</strong>中<strong id="b1337173924315"><a name="b1337173924315"></a><a name="b1337173924315"></a><em id="i203841154410"><a name="i203841154410"></a><a name="i203841154410"></a>type</em></strong>字段说明</p>
</li></ul>
</td>
</tr>
<tr id="row5546937123616"><td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.4.1.1 "><p id="p5546837103617"><a name="p5546837103617"></a><a name="p5546837103617"></a>ipVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.4.1.2 "><p id="p1054703763619"><a name="p1054703763619"></a><a name="p1054703763619"></a>Int32</p>
</td>
<td class="cellrowborder" valign="top" width="67.22%" headers="mcps1.2.4.1.3 "><p id="p66140346152"><a name="p66140346152"></a><a name="p66140346152"></a>IP版本，可选值：</p>
<a name="ul51351538361"></a><a name="ul51351538361"></a><ul id="ul51351538361"><li>4：IPV4</li><li>6：IPV6（暂未开放）</li></ul>
</td>
</tr>
<tr id="row1956631123818"><td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.4.1.1 "><p id="p247719300227"><a name="p247719300227"></a><a name="p247719300227"></a>bandwidth</p>
</td>
<td class="cellrowborder" valign="top" width="20.75%" headers="mcps1.2.4.1.2 "><p id="p64771030172217"><a name="p64771030172217"></a><a name="p64771030172217"></a><a href="zh-cn_topic_0238845544.md#table626381192419">bandwidth</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="67.22%" headers="mcps1.2.4.1.3 "><p id="p1747715309220"><a name="p1747715309220"></a><a name="p1747715309220"></a>带宽配置，详情请参考<a href="zh-cn_topic_0238845544.md#table626381192419">表7</a></p>
</td>
</tr>
</tbody>
</table>

响应示例

```
{
    "apiVersion":"v1",
    "kind":"Pod",
    "metadata":{
        "annotations":{
            "k8s.v1.cni.cncf.io/network-status":"[{"name":"default-network","ips":["192.168.81.57",""],"mac":"fa:16:3e:b0:d7:44"}]",
            "k8s.v1.cni.cncf.io/networks":"[{"name":"default-network","pniPool":"fixpool"}]"
        },
        "creationTimestamp":"2020-04-23T07:34:07Z",
        "generateName":"test-59bbdbb86d-",
        "labels":{
            "app":"test"
        },
        "name":"test-59bbdbb86d-dhrcp",
        "namespace":"default",
        "ownerReferences":[
            {
                "apiVersion":"apps/v1",
                "blockOwnerDeletion":true,
                "controller":true,
                "kind":"ReplicaSet",
                "name":"test-59bbdbb86d",
                "uid":"724f9c56-480b-4e9d-ad02-4c689f36ab82"
            }
        ],
        "resourceVersion":"1096408",
        "selfLink":"/api/v1/namespaces/default/pods/test-59bbdbb86d-dhrcp",
        "uid":"15fef2bf-c8f5-4e1c-8b53-0855f659c619"
    },
    "spec":{
        "containers":[
            {
                "image":"100.125.4.7:20202/cce/nginx",
                "imagePullPolicy":"IfNotPresent",
                "name":"test",
                "terminationMessagePath":"/dev/termination-log",
                "terminationMessagePolicy":"File"
            }
        ],
        "dnsConfig":{
            "options":[
                {
                    "name":"single-request-reopen",
                    "value":""
                },
                {
                    "name":"timeout",
                    "value":"2"
                }
            ]
        },
        "dnsPolicy":"ClusterFirst",
        "enableServiceLinks":true,
        "imagePullSecrets":[
            {
                "name":"default-secret"
            }
        ],
        "nodeName":"192.168.0.9",
        "priority":0,
        "restartPolicy":"Always",
        "schedulerName":"default-scheduler",
        "securityContext":{

        },
        "serviceAccount":"default",
        "serviceAccountName":"default",
        "terminationGracePeriodSeconds":30,
        "tolerations":[
            {
                "effect":"NoExecute",
                "key":"node.kubernetes.io/not-ready",
                "operator":"Exists",
                "tolerationSeconds":300
            },
            {
                "effect":"NoExecute",
                "key":"node.kubernetes.io/unreachable",
                "operator":"Exists",
                "tolerationSeconds":300
            }
        ]
    },
    "status":{
        "conditions":[
            {
                "lastProbeTime":null,
                "lastTransitionTime":"2020-04-23T07:48:01Z",
                "status":"True",
                "type":"Initialized"
            },
            {
                "lastProbeTime":null,
                "lastTransitionTime":"2020-04-23T07:48:23Z",
                "status":"True",
                "type":"Ready"
            },
            {
                "lastProbeTime":null,
                "lastTransitionTime":"2020-04-23T07:48:23Z",
                "status":"True",
                "type":"ContainersReady"
            },
            {
                "lastProbeTime":null,
                "lastTransitionTime":"2020-04-23T07:48:01Z",
                "status":"True",
                "type":"PodScheduled"
            }
        ],
        "containerStatuses":[
            {
                "containerID":"docker://b5cf9a92d5004dbc9143947ab48294e67332135b5fbccbaab639d6f7e18dc953",
                "image":"100.125.4.7:20202/cce-test/nginx:latest",
                "imageID":"docker-pullable://100.125.4.7:20202/cce/nginx@sha256:18c8411a66ef352ba7fc857d924c8c9357dbd37551760fd6deba40ee68c9e62a",
                "lastState":{

                },
                "name":"test",
                "ready":true,
                "restartCount":0,
                "state":{
                    "running":{
                        "startedAt":"2020-04-23T07:48:23Z"
                    }
                }
            }
        ],
        "hostIP":"192.168.0.9",
        "phase":"Running",
        "podIP":"192.168.81.57",
        "podIPs":[
            {
                "ip":"192.168.81.57"
            }
        ],
        "startTime":"2020-04-23T07:48:01Z"
    }
}
```

## 其他操作<a name="section2314125415245"></a>

您可以查看新添加网络平面的YAML，也可以对新添加的网络平面进行“删除“操作。

>![](public_sys-resources/icon-note.gif) **说明：** 
>如果网络平面已经被工作负载绑定且在使用中，则不能被删除。如需删除该网络平面，请先删除绑定的工作负载。

**图 6**  管理网络平面<a name="fig29028593411"></a>  
![](figures/管理网络平面.png "管理网络平面")

