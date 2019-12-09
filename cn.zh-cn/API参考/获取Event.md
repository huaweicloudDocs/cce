# 获取Event<a name="cce_02_0338"></a>

## 功能介绍<a name="section164422961814"></a>

list or watch objects of kind Event.

## URI<a name="section13645129151819"></a>

GET /api/v1/events

GET /apis/events.k8s.io/v1beta1/events

**表 1**  Query参数

<a name="table165216295189"></a>
<table><thead align="left"><tr id="row4649142981810"><th class="cellrowborder" valign="top" width="20.380000000000003%" id="mcps1.2.5.1.1"><p id="p965252915185"><a name="p965252915185"></a><a name="p965252915185"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.27%" id="mcps1.2.5.1.2"><p id="p119882330116"><a name="p119882330116"></a><a name="p119882330116"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.4%" id="mcps1.2.5.1.3"><p id="p146531298188"><a name="p146531298188"></a><a name="p146531298188"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.949999999999996%" id="mcps1.2.5.1.4"><p id="p4654122931816"><a name="p4654122931816"></a><a name="p4654122931816"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12649112918188"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p1565442911810"><a name="p1565442911810"></a><a name="p1565442911810"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="16.27%" headers="mcps1.2.5.1.2 "><p id="p9655122915185"><a name="p9655122915185"></a><a name="p9655122915185"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.4%" headers="mcps1.2.5.1.3 "><p id="p19655112981817"><a name="p19655112981817"></a><a name="p19655112981817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p165662991812"><a name="p165662991812"></a><a name="p165662991812"></a>The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server the server will respond with a 410 ResourceExpired error indicating the client must restart their list without the continue field. This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.</p>
</td>
</tr>
<tr id="row1564913295181"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p3656129141811"><a name="p3656129141811"></a><a name="p3656129141811"></a>fieldSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.27%" headers="mcps1.2.5.1.2 "><p id="p136581294182"><a name="p136581294182"></a><a name="p136581294182"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.4%" headers="mcps1.2.5.1.3 "><p id="p186573293183"><a name="p186573293183"></a><a name="p186573293183"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p116581129151810"><a name="p116581129151810"></a><a name="p116581129151810"></a>A selector to restrict the list of returned objects by their fields. Defaults to everything.</p>
</td>
</tr>
<tr id="row864917294186"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p146588291187"><a name="p146588291187"></a><a name="p146588291187"></a>includeUninitialized</p>
</td>
<td class="cellrowborder" valign="top" width="16.27%" headers="mcps1.2.5.1.2 "><p id="p1066012931817"><a name="p1066012931817"></a><a name="p1066012931817"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.4%" headers="mcps1.2.5.1.3 "><p id="p20659122981817"><a name="p20659122981817"></a><a name="p20659122981817"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p36607291184"><a name="p36607291184"></a><a name="p36607291184"></a>If true, partially initialized resources are included in the response.</p>
</td>
</tr>
<tr id="row36491229141820"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p106611329101810"><a name="p106611329101810"></a><a name="p106611329101810"></a>labelSelector</p>
</td>
<td class="cellrowborder" valign="top" width="16.27%" headers="mcps1.2.5.1.2 "><p id="p1266220295184"><a name="p1266220295184"></a><a name="p1266220295184"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.4%" headers="mcps1.2.5.1.3 "><p id="p186611029101813"><a name="p186611029101813"></a><a name="p186611029101813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p15663142981817"><a name="p15663142981817"></a><a name="p15663142981817"></a>A selector to restrict the list of returned objects by their labels. Defaults to everything.</p>
</td>
</tr>
<tr id="row165072919184"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p126639290186"><a name="p126639290186"></a><a name="p126639290186"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="16.27%" headers="mcps1.2.5.1.2 "><p id="p126651129121817"><a name="p126651129121817"></a><a name="p126651129121817"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.4%" headers="mcps1.2.5.1.3 "><p id="p18664329191814"><a name="p18664329191814"></a><a name="p18664329191814"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p466511298184"><a name="p466511298184"></a><a name="p466511298184"></a>limit is a maximum number of responses to return for a list call. If more items exist, the server will set the `continue` field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.</p>
<p id="p2666122910189"><a name="p2666122910189"></a><a name="p2666122910189"></a>The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.</p>
</td>
</tr>
<tr id="row76501129191815"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p1166792911812"><a name="p1166792911812"></a><a name="p1166792911812"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.27%" headers="mcps1.2.5.1.2 "><p id="p166681829131815"><a name="p166681829131815"></a><a name="p166681829131815"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.4%" headers="mcps1.2.5.1.3 "><p id="p066752951810"><a name="p066752951810"></a><a name="p066752951810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p3668202912189"><a name="p3668202912189"></a><a name="p3668202912189"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row365010298185"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p116691729101812"><a name="p116691729101812"></a><a name="p116691729101812"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.27%" headers="mcps1.2.5.1.2 "><p id="p467022918184"><a name="p467022918184"></a><a name="p467022918184"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.4%" headers="mcps1.2.5.1.3 "><p id="p20670102951811"><a name="p20670102951811"></a><a name="p20670102951811"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p0671122910181"><a name="p0671122910181"></a><a name="p0671122910181"></a>When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv.</p>
</td>
</tr>
<tr id="row8650729171810"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p1467222915187"><a name="p1467222915187"></a><a name="p1467222915187"></a>timeoutSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.27%" headers="mcps1.2.5.1.2 "><p id="p9672429141813"><a name="p9672429141813"></a><a name="p9672429141813"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.4%" headers="mcps1.2.5.1.3 "><p id="p367222951820"><a name="p367222951820"></a><a name="p367222951820"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p156731429181818"><a name="p156731429181818"></a><a name="p156731429181818"></a>Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity.</p>
</td>
</tr>
<tr id="row665016299186"><td class="cellrowborder" valign="top" width="20.380000000000003%" headers="mcps1.2.5.1.1 "><p id="p16674152951814"><a name="p16674152951814"></a><a name="p16674152951814"></a>watch</p>
</td>
<td class="cellrowborder" valign="top" width="16.27%" headers="mcps1.2.5.1.2 "><p id="p186751329191819"><a name="p186751329191819"></a><a name="p186751329191819"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.4%" headers="mcps1.2.5.1.3 "><p id="p967432901817"><a name="p967432901817"></a><a name="p967432901817"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="50.949999999999996%" headers="mcps1.2.5.1.4 "><p id="p206756295181"><a name="p206756295181"></a><a name="p206756295181"></a>Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion.</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section15676629161820"></a>

无

## 响应参数<a name="section2677142914182"></a>

状态码为 200 时:

**表 2**  响应Body参数

<a name="responseParameter"></a>
<table><thead align="left"><tr id="row1867918292184"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p13682142917188"><a name="p13682142917188"></a><a name="p13682142917188"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p15683112921811"><a name="p15683112921811"></a><a name="p15683112921811"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p18683629171816"><a name="p18683629171816"></a><a name="p18683629171816"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1967952961816"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p168402914189"><a name="p168402914189"></a><a name="p168402914189"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p156848298182"><a name="p156848298182"></a><a name="p156848298182"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p668532917186"><a name="p668532917186"></a><a name="p668532917186"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources</p>
</td>
</tr>
<tr id="row1679229141818"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p16685929181819"><a name="p16685929181819"></a><a name="p16685929181819"></a>items</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p46861929121815"><a name="p46861929121815"></a><a name="p46861929121815"></a>io.k8s.api.core.v1.Event object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1968752991814"><a name="p1968752991814"></a><a name="p1968752991814"></a>List of events. More info:</p>
<p id="p274631265020"><a name="p274631265020"></a><a name="p274631265020"></a>Standard list metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row1368062991820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p368718296181"><a name="p368718296181"></a><a name="p368718296181"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p268712293182"><a name="p268712293182"></a><a name="p268712293182"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19688202961818"><a name="p19688202961818"></a><a name="p19688202961818"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row126809291188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1668882911811"><a name="p1668882911811"></a><a name="p1668882911811"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16892292188"><a name="p16892292188"></a><a name="p16892292188"></a>io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p11689102915189"><a name="p11689102915189"></a><a name="p11689102915189"></a>Standard list metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
</tbody>
</table>

**表 3**  io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta"></a>
<table><thead align="left"><tr id="row56911329101816"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1169315297186"><a name="p1169315297186"></a><a name="p1169315297186"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p969362918188"><a name="p969362918188"></a><a name="p969362918188"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p869472931814"><a name="p869472931814"></a><a name="p869472931814"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row469119297186"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p16695192913184"><a name="p16695192913184"></a><a name="p16695192913184"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p17695182911816"><a name="p17695182911816"></a><a name="p17695182911816"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p10696122917183"><a name="p10696122917183"></a><a name="p10696122917183"></a>continue may be set if the user set a limit on the number of items returned, and indicates that the server has more data available. The value is opaque and may be used to issue another request to the endpoint that served this list to retrieve the next set of available objects. Continuing a list may not be possible if the server configuration has changed or more than a few minutes have passed. The resourceVersion field returned when using this continue value will be identical to the value in the first response.</p>
</td>
</tr>
<tr id="row156919290187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18697172913182"><a name="p18697172913182"></a><a name="p18697172913182"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p10697029131814"><a name="p10697029131814"></a><a name="p10697029131814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p14698112971816"><a name="p14698112971816"></a><a name="p14698112971816"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency</p>
</td>
</tr>
<tr id="row1769142961814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p26981429111817"><a name="p26981429111817"></a><a name="p26981429111817"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1669992914181"><a name="p1669992914181"></a><a name="p1669992914181"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17700182910189"><a name="p17700182910189"></a><a name="p17700182910189"></a>selfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  io.k8s.api.core.v1.Event

<a name="response_io.k8s.api.core.v1.Event"></a>
<table><thead align="left"><tr id="row2702112911819"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p97091429161819"><a name="p97091429161819"></a><a name="p97091429161819"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1371016298188"><a name="p1371016298188"></a><a name="p1371016298188"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p07111291189"><a name="p07111291189"></a><a name="p07111291189"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6703829161810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p16711202991811"><a name="p16711202991811"></a><a name="p16711202991811"></a>action</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p117121292187"><a name="p117121292187"></a><a name="p117121292187"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p871242981810"><a name="p871242981810"></a><a name="p871242981810"></a>What action was taken/failed regarding to the Regarding object.</p>
</td>
</tr>
<tr id="row12703142910189"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p071352901820"><a name="p071352901820"></a><a name="p071352901820"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p187131629131814"><a name="p187131629131814"></a><a name="p187131629131814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19714729161811"><a name="p19714729161811"></a><a name="p19714729161811"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources</p>
</td>
</tr>
<tr id="row570352931812"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p147141629141811"><a name="p147141629141811"></a><a name="p147141629141811"></a>count</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p3714142910189"><a name="p3714142910189"></a><a name="p3714142910189"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p971518292181"><a name="p971518292181"></a><a name="p971518292181"></a>The number of times this event has occurred.</p>
</td>
</tr>
<tr id="row670372931814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1715192915183"><a name="p1715192915183"></a><a name="p1715192915183"></a>eventTime</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p241141130"><a name="p241141130"></a><a name="p241141130"></a>io.k8s.apimachinery.pkg.apis.meta.v1.MicroTime object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p371652910183"><a name="p371652910183"></a><a name="p371652910183"></a>MicroTime is version of Time with microsecond level precision.</p>
</td>
</tr>
<tr id="row107031429181816"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1871602981816"><a name="p1871602981816"></a><a name="p1871602981816"></a>firstTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1089112316133"><a name="p1089112316133"></a><a name="p1089112316133"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Time object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p3717132916185"><a name="p3717132916185"></a><a name="p3717132916185"></a>Time is a wrapper around time.Time which supports correct marshaling to YAML and JSON.  Wrappers are provided for many of the factory methods that the time package offers.</p>
</td>
</tr>
<tr id="row770413292181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p971892941818"><a name="p971892941818"></a><a name="p971892941818"></a>involvedObject</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1295072881313"><a name="p1295072881313"></a><a name="p1295072881313"></a>io.k8s.api.core.v1.ObjectReference object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p57209295189"><a name="p57209295189"></a><a name="p57209295189"></a>The object that this event is about.</p>
</td>
</tr>
<tr id="row147042297182"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15722122911811"><a name="p15722122911811"></a><a name="p15722122911811"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p7723929131811"><a name="p7723929131811"></a><a name="p7723929131811"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p172342991817"><a name="p172342991817"></a><a name="p172342991817"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row1070462961811"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p5723172918189"><a name="p5723172918189"></a><a name="p5723172918189"></a>lastTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p5724529131814"><a name="p5724529131814"></a><a name="p5724529131814"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Time object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p67256299184"><a name="p67256299184"></a><a name="p67256299184"></a>Time is a wrapper around time.Time which supports correct marshaling to YAML and JSON.  Wrappers are provided for many of the factory methods that the time package offers.</p>
</td>
</tr>
<tr id="row1870413295184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1672662951819"><a name="p1672662951819"></a><a name="p1672662951819"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p15726132914181"><a name="p15726132914181"></a><a name="p15726132914181"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p7727629171818"><a name="p7727629171818"></a><a name="p7727629171818"></a>A human-readable description of the status of this operation.</p>
</td>
</tr>
<tr id="row87041629151818"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p127281529121812"><a name="p127281529121812"></a><a name="p127281529121812"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p6728112914181"><a name="p6728112914181"></a><a name="p6728112914181"></a>io.k8s.apimachinery.pkg.apis.meta.v1.ObjectMeta object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p18729729141812"><a name="p18729729141812"></a><a name="p18729729141812"></a>Standard object's metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#metadata</p>
</td>
</tr>
<tr id="row970522916187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p157309291185"><a name="p157309291185"></a><a name="p157309291185"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p273010299188"><a name="p273010299188"></a><a name="p273010299188"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1173182918188"><a name="p1173182918188"></a><a name="p1173182918188"></a>This should be a short, machine understandable string that gives the reason for the transition into the object's current status.</p>
</td>
</tr>
<tr id="row3705122913188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p873110296181"><a name="p873110296181"></a><a name="p873110296181"></a>related</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p19732172961810"><a name="p19732172961810"></a><a name="p19732172961810"></a>io.k8s.api.core.v1.ObjectReference object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p12732192901819"><a name="p12732192901819"></a><a name="p12732192901819"></a>Optional secondary object for more complex actions.</p>
</td>
</tr>
<tr id="row270512917187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1673214298181"><a name="p1673214298181"></a><a name="p1673214298181"></a>reportingComponent</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p177331529191820"><a name="p177331529191820"></a><a name="p177331529191820"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p873392931819"><a name="p873392931819"></a><a name="p873392931819"></a>Name of the controller that emitted this Event, e.g. `kubernetes.io/kubelet`.</p>
</td>
</tr>
<tr id="row197051629101819"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p973412931815"><a name="p973412931815"></a><a name="p973412931815"></a>reportingInstance</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p77351929111811"><a name="p77351929111811"></a><a name="p77351929111811"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p8735929141810"><a name="p8735929141810"></a><a name="p8735929141810"></a>ID of the controller instance, e.g. `kubelet-xyzf`.</p>
</td>
</tr>
<tr id="row14705122911819"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p197360292189"><a name="p197360292189"></a><a name="p197360292189"></a>series</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p18736102931816"><a name="p18736102931816"></a><a name="p18736102931816"></a>io.k8s.api.core.v1.EventSeries object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1373615293184"><a name="p1373615293184"></a><a name="p1373615293184"></a>Data about the Event series this event represents or nil if it's a singleton Event.</p>
</td>
</tr>
<tr id="row187051329161817"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1873713291187"><a name="p1873713291187"></a><a name="p1873713291187"></a>source</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p107371329141813"><a name="p107371329141813"></a><a name="p107371329141813"></a>io.k8s.api.core.v1.EventSource object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p2073862961819"><a name="p2073862961819"></a><a name="p2073862961819"></a>The component reporting this event. Should be a short machine understandable string.</p>
</td>
</tr>
<tr id="row187052029181812"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18739152911814"><a name="p18739152911814"></a><a name="p18739152911814"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p6739112931810"><a name="p6739112931810"></a><a name="p6739112931810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1773992911186"><a name="p1773992911186"></a><a name="p1773992911186"></a>Type of this event (Normal, Warning), new types could be added in the future</p>
</td>
</tr>
</tbody>
</table>

**表 5**  io.k8s.api.core.v1.EventSource

<a name="response_io.k8s.api.core.v1.EventSource"></a>
<table><thead align="left"><tr id="row207401829101816"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p27422293184"><a name="p27422293184"></a><a name="p27422293184"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p11742142911189"><a name="p11742142911189"></a><a name="p11742142911189"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p107432029181812"><a name="p107432029181812"></a><a name="p107432029181812"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1741162916183"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15743162913182"><a name="p15743162913182"></a><a name="p15743162913182"></a>component</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16744202921811"><a name="p16744202921811"></a><a name="p16744202921811"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1074416296183"><a name="p1074416296183"></a><a name="p1074416296183"></a>Component from which the event is generated.</p>
</td>
</tr>
<tr id="row4741129111814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p187453296187"><a name="p187453296187"></a><a name="p187453296187"></a>host</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14746102951810"><a name="p14746102951810"></a><a name="p14746102951810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p574662910184"><a name="p574662910184"></a><a name="p574662910184"></a>Node name on which the event is generated.</p>
</td>
</tr>
</tbody>
</table>

**表 6**  io.k8s.api.core.v1.EventSeries

<a name="response_io.k8s.api.core.v1.EventSeries"></a>
<table><thead align="left"><tr id="row1974782911813"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p17749129191816"><a name="p17749129191816"></a><a name="p17749129191816"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p10750172981811"><a name="p10750172981811"></a><a name="p10750172981811"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p975052913189"><a name="p975052913189"></a><a name="p975052913189"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1747172916186"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p175192916183"><a name="p175192916183"></a><a name="p175192916183"></a>count</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p177511029161818"><a name="p177511029161818"></a><a name="p177511029161818"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p575272915182"><a name="p575272915182"></a><a name="p575272915182"></a>Number of occurrences in this series up to the last heartbeat time</p>
</td>
</tr>
<tr id="row97481429181820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p075292931814"><a name="p075292931814"></a><a name="p075292931814"></a>lastObservedTime</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p7753429121814"><a name="p7753429121814"></a><a name="p7753429121814"></a>io.k8s.apimachinery.pkg.apis.meta.v1.MicroTime object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17541229111818"><a name="p17541229111818"></a><a name="p17541229111818"></a>MicroTime is version of Time with microsecond level precision.</p>
</td>
</tr>
<tr id="row1574862921812"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15755122920188"><a name="p15755122920188"></a><a name="p15755122920188"></a>state</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1175522991814"><a name="p1175522991814"></a><a name="p1175522991814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p14755192941813"><a name="p14755192941813"></a><a name="p14755192941813"></a>State of this Series: Ongoing or Finished</p>
</td>
</tr>
</tbody>
</table>

**表 7**  io.k8s.api.core.v1.ObjectReference

<a name="response_io.k8s.api.core.v1.ObjectReference"></a>
<table><thead align="left"><tr id="row1758229181813"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1276312961819"><a name="p1276312961819"></a><a name="p1276312961819"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p4764172914180"><a name="p4764172914180"></a><a name="p4764172914180"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p17765172912186"><a name="p17765172912186"></a><a name="p17765172912186"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1975972911184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p77651629201819"><a name="p77651629201819"></a><a name="p77651629201819"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p2766162918183"><a name="p2766162918183"></a><a name="p2766162918183"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17767162910183"><a name="p17767162910183"></a><a name="p17767162910183"></a>API version of the referent.</p>
</td>
</tr>
<tr id="row875942917186"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p97671629111810"><a name="p97671629111810"></a><a name="p97671629111810"></a>fieldPath</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p15767429121813"><a name="p15767429121813"></a><a name="p15767429121813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p15768142912182"><a name="p15768142912182"></a><a name="p15768142912182"></a>If referring to a piece of an object instead of an entire object, this string should contain a valid JSON/Go field access statement, such as desiredState.manifest.containers[2]. For example, if the object reference is to a container within a pod, this would take on a value like: "spec.containers{name}" (where "name" refers to the name of the container that triggered the event) or if no container name is specified "spec.containers[2]" (container with index 2 in this pod). This syntax is chosen only to have some well-defined way of referencing a part of an object.</p>
</td>
</tr>
<tr id="row2075962961820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1768192951814"><a name="p1768192951814"></a><a name="p1768192951814"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p19769829131813"><a name="p19769829131813"></a><a name="p19769829131813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p3770129151814"><a name="p3770129151814"></a><a name="p3770129151814"></a>Kind of the referent. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row775918291184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p11771162961819"><a name="p11771162961819"></a><a name="p11771162961819"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p977202918186"><a name="p977202918186"></a><a name="p977202918186"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p167737299181"><a name="p167737299181"></a><a name="p167737299181"></a>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names</p>
</td>
</tr>
<tr id="row8760529121814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p97741029171814"><a name="p97741029171814"></a><a name="p97741029171814"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1877513294186"><a name="p1877513294186"></a><a name="p1877513294186"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19776729131814"><a name="p19776729131814"></a><a name="p19776729131814"></a>Namespace of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/</p>
</td>
</tr>
<tr id="row1276092913184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p5777112991819"><a name="p5777112991819"></a><a name="p5777112991819"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1777529181810"><a name="p1777529181810"></a><a name="p1777529181810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p6778132941819"><a name="p6778132941819"></a><a name="p6778132941819"></a>Specific resourceVersion to which this reference is made, if any. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency</p>
</td>
</tr>
<tr id="row13760142915186"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p9778629121812"><a name="p9778629121812"></a><a name="p9778629121812"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p577814293182"><a name="p577814293182"></a><a name="p577814293182"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p57791529191810"><a name="p57791529191810"></a><a name="p57791529191810"></a>UID of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#uids</p>
</td>
</tr>
</tbody>
</table>

**表 8**  io.k8s.apimachinery.pkg.apis.meta.v1.ObjectMeta

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.ObjectMeta"></a>
<table><thead align="left"><tr id="row278116293183"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p8785122901820"><a name="p8785122901820"></a><a name="p8785122901820"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p197859297189"><a name="p197859297189"></a><a name="p197859297189"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p2078602918189"><a name="p2078602918189"></a><a name="p2078602918189"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13781629191815"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p5786152961810"><a name="p5786152961810"></a><a name="p5786152961810"></a>annotations</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p878722915180"><a name="p878722915180"></a><a name="p878722915180"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1178814291183"><a name="p1178814291183"></a><a name="p1178814291183"></a>Annotations is an unstructured key value map stored with a resource that may be set by external tools to store and retrieve arbitrary metadata. They are not queryable and should be preserved when modifying objects. More info: http://kubernetes.io/docs/user-guide/annotations</p>
</td>
</tr>
<tr id="row1978182931811"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p478813291184"><a name="p478813291184"></a><a name="p478813291184"></a>clusterName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16124630171812"><a name="p16124630171812"></a><a name="p16124630171812"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p01245301188"><a name="p01245301188"></a><a name="p01245301188"></a>The name of the cluster which the object belongs to. This is used to distinguish resources with same name and namespace in different clusters. This field is not set anywhere right now and apiserver is going to ignore it if set in create or update request.</p>
</td>
</tr>
<tr id="row107818294185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18124103015188"><a name="p18124103015188"></a><a name="p18124103015188"></a>creationTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p31242305186"><a name="p31242305186"></a><a name="p31242305186"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Time object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p91245306184"><a name="p91245306184"></a><a name="p91245306184"></a>Time is a wrapper around time.Time which supports correct marshaling to YAML and JSON.  Wrappers are provided for many of the factory methods that the time package offers.</p>
</td>
</tr>
<tr id="row20782182911811"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1512418306181"><a name="p1512418306181"></a><a name="p1512418306181"></a>deletionGracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p181248309181"><a name="p181248309181"></a><a name="p181248309181"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p14124193012189"><a name="p14124193012189"></a><a name="p14124193012189"></a>Number of seconds allowed for this object to gracefully terminate before it will be removed from the system. Only set when deletionTimestamp is also set. May only be shortened. Read-only.</p>
</td>
</tr>
<tr id="row178216294186"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p412414309181"><a name="p412414309181"></a><a name="p412414309181"></a>deletionTimestamp</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p4125143011812"><a name="p4125143011812"></a><a name="p4125143011812"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Time object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p41251930191810"><a name="p41251930191810"></a><a name="p41251930191810"></a>Time is a wrapper around time.Time which supports correct marshaling to YAML and JSON.  Wrappers are provided for many of the factory methods that the time package offers.</p>
</td>
</tr>
<tr id="row67821295180"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1112512309184"><a name="p1112512309184"></a><a name="p1112512309184"></a>enable</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p161251730161815"><a name="p161251730161815"></a><a name="p161251730161815"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p181254303186"><a name="p181254303186"></a><a name="p181254303186"></a>Enable identify whether the resource is available</p>
</td>
</tr>
<tr id="row678242931815"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1512533012182"><a name="p1512533012182"></a><a name="p1512533012182"></a>finalizers</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p18125133019180"><a name="p18125133019180"></a><a name="p18125133019180"></a>Array of string</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19125230171816"><a name="p19125230171816"></a><a name="p19125230171816"></a>Must be empty before the object is deleted from the registry. Each entry is an identifier for the responsible component that will remove the entry from the list. If the deletionTimestamp of the object is non-nil, entries in this list can only be removed.</p>
</td>
</tr>
<tr id="row1478222981818"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p10126130161820"><a name="p10126130161820"></a><a name="p10126130161820"></a>generateName</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1112673051816"><a name="p1112673051816"></a><a name="p1112673051816"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p12126163017187"><a name="p12126163017187"></a><a name="p12126163017187"></a>GenerateName is an optional prefix, used by the server, to generate a unique name ONLY IF the Name field has not been provided. If this field is used, the name returned to the client will be different than the name passed. This value will also be combined with a unique suffix. The provided value has the same validation rules as the Name field, and may be truncated by the length of the suffix required to make the value unique on the server.</p>
<p id="p412614304183"><a name="p412614304183"></a><a name="p412614304183"></a></p>
<p id="p111263304182"><a name="p111263304182"></a><a name="p111263304182"></a>If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header).</p>
<p id="p612611308181"><a name="p612611308181"></a><a name="p612611308181"></a></p>
<p id="p912612305188"><a name="p912612305188"></a><a name="p912612305188"></a>Applied only if Name is not specified. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#idempotency</p>
</td>
</tr>
<tr id="row37831329201817"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1012633014181"><a name="p1012633014181"></a><a name="p1012633014181"></a>generation</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p13126430131811"><a name="p13126430131811"></a><a name="p13126430131811"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p191261530201818"><a name="p191261530201818"></a><a name="p191261530201818"></a>A sequence number representing a specific generation of the desired state. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row77834297183"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p16126133018182"><a name="p16126133018182"></a><a name="p16126133018182"></a>initializers</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p31274305186"><a name="p31274305186"></a><a name="p31274305186"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Initializers object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p171271130111814"><a name="p171271130111814"></a><a name="p171271130111814"></a>An initializer is a controller which enforces some system invariant at object creation time. This field is a list of initializers that have not yet acted on this object. If nil or empty, this object has been completely initialized. Otherwise, the object is considered uninitialized and is hidden (in list/watch and get calls) from clients that haven't explicitly asked to observe uninitialized objects.</p>
<p id="p12127123017187"><a name="p12127123017187"></a><a name="p12127123017187"></a></p>
<p id="p131271830101813"><a name="p131271830101813"></a><a name="p131271830101813"></a>When an object is created, the system will populate this list with the current set of initializers. Only privileged users may set or modify this list. Once it is empty, it may not be modified further by any user.</p>
</td>
</tr>
<tr id="row18783192931816"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p81279302184"><a name="p81279302184"></a><a name="p81279302184"></a>labels</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p412813021818"><a name="p412813021818"></a><a name="p412813021818"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p812893016189"><a name="p812893016189"></a><a name="p812893016189"></a>Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels</p>
</td>
</tr>
<tr id="row378316298185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p0128153015188"><a name="p0128153015188"></a><a name="p0128153015188"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p7128123031817"><a name="p7128123031817"></a><a name="p7128123031817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p12129123031810"><a name="p12129123031810"></a><a name="p12129123031810"></a>Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names</p>
</td>
</tr>
<tr id="row12783102912185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p19129193015186"><a name="p19129193015186"></a><a name="p19129193015186"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14129143051814"><a name="p14129143051814"></a><a name="p14129143051814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p61291230151817"><a name="p61291230151817"></a><a name="p61291230151817"></a>Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty.</p>
<p id="p1013019307181"><a name="p1013019307181"></a><a name="p1013019307181"></a></p>
<p id="p813011309184"><a name="p813011309184"></a><a name="p813011309184"></a>Must be a DNS_LABEL. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/namespaces</p>
</td>
</tr>
<tr id="row16783629131815"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p113043051818"><a name="p113043051818"></a><a name="p113043051818"></a>ownerReferences</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p20130113010186"><a name="p20130113010186"></a><a name="p20130113010186"></a>io.k8s.apimachinery.pkg.apis.meta.v1.OwnerReference object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p161301330191820"><a name="p161301330191820"></a><a name="p161301330191820"></a>List of objects depended by this object. If ALL objects in the list have been deleted, this object will be garbage collected. If this object is managed by a controller, then an entry in this list will point to this controller, with the controller field set to true. There cannot be more than one managing controller.</p>
</td>
</tr>
<tr id="row2783229191814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p413143071817"><a name="p413143071817"></a><a name="p413143071817"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p513153013182"><a name="p513153013182"></a><a name="p513153013182"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p81311730121818"><a name="p81311730121818"></a><a name="p81311730121818"></a>An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources.</p>
<p id="p2131133010187"><a name="p2131133010187"></a><a name="p2131133010187"></a></p>
<p id="p161311930161818"><a name="p161311930161818"></a><a name="p161311930161818"></a>Populated by the system. Read-only. Value must be treated as opaque by clients and . More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency</p>
</td>
</tr>
<tr id="row12783182910188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1013213061810"><a name="p1013213061810"></a><a name="p1013213061810"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p813233051818"><a name="p813233051818"></a><a name="p813233051818"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p5132330141811"><a name="p5132330141811"></a><a name="p5132330141811"></a>SelfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
<tr id="row878402919185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1313223081820"><a name="p1313223081820"></a><a name="p1313223081820"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p813211303184"><a name="p813211303184"></a><a name="p813211303184"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1613213091810"><a name="p1613213091810"></a><a name="p1613213091810"></a>UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations.</p>
<p id="p2132203012187"><a name="p2132203012187"></a><a name="p2132203012187"></a></p>
<p id="p6132163051819"><a name="p6132163051819"></a><a name="p6132163051819"></a>Populated by the system. Read-only. More info: http://kubernetes.io/docs/user-guide/identifiers#uids</p>
</td>
</tr>
</tbody>
</table>

**表 9**  io.k8s.apimachinery.pkg.apis.meta.v1.OwnerReference

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.OwnerReference"></a>
<table><thead align="left"><tr id="row138121029111819"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p313313307187"><a name="p313313307187"></a><a name="p313313307187"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p013333017187"><a name="p013333017187"></a><a name="p013333017187"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p18134173061816"><a name="p18134173061816"></a><a name="p18134173061816"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row128121729161813"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1513420305188"><a name="p1513420305188"></a><a name="p1513420305188"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p0134193014181"><a name="p0134193014181"></a><a name="p0134193014181"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1513493061818"><a name="p1513493061818"></a><a name="p1513493061818"></a>API version of the referent.</p>
</td>
</tr>
<tr id="row1181220299187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1513493010186"><a name="p1513493010186"></a><a name="p1513493010186"></a>blockOwnerDeletion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p013443011185"><a name="p013443011185"></a><a name="p013443011185"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1213483016183"><a name="p1213483016183"></a><a name="p1213483016183"></a>If true, AND if the owner has the "foregroundDeletion" finalizer, then the owner cannot be deleted from the key-value store until this reference is removed. Defaults to false. To set this field, a user needs "delete" permission of the owner, otherwise 422 (Unprocessable Entity) will be returned.</p>
</td>
</tr>
<tr id="row1481262971817"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1513423011810"><a name="p1513423011810"></a><a name="p1513423011810"></a>controller</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1213419304183"><a name="p1213419304183"></a><a name="p1213419304183"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p113511301185"><a name="p113511301185"></a><a name="p113511301185"></a>If true, this reference points to the managing controller.</p>
</td>
</tr>
<tr id="row781262912187"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p9135830191810"><a name="p9135830191810"></a><a name="p9135830191810"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p191356302188"><a name="p191356302188"></a><a name="p191356302188"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1613514305185"><a name="p1613514305185"></a><a name="p1613514305185"></a>Kind of the referent. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row8813629121814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p91351930151820"><a name="p91351930151820"></a><a name="p91351930151820"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p713573018185"><a name="p713573018185"></a><a name="p713573018185"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p81359306187"><a name="p81359306187"></a><a name="p81359306187"></a>Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names</p>
</td>
</tr>
<tr id="row4813229121810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p19135730101814"><a name="p19135730101814"></a><a name="p19135730101814"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p313513016186"><a name="p313513016186"></a><a name="p313513016186"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p41368303188"><a name="p41368303188"></a><a name="p41368303188"></a>UID of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#uids</p>
</td>
</tr>
</tbody>
</table>

**表 10**  io.k8s.apimachinery.pkg.apis.meta.v1.Initializers

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.Initializers"></a>
<table><thead align="left"><tr id="row282418292186"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p14136113010188"><a name="p14136113010188"></a><a name="p14136113010188"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1113693010187"><a name="p1113693010187"></a><a name="p1113693010187"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p131367303187"><a name="p131367303187"></a><a name="p131367303187"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6825112912184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p413613306184"><a name="p413613306184"></a><a name="p413613306184"></a>pending</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p21361230161812"><a name="p21361230161812"></a><a name="p21361230161812"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Initializer object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19137330131817"><a name="p19137330131817"></a><a name="p19137330131817"></a>Pending is a list of initializers that must execute in order before this object is visible. When the last pending initializer is removed, and no failing result is set, the initializers struct will be set to nil and the object is considered as initialized and visible to all clients.</p>
</td>
</tr>
<tr id="row1382515292181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p13137143001817"><a name="p13137143001817"></a><a name="p13137143001817"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p31371430151813"><a name="p31371430151813"></a><a name="p31371430151813"></a>io.k8s.apimachinery.pkg.apis.meta.v1.Status object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p16137113020184"><a name="p16137113020184"></a><a name="p16137113020184"></a>If result is set with the Failure field, the object will be persisted to storage and then deleted, ensuring that other clients can observe the deletion.</p>
</td>
</tr>
</tbody>
</table>

**表 11**  io.k8s.apimachinery.pkg.apis.meta.v1.Status

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.Status"></a>
<table><thead align="left"><tr id="row14831529161820"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p313793011182"><a name="p313793011182"></a><a name="p313793011182"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p181374301188"><a name="p181374301188"></a><a name="p181374301188"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p7138113071819"><a name="p7138113071819"></a><a name="p7138113071819"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row38311529171816"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p121389303184"><a name="p121389303184"></a><a name="p121389303184"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p713813306184"><a name="p713813306184"></a><a name="p713813306184"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1913823014181"><a name="p1913823014181"></a><a name="p1913823014181"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources</p>
</td>
</tr>
<tr id="row10831152931816"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p4138183091813"><a name="p4138183091813"></a><a name="p4138183091813"></a>code</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p20138930201815"><a name="p20138930201815"></a><a name="p20138930201815"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p16138163041816"><a name="p16138163041816"></a><a name="p16138163041816"></a>Suggested HTTP return code for this status, 0 if not set.</p>
</td>
</tr>
<tr id="row12832202918189"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1513863071811"><a name="p1513863071811"></a><a name="p1513863071811"></a>details</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p513803014185"><a name="p513803014185"></a><a name="p513803014185"></a>io.k8s.apimachinery.pkg.apis.meta.v1.StatusDetails object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1913816308185"><a name="p1913816308185"></a><a name="p1913816308185"></a>Extended data associated with the reason.  Each reason may define its own extended details. This field is optional and the data returned is not guaranteed to conform to any schema except that defined by the reason type.</p>
</td>
</tr>
<tr id="row12832102911185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p201391630171810"><a name="p201391630171810"></a><a name="p201391630171810"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1713911302183"><a name="p1713911302183"></a><a name="p1713911302183"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p6139930171818"><a name="p6139930171818"></a><a name="p6139930171818"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row283222961810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p12139133019185"><a name="p12139133019185"></a><a name="p12139133019185"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p111391630151820"><a name="p111391630151820"></a><a name="p111391630151820"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p51391530161816"><a name="p51391530161816"></a><a name="p51391530161816"></a>A human-readable description of the status of this operation.</p>
</td>
</tr>
<tr id="row2832122910181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p161391130191820"><a name="p161391130191820"></a><a name="p161391130191820"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p9139030131815"><a name="p9139030131815"></a><a name="p9139030131815"></a>io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p41390307183"><a name="p41390307183"></a><a name="p41390307183"></a>Standard list metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row483212298185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p6139183081819"><a name="p6139183081819"></a><a name="p6139183081819"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1213963019180"><a name="p1213963019180"></a><a name="p1213963019180"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p213973011182"><a name="p213973011182"></a><a name="p213973011182"></a>A machine-readable description of why this operation is in the "Failure" status. If this value is empty there is no information available. A Reason clarifies an HTTP status code but does not override it.</p>
</td>
</tr>
<tr id="row198321295185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p114017301183"><a name="p114017301183"></a><a name="p114017301183"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p10140103041813"><a name="p10140103041813"></a><a name="p10140103041813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1514033051812"><a name="p1514033051812"></a><a name="p1514033051812"></a>Status of the operation. One of: "Success" or "Failure". More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#spec-and-status</p>
</td>
</tr>
</tbody>
</table>

**表 12**  io.k8s.apimachinery.pkg.apis.meta.v1.ListMeta

<a name="table1846162917182"></a>
<table><thead align="left"><tr id="row784772971810"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p314053061812"><a name="p314053061812"></a><a name="p314053061812"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1014013014184"><a name="p1014013014184"></a><a name="p1014013014184"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p18140730181813"><a name="p18140730181813"></a><a name="p18140730181813"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1784762915184"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1114023011185"><a name="p1114023011185"></a><a name="p1114023011185"></a>continue</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p5140133021810"><a name="p5140133021810"></a><a name="p5140133021810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1814119302187"><a name="p1814119302187"></a><a name="p1814119302187"></a>continue may be set if the user set a limit on the number of items returned, and indicates that the server has more data available. The value is opaque and may be used to issue another request to the endpoint that served this list to retrieve the next set of available objects. Continuing a list may not be possible if the server configuration has changed or more than a few minutes have passed. The resourceVersion field returned when using this continue value will be identical to the value in the first response.</p>
</td>
</tr>
<tr id="row284792919181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p514153016183"><a name="p514153016183"></a><a name="p514153016183"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p11414309182"><a name="p11414309182"></a><a name="p11414309182"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p014112304189"><a name="p014112304189"></a><a name="p014112304189"></a>String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency</p>
</td>
</tr>
<tr id="row0847112911181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p181411830171819"><a name="p181411830171819"></a><a name="p181411830171819"></a>selfLink</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p6141183081813"><a name="p6141183081813"></a><a name="p6141183081813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p13141163017188"><a name="p13141163017188"></a><a name="p13141163017188"></a>selfLink is a URL representing this object. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 13**  io.k8s.apimachinery.pkg.apis.meta.v1.StatusDetails

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.StatusDetails"></a>
<table><thead align="left"><tr id="row385519295183"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p151412030161816"><a name="p151412030161816"></a><a name="p151412030161816"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p11141330151811"><a name="p11141330151811"></a><a name="p11141330151811"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p7141330131812"><a name="p7141330131812"></a><a name="p7141330131812"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row108551729111810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p8141930191818"><a name="p8141930191818"></a><a name="p8141930191818"></a>causes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1914113309183"><a name="p1914113309183"></a><a name="p1914113309183"></a>io.k8s.apimachinery.pkg.apis.meta.v1.StatusCause object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p101418309188"><a name="p101418309188"></a><a name="p101418309188"></a>The Causes array includes more details associated with the StatusReason failure. Not all StatusReasons may provide detailed causes.</p>
</td>
</tr>
<tr id="row1385592941820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1141163015182"><a name="p1141163015182"></a><a name="p1141163015182"></a>group</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p15142143013182"><a name="p15142143013182"></a><a name="p15142143013182"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p714211302189"><a name="p714211302189"></a><a name="p714211302189"></a>The group attribute of the resource associated with the status StatusReason.</p>
</td>
</tr>
<tr id="row198558294182"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1014213308183"><a name="p1014213308183"></a><a name="p1014213308183"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p18142173016181"><a name="p18142173016181"></a><a name="p18142173016181"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p16142123011185"><a name="p16142123011185"></a><a name="p16142123011185"></a>The kind attribute of the resource associated with the status StatusReason. On some operations may differ from the requested resource Kind. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row985642961820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p121421330131817"><a name="p121421330131817"></a><a name="p121421330131817"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p414203011184"><a name="p414203011184"></a><a name="p414203011184"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p10142193011813"><a name="p10142193011813"></a><a name="p10142193011813"></a>The name attribute of the resource associated with the status StatusReason (when there is a single name which can be described).</p>
</td>
</tr>
<tr id="row1485616299186"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p114216303186"><a name="p114216303186"></a><a name="p114216303186"></a>retryAfterSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1514273010184"><a name="p1514273010184"></a><a name="p1514273010184"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p414213031812"><a name="p414213031812"></a><a name="p414213031812"></a>If specified, the time in seconds before the operation should be retried. Some errors may indicate the client must take an alternate action - for those errors this field may indicate how long to wait before taking the alternate action.</p>
</td>
</tr>
<tr id="row1385652971813"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18142193081811"><a name="p18142193081811"></a><a name="p18142193081811"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p19142123091813"><a name="p19142123091813"></a><a name="p19142123091813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p0142153019188"><a name="p0142153019188"></a><a name="p0142153019188"></a>UID of the resource. (when there is a single resource which can be described). More info: http://kubernetes.io/docs/user-guide/identifiers#uids</p>
</td>
</tr>
</tbody>
</table>

**表 14**  io.k8s.apimachinery.pkg.apis.meta.v1.StatusCause

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.StatusCause"></a>
<table><thead align="left"><tr id="row4873112914187"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1514373041814"><a name="p1514373041814"></a><a name="p1514373041814"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1914343017185"><a name="p1914343017185"></a><a name="p1914343017185"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p714320308187"><a name="p714320308187"></a><a name="p714320308187"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1587314293188"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p714312301181"><a name="p714312301181"></a><a name="p714312301181"></a>field</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p4143133012189"><a name="p4143133012189"></a><a name="p4143133012189"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p714333015185"><a name="p714333015185"></a><a name="p714333015185"></a>The field of the resource that has caused this error, as named by its JSON serialization. May include dot and postfix notation for nested attributes. Arrays are zero-indexed.  Fields may appear more than once in an array of causes due to fields having multiple errors. Optional.</p>
<p id="p2143143015184"><a name="p2143143015184"></a><a name="p2143143015184"></a>Examples:</p>
<p id="p1514313308183"><a name="p1514313308183"></a><a name="p1514313308183"></a>"name" - the field "name" on the current resource</p>
<p id="p101433309185"><a name="p101433309185"></a><a name="p101433309185"></a>"items[0].name" - the field "name" on the first array entry in "items"</p>
</td>
</tr>
<tr id="row2873629161817"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p151441230151813"><a name="p151441230151813"></a><a name="p151441230151813"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p714433012186"><a name="p714433012186"></a><a name="p714433012186"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1814463031818"><a name="p1814463031818"></a><a name="p1814463031818"></a>A human-readable description of the cause of the error.  This field may be presented as-is to a reader.</p>
</td>
</tr>
<tr id="row18873102971816"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p314433041810"><a name="p314433041810"></a><a name="p314433041810"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1914473017186"><a name="p1914473017186"></a><a name="p1914473017186"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p5144123016184"><a name="p5144123016184"></a><a name="p5144123016184"></a>A machine-readable description of the cause of the error. If this value is empty there is no information available.</p>
</td>
</tr>
</tbody>
</table>

**表 15**  io.k8s.apimachinery.pkg.apis.meta.v1.Initializer

<a name="response_io.k8s.apimachinery.pkg.apis.meta.v1.Initializer"></a>
<table><thead align="left"><tr id="row1588514294185"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p18144330191818"><a name="p18144330191818"></a><a name="p18144330191818"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p5144430171810"><a name="p5144430171810"></a><a name="p5144430171810"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p214533017182"><a name="p214533017182"></a><a name="p214533017182"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15885122971810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1214510304181"><a name="p1214510304181"></a><a name="p1214510304181"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1014517307187"><a name="p1014517307187"></a><a name="p1014517307187"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p201459303182"><a name="p201459303182"></a><a name="p201459303182"></a>name of the process that is responsible for initializing this object.</p>
</td>
</tr>
</tbody>
</table>

**表 16**  io.k8s.api.core.v1.ObjectReference

<a name="table0892192919189"></a>
<table><thead align="left"><tr id="row5893529141811"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p13145930191811"><a name="p13145930191811"></a><a name="p13145930191811"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p9145143015185"><a name="p9145143015185"></a><a name="p9145143015185"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p014663012185"><a name="p014663012185"></a><a name="p014663012185"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row889412294181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p114616308183"><a name="p114616308183"></a><a name="p114616308183"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1014613304182"><a name="p1014613304182"></a><a name="p1014613304182"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p11146153031819"><a name="p11146153031819"></a><a name="p11146153031819"></a>API version of the referent.</p>
</td>
</tr>
<tr id="row3894102914181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1146173081816"><a name="p1146173081816"></a><a name="p1146173081816"></a>fieldPath</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14146930141813"><a name="p14146930141813"></a><a name="p14146930141813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1514619309185"><a name="p1514619309185"></a><a name="p1514619309185"></a>If referring to a piece of an object instead of an entire object, this string should contain a valid JSON/Go field access statement, such as desiredState.manifest.containers[2]. For example, if the object reference is to a container within a pod, this would take on a value like: "spec.containers{name}" (where "name" refers to the name of the container that triggered the event) or if no container name is specified "spec.containers[2]" (container with index 2 in this pod). This syntax is chosen only to have some well-defined way of referencing a part of an object.</p>
</td>
</tr>
<tr id="row188941729131811"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p81461930111810"><a name="p81461930111810"></a><a name="p81461930111810"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1514716309181"><a name="p1514716309181"></a><a name="p1514716309181"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p101471830141817"><a name="p101471830141817"></a><a name="p101471830141817"></a>Kind of the referent. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds</p>
</td>
</tr>
<tr id="row4894122921817"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1014783091812"><a name="p1014783091812"></a><a name="p1014783091812"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1114723015186"><a name="p1114723015186"></a><a name="p1114723015186"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p9147103016184"><a name="p9147103016184"></a><a name="p9147103016184"></a>Name of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#names</p>
</td>
</tr>
<tr id="row98945297185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1314714302181"><a name="p1314714302181"></a><a name="p1314714302181"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p61471530181813"><a name="p61471530181813"></a><a name="p61471530181813"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p15147133041819"><a name="p15147133041819"></a><a name="p15147133041819"></a>Namespace of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/</p>
</td>
</tr>
<tr id="row7894162931820"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p141471230191817"><a name="p141471230191817"></a><a name="p141471230191817"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p141471730191819"><a name="p141471730191819"></a><a name="p141471730191819"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1314783016186"><a name="p1314783016186"></a><a name="p1314783016186"></a>Specific resourceVersion to which this reference is made, if any. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency</p>
</td>
</tr>
<tr id="row1894172919183"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p51482306180"><a name="p51482306180"></a><a name="p51482306180"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p171481430141817"><a name="p171481430141817"></a><a name="p171481430141817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19148123014185"><a name="p19148123014185"></a><a name="p19148123014185"></a>UID of the referent. More info: https://kubernetes.io/docs/concepts/overview/working-with-objects/names/#uids</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section101481308186"></a>

无

## 响应示例<a name="section814803011817"></a>

状态码为 200 时:

```
{
    "apiVersion": "v1",
    "items": [
        {
            "apiVersion": "v1",
            "count": 9,
            "eventTime": null,
            "firstTimestamp": "2019-07-03T07:35:30Z",
            "involvedObject": {
                "apiVersion": "v1",
                "kind": "Pod",
                "name": "coredns-85cb64445b-mvthn",
                "namespace": "kube-system",
                "resourceVersion": "3714354",
                "uid": "225b433a-9d65-11e9-8d38-fa163eb8e88a"
            },
            "kind": "Event",
            "lastTimestamp": "2019-07-03T07:40:59Z",
            "message": "0/1 nodes are available: 1 Insufficient memory.",
            "metadata": {
                "creationTimestamp": "2019-07-03T07:35:30Z",
                "name": "coredns-85cb64445b-mvthn.15add571ce713ccc",
                "namespace": "kube-system",
                "resourceVersion": "20929",
                "selfLink": "/api/v1/namespaces/kube-system/events/coredns-85cb64445b-mvthn.15add571ce713ccc",
                "uid": "225eb9ac-9d65-11e9-8d38-fa163eb8e88a"
            },
            "reason": "FailedScheduling",
            "reportingComponent": "",
            "reportingInstance": "",
            "source": {
                "component": "default-scheduler"
            },
            "type": "Warning"
        },
        {
            "apiVersion": "v1",
            "count": 10,
            "eventTime": null,
            "firstTimestamp": "2019-07-03T07:35:30Z",
            "involvedObject": {
                "apiVersion": "v1",
                "kind": "Pod",
                "name": "coredns-85cb64445b-zq9hw",
                "namespace": "kube-system",
                "resourceVersion": "3714351",
                "uid": "225aac93-9d65-11e9-8d38-fa163eb8e88a"
            },
            "kind": "Event",
            "lastTimestamp": "2019-07-03T07:40:59Z",
            "message": "0/1 nodes are available: 1 Insufficient memory.",
            "metadata": {
                "creationTimestamp": "2019-07-03T07:35:30Z",
                "name": "coredns-85cb64445b-zq9hw.15add571cd0faa51",
                "namespace": "kube-system",
                "resourceVersion": "20930",
                "selfLink": "/api/v1/namespaces/kube-system/events/coredns-85cb64445b-zq9hw.15add571cd0faa51",
                "uid": "225b53ba-9d65-11e9-8d38-fa163eb8e88a"
            },
            "reason": "FailedScheduling",
            "reportingComponent": "",
            "reportingInstance": "",
            "source": {
                "component": "default-scheduler"
            },
            "type": "Warning"
        },
        {
            "apiVersion": "v1",
            "count": 1,
            "eventTime": null,
            "firstTimestamp": "2019-07-03T07:35:30Z",
            "involvedObject": {
                "apiVersion": "apps/v1",
                "kind": "ReplicaSet",
                "name": "coredns-85cb64445b",
                "namespace": "kube-system",
                "resourceVersion": "3714349",
                "uid": "22586f58-9d65-11e9-8d38-fa163eb8e88a"
            },
            "kind": "Event",
            "lastTimestamp": "2019-07-03T07:35:30Z",
            "message": "Created pod: coredns-85cb64445b-zq9hw",
            "metadata": {
                "creationTimestamp": "2019-07-03T07:35:30Z",
                "name": "coredns-85cb64445b.15add571cd1f20ce",
                "namespace": "kube-system",
                "resourceVersion": "20899",
                "selfLink": "/api/v1/namespaces/kube-system/events/coredns-85cb64445b.15add571cd1f20ce",
                "uid": "225b5363-9d65-11e9-8d38-fa163eb8e88a"
            },
            "reason": "SuccessfulCreate",
            "reportingComponent": "",
            "reportingInstance": "",
            "source": {
                "component": "replicaset-controller"
            },
            "type": "Normal"
        },
        {
            "apiVersion": "v1",
            "count": 1,
            "eventTime": null,
            "firstTimestamp": "2019-07-03T07:35:30Z",
            "involvedObject": {
                "apiVersion": "apps/v1",
                "kind": "ReplicaSet",
                "name": "coredns-85cb64445b",
                "namespace": "kube-system",
                "resourceVersion": "3714349",
                "uid": "22586f58-9d65-11e9-8d38-fa163eb8e88a"
            },
            "kind": "Event",
            "lastTimestamp": "2019-07-03T07:35:30Z",
            "message": "Created pod: coredns-85cb64445b-mvthn",
            "metadata": {
                "creationTimestamp": "2019-07-03T07:35:30Z",
                "name": "coredns-85cb64445b.15add571cd6f40ae",
                "namespace": "kube-system",
                "resourceVersion": "20901",
                "selfLink": "/api/v1/namespaces/kube-system/events/coredns-85cb64445b.15add571cd6f40ae",
                "uid": "225c5dae-9d65-11e9-8d38-fa163eb8e88a"
            },
            "reason": "SuccessfulCreate",
            "reportingComponent": "",
            "reportingInstance": "",
            "source": {
                "component": "replicaset-controller"
            },
            "type": "Normal"
        },
        {
            "apiVersion": "v1",
            "count": 1,
            "eventTime": null,
            "firstTimestamp": "2019-07-03T07:35:30Z",
            "involvedObject": {
                "apiVersion": "apps/v1",
                "kind": "Deployment",
                "name": "coredns",
                "namespace": "kube-system",
                "resourceVersion": "3714347",
                "uid": "22573447-9d65-11e9-8d38-fa163eb8e88a"
            },
            "kind": "Event",
            "lastTimestamp": "2019-07-03T07:35:30Z",
            "message": "Scaled up replica set coredns-85cb64445b to 2",
            "metadata": {
                "creationTimestamp": "2019-07-03T07:35:30Z",
                "name": "coredns.15add571cc4fcfab",
                "namespace": "kube-system",
                "resourceVersion": "20898",
                "selfLink": "/api/v1/namespaces/kube-system/events/coredns.15add571cc4fcfab",
                "uid": "22593def-9d65-11e9-8d38-fa163eb8e88a"
            },
            "reason": "ScalingReplicaSet",
            "reportingComponent": "",
            "reportingInstance": "",
            "source": {
                "component": "deployment-controller"
            },
            "type": "Normal"
        }
    ],
    "kind": "List",
    "metadata": {
        "resourceVersion": "",
        "selfLink": ""
    }
}
```

## 返回值<a name="section10159153010185"></a>

<a name="table508"></a>
<table><thead align="left"><tr id="row14963102991818"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p2016033011813"><a name="p2016033011813"></a><a name="p2016033011813"></a>返回值</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p5160143091813"><a name="p5160143091813"></a><a name="p5160143091813"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row16963112920183"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p171605302183"><a name="p171605302183"></a><a name="p171605302183"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p14160193012186"><a name="p14160193012186"></a><a name="p14160193012186"></a>OK</p>
</td>
</tr>
<tr id="row496316296184"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p016016305183"><a name="p016016305183"></a><a name="p016016305183"></a>401</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p181601430101819"><a name="p181601430101819"></a><a name="p181601430101819"></a>Unauthorized</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section91601930111812"></a>

无

