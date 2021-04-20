# 创建StatefulSet<a name="cce_02_0145"></a>

## 功能介绍<a name="section40975543"></a>

This API is used to create a StatefulSet resource object.

## URI<a name="section33235568"></a>

POST /apis/apps/v1/namespaces/\{namespace\}/statefulsets （适用于1.9及以上版本的所有集群）

POST /apis/apps/v1beta1/namespaces/\{namespace\}/statefulsets （仅适用于1.15及以下版本的集群）

[表1](#d0e37523)描述该API的参数。

**表 1**  参数解释

<a name="d0e37523"></a>
<table><thead align="left"><tr id="row5993206"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.61%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12622186"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p15764126"><a name="p15764126"></a><a name="p15764126"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p1825823"><a name="p1825823"></a><a name="p1825823"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p13673940"><a name="p13673940"></a><a name="p13673940"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row55956597"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p36190548"><a name="p36190548"></a><a name="p36190548"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p45753308"><a name="p45753308"></a><a name="p45753308"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p15030452"><a name="p15030452"></a><a name="p15030452"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section30684661"></a>

**请求参数：**

请求参数如[表2](#d0e37568)所示。

**表 2**  请求参数

<a name="d0e37568"></a>
<table><thead align="left"><tr id="row22231582"><th class="cellrowborder" valign="top" width="22.447755224477554%" id="mcps1.2.5.1.1"><p id="p55927689"><a name="p55927689"></a><a name="p55927689"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.288571142885711%" id="mcps1.2.5.1.2"><p id="p33848965"><a name="p33848965"></a><a name="p33848965"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.3"><p id="p57411641"><a name="p57411641"></a><a name="p57411641"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.85571442855714%" id="mcps1.2.5.1.4"><p id="p19831374"><a name="p19831374"></a><a name="p19831374"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row62837484"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p56671418"><a name="p56671418"></a><a name="p56671418"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p26982112"><a name="p26982112"></a><a name="p26982112"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p38067463"><a name="p38067463"></a><a name="p38067463"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p63565654"><a name="p63565654"></a><a name="p63565654"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row35219981"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p34246188"><a name="p34246188"></a><a name="p34246188"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p22477832"><a name="p22477832"></a><a name="p22477832"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p8765064"><a name="p8765064"></a><a name="p8765064"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p38881556"><a name="p38881556"></a><a name="p38881556"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row14389691"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p24714309"><a name="p24714309"></a><a name="p24714309"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p55702032"><a name="p55702032"></a><a name="p55702032"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p15570756"><a name="p15570756"></a><a name="p15570756"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table47756489">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p9683143"><a name="p9683143"></a><a name="p9683143"></a>Standard list metadata.</p>
</td>
</tr>
<tr id="row20039428"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p12580961"><a name="p12580961"></a><a name="p12580961"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p12424902"><a name="p12424902"></a><a name="p12424902"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p66893020"><a name="p66893020"></a><a name="p66893020"></a><a href="#d0e37783">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p43976738"><a name="p43976738"></a><a name="p43976738"></a>Spec defines the desired identities of pods in this set.</p>
</td>
</tr>
<tr id="row60246329"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p48114513"><a name="p48114513"></a><a name="p48114513"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p4961465"><a name="p4961465"></a><a name="p4961465"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p66334361"><a name="p66334361"></a><a name="p66334361"></a><a href="#d0e37659">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p39367534"><a name="p39367534"></a><a name="p39367534"></a>Status is the current status of Pods in this StatefulSet. This data may be out of date by some window of time.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  status字段数据结构说明

<a name="d0e37659"></a>
<table><thead align="left"><tr id="row16874366"><th class="cellrowborder" valign="top" width="22.68%" id="mcps1.2.5.1.1"><p id="p24646410"><a name="p24646410"></a><a name="p24646410"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.430000000000001%" id="mcps1.2.5.1.2"><p id="p50202190"><a name="p50202190"></a><a name="p50202190"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.59%" id="mcps1.2.5.1.3"><p id="p39845619"><a name="p39845619"></a><a name="p39845619"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.3%" id="mcps1.2.5.1.4"><p id="p6269729"><a name="p6269729"></a><a name="p6269729"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row38086015"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p65068341"><a name="p65068341"></a><a name="p65068341"></a>observedGeneration</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p36044268"><a name="p36044268"></a><a name="p36044268"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p33904587"><a name="p33904587"></a><a name="p33904587"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p61917051"><a name="p61917051"></a><a name="p61917051"></a>Most recent generation observed by this autoscaler.</p>
</td>
</tr>
<tr id="row20382553"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p40374085"><a name="p40374085"></a><a name="p40374085"></a>replicas</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p49075413"><a name="p49075413"></a><a name="p49075413"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p15685489"><a name="p15685489"></a><a name="p15685489"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p62565122"><a name="p62565122"></a><a name="p62565122"></a>Replicas is the number of actual replicas.</p>
</td>
</tr>
<tr id="row26215194"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p43055989"><a name="p43055989"></a><a name="p43055989"></a>currentReplicas</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p64983097"><a name="p64983097"></a><a name="p64983097"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p29139468"><a name="p29139468"></a><a name="p29139468"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p36271844"><a name="p36271844"></a><a name="p36271844"></a>currentReplicas is the number of Pods created by the StatefulSet controller from the StatefulSet version indicated by currentRevision.</p>
</td>
</tr>
<tr id="row58011142"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p1282043"><a name="p1282043"></a><a name="p1282043"></a>currentRevision</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p36736673"><a name="p36736673"></a><a name="p36736673"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p22880543"><a name="p22880543"></a><a name="p22880543"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p36918294"><a name="p36918294"></a><a name="p36918294"></a>currentRevision, if not empty, indicates the version of the StatefulSet used to generate Pods in the sequence [0,currentReplicas).</p>
</td>
</tr>
<tr id="row63829190"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p2781886"><a name="p2781886"></a><a name="p2781886"></a>readyReplicas</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p24006190"><a name="p24006190"></a><a name="p24006190"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p65453247"><a name="p65453247"></a><a name="p65453247"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p1015136"><a name="p1015136"></a><a name="p1015136"></a>readyReplicas is the number of Pods created by the StatefulSet controller that have a Ready Condition.</p>
</td>
</tr>
<tr id="row9136226"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p1836869"><a name="p1836869"></a><a name="p1836869"></a>updateRevision</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p14568680"><a name="p14568680"></a><a name="p14568680"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p39212403"><a name="p39212403"></a><a name="p39212403"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p64574987"><a name="p64574987"></a><a name="p64574987"></a>updateRevision, if not empty, indicates the version of the StatefulSet used to generate Pods in the sequence [replicas-updatedReplicas,replicas)</p>
</td>
</tr>
<tr id="row44303971"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p31851928"><a name="p31851928"></a><a name="p31851928"></a>updatedReplicas</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p29869398"><a name="p29869398"></a><a name="p29869398"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p3502148"><a name="p3502148"></a><a name="p3502148"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p2929118"><a name="p2929118"></a><a name="p2929118"></a>updatedReplicas is the number of Pods created by the StatefulSet controller from the StatefulSet version indicated by updateRevision.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  spec字段数据结构说明

<a name="d0e37783"></a>
<table><thead align="left"><tr id="row52680850"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.5.1.1"><p id="p39290419"><a name="p39290419"></a><a name="p39290419"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p28407365"><a name="p28407365"></a><a name="p28407365"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.5.1.3"><p id="p19295215"><a name="p19295215"></a><a name="p19295215"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42%" id="mcps1.2.5.1.4"><p id="p19408602"><a name="p19408602"></a><a name="p19408602"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row28592942"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p34326929"><a name="p34326929"></a><a name="p34326929"></a>replicas</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p29017902"><a name="p29017902"></a><a name="p29017902"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p1639851"><a name="p1639851"></a><a name="p1639851"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p65719088"><a name="p65719088"></a><a name="p65719088"></a>Replicas is the desired number of replicas of the given Template. These are replicas in the sense that they are instantiations of the same Template, but individual replicas also have a consistent identity. If unspecified, defaults to 1.</p>
</td>
</tr>
<tr id="row54600886"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p60595611"><a name="p60595611"></a><a name="p60595611"></a>podManagementPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p9297436"><a name="p9297436"></a><a name="p9297436"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p14894883"><a name="p14894883"></a><a name="p14894883"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p53842627"><a name="p53842627"></a><a name="p53842627"></a>podManagementPolicy controls how pods are created during initial scale up, when replacing pods on nodes, or when scaling down. The default policy is OrderedReady, where pods are created in increasing order (pod-0, then pod-1, etc) and the controller will wait until each pod is ready before continuing. When scaling down, the pods are removed in the opposite order. The alternative policy is Parallel which will create pods in parallel to match the desired scale without waiting, and on scale down will delete all pods at once.</p>
</td>
</tr>
<tr id="row14821596"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p59698656"><a name="p59698656"></a><a name="p59698656"></a>revisionHistoryLimit</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3752968"><a name="p3752968"></a><a name="p3752968"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p35555005"><a name="p35555005"></a><a name="p35555005"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p15577370"><a name="p15577370"></a><a name="p15577370"></a>revisionHistoryLimit is the maximum number of revisions that will be maintained in the StatefulSet's revision history. The revision history consists of all revisions not represented by a currently applied StatefulSetSpec version. The default value is 10.</p>
</td>
</tr>
<tr id="row5978604"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p14504886"><a name="p14504886"></a><a name="p14504886"></a>updateStrategy</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p34045100"><a name="p34045100"></a><a name="p34045100"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p6189752"><a name="p6189752"></a><a name="p6189752"></a><a href="#d0e38083">updateStrategy</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p10100779"><a name="p10100779"></a><a name="p10100779"></a>updateStrategy indicates the StatefulSetUpdateStrategy that will be employed to update Pods in the StatefulSet when a revision is made to Template.</p>
</td>
</tr>
<tr id="row23798155"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p48602377"><a name="p48602377"></a><a name="p48602377"></a>serviceName</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p44478431"><a name="p44478431"></a><a name="p44478431"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p45983158"><a name="p45983158"></a><a name="p45983158"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p33648309"><a name="p33648309"></a><a name="p33648309"></a>ServiceName is the name of the service that governs this StatefulSet. This service must exist before the StatefulSet, and is responsible for the network identity of the set. Pods get DNS/hostnames that follow the pattern: pod-specific-string.serviceName.default.svc.cluster.local where "pod-specific-string" is managed by the StatefulSet controller.</p>
</td>
</tr>
<tr id="row34399332"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p34882483"><a name="p34882483"></a><a name="p34882483"></a>volumeClaimTemplates</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p6908863"><a name="p6908863"></a><a name="p6908863"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p22746991"><a name="p22746991"></a><a name="p22746991"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p6667146"><a name="p6667146"></a><a name="p6667146"></a>VolumeClaimTemplates is a list of claims that pods are allowed to reference. The StatefulSet controller is responsible for mapping network identities to claims in a way that maintains the identity of a pod. Every claim in this list must have at least one matching (by name) volumeMount in one container in the template. A claim in this list takes precedence over any volumes in the template, with the same name.具体请参见<a href="获取指定的PersistentVolumeClaim.md#t7aa9de1153e9466cbfcaa9af17a24772">表2</a>。</p>
</td>
</tr>
<tr id="row60004316"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p28511466"><a name="p28511466"></a><a name="p28511466"></a>selector</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p27727420"><a name="p27727420"></a><a name="p27727420"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p31328571"><a name="p31328571"></a><a name="p31328571"></a><a href="#d0e37920">selector</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p21514819"><a name="p21514819"></a><a name="p21514819"></a>Selector is a label query over pods that should match the replica count. If empty, defaulted to labels on the pod template.</p>
</td>
</tr>
<tr id="row59415646"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p47938002"><a name="p47938002"></a><a name="p47938002"></a>template</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p57772947"><a name="p57772947"></a><a name="p57772947"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p49097096"><a name="p49097096"></a><a name="p49097096"></a><a href="#d0e38032">PodTemplateSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p22758632"><a name="p22758632"></a><a name="p22758632"></a>Template is the object that describes the pod that will be created if insufficient replicas are detected. Each pod stamped out by the StatefulSet will fulfill this Template, but have a unique identity from the rest of the StatefulSet.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  selector字段数据结构说明

<a name="d0e37920"></a>
<table><thead align="left"><tr id="row42112853"><th class="cellrowborder" valign="top" width="22.447755224477554%" id="mcps1.2.5.1.1"><p id="p55697946"><a name="p55697946"></a><a name="p55697946"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.308469153084694%" id="mcps1.2.5.1.2"><p id="p15239763"><a name="p15239763"></a><a name="p15239763"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.3"><p id="p26461289"><a name="p26461289"></a><a name="p26461289"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.85571442855714%" id="mcps1.2.5.1.4"><p id="p62989635"><a name="p62989635"></a><a name="p62989635"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1886793"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p18612581"><a name="p18612581"></a><a name="p18612581"></a>matchExpressions</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084694%" headers="mcps1.2.5.1.2 "><p id="p31224060"><a name="p31224060"></a><a name="p31224060"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p46120952"><a name="p46120952"></a><a name="p46120952"></a><a href="#d0e37970">matchExpressions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p633806"><a name="p633806"></a><a name="p633806"></a>matchExpressions is a list of label selector requirements. The requirements are ANDed.</p>
</td>
</tr>
<tr id="row5704254"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p59391448"><a name="p59391448"></a><a name="p59391448"></a>matchLabels</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084694%" headers="mcps1.2.5.1.2 "><p id="p45977974"><a name="p45977974"></a><a name="p45977974"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p33228417"><a name="p33228417"></a><a name="p33228417"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p7147232"><a name="p7147232"></a><a name="p7147232"></a>MatchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</p>
</td>
</tr>
</tbody>
</table>

**表 6**  matchExpressions字段数据结构说明

<a name="d0e37970"></a>
<table><thead align="left"><tr id="row44155801"><th class="cellrowborder" valign="top" width="22.447755224477547%" id="mcps1.2.5.1.1"><p id="p19850148"><a name="p19850148"></a><a name="p19850148"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.308469153084689%" id="mcps1.2.5.1.2"><p id="p64358168"><a name="p64358168"></a><a name="p64358168"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.40795920407959%" id="mcps1.2.5.1.3"><p id="p45629083"><a name="p45629083"></a><a name="p45629083"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.83581641835816%" id="mcps1.2.5.1.4"><p id="p4968280"><a name="p4968280"></a><a name="p4968280"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row66886389"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p49088410"><a name="p49088410"></a><a name="p49088410"></a>key</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p16738288"><a name="p16738288"></a><a name="p16738288"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p13624094"><a name="p13624094"></a><a name="p13624094"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p29809869"><a name="p29809869"></a><a name="p29809869"></a>key is the label key that the selector applies to.</p>
</td>
</tr>
<tr id="row66962237"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p55232079"><a name="p55232079"></a><a name="p55232079"></a>operator</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p44613430"><a name="p44613430"></a><a name="p44613430"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p56918106"><a name="p56918106"></a><a name="p56918106"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p46963874"><a name="p46963874"></a><a name="p46963874"></a>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</p>
</td>
</tr>
<tr id="row20021687"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p11143985"><a name="p11143985"></a><a name="p11143985"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p30247620"><a name="p30247620"></a><a name="p30247620"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p34138135"><a name="p34138135"></a><a name="p34138135"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p13725522"><a name="p13725522"></a><a name="p13725522"></a>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  PodTemplateSpec字段数据结构说明

<a name="d0e38032"></a>
<table><thead align="left"><tr id="row47226782"><th class="cellrowborder" valign="top" width="22.447755224477547%" id="mcps1.2.5.1.1"><p id="p164139"><a name="p164139"></a><a name="p164139"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.308469153084689%" id="mcps1.2.5.1.2"><p id="p13295317"><a name="p13295317"></a><a name="p13295317"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.40795920407959%" id="mcps1.2.5.1.3"><p id="p3178883"><a name="p3178883"></a><a name="p3178883"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.83581641835816%" id="mcps1.2.5.1.4"><p id="p56162974"><a name="p56162974"></a><a name="p56162974"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row52907021"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p57610297"><a name="p57610297"></a><a name="p57610297"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p35922441"><a name="p35922441"></a><a name="p35922441"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p24036581"><a name="p24036581"></a><a name="p24036581"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table47756489">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p7254638"><a name="p7254638"></a><a name="p7254638"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="row65291748"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p54140246"><a name="p54140246"></a><a name="p54140246"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p23283829"><a name="p23283829"></a><a name="p23283829"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p6941992"><a name="p6941992"></a><a name="p6941992"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table66152725">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p27547802"><a name="p27547802"></a><a name="p27547802"></a>Specification of the desired behavior of the pod.</p>
</td>
</tr>
</tbody>
</table>

**表 8**  updateStrategy字段数据结构说明

<a name="d0e38083"></a>
<table><thead align="left"><tr id="row1068106"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.1"><p id="p19407724"><a name="p19407724"></a><a name="p19407724"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.5.1.2"><p id="p28521827"><a name="p28521827"></a><a name="p28521827"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="23.46765323467653%" id="mcps1.2.5.1.3"><p id="p28566679"><a name="p28566679"></a><a name="p28566679"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.796020397960206%" id="mcps1.2.5.1.4"><p id="p32199663"><a name="p32199663"></a><a name="p32199663"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row58035924"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p3289389"><a name="p3289389"></a><a name="p3289389"></a>rollingUpdate</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p65113955"><a name="p65113955"></a><a name="p65113955"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="23.46765323467653%" headers="mcps1.2.5.1.3 "><p id="p39738973"><a name="p39738973"></a><a name="p39738973"></a><a href="#table102371729161619">rollingUpdate</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p9467071"><a name="p9467071"></a><a name="p9467071"></a>RollingUpdate is used to communicate parameters when Type is RollingUpdateStatefulSetStrategyType.</p>
</td>
</tr>
<tr id="row18094775"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p56390700"><a name="p56390700"></a><a name="p56390700"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p4244010"><a name="p4244010"></a><a name="p4244010"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="23.46765323467653%" headers="mcps1.2.5.1.3 "><p id="p8220504"><a name="p8220504"></a><a name="p8220504"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p20058578"><a name="p20058578"></a><a name="p20058578"></a>Type indicates the type of the StatefulSetUpdateStrategy.</p>
</td>
</tr>
</tbody>
</table>

**表 9**  rollingUpdate字段数据结构说明

<a name="table102371729161619"></a>
<table><thead align="left"><tr id="row66152742"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.1"><p id="p56771847"><a name="p56771847"></a><a name="p56771847"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.5.1.2"><p id="p35116889"><a name="p35116889"></a><a name="p35116889"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="23.46765323467653%" id="mcps1.2.5.1.3"><p id="p25895747"><a name="p25895747"></a><a name="p25895747"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.796020397960206%" id="mcps1.2.5.1.4"><p id="p17180782"><a name="p17180782"></a><a name="p17180782"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49466114"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p47332261"><a name="p47332261"></a><a name="p47332261"></a>partition</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p8707970"><a name="p8707970"></a><a name="p8707970"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="23.46765323467653%" headers="mcps1.2.5.1.3 "><p id="p34256959"><a name="p34256959"></a><a name="p34256959"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p8825898"><a name="p8825898"></a><a name="p8825898"></a>Partition indicates the ordinal at which the StatefulSet should be partitioned.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
    "apiVersion": "apps/v1beta1",
    "kind": "StatefulSet",
    "metadata": {
        "labels": {
            "name": "statefulset-test"
        },
        "name": "statefulset-test"
    },
    "spec": {
        "replicas": 1,
        "selector": {
            "matchLabels": {
                "name": "statefulset-test"
            }
        },
        "serviceName": "service-test",
        "template": {
            "metadata": {
                "labels": {
                    "name": "statefulset-test"
                }
            },
            "spec": {
                "containers": [
                    {
                        "image": "172.16.5.235:20202/test/nginx",
                        "name": "statefulset-test"
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

## 响应消息<a name="section7726493"></a>

**响应参数：**

响应参数的详细描述请参见[表2](#d0e37568)

**响应示例：**

```
{
    "kind": "StatefulSet",
    "apiVersion": "apps/v1beta1",
    "metadata": {
        "name": "statefulset-test",
        "namespace": "default",
        "selfLink": "/apis/apps/v1beta1/namespaces/default/statefulsets/statefulset-test",
        "uid": "d9e1118c-fc20-11e7-9c3c-fa163eb8ad1a",
        "resourceVersion": "486277",
        "generation": 1,
        "creationTimestamp": "2018-01-18T07:26:08Z",
        "labels": {
            "name": "statefulset-test"
        },
        "enable": true
    },
    "spec": {
        "replicas": 1,
        "selector": {
            "matchLabels": {
                "name": "statefulset-test"
            }
        },
        "template": {
            "metadata": {
                "creationTimestamp": null,
                "labels": {
                    "name": "statefulset-test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "statefulset-test",
                        "image": "172.16.5.235:20202/test/nginx",
                        "resources": {},
                        "terminationMessagePath": "/dev/termination-log",
                        "terminationMessagePolicy": "File",
                        "imagePullPolicy": "Always"
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
        "serviceName": "service-test",
        "podManagementPolicy": "OrderedReady",
        "updateStrategy": {
            "type": "OnDelete"
        },
        "revisionHistoryLimit": 10
    },
    "status": {
        "replicas": 0
    }
}
```

## 状态码<a name="section2429579"></a>

[表10](#d0e38203)描述API的状态码。

**表 10**  状态码

<a name="d0e38203"></a>
<table><thead align="left"><tr id="row26900678"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p31471277"><a name="p31471277"></a><a name="p31471277"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p66145529"><a name="p66145529"></a><a name="p66145529"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row56187666"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p54907103"><a name="p54907103"></a><a name="p54907103"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18290377"><a name="p18290377"></a><a name="p18290377"></a>The request has been fulfilled, resulting in the creation of a new resource.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

