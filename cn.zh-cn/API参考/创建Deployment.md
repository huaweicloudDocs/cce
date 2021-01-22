# 创建Deployment<a name="cce_02_0095"></a>

## 功能介绍<a name="section15904123713483"></a>

该API用于创建一个Deployment资源对象。

如果要将创建的Deployment对象在CCE工作负载界面上正常显示，则必须给创建的Deployment资源对象添加labels标签。

设置请求消息体中的“metadata.labels“参数键值示例如下：

```
labels:
    app: deploymentname
```

其中：

-   同命名空间下，deploymentname名称不要重复
-   deploymentname为显示在CCE工作负载界面上的工作负载名称，需要和metadata.name的值保持一致。且“metadata.labels.app”、“spec.selector.matchLabels.app”、“spec.template.metadata.labels.app”的值要和deploymentname的值同步。可参考请求示例。

## URI<a name="section764545414815"></a>

POST /apis/apps/v1/namespaces/\{namespace\}/deployments \(Supports 1.9 and 1.9+\)

POST /apis/apps/v1beta1/namespaces/\{namespace\}/deployments \(Supports only1.7\)

POST /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments \(Supports 1.15 and 1.15-\)

[表1](#table167042013408)描述该API的参数。

**表 1**  参数描述

<a name="table167042013408"></a>
<table><thead align="left"><tr id="row2067022020405"><th class="cellrowborder" valign="top" width="17.82178217821782%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.693069306930692%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="51.48514851485149%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1670122004014"><td class="cellrowborder" valign="top" width="17.82178217821782%" headers="mcps1.2.4.1.1 "><p id="p166701820144010"><a name="p166701820144010"></a><a name="p166701820144010"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.4.1.2 "><p id="p14670122004017"><a name="p14670122004017"></a><a name="p14670122004017"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="51.48514851485149%" headers="mcps1.2.4.1.3 "><p id="p136704204403"><a name="p136704204403"></a><a name="p136704204403"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row136701220114011"><td class="cellrowborder" valign="top" width="17.82178217821782%" headers="mcps1.2.4.1.1 "><p id="p19670182074012"><a name="p19670182074012"></a><a name="p19670182074012"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.4.1.2 "><p id="p196702020184012"><a name="p196702020184012"></a><a name="p196702020184012"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="51.48514851485149%" headers="mcps1.2.4.1.3 "><p id="p11670162004012"><a name="p11670162004012"></a><a name="p11670162004012"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section24905416619"></a>

**请求参数**：

请求参数如[表2](#table12862324102610)所示。

**表 2**  请求参数

<a name="table12862324102610"></a>
<table><thead align="left"><tr id="row68631424102610"><th class="cellrowborder" valign="top" width="17.01829817018298%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0083857388_zh-cn_topic_0079615000_p19784972"><a name="zh-cn_topic_0083857388_zh-cn_topic_0079615000_p19784972"></a><a name="zh-cn_topic_0083857388_zh-cn_topic_0079615000_p19784972"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.07839216078392%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0083857388_p62904453205444"><a name="zh-cn_topic_0083857388_p62904453205444"></a><a name="zh-cn_topic_0083857388_p62904453205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.92810718928107%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0083857388_p62095922205444"><a name="zh-cn_topic_0083857388_p62095922205444"></a><a name="zh-cn_topic_0083857388_p62095922205444"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.97520247975203%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0083857388_p63713767205444"><a name="zh-cn_topic_0083857388_p63713767205444"></a><a name="zh-cn_topic_0083857388_p63713767205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row386313249268"><td class="cellrowborder" valign="top" width="17.01829817018298%" headers="mcps1.2.5.1.1 "><p id="p1986314247267"><a name="p1986314247267"></a><a name="p1986314247267"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.07839216078392%" headers="mcps1.2.5.1.2 "><p id="p1486362472612"><a name="p1486362472612"></a><a name="p1486362472612"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.92810718928107%" headers="mcps1.2.5.1.3 "><p id="p148631124192613"><a name="p148631124192613"></a><a name="p148631124192613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.97520247975203%" headers="mcps1.2.5.1.4 "><p id="p38631024132612"><a name="p38631024132612"></a><a name="p38631024132612"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row8863172412267"><td class="cellrowborder" valign="top" width="17.01829817018298%" headers="mcps1.2.5.1.1 "><p id="p148638244268"><a name="p148638244268"></a><a name="p148638244268"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="16.07839216078392%" headers="mcps1.2.5.1.2 "><p id="p76386914116"><a name="p76386914116"></a><a name="p76386914116"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.92810718928107%" headers="mcps1.2.5.1.3 "><p id="p1486372472613"><a name="p1486372472613"></a><a name="p1486372472613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.97520247975203%" headers="mcps1.2.5.1.4 "><p id="p1863112415264"><a name="p1863112415264"></a><a name="p1863112415264"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="row9863724112610"><td class="cellrowborder" valign="top" width="17.01829817018298%" headers="mcps1.2.5.1.1 "><p id="p686372411268"><a name="p686372411268"></a><a name="p686372411268"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="16.07839216078392%" headers="mcps1.2.5.1.2 "><p id="p1312651084112"><a name="p1312651084112"></a><a name="p1312651084112"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.92810718928107%" headers="mcps1.2.5.1.3 "><p id="p8864172472616"><a name="p8864172472616"></a><a name="p8864172472616"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table47756489">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="47.97520247975203%" headers="mcps1.2.5.1.4 "><p id="p6864112411261"><a name="p6864112411261"></a><a name="p6864112411261"></a>Standard object metadata.</p>
</td>
</tr>
<tr id="row15864524102611"><td class="cellrowborder" valign="top" width="17.01829817018298%" headers="mcps1.2.5.1.1 "><p id="p9864152411266"><a name="p9864152411266"></a><a name="p9864152411266"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="16.07839216078392%" headers="mcps1.2.5.1.2 "><p id="p4986110104112"><a name="p4986110104112"></a><a name="p4986110104112"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="18.92810718928107%" headers="mcps1.2.5.1.3 "><p id="p8864142422612"><a name="p8864142422612"></a><a name="p8864142422612"></a><a href="#table15570752102811">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="47.97520247975203%" headers="mcps1.2.5.1.4 "><p id="p086472482619"><a name="p086472482619"></a><a name="p086472482619"></a>Specification of the desired behavior of the Deployment.</p>
</td>
</tr>
<tr id="row78644248266"><td class="cellrowborder" valign="top" width="17.01829817018298%" headers="mcps1.2.5.1.1 "><p id="p786418243264"><a name="p786418243264"></a><a name="p786418243264"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="16.07839216078392%" headers="mcps1.2.5.1.2 "><p id="p3864112482611"><a name="p3864112482611"></a><a name="p3864112482611"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.92810718928107%" headers="mcps1.2.5.1.3 "><p id="p586492412263"><a name="p586492412263"></a><a name="p586492412263"></a><a href="#table3226535203116">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="47.97520247975203%" headers="mcps1.2.5.1.4 "><p id="p9864162417264"><a name="p9864162417264"></a><a name="p9864162417264"></a>Most recently observed status of the Deployment.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  spec字段数据结构说明

<a name="table15570752102811"></a>
<table><thead align="left"><tr id="row457055292811"><th class="cellrowborder" valign="top" width="17%" id="mcps1.2.5.1.1"><p id="p1745604817818"><a name="p1745604817818"></a><a name="p1745604817818"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.2"><p id="p046512488820"><a name="p046512488820"></a><a name="p046512488820"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.5.1.3"><p id="p104741648481"><a name="p104741648481"></a><a name="p104741648481"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="48%" id="mcps1.2.5.1.4"><p id="p15491184819810"><a name="p15491184819810"></a><a name="p15491184819810"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row4570125212286"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p15617156102917"><a name="p15617156102917"></a><a name="p15617156102917"></a>minReadySeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p196171162291"><a name="p196171162291"></a><a name="p196171162291"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p1461720642920"><a name="p1461720642920"></a><a name="p1461720642920"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p961746112911"><a name="p961746112911"></a><a name="p961746112911"></a>Minimum number of seconds for which a newly created pod should be ready without any of its container crashing, for it to be considered available. Defaults to 0 (pod will be considered available as soon as it is ready)</p>
</td>
</tr>
<tr id="row18570145219282"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p06171614294"><a name="p06171614294"></a><a name="p06171614294"></a>paused</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p26171263291"><a name="p26171263291"></a><a name="p26171263291"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p66174617297"><a name="p66174617297"></a><a name="p66174617297"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p1261715618295"><a name="p1261715618295"></a><a name="p1261715618295"></a>Indicates that the deployment is paused.</p>
</td>
</tr>
<tr id="row1257055232819"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p1061716652918"><a name="p1061716652918"></a><a name="p1061716652918"></a>progressDeadlineSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p136185612293"><a name="p136185612293"></a><a name="p136185612293"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p1161815622910"><a name="p1161815622910"></a><a name="p1161815622910"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p17618961297"><a name="p17618961297"></a><a name="p17618961297"></a>The maximum time in seconds for a deployment to make progress before it is considered to be failed. The deployment controller will continue to process failed deployments and a condition with a ProgressDeadlineExceeded reason will be surfaced in the deployment status. Once autoRollback is implemented, the deployment controller will automatically rollback failed deployments. Note that progress will not be estimated during the time a deployment is paused. Defaults to 600s.</p>
</td>
</tr>
<tr id="row4570175212287"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p136182612299"><a name="p136182612299"></a><a name="p136182612299"></a>replicas</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p156184692916"><a name="p156184692916"></a><a name="p156184692916"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p19618156152920"><a name="p19618156152920"></a><a name="p19618156152920"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p761818692914"><a name="p761818692914"></a><a name="p761818692914"></a>Number of desired pods. This is a pointer to distinguish between explicit zero and not specified. Defaults to 1.</p>
</td>
</tr>
<tr id="row16571252142813"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p13618136202911"><a name="p13618136202911"></a><a name="p13618136202911"></a>revisionHistoryLimit</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p96181069296"><a name="p96181069296"></a><a name="p96181069296"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p961836122910"><a name="p961836122910"></a><a name="p961836122910"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p1761815614291"><a name="p1761815614291"></a><a name="p1761815614291"></a>The number of old ReplicaSets to retain to allow rollback. This is a pointer to distinguish between explicit zero and not specified. Defaults to 2.</p>
</td>
</tr>
<tr id="row557165219282"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p1861914682913"><a name="p1861914682913"></a><a name="p1861914682913"></a>selector</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p10619126192913"><a name="p10619126192913"></a><a name="p10619126192913"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p138907188364"><a name="p138907188364"></a><a name="p138907188364"></a><a href="#table5344134293516">selector</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p156190611293"><a name="p156190611293"></a><a name="p156190611293"></a>Label selector for pods. Existing ReplicaSets whose pods are selected by this will be the ones affected by this deployment.</p>
</td>
</tr>
<tr id="row1757135214288"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p76191760292"><a name="p76191760292"></a><a name="p76191760292"></a>strategy</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p361936172916"><a name="p361936172916"></a><a name="p361936172916"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p1619116122915"><a name="p1619116122915"></a><a name="p1619116122915"></a><a href="#table10348336183618">strategy</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p361915616297"><a name="p361915616297"></a><a name="p361915616297"></a>The deployment strategy to use to replace existing pods with new ones.</p>
</td>
</tr>
<tr id="row4571145219283"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p1861913692914"><a name="p1861913692914"></a><a name="p1861913692914"></a>template</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p19619176142914"><a name="p19619176142914"></a><a name="p19619176142914"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p1849772214710"><a name="p1849772214710"></a><a name="p1849772214710"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table52089545">template</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p361914615293"><a name="p361914615293"></a><a name="p361914615293"></a>Template describes the pods that will be created.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  status字段数据结构说明

<a name="table3226535203116"></a>
<table><thead align="left"><tr id="row162271135153117"><th class="cellrowborder" valign="top" width="17.378262173782623%" id="mcps1.2.5.1.1"><p id="p186516551182"><a name="p186516551182"></a><a name="p186516551182"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.828417158284172%" id="mcps1.2.5.1.2"><p id="p107515551089"><a name="p107515551089"></a><a name="p107515551089"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.998100189981002%" id="mcps1.2.5.1.3"><p id="p15881655682"><a name="p15881655682"></a><a name="p15881655682"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.795220477952206%" id="mcps1.2.5.1.4"><p id="p69835516817"><a name="p69835516817"></a><a name="p69835516817"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row722703513115"><td class="cellrowborder" valign="top" width="17.378262173782623%" headers="mcps1.2.5.1.1 "><p id="p7770135423110"><a name="p7770135423110"></a><a name="p7770135423110"></a>availableReplicas</p>
</td>
<td class="cellrowborder" valign="top" width="15.828417158284172%" headers="mcps1.2.5.1.2 "><p id="p77701754123116"><a name="p77701754123116"></a><a name="p77701754123116"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.998100189981002%" headers="mcps1.2.5.1.3 "><p id="p15770754123114"><a name="p15770754123114"></a><a name="p15770754123114"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.795220477952206%" headers="mcps1.2.5.1.4 "><p id="p17706543314"><a name="p17706543314"></a><a name="p17706543314"></a>Total number of available pods (ready for at least minReadySeconds) targeted by this deployment.</p>
</td>
</tr>
<tr id="row222703573119"><td class="cellrowborder" valign="top" width="17.378262173782623%" headers="mcps1.2.5.1.1 "><p id="p1577045419318"><a name="p1577045419318"></a><a name="p1577045419318"></a>collisionCount</p>
</td>
<td class="cellrowborder" valign="top" width="15.828417158284172%" headers="mcps1.2.5.1.2 "><p id="p1770105416310"><a name="p1770105416310"></a><a name="p1770105416310"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.998100189981002%" headers="mcps1.2.5.1.3 "><p id="p13770854193119"><a name="p13770854193119"></a><a name="p13770854193119"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.795220477952206%" headers="mcps1.2.5.1.4 "><p id="p1477014546311"><a name="p1477014546311"></a><a name="p1477014546311"></a>Count of hash collisions for the Deployment. The Deployment controller uses this field as a collision avoidance mechanism when it needs to create the name for the newest ReplicaSet.</p>
</td>
</tr>
<tr id="row13227123593111"><td class="cellrowborder" valign="top" width="17.378262173782623%" headers="mcps1.2.5.1.1 "><p id="p7770354203113"><a name="p7770354203113"></a><a name="p7770354203113"></a>conditions</p>
</td>
<td class="cellrowborder" valign="top" width="15.828417158284172%" headers="mcps1.2.5.1.2 "><p id="p377012542314"><a name="p377012542314"></a><a name="p377012542314"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.998100189981002%" headers="mcps1.2.5.1.3 "><p id="p5707133213438"><a name="p5707133213438"></a><a name="p5707133213438"></a><a href="#table2173152418384">conditions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="47.795220477952206%" headers="mcps1.2.5.1.4 "><p id="p15770105413316"><a name="p15770105413316"></a><a name="p15770105413316"></a>Represents the latest available observations of a deployment's current state.</p>
</td>
</tr>
<tr id="row922733533115"><td class="cellrowborder" valign="top" width="17.378262173782623%" headers="mcps1.2.5.1.1 "><p id="p1977014542315"><a name="p1977014542315"></a><a name="p1977014542315"></a>observedGeneration</p>
</td>
<td class="cellrowborder" valign="top" width="15.828417158284172%" headers="mcps1.2.5.1.2 "><p id="p13770105419318"><a name="p13770105419318"></a><a name="p13770105419318"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.998100189981002%" headers="mcps1.2.5.1.3 "><p id="p17770154183118"><a name="p17770154183118"></a><a name="p17770154183118"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.795220477952206%" headers="mcps1.2.5.1.4 "><p id="p197709544316"><a name="p197709544316"></a><a name="p197709544316"></a>The generation observed by the deployment controller</p>
</td>
</tr>
<tr id="row2227143519311"><td class="cellrowborder" valign="top" width="17.378262173782623%" headers="mcps1.2.5.1.1 "><p id="p10770205413314"><a name="p10770205413314"></a><a name="p10770205413314"></a>readyReplicas</p>
</td>
<td class="cellrowborder" valign="top" width="15.828417158284172%" headers="mcps1.2.5.1.2 "><p id="p11770154173115"><a name="p11770154173115"></a><a name="p11770154173115"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.998100189981002%" headers="mcps1.2.5.1.3 "><p id="p13770145483112"><a name="p13770145483112"></a><a name="p13770145483112"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.795220477952206%" headers="mcps1.2.5.1.4 "><p id="p14770145414316"><a name="p14770145414316"></a><a name="p14770145414316"></a>Total number of ready pods targeted by this deployment</p>
</td>
</tr>
<tr id="row12271235143114"><td class="cellrowborder" valign="top" width="17.378262173782623%" headers="mcps1.2.5.1.1 "><p id="p4770115412311"><a name="p4770115412311"></a><a name="p4770115412311"></a>replicas</p>
</td>
<td class="cellrowborder" valign="top" width="15.828417158284172%" headers="mcps1.2.5.1.2 "><p id="p577112540319"><a name="p577112540319"></a><a name="p577112540319"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.998100189981002%" headers="mcps1.2.5.1.3 "><p id="p17771195414319"><a name="p17771195414319"></a><a name="p17771195414319"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.795220477952206%" headers="mcps1.2.5.1.4 "><p id="p8771185414313"><a name="p8771185414313"></a><a name="p8771185414313"></a>Total number of non-terminated pods targeted by this deployment (their labels match the selector).</p>
</td>
</tr>
<tr id="row22281835203110"><td class="cellrowborder" valign="top" width="17.378262173782623%" headers="mcps1.2.5.1.1 "><p id="p107718541314"><a name="p107718541314"></a><a name="p107718541314"></a>unavailableReplicas</p>
</td>
<td class="cellrowborder" valign="top" width="15.828417158284172%" headers="mcps1.2.5.1.2 "><p id="p2077110546313"><a name="p2077110546313"></a><a name="p2077110546313"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.998100189981002%" headers="mcps1.2.5.1.3 "><p id="p37711154163115"><a name="p37711154163115"></a><a name="p37711154163115"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.795220477952206%" headers="mcps1.2.5.1.4 "><p id="p6771115483111"><a name="p6771115483111"></a><a name="p6771115483111"></a>Total number of unavailable pods targeted by this deployment.</p>
</td>
</tr>
<tr id="row102281735193120"><td class="cellrowborder" valign="top" width="17.378262173782623%" headers="mcps1.2.5.1.1 "><p id="p10771175433111"><a name="p10771175433111"></a><a name="p10771175433111"></a>updatedReplicas</p>
</td>
<td class="cellrowborder" valign="top" width="15.828417158284172%" headers="mcps1.2.5.1.2 "><p id="p1777155423110"><a name="p1777155423110"></a><a name="p1777155423110"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.998100189981002%" headers="mcps1.2.5.1.3 "><p id="p277185413115"><a name="p277185413115"></a><a name="p277185413115"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.795220477952206%" headers="mcps1.2.5.1.4 "><p id="p10771105413317"><a name="p10771105413317"></a><a name="p10771105413317"></a>Total number of non-terminated pods targeted by this deployment that have the desired template spec.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  rollbackTo字段数据结构说明

<a name="table38158357321"></a>
<table><thead align="left"><tr id="row19816735143214"><th class="cellrowborder" valign="top" width="17.078292170782923%" id="mcps1.2.5.1.1"><p id="p237555920814"><a name="p237555920814"></a><a name="p237555920814"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.258374162583742%" id="mcps1.2.5.1.2"><p id="p338415916810"><a name="p338415916810"></a><a name="p338415916810"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.95810418958104%" id="mcps1.2.5.1.3"><p id="p93912591082"><a name="p93912591082"></a><a name="p93912591082"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.7052294770523%" id="mcps1.2.5.1.4"><p id="p1400185912814"><a name="p1400185912814"></a><a name="p1400185912814"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1181643511323"><td class="cellrowborder" valign="top" width="17.078292170782923%" headers="mcps1.2.5.1.1 "><p id="p714245073218"><a name="p714245073218"></a><a name="p714245073218"></a>revision</p>
</td>
<td class="cellrowborder" valign="top" width="16.258374162583742%" headers="mcps1.2.5.1.2 "><p id="p2014218504328"><a name="p2014218504328"></a><a name="p2014218504328"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.95810418958104%" headers="mcps1.2.5.1.3 "><p id="p714216500323"><a name="p714216500323"></a><a name="p714216500323"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.7052294770523%" headers="mcps1.2.5.1.4 "><p id="p81425509322"><a name="p81425509322"></a><a name="p81425509322"></a>The revision to rollback to. If set to 0, rollback to the last revision.</p>
</td>
</tr>
</tbody>
</table>

**表 6**  selector字段数据结构说明

<a name="table5344134293516"></a>
<table><thead align="left"><tr id="row534520429359"><th class="cellrowborder" valign="top" width="17.071707170717072%" id="mcps1.2.5.1.1"><p id="p719318520913"><a name="p719318520913"></a><a name="p719318520913"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.2016201620162%" id="mcps1.2.5.1.2"><p id="p172011251691"><a name="p172011251691"></a><a name="p172011251691"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.801880188018803%" id="mcps1.2.5.1.3"><p id="p4212351298"><a name="p4212351298"></a><a name="p4212351298"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.92479247924793%" id="mcps1.2.5.1.4"><p id="p5221851899"><a name="p5221851899"></a><a name="p5221851899"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6345184212356"><td class="cellrowborder" valign="top" width="17.071707170717072%" headers="mcps1.2.5.1.1 "><p id="p944819019361"><a name="p944819019361"></a><a name="p944819019361"></a>matchExpressions</p>
</td>
<td class="cellrowborder" valign="top" width="16.2016201620162%" headers="mcps1.2.5.1.2 "><p id="p1144815011368"><a name="p1144815011368"></a><a name="p1144815011368"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.801880188018803%" headers="mcps1.2.5.1.3 "><p id="p1744810113613"><a name="p1744810113613"></a><a name="p1744810113613"></a><a href="#table175828716396">matchExpressions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="47.92479247924793%" headers="mcps1.2.5.1.4 "><p id="p744813073619"><a name="p744813073619"></a><a name="p744813073619"></a>matchExpressions is a list of label selector requirements. The requirements are ANDed.</p>
</td>
</tr>
<tr id="row3345164233517"><td class="cellrowborder" valign="top" width="17.071707170717072%" headers="mcps1.2.5.1.1 "><p id="p194481063618"><a name="p194481063618"></a><a name="p194481063618"></a>matchLabels</p>
</td>
<td class="cellrowborder" valign="top" width="16.2016201620162%" headers="mcps1.2.5.1.2 "><p id="p184481017368"><a name="p184481017368"></a><a name="p184481017368"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.801880188018803%" headers="mcps1.2.5.1.3 "><p id="p2044820153610"><a name="p2044820153610"></a><a name="p2044820153610"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="47.92479247924793%" headers="mcps1.2.5.1.4 "><p id="p154481302365"><a name="p154481302365"></a><a name="p154481302365"></a>matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  strategy字段数据结构说明

<a name="table10348336183618"></a>
<table><thead align="left"><tr id="row1134893616361"><th class="cellrowborder" valign="top" width="17%" id="mcps1.2.5.1.1"><p id="p582213142912"><a name="p582213142912"></a><a name="p582213142912"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.2"><p id="p583310141595"><a name="p583310141595"></a><a name="p583310141595"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.5.1.3"><p id="p68451414897"><a name="p68451414897"></a><a name="p68451414897"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="48%" id="mcps1.2.5.1.4"><p id="p14859814891"><a name="p14859814891"></a><a name="p14859814891"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row934963683617"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p878476133714"><a name="p878476133714"></a><a name="p878476133714"></a>rollingUpdate</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p97843653716"><a name="p97843653716"></a><a name="p97843653716"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p19720175165913"><a name="p19720175165913"></a><a name="p19720175165913"></a><a href="#table890691614586">RollingUpateDeployment</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p17842616373"><a name="p17842616373"></a><a name="p17842616373"></a>Rolling update config params. Present only if DeploymentStrategyType = RollingUpdate.</p>
</td>
</tr>
<tr id="row2034916369362"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.5.1.1 "><p id="p20784965372"><a name="p20784965372"></a><a name="p20784965372"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p127848613719"><a name="p127848613719"></a><a name="p127848613719"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.3 "><p id="p778436123715"><a name="p778436123715"></a><a name="p778436123715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48%" headers="mcps1.2.5.1.4 "><p id="p37841653711"><a name="p37841653711"></a><a name="p37841653711"></a>Type of deployment. Can be "Recreate" or "RollingUpdate". Default is RollingUpdate.</p>
</td>
</tr>
</tbody>
</table>

**表 8**  conditions字段数据结构说明

<a name="table2173152418384"></a>
<table><thead align="left"><tr id="row2173224153814"><th class="cellrowborder" valign="top" width="17.23%" id="mcps1.2.5.1.1"><p id="p132092172915"><a name="p132092172915"></a><a name="p132092172915"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.959999999999999%" id="mcps1.2.5.1.2"><p id="p192215171194"><a name="p192215171194"></a><a name="p192215171194"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.3"><p id="p923313171796"><a name="p923313171796"></a><a name="p923313171796"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.64%" id="mcps1.2.5.1.4"><p id="p924521711912"><a name="p924521711912"></a><a name="p924521711912"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1317317240385"><td class="cellrowborder" valign="top" width="17.23%" headers="mcps1.2.5.1.1 "><p id="p164612382388"><a name="p164612382388"></a><a name="p164612382388"></a>lastTransitionTime</p>
</td>
<td class="cellrowborder" valign="top" width="15.959999999999999%" headers="mcps1.2.5.1.2 "><p id="p1464617388382"><a name="p1464617388382"></a><a name="p1464617388382"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.3 "><p id="p76461238143813"><a name="p76461238143813"></a><a name="p76461238143813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.64%" headers="mcps1.2.5.1.4 "><p id="p8646838173813"><a name="p8646838173813"></a><a name="p8646838173813"></a>Last time the condition transitioned from one status to another.</p>
</td>
</tr>
<tr id="row131740244384"><td class="cellrowborder" valign="top" width="17.23%" headers="mcps1.2.5.1.1 "><p id="p14646123819381"><a name="p14646123819381"></a><a name="p14646123819381"></a>lastUpdateTime</p>
</td>
<td class="cellrowborder" valign="top" width="15.959999999999999%" headers="mcps1.2.5.1.2 "><p id="p1564633813385"><a name="p1564633813385"></a><a name="p1564633813385"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.3 "><p id="p1864615387381"><a name="p1864615387381"></a><a name="p1864615387381"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.64%" headers="mcps1.2.5.1.4 "><p id="p12646173816383"><a name="p12646173816383"></a><a name="p12646173816383"></a>The last time this condition was updated.</p>
</td>
</tr>
<tr id="row13174124123814"><td class="cellrowborder" valign="top" width="17.23%" headers="mcps1.2.5.1.1 "><p id="p12646838133815"><a name="p12646838133815"></a><a name="p12646838133815"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="15.959999999999999%" headers="mcps1.2.5.1.2 "><p id="p11646163893819"><a name="p11646163893819"></a><a name="p11646163893819"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.3 "><p id="p2647173811388"><a name="p2647173811388"></a><a name="p2647173811388"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.64%" headers="mcps1.2.5.1.4 "><p id="p1064773843816"><a name="p1064773843816"></a><a name="p1064773843816"></a>A human readable message indicating details about the transition.</p>
</td>
</tr>
<tr id="row817492473812"><td class="cellrowborder" valign="top" width="17.23%" headers="mcps1.2.5.1.1 "><p id="p146471738113811"><a name="p146471738113811"></a><a name="p146471738113811"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="15.959999999999999%" headers="mcps1.2.5.1.2 "><p id="p156471038143813"><a name="p156471038143813"></a><a name="p156471038143813"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.3 "><p id="p5647103816385"><a name="p5647103816385"></a><a name="p5647103816385"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.64%" headers="mcps1.2.5.1.4 "><p id="p6647143815384"><a name="p6647143815384"></a><a name="p6647143815384"></a>The reason for the condition's last transition.</p>
</td>
</tr>
<tr id="row11747243386"><td class="cellrowborder" valign="top" width="17.23%" headers="mcps1.2.5.1.1 "><p id="p1064723833816"><a name="p1064723833816"></a><a name="p1064723833816"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="15.959999999999999%" headers="mcps1.2.5.1.2 "><p id="p3647113833811"><a name="p3647113833811"></a><a name="p3647113833811"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.3 "><p id="p20647638173812"><a name="p20647638173812"></a><a name="p20647638173812"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.64%" headers="mcps1.2.5.1.4 "><p id="p16471338163813"><a name="p16471338163813"></a><a name="p16471338163813"></a>Status of the condition, one of True, False, Unknown.</p>
</td>
</tr>
<tr id="row2174724103810"><td class="cellrowborder" valign="top" width="17.23%" headers="mcps1.2.5.1.1 "><p id="p6647638183810"><a name="p6647638183810"></a><a name="p6647638183810"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="15.959999999999999%" headers="mcps1.2.5.1.2 "><p id="p16647113814389"><a name="p16647113814389"></a><a name="p16647113814389"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.3 "><p id="p18647638153813"><a name="p18647638153813"></a><a name="p18647638153813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.64%" headers="mcps1.2.5.1.4 "><p id="p20647143817386"><a name="p20647143817386"></a><a name="p20647143817386"></a>Type of deployment condition.</p>
</td>
</tr>
</tbody>
</table>

**表 9**  matchExpressions字段数据结构说明

<a name="table175828716396"></a>
<table><thead align="left"><tr id="row75824713398"><th class="cellrowborder" valign="top" width="17.43%" id="mcps1.2.5.1.1"><p id="p1335920202096"><a name="p1335920202096"></a><a name="p1335920202096"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.93%" id="mcps1.2.5.1.2"><p id="p153690201997"><a name="p153690201997"></a><a name="p153690201997"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.12%" id="mcps1.2.5.1.3"><p id="p183818201399"><a name="p183818201399"></a><a name="p183818201399"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.52%" id="mcps1.2.5.1.4"><p id="p2390142012911"><a name="p2390142012911"></a><a name="p2390142012911"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row95827773910"><td class="cellrowborder" valign="top" width="17.43%" headers="mcps1.2.5.1.1 "><p id="p6676201723913"><a name="p6676201723913"></a><a name="p6676201723913"></a>key</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p18676181773911"><a name="p18676181773911"></a><a name="p18676181773911"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.12%" headers="mcps1.2.5.1.3 "><p id="p1567691743916"><a name="p1567691743916"></a><a name="p1567691743916"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.52%" headers="mcps1.2.5.1.4 "><p id="p7676101711397"><a name="p7676101711397"></a><a name="p7676101711397"></a>key is the label key that the selector applies to.</p>
</td>
</tr>
<tr id="row8582187133920"><td class="cellrowborder" valign="top" width="17.43%" headers="mcps1.2.5.1.1 "><p id="p19676191719393"><a name="p19676191719393"></a><a name="p19676191719393"></a>operator</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p14676117203913"><a name="p14676117203913"></a><a name="p14676117203913"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.12%" headers="mcps1.2.5.1.3 "><p id="p86761317183918"><a name="p86761317183918"></a><a name="p86761317183918"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="47.52%" headers="mcps1.2.5.1.4 "><p id="p5676171783913"><a name="p5676171783913"></a><a name="p5676171783913"></a>operator represents a key's relationship to a set of values. Valid operators ard In, NotIn, Exists and DoesNotExist.</p>
</td>
</tr>
<tr id="row1583197143917"><td class="cellrowborder" valign="top" width="17.43%" headers="mcps1.2.5.1.1 "><p id="p86765171392"><a name="p86765171392"></a><a name="p86765171392"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p1167671703912"><a name="p1167671703912"></a><a name="p1167671703912"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.12%" headers="mcps1.2.5.1.3 "><p id="p76764177390"><a name="p76764177390"></a><a name="p76764177390"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="47.52%" headers="mcps1.2.5.1.4 "><p id="p1567618173394"><a name="p1567618173394"></a><a name="p1567618173394"></a>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</p>
</td>
</tr>
</tbody>
</table>

**表 10**  RollingUpateDeployment字段数据结构说明

<a name="table890691614586"></a>
<table><thead align="left"><tr id="row1892421675817"><th class="cellrowborder" valign="top" width="17.43%" id="mcps1.2.5.1.1"><p id="p991719241897"><a name="p991719241897"></a><a name="p991719241897"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.93%" id="mcps1.2.5.1.2"><p id="p20924224396"><a name="p20924224396"></a><a name="p20924224396"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.12%" id="mcps1.2.5.1.3"><p id="p19934202412920"><a name="p19934202412920"></a><a name="p19934202412920"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="47.52%" id="mcps1.2.5.1.4"><p id="p4948102417917"><a name="p4948102417917"></a><a name="p4948102417917"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row694815168581"><td class="cellrowborder" valign="top" width="17.43%" headers="mcps1.2.5.1.1 "><p id="p4952181618587"><a name="p4952181618587"></a><a name="p4952181618587"></a>maxSurge</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p11955121645820"><a name="p11955121645820"></a><a name="p11955121645820"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.12%" headers="mcps1.2.5.1.3 "><p id="p1295919168584"><a name="p1295919168584"></a><a name="p1295919168584"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.52%" headers="mcps1.2.5.1.4 "><p id="p5963121610580"><a name="p5963121610580"></a><a name="p5963121610580"></a>The maximum number of pods that can be scheduled above the desired number of pods. Value can be an absolute number (ex: 5) or a percentage of desired pods (ex: 10%). This can not be 0 if MaxUnavailable is 0. Absolute number is calculated from percentage by rounding up. Defaults to 25%. Example: when this is set to 30%, the new RC can be scaled up immediately when the rolling update starts, such that the total number of old and new pods do not exceed 130% of desired pods. Once old pods have been killed, new RC can be scaled up further, ensuring that total number of pods running at any time during the update is atmost 130% of desired pods.</p>
</td>
</tr>
<tr id="row1496614166583"><td class="cellrowborder" valign="top" width="17.43%" headers="mcps1.2.5.1.1 "><p id="p1997013167589"><a name="p1997013167589"></a><a name="p1997013167589"></a>maxUnavailable</p>
</td>
<td class="cellrowborder" valign="top" width="15.93%" headers="mcps1.2.5.1.2 "><p id="p4975161635818"><a name="p4975161635818"></a><a name="p4975161635818"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.12%" headers="mcps1.2.5.1.3 "><p id="p497801645820"><a name="p497801645820"></a><a name="p497801645820"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="47.52%" headers="mcps1.2.5.1.4 "><p id="p66201122115917"><a name="p66201122115917"></a><a name="p66201122115917"></a>The maximum number of pods that can be unavailable during the update. Value can be an absolute number (ex: 5) or a percentage of desired pods (ex: 10%). Absolute number is calculated from percentage by rounding down. This can not be 0 if MaxSurge is 0. Defaults to 25%. Example: when this is set to 30%, the old RC can be scaled down to 70% of desired pods immediately when the rolling update starts. Once new pods are ready, old RC can be scaled down further, followed by scaling up the new RC, ensuring that the total number of pods available at all times during the update is at least 70% of desired pods.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
    "apiVersion": "apps/v1beta1",
    "kind": "Deployment",
    "metadata": {
        "labels": {
            "app": "deployment-test"
        },
        "name": "deployment-test"
    },
    "spec": {
        "replicas": 1,
        "selector": {
            "matchLabels": {
                "app": "deployment-test"
            }
        },
        "template": {
            "metadata": {
                "labels": {
                    "app": "deployment-test"
                }
            },
            "spec": {
                "containers": [
                    {
                        "image": "172.16.5.235:20202/test/nginx",
                        "imagePullPolicy": "IfNotPresent",
                        "name": "deployment-test"
                    }
                ],
                "imagePullSecrets": [{
                    "name": "default-secret"
                }]
            }
        }
    }
}
```

## 响应消息<a name="section1575712476123"></a>

**响应参数**：

响应参数如[表2](#table12862324102610)所示。

**响应示例：**

```
{
    "kind": "Deployment",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "name": "deployment-test",
        "namespace": "default",
        "selfLink": "/apis/apps/v1beta1/namespaces/default/deployments/deployment-test",
        "uid": "d079d1a0-fc1f-11e7-9c3c-fa163eb8ad1a",
        "resourceVersion": "485774",
        "generation": 1,
        "creationTimestamp": "2018-01-18T07:18:42Z",
        "labels": {
            "name": "deployment-test"
        },
        "enable": true
    },
    "spec": {
        "replicas": 1,
        "selector": {
            "matchLabels": {
                "name": "deployment-test"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "name": "deployment-test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "deployment-test",
                        "image": "172.16.5.235:20202/test/nginx",
                        "resources": {},
                        "terminationMessagePath": "/dev/termination-log",
                        "terminationMessagePolicy": "File",
                        "imagePullPolicy": "IfNotPresent"
                    }
                ],
                "restartPolicy": "Always",
                "terminationGracePeriodSeconds": 30,
                "dnsPolicy": "ClusterFirst",
                "securityContext": {},
                "imagePullSecrets": [
                    {
                        "name": "default-secret"
                    }
                ],
                "schedulerName": "default-scheduler"
            }
        },
        "strategy": {
            "type": "RollingUpdate",
            "rollingUpdate": {
                "maxUnavailable": "25%",
                "maxSurge": "25%"
            }
        },
        "revisionHistoryLimit": 2,
        "progressDeadlineSeconds": 600
    },
    "status": {}
}
```

## 状态码<a name="section16509142112516"></a>

[表11 状态码](#table6957182913514)描述API的状态码。

**表 11**  状态码

<a name="table6957182913514"></a>
<table><thead align="left"><tr id="row12961162965119"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p189627299518"><a name="p189627299518"></a><a name="p189627299518"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1596342917515"><a name="p1596342917515"></a><a name="p1596342917515"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15964122975119"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p09651299518"><a name="p09651299518"></a><a name="p09651299518"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18966142915518"><a name="p18966142915518"></a><a name="p18966142915518"></a>This operation succeeds, and a  Endpoint resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

