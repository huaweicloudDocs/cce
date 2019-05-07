# 创建Secret<a name="cce_02_0043"></a>

## 功能介绍<a name="s4e0a1c9701464caaa087bfb241e8faeb"></a>

该API用于创建Secret资源类型，Secret解决了密码、token、密钥等敏感数据的配置问题，而不需要把这些敏感数据暴露到镜像或者Pod Spec中。Secret可以以Volume或者环境变量的方式使用。

Secret有主要有四种类型：

-   kubernetes.io/service-account-token ：用来访问Kubernetes API，由Kubernetes自动创建，并且会自动挂载到Pod的/run/secrets/kubernetes.io/serviceaccount目录中；
-   opaque ：base64编码格式的Secret，用来存储密码、密钥等；
-   cfe/secure-opaque：华为云提供的secret格式，数据经过PSM加密后存储，可以有效保障用户数据安全；
-   kubernetes.io/dockerconfigjson ：用来存储私有docker registry的认证信息。

## URI<a name="s3cae00f6e7914695ba88e44aa7a2a633"></a>

POST /api/v1/namespaces/\{namespace\}/secrets

[表1](#zh-cn_topic_0079614900_table43659541)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614900_table43659541"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row65791910"><th class="cellrowborder" valign="top" width="19.21192119211921%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614900_p27544487"><a name="zh-cn_topic_0079614900_p27544487"></a><a name="zh-cn_topic_0079614900_p27544487"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.441444144414442%" id="mcps1.2.4.1.2"><p id="p4973534205955"><a name="p4973534205955"></a><a name="p4973534205955"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="66.34663466346635%" id="mcps1.2.4.1.3"><p id="p203075205955"><a name="p203075205955"></a><a name="p203075205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row43820797"><td class="cellrowborder" valign="top" width="19.21192119211921%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614900_p59823639"><a name="zh-cn_topic_0079614900_p59823639"></a><a name="zh-cn_topic_0079614900_p59823639"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="14.441444144414442%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614900_p13876573"><a name="zh-cn_topic_0079614900_p13876573"></a><a name="zh-cn_topic_0079614900_p13876573"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.34663466346635%" headers="mcps1.2.4.1.3 "><p id="p166752264459"><a name="p166752264459"></a><a name="p166752264459"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。可以任选其一使用：</p>
<a name="ul75828215461"></a><a name="ul75828215461"></a><ul id="ul75828215461"><li>用户自定义的namespace，使用前必须先<a href="创建Namespace.md">创建Namespace</a></li><li>系统自带的namespace：default或kube-system</li></ul>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079614900_d0e9414"></a>

请求参数：

请求参数如[表2](#zh-cn_topic_0079614900_ref458786458)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079614900_ref458786458"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row23223189"><th class="cellrowborder" valign="top" width="22.189999999999998%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614900_p2030132"><a name="zh-cn_topic_0079614900_p2030132"></a><a name="zh-cn_topic_0079614900_p2030132"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.849999999999998%" id="mcps1.2.5.1.2"><p id="p1331399205955"><a name="p1331399205955"></a><a name="p1331399205955"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.3%" id="mcps1.2.5.1.3"><p id="p40734494205955"><a name="p40734494205955"></a><a name="p40734494205955"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.660000000000004%" id="mcps1.2.5.1.4"><p id="p11159709205955"><a name="p11159709205955"></a><a name="p11159709205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row35800477"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p14157563"><a name="zh-cn_topic_0079614900_p14157563"></a><a name="zh-cn_topic_0079614900_p14157563"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p5911965"><a name="zh-cn_topic_0079614900_p5911965"></a><a name="zh-cn_topic_0079614900_p5911965"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p9107180"><a name="zh-cn_topic_0079614900_p9107180"></a><a name="zh-cn_topic_0079614900_p9107180"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p66592975"><a name="zh-cn_topic_0079614900_p66592975"></a><a name="zh-cn_topic_0079614900_p66592975"></a><span id="ph1174310195614"><a name="ph1174310195614"></a><a name="ph1174310195614"></a>API类型，固定值</span><span id="ph67530461539"><a name="ph67530461539"></a><a name="ph67530461539"></a>＂Secret＂</span><span id="ph168222575562"><a name="ph168222575562"></a><a name="ph168222575562"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row26570537"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p4729870"><a name="zh-cn_topic_0079614900_p4729870"></a><a name="zh-cn_topic_0079614900_p4729870"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p47575204"><a name="zh-cn_topic_0079614900_p47575204"></a><a name="zh-cn_topic_0079614900_p47575204"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p28386322"><a name="zh-cn_topic_0079614900_p28386322"></a><a name="zh-cn_topic_0079614900_p28386322"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p17590785"><a name="zh-cn_topic_0079614900_p17590785"></a><a name="zh-cn_topic_0079614900_p17590785"></a><span id="ph6998234195713"><a name="ph6998234195713"></a><a name="ph6998234195713"></a>API版本，固定值＂v1＂</span><span id="ph61361357115617"><a name="ph61361357115617"></a><a name="ph61361357115617"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row5889891"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p7319178"><a name="zh-cn_topic_0079614900_p7319178"></a><a name="zh-cn_topic_0079614900_p7319178"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p55982574"><a name="zh-cn_topic_0079614900_p55982574"></a><a name="zh-cn_topic_0079614900_p55982574"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p38294646"><a name="zh-cn_topic_0079614900_p38294646"></a><a name="zh-cn_topic_0079614900_p38294646"></a><a href="#zh-cn_topic_0079614900_table57391552">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p14858635"><a name="zh-cn_topic_0079614900_p14858635"></a><a name="zh-cn_topic_0079614900_p14858635"></a>-</p>
</td>
</tr>
<tr id="r4da44c1005dc4397ab1b1ccf464484c7"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="a0409150518b342c1aa173b44cb238e6a"><a name="a0409150518b342c1aa173b44cb238e6a"></a><a name="a0409150518b342c1aa173b44cb238e6a"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="aa1c1da83ee97430f9257ae829978892e"><a name="aa1c1da83ee97430f9257ae829978892e"></a><a name="aa1c1da83ee97430f9257ae829978892e"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="a146c165b312544a28557e9eeb74b2edc"><a name="a146c165b312544a28557e9eeb74b2edc"></a><a name="a146c165b312544a28557e9eeb74b2edc"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="p5481144341211"><a name="p5481144341211"></a><a name="p5481144341211"></a>Data 表示具体的secret数据，格式为Key/Value对。</p>
<a name="ul119491847111216"></a><a name="ul119491847111216"></a><ul id="ul119491847111216"><li>Key可以包含字符，数字，连字符，下划线和点</li><li>Value是对原数据进行base64加密后的字符串</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row66618853"><td class="cellrowborder" valign="top" width="22.189999999999998%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p27418040"><a name="zh-cn_topic_0079614900_p27418040"></a><a name="zh-cn_topic_0079614900_p27418040"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="17.849999999999998%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p6268747"><a name="zh-cn_topic_0079614900_p6268747"></a><a name="zh-cn_topic_0079614900_p6268747"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.3%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p38006470"><a name="zh-cn_topic_0079614900_p38006470"></a><a name="zh-cn_topic_0079614900_p38006470"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p57865062"><a name="zh-cn_topic_0079614900_p57865062"></a><a name="zh-cn_topic_0079614900_p57865062"></a><span id="ph11997117171517"><a name="ph11997117171517"></a><a name="ph11997117171517"></a>Secret类型，</span><span id="ph146000461236"><a name="ph146000461236"></a><a name="ph146000461236"></a>华为云kubernetes支持cfe/secure-opaque类型，</span><span id="ph165745293151"><a name="ph165745293151"></a><a name="ph165745293151"></a>原生kubernetes支持以下类型：</span></p>
<a name="zh-cn_topic_0079614900_ul51023510"></a><a name="zh-cn_topic_0079614900_ul51023510"></a><ul id="zh-cn_topic_0079614900_ul51023510"><li>kubernetes.io/service-account-token</li><li>kubernetes.io/.dockercfg</li><li>kubernetes.io/.dockerconfigjson</li><li>kubernetes.io/basic-auth</li><li>kubernetes.io/ssh-auth</li><li>kubernetes.io/tls</li><li>opaque</li></ul>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="zh-cn_topic_0079614900_table57391552"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row49758049"><th class="cellrowborder" valign="top" width="22.22222222222222%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614900_p3870157"><a name="zh-cn_topic_0079614900_p3870157"></a><a name="zh-cn_topic_0079614900_p3870157"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.18181818181818%" id="mcps1.2.5.1.2"><p id="p1711493205955"><a name="p1711493205955"></a><a name="p1711493205955"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.2020202020202%" id="mcps1.2.5.1.3"><p id="p4413239205955"><a name="p4413239205955"></a><a name="p4413239205955"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.39393939393939%" id="mcps1.2.5.1.4"><p id="p21928065205955"><a name="p21928065205955"></a><a name="p21928065205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row15135864"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p18045482"><a name="zh-cn_topic_0079614900_p18045482"></a><a name="zh-cn_topic_0079614900_p18045482"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p52397961"><a name="zh-cn_topic_0079614900_p52397961"></a><a name="zh-cn_topic_0079614900_p52397961"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p16376444"><a name="zh-cn_topic_0079614900_p16376444"></a><a name="zh-cn_topic_0079614900_p16376444"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p168024282424"><a name="zh-cn_topic_0079614900_p168024282424"></a><a name="zh-cn_topic_0079614900_p168024282424"></a><span id="ph11998113320290"><a name="ph11998113320290"></a><a name="ph11998113320290"></a>Secret名称，</span><span id="ph862513911341"><a name="ph862513911341"></a><a name="ph862513911341"></a>可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符，</span><span id="ph762911148347"><a name="ph762911148347"></a><a name="ph762911148347"></a>同一namespace下name不能重复。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row41055555"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p37165673"><a name="zh-cn_topic_0079614900_p37165673"></a><a name="zh-cn_topic_0079614900_p37165673"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p57629543"><a name="zh-cn_topic_0079614900_p57629543"></a><a name="zh-cn_topic_0079614900_p57629543"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p37481446"><a name="zh-cn_topic_0079614900_p37481446"></a><a name="zh-cn_topic_0079614900_p37481446"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p16098318"><a name="zh-cn_topic_0079614900_p16098318"></a><a name="zh-cn_topic_0079614900_p16098318"></a>GenerateName<span id="ph6891532185620"><a name="ph6891532185620"></a><a name="ph6891532185620"></a> 是一个可选项，表示名字的前缀，当Name字段为空时，会自动使用该前缀生成一个集群内唯一存在的Name。</span><span id="ph17533141584"><a name="ph17533141584"></a><a name="ph17533141584"></a>只有当Name字段为空时才需要配置generateName，generateName</span><span id="ph1077055145812"><a name="ph1077055145812"></a><a name="ph1077055145812"></a>可以包含小写字母、数字、连字符和点，开头和结尾必须是字母或数字，最长253个字符</span><span id="ph6119185045611"><a name="ph6119185045611"></a><a name="ph6119185045611"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row59647531"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p66720707"><a name="zh-cn_topic_0079614900_p66720707"></a><a name="zh-cn_topic_0079614900_p66720707"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p35668200"><a name="zh-cn_topic_0079614900_p35668200"></a><a name="zh-cn_topic_0079614900_p35668200"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p3443073"><a name="zh-cn_topic_0079614900_p3443073"></a><a name="zh-cn_topic_0079614900_p3443073"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="p18341134117277"><a name="p18341134117277"></a><a name="p18341134117277"></a>Namespace是对一组资源和对象的抽象集合，用来将系统内部的对象划分为不同的项目组或用户组。字符串必须满足正则表达式 [a-z0-9]([-a-z0-9]*[a-z0-9])?。可以任选其一使用：</p>
<a name="ul2786250175914"></a><a name="ul2786250175914"></a><ul id="ul2786250175914"><li>用户自定义的namespace，使用前必须先<a href="创建Namespace.md">创建Namespace</a></li><li>系统自带的namespace：default或kube-system</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row37296315"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p1102679"><a name="zh-cn_topic_0079614900_p1102679"></a><a name="zh-cn_topic_0079614900_p1102679"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p22208171"><a name="zh-cn_topic_0079614900_p22208171"></a><a name="zh-cn_topic_0079614900_p22208171"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p54031456"><a name="zh-cn_topic_0079614900_p54031456"></a><a name="zh-cn_topic_0079614900_p54031456"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p14471838"><a name="zh-cn_topic_0079614900_p14471838"></a><a name="zh-cn_topic_0079614900_p14471838"></a>SelfLink <span id="ph2354174512018"><a name="ph2354174512018"></a><a name="ph2354174512018"></a>是该资源对象的</span> URL<span id="ph736813855616"><a name="ph736813855616"></a><a name="ph736813855616"></a>。</span><span id="ph1229110121714"><a name="ph1229110121714"></a><a name="ph1229110121714"></a> </span><span id="ph51072115113"><a name="ph51072115113"></a><a name="ph51072115113"></a>系统内部使用，只读项。</span>.</p>
<div class="note" id="zh-cn_topic_0079614900_note63137679"><a name="zh-cn_topic_0079614900_note63137679"></a><a name="zh-cn_topic_0079614900_note63137679"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079614900_p31368204"><a name="zh-cn_topic_0079614900_p31368204"></a><a name="zh-cn_topic_0079614900_p31368204"></a><span id="ph201661852015"><a name="ph201661852015"></a><a name="ph201661852015"></a>该参数是系统自动生成的，不能手动配置，否则会导致接口调用失败</span><span id="ph2854151310299"><a name="ph2854151310299"></a><a name="ph2854151310299"></a>。</span></p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row13878380"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p50407014"><a name="zh-cn_topic_0079614900_p50407014"></a><a name="zh-cn_topic_0079614900_p50407014"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p56436324"><a name="zh-cn_topic_0079614900_p56436324"></a><a name="zh-cn_topic_0079614900_p56436324"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p7939535"><a name="zh-cn_topic_0079614900_p7939535"></a><a name="zh-cn_topic_0079614900_p7939535"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p39122574"><a name="zh-cn_topic_0079614900_p39122574"></a><a name="zh-cn_topic_0079614900_p39122574"></a>UID <span id="ph1095010917420"><a name="ph1095010917420"></a><a name="ph1095010917420"></a>是赋值给该资源对象全局唯一的ID</span><span id="ph18506056113314"><a name="ph18506056113314"></a><a name="ph18506056113314"></a>。</span> <span id="ph1749880154"><a name="ph1749880154"></a><a name="ph1749880154"></a>系统自动生成以及提供系统内部使用，只读项。</span></p>
<div class="note" id="zh-cn_topic_0079614900_note16558849"><a name="zh-cn_topic_0079614900_note16558849"></a><a name="zh-cn_topic_0079614900_note16558849"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1843711491951"><a name="p1843711491951"></a><a name="p1843711491951"></a>该参数是系统自动生成的，不能手动配置，否则会导致接口调用失败。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row66198362"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p60467067"><a name="zh-cn_topic_0079614900_p60467067"></a><a name="zh-cn_topic_0079614900_p60467067"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p65994253"><a name="zh-cn_topic_0079614900_p65994253"></a><a name="zh-cn_topic_0079614900_p65994253"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p43934263"><a name="zh-cn_topic_0079614900_p43934263"></a><a name="zh-cn_topic_0079614900_p43934263"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p1905570"><a name="zh-cn_topic_0079614900_p1905570"></a><a name="zh-cn_topic_0079614900_p1905570"></a><span id="ph516213221259"><a name="ph516213221259"></a><a name="ph516213221259"></a>ResourceVersion表示该资源对象内部版本</span><span id="ph188361713112614"><a name="ph188361713112614"></a><a name="ph188361713112614"></a>，可以用来优化并发性能和监视资源变化，</span><span id="ph173071947202820"><a name="ph173071947202820"></a><a name="ph173071947202820"></a>系统内部使用，只读项</span><span id="ph577585316285"><a name="ph577585316285"></a><a name="ph577585316285"></a>。</span></p>
<div class="note" id="zh-cn_topic_0079614900_note17150135"><a name="zh-cn_topic_0079614900_note17150135"></a><a name="zh-cn_topic_0079614900_note17150135"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p93531251295"><a name="p93531251295"></a><a name="p93531251295"></a>该参数是系统自动生成的，不能手动配置，否则会导致接口调用失败。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row46983718"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p47584809"><a name="zh-cn_topic_0079614900_p47584809"></a><a name="zh-cn_topic_0079614900_p47584809"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p29164329"><a name="zh-cn_topic_0079614900_p29164329"></a><a name="zh-cn_topic_0079614900_p29164329"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p13500429"><a name="zh-cn_topic_0079614900_p13500429"></a><a name="zh-cn_topic_0079614900_p13500429"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p19792958"><a name="zh-cn_topic_0079614900_p19792958"></a><a name="zh-cn_topic_0079614900_p19792958"></a><span id="ph1414374372"><a name="ph1414374372"></a><a name="ph1414374372"></a>Generation是根据资源对象预期状态生成的一串序列，由</span>replication controllers<span id="ph8129152173813"><a name="ph8129152173813"></a><a name="ph8129152173813"></a>生成</span><span id="ph1481811262386"><a name="ph1481811262386"></a><a name="ph1481811262386"></a>，</span> <span id="ph7114185110381"><a name="ph7114185110381"></a><a name="ph7114185110381"></a>系统内部使用，只读项。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row43918894"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p660668"><a name="zh-cn_topic_0079614900_p660668"></a><a name="zh-cn_topic_0079614900_p660668"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p53514187"><a name="zh-cn_topic_0079614900_p53514187"></a><a name="zh-cn_topic_0079614900_p53514187"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p39681923"><a name="zh-cn_topic_0079614900_p39681923"></a><a name="zh-cn_topic_0079614900_p39681923"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p60119179"><a name="zh-cn_topic_0079614900_p60119179"></a><a name="zh-cn_topic_0079614900_p60119179"></a>CreationTimestamp<span id="ph118191040123920"><a name="ph118191040123920"></a><a name="ph118191040123920"></a>是该资源对象创建的时间戳，UTC时间，使用RFC3339格式。</span></p>
<div class="note" id="zh-cn_topic_0079614900_note4201700"><a name="zh-cn_topic_0079614900_note4201700"></a><a name="zh-cn_topic_0079614900_note4201700"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079614900_p37815307"><a name="zh-cn_topic_0079614900_p37815307"></a><a name="zh-cn_topic_0079614900_p37815307"></a><span id="ph2855182617433"><a name="ph2855182617433"></a><a name="ph2855182617433"></a>该参数是系统自动生成的，不能手动配置，否则会导致接口调用失败。</span></p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row4793448"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p52725008"><a name="zh-cn_topic_0079614900_p52725008"></a><a name="zh-cn_topic_0079614900_p52725008"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p42867269"><a name="zh-cn_topic_0079614900_p42867269"></a><a name="zh-cn_topic_0079614900_p42867269"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p49696750"><a name="zh-cn_topic_0079614900_p49696750"></a><a name="zh-cn_topic_0079614900_p49696750"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p66013812"><a name="zh-cn_topic_0079614900_p66013812"></a><a name="zh-cn_topic_0079614900_p66013812"></a>DeletionTimestamp<span id="ph1156113054514"><a name="ph1156113054514"></a><a name="ph1156113054514"></a>是该资源对象</span><span id="ph441961574518"><a name="ph441961574518"></a><a name="ph441961574518"></a>即将被删除的时间戳，使用</span>RFC3339<span id="ph2085814444615"><a name="ph2085814444615"></a><a name="ph2085814444615"></a>格式。</span> <span id="ph2719147144717"><a name="ph2719147144717"></a><a name="ph2719147144717"></a>只有当客户端请求优雅删除资源对象的时候，该参数才会被系统赋值，客户端无法直接设置该参数，资源对象会在该时间之后被删除（list无法看到已经通过名字无法查询到），该参数值设置后无法修改，只读项。</span><span id="ph7876171134911"><a name="ph7876171134911"></a><a name="ph7876171134911"></a>。</span>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row57253397"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p7013552"><a name="zh-cn_topic_0079614900_p7013552"></a><a name="zh-cn_topic_0079614900_p7013552"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p31226844"><a name="zh-cn_topic_0079614900_p31226844"></a><a name="zh-cn_topic_0079614900_p31226844"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p46346432"><a name="zh-cn_topic_0079614900_p46346432"></a><a name="zh-cn_topic_0079614900_p46346432"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p63073541"><a name="zh-cn_topic_0079614900_p63073541"></a><a name="zh-cn_topic_0079614900_p63073541"></a><span id="ph245212013110"><a name="ph245212013110"></a><a name="ph245212013110"></a>设置允许资源对象被优雅删除的最长时间</span><span id="ph1440810177314"><a name="ph1440810177314"></a><a name="ph1440810177314"></a>，该参数会和</span><span id="ph1675215517310"><a name="ph1675215517310"></a><a name="ph1675215517310"></a>deletionTimestamp</span><span id="ph569018532314"><a name="ph569018532314"></a><a name="ph569018532314"></a>一起被设置，只读项。</span> </p>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row30790963"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p11040108"><a name="zh-cn_topic_0079614900_p11040108"></a><a name="zh-cn_topic_0079614900_p11040108"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p21833561"><a name="zh-cn_topic_0079614900_p21833561"></a><a name="zh-cn_topic_0079614900_p21833561"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p23688035"><a name="zh-cn_topic_0079614900_p23688035"></a><a name="zh-cn_topic_0079614900_p23688035"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="p1891734165913"><a name="p1891734165913"></a><a name="p1891734165913"></a>Secret标签，key/value对格式。</p>
<a name="ul1736685012"></a><a name="ul1736685012"></a><ul id="ul1736685012"><li>Key：必须以字母或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符；另外可以使用DNS子域作为前缀，例如example.com/my-key， DNS子域最长253个字符。</li><li>Value：可以为空或者非空字符串，非空字符串必须以字符或数字开头，可以包含字母、数字、连字符、下划线和点，最长63个字符。</li></ul>
<p id="p156295249512"><a name="p156295249512"></a><a name="p156295249512"></a>示例：</p>
<a name="ul184411422183314"></a><a name="ul184411422183314"></a><ul id="ul184411422183314"><li>"foo": "bar"</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0079614900_row21599741"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614900_p4748621"><a name="zh-cn_topic_0079614900_p4748621"></a><a name="zh-cn_topic_0079614900_p4748621"></a>Annotations</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p49094038"><a name="zh-cn_topic_0079614900_p49094038"></a><a name="zh-cn_topic_0079614900_p49094038"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614900_p17194111"><a name="zh-cn_topic_0079614900_p17194111"></a><a name="zh-cn_topic_0079614900_p17194111"></a>Map[string]string</p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614900_p50545712"><a name="zh-cn_topic_0079614900_p50545712"></a><a name="zh-cn_topic_0079614900_p50545712"></a>Annotations<span id="ph18651246698"><a name="ph18651246698"></a><a name="ph18651246698"></a>是非结构化的键值对，通常用来保存任意外部定义的元数据。</span></p>
</td>
</tr>
<tr id="rd6cf3435589e4112b5e54dd5fecc7795"><td class="cellrowborder" valign="top" width="22.22222222222222%" headers="mcps1.2.5.1.1 "><p id="a5e699b787f7c456bb897a571b2bd303b"><a name="a5e699b787f7c456bb897a571b2bd303b"></a><a name="a5e699b787f7c456bb897a571b2bd303b"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="18.18181818181818%" headers="mcps1.2.5.1.2 "><p id="a9499098f0a904fb1979e0f9292b6b87c"><a name="a9499098f0a904fb1979e0f9292b6b87c"></a><a name="a9499098f0a904fb1979e0f9292b6b87c"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.2020202020202%" headers="mcps1.2.5.1.3 "><p id="a1857e4ea59ee46e78931c80b1ce4d570"><a name="a1857e4ea59ee46e78931c80b1ce4d570"></a><a name="a1857e4ea59ee46e78931c80b1ce4d570"></a><a href="#t56c9527f988e4c2c8b0d5a53ba538176">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.39393939393939%" headers="mcps1.2.5.1.4 "><p id="a47143b35d469419b80303ee850b0642e"><a name="a47143b35d469419b80303ee850b0642e"></a><a name="a47143b35d469419b80303ee850b0642e"></a><span id="ph1168873081810"><a name="ph1168873081810"></a><a name="ph1168873081810"></a>OwnerReferences是</span><span id="ph1938645591310"><a name="ph1938645591310"></a><a name="ph1938645591310"></a>所有依赖当前资源对象的其他资源对象列表，如果列表里资源都已经被删除，则当前资源会被垃圾回收。如果当前资源被controller管理，则列表中有一项指向该controller，该项中controller字段被设置为true</span><span id="ph1264214916190"><a name="ph1264214916190"></a><a name="ph1264214916190"></a>，controller不会超过一个。</span> </p>
</td>
</tr>
</tbody>
</table>

**表 4**  ownerReferences字段数据结构说明

<a name="t56c9527f988e4c2c8b0d5a53ba538176"></a>
<table><thead align="left"><tr id="r550b08f0ee964525be70ec96f41d8475"><th class="cellrowborder" valign="top" width="22.37%" id="mcps1.2.5.1.1"><p id="a3f6c00cbf4d44f82906917be33495c96"><a name="a3f6c00cbf4d44f82906917be33495c96"></a><a name="a3f6c00cbf4d44f82906917be33495c96"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.86%" id="mcps1.2.5.1.2"><p id="p16985922205955"><a name="p16985922205955"></a><a name="p16985922205955"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.49%" id="mcps1.2.5.1.3"><p id="p33682440205955"><a name="p33682440205955"></a><a name="p33682440205955"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.28%" id="mcps1.2.5.1.4"><p id="p43923090205955"><a name="p43923090205955"></a><a name="p43923090205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rc77662aed67a428eb415a6a70e2f2cc0"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="a94c8a8baf1d347a0927d0db9a98b0edd"><a name="a94c8a8baf1d347a0927d0db9a98b0edd"></a><a name="a94c8a8baf1d347a0927d0db9a98b0edd"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="aa8414eb11e6d4d219a843224790cecf4"><a name="aa8414eb11e6d4d219a843224790cecf4"></a><a name="aa8414eb11e6d4d219a843224790cecf4"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="a2689014b700340c3b7a06423e8ea47a8"><a name="a2689014b700340c3b7a06423e8ea47a8"></a><a name="a2689014b700340c3b7a06423e8ea47a8"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="ac964351ba76e4233b5f31aa5309de4b4"><a name="ac964351ba76e4233b5f31aa5309de4b4"></a><a name="ac964351ba76e4233b5f31aa5309de4b4"></a><span id="ph977232819508"><a name="ph977232819508"></a><a name="ph977232819508"></a>资源对象的API版本</span></p>
</td>
</tr>
<tr id="r97f9bda38ecc4049b7df9d01b3628b45"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="a940e95193ce44e44afc20dcdf0b24958"><a name="a940e95193ce44e44afc20dcdf0b24958"></a><a name="a940e95193ce44e44afc20dcdf0b24958"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="abac88577765d4a25b4fe1873aca0b729"><a name="abac88577765d4a25b4fe1873aca0b729"></a><a name="abac88577765d4a25b4fe1873aca0b729"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="a485b075ba5e848a684f32c68f2f49bdd"><a name="a485b075ba5e848a684f32c68f2f49bdd"></a><a name="a485b075ba5e848a684f32c68f2f49bdd"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a4d2494c2f65b402db38a21a347dbb2ff"><a name="a4d2494c2f65b402db38a21a347dbb2ff"></a><a name="a4d2494c2f65b402db38a21a347dbb2ff"></a><span id="ph144911593509"><a name="ph144911593509"></a><a name="ph144911593509"></a>资源对象的类型</span></p>
</td>
</tr>
<tr id="r0ae02b5d933345829dd94dbe697b10d5"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="a681a134085fc422fa901f57984edbab9"><a name="a681a134085fc422fa901f57984edbab9"></a><a name="a681a134085fc422fa901f57984edbab9"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="ab5fe6157b1dc4ff3b50c69bb185ab420"><a name="ab5fe6157b1dc4ff3b50c69bb185ab420"></a><a name="ab5fe6157b1dc4ff3b50c69bb185ab420"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="a9e7d6ca2ef7b41d79fc3bb0328b224b2"><a name="a9e7d6ca2ef7b41d79fc3bb0328b224b2"></a><a name="a9e7d6ca2ef7b41d79fc3bb0328b224b2"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a2484d62071634d99981015986f3c8faf"><a name="a2484d62071634d99981015986f3c8faf"></a><a name="a2484d62071634d99981015986f3c8faf"></a><span id="ph415781355111"><a name="ph415781355111"></a><a name="ph415781355111"></a>资源对象的名字</span></p>
</td>
</tr>
<tr id="r23e2627b1b114d4b926db2721d59c1eb"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="a7646e7d4535d4afcb99e819c66b88cbe"><a name="a7646e7d4535d4afcb99e819c66b88cbe"></a><a name="a7646e7d4535d4afcb99e819c66b88cbe"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614900_p570124172656"><a name="zh-cn_topic_0079614900_p570124172656"></a><a name="zh-cn_topic_0079614900_p570124172656"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="adcd3ed14ebaf4b5f9ac15e48cfc06d22"><a name="adcd3ed14ebaf4b5f9ac15e48cfc06d22"></a><a name="adcd3ed14ebaf4b5f9ac15e48cfc06d22"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a17f25dca1d6a472b950aa60856c4912d"><a name="a17f25dca1d6a472b950aa60856c4912d"></a><a name="a17f25dca1d6a472b950aa60856c4912d"></a><span id="ph1028315231513"><a name="ph1028315231513"></a><a name="ph1028315231513"></a>资源对象的ID</span></p>
</td>
</tr>
<tr id="r23569e934f4c435bafdd343d76a240ba"><td class="cellrowborder" valign="top" width="22.37%" headers="mcps1.2.5.1.1 "><p id="abe8fbcc645e34aa5b63e4877951cf16f"><a name="abe8fbcc645e34aa5b63e4877951cf16f"></a><a name="abe8fbcc645e34aa5b63e4877951cf16f"></a>controller</p>
</td>
<td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.5.1.2 "><p id="a6c3e93d72df44415b9c26a8047ee5945"><a name="a6c3e93d72df44415b9c26a8047ee5945"></a><a name="a6c3e93d72df44415b9c26a8047ee5945"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="ad3e358d29eb54e5987b16b12933c7378"><a name="ad3e358d29eb54e5987b16b12933c7378"></a><a name="ad3e358d29eb54e5987b16b12933c7378"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.28%" headers="mcps1.2.5.1.4 "><p id="a8c96e54ca8e34c58806c4ff79c8ec8b9"><a name="a8c96e54ca8e34c58806c4ff79c8ec8b9"></a><a name="a8c96e54ca8e34c58806c4ff79c8ec8b9"></a><span id="ph1818843935119"><a name="ph1818843935119"></a><a name="ph1818843935119"></a>如果是true，则表示该资源对象被controller管理</span></p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
  "apiVersion": "v1",
  "kind": "Secret",
  "metadata": {
    "name": "mysecret"
  },
  "type": "Opaque",
  "data": {
    "password": "******", #需要用Base64编码，方法：echo -n "待编码内容" | base64
    "username": "*****" #需要用Base64编码，方法：echo -n "待编码内容" | base64
  }
}
```

## 响应消息<a name="s08d56e5f4e57452da0a49400212440a4"></a>

**响应参数：**

响应参数的详细描述请参见[表2](#zh-cn_topic_0079614900_ref458786458)。

**响应示例：**

```
{ 
   "kind": "Secret", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "mysecret", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/secrets/mysecret", 
     "uid": "597c306b-594e-11e6-b444-286ed488fafe", 
     "resourceVersion": "10742", 
     "creationTimestamp": "2016-08-03T07:46:12Z" 
   }, 
   "data": { 
     "password": "******", 
     "username": "*****"      
   }, 
   "type": "Opaque" 
 }
```

## 状态码<a name="s50f1049a6a4d404c895cf636eb8f3bf1"></a>

[表5](#zh-cn_topic_0079614900_table46761928)描述API的状态码。

**表 5**  状态码

<a name="zh-cn_topic_0079614900_table46761928"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614900_row33254664"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p55616028205955"><a name="p55616028205955"></a><a name="p55616028205955"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p8604418205955"><a name="p8604418205955"></a><a name="p8604418205955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614900_row41084259"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614900_p39490674"><a name="zh-cn_topic_0079614900_p39490674"></a><a name="zh-cn_topic_0079614900_p39490674"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614900_p44628050"><a name="zh-cn_topic_0079614900_p44628050"></a><a name="zh-cn_topic_0079614900_p44628050"></a><span id="ph15619164213014"><a name="ph15619164213014"></a><a name="ph15619164213014"></a>接口调用成功，</span><span id="ph1613560311"><a name="ph1613560311"></a><a name="ph1613560311"></a>返回创建的secret资源对象</span></p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

