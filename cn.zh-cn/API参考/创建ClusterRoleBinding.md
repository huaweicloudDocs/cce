# 创建ClusterRoleBinding<a name="cce_02_0294"></a>

## 功能介绍<a name="section8881601595"></a>

This API is used to create a ClusterRoleBinding

## URL<a name="section22432013155911"></a>

POST /apis/rbac.authorization.k8s.io/v1/clusterrolebindings

[参数解释](#table1420670321)描述该API的参数。

**表 1**  参数解释

<a name="table1420670321"></a>
<table><thead align="left"><tr id="row13419167183218"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p164191473326"><a name="p164191473326"></a><a name="p164191473326"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p041910713219"><a name="p041910713219"></a><a name="p041910713219"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.61%" id="mcps1.2.4.1.3"><p id="p174195753211"><a name="p174195753211"></a><a name="p174195753211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1541915711328"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p5419873324"><a name="p5419873324"></a><a name="p5419873324"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p7419167133218"><a name="p7419167133218"></a><a name="p7419167133218"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p941918773219"><a name="p941918773219"></a><a name="p941918773219"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row1442011716321"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p164190723212"><a name="p164190723212"></a><a name="p164190723212"></a>body</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p1941911703216"><a name="p1941911703216"></a><a name="p1941911703216"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p14419107123212"><a name="p14419107123212"></a><a name="p14419107123212"></a><a href="#d0e42951">请求参数</a></p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section662381310137"></a>

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
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p1977810533112"><a name="p1977810533112"></a><a name="p1977810533112"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="row899203"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p1177617531118"><a name="p1177617531118"></a><a name="p1177617531118"></a>roleRef</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p4774175316112"><a name="p4774175316112"></a><a name="p4774175316112"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p157721753151112"><a name="p157721753151112"></a><a name="p157721753151112"></a><a href="#zh-cn_topic_0079615000_table58989182">roleref字段数据结构说明</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p19771175311119"><a name="p19771175311119"></a><a name="p19771175311119"></a>RoleRef can only reference a ClusterRole in the global namespace. If the RoleRef cannot be resolved, the Authorizer must return an error.</p>
</td>
</tr>
<tr id="row10626123014167"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p3626163014166"><a name="p3626163014166"></a><a name="p3626163014166"></a>subjects</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p06261630201619"><a name="p06261630201619"></a><a name="p06261630201619"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p13626530181618"><a name="p13626530181618"></a><a name="p13626530181618"></a><a href="#table0504127112315">subjects字段数据结构说明</a> array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p462643012160"><a name="p462643012160"></a><a name="p462643012160"></a>Subjects holds references to the objects the role applies to.</p>
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
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p101482549231"><a name="p101482549231"></a><a name="p101482549231"></a>CreationTimestamp is a timestamp representing the server time when this object was created. It is not guaranteed to be set in happens-before order across separate operations. Clients may not set this value. It is represented in RFC3339 form and is in UTC. Populated by the system. Read-only. Null for lists.</p>
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
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p159875142520"><a name="p159875142520"></a><a name="p159875142520"></a>DeletionTimestamp is RFC 3339 date and time at which this resource will be deleted. This field is set by the server when a graceful deletion is requested by the user, and is not directly settable by a client. The resource is expected to be deleted (no longer visible from resource lists, and not reachable by name) after the time in this field, once the finalizers list is empty. As long as the finalizers list contains items, deletion is blocked. Once the deletionTimestamp is set, this value may not be unset or be set further into the future, although it may be shortened or the resource may be deleted prior to this time. For example, a user may request that a pod is deleted in 30 seconds. The Kubelet will react by sending a graceful termination signal to the containers in the pod. After that 30 seconds, the Kubelet will send a hard termination signal (SIGKILL) to the container and after cleanup, remove the pod from the API. In the presence of network partitions, this object may still exist after this timestamp, until an administrator or automated process can determine the resource is fully terminated. If not set, graceful deletion of the object has not been requested. Populated by the system when a graceful deletion is requested. Read-only.</p>
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
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p111961949132220"><a name="p111961949132220"></a><a name="p111961949132220"></a>GenerateName is an optional prefix, used by the server, to generate a unique name ONLY IF the Name field has not been provided. If this field is used, the name returned to the client will be different than the name passed. This value will also be combined with a unique suffix. The provided value has the same validation rules as the Name field, and may be truncated by the length of the suffix required to make the value unique on the server. If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header). Applied only if Name is not specified.</p>
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
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p6875616152317"><a name="p6875616152317"></a><a name="p6875616152317"></a>An initializer is a controller which enforces some system invariant at object creation time. This field is a list of initializers that have not yet acted on this object. If nil or empty, this object has been completely initialized. Otherwise, the object is considered uninitialized and is hidden (in list/watch and get calls) from clients that haven't explicitly asked to observe uninitialized objects. When an object is created, the system will populate this list with the current set of initializers. Only privileged users may set or modify this list. Once it is empty, it may not be modified further by any user.</p>
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
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p3732154619242"><a name="p3732154619242"></a><a name="p3732154619242"></a>Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty. Must be a DNS_LABEL. Cannot be updated.</p>
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
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p107851058122512"><a name="p107851058122512"></a><a name="p107851058122512"></a>An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources. Populated by the system. Read-only. Value must be treated as opaque by clients and .</p>
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
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.5.1.4 "><p id="p149248782613"><a name="p149248782613"></a><a name="p149248782613"></a>UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  roleref字段数据结构说明

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
<tbody><tr id="zh-cn_topic_0079615000_row59285030"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079615000_p37358106"><a name="zh-cn_topic_0079615000_p37358106"></a><a name="zh-cn_topic_0079615000_p37358106"></a>apiGroup</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079615000_p6107739"><a name="zh-cn_topic_0079615000_p6107739"></a><a name="zh-cn_topic_0079615000_p6107739"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079615000_p24964816"><a name="zh-cn_topic_0079615000_p24964816"></a><a name="zh-cn_topic_0079615000_p24964816"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p97961317123012"><a name="p97961317123012"></a><a name="p97961317123012"></a>APIGroup is the group for the resource being referenced.</p>
</td>
</tr>
<tr id="r84d3b4cd4c354a7b8d2c2d8e643f2eb2"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a20c290dec91e461f9806ac7ddb64b32e"><a name="a20c290dec91e461f9806ac7ddb64b32e"></a><a name="a20c290dec91e461f9806ac7ddb64b32e"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a792005b9cc9c4b62aa05ca6ba72edb1b"><a name="a792005b9cc9c4b62aa05ca6ba72edb1b"></a><a name="a792005b9cc9c4b62aa05ca6ba72edb1b"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a9fd3a2cf6b17488ebf787d90dcdd4806"><a name="a9fd3a2cf6b17488ebf787d90dcdd4806"></a><a name="a9fd3a2cf6b17488ebf787d90dcdd4806"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="aaca6cae38740430c8d9c48adc947545c"><a name="aaca6cae38740430c8d9c48adc947545c"></a><a name="aaca6cae38740430c8d9c48adc947545c"></a>Kind is the type of resource being referenced.</p>
</td>
</tr>
<tr id="row823812573016"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p10323185414332"><a name="p10323185414332"></a><a name="p10323185414332"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p52382510302"><a name="p52382510302"></a><a name="p52382510302"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p323813563014"><a name="p323813563014"></a><a name="p323813563014"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p2023814519307"><a name="p2023814519307"></a><a name="p2023814519307"></a>Name is the name of resource being referenced.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  subjects字段数据结构说明

<a name="table0504127112315"></a>
<table><thead align="left"><tr id="row6513112742318"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="p195151827102314"><a name="p195151827102314"></a><a name="p195151827102314"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p195181827182318"><a name="p195181827182318"></a><a name="p195181827182318"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p25211827172312"><a name="p25211827172312"></a><a name="p25211827172312"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p5523427192315"><a name="p5523427192315"></a><a name="p5523427192315"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1652572716231"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p205265279236"><a name="p205265279236"></a><a name="p205265279236"></a>apiGroup</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p35282274231"><a name="p35282274231"></a><a name="p35282274231"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p195309278232"><a name="p195309278232"></a><a name="p195309278232"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p6531152752318"><a name="p6531152752318"></a><a name="p6531152752318"></a>APIGroup is the group for the resource being referenced.</p>
</td>
</tr>
<tr id="row1653282772313"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p35345279239"><a name="p35345279239"></a><a name="p35345279239"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p18536102715233"><a name="p18536102715233"></a><a name="p18536102715233"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p5537172732318"><a name="p5537172732318"></a><a name="p5537172732318"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p17539127172319"><a name="p17539127172319"></a><a name="p17539127172319"></a>Kind is the type of resource being referenced.</p>
</td>
</tr>
<tr id="row5540142714236"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p054212752320"><a name="p054212752320"></a><a name="p054212752320"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p15447279235"><a name="p15447279235"></a><a name="p15447279235"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p10546162715233"><a name="p10546162715233"></a><a name="p10546162715233"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p145481627192312"><a name="p145481627192312"></a><a name="p145481627192312"></a>Name is the name of resource being referenced.</p>
</td>
</tr>
<tr id="row15381250102420"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="p23835017247"><a name="p23835017247"></a><a name="p23835017247"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="p10170158112415"><a name="p10170158112415"></a><a name="p10170158112415"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="p917365818244"><a name="p917365818244"></a><a name="p917365818244"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="p1838145032417"><a name="p1838145032417"></a><a name="p1838145032417"></a>Namespace of the referenced object. If the object kind is non-namespace, such as "User" or "Group", and this value is not empty the Authorizer should report an error.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
# 以下`ClusterRoleBinding`对象允许在用户组"manager"中的任何用户都可以读取集群中任何名字空间中的secret。
{
   "kind": "ClusterRoleBinding",
   "apiVersion": "rbac.authorization.k8s.io/v1beta1",
   "metadata": {
       "name": "read-secrets-global"
	},
   "subjects":[{
       "kind": "Group",
       "name": "manager",
       "apiGroup": "rbac.authorization.k8s.io"
	}],
   "roleRef":{
       "kind": "ClusterRole",
       "name": "secret-reader",
       "apiGroup": "rbac.authorization.k8s.io"}
}
```

## 响应消息<a name="section294685611597"></a>

**响应参数：**

响应参数的详细描述请参见[表2](#d0e42951)。

**响应示例：**

```
{
    "kind" : "ClusterRoleBinding",
    "apiVersion" : "rbac.authorization.k8s.io/v1",
    "metadata" : {
        "name" : "read-secrets-global",
        "selfLink" : "/apis/rbac.authorization.k8s.io/v1/clusterrolebindings/read-secrets-global",
        "uid" : "8e20ec38-f1e7-11e8-b449-fa163ec24e06",
        "resourceVersion" : "4625",
        "creationTimestamp" : "2018-11-27T01:55:45Z"
    },
    "subjects" : [ {
        "kind" : "Group",
        "apiGroup" : "rbac.authorization.k8s.io",
        "name" : "manager"
    } ],
    "roleRef" : {
        "apiGroup" : "rbac.authorization.k8s.io",
        "kind" : "ClusterRole",
        "name" : "secret-reader"
    }
}
```

## 状态码<a name="section7688181432015"></a>

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
<tr id="row681622103615"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p886495133310"><a name="p886495133310"></a><a name="p886495133310"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1786435113335"><a name="p1786435113335"></a><a name="p1786435113335"></a>OK</p>
</td>
</tr>
<tr id="row4272925153610"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p13311555103311"><a name="p13311555103311"></a><a name="p13311555103311"></a>202</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p731165523310"><a name="p731165523310"></a><a name="p731165523310"></a>Accepted</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

