# 创建RoleBinding<a name="cce_02_0311"></a>

## 功能介绍<a name="section152914720538"></a>

This API is used to create a RoleBinding

## URL<a name="section2026625815310"></a>

POST /apis/rbac.authorization.k8s.io/v1/namespaces/\{namespace\}/rolebindings

[参数解释](#d0e42906)描述该API的参数。

**表 1**  参数解释

<a name="d0e42906"></a>
<table><thead align="left"><tr id="row10640301"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.61%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row19095777"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p3254085"><a name="p3254085"></a><a name="p3254085"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p62254326"><a name="p62254326"></a><a name="p62254326"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p9435611"><a name="p9435611"></a><a name="p9435611"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row17811636"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p33456451"><a name="p33456451"></a><a name="p33456451"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p25618043"><a name="p25618043"></a><a name="p25618043"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p61795587"><a name="p61795587"></a><a name="p61795587"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row26391471649"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p14640471145"><a name="p14640471145"></a><a name="p14640471145"></a>body</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p064011716413"><a name="p064011716413"></a><a name="p064011716413"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p46408710414"><a name="p46408710414"></a><a name="p46408710414"></a><a href="#d0e42951">请求参数</a></p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section18662134312520"></a>

**请求参数：**

请求参数如[请求参数](#d0e42951)所示。

**表 2**  请求参数

<a name="d0e42951"></a>
<table><thead align="left"><tr id="row29055885"><th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.5.1.1"><p id="p4716456"><a name="p4716456"></a><a name="p4716456"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.141414141414144%" id="mcps1.2.5.1.2"><p id="p46488660"><a name="p46488660"></a><a name="p46488660"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.5.1.3"><p id="p7485112"><a name="p7485112"></a><a name="p7485112"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.43434343434344%" id="mcps1.2.5.1.4"><p id="p2314365"><a name="p2314365"></a><a name="p2314365"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row772562671320"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p772532621317"><a name="p772532621317"></a><a name="p772532621317"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p16725132617134"><a name="p16725132617134"></a><a name="p16725132617134"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p17725142619139"><a name="p17725142619139"></a><a name="p17725142619139"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p1772519266135"><a name="p1772519266135"></a><a name="p1772519266135"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row63487140"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p14792753151115"><a name="p14792753151115"></a><a name="p14792753151115"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p13790153101115"><a name="p13790153101115"></a><a name="p13790153101115"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p10789155381112"><a name="p10789155381112"></a><a name="p10789155381112"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p978795341120"><a name="p978795341120"></a><a name="p978795341120"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="row36873674"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p6785175341110"><a name="p6785175341110"></a><a name="p6785175341110"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p1378375321115"><a name="p1378375321115"></a><a name="p1378375321115"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p1578195321111"><a name="p1578195321111"></a><a name="p1578195321111"></a><a href="#zh-cn_topic_0079615000_table43837055">metadata字段数据结构说明</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p1977810533112"><a name="p1977810533112"></a><a name="p1977810533112"></a>Standard object’s metadata.</p>
</td>
</tr>
<tr id="row11417416101017"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p1041718169105"><a name="p1041718169105"></a><a name="p1041718169105"></a>roleRef</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p1141701601014"><a name="p1141701601014"></a><a name="p1141701601014"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p04171016181015"><a name="p04171016181015"></a><a name="p04171016181015"></a><a href="#table8814183942020">RoleRef字段数据结构说明</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p184171168106"><a name="p184171168106"></a><a name="p184171168106"></a>RoleRef can reference a Role in the current namespace or a ClusterRole in the global namespace. If the RoleRef cannot be resolved, the Authorizer must return an error.</p>
</td>
</tr>
<tr id="row899203"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p15394039111013"><a name="p15394039111013"></a><a name="p15394039111013"></a>subjects</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p4774175316112"><a name="p4774175316112"></a><a name="p4774175316112"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p1698214564448"><a name="p1698214564448"></a><a name="p1698214564448"></a><a href="#table172861541152017">Subject字段数据结构说明</a> array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p19771175311119"><a name="p19771175311119"></a><a name="p19771175311119"></a>Subjects holds references to the objects the role applies to.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  metadata字段数据结构说明

<a name="zh-cn_topic_0079615000_table43837055"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079615000_row29476029"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079615000_p38748148"><a name="zh-cn_topic_0079615000_p38748148"></a><a name="zh-cn_topic_0079615000_p38748148"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.5.1.2"><p id="p19758610205444"><a name="p19758610205444"></a><a name="p19758610205444"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p56943584205444"><a name="p56943584205444"></a><a name="p56943584205444"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39%" id="mcps1.2.5.1.4"><p id="p49027631205444"><a name="p49027631205444"></a><a name="p49027631205444"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079615000_row51840373"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p38320646"><a name="zh-cn_topic_0079615000_p38320646"></a><a name="zh-cn_topic_0079615000_p38320646"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p16964616"><a name="zh-cn_topic_0079615000_p16964616"></a><a name="zh-cn_topic_0079615000_p16964616"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p31956642"><a name="zh-cn_topic_0079615000_p31956642"></a><a name="zh-cn_topic_0079615000_p31956642"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079615000_p19441857"><a name="zh-cn_topic_0079615000_p19441857"></a><a name="zh-cn_topic_0079615000_p19441857"></a>Annotations is an unstructured key value map stored with a resource that may be set by external tools to store and retrieve arbitrary metadata. They are not queryable and should be preserved when modifying objects.</p>
</td>
</tr>
<tr id="r59e9b08f407d496eac092f809321b53f"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="aeefc6fe8fca8446685053b6d0902640e"><a name="aeefc6fe8fca8446685053b6d0902640e"></a><a name="aeefc6fe8fca8446685053b6d0902640e"></a>clusterName</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p541213427308"><a name="zh-cn_topic_0079615000_p541213427308"></a><a name="zh-cn_topic_0079615000_p541213427308"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p641274253010"><a name="zh-cn_topic_0079615000_p641274253010"></a><a name="zh-cn_topic_0079615000_p641274253010"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="a7814694051a0406dbbba95ba61cb3e8f"><a name="a7814694051a0406dbbba95ba61cb3e8f"></a><a name="a7814694051a0406dbbba95ba61cb3e8f"></a>The name of the cluster which the object belongs to. This is used to distinguish resources with same name and namespace in different clusters. This field is not set anywhere right now and apiserver is going to ignore it if set in create or update request.</p>
</td>
</tr>
<tr id="row1243774431910"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p24375449197"><a name="p24375449197"></a><a name="p24375449197"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p1943714418192"><a name="p1943714418192"></a><a name="p1943714418192"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1243715444198"><a name="p1243715444198"></a><a name="p1243715444198"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p1144916442010"><a name="p1144916442010"></a><a name="p1144916442010"></a>CreationTimestamp is a timestamp representing the server time when this object was created. It is not guaranteed to be set in happens-before order across separate operations. Clients may not set this value. It is represented in RFC3339 form and is in UTC.</p>
<p id="p20449144162012"><a name="p20449144162012"></a><a name="p20449144162012"></a>Populated by the system. Read-only. Null for lists.</p>
</td>
</tr>
<tr id="row141132424192"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p19113144212196"><a name="p19113144212196"></a><a name="p19113144212196"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p1711354211191"><a name="p1711354211191"></a><a name="p1711354211191"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p11113942101915"><a name="p11113942101915"></a><a name="p11113942101915"></a>integer(int64)</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p71132042121912"><a name="p71132042121912"></a><a name="p71132042121912"></a>Number of seconds allowed for this object to gracefully terminate before it will be removed from the system. Only set when deletionTimestamp is also set. May only be shortened. Read-only.</p>
</td>
</tr>
<tr id="row73343395199"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p83341439191916"><a name="p83341439191916"></a><a name="p83341439191916"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p333433915197"><a name="p333433915197"></a><a name="p333433915197"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1833493916193"><a name="p1833493916193"></a><a name="p1833493916193"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p142260512117"><a name="p142260512117"></a><a name="p142260512117"></a>DeletionTimestamp is RFC 3339 date and time at which this resource will be deleted. This field is set by the server when a graceful deletion is requested by the user, and is not directly settable by a client. The resource is expected to be deleted (no longer visible from resource lists, and not reachable by name) after the time in this field, once the finalizers list is empty. As long as the finalizers list contains items, deletion is blocked. Once the deletionTimestamp is set, this value may not be unset or be set further into the future, although it may be shortened or the resource may be deleted prior to this time. For example, a user may request that a pod is deleted in 30 seconds. The Kubelet will react by sending a graceful termination signal to the containers in the pod. After that 30 seconds, the Kubelet will send a hard termination signal (SIGKILL) to the container and after cleanup, remove the pod from the API. In the presence of network partitions, this object may still exist after this timestamp, until an administrator or automated process can determine the resource is fully terminated. If not set, graceful deletion of the object has not been requested.</p>
<p id="p182261859217"><a name="p182261859217"></a><a name="p182261859217"></a>Populated by the system when a graceful deletion is requested. Read-only.</p>
</td>
</tr>
<tr id="row1323812362219"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p19238113682110"><a name="p19238113682110"></a><a name="p19238113682110"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p2238153619213"><a name="p2238153619213"></a><a name="p2238153619213"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1023883616213"><a name="p1023883616213"></a><a name="p1023883616213"></a>&lt; string &gt; array</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p16238736112120"><a name="p16238736112120"></a><a name="p16238736112120"></a>Must be empty before the object is deleted from the registry. Each entry is an identifier for the responsible component that will remove the entry from the list. If the deletionTimestamp of the object is non-nil, entries in this list can only be removed.</p>
</td>
</tr>
<tr id="row54415193223"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p84471992210"><a name="p84471992210"></a><a name="p84471992210"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p154421962217"><a name="p154421962217"></a><a name="p154421962217"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p13441219182217"><a name="p13441219182217"></a><a name="p13441219182217"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p619664919227"><a name="p619664919227"></a><a name="p619664919227"></a>If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header).</p>
<p id="p111961949132220"><a name="p111961949132220"></a><a name="p111961949132220"></a>Applied only if Name is not specified.</p>
</td>
</tr>
<tr id="row14389026102214"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p1638912261228"><a name="p1638912261228"></a><a name="p1638912261228"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p138972692215"><a name="p138972692215"></a><a name="p138972692215"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p938919263228"><a name="p938919263228"></a><a name="p938919263228"></a>integer(int64)</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p20389102617222"><a name="p20389102617222"></a><a name="p20389102617222"></a>A sequence number representing a specific generation of the desired state. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row7286428132210"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p1628602842215"><a name="p1628602842215"></a><a name="p1628602842215"></a>initializers</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p528613288229"><a name="p528613288229"></a><a name="p528613288229"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p72861289222"><a name="p72861289222"></a><a name="p72861289222"></a><a href="公共请求参数.md#t693768b66dfa47239c0f155ad4dd18e8">表14</a></p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p2875101613239"><a name="p2875101613239"></a><a name="p2875101613239"></a>An initializer is a controller which enforces some system invariant at object creation time. This field is a list of initializers that have not yet acted on this object. If nil or empty, this object has been completely initialized. Otherwise, the object is considered uninitialized and is hidden (in list/watch and get calls) from clients that haven’t explicitly asked to observe uninitialized objects.</p>
<p id="p6875616152317"><a name="p6875616152317"></a><a name="p6875616152317"></a>When an object is created, the system will populate this list with the current set of initializers. Only privileged users may set or modify this list. Once it is empty, it may not be modified further by any user.</p>
</td>
</tr>
<tr id="row2469153416235"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p14469163413236"><a name="p14469163413236"></a><a name="p14469163413236"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p147083418238"><a name="p147083418238"></a><a name="p147083418238"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p6470634132312"><a name="p6470634132312"></a><a name="p6470634132312"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p104717345234"><a name="p104717345234"></a><a name="p104717345234"></a>Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services.</p>
</td>
</tr>
<tr id="row9249184492313"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p1324912446231"><a name="p1324912446231"></a><a name="p1324912446231"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p12491442236"><a name="p12491442236"></a><a name="p12491442236"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p2024954412311"><a name="p2024954412311"></a><a name="p2024954412311"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p9249154482310"><a name="p9249154482310"></a><a name="p9249154482310"></a>Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated.</p>
</td>
</tr>
<tr id="row12444144010238"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p64441840152320"><a name="p64441840152320"></a><a name="p64441840152320"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p19444540122316"><a name="p19444540122316"></a><a name="p19444540122316"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p144417403230"><a name="p144417403230"></a><a name="p144417403230"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p12732184617241"><a name="p12732184617241"></a><a name="p12732184617241"></a>Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty.</p>
<p id="p3732154619242"><a name="p3732154619242"></a><a name="p3732154619242"></a>Must be a DNS_LABEL. Cannot be updated.</p>
</td>
</tr>
<tr id="row461716372238"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p561717377234"><a name="p561717377234"></a><a name="p561717377234"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p12617133782317"><a name="p12617133782317"></a><a name="p12617133782317"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p261773702319"><a name="p261773702319"></a><a name="p261773702319"></a>array</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p11617183710234"><a name="p11617183710234"></a><a name="p11617183710234"></a>List of objects depended by this object. If ALL objects in the list have been deleted, this object will be garbage collected. If this object is managed by a controller, then an entry in this list will point to this controller, with the controller field set to true. There cannot be more than one managing controller.</p>
</td>
</tr>
<tr id="row13222218257"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p53223217255"><a name="p53223217255"></a><a name="p53223217255"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p532215242511"><a name="p532215242511"></a><a name="p532215242511"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p12322321251"><a name="p12322321251"></a><a name="p12322321251"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p20785858182511"><a name="p20785858182511"></a><a name="p20785858182511"></a>An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources.</p>
<p id="p107851058122512"><a name="p107851058122512"></a><a name="p107851058122512"></a>Populated by the system. Read-only. Value must be treated as opaque by clients and .</p>
</td>
</tr>
<tr id="row13173092511"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p101719017252"><a name="p101719017252"></a><a name="p101719017252"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p6173016255"><a name="p6173016255"></a><a name="p6173016255"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p81813052517"><a name="p81813052517"></a><a name="p81813052517"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p11811013257"><a name="p11811013257"></a><a name="p11811013257"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row12738145612247"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p13738135616240"><a name="p13738135616240"></a><a name="p13738135616240"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p12738145682415"><a name="p12738145682415"></a><a name="p12738145682415"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p67382567242"><a name="p67382567242"></a><a name="p67382567242"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p2092415714264"><a name="p2092415714264"></a><a name="p2092415714264"></a>UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations.</p>
<p id="p149248782613"><a name="p149248782613"></a><a name="p149248782613"></a>Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  RoleRef字段数据结构说明

<a name="table8814183942020"></a>
<table><thead align="left"><tr id="row12823103972010"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.5.1.1"><p id="p1382533916207"><a name="p1382533916207"></a><a name="p1382533916207"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.5.1.2"><p id="p18828123910207"><a name="p18828123910207"></a><a name="p18828123910207"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p9829739102014"><a name="p9829739102014"></a><a name="p9829739102014"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39%" id="mcps1.2.5.1.4"><p id="p15831539202013"><a name="p15831539202013"></a><a name="p15831539202013"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row188359394200"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p53238363210"><a name="p53238363210"></a><a name="p53238363210"></a>apiGroup</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p8839203932019"><a name="p8839203932019"></a><a name="p8839203932019"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p28416390206"><a name="p28416390206"></a><a name="p28416390206"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p15843163972020"><a name="p15843163972020"></a><a name="p15843163972020"></a>APIGroup is the group for the resource being referenced.</p>
</td>
</tr>
<tr id="row20765923152119"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p276512310213"><a name="p276512310213"></a><a name="p276512310213"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p3433816192214"><a name="p3433816192214"></a><a name="p3433816192214"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p243581614225"><a name="p243581614225"></a><a name="p243581614225"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p1876615231217"><a name="p1876615231217"></a><a name="p1876615231217"></a>Kind is the type of resource being referenced.</p>
</td>
</tr>
<tr id="row9449122714217"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p1144911271218"><a name="p1144911271218"></a><a name="p1144911271218"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p1533031713226"><a name="p1533031713226"></a><a name="p1533031713226"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p63321117202212"><a name="p63321117202212"></a><a name="p63321117202212"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p844913274212"><a name="p844913274212"></a><a name="p844913274212"></a>Name is the name of resource being referenced.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  Subject字段数据结构说明

<a name="table172861541152017"></a>
<table><thead align="left"><tr id="row9293124115202"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.5.1.1"><p id="p229518417209"><a name="p229518417209"></a><a name="p229518417209"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.5.1.2"><p id="p2297184132012"><a name="p2297184132012"></a><a name="p2297184132012"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1529984114207"><a name="p1529984114207"></a><a name="p1529984114207"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39%" id="mcps1.2.5.1.4"><p id="p830174112202"><a name="p830174112202"></a><a name="p830174112202"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6304141132013"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p1745310474233"><a name="p1745310474233"></a><a name="p1745310474233"></a>apiGroup</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p6720820172211"><a name="p6720820172211"></a><a name="p6720820172211"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1072212019222"><a name="p1072212019222"></a><a name="p1072212019222"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p183102041112013"><a name="p183102041112013"></a><a name="p183102041112013"></a>APIGroup holds the API group of the referenced subject. Defaults to "" for ServiceAccount subjects. Defaults to "rbac.authorization.k8s.io" for User and Group subjects.</p>
</td>
</tr>
<tr id="row1657144717223"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p16572473226"><a name="p16572473226"></a><a name="p16572473226"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p14552182152316"><a name="p14552182152316"></a><a name="p14552182152316"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p12555142142313"><a name="p12555142142313"></a><a name="p12555142142313"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p19571447132212"><a name="p19571447132212"></a><a name="p19571447132212"></a>Kind of object being referenced. Values defined by this API group are "User", "Group", and "ServiceAccount". If the Authorizer does not recognized the kind value, the Authorizer should report an error.</p>
</td>
</tr>
<tr id="row66575672214"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p13651356122218"><a name="p13651356122218"></a><a name="p13651356122218"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p1215612320236"><a name="p1215612320236"></a><a name="p1215612320236"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p5160153172312"><a name="p5160153172312"></a><a name="p5160153172312"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p7651956132218"><a name="p7651956132218"></a><a name="p7651956132218"></a>Name of the object being referenced.</p>
</td>
</tr>
<tr id="row165195602213"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p1065125616221"><a name="p1065125616221"></a><a name="p1065125616221"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.2 "><p id="p1068913392319"><a name="p1068913392319"></a><a name="p1068913392319"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1569173182318"><a name="p1569173182318"></a><a name="p1569173182318"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p126555672217"><a name="p126555672217"></a><a name="p126555672217"></a>Namespace of the referenced object. If the object kind is non-namespace, such as "User" or "Group", and this value is not empty the Authorizer should report an error.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
# 以下角色绑定定义将允许用户"jane"从"default"命名空间中读取pod。
{
   "kind": "RoleBinding",
   "apiVersion": "rbac.authorization.k8s.io/v1",
   "metadata": {
       "name": "read-pods",
	   "namespace": "default"
	},
   "subjects":[{
       "kind": "User",
       "name": "jane",
       "apiGroup": "rbac.authorization.k8s.io"
	}],
   "roleRef":{
       "kind": "Role",
       "name": "pod-reader",
       "apiGroup": "rbac.authorization.k8s.io"}
}
```

## 响应消息<a name="section13598181712916"></a>

**响应参数：**

响应参数的详细描述请参见[请求参数](#d0e42951)。

**响应示例：**

```
{
    "kind" : "RoleBinding",
    "apiVersion" : "rbac.authorization.k8s.io/v1",
    "metadata" : {
        "name" : "read-pods",
        "namespace" : "default",
        "selfLink" : "/apis/rbac.authorization.k8s.io/v1/namespaces/default/rolebindings/secret-reader",
        "uid" : "b3d1a49a-f1f4-11e8-b449-fa163ec24e06",
        "resourceVersion" : "16611",
        "creationTimestamp" : "2018-11-27T03:29:52Z"
    },
    "subjects" : [ {
        "kind" : "User",
        "apiGroup" : "rbac.authorization.k8s.io",
        "name" : "jane"
    } ],
    "roleRef" : {
        "apiGroup" : "rbac.authorization.k8s.io",
        "kind" : "Role",
        "name" : "pod-reader"
    }
}
```

## 状态码<a name="section14947131610112"></a>

[状态码](#d0e43055)描述API的状态码。

**表 6**  状态码

<a name="d0e43055"></a>
<table><thead align="left"><tr id="row20813512"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p8172937"><a name="p8172937"></a><a name="p8172937"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p58028199"><a name="p58028199"></a><a name="p58028199"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2663689"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p14432280"><a name="p14432280"></a><a name="p14432280"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p13489144118012"><a name="p13489144118012"></a><a name="p13489144118012"></a>Created</p>
</td>
</tr>
<tr id="row19571497408"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p886495133310"><a name="p886495133310"></a><a name="p886495133310"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1786435113335"><a name="p1786435113335"></a><a name="p1786435113335"></a>OK</p>
</td>
</tr>
<tr id="row24255539400"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p13311555103311"><a name="p13311555103311"></a><a name="p13311555103311"></a>202</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p731165523310"><a name="p731165523310"></a><a name="p731165523310"></a>Accepted</p>
</td>
</tr>
</tbody>
</table>

