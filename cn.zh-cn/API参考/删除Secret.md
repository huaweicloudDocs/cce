# 删除Secret<a name="cce_02_0044"></a>

## 功能介绍<a name="s33443b62a3884400b29be7af1a63ce43"></a>

该API用于删除指定Namespace下的Secret对象。

## URI<a name="sb59375acc1994f429f8cabd5b1bf4b80"></a>

DELETE /api/v1/namespaces/\{namespace\}/secrets/\{name\}

[表1](#zh-cn_topic_0079615047_table8667044)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079615047_table8667044"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row41088586"><th class="cellrowborder" valign="top" width="17.481748174817483%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p39841133"><a name="zh-cn_topic_0079615047_p39841133"></a><a name="zh-cn_topic_0079615047_p39841133"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.21182118211821%" id="mcps1.2.4.1.2"><p id="p9546513203257"><a name="p9546513203257"></a><a name="p9546513203257"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="64.3064306430643%" id="mcps1.2.4.1.3"><p id="p35070093203257"><a name="p35070093203257"></a><a name="p35070093203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row50486336"><td class="cellrowborder" valign="top" width="17.481748174817483%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p62861417"><a name="zh-cn_topic_0079615047_p62861417"></a><a name="zh-cn_topic_0079615047_p62861417"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="18.21182118211821%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p58610051"><a name="zh-cn_topic_0079615047_p58610051"></a><a name="zh-cn_topic_0079615047_p58610051"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="64.3064306430643%" headers="mcps1.2.4.1.3 "><p id="p166752264459"><a name="p166752264459"></a><a name="p166752264459"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。可以任选其一使用：</p>
<a name="ul75828215461"></a><a name="ul75828215461"></a><ul id="ul75828215461"><li>用户自定义的namespace，使用前必须先<a href="创建Namespace.md">创建Namespace</a></li><li>系统自带的namespace：default或kube-system</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row45490280"><td class="cellrowborder" valign="top" width="17.481748174817483%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p60834034"><a name="zh-cn_topic_0079615047_p60834034"></a><a name="zh-cn_topic_0079615047_p60834034"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="18.21182118211821%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p28609704"><a name="zh-cn_topic_0079615047_p28609704"></a><a name="zh-cn_topic_0079615047_p28609704"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="64.3064306430643%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p35684724"><a name="zh-cn_topic_0079615047_p35684724"></a><a name="zh-cn_topic_0079615047_p35684724"></a><span id="ph787510237582"><a name="ph787510237582"></a><a name="ph787510237582"></a>指定删除的secret的名称</span></p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="see27f791d3ac4acfa5128d4b61126f2f"></a>

**请求参数：**

请求参数如[表2](#zh-cn_topic_0079615047_table10894532)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079615047_table10894532"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row27851360"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615047_p41367663"><a name="zh-cn_topic_0079615047_p41367663"></a><a name="zh-cn_topic_0079615047_p41367663"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.18%" id="mcps1.2.5.1.2"><p id="p11434212203257"><a name="p11434212203257"></a><a name="p11434212203257"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p53755986203257"><a name="p53755986203257"></a><a name="p53755986203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28%" id="mcps1.2.5.1.4"><p id="p59267649203257"><a name="p59267649203257"></a><a name="p59267649203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row33398680"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615047_p20938598"><a name="zh-cn_topic_0079615047_p20938598"></a><a name="zh-cn_topic_0079615047_p20938598"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615047_p18304888"><a name="zh-cn_topic_0079615047_p18304888"></a><a name="zh-cn_topic_0079615047_p18304888"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615047_p6300983"><a name="zh-cn_topic_0079615047_p6300983"></a><a name="zh-cn_topic_0079615047_p6300983"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615047_p30014175"><a name="zh-cn_topic_0079615047_p30014175"></a><a name="zh-cn_topic_0079615047_p30014175"></a><span id="ph3486163216592"><a name="ph3486163216592"></a><a name="ph3486163216592"></a>API类型，固定值</span> <span id="ph67530461539"><a name="ph67530461539"></a><a name="ph67530461539"></a>＂<strong id="b145971171807"><a name="b145971171807"></a><a name="b145971171807"></a>DeleteOptions</strong>＂</span><span id="ph54971620013"><a name="ph54971620013"></a><a name="ph54971620013"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row15229100"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615047_p25597569"><a name="zh-cn_topic_0079615047_p25597569"></a><a name="zh-cn_topic_0079615047_p25597569"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615047_p60137223"><a name="zh-cn_topic_0079615047_p60137223"></a><a name="zh-cn_topic_0079615047_p60137223"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615047_p39276901"><a name="zh-cn_topic_0079615047_p39276901"></a><a name="zh-cn_topic_0079615047_p39276901"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615047_p44485484"><a name="zh-cn_topic_0079615047_p44485484"></a><a name="zh-cn_topic_0079615047_p44485484"></a><span id="ph12159122911015"><a name="ph12159122911015"></a><a name="ph12159122911015"></a>API版本，固定值</span> <span id="ph18254116012"><a name="ph18254116012"></a><a name="ph18254116012"></a>＂</span><strong id="zh-cn_topic_0079615047_b64825036"><a name="zh-cn_topic_0079615047_b64825036"></a><a name="zh-cn_topic_0079615047_b64825036"></a>v1<span id="ph179884431303"><a name="ph179884431303"></a><a name="ph179884431303"></a>＂</span></strong><span id="ph490911474016"><a name="ph490911474016"></a><a name="ph490911474016"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row46554414"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615047_p12811205"><a name="zh-cn_topic_0079615047_p12811205"></a><a name="zh-cn_topic_0079615047_p12811205"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615047_p31074713"><a name="zh-cn_topic_0079615047_p31074713"></a><a name="zh-cn_topic_0079615047_p31074713"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615047_p34023825"><a name="zh-cn_topic_0079615047_p34023825"></a><a name="zh-cn_topic_0079615047_p34023825"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615047_p4466454"><a name="zh-cn_topic_0079615047_p4466454"></a><a name="zh-cn_topic_0079615047_p4466454"></a><span id="ph17552131828"><a name="ph17552131828"></a><a name="ph17552131828"></a>该参数设置多少秒后删除该资源对象，必须是非负整数，设置为0表示立即删除</span><span id="ph558414556314"><a name="ph558414556314"></a><a name="ph558414556314"></a>。</span></p>
</td>
</tr>
<tr id="r5127218248e44810aef8009970b099fe"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="af2819716cf77473687ccab24616a578e"><a name="af2819716cf77473687ccab24616a578e"></a><a name="af2819716cf77473687ccab24616a578e"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="a641ed44081304841a5fd30190451fa21"><a name="a641ed44081304841a5fd30190451fa21"></a><a name="a641ed44081304841a5fd30190451fa21"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a38577330aabe498982d7e5570c56ca61"><a name="a38577330aabe498982d7e5570c56ca61"></a><a name="a38577330aabe498982d7e5570c56ca61"></a><a href="#t3a3f9a21f2254ea1a37ab173af770d4b">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="add861d80e28b4c3abeb4aaba2bc1656e"><a name="add861d80e28b4c3abeb4aaba2bc1656e"></a><a name="add861d80e28b4c3abeb4aaba2bc1656e"></a><span id="ph19118164713414"><a name="ph19118164713414"></a><a name="ph19118164713414"></a>该参数设置必须在删除执行前完成的项，如果不能完成则会返回409冲突的状态码。</span></p>
</td>
</tr>
<tr id="r280ac76ab36f441a9340fd44c7c18eca"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a0bf8df19415f4b5bacf092be129b8cdd"><a name="a0bf8df19415f4b5bacf092be129b8cdd"></a><a name="a0bf8df19415f4b5bacf092be129b8cdd"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.18%" headers="mcps1.2.5.1.2 "><p id="ad17b008e7916427d97b66618d77c9284"><a name="ad17b008e7916427d97b66618d77c9284"></a><a name="ad17b008e7916427d97b66618d77c9284"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a44d8e6006792468ab7322ab1cfa791ef"><a name="a44d8e6006792468ab7322ab1cfa791ef"></a><a name="a44d8e6006792468ab7322ab1cfa791ef"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a81268fbf98a84f07a0a4492319b5b36a"><a name="a81268fbf98a84f07a0a4492319b5b36a"></a><a name="a81268fbf98a84f07a0a4492319b5b36a"></a><span id="ph12505131493910"><a name="ph12505131493910"></a><a name="ph12505131493910"></a>该参数表示依赖的</span><span id="ph13896125518393"><a name="ph13896125518393"></a><a name="ph13896125518393"></a>资源对象是否被设置为孤儿（orphan），ture表示设置，false则不设置。默认为false。</span></p>
</td>
</tr>
</tbody>
</table>

**表 3**  preconditions字段数据结构说明

<a name="t3a3f9a21f2254ea1a37ab173af770d4b"></a>
<table><thead align="left"><tr id="rdf23a66a2e97487dadafe65b50690fd6"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="aceada35a29e04de7b4366e0429c828e7"><a name="aceada35a29e04de7b4366e0429c828e7"></a><a name="aceada35a29e04de7b4366e0429c828e7"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p6896990203257"><a name="p6896990203257"></a><a name="p6896990203257"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p21785280203257"><a name="p21785280203257"></a><a name="p21785280203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p19777271203257"><a name="p19777271203257"></a><a name="p19777271203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r440e4627ef3f46bcb2819e8054930c91"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="ade720eb2e553427598834fad82739f47"><a name="ade720eb2e553427598834fad82739f47"></a><a name="ade720eb2e553427598834fad82739f47"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a7afebb3677e84e6d9567a2e465b8c2d9"><a name="a7afebb3677e84e6d9567a2e465b8c2d9"></a><a name="a7afebb3677e84e6d9567a2e465b8c2d9"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a4623a62cb6324c1c900e9a92971f774d"><a name="a4623a62cb6324c1c900e9a92971f774d"></a><a name="a4623a62cb6324c1c900e9a92971f774d"></a>types.UID</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="a065c010ac9d74729897e30c457cae2bd"><a name="a065c010ac9d74729897e30c457cae2bd"></a><a name="a065c010ac9d74729897e30c457cae2bd"></a><span id="ph297004517482"><a name="ph297004517482"></a><a name="ph297004517482"></a>指定的UID</span><span id="ph1281317349490"><a name="ph1281317349490"></a><a name="ph1281317349490"></a>。</span></p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{ 
   "kind": "DeleteOptions", 
   "apiVersion": "v1", 
   "gracePeriodSeconds": 10 
 }
```

## 响应消息<a name="s00e4933458e84b218d5369e1c39bfae6"></a>

**响应参数：**

响应参数如[表4](#zh-cn_topic_0079615047_table30941925)所示。

**表 4**  参数描述

<a name="zh-cn_topic_0079615047_table30941925"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row37328119"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p3678790"><a name="zh-cn_topic_0079615047_p3678790"></a><a name="zh-cn_topic_0079615047_p3678790"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p56650888203257"><a name="p56650888203257"></a><a name="p56650888203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p25319233203257"><a name="p25319233203257"></a><a name="p25319233203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row44834872"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p7745977"><a name="zh-cn_topic_0079615047_p7745977"></a><a name="zh-cn_topic_0079615047_p7745977"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p23444395"><a name="zh-cn_topic_0079615047_p23444395"></a><a name="zh-cn_topic_0079615047_p23444395"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p19947829"><a name="zh-cn_topic_0079615047_p19947829"></a><a name="zh-cn_topic_0079615047_p19947829"></a><span id="ph278219711497"><a name="ph278219711497"></a><a name="ph278219711497"></a>API类型</span><span id="ph14610336154920"><a name="ph14610336154920"></a><a name="ph14610336154920"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row45312739"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p46453253"><a name="zh-cn_topic_0079615047_p46453253"></a><a name="zh-cn_topic_0079615047_p46453253"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p4617172"><a name="zh-cn_topic_0079615047_p4617172"></a><a name="zh-cn_topic_0079615047_p4617172"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p38446647"><a name="zh-cn_topic_0079615047_p38446647"></a><a name="zh-cn_topic_0079615047_p38446647"></a><span id="ph20688181413493"><a name="ph20688181413493"></a><a name="ph20688181413493"></a>API版本</span><span id="ph141513814499"><a name="ph141513814499"></a><a name="ph141513814499"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row10475508"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p43209809"><a name="zh-cn_topic_0079615047_p43209809"></a><a name="zh-cn_topic_0079615047_p43209809"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p10333622"><a name="zh-cn_topic_0079615047_p10333622"></a><a name="zh-cn_topic_0079615047_p10333622"></a><a href="#zh-cn_topic_0079615047_table10041872">表5</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p31717068"><a name="zh-cn_topic_0079615047_p31717068"></a><a name="zh-cn_topic_0079615047_p31717068"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row17018161"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p36293778"><a name="zh-cn_topic_0079615047_p36293778"></a><a name="zh-cn_topic_0079615047_p36293778"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p54114937"><a name="zh-cn_topic_0079615047_p54114937"></a><a name="zh-cn_topic_0079615047_p54114937"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p9503344503"><a name="p9503344503"></a><a name="p9503344503"></a>表示操作的状态，可以为：</p>
<a name="ul534113018509"></a><a name="ul534113018509"></a><ul id="ul534113018509"><li>"Success"：成功</li><li>"Failure"：失败</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row56885929"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p44357513"><a name="zh-cn_topic_0079615047_p44357513"></a><a name="zh-cn_topic_0079615047_p44357513"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p36188810"><a name="zh-cn_topic_0079615047_p36188810"></a><a name="zh-cn_topic_0079615047_p36188810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p45612499"><a name="zh-cn_topic_0079615047_p45612499"></a><a name="zh-cn_topic_0079615047_p45612499"></a><span id="ph1637745165210"><a name="ph1637745165210"></a><a name="ph1637745165210"></a>具体描述</span><span id="ph530016229519"><a name="ph530016229519"></a><a name="ph530016229519"></a>该操作的状态</span><span id="ph10489624205317"><a name="ph10489624205317"></a><a name="ph10489624205317"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row7859315"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p32624764"><a name="zh-cn_topic_0079615047_p32624764"></a><a name="zh-cn_topic_0079615047_p32624764"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p25360226"><a name="zh-cn_topic_0079615047_p25360226"></a><a name="zh-cn_topic_0079615047_p25360226"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p40912396"><a name="zh-cn_topic_0079615047_p40912396"></a><a name="zh-cn_topic_0079615047_p40912396"></a><span id="ph9412234125312"><a name="ph9412234125312"></a><a name="ph9412234125312"></a>具体描述操作失败的原因，如果该字段为空，表示没有可用信息。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row32667246"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p28801274"><a name="zh-cn_topic_0079615047_p28801274"></a><a name="zh-cn_topic_0079615047_p28801274"></a>details</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p51201854"><a name="zh-cn_topic_0079615047_p51201854"></a><a name="zh-cn_topic_0079615047_p51201854"></a><a href="#zh-cn_topic_0079615047_table23267991">表6</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p53709539"><a name="zh-cn_topic_0079615047_p53709539"></a><a name="zh-cn_topic_0079615047_p53709539"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row13623809"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p29786778"><a name="zh-cn_topic_0079615047_p29786778"></a><a name="zh-cn_topic_0079615047_p29786778"></a>code</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p63918823"><a name="zh-cn_topic_0079615047_p63918823"></a><a name="zh-cn_topic_0079615047_p63918823"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p10042193"><a name="zh-cn_topic_0079615047_p10042193"></a><a name="zh-cn_topic_0079615047_p10042193"></a><span id="ph108671583547"><a name="ph108671583547"></a><a name="ph108671583547"></a>表示操作的返回码</span><span id="ph1821161610565"><a name="ph1821161610565"></a><a name="ph1821161610565"></a>。</span></p>
</td>
</tr>
</tbody>
</table>

**表 5**  metadata字段数据结构说明

<a name="zh-cn_topic_0079615047_table10041872"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row4239285"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p7837765"><a name="zh-cn_topic_0079615047_p7837765"></a><a name="zh-cn_topic_0079615047_p7837765"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p16832548203257"><a name="p16832548203257"></a><a name="p16832548203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p21259186203257"><a name="p21259186203257"></a><a name="p21259186203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row63891552"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p7833234"><a name="zh-cn_topic_0079615047_p7833234"></a><a name="zh-cn_topic_0079615047_p7833234"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p30512241"><a name="zh-cn_topic_0079615047_p30512241"></a><a name="zh-cn_topic_0079615047_p30512241"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p14471838"><a name="zh-cn_topic_0079614900_p14471838"></a><a name="zh-cn_topic_0079614900_p14471838"></a>SelfLink 是该资源对象的 URL。系统内部使用，只读项。</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row30390025"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p45672950"><a name="zh-cn_topic_0079615047_p45672950"></a><a name="zh-cn_topic_0079615047_p45672950"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p8521451"><a name="zh-cn_topic_0079615047_p8521451"></a><a name="zh-cn_topic_0079615047_p8521451"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614900_p1905570"><a name="zh-cn_topic_0079614900_p1905570"></a><a name="zh-cn_topic_0079614900_p1905570"></a>ResourceVersion表示该资源对象内部版本，可以用来优化并发性能和监视资源变化，系统内部使用，只读项。</p>
</td>
</tr>
</tbody>
</table>

**表 6**  details字段数据结构说明

<a name="zh-cn_topic_0079615047_table23267991"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row467118"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p37836574"><a name="zh-cn_topic_0079615047_p37836574"></a><a name="zh-cn_topic_0079615047_p37836574"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p32915338203257"><a name="p32915338203257"></a><a name="p32915338203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p48896756203257"><a name="p48896756203257"></a><a name="p48896756203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row11018834"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p20110389"><a name="zh-cn_topic_0079615047_p20110389"></a><a name="zh-cn_topic_0079615047_p20110389"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p18328792"><a name="zh-cn_topic_0079615047_p18328792"></a><a name="zh-cn_topic_0079615047_p18328792"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p8237155"><a name="zh-cn_topic_0079615047_p8237155"></a><a name="zh-cn_topic_0079615047_p8237155"></a><span id="ph770054917410"><a name="ph770054917410"></a><a name="ph770054917410"></a>与StatusReason关联的资源</span><span id="ph104962551348"><a name="ph104962551348"></a><a name="ph104962551348"></a>名称。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row7025535"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p32197499"><a name="zh-cn_topic_0079615047_p32197499"></a><a name="zh-cn_topic_0079615047_p32197499"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p57860594"><a name="zh-cn_topic_0079615047_p57860594"></a><a name="zh-cn_topic_0079615047_p57860594"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p56196558"><a name="zh-cn_topic_0079615047_p56196558"></a><a name="zh-cn_topic_0079615047_p56196558"></a><span id="ph178911178515"><a name="ph178911178515"></a><a name="ph178911178515"></a>与StatusReason关联的资源</span><span id="ph8292172415519"><a name="ph8292172415519"></a><a name="ph8292172415519"></a>类型</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row36006982"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p30884404"><a name="zh-cn_topic_0079615047_p30884404"></a><a name="zh-cn_topic_0079615047_p30884404"></a>causes</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p18608762"><a name="zh-cn_topic_0079615047_p18608762"></a><a name="zh-cn_topic_0079615047_p18608762"></a><a href="#zh-cn_topic_0079615047_table8085329">表7</a></p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p30914753"><a name="zh-cn_topic_0079615047_p30914753"></a><a name="zh-cn_topic_0079615047_p30914753"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row9797324"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p55385783"><a name="zh-cn_topic_0079615047_p55385783"></a><a name="zh-cn_topic_0079615047_p55385783"></a>retryAfterSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p57063414"><a name="zh-cn_topic_0079615047_p57063414"></a><a name="zh-cn_topic_0079615047_p57063414"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p58733810"><a name="zh-cn_topic_0079615047_p58733810"></a><a name="zh-cn_topic_0079615047_p58733810"></a><span id="ph126371048157"><a name="ph126371048157"></a><a name="ph126371048157"></a>该参数设置删除重试的时间，单位为秒。</span></p>
</td>
</tr>
<tr id="r0d1d58b07bd040818c28c28ba70ade83"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a37b4a7b3504040c8b24983f9f034d212"><a name="a37b4a7b3504040c8b24983f9f034d212"></a><a name="a37b4a7b3504040c8b24983f9f034d212"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p198842574110"><a name="zh-cn_topic_0079615047_p198842574110"></a><a name="zh-cn_topic_0079615047_p198842574110"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="aa4615c1a43234eb19bfd9f0ad4658d5e"><a name="aa4615c1a43234eb19bfd9f0ad4658d5e"></a><a name="aa4615c1a43234eb19bfd9f0ad4658d5e"></a><span id="ph618635111616"><a name="ph618635111616"></a><a name="ph618635111616"></a>资源对象的UID</span></p>
</td>
</tr>
<tr id="rc0e343be5f114feeaa79e099c6662dbe"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p199461439422"><a name="zh-cn_topic_0079615047_p199461439422"></a><a name="zh-cn_topic_0079615047_p199461439422"></a>group</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p094619316422"><a name="zh-cn_topic_0079615047_p094619316422"></a><a name="zh-cn_topic_0079615047_p094619316422"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p143112091679"><a name="p143112091679"></a><a name="p143112091679"></a>与StatusReason关联的组属性。</p>
</td>
</tr>
</tbody>
</table>

**表 7**  causes字段数据结构说明

<a name="zh-cn_topic_0079615047_table8085329"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row2488285"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079615047_p224543"><a name="zh-cn_topic_0079615047_p224543"></a><a name="zh-cn_topic_0079615047_p224543"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p40819061203257"><a name="p40819061203257"></a><a name="p40819061203257"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p18009654203257"><a name="p18009654203257"></a><a name="p18009654203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row12212497"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p49688181"><a name="zh-cn_topic_0079615047_p49688181"></a><a name="zh-cn_topic_0079615047_p49688181"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p65319718"><a name="zh-cn_topic_0079615047_p65319718"></a><a name="zh-cn_topic_0079615047_p65319718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p56405771"><a name="zh-cn_topic_0079615047_p56405771"></a><a name="zh-cn_topic_0079615047_p56405771"></a><span id="ph17921481811"><a name="ph17921481811"></a><a name="ph17921481811"></a>具体描述错误的原因，如果该字段为空，表示没有可用信息。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row37889892"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p49182451"><a name="zh-cn_topic_0079615047_p49182451"></a><a name="zh-cn_topic_0079615047_p49182451"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p24355627"><a name="zh-cn_topic_0079615047_p24355627"></a><a name="zh-cn_topic_0079615047_p24355627"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079615047_p26648755"><a name="zh-cn_topic_0079615047_p26648755"></a><a name="zh-cn_topic_0079615047_p26648755"></a><span id="ph147844411812"><a name="ph147844411812"></a><a name="ph147844411812"></a>具体描述错误的原因，</span><span id="ph13301114105"><a name="ph13301114105"></a><a name="ph13301114105"></a>可读性更好。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079615047_row38512204"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615047_p32480848"><a name="zh-cn_topic_0079615047_p32480848"></a><a name="zh-cn_topic_0079615047_p32480848"></a>field</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615047_p13703032"><a name="zh-cn_topic_0079615047_p13703032"></a><a name="zh-cn_topic_0079615047_p13703032"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="p04861744111015"><a name="p04861744111015"></a><a name="p04861744111015"></a>表示导致此错误的资源对象数组，数组成员是序列化的JSON格式。数组索引从0开始，由于某个资源对象可能有多个错误，所以在该数组里可能多次出现该资源对象。</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{ 
   "kind": "Status", 
   "apiVersion": "v1", 
   "metadata": {}, 
   "status": "Success", 
   "code": 200 
 }
```

## 状态码<a name="s25ccd5e4fb8949dd9dee7a70d15c0810"></a>

[表8](#zh-cn_topic_0079615047_table5659105)描述API的状态码。

**表 8**  状态码

<a name="zh-cn_topic_0079615047_table5659105"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615047_row40139983"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p36672758203257"><a name="p36672758203257"></a><a name="p36672758203257"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p17703441203257"><a name="p17703441203257"></a><a name="p17703441203257"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615047_row4146549"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079615047_p326206"><a name="zh-cn_topic_0079615047_p326206"></a><a name="zh-cn_topic_0079615047_p326206"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079615047_p26422695"><a name="zh-cn_topic_0079615047_p26422695"></a><a name="zh-cn_topic_0079615047_p26422695"></a><span id="ph1196922160"><a name="ph1196922160"></a><a name="ph1196922160"></a>删除secret资源对象成功。</span></p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

