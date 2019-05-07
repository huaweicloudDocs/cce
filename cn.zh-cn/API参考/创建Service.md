# 创建Service<a name="cce_02_0025"></a>

## 功能介绍<a name="s6b7bf0e53f9c495eb9b89e73dc6bae80"></a>

该API用于创建一个Service对象。

-   如果在创建Service资源对象和Deployment资源对象后，要在CCE界面，工作负载详情页面中，“访问方式“页签下显示对应的Service资源，则需要给创建的Service资源对象添加labels标签，并且设置对应的selector。

    设置请求消息体中的“metadata.labels“参数键值如下：

    ```
    labels:
        app: appname
    ```

    设置请求消息体中的“spec.selector“参数键值如下：

    ```
    selector:
        app: appname 
    ```

    其中：

    -   lables参数下“app“参数所键入的“appname“为显示在CCE工作负载界面上的工作负载名称，其值与Deployment的“metadata.labels“中所添加的内容一致。
    -   selector参数下“app“的值与需要关联的Deployment的“spec.selector“保持一致。


## URI<a name="s5d6abc7988cb426db0a9a10aa1e612b6"></a>

POST /api/v1/namespaces/\{namespace\}/services

[表1](#zh-cn_topic_0079615000_table64523107)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615000_table64523107"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row55516030"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615000_p504568"><a name="zh-cn_topic_0079615000_p504568"></a><a name="zh-cn_topic_0079615000_p504568"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p64287338205444"><a name="p64287338205444"></a><a name="p64287338205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p39891894205444"><a name="p39891894205444"></a><a name="p39891894205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row48602122"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615000_p44457847"><a name="zh-cn_topic_0079615000_p44457847"></a><a name="zh-cn_topic_0079615000_p44457847"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p44315844"><a name="zh-cn_topic_0079615000_p44315844"></a><a name="zh-cn_topic_0079615000_p44315844"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615000_p32813593"><a name="zh-cn_topic_0079615000_p32813593"></a><a name="zh-cn_topic_0079615000_p32813593"></a><span id="ph17235553135916"><a name="ph17235553135916"></a><a name="ph17235553135916"></a>设置为true后，会打印漂亮的输出结果。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row41865316"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615000_p35647420"><a name="zh-cn_topic_0079615000_p35647420"></a><a name="zh-cn_topic_0079615000_p35647420"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p1759884"><a name="zh-cn_topic_0079615000_p1759884"></a><a name="zh-cn_topic_0079615000_p1759884"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p166752264459"><a name="p166752264459"></a><a name="p166752264459"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。可以任选其一使用：</p>
<a name="ul75828215461"></a><a name="ul75828215461"></a><ul id="ul75828215461"><li>用户自定义的namespace，使用前必须先<a href="创建Namespace.md">创建Namespace</a></li><li>系统自带的namespace：default或kube-system</li></ul>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079615000_ref458763557"></a>

**请求参数：**

请求参数如[表2](#zh-cn_topic_0079615000_ref458759328)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079615000_ref458759328"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row23442384"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615000_p19784972"><a name="zh-cn_topic_0079615000_p19784972"></a><a name="zh-cn_topic_0079615000_p19784972"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p62904453205444"><a name="p62904453205444"></a><a name="p62904453205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p62095922205444"><a name="p62095922205444"></a><a name="p62095922205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p63713767205444"><a name="p63713767205444"></a><a name="p63713767205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row18401162"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p14099157"><a name="zh-cn_topic_0079615000_p14099157"></a><a name="zh-cn_topic_0079615000_p14099157"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p1181044"><a name="zh-cn_topic_0079615000_p1181044"></a><a name="zh-cn_topic_0079615000_p1181044"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p28555728"><a name="zh-cn_topic_0079615000_p28555728"></a><a name="zh-cn_topic_0079615000_p28555728"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p31312592"><a name="zh-cn_topic_0079615000_p31312592"></a><a name="zh-cn_topic_0079615000_p31312592"></a><span id="ph1174310195614"><a name="ph1174310195614"></a><a name="ph1174310195614"></a>API类型，固定值</span><span id="ph67530461539"><a name="ph67530461539"></a><a name="ph67530461539"></a>＂Service＂</span><span id="ph168222575562"><a name="ph168222575562"></a><a name="ph168222575562"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row9865923"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p60942285"><a name="zh-cn_topic_0079615000_p60942285"></a><a name="zh-cn_topic_0079615000_p60942285"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p37378072"><a name="zh-cn_topic_0079615000_p37378072"></a><a name="zh-cn_topic_0079615000_p37378072"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p7725004"><a name="zh-cn_topic_0079615000_p7725004"></a><a name="zh-cn_topic_0079615000_p7725004"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p17590785"><a name="zh-cn_topic_0079614900_p17590785"></a><a name="zh-cn_topic_0079614900_p17590785"></a>API版本，固定值＂v1＂。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row14815471"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p59202483"><a name="zh-cn_topic_0079615000_p59202483"></a><a name="zh-cn_topic_0079615000_p59202483"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p30671812"><a name="zh-cn_topic_0079615000_p30671812"></a><a name="zh-cn_topic_0079615000_p30671812"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p1388809"><a name="zh-cn_topic_0079615000_p1388809"></a><a name="zh-cn_topic_0079615000_p1388809"></a><a href="#zh-cn_topic_0079615000_table43837055">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p5808961"><a name="zh-cn_topic_0079615000_p5808961"></a><a name="zh-cn_topic_0079615000_p5808961"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row52280657"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p6874787"><a name="zh-cn_topic_0079615000_p6874787"></a><a name="zh-cn_topic_0079615000_p6874787"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p19986890"><a name="zh-cn_topic_0079615000_p19986890"></a><a name="zh-cn_topic_0079615000_p19986890"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p8325422"><a name="zh-cn_topic_0079615000_p8325422"></a><a name="zh-cn_topic_0079615000_p8325422"></a><a href="#zh-cn_topic_0079615000_table58989182">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p29435243"><a name="zh-cn_topic_0079615000_p29435243"></a><a name="zh-cn_topic_0079615000_p29435243"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row63590603"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p50565204"><a name="zh-cn_topic_0079615000_p50565204"></a><a name="zh-cn_topic_0079615000_p50565204"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p2140858"><a name="zh-cn_topic_0079615000_p2140858"></a><a name="zh-cn_topic_0079615000_p2140858"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p39191780"><a name="zh-cn_topic_0079615000_p39191780"></a><a name="zh-cn_topic_0079615000_p39191780"></a><a href="#zh-cn_topic_0079615000_table61140591">表5</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p49540626"><a name="zh-cn_topic_0079615000_p49540626"></a><a name="zh-cn_topic_0079615000_p49540626"></a>-</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="zh-cn_topic_0079615000_table43837055"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row29476029"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615000_p38748148"><a name="zh-cn_topic_0079615000_p38748148"></a><a name="zh-cn_topic_0079615000_p38748148"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p19758610205444"><a name="p19758610205444"></a><a name="p19758610205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.67%" id="mcps1.2.5.1.3"><p id="p56943584205444"><a name="p56943584205444"></a><a name="p56943584205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.36%" id="mcps1.2.5.1.4"><p id="p49027631205444"><a name="p49027631205444"></a><a name="p49027631205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row51840373"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p38320646"><a name="zh-cn_topic_0079615000_p38320646"></a><a name="zh-cn_topic_0079615000_p38320646"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p16964616"><a name="zh-cn_topic_0079615000_p16964616"></a><a name="zh-cn_topic_0079615000_p16964616"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p31956642"><a name="zh-cn_topic_0079615000_p31956642"></a><a name="zh-cn_topic_0079615000_p31956642"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="p13937197564"><a name="p13937197564"></a><a name="p13937197564"></a>Service名称，可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长24个字符，同一namespace下name不能重复。</p>
<a name="ul72362268611"></a><a name="ul72362268611"></a><ul id="ul72362268611"><li>字符串必须满足正则表达式：[a-z0-9]([-a-z0-9]*[a-z0-9])?</li></ul>
</td>
</tr>
<tr id="r59e9b08f407d496eac092f809321b53f"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="aeefc6fe8fca8446685053b6d0902640e"><a name="aeefc6fe8fca8446685053b6d0902640e"></a><a name="aeefc6fe8fca8446685053b6d0902640e"></a>clusterName</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p541213427308"><a name="zh-cn_topic_0079615000_p541213427308"></a><a name="zh-cn_topic_0079615000_p541213427308"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p641274253010"><a name="zh-cn_topic_0079615000_p641274253010"></a><a name="zh-cn_topic_0079615000_p641274253010"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="p186894445710"><a name="p186894445710"></a><a name="p186894445710"></a>对象所属的群集的名称。用于区分不同集群中具有相同名称和命名空间的资源。这个字段现在不在任何地方设置，如果在Create或Update请求中设置，apiserver将忽略它。</p>
</td>
</tr>
<tr id="r08d3f4618a3d463fb26929343fc28aa7"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a5a6084a987a14186b0d019c3a9f73036"><a name="a5a6084a987a14186b0d019c3a9f73036"></a><a name="a5a6084a987a14186b0d019c3a9f73036"></a>initializers</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p561852113110"><a name="zh-cn_topic_0079615000_p561852113110"></a><a name="zh-cn_topic_0079615000_p561852113110"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="a50f457b14c8a4bcbb8c8d6560a2724ff"><a name="a50f457b14c8a4bcbb8c8d6560a2724ff"></a><a name="a50f457b14c8a4bcbb8c8d6560a2724ff"></a><a href="公共请求参数.md#t693768b66dfa47239c0f155ad4dd18e8">表13</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p161812183116"><a name="zh-cn_topic_0079615000_p161812183116"></a><a name="zh-cn_topic_0079615000_p161812183116"></a><span id="ph164173313143"><a name="ph164173313143"></a><a name="ph164173313143"></a>Initializers是一个准入控制器，可以用来方便地扩展准入控制</span><span id="ph8942182207"><a name="ph8942182207"></a><a name="ph8942182207"></a>。</span><span id="ph114009203203"><a name="ph114009203203"></a><a name="ph114009203203"></a>如果该参数为零或空，则表示该对象已完全初始化，</span><span id="ph8348121118213"><a name="ph8348121118213"></a><a name="ph8348121118213"></a>只有特权用户可以设置或修改此列表。一旦它被设置为空，则不能被任何用户进一步修改。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row40758985"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p13143484"><a name="zh-cn_topic_0079615000_p13143484"></a><a name="zh-cn_topic_0079615000_p13143484"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p57989292"><a name="zh-cn_topic_0079615000_p57989292"></a><a name="zh-cn_topic_0079615000_p57989292"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p66621056"><a name="zh-cn_topic_0079615000_p66621056"></a><a name="zh-cn_topic_0079615000_p66621056"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p52261031"><a name="zh-cn_topic_0079615000_p52261031"></a><a name="zh-cn_topic_0079615000_p52261031"></a><span id="ph106714519341"><a name="ph106714519341"></a><a name="ph106714519341"></a>GenerateName</span><span id="ph16754593420"><a name="ph16754593420"></a><a name="ph16754593420"></a> is an optional prefix</span><span id="ph4670458344"><a name="ph4670458344"></a><a name="ph4670458344"></a> 是一个可选项，表示名字的前缀，当Name字段为空时，会自动使用该前缀生成一个集群内唯一存在的Name。</span><span id="ph067134543416"><a name="ph067134543416"></a><a name="ph067134543416"></a>只有当Name字段为空时才需要配置generateName，generateName</span><span id="ph13671145143415"><a name="ph13671145143415"></a><a name="ph13671145143415"></a>可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长24个字符</span><span id="ph867104573413"><a name="ph867104573413"></a><a name="ph867104573413"></a>。</span></p>
<a name="ul28516562248"></a><a name="ul28516562248"></a><ul id="ul28516562248"><li>字符串必须满足正则表达式： [a-z0-9]([-a-z0-9]*[a-z0-9])?</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row5285158"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p25444686"><a name="zh-cn_topic_0079615000_p25444686"></a><a name="zh-cn_topic_0079615000_p25444686"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p47753670"><a name="zh-cn_topic_0079615000_p47753670"></a><a name="zh-cn_topic_0079615000_p47753670"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p42842038"><a name="zh-cn_topic_0079615000_p42842038"></a><a name="zh-cn_topic_0079615000_p42842038"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p26224387"><a name="zh-cn_topic_0079615000_p26224387"></a><a name="zh-cn_topic_0079615000_p26224387"></a><span id="ph2076915358349"><a name="ph2076915358349"></a><a name="ph2076915358349"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。字符串必须满足正则表达式</span><span> [a-z0-9]([-a-z0-9]</span><span>*[a-z0-9])?</span><span id="ph8769173513340"><a name="ph8769173513340"></a><a name="ph8769173513340"></a>。可以任选其一使用：</span></p>
<a name="ul2786250175914"></a><a name="ul2786250175914"></a><ul id="ul2786250175914"><li>用户自定义的namespace，使用前必须先<a href="创建Namespace.md">创建Namespace</a></li><li>系统自带的namespace：default或kube-system</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row43800616"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p58188993"><a name="zh-cn_topic_0079615000_p58188993"></a><a name="zh-cn_topic_0079615000_p58188993"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p15687991"><a name="zh-cn_topic_0079615000_p15687991"></a><a name="zh-cn_topic_0079615000_p15687991"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p62767729"><a name="zh-cn_topic_0079615000_p62767729"></a><a name="zh-cn_topic_0079615000_p62767729"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p51021271"><a name="zh-cn_topic_0079615000_p51021271"></a><a name="zh-cn_topic_0079615000_p51021271"></a><span id="ph1878720433220"><a name="ph1878720433220"></a><a name="ph1878720433220"></a>SelfLink </span><span id="ph2354174512018"><a name="ph2354174512018"></a><a name="ph2354174512018"></a>是该资源对象的</span><span id="ph10788124103213"><a name="ph10788124103213"></a><a name="ph10788124103213"></a>URL</span><span id="ph736813855616"><a name="ph736813855616"></a><a name="ph736813855616"></a>。</span><span id="ph51072115113"><a name="ph51072115113"></a><a name="ph51072115113"></a>系统内部使用，只读项</span><span id="ph3332102416321"><a name="ph3332102416321"></a><a name="ph3332102416321"></a>。</span></p>
<div class="note" id="zh-cn_topic_0079615000_note56538263"><a name="zh-cn_topic_0079615000_note56538263"></a><a name="zh-cn_topic_0079615000_note56538263"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0079614900_p31368204"><a name="zh-cn_topic_0079614900_p31368204"></a><a name="zh-cn_topic_0079614900_p31368204"></a>该参数是系统自动生成的，不能手动配置，否则会导致接口调用失败。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row16196587"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p36855200"><a name="zh-cn_topic_0079615000_p36855200"></a><a name="zh-cn_topic_0079615000_p36855200"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p32481246"><a name="zh-cn_topic_0079615000_p32481246"></a><a name="zh-cn_topic_0079615000_p32481246"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p13735244"><a name="zh-cn_topic_0079615000_p13735244"></a><a name="zh-cn_topic_0079615000_p13735244"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p38812946"><a name="zh-cn_topic_0079615000_p38812946"></a><a name="zh-cn_topic_0079615000_p38812946"></a><span id="ph99203463328"><a name="ph99203463328"></a><a name="ph99203463328"></a>UID</span><span id="ph1095010917420"><a name="ph1095010917420"></a><a name="ph1095010917420"></a>是赋值给该资源对象全局唯一的ID</span><span id="ph1749880154"><a name="ph1749880154"></a><a name="ph1749880154"></a>。系统自动生成以及提供系统内部使用，只读项。</span></p>
<div class="note" id="zh-cn_topic_0079615000_note13772198"><a name="zh-cn_topic_0079615000_note13772198"></a><a name="zh-cn_topic_0079615000_note13772198"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079615000_p56840921"><a name="zh-cn_topic_0079615000_p56840921"></a><a name="zh-cn_topic_0079615000_p56840921"></a><span id="ph329517182331"><a name="ph329517182331"></a><a name="ph329517182331"></a>该参数是系统自动生成的，不能手动配置，否则会导致接口调用失败。</span></p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row41806244"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p30862607"><a name="zh-cn_topic_0079615000_p30862607"></a><a name="zh-cn_topic_0079615000_p30862607"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p16843214"><a name="zh-cn_topic_0079615000_p16843214"></a><a name="zh-cn_topic_0079615000_p16843214"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p22123082"><a name="zh-cn_topic_0079615000_p22123082"></a><a name="zh-cn_topic_0079615000_p22123082"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p47139178"><a name="zh-cn_topic_0079615000_p47139178"></a><a name="zh-cn_topic_0079615000_p47139178"></a><span id="ph516213221259"><a name="ph516213221259"></a><a name="ph516213221259"></a>ResourceVersion表示该资源对象内部版本</span><span id="ph188361713112614"><a name="ph188361713112614"></a><a name="ph188361713112614"></a>，可以用来优化并发性能和监视资源变化，</span><span id="ph173071947202820"><a name="ph173071947202820"></a><a name="ph173071947202820"></a>系统内部使用，只读项</span><span id="ph577585316285"><a name="ph577585316285"></a><a name="ph577585316285"></a>。</span></p>
<div class="note" id="zh-cn_topic_0079615000_note21599419"><a name="zh-cn_topic_0079615000_note21599419"></a><a name="zh-cn_topic_0079615000_note21599419"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p84114143351"><a name="p84114143351"></a><a name="p84114143351"></a>该参数是系统自动生成的，不能手动配置，否则会导致接口调用失败。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row4722509"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p46978935"><a name="zh-cn_topic_0079615000_p46978935"></a><a name="zh-cn_topic_0079615000_p46978935"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p47197410"><a name="zh-cn_topic_0079615000_p47197410"></a><a name="zh-cn_topic_0079615000_p47197410"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p64893878"><a name="zh-cn_topic_0079615000_p64893878"></a><a name="zh-cn_topic_0079615000_p64893878"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p19792958"><a name="zh-cn_topic_0079614900_p19792958"></a><a name="zh-cn_topic_0079614900_p19792958"></a>Generation是根据资源对象预期状态生成的一串序列，由replication controllers生成， 系统内部使用，只读项。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row62996841"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p2470505"><a name="zh-cn_topic_0079615000_p2470505"></a><a name="zh-cn_topic_0079615000_p2470505"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p65893197"><a name="zh-cn_topic_0079615000_p65893197"></a><a name="zh-cn_topic_0079615000_p65893197"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p35748734"><a name="zh-cn_topic_0079615000_p35748734"></a><a name="zh-cn_topic_0079615000_p35748734"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p9966307"><a name="zh-cn_topic_0079615000_p9966307"></a><a name="zh-cn_topic_0079615000_p9966307"></a><span id="ph18301048361"><a name="ph18301048361"></a><a name="ph18301048361"></a>CreationTimestamp</span><span id="ph118191040123920"><a name="ph118191040123920"></a><a name="ph118191040123920"></a>是该资源对象创建的时间戳，UTC时间，使用RFC3339格式。</span></p>
<div class="note" id="zh-cn_topic_0079615000_note22587900"><a name="zh-cn_topic_0079615000_note22587900"></a><a name="zh-cn_topic_0079615000_note22587900"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0079614900_p37815307"><a name="zh-cn_topic_0079614900_p37815307"></a><a name="zh-cn_topic_0079614900_p37815307"></a>该参数是系统自动生成的，不能手动配置，否则会导致接口调用失败。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row17680651"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p22846659"><a name="zh-cn_topic_0079615000_p22846659"></a><a name="zh-cn_topic_0079615000_p22846659"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p38640075"><a name="zh-cn_topic_0079615000_p38640075"></a><a name="zh-cn_topic_0079615000_p38640075"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p42838347"><a name="zh-cn_topic_0079615000_p42838347"></a><a name="zh-cn_topic_0079615000_p42838347"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614927_p19988199"><a name="zh-cn_topic_0079614927_p19988199"></a><a name="zh-cn_topic_0079614927_p19988199"></a>DeletionTimestamp是该资源对象即将被删除的时间戳，使用RFC3339格式。 只有当客户端请求优雅删除资源对象的时候，该参数才会被系统赋值，客户端无法直接设置该参数，资源对象会在该时间之后被删除（list无法看到以及通过名字无法查询到），该参数值设置后无法修改，只读项。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row23533648"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p27177349"><a name="zh-cn_topic_0079615000_p27177349"></a><a name="zh-cn_topic_0079615000_p27177349"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p53881646"><a name="zh-cn_topic_0079615000_p53881646"></a><a name="zh-cn_topic_0079615000_p53881646"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p2337204"><a name="zh-cn_topic_0079615000_p2337204"></a><a name="zh-cn_topic_0079615000_p2337204"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p63073541"><a name="zh-cn_topic_0079614900_p63073541"></a><a name="zh-cn_topic_0079614900_p63073541"></a>设置允许资源对象被优雅删除的最长时间，该参数会和deletionTimestamp一起被设置，只读项。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row26100208"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p33742108"><a name="zh-cn_topic_0079615000_p33742108"></a><a name="zh-cn_topic_0079615000_p33742108"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p48756224"><a name="zh-cn_topic_0079615000_p48756224"></a><a name="zh-cn_topic_0079615000_p48756224"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p56940101"><a name="zh-cn_topic_0079615000_p56940101"></a><a name="zh-cn_topic_0079615000_p56940101"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="p1891734165913"><a name="p1891734165913"></a><a name="p1891734165913"></a>Service标签，key/value对格式。</p>
<a name="ul1736685012"></a><a name="ul1736685012"></a><ul id="ul1736685012"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</li><li>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li></ul>
<p id="p156295249512"><a name="p156295249512"></a><a name="p156295249512"></a>示例：</p>
<a name="ul184411422183314"></a><a name="ul184411422183314"></a><ul id="ul184411422183314"><li>"foo": "bar"</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row36056236"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p34874009"><a name="zh-cn_topic_0079615000_p34874009"></a><a name="zh-cn_topic_0079615000_p34874009"></a>Annotations</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p6222499"><a name="zh-cn_topic_0079615000_p6222499"></a><a name="zh-cn_topic_0079615000_p6222499"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p34260401"><a name="zh-cn_topic_0079615000_p34260401"></a><a name="zh-cn_topic_0079615000_p34260401"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p23629100"><a name="zh-cn_topic_0079615000_p23629100"></a><a name="zh-cn_topic_0079615000_p23629100"></a><span id="ph1116519213128"><a name="ph1116519213128"></a><a name="ph1116519213128"></a>Annotations</span><span id="ph18651246698"><a name="ph18651246698"></a><a name="ph18651246698"></a>是非结构化的键值对，通常用来保存任意外部定义的元数据。</span></p>
</td>
</tr>
<tr id="r7a1239227d8c4999a488e54b7405613f"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a4ac11975cfca47d4a172ea9b2c1bbd8c"><a name="a4ac11975cfca47d4a172ea9b2c1bbd8c"></a><a name="a4ac11975cfca47d4a172ea9b2c1bbd8c"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p405649418162"><a name="zh-cn_topic_0079615000_p405649418162"></a><a name="zh-cn_topic_0079615000_p405649418162"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p439439618162"><a name="zh-cn_topic_0079615000_p439439618162"></a><a name="zh-cn_topic_0079615000_p439439618162"></a><a href="#tf1f749652c974a92b9e9cf83deb8d111">表6</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="a9587edde5d2447baad8fc20f25e98936"><a name="a9587edde5d2447baad8fc20f25e98936"></a><a name="a9587edde5d2447baad8fc20f25e98936"></a><span id="ph1694511301564"><a name="ph1694511301564"></a><a name="ph1694511301564"></a>OwnerReferences是所有依赖当前资源对象的其他资源对象列表，如果列表里资源都已经被删除，则当前资源会被垃圾回收。如果当前资源被controller管理，则列表中有一项指向该controller，该项中controller字段被设置为true，controller不会超过一个。</span></p>
</td>
</tr>
<tr id="r375d22b85d2e49f8a4c776f12c7be3c6"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="ad7058987bd734754a40cb402767e2b63"><a name="ad7058987bd734754a40cb402767e2b63"></a><a name="ad7058987bd734754a40cb402767e2b63"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a6f58b1f64d024488b85c0b04bc817661"><a name="a6f58b1f64d024488b85c0b04bc817661"></a><a name="a6f58b1f64d024488b85c0b04bc817661"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.67%" headers="mcps1.2.5.1.3 "><p id="a3d920784b3614106b4a92de589781fbc"><a name="a3d920784b3614106b4a92de589781fbc"></a><a name="a3d920784b3614106b4a92de589781fbc"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="39.36%" headers="mcps1.2.5.1.4 "><p id="a69e1b2402dce4f358aeab4184e6cf280"><a name="a69e1b2402dce4f358aeab4184e6cf280"></a><a name="a69e1b2402dce4f358aeab4184e6cf280"></a>在从注册表中删除对象之前，该参数必须为空。</p>
</td>
</tr>
</tbody>
</table>

**表 4**  spec字段数据结构说明

<a name="zh-cn_topic_0079615000_table58989182"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row48974116"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615000_p7480498"><a name="zh-cn_topic_0079615000_p7480498"></a><a name="zh-cn_topic_0079615000_p7480498"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p38367937205444"><a name="p38367937205444"></a><a name="p38367937205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p20795188205444"><a name="p20795188205444"></a><a name="p20795188205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p6688676205444"><a name="p6688676205444"></a><a name="p6688676205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row59285030"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p37358106"><a name="zh-cn_topic_0079615000_p37358106"></a><a name="zh-cn_topic_0079615000_p37358106"></a>ports</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p6107739"><a name="zh-cn_topic_0079615000_p6107739"></a><a name="zh-cn_topic_0079615000_p6107739"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p24964816"><a name="zh-cn_topic_0079615000_p24964816"></a><a name="zh-cn_topic_0079615000_p24964816"></a><a href="#zh-cn_topic_0079615000_table13394413">表7</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p12848880"><a name="zh-cn_topic_0079615000_p12848880"></a><a name="zh-cn_topic_0079615000_p12848880"></a><span id="ph1598712521573"><a name="ph1598712521573"></a><a name="ph1598712521573"></a>该服务暴露的端口号列表。</span></p>
</td>
</tr>
<tr id="r84d3b4cd4c354a7b8d2c2d8e643f2eb2"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a20c290dec91e461f9806ac7ddb64b32e"><a name="a20c290dec91e461f9806ac7ddb64b32e"></a><a name="a20c290dec91e461f9806ac7ddb64b32e"></a>selector</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a792005b9cc9c4b62aa05ca6ba72edb1b"><a name="a792005b9cc9c4b62aa05ca6ba72edb1b"></a><a name="a792005b9cc9c4b62aa05ca6ba72edb1b"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a9fd3a2cf6b17488ebf787d90dcdd4806"><a name="a9fd3a2cf6b17488ebf787d90dcdd4806"></a><a name="a9fd3a2cf6b17488ebf787d90dcdd4806"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="aaca6cae38740430c8d9c48adc947545c"><a name="aaca6cae38740430c8d9c48adc947545c"></a><a name="aaca6cae38740430c8d9c48adc947545c"></a><span id="ph1150142819016"><a name="ph1150142819016"></a><a name="ph1150142819016"></a>该服务会将流量转发到匹配该selector的后端Pod。后端Pod</span><span id="ph1125913186216"><a name="ph1125913186216"></a><a name="ph1125913186216"></a>标签的Key和Value值都必须相匹配才能接受到转发的流量</span><span id="ph242718138316"><a name="ph242718138316"></a><a name="ph242718138316"></a>。如果该参数为空，则所有的Pod都会被选择到，必须手动配置endpoints。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row48531064"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p38702074"><a name="zh-cn_topic_0079615000_p38702074"></a><a name="zh-cn_topic_0079615000_p38702074"></a>clusterIP</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p47860305"><a name="zh-cn_topic_0079615000_p47860305"></a><a name="zh-cn_topic_0079615000_p47860305"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p51479525"><a name="zh-cn_topic_0079615000_p51479525"></a><a name="zh-cn_topic_0079615000_p51479525"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p9091997"><a name="zh-cn_topic_0079615000_p9091997"></a><a name="zh-cn_topic_0079615000_p9091997"></a><span id="ph109864372817"><a name="ph109864372817"></a><a name="ph109864372817"></a>ClusterIP通常是由系统内部</span><span id="ph131342450915"><a name="ph131342450915"></a><a name="ph131342450915"></a>分配的，表示该服务的IP地址。可以把指定的IP分配给该服务，指定IP时必须保证该IP未被使用，否则会创建服务失败。该参数可以是：</span></p>
<a name="ul3900911171219"></a><a name="ul3900911171219"></a><ul id="ul3900911171219"><li>None</li><li>空字符串（""）</li><li>有效的IP地址</li></ul>
<p id="zh-cn_topic_0079615000_p14719114"><a name="zh-cn_topic_0079615000_p14719114"></a><a name="zh-cn_topic_0079615000_p14719114"></a><span id="ph1157184971312"><a name="ph1157184971312"></a><a name="ph1157184971312"></a>当不需要代理时，可以配置该参数为None，此时会将该Service的域名直接解析为Pod</span><span id="ph176152014171515"><a name="ph176152014171515"></a><a name="ph176152014171515"></a>的IP地址</span><span id="ph196741226131518"><a name="ph196741226131518"></a><a name="ph196741226131518"></a>。</span></p>
<p id="p48521034131316"><a name="p48521034131316"></a><a name="p48521034131316"></a></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row51397620"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p2457719"><a name="zh-cn_topic_0079615000_p2457719"></a><a name="zh-cn_topic_0079615000_p2457719"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p64857530"><a name="zh-cn_topic_0079615000_p64857530"></a><a name="zh-cn_topic_0079615000_p64857530"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p18968549"><a name="zh-cn_topic_0079615000_p18968549"></a><a name="zh-cn_topic_0079615000_p18968549"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p60057505"><a name="zh-cn_topic_0079615000_p60057505"></a><a name="zh-cn_topic_0079615000_p60057505"></a><span id="ph11959747111715"><a name="ph11959747111715"></a><a name="ph11959747111715"></a>服务的类型，</span><span id="ph1332110596177"><a name="ph1332110596177"></a><a name="ph1332110596177"></a>必须是：</span></p>
<a name="ul14623172361812"></a><a name="ul14623172361812"></a><ul id="ul14623172361812"><li>ClusterIP</li><li>NodePort</li><li>LoadBalancer</li></ul>
<p id="p105861922191810"><a name="p105861922191810"></a><a name="p105861922191810"></a><span id="ph627113711814"><a name="ph627113711814"></a><a name="ph627113711814"></a>默认是ClusterIP。使用</span> <span class="parmname" id="p142747974e2045eea6c2862545e07ed2"><a name="p142747974e2045eea6c2862545e07ed2"></a><a name="p142747974e2045eea6c2862545e07ed2"></a>“LoadBalancer”</span><span id="ph246821515196"><a name="ph246821515196"></a><a name="ph246821515196"></a>时表示会使用弹性负载均衡器</span>(ELB) <span id="ph1311115719191"><a name="ph1311115719191"></a><a name="ph1311115719191"></a>。</span> <span id="ph181038136201"><a name="ph181038136201"></a><a name="ph181038136201"></a>详情见</span>&nbsp;<a href="集群中使用ELB的操作方法.md">集群中使用ELB的操作方法</a>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row45038152"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p24211670"><a name="zh-cn_topic_0079615000_p24211670"></a><a name="zh-cn_topic_0079615000_p24211670"></a>externalIPs</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p14988220"><a name="zh-cn_topic_0079615000_p14988220"></a><a name="zh-cn_topic_0079615000_p14988220"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p6086307"><a name="zh-cn_topic_0079615000_p6086307"></a><a name="zh-cn_topic_0079615000_p6086307"></a>Array[string]</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p23228850"><a name="zh-cn_topic_0079615000_p23228850"></a><a name="zh-cn_topic_0079615000_p23228850"></a><span id="ph18225151192412"><a name="ph18225151192412"></a><a name="ph18225151192412"></a>ExternalIPs是一个IP地址列表，表示集群中哪些node节点会接受到该服务的流量。这些IP地址不是由kubernetes来管理的，用户必须自己保证流量可以到达这些节点。常见的场景是使用外部负载均衡器，这些负载均衡器并不是kubernetes系统的一部分。该功能之前在deprecatedPublicIPs字段里配置，当使用externalIPs参数时，必须清空</span><span id="ph1145517571273"><a name="ph1145517571273"></a><a name="ph1145517571273"></a>deprecatedPublicIPs字段。</span></p>
</td>
</tr>
<tr id="r8c13c2686b9b4cd4b6524cd9424a33ea"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="aea7cc907862a434a926b2ae1ada48056"><a name="aea7cc907862a434a926b2ae1ada48056"></a><a name="aea7cc907862a434a926b2ae1ada48056"></a>externalTrafficPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p126206215368"><a name="zh-cn_topic_0079615000_p126206215368"></a><a name="zh-cn_topic_0079615000_p126206215368"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p962062143619"><a name="zh-cn_topic_0079615000_p962062143619"></a><a name="zh-cn_topic_0079615000_p962062143619"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p741324712357"><a name="p741324712357"></a><a name="p741324712357"></a>ExternalTrafficPolicy表示是服务会把流量转发到固定的本地节点还是转发到集群范围内任意的endpoints里。可以配置为：</p>
<a name="ul1765233610447"></a><a name="ul1765233610447"></a><ul id="ul1765233610447"><li>"Local" ：会记录客户端的源IP，每次流量转发到固定的后端，避免了流量切换，但是存在负载不均衡的风险</li><li>"Cluster" ：客户端访问时，会在集群范围内所有的endpoints选择一个然后把流量转发给它，存在客户端和后端反复切换，但是可以保证良好额负载均衡。</li></ul>
</td>
</tr>
<tr id="re7093443281c4ba2a8de2837ac34d456"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p133296474363"><a name="zh-cn_topic_0079615000_p133296474363"></a><a name="zh-cn_topic_0079615000_p133296474363"></a>healthCheckNodePort</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p193295472360"><a name="zh-cn_topic_0079615000_p193295472360"></a><a name="zh-cn_topic_0079615000_p193295472360"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a807a0eaa37ad462fbdc2b3051c8f720c"><a name="a807a0eaa37ad462fbdc2b3051c8f720c"></a><a name="a807a0eaa37ad462fbdc2b3051c8f720c"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p432919473363"><a name="zh-cn_topic_0079615000_p432919473363"></a><a name="zh-cn_topic_0079615000_p432919473363"></a>healthCheckNodePort specifies the healthcheck nodePort for the service. If not specified, HealthCheckNodePort is created by the service api backend with the allocated nodePort. Will use user-specified nodePort value if specified by the client. Only effects when Type is set to LoadBalancer and ExternalTrafficPolicy is set to Local.</p>
</td>
</tr>
<tr id="r4ad3f7ed3c7043f8b8e091f93a268a16"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p437123915289"><a name="zh-cn_topic_0079615000_p437123915289"></a><a name="zh-cn_topic_0079615000_p437123915289"></a>externalName</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p143718398286"><a name="zh-cn_topic_0079615000_p143718398286"></a><a name="zh-cn_topic_0079615000_p143718398286"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="aa3226079bd494142a3d3d909335b2841"><a name="aa3226079bd494142a3d3d909335b2841"></a><a name="aa3226079bd494142a3d3d909335b2841"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p737183952814"><a name="zh-cn_topic_0079615000_p737183952814"></a><a name="zh-cn_topic_0079615000_p737183952814"></a>externalName is the external reference that kubedns or equivalent will return as a CNAME record for this service. No proxying will be involved. Must be a valid DNS name and requires Type to be ExternalName.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row36510679"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p4575009"><a name="zh-cn_topic_0079615000_p4575009"></a><a name="zh-cn_topic_0079615000_p4575009"></a>sessionAffinity</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p35031468"><a name="zh-cn_topic_0079615000_p35031468"></a><a name="zh-cn_topic_0079615000_p35031468"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p18976672"><a name="zh-cn_topic_0079615000_p18976672"></a><a name="zh-cn_topic_0079615000_p18976672"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p60715427"><a name="zh-cn_topic_0079615000_p60715427"></a><a name="zh-cn_topic_0079615000_p60715427"></a>Supports "ClientIP" and "None". Used to maintain session affinity. Enable client IP based session affinity. Must be ClientIP or None. Defaults to None.</p>
<p id="zh-cn_topic_0079615000_p9567939"><a name="zh-cn_topic_0079615000_p9567939"></a><a name="zh-cn_topic_0079615000_p9567939"></a>This parameter can be set to:</p>
<a name="zh-cn_topic_0079615000_ul19002592"></a><a name="zh-cn_topic_0079615000_ul19002592"></a><ul id="zh-cn_topic_0079615000_ul19002592"><li>ClientIP</li><li>None</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row28463847"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p23870264"><a name="zh-cn_topic_0079615000_p23870264"></a><a name="zh-cn_topic_0079615000_p23870264"></a>loadBalancerIP</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p54443197"><a name="zh-cn_topic_0079615000_p54443197"></a><a name="zh-cn_topic_0079615000_p54443197"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p47822814"><a name="zh-cn_topic_0079615000_p47822814"></a><a name="zh-cn_topic_0079615000_p47822814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p48442757"><a name="zh-cn_topic_0079615000_p48442757"></a><a name="zh-cn_topic_0079615000_p48442757"></a>Only applies to Service Type: LoadBalancer LoadBalancer will get created with the IP specified in this field. This feature depends on whether the underlying cloud-provider supports specifying the loadBalancerIP when a load balancer is created. This field will be ignored if the cloud-provider does not support the feature.</p>
</td>
</tr>
<tr id="rb5875adbae4c4c66b9ba73e00d3865d3"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a61557620bc4942e288a6c987f9eb8dc9"><a name="a61557620bc4942e288a6c987f9eb8dc9"></a><a name="a61557620bc4942e288a6c987f9eb8dc9"></a>loadBalancerSourceRanges</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a95d01ac792dc4005b05c69533f55e7e1"><a name="a95d01ac792dc4005b05c69533f55e7e1"></a><a name="a95d01ac792dc4005b05c69533f55e7e1"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p17499376531"><a name="zh-cn_topic_0079615000_p17499376531"></a><a name="zh-cn_topic_0079615000_p17499376531"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a3e7a11cd383a43748d80b4ce4148b882"><a name="a3e7a11cd383a43748d80b4ce4148b882"></a><a name="a3e7a11cd383a43748d80b4ce4148b882"></a>Optional: If specified and supported by the platform, this will restrict traffic through the cloud-provide.load-balancer will be restricted to the specified client IPs. This field will be ignored if the cloud-provider does not support the feature.".</p>
</td>
</tr>
<tr id="row92981025102611"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p2029882510268"><a name="p2029882510268"></a><a name="p2029882510268"></a>publishNotReadyAddresses</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p1729862582611"><a name="p1729862582611"></a><a name="p1729862582611"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p52986255267"><a name="p52986255267"></a><a name="p52986255267"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p6852115118407"><a name="p6852115118407"></a><a name="p6852115118407"></a>publishNotReadyAddresses, when set to true, indicates that DNS implementations must publish the notReadyAddresses of subsets for the Endpoints associated with the Service. The default value is false. The primary use case for setting this field is to use a StatefulSet's Headless Service to propagate SRV records for its Pods without respect to their readiness for purpose of peer discovery. This field will replace the service.alpha.kubernetes.io/tolerate-unready-endpoints when that annotation is deprecated and all clients have been converted to use this field.</p>
</td>
</tr>
<tr id="row10504132411418"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p1550452464112"><a name="p1550452464112"></a><a name="p1550452464112"></a>sessionAffinityConfig</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p2504182413416"><a name="p2504182413416"></a><a name="p2504182413416"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p871715105433"><a name="p871715105433"></a><a name="p871715105433"></a><a href="#table136388588444">表10</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p20504142414114"><a name="p20504142414114"></a><a name="p20504142414114"></a>sessionAffinityConfig contains the configurations of session affinity.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  status字段数据结构说明

<a name="zh-cn_topic_0079615000_table61140591"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row8673855"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615000_p31493640"><a name="zh-cn_topic_0079615000_p31493640"></a><a name="zh-cn_topic_0079615000_p31493640"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p56505630205444"><a name="p56505630205444"></a><a name="p56505630205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p13553298205444"><a name="p13553298205444"></a><a name="p13553298205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p24075347205444"><a name="p24075347205444"></a><a name="p24075347205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row50459994"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p60727681"><a name="zh-cn_topic_0079615000_p60727681"></a><a name="zh-cn_topic_0079615000_p60727681"></a>loadBalancer</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p19995149"><a name="zh-cn_topic_0079615000_p19995149"></a><a name="zh-cn_topic_0079615000_p19995149"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p8994406"><a name="zh-cn_topic_0079615000_p8994406"></a><a name="zh-cn_topic_0079615000_p8994406"></a><a href="#zh-cn_topic_0079615000_table53440856">表8</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p47362577"><a name="zh-cn_topic_0079615000_p47362577"></a><a name="zh-cn_topic_0079615000_p47362577"></a>-</p>
</td>
</tr>
</tbody>
</table>

**表 6**  ownerReferences字段数据结构说明

<a name="tf1f749652c974a92b9e9cf83deb8d111"></a>
<table><thead align="left"><tr id="rbf26af93c2ce4d98821988919da471e4"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="a2b045691122b4b67a57fc74d036139ec"><a name="a2b045691122b4b67a57fc74d036139ec"></a><a name="a2b045691122b4b67a57fc74d036139ec"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.36%" id="mcps1.2.5.1.2"><p id="p28240649205444"><a name="p28240649205444"></a><a name="p28240649205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p5791269205444"><a name="p5791269205444"></a><a name="p5791269205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.1%" id="mcps1.2.5.1.4"><p id="p66439612205444"><a name="p66439612205444"></a><a name="p66439612205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rc9c5b4e8234343a7beba17c1c42d0ff5"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="abb0b398fa4a74a6d8e2fdd88449f1efe"><a name="abb0b398fa4a74a6d8e2fdd88449f1efe"></a><a name="abb0b398fa4a74a6d8e2fdd88449f1efe"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.2 "><p id="a08f4e379cccd4a3ba0a3c975c92819cd"><a name="a08f4e379cccd4a3ba0a3c975c92819cd"></a><a name="a08f4e379cccd4a3ba0a3c975c92819cd"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="abbb6188c906f479ba43be7e06bb5a7ba"><a name="abbb6188c906f479ba43be7e06bb5a7ba"></a><a name="abbb6188c906f479ba43be7e06bb5a7ba"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.1%" headers="mcps1.2.5.1.4 "><p id="a8410b8acbc6943f087b97ddd900ab8be"><a name="a8410b8acbc6943f087b97ddd900ab8be"></a><a name="a8410b8acbc6943f087b97ddd900ab8be"></a>API version of the referent.</p>
</td>
</tr>
<tr id="rc1363239a52a4d3e9c766045b3f9c0b2"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p01219203340"><a name="zh-cn_topic_0079615000_p01219203340"></a><a name="zh-cn_topic_0079615000_p01219203340"></a>blockOwnerDeletion</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.2 "><p id="ab183d2c5b29240b08a0ef77fc4c4375c"><a name="ab183d2c5b29240b08a0ef77fc4c4375c"></a><a name="ab183d2c5b29240b08a0ef77fc4c4375c"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a30f7c5b04b0d48b09fb5910b73a25596"><a name="a30f7c5b04b0d48b09fb5910b73a25596"></a><a name="a30f7c5b04b0d48b09fb5910b73a25596"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.1%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p612112204349"><a name="zh-cn_topic_0079615000_p612112204349"></a><a name="zh-cn_topic_0079615000_p612112204349"></a>If true, AND if the owner has the "foregroundDeletion" finalizer, then the owner cannot be deleted from the key-value store until this reference is removed. Defaults to false. To set this field, a user needs "delete" permission of the owner, otherwise 422 (Unprocessable Entity) will be returned.</p>
</td>
</tr>
<tr id="rba9fd1885e3d4ad69d2db484b130898e"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a0c08c123c99f4e6da8b411dfcd83cfc8"><a name="a0c08c123c99f4e6da8b411dfcd83cfc8"></a><a name="a0c08c123c99f4e6da8b411dfcd83cfc8"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.2 "><p id="a1d03dcc9f06c451a9fcb637644f0ce15"><a name="a1d03dcc9f06c451a9fcb637644f0ce15"></a><a name="a1d03dcc9f06c451a9fcb637644f0ce15"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a768f7fb91797485a8767e9bf727dd218"><a name="a768f7fb91797485a8767e9bf727dd218"></a><a name="a768f7fb91797485a8767e9bf727dd218"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.1%" headers="mcps1.2.5.1.4 "><p id="aefdb2bae5ad9465dbae9e2dcd3b6377f"><a name="aefdb2bae5ad9465dbae9e2dcd3b6377f"></a><a name="aefdb2bae5ad9465dbae9e2dcd3b6377f"></a>Kind of the referent.</p>
</td>
</tr>
<tr id="rcfa9c5896fe940e5b8c33c6969082c39"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a2a72dba566124f979f7148426c123a19"><a name="a2a72dba566124f979f7148426c123a19"></a><a name="a2a72dba566124f979f7148426c123a19"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.2 "><p id="ad13d850b95114b88b90c3bf01766d557"><a name="ad13d850b95114b88b90c3bf01766d557"></a><a name="ad13d850b95114b88b90c3bf01766d557"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="ac0c8a58a319940c3a40f380b30c74bda"><a name="ac0c8a58a319940c3a40f380b30c74bda"></a><a name="ac0c8a58a319940c3a40f380b30c74bda"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.1%" headers="mcps1.2.5.1.4 "><p id="a1e7163884ca24f00aacb8ad9b954b5da"><a name="a1e7163884ca24f00aacb8ad9b954b5da"></a><a name="a1e7163884ca24f00aacb8ad9b954b5da"></a>Name of the referent.</p>
</td>
</tr>
<tr id="rc10862c6c3344ed1a2e4ddb7dd03ec84"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a4b331ec0b4bb4305bddfb3afe7877dcd"><a name="a4b331ec0b4bb4305bddfb3afe7877dcd"></a><a name="a4b331ec0b4bb4305bddfb3afe7877dcd"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p570124172656"><a name="zh-cn_topic_0079615000_p570124172656"></a><a name="zh-cn_topic_0079615000_p570124172656"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="ae319391e50304a7bb01bf201c96bd672"><a name="ae319391e50304a7bb01bf201c96bd672"></a><a name="ae319391e50304a7bb01bf201c96bd672"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.1%" headers="mcps1.2.5.1.4 "><p id="a9a3f07d66a1a47a58f899cfecb26edbc"><a name="a9a3f07d66a1a47a58f899cfecb26edbc"></a><a name="a9a3f07d66a1a47a58f899cfecb26edbc"></a>UID of the referent.</p>
</td>
</tr>
<tr id="r8aaeb3ee76c247779185338f179e27cb"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="affcb693deec94c3e9dface5cafbc1dbf"><a name="affcb693deec94c3e9dface5cafbc1dbf"></a><a name="affcb693deec94c3e9dface5cafbc1dbf"></a>controller</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.2 "><p id="aa308da7be326430abdaf2c6de2045de1"><a name="aa308da7be326430abdaf2c6de2045de1"></a><a name="aa308da7be326430abdaf2c6de2045de1"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a27f021c68c354003b75d2e72d0ca8cfe"><a name="a27f021c68c354003b75d2e72d0ca8cfe"></a><a name="a27f021c68c354003b75d2e72d0ca8cfe"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.1%" headers="mcps1.2.5.1.4 "><p id="a729987ad88364c5ba6341ad35f9ee7f4"><a name="a729987ad88364c5ba6341ad35f9ee7f4"></a><a name="a729987ad88364c5ba6341ad35f9ee7f4"></a>If true, this reference points to the managing controller.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  ports字段数据结构说明

<a name="zh-cn_topic_0079615000_table13394413"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row4541961"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615000_p32354522"><a name="zh-cn_topic_0079615000_p32354522"></a><a name="zh-cn_topic_0079615000_p32354522"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p28018243205444"><a name="p28018243205444"></a><a name="p28018243205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p54885214205444"><a name="p54885214205444"></a><a name="p54885214205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p16517325205444"><a name="p16517325205444"></a><a name="p16517325205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row9920661"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p65376040"><a name="zh-cn_topic_0079615000_p65376040"></a><a name="zh-cn_topic_0079615000_p65376040"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p60967925"><a name="zh-cn_topic_0079615000_p60967925"></a><a name="zh-cn_topic_0079615000_p60967925"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p39454882"><a name="zh-cn_topic_0079615000_p39454882"></a><a name="zh-cn_topic_0079615000_p39454882"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p41728855"><a name="zh-cn_topic_0079615000_p41728855"></a><a name="zh-cn_topic_0079615000_p41728855"></a>The name of this port within the service. This must be a DNS_LABEL. All ports within a ServiceSpec must have unique names. This maps to the 'Name' field in EndpointPort objects. Optional if only one ServicePort is defined on this service.</p>
<p id="zh-cn_topic_0079615000_p40015381"><a name="zh-cn_topic_0079615000_p40015381"></a><a name="zh-cn_topic_0079615000_p40015381"></a>Value length: 0 character &lt; String length ≤ 63 characters.</p>
<p id="zh-cn_topic_0079615000_p24594109"><a name="zh-cn_topic_0079615000_p24594109"></a><a name="zh-cn_topic_0079615000_p24594109"></a>The string must comply with regular expression [a-z0-9]([-a-z0-9]*[a-z0-9])?.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row20020394"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p11039195"><a name="zh-cn_topic_0079615000_p11039195"></a><a name="zh-cn_topic_0079615000_p11039195"></a>protocol</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p21759634"><a name="zh-cn_topic_0079615000_p21759634"></a><a name="zh-cn_topic_0079615000_p21759634"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p17699892"><a name="zh-cn_topic_0079615000_p17699892"></a><a name="zh-cn_topic_0079615000_p17699892"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p24405163"><a name="zh-cn_topic_0079615000_p24405163"></a><a name="zh-cn_topic_0079615000_p24405163"></a>The IP protocol for this port. Supports "TCP" and "UDP".</p>
<p id="zh-cn_topic_0079615000_p18319882"><a name="zh-cn_topic_0079615000_p18319882"></a><a name="zh-cn_topic_0079615000_p18319882"></a>This parameter can be set to:</p>
<a name="zh-cn_topic_0079615000_ul30661215"></a><a name="zh-cn_topic_0079615000_ul30661215"></a><ul id="zh-cn_topic_0079615000_ul30661215"><li>TCP</li><li>UDP</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row4774388"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p51181182"><a name="zh-cn_topic_0079615000_p51181182"></a><a name="zh-cn_topic_0079615000_p51181182"></a>port</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p52035105"><a name="zh-cn_topic_0079615000_p52035105"></a><a name="zh-cn_topic_0079615000_p52035105"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p54093956"><a name="zh-cn_topic_0079615000_p54093956"></a><a name="zh-cn_topic_0079615000_p54093956"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p19534287"><a name="zh-cn_topic_0079615000_p19534287"></a><a name="zh-cn_topic_0079615000_p19534287"></a>The port that will be exposed by this service.</p>
<p id="zh-cn_topic_0079615000_p41590859"><a name="zh-cn_topic_0079615000_p41590859"></a><a name="zh-cn_topic_0079615000_p41590859"></a>Value range: (0,65535].</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row38773419"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p53639231"><a name="zh-cn_topic_0079615000_p53639231"></a><a name="zh-cn_topic_0079615000_p53639231"></a>targetPort</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p49810484"><a name="zh-cn_topic_0079615000_p49810484"></a><a name="zh-cn_topic_0079615000_p49810484"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p8117426"><a name="zh-cn_topic_0079615000_p8117426"></a><a name="zh-cn_topic_0079615000_p8117426"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p53531744"><a name="zh-cn_topic_0079615000_p53531744"></a><a name="zh-cn_topic_0079615000_p53531744"></a>Number or name of the port to access on the pods targeted by the service. Number must be in the range 1 to 65535. Name must be an IANA_SVC_NAME. If this is a string, it will be looked up as a named port in the target Pod's container ports. If this is not specified, the value of Port is used (an identity map). Defaults to the service port.</p>
<p id="zh-cn_topic_0079615000_p12023648"><a name="zh-cn_topic_0079615000_p12023648"></a><a name="zh-cn_topic_0079615000_p12023648"></a>Value range: (0,65535].</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row41103974"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p41087597"><a name="zh-cn_topic_0079615000_p41087597"></a><a name="zh-cn_topic_0079615000_p41087597"></a>nodePort</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p39761052"><a name="zh-cn_topic_0079615000_p39761052"></a><a name="zh-cn_topic_0079615000_p39761052"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p66528668"><a name="zh-cn_topic_0079615000_p66528668"></a><a name="zh-cn_topic_0079615000_p66528668"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p20113045"><a name="zh-cn_topic_0079615000_p20113045"></a><a name="zh-cn_topic_0079615000_p20113045"></a>The port on each node on which this service is exposed when type=NodePort or LoadBalancer. Usually assigned by the system. If specified, it will be allocated to the service if unused or else creation of the service will fail. Default is to auto-allocate a port if the ServiceType of this Service requires one.</p>
<p id="zh-cn_topic_0079615000_p46799678"><a name="zh-cn_topic_0079615000_p46799678"></a><a name="zh-cn_topic_0079615000_p46799678"></a>Value range: [30000,32767].</p>
</td>
</tr>
</tbody>
</table>

**表 8**  loadBalancer字段数据结构说明

<a name="zh-cn_topic_0079615000_table53440856"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row51962411"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615000_p48205786"><a name="zh-cn_topic_0079615000_p48205786"></a><a name="zh-cn_topic_0079615000_p48205786"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p47818518205444"><a name="p47818518205444"></a><a name="p47818518205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p48094722205444"><a name="p48094722205444"></a><a name="p48094722205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p3358435205444"><a name="p3358435205444"></a><a name="p3358435205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row5522162"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p44641943"><a name="zh-cn_topic_0079615000_p44641943"></a><a name="zh-cn_topic_0079615000_p44641943"></a>ingress</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p59227608"><a name="zh-cn_topic_0079615000_p59227608"></a><a name="zh-cn_topic_0079615000_p59227608"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p32706975"><a name="zh-cn_topic_0079615000_p32706975"></a><a name="zh-cn_topic_0079615000_p32706975"></a><a href="#zh-cn_topic_0079615000_table11205657">表9</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p19738079"><a name="zh-cn_topic_0079615000_p19738079"></a><a name="zh-cn_topic_0079615000_p19738079"></a>Ingress is a list containing ingress points for the load-balancer. Traffic intended for the service should be sent to these ingress points.</p>
</td>
</tr>
</tbody>
</table>

**表 9**  ingress字段数据结构说明

<a name="zh-cn_topic_0079615000_table11205657"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row45645814"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615000_p6323433"><a name="zh-cn_topic_0079615000_p6323433"></a><a name="zh-cn_topic_0079615000_p6323433"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p37689936205444"><a name="p37689936205444"></a><a name="p37689936205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p32986004205444"><a name="p32986004205444"></a><a name="p32986004205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p54620668205444"><a name="p54620668205444"></a><a name="p54620668205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row47516889"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p23662823"><a name="zh-cn_topic_0079615000_p23662823"></a><a name="zh-cn_topic_0079615000_p23662823"></a>ip</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p37640485"><a name="zh-cn_topic_0079615000_p37640485"></a><a name="zh-cn_topic_0079615000_p37640485"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p28980411"><a name="zh-cn_topic_0079615000_p28980411"></a><a name="zh-cn_topic_0079615000_p28980411"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p65711954"><a name="zh-cn_topic_0079615000_p65711954"></a><a name="zh-cn_topic_0079615000_p65711954"></a>IP is set for load-balancer ingress points that are IP based.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row54536677"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p55394720"><a name="zh-cn_topic_0079615000_p55394720"></a><a name="zh-cn_topic_0079615000_p55394720"></a>hostname</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p57787311"><a name="zh-cn_topic_0079615000_p57787311"></a><a name="zh-cn_topic_0079615000_p57787311"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p50260603"><a name="zh-cn_topic_0079615000_p50260603"></a><a name="zh-cn_topic_0079615000_p50260603"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p44577003"><a name="zh-cn_topic_0079615000_p44577003"></a><a name="zh-cn_topic_0079615000_p44577003"></a>Hostname is set for load-balancer ingress points that are DNS based.</p>
</td>
</tr>
</tbody>
</table>

**表 10**  SessionAffinityConfig字段数据结构说明

<a name="table136388588444"></a>
<table><thead align="left"><tr id="row17654195814445"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="p065714584446"><a name="p065714584446"></a><a name="p065714584446"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p1661758184416"><a name="p1661758184416"></a><a name="p1661758184416"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p15664155811447"><a name="p15664155811447"></a><a name="p15664155811447"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p11666115894413"><a name="p11666115894413"></a><a name="p11666115894413"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row96705581444"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p12673105874416"><a name="p12673105874416"></a><a name="p12673105874416"></a>clientIP</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p19676258124412"><a name="p19676258124412"></a><a name="p19676258124412"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p18954145284618"><a name="p18954145284618"></a><a name="p18954145284618"></a><a href="#table135671447154712">表11</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p147181506490"><a name="p147181506490"></a><a name="p147181506490"></a>clientIP contains the configurations of Client IP based session affinity.</p>
</td>
</tr>
</tbody>
</table>

**表 11**  ClientIPConfig字段数据结构说明

<a name="table135671447154712"></a>
<table><thead align="left"><tr id="row19584134734714"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="p14588144710478"><a name="p14588144710478"></a><a name="p14588144710478"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p1159113472474"><a name="p1159113472474"></a><a name="p1159113472474"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p159474774710"><a name="p159474774710"></a><a name="p159474774710"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p10597447134717"><a name="p10597447134717"></a><a name="p10597447134717"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1560115477471"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p1760484719472"><a name="p1760484719472"></a><a name="p1760484719472"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p160812473475"><a name="p160812473475"></a><a name="p160812473475"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p861110476477"><a name="p861110476477"></a><a name="p861110476477"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p57539265015"><a name="p57539265015"></a><a name="p57539265015"></a>timeoutSeconds specifies the seconds of ClientIP type session sticky time. The value must be &gt;0 &amp;&amp; &lt;=86400(for 1 day) if ServiceAffinity == "ClientIP". Default value is 10800(for 3 hours).</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
    "kind":"Service",
    "apiVersion":"v1",
    "metadata":{
       "name":"service-test",
       "creationTimestamp":null,
       "labels":{
          "app":"cce"
       }
    },
    "spec":{
       "ports":[{
          "name":"http",
          "port":80,
          "targetPort":0
       }],
       "selector":{
       "app":"cce"
       },
       "clusterIP":"None"
   },
   "status":{
      "loadBalancer":{}
   }
}
```

## 响应消息<a name="s6d1491fd7cac4a0fa401c80bcb2778d1"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079615000_ref458763557)。

**响应示例：**

```
{
   "kind":"Service",
   "apiVersion":"v1",
   "metadata":{
      "name":"service-test",
      "namespace":"default",
      "selfLink":"/api/v1/namespaces/default/services/service-test",
      "uid":"61c9aee7-29aa-11e7-896b-fa163ebe5340",
      "resourceVersion":"1349201",
      "creationTimestamp":"2017-04-25T11:29:01Z",
      "labels":{
         "app":"cce"     
      }
   },
   "spec":{
      "ports":[{
         "name":"http",
         "protocol":"TCP",
         "port":80,
         "targetPort":80
      }],
      "selector":{"app":"cce"},
      "clusterIP":"None",
      "type":"ClusterIP",
      "sessionAffinity":"None"
   },
   "status":{
      "loadBalancer":{}
   }
}
```

## 状态码<a name="s98b5155925e944f0b008c4f34c95225b"></a>

[表12](#zh-cn_topic_0079615000_table33742049)描述API的状态码。

**表 12**  状态码

<a name="zh-cn_topic_0079615000_table33742049"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row19948981"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p59593538205444"><a name="p59593538205444"></a><a name="p59593538205444"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p62347282205444"><a name="p62347282205444"></a><a name="p62347282205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row49645340"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615000_p61849578"><a name="zh-cn_topic_0079615000_p61849578"></a><a name="zh-cn_topic_0079615000_p61849578"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615000_p43759888"><a name="zh-cn_topic_0079615000_p43759888"></a><a name="zh-cn_topic_0079615000_p43759888"></a>The request has been fulfilled, resulting in the creation of a new resource.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

