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

    -   labels参数下“app“参数所键入的“appname“为显示在CCE工作负载界面上的工作负载名称，其值与Deployment的“metadata.labels“中所添加的内容一致。
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
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p16274301796"><a name="p16274301796"></a><a name="p16274301796"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row41865316"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615000_p35647420"><a name="zh-cn_topic_0079615000_p35647420"></a><a name="zh-cn_topic_0079615000_p35647420"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p1759884"><a name="zh-cn_topic_0079615000_p1759884"></a><a name="zh-cn_topic_0079615000_p1759884"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615000_p8332925"><a name="zh-cn_topic_0079615000_p8332925"></a><a name="zh-cn_topic_0079615000_p8332925"></a>Name and auth scope, such as for teams and projects.</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p62095922205444"><a name="p62095922205444"></a><a name="p62095922205444"></a>参数类型</p>
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
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p31312592"><a name="zh-cn_topic_0079615000_p31312592"></a><a name="zh-cn_topic_0079615000_p31312592"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="zh-cn_topic_0079615000_p13377873"><a name="zh-cn_topic_0079615000_p13377873"></a><a name="zh-cn_topic_0079615000_p13377873"></a>The value of this parameter is <strong id="zh-cn_topic_0079615000_b53291996"><a name="zh-cn_topic_0079615000_b53291996"></a><a name="zh-cn_topic_0079615000_b53291996"></a>Service</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row9865923"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p60942285"><a name="zh-cn_topic_0079615000_p60942285"></a><a name="zh-cn_topic_0079615000_p60942285"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p37378072"><a name="zh-cn_topic_0079615000_p37378072"></a><a name="zh-cn_topic_0079615000_p37378072"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p7725004"><a name="zh-cn_topic_0079615000_p7725004"></a><a name="zh-cn_topic_0079615000_p7725004"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p21745551"><a name="zh-cn_topic_0079615000_p21745551"></a><a name="zh-cn_topic_0079615000_p21745551"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="zh-cn_topic_0079615000_p61492239"><a name="zh-cn_topic_0079615000_p61492239"></a><a name="zh-cn_topic_0079615000_p61492239"></a>The value of this parameter is <strong id="zh-cn_topic_0079615000_b16559244"><a name="zh-cn_topic_0079615000_b16559244"></a><a name="zh-cn_topic_0079615000_b16559244"></a>v1</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row14815471"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p59202483"><a name="zh-cn_topic_0079615000_p59202483"></a><a name="zh-cn_topic_0079615000_p59202483"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p30671812"><a name="zh-cn_topic_0079615000_p30671812"></a><a name="zh-cn_topic_0079615000_p30671812"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p1388809"><a name="zh-cn_topic_0079615000_p1388809"></a><a name="zh-cn_topic_0079615000_p1388809"></a><a href="#zh-cn_topic_0079615000_table43837055">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p5808961"><a name="zh-cn_topic_0079615000_p5808961"></a><a name="zh-cn_topic_0079615000_p5808961"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row52280657"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p6874787"><a name="zh-cn_topic_0079615000_p6874787"></a><a name="zh-cn_topic_0079615000_p6874787"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p19986890"><a name="zh-cn_topic_0079615000_p19986890"></a><a name="zh-cn_topic_0079615000_p19986890"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p8325422"><a name="zh-cn_topic_0079615000_p8325422"></a><a name="zh-cn_topic_0079615000_p8325422"></a><a href="#zh-cn_topic_0079615000_table58989182">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p29435243"><a name="zh-cn_topic_0079615000_p29435243"></a><a name="zh-cn_topic_0079615000_p29435243"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row63590603"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p50565204"><a name="zh-cn_topic_0079615000_p50565204"></a><a name="zh-cn_topic_0079615000_p50565204"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p2140858"><a name="zh-cn_topic_0079615000_p2140858"></a><a name="zh-cn_topic_0079615000_p2140858"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p39191780"><a name="zh-cn_topic_0079615000_p39191780"></a><a name="zh-cn_topic_0079615000_p39191780"></a><a href="#zh-cn_topic_0079615000_table61140591">status</a> object</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p56943584205444"><a name="p56943584205444"></a><a name="p56943584205444"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p49027631205444"><a name="p49027631205444"></a><a name="p49027631205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row51840373"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p38320646"><a name="zh-cn_topic_0079615000_p38320646"></a><a name="zh-cn_topic_0079615000_p38320646"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p16964616"><a name="zh-cn_topic_0079615000_p16964616"></a><a name="zh-cn_topic_0079615000_p16964616"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p31956642"><a name="zh-cn_topic_0079615000_p31956642"></a><a name="zh-cn_topic_0079615000_p31956642"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p38351229"><a name="zh-cn_topic_0079615000_p38351229"></a><a name="zh-cn_topic_0079615000_p38351229"></a>Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated.</p>
<p id="zh-cn_topic_0079615000_p9616746"><a name="zh-cn_topic_0079615000_p9616746"></a><a name="zh-cn_topic_0079615000_p9616746"></a>Value length: 4 character ≤ String length ≤ 63 characters</p>
<p id="zh-cn_topic_0079615000_p19441857"><a name="zh-cn_topic_0079615000_p19441857"></a><a name="zh-cn_topic_0079615000_p19441857"></a>The string must comply with regular expression: ^[a-z]([-a-z0-9]*[a-z0-9])?$.</p>
</td>
</tr>
<tr id="r59e9b08f407d496eac092f809321b53f"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="aeefc6fe8fca8446685053b6d0902640e"><a name="aeefc6fe8fca8446685053b6d0902640e"></a><a name="aeefc6fe8fca8446685053b6d0902640e"></a>clusterName</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p541213427308"><a name="zh-cn_topic_0079615000_p541213427308"></a><a name="zh-cn_topic_0079615000_p541213427308"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p641274253010"><a name="zh-cn_topic_0079615000_p641274253010"></a><a name="zh-cn_topic_0079615000_p641274253010"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a7814694051a0406dbbba95ba61cb3e8f"><a name="a7814694051a0406dbbba95ba61cb3e8f"></a><a name="a7814694051a0406dbbba95ba61cb3e8f"></a>The name of the cluster which the object belongs to. This is used to distinguish resources with same name and namespace in different clusters. This field is not set anywhere right now and apiserver is going to ignore it if set in create or update request.</p>
</td>
</tr>
<tr id="r08d3f4618a3d463fb26929343fc28aa7"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a5a6084a987a14186b0d019c3a9f73036"><a name="a5a6084a987a14186b0d019c3a9f73036"></a><a name="a5a6084a987a14186b0d019c3a9f73036"></a>initializers</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p561852113110"><a name="zh-cn_topic_0079615000_p561852113110"></a><a name="zh-cn_topic_0079615000_p561852113110"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a50f457b14c8a4bcbb8c8d6560a2724ff"><a name="a50f457b14c8a4bcbb8c8d6560a2724ff"></a><a name="a50f457b14c8a4bcbb8c8d6560a2724ff"></a><a href="请求数据结构.md#t693768b66dfa47239c0f155ad4dd18e8">initializers</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p161812183116"><a name="zh-cn_topic_0079615000_p161812183116"></a><a name="zh-cn_topic_0079615000_p161812183116"></a>An initializer is a controller which enforces some system invariant at object creation time. This field is a list of initializers that have not yet acted on this object. If nil or empty, this object has been completely initialized. Otherwise, the object is considered uninitialized and is hidden (in list/watch and get calls) from clients that haven't explicitly asked to observe uninitialized objects. When an object is created, the system will populate this list with the current set of initializers. Only privileged users may set or modify this list. Once it is empty, it may not be modified further by any user.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row40758985"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p13143484"><a name="zh-cn_topic_0079615000_p13143484"></a><a name="zh-cn_topic_0079615000_p13143484"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p57989292"><a name="zh-cn_topic_0079615000_p57989292"></a><a name="zh-cn_topic_0079615000_p57989292"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p66621056"><a name="zh-cn_topic_0079615000_p66621056"></a><a name="zh-cn_topic_0079615000_p66621056"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p27596449"><a name="zh-cn_topic_0079615000_p27596449"></a><a name="zh-cn_topic_0079615000_p27596449"></a>GenerateName is an optional prefix, used by the server, to generate a unique name ONLY IF the Name field has not been provided. If this field is used, the name returned to the client will be different than the name passed. This value will also be combined with a unique suffix. The provided value has the same validation rules as the Name field, and may be truncated by the length of the suffix required to make the value unique on the server.</p>
<p id="zh-cn_topic_0079615000_p47041449"><a name="zh-cn_topic_0079615000_p47041449"></a><a name="zh-cn_topic_0079615000_p47041449"></a>If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header).</p>
<p id="zh-cn_topic_0079615000_p20719862"><a name="zh-cn_topic_0079615000_p20719862"></a><a name="zh-cn_topic_0079615000_p20719862"></a>Applied only if Name is not specified.</p>
<p id="zh-cn_topic_0079615000_p52261031"><a name="zh-cn_topic_0079615000_p52261031"></a><a name="zh-cn_topic_0079615000_p52261031"></a>Value length: 4 character ≤ String length ≤ 63 characters</p>
<p id="zh-cn_topic_0079615000_p587239"><a name="zh-cn_topic_0079615000_p587239"></a><a name="zh-cn_topic_0079615000_p587239"></a>The string must comply with regular expression: ^[a-z]([-a-z0-9]*[a-z0-9])?$.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row5285158"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p25444686"><a name="zh-cn_topic_0079615000_p25444686"></a><a name="zh-cn_topic_0079615000_p25444686"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p47753670"><a name="zh-cn_topic_0079615000_p47753670"></a><a name="zh-cn_topic_0079615000_p47753670"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p42842038"><a name="zh-cn_topic_0079615000_p42842038"></a><a name="zh-cn_topic_0079615000_p42842038"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p47653063"><a name="zh-cn_topic_0079615000_p47653063"></a><a name="zh-cn_topic_0079615000_p47653063"></a>Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty. Must be a DNS_LABEL. Cannot be updated.</p>
<p id="zh-cn_topic_0079615000_p26224387"><a name="zh-cn_topic_0079615000_p26224387"></a><a name="zh-cn_topic_0079615000_p26224387"></a>Value length: 0 character &lt; String length ≤ 63 characters.</p>
<p id="zh-cn_topic_0079615000_p34692896"><a name="zh-cn_topic_0079615000_p34692896"></a><a name="zh-cn_topic_0079615000_p34692896"></a>The string must comply with regular expression [a-z0-9]([-a-z0-9]*[a-z0-9])?.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row43800616"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p58188993"><a name="zh-cn_topic_0079615000_p58188993"></a><a name="zh-cn_topic_0079615000_p58188993"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p15687991"><a name="zh-cn_topic_0079615000_p15687991"></a><a name="zh-cn_topic_0079615000_p15687991"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p62767729"><a name="zh-cn_topic_0079615000_p62767729"></a><a name="zh-cn_topic_0079615000_p62767729"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p51021271"><a name="zh-cn_topic_0079615000_p51021271"></a><a name="zh-cn_topic_0079615000_p51021271"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
<div class="note" id="zh-cn_topic_0079615000_note56538263"><a name="zh-cn_topic_0079615000_note56538263"></a><a name="zh-cn_topic_0079615000_note56538263"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079615000_p39082323"><a name="zh-cn_topic_0079615000_p39082323"></a><a name="zh-cn_topic_0079615000_p39082323"></a>This parameter is automatically generated. Do not assign values to this parameter. Otherwise, the API fails to be called.</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row16196587"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p36855200"><a name="zh-cn_topic_0079615000_p36855200"></a><a name="zh-cn_topic_0079615000_p36855200"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p32481246"><a name="zh-cn_topic_0079615000_p32481246"></a><a name="zh-cn_topic_0079615000_p32481246"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p13735244"><a name="zh-cn_topic_0079615000_p13735244"></a><a name="zh-cn_topic_0079615000_p13735244"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p38812946"><a name="zh-cn_topic_0079615000_p38812946"></a><a name="zh-cn_topic_0079615000_p38812946"></a>UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations. Populated by the system. Read-only.</p>
<div class="note" id="zh-cn_topic_0079615000_note13772198"><a name="zh-cn_topic_0079615000_note13772198"></a><a name="zh-cn_topic_0079615000_note13772198"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079615000_p56840921"><a name="zh-cn_topic_0079615000_p56840921"></a><a name="zh-cn_topic_0079615000_p56840921"></a>This parameter is automatically generated. Do not assign values to this parameter. Otherwise, the API fails to be called.</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row41806244"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p30862607"><a name="zh-cn_topic_0079615000_p30862607"></a><a name="zh-cn_topic_0079615000_p30862607"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p16843214"><a name="zh-cn_topic_0079615000_p16843214"></a><a name="zh-cn_topic_0079615000_p16843214"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p22123082"><a name="zh-cn_topic_0079615000_p22123082"></a><a name="zh-cn_topic_0079615000_p22123082"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p47139178"><a name="zh-cn_topic_0079615000_p47139178"></a><a name="zh-cn_topic_0079615000_p47139178"></a>An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources. Populated by the system. Read-only. Value must be treated as opaque by clients.</p>
<div class="note" id="zh-cn_topic_0079615000_note21599419"><a name="zh-cn_topic_0079615000_note21599419"></a><a name="zh-cn_topic_0079615000_note21599419"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079615000_p60177046"><a name="zh-cn_topic_0079615000_p60177046"></a><a name="zh-cn_topic_0079615000_p60177046"></a>This parameter is automatically generated. Do not assign values to this parameter. Otherwise, the API fails to be called.</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row4722509"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p46978935"><a name="zh-cn_topic_0079615000_p46978935"></a><a name="zh-cn_topic_0079615000_p46978935"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p47197410"><a name="zh-cn_topic_0079615000_p47197410"></a><a name="zh-cn_topic_0079615000_p47197410"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p64893878"><a name="zh-cn_topic_0079615000_p64893878"></a><a name="zh-cn_topic_0079615000_p64893878"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p21912729"><a name="zh-cn_topic_0079615000_p21912729"></a><a name="zh-cn_topic_0079615000_p21912729"></a>A sequence number representing a specific generation of the desired state. Currently only implemented by replication controllers. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row62996841"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p2470505"><a name="zh-cn_topic_0079615000_p2470505"></a><a name="zh-cn_topic_0079615000_p2470505"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p65893197"><a name="zh-cn_topic_0079615000_p65893197"></a><a name="zh-cn_topic_0079615000_p65893197"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p35748734"><a name="zh-cn_topic_0079615000_p35748734"></a><a name="zh-cn_topic_0079615000_p35748734"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p9966307"><a name="zh-cn_topic_0079615000_p9966307"></a><a name="zh-cn_topic_0079615000_p9966307"></a>CreationTimestamp is a timestamp representing the server time when this object was created. It is not guaranteed to be set in happens-before order across separate operations. Clients may not set this value. It is represented in RFC3339 form and is in UTC. Populated by the system. Read-only. Null for lists.</p>
<div class="note" id="zh-cn_topic_0079615000_note22587900"><a name="zh-cn_topic_0079615000_note22587900"></a><a name="zh-cn_topic_0079615000_note22587900"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079615000_p1964516"><a name="zh-cn_topic_0079615000_p1964516"></a><a name="zh-cn_topic_0079615000_p1964516"></a>This parameter is automatically generated. Do not assign values to this parameter. Otherwise, the API fails to be called.</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row17680651"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p22846659"><a name="zh-cn_topic_0079615000_p22846659"></a><a name="zh-cn_topic_0079615000_p22846659"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p38640075"><a name="zh-cn_topic_0079615000_p38640075"></a><a name="zh-cn_topic_0079615000_p38640075"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p42838347"><a name="zh-cn_topic_0079615000_p42838347"></a><a name="zh-cn_topic_0079615000_p42838347"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p47354092"><a name="zh-cn_topic_0079615000_p47354092"></a><a name="zh-cn_topic_0079615000_p47354092"></a>DeletionTimestamp is RFC 3339 date and time at which this resource will be deleted. This field is set by the server when a graceful deletion is requested by the user, and is not directly settable by a client. The resource will be deleted (no longer visible from resource lists, and not reachable by name) after the time in this field. Once set, this value may not be unset or be set further into the future, although it may be shortened or the resource may be deleted prior to this time. For example, a user may request that a pod is deleted in 30 seconds. The Kubelet will react by sending a graceful termination signal to the containers in the pod. Once the resource is deleted in the API, the Kubelet will send a hard termination signal to the container. If not set, graceful deletion of the object has not been requested. Populated by the system when a graceful deletion is requested. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row23533648"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p27177349"><a name="zh-cn_topic_0079615000_p27177349"></a><a name="zh-cn_topic_0079615000_p27177349"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p53881646"><a name="zh-cn_topic_0079615000_p53881646"></a><a name="zh-cn_topic_0079615000_p53881646"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p2337204"><a name="zh-cn_topic_0079615000_p2337204"></a><a name="zh-cn_topic_0079615000_p2337204"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p55095806"><a name="zh-cn_topic_0079615000_p55095806"></a><a name="zh-cn_topic_0079615000_p55095806"></a>Number of seconds allowed for this object to gracefully terminate before it will be removed from the system. Only set when deletionTimestamp is also set. May only be shortened. Read-only.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row26100208"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p33742108"><a name="zh-cn_topic_0079615000_p33742108"></a><a name="zh-cn_topic_0079615000_p33742108"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p48756224"><a name="zh-cn_topic_0079615000_p48756224"></a><a name="zh-cn_topic_0079615000_p48756224"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p729565691414"><a name="p729565691414"></a><a name="p729565691414"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p48745491"><a name="zh-cn_topic_0079615000_p48745491"></a><a name="zh-cn_topic_0079615000_p48745491"></a>Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row36056236"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p34874009"><a name="zh-cn_topic_0079615000_p34874009"></a><a name="zh-cn_topic_0079615000_p34874009"></a>Annotations</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p6222499"><a name="zh-cn_topic_0079615000_p6222499"></a><a name="zh-cn_topic_0079615000_p6222499"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p1177145917144"><a name="p1177145917144"></a><a name="p1177145917144"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p23629100"><a name="zh-cn_topic_0079615000_p23629100"></a><a name="zh-cn_topic_0079615000_p23629100"></a>Annotations is an unstructured key value map stored with a resource that may be set by external tools to store and retrieve arbitrary metadata. They are not queryable and should be preserved when modifying objects.</p>
</td>
</tr>
<tr id="r7a1239227d8c4999a488e54b7405613f"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a4ac11975cfca47d4a172ea9b2c1bbd8c"><a name="a4ac11975cfca47d4a172ea9b2c1bbd8c"></a><a name="a4ac11975cfca47d4a172ea9b2c1bbd8c"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p405649418162"><a name="zh-cn_topic_0079615000_p405649418162"></a><a name="zh-cn_topic_0079615000_p405649418162"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p439439618162"><a name="zh-cn_topic_0079615000_p439439618162"></a><a name="zh-cn_topic_0079615000_p439439618162"></a><a href="#tf1f749652c974a92b9e9cf83deb8d111">ownerReferences</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a9587edde5d2447baad8fc20f25e98936"><a name="a9587edde5d2447baad8fc20f25e98936"></a><a name="a9587edde5d2447baad8fc20f25e98936"></a>List of objects depended by this object. If ALL objects in the list have been deleted, this object will be garbage collected. If this object is managed by a controller, then an entry in this list will point to this controller, with the controller field set to true. There cannot be more than one managing controller.</p>
</td>
</tr>
<tr id="r375d22b85d2e49f8a4c776f12c7be3c6"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="ad7058987bd734754a40cb402767e2b63"><a name="ad7058987bd734754a40cb402767e2b63"></a><a name="ad7058987bd734754a40cb402767e2b63"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a6f58b1f64d024488b85c0b04bc817661"><a name="a6f58b1f64d024488b85c0b04bc817661"></a><a name="a6f58b1f64d024488b85c0b04bc817661"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p12528182712158"><a name="p12528182712158"></a><a name="p12528182712158"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a924801d78ff14b239b16888f8c28249a"><a name="a924801d78ff14b239b16888f8c28249a"></a><a name="a924801d78ff14b239b16888f8c28249a"></a>Must be empty before the object is deleted from the registry. Each entry is an identifier for the responsible component that will remove the entry from the list. If the deletionTimestamp of the object is non-nil, entries in this list can only be removed.</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p20795188205444"><a name="p20795188205444"></a><a name="p20795188205444"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p6688676205444"><a name="p6688676205444"></a><a name="p6688676205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row59285030"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p37358106"><a name="zh-cn_topic_0079615000_p37358106"></a><a name="zh-cn_topic_0079615000_p37358106"></a>ports</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p6107739"><a name="zh-cn_topic_0079615000_p6107739"></a><a name="zh-cn_topic_0079615000_p6107739"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p24964816"><a name="zh-cn_topic_0079615000_p24964816"></a><a name="zh-cn_topic_0079615000_p24964816"></a><a href="#zh-cn_topic_0079615000_table13394413">ports</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p12848880"><a name="zh-cn_topic_0079615000_p12848880"></a><a name="zh-cn_topic_0079615000_p12848880"></a>The list of ports that are exposed by this service.</p>
</td>
</tr>
<tr id="r84d3b4cd4c354a7b8d2c2d8e643f2eb2"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a20c290dec91e461f9806ac7ddb64b32e"><a name="a20c290dec91e461f9806ac7ddb64b32e"></a><a name="a20c290dec91e461f9806ac7ddb64b32e"></a>selector</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a792005b9cc9c4b62aa05ca6ba72edb1b"><a name="a792005b9cc9c4b62aa05ca6ba72edb1b"></a><a name="a792005b9cc9c4b62aa05ca6ba72edb1b"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a9fd3a2cf6b17488ebf787d90dcdd4806"><a name="a9fd3a2cf6b17488ebf787d90dcdd4806"></a><a name="a9fd3a2cf6b17488ebf787d90dcdd4806"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p1632525513155"><a name="p1632525513155"></a><a name="p1632525513155"></a>This service will route traffic to pods having labels matching this selector. Label keys and values that must match in order to receive traffic for this service. If empty, all pods are selected, if not specified, endpoints must be manually specified.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row48531064"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p38702074"><a name="zh-cn_topic_0079615000_p38702074"></a><a name="zh-cn_topic_0079615000_p38702074"></a>clusterIP</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p47860305"><a name="zh-cn_topic_0079615000_p47860305"></a><a name="zh-cn_topic_0079615000_p47860305"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p51479525"><a name="zh-cn_topic_0079615000_p51479525"></a><a name="zh-cn_topic_0079615000_p51479525"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p9091997"><a name="zh-cn_topic_0079615000_p9091997"></a><a name="zh-cn_topic_0079615000_p9091997"></a>ClusterIP is usually assigned by the master and is the IP address of the service. If specified, it will be allocated to the service if it is unused or else creation of the service will fail. Valid values are None, empty string (""), or a valid IP address. 'None' can be specified for a headless service when proxying is not required. Cannot be updated.</p>
<p id="zh-cn_topic_0079615000_p14719114"><a name="zh-cn_topic_0079615000_p14719114"></a><a name="zh-cn_topic_0079615000_p14719114"></a>The value of this parameter is <strong id="zh-cn_topic_0079615000_b65363170"><a name="zh-cn_topic_0079615000_b65363170"></a><a name="zh-cn_topic_0079615000_b65363170"></a>NONE</strong> or a valid IP address.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row51397620"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p2457719"><a name="zh-cn_topic_0079615000_p2457719"></a><a name="zh-cn_topic_0079615000_p2457719"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p64857530"><a name="zh-cn_topic_0079615000_p64857530"></a><a name="zh-cn_topic_0079615000_p64857530"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p18968549"><a name="zh-cn_topic_0079615000_p18968549"></a><a name="zh-cn_topic_0079615000_p18968549"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p60057505"><a name="zh-cn_topic_0079615000_p60057505"></a><a name="zh-cn_topic_0079615000_p60057505"></a>Type of exposed service. Must be ClusterIP, NodePort, or LoadBalancer. Defaults to ClusterIP.</p>
<p id="p939314015208"><a name="p939314015208"></a><a name="p939314015208"></a>The <span class="parmname" id="p142747974e2045eea6c2862545e07ed2"><a name="p142747974e2045eea6c2862545e07ed2"></a><a name="p142747974e2045eea6c2862545e07ed2"></a>“LoadBalancer”</span>&nbsp;value indicates that Elastic Load Balance (ELB) is in use. For details about how to use ELB with a cluster created by the CCE console, see section&nbsp;<a href="集群中使用ELB的操作方法.md">集群中使用ELB的操作方法</a>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615000_row45038152"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p24211670"><a name="zh-cn_topic_0079615000_p24211670"></a><a name="zh-cn_topic_0079615000_p24211670"></a>externalIPs</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p14988220"><a name="zh-cn_topic_0079615000_p14988220"></a><a name="zh-cn_topic_0079615000_p14988220"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p6086307"><a name="zh-cn_topic_0079615000_p6086307"></a><a name="zh-cn_topic_0079615000_p6086307"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p1531612555153"><a name="p1531612555153"></a><a name="p1531612555153"></a>externalIPs is a list of IP addresses for which nodes in the cluster will also accept traffic for this service. These IPs are not managed by Kubernetes. The user is responsible for ensuring that traffic arrives at a node with this IP. A common example is external load-balancers that are not part of the Kubernetes system. A previous form of this functionality exists as the deprecatedPublicIPs field. When using this field, callers should also clear the deprecatedPublicIPs field.</p>
</td>
</tr>
<tr id="r8c13c2686b9b4cd4b6524cd9424a33ea"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="aea7cc907862a434a926b2ae1ada48056"><a name="aea7cc907862a434a926b2ae1ada48056"></a><a name="aea7cc907862a434a926b2ae1ada48056"></a>externalTrafficPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p126206215368"><a name="zh-cn_topic_0079615000_p126206215368"></a><a name="zh-cn_topic_0079615000_p126206215368"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p962062143619"><a name="zh-cn_topic_0079615000_p962062143619"></a><a name="zh-cn_topic_0079615000_p962062143619"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p1931535551511"><a name="p1931535551511"></a><a name="p1931535551511"></a>externalTrafficPolicy denotes if this Service desires to route external traffic to node-local or cluster-wide endpoints. "Local" preserves the client source IP and avoids a second hop for LoadBalancer and Nodeport type services, but risks potentially imbalanced traffic spreading. "Cluster" obscures the client source IP and may cause a second hop to another node, but should have good overall load-spreading.</p>
</td>
</tr>
<tr id="re7093443281c4ba2a8de2837ac34d456"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p133296474363"><a name="zh-cn_topic_0079615000_p133296474363"></a><a name="zh-cn_topic_0079615000_p133296474363"></a>healthCheckNodePort</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p193295472360"><a name="zh-cn_topic_0079615000_p193295472360"></a><a name="zh-cn_topic_0079615000_p193295472360"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a807a0eaa37ad462fbdc2b3051c8f720c"><a name="a807a0eaa37ad462fbdc2b3051c8f720c"></a><a name="a807a0eaa37ad462fbdc2b3051c8f720c"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p12312185514158"><a name="p12312185514158"></a><a name="p12312185514158"></a>healthCheckNodePort specifies the healthcheck nodePort for the service. If not specified, HealthCheckNodePort is created by the service api backend with the allocated nodePort. Will use user-specified nodePort value if specified by the client. Only effects when Type is set to LoadBalancer and ExternalTrafficPolicy is set to Local.</p>
</td>
</tr>
<tr id="r4ad3f7ed3c7043f8b8e091f93a268a16"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p437123915289"><a name="zh-cn_topic_0079615000_p437123915289"></a><a name="zh-cn_topic_0079615000_p437123915289"></a>externalName</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p143718398286"><a name="zh-cn_topic_0079615000_p143718398286"></a><a name="zh-cn_topic_0079615000_p143718398286"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="aa3226079bd494142a3d3d909335b2841"><a name="aa3226079bd494142a3d3d909335b2841"></a><a name="aa3226079bd494142a3d3d909335b2841"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p6310205571519"><a name="p6310205571519"></a><a name="p6310205571519"></a>externalName is the external reference that kubedns or equivalent will return as a CNAME record for this service. No proxying will be involved. Must be a valid DNS name and requires Type to be ExternalName.</p>
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
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p17499376531"><a name="zh-cn_topic_0079615000_p17499376531"></a><a name="zh-cn_topic_0079615000_p17499376531"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p17544165881512"><a name="p17544165881512"></a><a name="p17544165881512"></a>Optional: If specified and supported by the platform, this will restrict traffic through the cloud-provide.load-balancer will be restricted to the specified client IPs. This field will be ignored if the cloud-provider does not support the feature.".</p>
</td>
</tr>
<tr id="row92981025102611"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p2029882510268"><a name="p2029882510268"></a><a name="p2029882510268"></a>publishNotReadyAddresses</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p1729862582611"><a name="p1729862582611"></a><a name="p1729862582611"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p52986255267"><a name="p52986255267"></a><a name="p52986255267"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p016184181613"><a name="p016184181613"></a><a name="p016184181613"></a>publishNotReadyAddresses, when set to true, indicates that DNS implementations must publish the notReadyAddresses of subsets for the Endpoints associated with the Service. The default value is false. The primary use case for setting this field is to use a StatefulSet's Headless Service to propagate SRV records for its Pods without respect to their readiness for purpose of peer discovery. This field will replace the service.alpha.kubernetes.io/tolerate-unready-endpoints when that annotation is deprecated and all clients have been converted to use this field.</p>
</td>
</tr>
<tr id="row10504132411418"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p1550452464112"><a name="p1550452464112"></a><a name="p1550452464112"></a>sessionAffinityConfig</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p2504182413416"><a name="p2504182413416"></a><a name="p2504182413416"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p871715105433"><a name="p871715105433"></a><a name="p871715105433"></a><a href="#table136388588444">SessionAffinityConfig</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p111510411166"><a name="p111510411166"></a><a name="p111510411166"></a>sessionAffinityConfig contains the configurations of session affinity.</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p13553298205444"><a name="p13553298205444"></a><a name="p13553298205444"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p24075347205444"><a name="p24075347205444"></a><a name="p24075347205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row50459994"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p60727681"><a name="zh-cn_topic_0079615000_p60727681"></a><a name="zh-cn_topic_0079615000_p60727681"></a>loadBalancer</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p19995149"><a name="zh-cn_topic_0079615000_p19995149"></a><a name="zh-cn_topic_0079615000_p19995149"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p8994406"><a name="zh-cn_topic_0079615000_p8994406"></a><a name="zh-cn_topic_0079615000_p8994406"></a><a href="#zh-cn_topic_0079615000_table53440856">loadBalancer</a> object</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p5791269205444"><a name="p5791269205444"></a><a name="p5791269205444"></a>参数类型</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p54885214205444"><a name="p54885214205444"></a><a name="p54885214205444"></a>参数类型</p>
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
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p8117426"><a name="zh-cn_topic_0079615000_p8117426"></a><a name="zh-cn_topic_0079615000_p8117426"></a>Integer</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p48094722205444"><a name="p48094722205444"></a><a name="p48094722205444"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p3358435205444"><a name="p3358435205444"></a><a name="p3358435205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row5522162"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p44641943"><a name="zh-cn_topic_0079615000_p44641943"></a><a name="zh-cn_topic_0079615000_p44641943"></a>ingress</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p59227608"><a name="zh-cn_topic_0079615000_p59227608"></a><a name="zh-cn_topic_0079615000_p59227608"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p32706975"><a name="zh-cn_topic_0079615000_p32706975"></a><a name="zh-cn_topic_0079615000_p32706975"></a><a href="#zh-cn_topic_0079615000_table11205657">ingress</a> object</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p32986004205444"><a name="p32986004205444"></a><a name="p32986004205444"></a>参数类型</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p15664155811447"><a name="p15664155811447"></a><a name="p15664155811447"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p11666115894413"><a name="p11666115894413"></a><a name="p11666115894413"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row96705581444"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p12673105874416"><a name="p12673105874416"></a><a name="p12673105874416"></a>clientIP</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p19676258124412"><a name="p19676258124412"></a><a name="p19676258124412"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p18954145284618"><a name="p18954145284618"></a><a name="p18954145284618"></a><a href="#table135671447154712">ClientIPConfig</a> object</p>
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
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p159474774710"><a name="p159474774710"></a><a name="p159474774710"></a>参数类型</p>
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

