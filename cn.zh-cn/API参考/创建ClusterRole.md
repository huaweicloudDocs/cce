# 创建ClusterRole<a name="ZH-CN_TOPIC_0140918301"></a>

## 功能介绍<a name="section6913131642116"></a>

This API is used to create a ClusterRole

## URL<a name="section1943132116"></a>

POST /apis/rbac.authorization.k8s.io/v1/clusterroles

[参数解释](#d0e42906)描述该API的参数。

**表 1**  参数解释

<a name="table161311441165415"></a>
<table><thead align="left"><tr id="row3134641185412"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p91351441105413"><a name="p91351441105413"></a><a name="p91351441105413"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p1313620411541"><a name="p1313620411541"></a><a name="p1313620411541"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.61%" id="mcps1.2.4.1.3"><p id="p1136134112541"><a name="p1136134112541"></a><a name="p1136134112541"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row14140184135413"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p10141114175415"><a name="p10141114175415"></a><a name="p10141114175415"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p8142104111543"><a name="p8142104111543"></a><a name="p8142104111543"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p1143104195410"><a name="p1143104195410"></a><a name="p1143104195410"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row51431541115410"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p10144124112543"><a name="p10144124112543"></a><a name="p10144124112543"></a>body</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p614510411547"><a name="p614510411547"></a><a name="p614510411547"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p46408710414"><a name="p46408710414"></a><a name="p46408710414"></a><a href="#table1154814995615">请求参数</a></p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section18662134312520"></a>

**请求参数：**

请求参数如[请求参数](#d0e42951)所示。

**表 2**  请求参数

<a name="table1154814995615"></a>
<table><thead align="left"><tr id="row455284915618"><th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.5.1.1"><p id="p15553124911564"><a name="p15553124911564"></a><a name="p15553124911564"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.141414141414144%" id="mcps1.2.5.1.2"><p id="p85551499565"><a name="p85551499565"></a><a name="p85551499565"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.5.1.3"><p id="p125561849185616"><a name="p125561849185616"></a><a name="p125561849185616"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.43434343434344%" id="mcps1.2.5.1.4"><p id="p205571649135612"><a name="p205571649135612"></a><a name="p205571649135612"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1755864955619"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p1055914499565"><a name="p1055914499565"></a><a name="p1055914499565"></a>aggregationRule</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p7560174915565"><a name="p7560174915565"></a><a name="p7560174915565"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p20561104917566"><a name="p20561104917566"></a><a name="p20561104917566"></a><a href="#d0e42951">AggregationRule字段数据结构说明</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p75621249205619"><a name="p75621249205619"></a><a name="p75621249205619"></a>AggregationRule is an optional field that describes how to build the Rules for this ClusterRole. If AggregationRule is set, then the Rules are controller managed and direct changes to Rules will be stomped by the controller.</p>
</td>
</tr>
<tr id="row1478130175710"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p12478130105717"><a name="p12478130105717"></a><a name="p12478130105717"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p9120422579"><a name="p9120422579"></a><a name="p9120422579"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p101319428574"><a name="p101319428574"></a><a name="p101319428574"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p547913304576"><a name="p547913304576"></a><a name="p547913304576"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row10563349125616"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p85631049125619"><a name="p85631049125619"></a><a name="p85631049125619"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p8564164920566"><a name="p8564164920566"></a><a name="p8564164920566"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p115651494566"><a name="p115651494566"></a><a name="p115651494566"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p125661749135618"><a name="p125661749135618"></a><a name="p125661749135618"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="row36873674"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p6785175341110"><a name="p6785175341110"></a><a name="p6785175341110"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p1378375321115"><a name="p1378375321115"></a><a name="p1378375321115"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p1578195321111"><a name="p1578195321111"></a><a name="p1578195321111"></a><a href="#table866915511559">metadata字段数据结构说明</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p1977810533112"><a name="p1977810533112"></a><a name="p1977810533112"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="row899203"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p1177617531118"><a name="p1177617531118"></a><a name="p1177617531118"></a>rules</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p4774175316112"><a name="p4774175316112"></a><a name="p4774175316112"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p73260102467"><a name="p73260102467"></a><a name="p73260102467"></a><a href="#table157813483553">PolicyRule字段数据结构说明</a> array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p19771175311119"><a name="p19771175311119"></a><a name="p19771175311119"></a>Rules holds all the PolicyRules for this ClusterRole</p>
</td>
</tr>
</tbody>
</table>

**表 3**  AggregationRule字段数据结构说明

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
<tbody><tr id="row772562671320"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p772532621317"><a name="p772532621317"></a><a name="p772532621317"></a>clusterRoleSelectors</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p16725132617134"><a name="p16725132617134"></a><a name="p16725132617134"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p17725142619139"><a name="p17725142619139"></a><a name="p17725142619139"></a>array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p1772519266135"><a name="p1772519266135"></a><a name="p1772519266135"></a>ClusterRoleSelectors holds a list of selectors which will be used to find ClusterRoles and create the rules. If any of the selectors match, then the ClusterRole's permissions will be added.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  metadata字段数据结构说明

<a name="table204271324125219"></a>
<table><thead align="left"><tr id="row1942919240529"><th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.5.1.1"><p id="p2042942415210"><a name="p2042942415210"></a><a name="p2042942415210"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.141414141414144%" id="mcps1.2.5.1.2"><p id="p18430122495210"><a name="p18430122495210"></a><a name="p18430122495210"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.5.1.3"><p id="p11430122413526"><a name="p11430122413526"></a><a name="p11430122413526"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.43434343434344%" id="mcps1.2.5.1.4"><p id="p54311824115213"><a name="p54311824115213"></a><a name="p54311824115213"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row11431122475213"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p9432192445213"><a name="p9432192445213"></a><a name="p9432192445213"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p743262455214"><a name="p743262455214"></a><a name="p743262455214"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p3433724145219"><a name="p3433724145219"></a><a name="p3433724145219"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p9433824145212"><a name="p9433824145212"></a><a name="p9433824145212"></a>Annotations is an unstructured key value map stored with a resource that may be set by external tools to store and retrieve arbitrary metadata. They are not queryable and should be preserved when modifying objects.</p>
</td>
</tr>
<tr id="row12433182410522"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p3434624115217"><a name="p3434624115217"></a><a name="p3434624115217"></a>clusterName</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p5434924115214"><a name="p5434924115214"></a><a name="p5434924115214"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p10435524165219"><a name="p10435524165219"></a><a name="p10435524165219"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p17435192455217"><a name="p17435192455217"></a><a name="p17435192455217"></a>The name of the cluster which the object belongs to. This is used to distinguish resources with same name and namespace in different clusters. This field is not set anywhere right now and apiserver is going to ignore it if set in create or update request.</p>
</td>
</tr>
<tr id="row1711724133012"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p1711734153013"><a name="p1711734153013"></a><a name="p1711734153013"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p9117248305"><a name="p9117248305"></a><a name="p9117248305"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p1611794153011"><a name="p1611794153011"></a><a name="p1611794153011"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p311744163019"><a name="p311744163019"></a><a name="p311744163019"></a>CreationTimestamp is a timestamp representing the server time when this object was created. It is not guaranteed to be set in happens-before order across separate operations. Clients may not set this value. It is represented in RFC3339 form and is in UTC. Populated by the system. Read-only. Null for lists.</p>
</td>
</tr>
<tr id="row1014737163019"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p414711718306"><a name="p414711718306"></a><a name="p414711718306"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p61471710305"><a name="p61471710305"></a><a name="p61471710305"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p71471716302"><a name="p71471716302"></a><a name="p71471716302"></a>integer(int64)</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p1714710714304"><a name="p1714710714304"></a><a name="p1714710714304"></a>Number of seconds allowed for this object to gracefully terminate before it will be removed from the system. Only set when deletionTimestamp is also set. May only be shortened.</p>
</td>
</tr>
<tr id="row1652651343118"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p185261713193116"><a name="p185261713193116"></a><a name="p185261713193116"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p652641343113"><a name="p652641343113"></a><a name="p652641343113"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p2526171303115"><a name="p2526171303115"></a><a name="p2526171303115"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p6526713173110"><a name="p6526713173110"></a><a name="p6526713173110"></a>DeletionTimestamp is RFC 3339 date and time at which this resource will be deleted. This field is set by the server when a graceful deletion is requested by the user, and is not directly settable by a client. The resource is expected to be deleted (no longer visible from resource lists, and not reachable by name) after the time in this field, once the finalizers list is empty. As long as the finalizers list contains items, deletion is blocked. Once the deletionTimestamp is set, this value may not be unset or be set further into the future, although it may be shortened or the resource may be deleted prior to this time. For example, a user may request that a pod is deleted in 30 seconds. The Kubelet will react by sending a graceful termination signal to the containers in the pod. After that 30 seconds, the Kubelet will send a hard termination signal (SIGKILL) to the container and after cleanup, remove the pod from the API. In the presence of network partitions, this object may still exist after this timestamp, until an administrator or automated process can determine the resource is fully terminated. If not set, graceful deletion of the object has not been requested. Populated by the system when a graceful deletion is requested. Read-only.</p>
</td>
</tr>
<tr id="row966131813312"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p06721883111"><a name="p06721883111"></a><a name="p06721883111"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p1067718183116"><a name="p1067718183116"></a><a name="p1067718183116"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p186751853117"><a name="p186751853117"></a><a name="p186751853117"></a>string(array)</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p767161843113"><a name="p767161843113"></a><a name="p767161843113"></a>Must be empty before the object is deleted from the registry. Each entry is an identifier for the responsible component that will remove the entry from the list. If the deletionTimestamp of the object is non-nil, entries in this list can only be removed.</p>
</td>
</tr>
<tr id="row294017205317"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p294042093115"><a name="p294042093115"></a><a name="p294042093115"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p17940820103116"><a name="p17940820103116"></a><a name="p17940820103116"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p1394062013317"><a name="p1394062013317"></a><a name="p1394062013317"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p11940182011317"><a name="p11940182011317"></a><a name="p11940182011317"></a>GenerateName is an optional prefix, used by the server, to generate a unique name ONLY IF the Name field has not been provided. If this field is used, the name returned to the client will be different than the name passed. This value will also be combined with a unique suffix. The provided value has the same validation rules as the Name field, and may be truncated by the length of the suffix required to make the value unique on the server. If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header). Applied only if Name is not specified.</p>
</td>
</tr>
<tr id="row652202511314"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p852182513312"><a name="p852182513312"></a><a name="p852182513312"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p17526250311"><a name="p17526250311"></a><a name="p17526250311"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p25232517313"><a name="p25232517313"></a><a name="p25232517313"></a>integer(int64)</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p12814155216331"><a name="p12814155216331"></a><a name="p12814155216331"></a>A sequence number representing a specific generation of the desired state. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row144142093315"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p942207338"><a name="p942207338"></a><a name="p942207338"></a>initializers</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p34102013317"><a name="p34102013317"></a><a name="p34102013317"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p14182011335"><a name="p14182011335"></a><a name="p14182011335"></a><a href="公共请求参数.md#t693768b66dfa47239c0f155ad4dd18e8">表14</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p24220193314"><a name="p24220193314"></a><a name="p24220193314"></a>An initializer is a controller which enforces some system invariant at object creation time. This field is a list of initializers that have not yet acted on this object. If nil or empty, this object has been completely initialized. Otherwise, the object is considered uninitialized and is hidden (in list/watch and get calls) from clients that haven't explicitly asked to observe uninitialized objects. When an object is created, the system will populate this list with the current set of initializers. Only privileged users may set or modify this list. Once it is empty, it may not be modified further by any user.</p>
</td>
</tr>
<tr id="row5675143323316"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p20675203313336"><a name="p20675203313336"></a><a name="p20675203313336"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p147083418238"><a name="p147083418238"></a><a name="p147083418238"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p6470634132312"><a name="p6470634132312"></a><a name="p6470634132312"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p156754337335"><a name="p156754337335"></a><a name="p156754337335"></a>Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services.</p>
</td>
</tr>
<tr id="row6675633103315"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p0306076354"><a name="p0306076354"></a><a name="p0306076354"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p153083710357"><a name="p153083710357"></a><a name="p153083710357"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p163091475352"><a name="p163091475352"></a><a name="p163091475352"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p73111175354"><a name="p73111175354"></a><a name="p73111175354"></a>Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated.</p>
</td>
</tr>
<tr id="row1667653319338"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p1767618337334"><a name="p1767618337334"></a><a name="p1767618337334"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p12676933153312"><a name="p12676933153312"></a><a name="p12676933153312"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p1067615330332"><a name="p1067615330332"></a><a name="p1067615330332"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p1676193353316"><a name="p1676193353316"></a><a name="p1676193353316"></a>Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty. Must be a DNS_LABEL. Cannot be updated.</p>
</td>
</tr>
<tr id="row154555170356"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p204557172356"><a name="p204557172356"></a><a name="p204557172356"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p194551217103510"><a name="p194551217103510"></a><a name="p194551217103510"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p24551175353"><a name="p24551175353"></a><a name="p24551175353"></a>array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p184551417123511"><a name="p184551417123511"></a><a name="p184551417123511"></a>List of objects depended by this object. If ALL objects in the list have been deleted, this object will be garbage collected. If this object is managed by a controller, then an entry in this list will point to this controller, with the controller field set to true. There cannot be more than one managing controller.</p>
</td>
</tr>
<tr id="row1731917339352"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p83201133113512"><a name="p83201133113512"></a><a name="p83201133113512"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p232083323513"><a name="p232083323513"></a><a name="p232083323513"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p332073317357"><a name="p332073317357"></a><a name="p332073317357"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p6320153363513"><a name="p6320153363513"></a><a name="p6320153363513"></a>An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources. Populated by the system. Read-only. Value must be treated as opaque by clients and .</p>
</td>
</tr>
<tr id="row3320133193515"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p9320233143513"><a name="p9320233143513"></a><a name="p9320233143513"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p1320163383519"><a name="p1320163383519"></a><a name="p1320163383519"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p1832011338354"><a name="p1832011338354"></a><a name="p1832011338354"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p23202337356"><a name="p23202337356"></a><a name="p23202337356"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row1949154219351"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p154913425354"><a name="p154913425354"></a><a name="p154913425354"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p94924273515"><a name="p94924273515"></a><a name="p94924273515"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p249164273516"><a name="p249164273516"></a><a name="p249164273516"></a>string</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p19501142193512"><a name="p19501142193512"></a><a name="p19501142193512"></a>UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  PolicyRule字段数据结构说明

<a name="table157813483553"></a>
<table><thead align="left"><tr id="row78819487558"><th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.5.1.1"><p id="p88984811556"><a name="p88984811556"></a><a name="p88984811556"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.141414141414144%" id="mcps1.2.5.1.2"><p id="p119254815515"><a name="p119254815515"></a><a name="p119254815515"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.2.5.1.3"><p id="p119414818550"><a name="p119414818550"></a><a name="p119414818550"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.43434343434344%" id="mcps1.2.5.1.4"><p id="p39616488551"><a name="p39616488551"></a><a name="p39616488551"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1998144875516"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p13100148135517"><a name="p13100148135517"></a><a name="p13100148135517"></a>apiGroups</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p1110312484556"><a name="p1110312484556"></a><a name="p1110312484556"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p1105848175510"><a name="p1105848175510"></a><a name="p1105848175510"></a>string array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p141087482557"><a name="p141087482557"></a><a name="p141087482557"></a>APIGroups is the name of the APIGroup that contains the resources. If multiple API groups are specified, any action requested against one of the enumerated resources in any API group will be allowed.</p>
</td>
</tr>
<tr id="row1849255195810"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p16849115525816"><a name="p16849115525816"></a><a name="p16849115525816"></a>nonResourceURLs</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p19849185516585"><a name="p19849185516585"></a><a name="p19849185516585"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p58491555175810"><a name="p58491555175810"></a><a name="p58491555175810"></a>string array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p1684919559589"><a name="p1684919559589"></a><a name="p1684919559589"></a>NonResourceURLs is a set of partial urls that a user should have access to. *s are allowed, but only as the full, final step in the path Since non-resource URLs are not namespaced, this field is only applicable for ClusterRoles referenced from a ClusterRoleBinding. Rules can either apply to API resources (such as "pods" or "secrets") or non-resource URL paths (such as "/api"), but not both.</p>
</td>
</tr>
<tr id="row19120160165914"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p3120160125917"><a name="p3120160125917"></a><a name="p3120160125917"></a>resourceNames</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p91205035918"><a name="p91205035918"></a><a name="p91205035918"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p1012020105914"><a name="p1012020105914"></a><a name="p1012020105914"></a>string array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p91205035915"><a name="p91205035915"></a><a name="p91205035915"></a>ResourceNames is an optional white list of names that the rule applies to. An empty set means that everything is allowed.</p>
</td>
</tr>
<tr id="row8205416599"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p2020104155912"><a name="p2020104155912"></a><a name="p2020104155912"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p14206419596"><a name="p14206419596"></a><a name="p14206419596"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p15206485912"><a name="p15206485912"></a><a name="p15206485912"></a>string array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p172013415591"><a name="p172013415591"></a><a name="p172013415591"></a>Resources is a list of resources this rule applies to. ResourceAll represents all resources.</p>
</td>
</tr>
<tr id="row1258661265916"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.5.1.1 "><p id="p1558619125591"><a name="p1558619125591"></a><a name="p1558619125591"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="14.141414141414144%" headers="mcps1.2.5.1.2 "><p id="p19586191215597"><a name="p19586191215597"></a><a name="p19586191215597"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.2.5.1.3 "><p id="p175861112195911"><a name="p175861112195911"></a><a name="p175861112195911"></a>string array</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.5.1.4 "><p id="p95861212125919"><a name="p95861212125919"></a><a name="p95861212125919"></a>Verbs is a list of Verbs that apply to ALL the ResourceKinds and AttributeRestrictions contained in this rule. VerbAll represents all kinds.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
   "kind": "ClusterRole",
   "apiVersion": "rbac.authorization.k8s.io/v1",
   "metadata": {
       # 鉴于ClusterRole是集群范围对象，所以这里不需要定义"namespace"字段
       "name": "secret-reader"
	},
   "rules":[{
       "apiGroups": [""],
       "resources": ["secrets"],
       "verbs": ["get", "watch", "list"]
	}]
}
```

## 响应消息<a name="section13598181712916"></a>

**响应参数：**

响应参数的详细描述请参见[请求参数](#table1154814995615)。

**响应示例：**

```
{
    "kind" : "ClusterRole",
    "apiVersion" : "rbac.authorization.k8s.io/v1",
    "metadata" : {
        "name" : "secret-reader",
        "selfLink" : "/apis/rbac.authorization.k8s.io/v1/clusterroles/secret-reader",
        "uid" : "8d358854-f1e7-11e8-b449-fa163ec24e06",
        "resourceVersion" : "4619",
        "creationTimestamp" : "2018-11-27T01:55:44Z"
    },
    "rules" : [ {
        "verbs" : [ "get", "watch", "list" ],
        "apiGroups" : [ "" ],
        "resources" : [ "secrets" ]
    }]
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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p13489144118012"><a name="p13489144118012"></a><a name="p13489144118012"></a>success</p>
</td>
</tr>
</tbody>
</table>

