# 获取Resourcequotas<a name="cce_02_0337"></a>

## 功能介绍<a name="section14908183017187"></a>

list or watch objects of kind ResourceQuota.

## URI<a name="section89091530131814"></a>

GET /api/v1/resourcequotas

**表 1**  Query参数

<a name="table13914193017182"></a>
<table><thead align="left"><tr id="row5911123015187"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p391513051815"><a name="p391513051815"></a><a name="p391513051815"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="12.030000000000001%" id="mcps1.2.5.1.2"><p id="p0107538151812"><a name="p0107538151812"></a><a name="p0107538151812"></a>是否必须</p>
</th>
<th class="cellrowborder" valign="top" width="16.64%" id="mcps1.2.5.1.3"><p id="p8915153010184"><a name="p8915153010184"></a><a name="p8915153010184"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p1091711302188"><a name="p1091711302188"></a><a name="p1091711302188"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1991223081815"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p15918183011187"><a name="p15918183011187"></a><a name="p15918183011187"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p159641632199"><a name="p159641632199"></a><a name="p159641632199"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.64%" headers="mcps1.2.5.1.3 "><p id="p8918530131812"><a name="p8918530131812"></a><a name="p8918530131812"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p7919113013181"><a name="p7919113013181"></a><a name="p7919113013181"></a>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the "next key". This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</p>
</td>
</tr>
<tr id="row1912143031816"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p2092016309189"><a name="p2092016309189"></a><a name="p2092016309189"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p109647381911"><a name="p109647381911"></a><a name="p109647381911"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.64%" headers="mcps1.2.5.1.3 "><p id="p292073091810"><a name="p292073091810"></a><a name="p292073091810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1792110300181"><a name="p1792110300181"></a><a name="p1792110300181"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row169124302185"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p1922173014186"><a name="p1922173014186"></a><a name="p1922173014186"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p996420315197"><a name="p996420315197"></a><a name="p996420315197"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.64%" headers="mcps1.2.5.1.3 "><p id="p792215301184"><a name="p792215301184"></a><a name="p792215301184"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p092393021819"><a name="p092393021819"></a><a name="p092393021819"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row69125303187"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p39241730131814"><a name="p39241730131814"></a><a name="p39241730131814"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p79649314196"><a name="p79649314196"></a><a name="p79649314196"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.64%" headers="mcps1.2.5.1.3 "><p id="p492493012186"><a name="p492493012186"></a><a name="p492493012186"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p18925123031816"><a name="p18925123031816"></a><a name="p18925123031816"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row1791353010184"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p15926183071814"><a name="p15926183071814"></a><a name="p15926183071814"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p1096413317198"><a name="p1096413317198"></a><a name="p1096413317198"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.64%" headers="mcps1.2.5.1.3 "><p id="p892620305183"><a name="p892620305183"></a><a name="p892620305183"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p3927173020187"><a name="p3927173020187"></a><a name="p3927173020187"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the `continue` field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true. The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row19913103061812"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p10928193041814"><a name="p10928193041814"></a><a name="p10928193041814"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p99649381915"><a name="p99649381915"></a><a name="p99649381915"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.64%" headers="mcps1.2.5.1.3 "><p id="p14928113012189"><a name="p14928113012189"></a><a name="p14928113012189"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p18929630121814"><a name="p18929630121814"></a><a name="p18929630121814"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row6913530161818"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p7929330131815"><a name="p7929330131815"></a><a name="p7929330131815"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p996416331916"><a name="p996416331916"></a><a name="p996416331916"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.64%" headers="mcps1.2.5.1.3 "><p id="p12930103012187"><a name="p12930103012187"></a><a name="p12930103012187"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p4932113091815"><a name="p4932113091815"></a><a name="p4932113091815"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row18913183015183"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p093223014182"><a name="p093223014182"></a><a name="p093223014182"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p796413351919"><a name="p796413351919"></a><a name="p796413351919"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.64%" headers="mcps1.2.5.1.3 "><p id="p1593243019182"><a name="p1593243019182"></a><a name="p1593243019182"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p1593315303183"><a name="p1593315303183"></a><a name="p1593315303183"></a>Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity.</p>
</td>
</tr>
<tr id="row159132306187"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p593483019187"><a name="p593483019187"></a><a name="p593483019187"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p149656314191"><a name="p149656314191"></a><a name="p149656314191"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.64%" headers="mcps1.2.5.1.3 "><p id="p29341530181817"><a name="p29341530181817"></a><a name="p29341530181817"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p149351030151814"><a name="p149351030151814"></a><a name="p149351030151814"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section179351930141816"></a>

无

## 响应参数<a name="section1693618303187"></a>

状态码为 200 时:

**表 2**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row1393993012183"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p169421830111818"><a name="p169421830111818"></a><a name="p169421830111818"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1794273071814"><a name="p1794273071814"></a><a name="p1794273071814"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p7943143014181"><a name="p7943143014181"></a><a name="p7943143014181"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row20939113014188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p209442303182"><a name="p209442303182"></a><a name="p209442303182"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1894533011815"><a name="p1894533011815"></a><a name="p1894533011815"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1694543031812"><a name="p1694543031812"></a><a name="p1694543031812"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources</p>
</td>
</tr>
<tr id="row494073016185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p79461730161810"><a name="p79461730161810"></a><a name="p79461730161810"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1947113081815"><a name="p1947113081815"></a><a name="p1947113081815"></a>io.k8s.api.core.v1.ResourceQuota object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p4947230161812"><a name="p4947230161812"></a><a name="p4947230161812"></a>Items is a list of ResourceQuota objects. More info: https://kubernetes.io/docs/concepts/policy/resource-quotas/</p>
</td>
</tr>
<tr id="row094073011813"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p09481030141810"><a name="p09481030141810"></a><a name="p09481030141810"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p194893051817"><a name="p194893051817"></a><a name="p194893051817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p7948183041811"><a name="p7948183041811"></a><a name="p7948183041811"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row15940133051813"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1794913071818"><a name="p1794913071818"></a><a name="p1794913071818"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p994913071815"><a name="p994913071815"></a><a name="p994913071815"></a>io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p595053091819"><a name="p595053091819"></a><a name="p595053091819"></a>Standard list metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
</tbody>
</table>

**表 3**  io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta"></a>
<table><thead align="left"><tr id="row199551030181812"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1195843001811"><a name="p1195843001811"></a><a name="p1195843001811"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p99591230171815"><a name="p99591230171815"></a><a name="p99591230171815"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p996043011182"><a name="p996043011182"></a><a name="p996043011182"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row17955143012181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p296112308189"><a name="p296112308189"></a><a name="p296112308189"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p496113017184"><a name="p496113017184"></a><a name="p496113017184"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p196283061811"><a name="p196283061811"></a><a name="p196283061811"></a>continue may be set if the user set a limit on the number of items returned, and indicates that the server has more data available. The value is opaque and may be used to issue another request to the endpoint that served this list to retrieve the next set of available objects. Continuing a list may not be possible if the server configuration has changed or more than a few minutes have passed. The resourceVersion field returned when using this continue value will be identical to the value in the first response.</p>
</td>
</tr>
<tr id="row9955113017184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p149631830121813"><a name="p149631830121813"></a><a name="p149631830121813"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1096683081815"><a name="p1096683081815"></a><a name="p1096683081815"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1996619302182"><a name="p1996619302182"></a><a name="p1996619302182"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency</p>
</td>
</tr>
<tr id="row10956173013188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p69678307185"><a name="p69678307185"></a><a name="p69678307185"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1996812302185"><a name="p1996812302185"></a><a name="p1996812302185"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p15969330161816"><a name="p15969330161816"></a><a name="p15969330161816"></a>selfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  io.k8s.api.core.v1.ResourceQuota

<a name="response_io.k8s.api.core.v1.ResourceQuota"></a>
<table><thead align="left"><tr id="row4971163017182"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1897423014181"><a name="p1897423014181"></a><a name="p1897423014181"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1397413013186"><a name="p1397413013186"></a><a name="p1397413013186"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p2097519303185"><a name="p2097519303185"></a><a name="p2097519303185"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12971830141811"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1497510306184"><a name="p1497510306184"></a><a name="p1497510306184"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p3975193016185"><a name="p3975193016185"></a><a name="p3975193016185"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1297653071813"><a name="p1297653071813"></a><a name="p1297653071813"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources</p>
</td>
</tr>
<tr id="row09713303189"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1797743031816"><a name="p1797743031816"></a><a name="p1797743031816"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p197813015183"><a name="p197813015183"></a><a name="p197813015183"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17978133061815"><a name="p17978133061815"></a><a name="p17978133061815"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row49721530131816"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p129791830131815"><a name="p129791830131815"></a><a name="p129791830131815"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p29793307184"><a name="p29793307184"></a><a name="p29793307184"></a><a href="#response_io.k8s.apimachinery.pkg.apis.meta.v1.ObjectMeta">io.k8s.apimachinery.pkg.apis.meta.v1.ObjectMeta</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p498011301188"><a name="p498011301188"></a><a name="p498011301188"></a>Standard object's metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#metadata</p>
</td>
</tr>
<tr id="row4972630111819"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p209818304186"><a name="p209818304186"></a><a name="p209818304186"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p898163021814"><a name="p898163021814"></a><a name="p898163021814"></a><a href="#response_io.k8s.api.core.v1.ResourceQuotaSpec">io.k8s.api.core.v1.ResourceQuotaSpec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p5982183011183"><a name="p5982183011183"></a><a name="p5982183011183"></a>Spec defines the desired quota. https://git.k8s.io/community/contributors/devel/api-conventions.md#spec-and-status</p>
</td>
</tr>
<tr id="row199721030121812"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p498353041815"><a name="p498353041815"></a><a name="p498353041815"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p7984930151812"><a name="p7984930151812"></a><a name="p7984930151812"></a><a href="#response_io.k8s.api.core.v1.ResourceQuotaStatus">io.k8s.api.core.v1.ResourceQuotaStatus</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p698517307189"><a name="p698517307189"></a><a name="p698517307189"></a>Status defines the actual enforced quota and its current usage. https://git.k8s.io/community/contributors/devel/api-conventions.md#spec-and-status</p>
</td>
</tr>
</tbody>
</table>

**表 5**  io.k8s.api.core.v1.ResourceQuotaStatus

<a name="response_io.k8s.api.core.v1.ResourceQuotaStatus"></a>
<table><thead align="left"><tr id="row14987330151819"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p898953016186"><a name="p898953016186"></a><a name="p898953016186"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p159901430201819"><a name="p159901430201819"></a><a name="p159901430201819"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p2991103061817"><a name="p2991103061817"></a><a name="p2991103061817"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row898773016189"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p299123010186"><a name="p299123010186"></a><a name="p299123010186"></a>hard</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p0992930191817"><a name="p0992930191817"></a><a name="p0992930191817"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1899343071817"><a name="p1899343071817"></a><a name="p1899343071817"></a>Hard is the set of enforced hard limits for each named resource. More info: https://kubernetes.io/docs/concepts/policy/resource-quotas/</p>
</td>
</tr>
<tr id="row159876307182"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p599343018186"><a name="p599343018186"></a><a name="p599343018186"></a>used</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p4994143018186"><a name="p4994143018186"></a><a name="p4994143018186"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p9994430161817"><a name="p9994430161817"></a><a name="p9994430161817"></a>Used is the current observed total usage of the resource in the namespace.</p>
</td>
</tr>
</tbody>
</table>

**表 6**  io.k8s.api.core.v1.ResourceQuotaSpec

<a name="response_io.k8s.api.core.v1.ResourceQuotaSpec"></a>
<table><thead align="left"><tr id="row1799643031818"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p13999730131812"><a name="p13999730131812"></a><a name="p13999730131812"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p19003118186"><a name="p19003118186"></a><a name="p19003118186"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p501431191813"><a name="p501431191813"></a><a name="p501431191813"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row299718306187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p102173171817"><a name="p102173171817"></a><a name="p102173171817"></a>hard</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p92173171812"><a name="p92173171812"></a><a name="p92173171812"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p54183131816"><a name="p54183131816"></a><a name="p54183131816"></a>hard is the set of desired hard limits for each named resource. More info: https://kubernetes.io/docs/concepts/policy/resource-quotas/</p>
</td>
</tr>
<tr id="row799753010187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p75103151817"><a name="p75103151817"></a><a name="p75103151817"></a>scopeSelector</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p3514316181"><a name="p3514316181"></a><a name="p3514316181"></a><a href="#response_io.k8s.api.core.v1.ScopeSelector">io.k8s.api.core.v1.ScopeSelector</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1561031181810"><a name="p1561031181810"></a><a name="p1561031181810"></a>scopeSelector is also a collection of filters like scopes that must match each object tracked by a quota but expressed using ScopeSelectorOperator in combination with possible values. For a resource to match, both scopes AND scopeSelector (if specified in spec), must be matched.</p>
</td>
</tr>
<tr id="row299715307185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p13616316187"><a name="p13616316187"></a><a name="p13616316187"></a>scopes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p07103116180"><a name="p07103116180"></a><a name="p07103116180"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p878317188"><a name="p878317188"></a><a name="p878317188"></a>A collection of filters that must match each object tracked by a quota. If not specified, the quota matches all objects.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  io.k8s.api.core.v1.ScopeSelector

<a name="response_io.k8s.api.core.v1.ScopeSelector"></a>
<table><thead align="left"><tr id="row693313189"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p911163151814"><a name="p911163151814"></a><a name="p911163151814"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p15111831131811"><a name="p15111831131811"></a><a name="p15111831131811"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p1112431141811"><a name="p1112431141811"></a><a name="p1112431141811"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16993171811"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p91316318183"><a name="p91316318183"></a><a name="p91316318183"></a>matchExpressions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p131423161816"><a name="p131423161816"></a><a name="p131423161816"></a><a href="#response_io.k8s.api.core.v1.ScopedResourceSelectorRequirement">io.k8s.api.core.v1.ScopedResourceSelectorRequirement</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p131553111811"><a name="p131553111811"></a><a name="p131553111811"></a>A list of scope selector requirements by scope of the resources.</p>
</td>
</tr>
</tbody>
</table>

**表 8**  io.k8s.api.core.v1.ScopedResourceSelectorRequirement

<a name="response_io.k8s.api.core.v1.ScopedResourceSelectorRequirement"></a>
<table><thead align="left"><tr id="row181753141820"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p62018319182"><a name="p62018319182"></a><a name="p62018319182"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p321831111814"><a name="p321831111814"></a><a name="p321831111814"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p92163101811"><a name="p92163101811"></a><a name="p92163101811"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row71783115184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p4229313187"><a name="p4229313187"></a><a name="p4229313187"></a>operator</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p182318316187"><a name="p182318316187"></a><a name="p182318316187"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p52463117188"><a name="p52463117188"></a><a name="p52463117188"></a>Represents a scope's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist.</p>
</td>
</tr>
<tr id="row191823115187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p825193118185"><a name="p825193118185"></a><a name="p825193118185"></a>scopeName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p625123117185"><a name="p625123117185"></a><a name="p625123117185"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p142720315187"><a name="p142720315187"></a><a name="p142720315187"></a>The name of the scope that the selector applies to.</p>
</td>
</tr>
<tr id="row1118331121820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1727103117185"><a name="p1727103117185"></a><a name="p1727103117185"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p8281531101813"><a name="p8281531101813"></a><a name="p8281531101813"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1330113141816"><a name="p1330113141816"></a><a name="p1330113141816"></a>An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</p>
</td>
</tr>
</tbody>
</table>

**表 9**  io.k8s.apimachinery.pkg.apis.meta.v1.ObjectMeta

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.ObjectMeta"></a>
<table><thead align="left"><tr id="row1236731111815"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p247103191818"><a name="p247103191818"></a><a name="p247103191818"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p15481331191810"><a name="p15481331191810"></a><a name="p15481331191810"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p04883110182"><a name="p04883110182"></a><a name="p04883110182"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row43673191814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p144912319188"><a name="p144912319188"></a><a name="p144912319188"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p9501317186"><a name="p9501317186"></a><a name="p9501317186"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1350331171811"><a name="p1350331171811"></a><a name="p1350331171811"></a>Annotations is an unstructured key value map stored with a resource that may be set by external tools to store and retrieve arbitrary metadata. They are not queryable and should be preserved when modifying objects. More info: http://kubernetes.io/docs/user-guide/annotations</p>
</td>
</tr>
<tr id="row5381531111815"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p351193120188"><a name="p351193120188"></a><a name="p351193120188"></a>clusterName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p4511531141818"><a name="p4511531141818"></a><a name="p4511531141818"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17521231181814"><a name="p17521231181814"></a><a name="p17521231181814"></a>The name of the cluster which the object belongs to. This is used to distinguish resources with same name and namespace in different clusters. This field is not set anywhere right now and apiserver is going to ignore it if set in create or update request.</p>
</td>
</tr>
<tr id="row74018311189"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15253117181"><a name="p15253117181"></a><a name="p15253117181"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p195393141811"><a name="p195393141811"></a><a name="p195393141811"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Time object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p354113114186"><a name="p354113114186"></a><a name="p354113114186"></a>Time is a wrapper around time.Time which supports correct marshaling to YAML and JSON.  Wrappers are provided for many of the factory methods that the time package offers.</p>
</td>
</tr>
<tr id="row1940331161820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p255153119182"><a name="p255153119182"></a><a name="p255153119182"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1256163113186"><a name="p1256163113186"></a><a name="p1256163113186"></a>Interger</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p05712318188"><a name="p05712318188"></a><a name="p05712318188"></a>Number of seconds allowed for this object to gracefully terminate before it will be removed from the system. Only set when deletionTimestamp is also set. May only be shortened. Read-only.</p>
</td>
</tr>
<tr id="row240931121819"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p205813113181"><a name="p205813113181"></a><a name="p205813113181"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p75803113186"><a name="p75803113186"></a><a name="p75803113186"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Time object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p6596310185"><a name="p6596310185"></a><a name="p6596310185"></a>Time is a wrapper around time.Time which supports correct marshaling to YAML and JSON.  Wrappers are provided for many of the factory methods that the time package offers.</p>
</td>
</tr>
<tr id="row10401931151820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15606316182"><a name="p15606316182"></a><a name="p15606316182"></a>enable</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p106103112186"><a name="p106103112186"></a><a name="p106103112186"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p862183116181"><a name="p862183116181"></a><a name="p862183116181"></a>Enable identify whether the resource is available</p>
</td>
</tr>
<tr id="row640183161820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p362531191816"><a name="p362531191816"></a><a name="p362531191816"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p8631531141811"><a name="p8631531141811"></a><a name="p8631531141811"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1964203141816"><a name="p1964203141816"></a><a name="p1964203141816"></a>Must be empty before the object is deleted from the registry. Each entry is an identifier for the responsible component that will remove the entry from the list. If the deletionTimestamp of the object is non-nil, entries in this list can only be removed.</p>
</td>
</tr>
<tr id="row941143111185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p126623101816"><a name="p126623101816"></a><a name="p126623101816"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1866173113185"><a name="p1866173113185"></a><a name="p1866173113185"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p2671331161814"><a name="p2671331161814"></a><a name="p2671331161814"></a>GenerateName is an optional prefix, used by the server, to generate a unique name ONLY IF the Name field has not been provided. If this field is used, the name returned to the client will be different than the name passed. This value will also be combined with a unique suffix. The provided value has the same validation rules as the Name field, and may be truncated by the length of the suffix required to make the value unique on the server.</p>
<p id="p56733171814"><a name="p56733171814"></a><a name="p56733171814"></a></p>
<p id="p7671331191813"><a name="p7671331191813"></a><a name="p7671331191813"></a>If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header).</p>
<p id="p16687316183"><a name="p16687316183"></a><a name="p16687316183"></a></p>
<p id="p1068143141811"><a name="p1068143141811"></a><a name="p1068143141811"></a>Applied only if Name is not specified. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#idempotency</p>
</td>
</tr>
<tr id="row24113113184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p670113111181"><a name="p670113111181"></a><a name="p670113111181"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p27119318182"><a name="p27119318182"></a><a name="p27119318182"></a>Interger</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p572231151817"><a name="p572231151817"></a><a name="p572231151817"></a>A sequence number representing a specific generation of the desired state. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row1541631181814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p177218318188"><a name="p177218318188"></a><a name="p177218318188"></a>initializers</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p3738312184"><a name="p3738312184"></a><a name="p3738312184"></a><a href="#response_io.k8s.apimachinery.pkg.apis.meta.v1.Initializers">io.k8s.apimachinery.pkg.apis.meta.v1.Initializers</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17743318186"><a name="p17743318186"></a><a name="p17743318186"></a>An initializer is a controller which enforces some system invariant at object creation time. This field is a list of initializers that have not yet acted on this object. If nil or empty, this object has been completely initialized. Otherwise, the object is considered uninitialized and is hidden (in list/watch and get calls) from clients that haven't explicitly asked to observe uninitialized objects.</p>
<p id="p137453171818"><a name="p137453171818"></a><a name="p137453171818"></a></p>
<p id="p12751431121819"><a name="p12751431121819"></a><a name="p12751431121819"></a>When an object is created, the system will populate this list with the current set of initializers. Only privileged users may set or modify this list. Once it is empty, it may not be modified further by any user.</p>
</td>
</tr>
<tr id="row34418314188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p5751131141814"><a name="p5751131141814"></a><a name="p5751131141814"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1675193111182"><a name="p1675193111182"></a><a name="p1675193111182"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1376831181819"><a name="p1376831181819"></a><a name="p1376831181819"></a>Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels</p>
</td>
</tr>
<tr id="row1744123151814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p6764314186"><a name="p6764314186"></a><a name="p6764314186"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p18777316184"><a name="p18777316184"></a><a name="p18777316184"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p157833181816"><a name="p157833181816"></a><a name="p157833181816"></a>Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names</p>
</td>
</tr>
<tr id="row8451319181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1779113151813"><a name="p1779113151813"></a><a name="p1779113151813"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p38033113186"><a name="p38033113186"></a><a name="p38033113186"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p178114316187"><a name="p178114316187"></a><a name="p178114316187"></a>Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty.</p>
<p id="p19814319180"><a name="p19814319180"></a><a name="p19814319180"></a></p>
<p id="p18483173114189"><a name="p18483173114189"></a><a name="p18483173114189"></a>Must be a DNS_LABEL. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/namespaces</p>
</td>
</tr>
<tr id="row1945123111818"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p348411312183"><a name="p348411312183"></a><a name="p348411312183"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p54841831201812"><a name="p54841831201812"></a><a name="p54841831201812"></a>io.k8s.apimachinery.pkg.apis.meta.v1.OwnerReference object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p448412312183"><a name="p448412312183"></a><a name="p448412312183"></a>List of objects depended by this object. If ALL objects in the list have been deleted, this object will be garbage collected. If this object is managed by a controller, then an entry in this list will point to this controller, with the controller field set to true. There cannot be more than one managing controller.</p>
</td>
</tr>
<tr id="row1945193116186"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1748463111820"><a name="p1748463111820"></a><a name="p1748463111820"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1248423171820"><a name="p1248423171820"></a><a name="p1248423171820"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p14484163191818"><a name="p14484163191818"></a><a name="p14484163191818"></a>An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources.</p>
<p id="p248415311188"><a name="p248415311188"></a><a name="p248415311188"></a></p>
<p id="p104841631111813"><a name="p104841631111813"></a><a name="p104841631111813"></a>Populated by the system. Read-only. Value must be treated as opaque by clients. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency</p>
</td>
</tr>
<tr id="row94517311189"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1348513116182"><a name="p1348513116182"></a><a name="p1348513116182"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p848514315181"><a name="p848514315181"></a><a name="p848514315181"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p34851231111815"><a name="p34851231111815"></a><a name="p34851231111815"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row1345153116188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p448523101813"><a name="p448523101813"></a><a name="p448523101813"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p648573151812"><a name="p648573151812"></a><a name="p648573151812"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p54858319188"><a name="p54858319188"></a><a name="p54858319188"></a>UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations.</p>
<p id="p17485173191814"><a name="p17485173191814"></a><a name="p17485173191814"></a></p>
<p id="p12486123151820"><a name="p12486123151820"></a><a name="p12486123151820"></a>Populated by the system. Read-only. More info: http://kubernetes.io/docs/user-guide/identifiers#uids</p>
</td>
</tr>
</tbody>
</table>

**表 10**  io.k8s.apimachinery.pkg.apis.meta.v1.OwnerReference

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.OwnerReference"></a>
<table><thead align="left"><tr id="row59113111814"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p148603115180"><a name="p148603115180"></a><a name="p148603115180"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1486143118188"><a name="p1486143118188"></a><a name="p1486143118188"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p15486173141812"><a name="p15486173141812"></a><a name="p15486173141812"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2918319185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p104861531121817"><a name="p104861531121817"></a><a name="p104861531121817"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p8486153113183"><a name="p8486153113183"></a><a name="p8486153113183"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p16486231151810"><a name="p16486231151810"></a><a name="p16486231151810"></a>API version of the referent.</p>
</td>
</tr>
<tr id="row291183118188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15486431111819"><a name="p15486431111819"></a><a name="p15486431111819"></a>blockOwnerDeletion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p17486113116181"><a name="p17486113116181"></a><a name="p17486113116181"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p448783116181"><a name="p448783116181"></a><a name="p448783116181"></a>If true, AND if the owner has the "foregroundDeletion" finalizer, then the owner cannot be deleted from the key-value store until this reference is removed. Defaults to false. To set this field, a user needs "delete" permission of the owner, otherwise 422 (Unprocessable Entity) will be returned.</p>
</td>
</tr>
<tr id="row179219313182"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1948714313186"><a name="p1948714313186"></a><a name="p1948714313186"></a>controller</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p3487113171818"><a name="p3487113171818"></a><a name="p3487113171818"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1748712312182"><a name="p1748712312182"></a><a name="p1748712312182"></a>If true, this reference points to the managing controller.</p>
</td>
</tr>
<tr id="row292183117185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p12487431101813"><a name="p12487431101813"></a><a name="p12487431101813"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p174871031191817"><a name="p174871031191817"></a><a name="p174871031191817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p348743101819"><a name="p348743101819"></a><a name="p348743101819"></a>Kind of the referent. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row1092123118180"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p3487173171818"><a name="p3487173171818"></a><a name="p3487173171818"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p4488163110181"><a name="p4488163110181"></a><a name="p4488163110181"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17488831201818"><a name="p17488831201818"></a><a name="p17488831201818"></a>Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names</p>
</td>
</tr>
<tr id="row109214311182"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p4488153161810"><a name="p4488153161810"></a><a name="p4488153161810"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p5488153151814"><a name="p5488153151814"></a><a name="p5488153151814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p24881310187"><a name="p24881310187"></a><a name="p24881310187"></a>UID of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#uids</p>
</td>
</tr>
</tbody>
</table>

**表 11**  io.k8s.apimachinery.pkg.apis.meta.v1.Initializers

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.Initializers"></a>
<table><thead align="left"><tr id="row18102103112180"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p9488123116183"><a name="p9488123116183"></a><a name="p9488123116183"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p94880316189"><a name="p94880316189"></a><a name="p94880316189"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p15489531141816"><a name="p15489531141816"></a><a name="p15489531141816"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row9103431161813"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p20489183171817"><a name="p20489183171817"></a><a name="p20489183171817"></a>pending</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14899317188"><a name="p14899317188"></a><a name="p14899317188"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Initializer object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p748943112189"><a name="p748943112189"></a><a name="p748943112189"></a>Pending is a list of initializers that must execute in order before this object is visible. When the last pending initializer is removed, and no failing result is set, the initializers struct will be set to nil and the object is considered as initialized and visible to all clients.</p>
</td>
</tr>
<tr id="row1103631191814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p19489173181817"><a name="p19489173181817"></a><a name="p19489173181817"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16489143110184"><a name="p16489143110184"></a><a name="p16489143110184"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Status object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p44891531181812"><a name="p44891531181812"></a><a name="p44891531181812"></a>If result is set with the Failure field, the object will be persisted to storage and then deleted, ensuring that other clients can observe the deletion.</p>
</td>
</tr>
</tbody>
</table>

**表 12**  io.k8s.apimachinery.pkg.apis.meta.v1.Status

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.Status"></a>
<table><thead align="left"><tr id="row171101931121819"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p144907314181"><a name="p144907314181"></a><a name="p144907314181"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p6490631101820"><a name="p6490631101820"></a><a name="p6490631101820"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p4157124717218"><a name="p4157124717218"></a><a name="p4157124717218"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row31111931181811"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p649013110182"><a name="p649013110182"></a><a name="p649013110182"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p749043161811"><a name="p749043161811"></a><a name="p749043161811"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p194901831171810"><a name="p194901831171810"></a><a name="p194901831171810"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources</p>
</td>
</tr>
<tr id="row1811113315187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p12490931161814"><a name="p12490931161814"></a><a name="p12490931161814"></a>code</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p34901531141813"><a name="p34901531141813"></a><a name="p34901531141813"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p3491113151819"><a name="p3491113151819"></a><a name="p3491113151819"></a>Suggested HTTP return code for this status, 0 if not set.</p>
</td>
</tr>
<tr id="row12111193181815"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p449183111181"><a name="p449183111181"></a><a name="p449183111181"></a>details</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16491153115184"><a name="p16491153115184"></a><a name="p16491153115184"></a>io.k8s.apimachinery.pkg.apis.meta.v1.StatusDetails object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p13491431111815"><a name="p13491431111815"></a><a name="p13491431111815"></a>Extended data associated with the reason.  Each reason may define its own extended details. This field is optional and the data returned is not guaranteed to conform to any schema except that defined by the reason type.</p>
</td>
</tr>
<tr id="row15112183131814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p144911531131819"><a name="p144911531131819"></a><a name="p144911531131819"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p104911231111817"><a name="p104911231111817"></a><a name="p104911231111817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p74911531191810"><a name="p74911531191810"></a><a name="p74911531191810"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row6113153101812"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p9491131141813"><a name="p9491131141813"></a><a name="p9491131141813"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1549183110184"><a name="p1549183110184"></a><a name="p1549183110184"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p5491103116181"><a name="p5491103116181"></a><a name="p5491103116181"></a>A human-readable description of the status of this operation.</p>
</td>
</tr>
<tr id="row1711383151810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p12491123151812"><a name="p12491123151812"></a><a name="p12491123151812"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1249123151818"><a name="p1249123151818"></a><a name="p1249123151818"></a>io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p44921431191818"><a name="p44921431191818"></a><a name="p44921431191818"></a>Standard list metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row9113531101813"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p144922317185"><a name="p144922317185"></a><a name="p144922317185"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p84929312188"><a name="p84929312188"></a><a name="p84929312188"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p549223181817"><a name="p549223181817"></a><a name="p549223181817"></a>A machine-readable description of why this operation is in the "Failure" status. If this value is empty there is no information available. A Reason clarifies an HTTP status code but does not override it.</p>
</td>
</tr>
<tr id="row511483113186"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p849263151812"><a name="p849263151812"></a><a name="p849263151812"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p649263118186"><a name="p649263118186"></a><a name="p649263118186"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1549203119188"><a name="p1549203119188"></a><a name="p1549203119188"></a>Status of the operation. One of: "Success" or "Failure". More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#spec-and-status</p>
</td>
</tr>
</tbody>
</table>

**表 13**  io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta

<a name="table111291731151815"></a>
<table><thead align="left"><tr id="row113093119184"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p24929316185"><a name="p24929316185"></a><a name="p24929316185"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p84921131181819"><a name="p84921131181819"></a><a name="p84921131181819"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p10492103111182"><a name="p10492103111182"></a><a name="p10492103111182"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12130193118181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1492123115185"><a name="p1492123115185"></a><a name="p1492123115185"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p24939319180"><a name="p24939319180"></a><a name="p24939319180"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p184931231111816"><a name="p184931231111816"></a><a name="p184931231111816"></a>continue may be set if the user set a limit on the number of items returned, and indicates that the server has more data available. The value is opaque and may be used to issue another request to the endpoint that served this list to retrieve the next set of available objects. Continuing a list may not be possible if the server configuration has changed or more than a few minutes have passed. The resourceVersion field returned when using this continue value will be identical to the value in the first response.</p>
</td>
</tr>
<tr id="row81303317189"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p10493163118185"><a name="p10493163118185"></a><a name="p10493163118185"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p114931431161820"><a name="p114931431161820"></a><a name="p114931431161820"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p549363117184"><a name="p549363117184"></a><a name="p549363117184"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency</p>
</td>
</tr>
<tr id="row181301231171816"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p6493113161816"><a name="p6493113161816"></a><a name="p6493113161816"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1249383181813"><a name="p1249383181813"></a><a name="p1249383181813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1149353110188"><a name="p1149353110188"></a><a name="p1149353110188"></a>selfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 14**  io.k8s.apimachinery.pkg.apis.meta.v1.StatusDetails

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.StatusDetails"></a>
<table><thead align="left"><tr id="row314423161817"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p149415313187"><a name="p149415313187"></a><a name="p149415313187"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p9494153114183"><a name="p9494153114183"></a><a name="p9494153114183"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p19494183113183"><a name="p19494183113183"></a><a name="p19494183113183"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row14145331121815"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p249403121811"><a name="p249403121811"></a><a name="p249403121811"></a>causes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p124948315186"><a name="p124948315186"></a><a name="p124948315186"></a>io.k8s.apimachinery.pkg.apis.meta.v1.StatusCause object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1495731141819"><a name="p1495731141819"></a><a name="p1495731141819"></a>The Causes array includes more details associated with the StatusReason failure. Not all StatusReasons may provide detailed causes.</p>
</td>
</tr>
<tr id="row171451931111818"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p749593119185"><a name="p749593119185"></a><a name="p749593119185"></a>group</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p144951131181817"><a name="p144951131181817"></a><a name="p144951131181817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p10495133120184"><a name="p10495133120184"></a><a name="p10495133120184"></a>The group attribute of the resource associated with the status StatusReason.</p>
</td>
</tr>
<tr id="row514553119188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1449610318186"><a name="p1449610318186"></a><a name="p1449610318186"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p949693101817"><a name="p949693101817"></a><a name="p949693101817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p4496731191820"><a name="p4496731191820"></a><a name="p4496731191820"></a>The kind attribute of the resource associated with the status StatusReason. On some operations may differ from the requested resource Kind. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row814516310188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p84961531171812"><a name="p84961531171812"></a><a name="p84961531171812"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p349611312189"><a name="p349611312189"></a><a name="p349611312189"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p134966317186"><a name="p134966317186"></a><a name="p134966317186"></a>The name attribute of the resource associated with the status StatusReason (when there is a single name which can be described).</p>
</td>
</tr>
<tr id="row17145731101811"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15496331151819"><a name="p15496331151819"></a><a name="p15496331151819"></a>retryAfterSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1049613191820"><a name="p1049613191820"></a><a name="p1049613191820"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p11497731111817"><a name="p11497731111817"></a><a name="p11497731111817"></a>If specified, the time in seconds before the operation should be retried. Some errors may indicate the client must take an alternate action - for those errors this field may indicate how long to wait before taking the alternate action.</p>
</td>
</tr>
<tr id="row17146163112184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p144979311185"><a name="p144979311185"></a><a name="p144979311185"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1449717319188"><a name="p1449717319188"></a><a name="p1449717319188"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1249716313188"><a name="p1249716313188"></a><a name="p1249716313188"></a>UID of the resource. (when there is a single resource which can be described). More info: http://kubernetes.io/docs/user-guide/identifiers#uids</p>
</td>
</tr>
</tbody>
</table>

**表 15**  io.k8s.apimachinery.pkg.apis.meta.v1.StatusCause

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.StatusCause"></a>
<table><thead align="left"><tr id="row2161123117186"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1749783116185"><a name="p1749783116185"></a><a name="p1749783116185"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p24981731141813"><a name="p24981731141813"></a><a name="p24981731141813"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p144982319185"><a name="p144982319185"></a><a name="p144982319185"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12161831151812"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p8498103117187"><a name="p8498103117187"></a><a name="p8498103117187"></a>field</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p174981731121811"><a name="p174981731121811"></a><a name="p174981731121811"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p14986311182"><a name="p14986311182"></a><a name="p14986311182"></a>The field of the resource that has caused this error, as named by its JSON serialization. May include dot and postfix notation for nested attributes. Arrays are zero-indexed.  Fields may appear more than once in an array of causes due to fields having multiple errors. Optional.</p>
<p id="p549813118181"><a name="p549813118181"></a><a name="p549813118181"></a>Examples:</p>
<p id="p1649817316184"><a name="p1649817316184"></a><a name="p1649817316184"></a>"name" - the field "name" on the current resource</p>
<p id="p174985312187"><a name="p174985312187"></a><a name="p174985312187"></a>"items[0].name" - the field "name" on the first array entry in "items"</p>
</td>
</tr>
<tr id="row13161831101816"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p249813317183"><a name="p249813317183"></a><a name="p249813317183"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p44981731151818"><a name="p44981731151818"></a><a name="p44981731151818"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p4499133120189"><a name="p4499133120189"></a><a name="p4499133120189"></a>A human-readable description of the cause of the error.  This field may be presented as-is to a reader.</p>
</td>
</tr>
<tr id="row20161193161817"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p449973111812"><a name="p449973111812"></a><a name="p449973111812"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1949910318181"><a name="p1949910318181"></a><a name="p1949910318181"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p12499153141818"><a name="p12499153141818"></a><a name="p12499153141818"></a>A machine-readable description of the cause of the error. If this value is empty there is no information available.</p>
</td>
</tr>
</tbody>
</table>

**表 16**  io.k8s.apimachinery.pkg.apis.meta.v1.Initializer

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.Initializer"></a>
<table><thead align="left"><tr id="row18167123151812"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p4499193117181"><a name="p4499193117181"></a><a name="p4499193117181"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p104995319183"><a name="p104995319183"></a><a name="p104995319183"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p184991831191815"><a name="p184991831191815"></a><a name="p184991831191815"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row816863114187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p549911314187"><a name="p549911314187"></a><a name="p549911314187"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p54992310188"><a name="p54992310188"></a><a name="p54992310188"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p3500133131815"><a name="p3500133131815"></a><a name="p3500133131815"></a>name of the process that is responsible for initializing this object.</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section125001319183"></a>

无

## 响应示例<a name="section65002310186"></a>

状态码为 200 时:

```
{
    "apiVersion": "v1",
    "items": [
        {
            "apiVersion": "v1",
            "kind": "ResourceQuota",
            "metadata": {
                "creationTimestamp": "2019-07-03T07:59:50Z",
                "labels": {
                    "app": "resourcequota"
                },
                "name": "rq-test",
                "namespace": "default",
                "resourceVersion": "3718271",
                "selfLink": "/api/v1/namespaces/default/resourcequotas/rq-test",
                "uid": "886ac259-9d68-11e9-8d38-fa163eb8e88a"
            },
            "spec": {
                "hard": {
                    "configmaps": "20",
                    "limits.cpu": "5",
                    "limits.memory": "16Gi",
                    "persistentvolumeclaims": "20",
                    "pods": "50",
                    "replicationcontrollers": "20",
                    "requests.cpu": "500m",
                    "requests.memory": "512Mi",
                    "secrets": "20",
                    "services": "50"
                }
            },
            "status": {
                "hard": {
                    "configmaps": "20",
                    "limits.cpu": "5",
                    "limits.memory": "16Gi",
                    "persistentvolumeclaims": "20",
                    "pods": "50",
                    "replicationcontrollers": "20",
                    "requests.cpu": "500m",
                    "requests.memory": "512Mi",
                    "secrets": "20",
                    "services": "50"
                },
                "used": {
                    "configmaps": "1",
                    "limits.cpu": "950m",
                    "limits.memory": "2Gi",
                    "persistentvolumeclaims": "5",
                    "pods": "8",
                    "replicationcontrollers": "0",
                    "requests.cpu": "850m",
                    "requests.memory": "1792Mi",
                    "secrets": "5",
                    "services": "2"
                }
            }
        }
    ],
    "kind": "List",
    "metadata": {
        "resourceVersion": "",
        "selfLink": ""
    }
}
```

## 返回值<a name="section17509203181816"></a>

<a name="table538"></a>
<table><thead align="left"><tr id="row72079316186"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p1750973111186"><a name="p1750973111186"></a><a name="p1750973111186"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p205101631171811"><a name="p205101631171811"></a><a name="p205101631171811"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1220793118189"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p7510163120184"><a name="p7510163120184"></a><a name="p7510163120184"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p251013181816"><a name="p251013181816"></a><a name="p251013181816"></a>OK</p>
</td>
</tr>
<tr id="row22078317189"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p165101331171810"><a name="p165101331171810"></a><a name="p165101331171810"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p85101631191818"><a name="p85101631191818"></a><a name="p85101631191818"></a>Unauthorized</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section13510331111813"></a>

无

