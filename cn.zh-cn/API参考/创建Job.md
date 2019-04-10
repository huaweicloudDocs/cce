# 创建Job<a name="cce_02_0157"></a>

## 功能介绍<a name="section5825523"></a>

This API is used to create a Job resource object.

## URI<a name="section52429714"></a>

POST /apis/batch/v1/namespaces/\{namespace\}/jobs

[表1](#table65625523)描述该API的参数。

**表 1**  参数解释

<a name="table65625523"></a>
<table><thead align="left"><tr id="row19842874"><th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.169999999999998%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="60.61%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row54819108"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p11162788"><a name="p11162788"></a><a name="p11162788"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p31770653"><a name="p31770653"></a><a name="p31770653"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p23286070"><a name="p23286070"></a><a name="p23286070"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="row8248038"><td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.1 "><p id="p64111314"><a name="p64111314"></a><a name="p64111314"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="17.169999999999998%" headers="mcps1.2.4.1.2 "><p id="p25633971"><a name="p25633971"></a><a name="p25633971"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="60.61%" headers="mcps1.2.4.1.3 "><p id="p63085809"><a name="p63085809"></a><a name="p63085809"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section2105383"></a>

**请求参数：**

请求参数如[表2](#table8040885)所示。

**表 2**  请求参数

<a name="table8040885"></a>
<table><thead align="left"><tr id="row23603642"><th class="cellrowborder" valign="top" width="22.447755224477554%" id="mcps1.2.5.1.1"><p id="p32846815"><a name="p32846815"></a><a name="p32846815"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.288571142885711%" id="mcps1.2.5.1.2"><p id="p43346336"><a name="p43346336"></a><a name="p43346336"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.3"><p id="p21392359"><a name="p21392359"></a><a name="p21392359"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.85571442855714%" id="mcps1.2.5.1.4"><p id="p55059481"><a name="p55059481"></a><a name="p55059481"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row30632992"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p65353316"><a name="p65353316"></a><a name="p65353316"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p59127244"><a name="p59127244"></a><a name="p59127244"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p24577473"><a name="p24577473"></a><a name="p24577473"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p44618282"><a name="p44618282"></a><a name="p44618282"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row66020222"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p46037745"><a name="p46037745"></a><a name="p46037745"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p38069836"><a name="p38069836"></a><a name="p38069836"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p63757880"><a name="p63757880"></a><a name="p63757880"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p64114652"><a name="p64114652"></a><a name="p64114652"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row40160963"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p31812591"><a name="p31812591"></a><a name="p31812591"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p26683112"><a name="p26683112"></a><a name="p26683112"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p13848469"><a name="p13848469"></a><a name="p13848469"></a><a href="公共请求参数.md#zh-cn_topic_0079614925_table47756489">表11</a></p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p29204826"><a name="p29204826"></a><a name="p29204826"></a>Standard list metadata.</p>
</td>
</tr>
<tr id="row61516845"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p16808552"><a name="p16808552"></a><a name="p16808552"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p19315447"><a name="p19315447"></a><a name="p19315447"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p21047363"><a name="p21047363"></a><a name="p21047363"></a><a href="#table51402650">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p42706636"><a name="p42706636"></a><a name="p42706636"></a>Spec defines the desired identities of pods in this set.</p>
</td>
</tr>
<tr id="row48815407"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p61733920"><a name="p61733920"></a><a name="p61733920"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.2.5.1.2 "><p id="p34391662"><a name="p34391662"></a><a name="p34391662"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.3 "><p id="p34261248"><a name="p34261248"></a><a name="p34261248"></a><a href="#table28665255">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p11952954"><a name="p11952954"></a><a name="p11952954"></a>Status is the current status of Pods in this StatefulSet. This data may be out of date by some window of time.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  status字段数据结构说明

<a name="table28665255"></a>
<table><thead align="left"><tr id="row8005580"><th class="cellrowborder" valign="top" width="22.68%" id="mcps1.2.5.1.1"><p id="p44472221"><a name="p44472221"></a><a name="p44472221"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.430000000000001%" id="mcps1.2.5.1.2"><p id="p45480180"><a name="p45480180"></a><a name="p45480180"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.59%" id="mcps1.2.5.1.3"><p id="p60015926"><a name="p60015926"></a><a name="p60015926"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.3%" id="mcps1.2.5.1.4"><p id="p29451853"><a name="p29451853"></a><a name="p29451853"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row36789921"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p27193625"><a name="p27193625"></a><a name="p27193625"></a>active</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p55200030"><a name="p55200030"></a><a name="p55200030"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p42017431"><a name="p42017431"></a><a name="p42017431"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p47968749"><a name="p47968749"></a><a name="p47968749"></a>The number of actively running pods.</p>
</td>
</tr>
<tr id="row29065558"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p5499969"><a name="p5499969"></a><a name="p5499969"></a>completionTime</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p42844349"><a name="p42844349"></a><a name="p42844349"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p47840241"><a name="p47840241"></a><a name="p47840241"></a>Time</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p49854342"><a name="p49854342"></a><a name="p49854342"></a>Replicas is the number of actual replicas.</p>
</td>
</tr>
<tr id="row46035900"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p37920453"><a name="p37920453"></a><a name="p37920453"></a>conditions</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p51657858"><a name="p51657858"></a><a name="p51657858"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p23536988"><a name="p23536988"></a><a name="p23536988"></a><a href="#table38300416">表8</a></p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p45704206"><a name="p45704206"></a><a name="p45704206"></a>The latest available observations of an object's current state. More info:</p>
</td>
</tr>
<tr id="row8684677"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p32370212"><a name="p32370212"></a><a name="p32370212"></a>failed</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p4741504"><a name="p4741504"></a><a name="p4741504"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p48517504"><a name="p48517504"></a><a name="p48517504"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p37603724"><a name="p37603724"></a><a name="p37603724"></a>The number of pods which reached phase Failed.</p>
</td>
</tr>
<tr id="row2889203"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p32698877"><a name="p32698877"></a><a name="p32698877"></a>startTime</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p31363400"><a name="p31363400"></a><a name="p31363400"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p57407484"><a name="p57407484"></a><a name="p57407484"></a>Time</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p19494591"><a name="p19494591"></a><a name="p19494591"></a>Represents time when the job was acknowledged by the job controller. It is not guaranteed to be set in happens-before order across separate operations. It is represented in RFC3339 form and is in UTC.</p>
</td>
</tr>
<tr id="row41233599"><td class="cellrowborder" valign="top" width="22.68%" headers="mcps1.2.5.1.1 "><p id="p51587231"><a name="p51587231"></a><a name="p51587231"></a>succeeded</p>
</td>
<td class="cellrowborder" valign="top" width="14.430000000000001%" headers="mcps1.2.5.1.2 "><p id="p17816163"><a name="p17816163"></a><a name="p17816163"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.59%" headers="mcps1.2.5.1.3 "><p id="p33823092"><a name="p33823092"></a><a name="p33823092"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="43.3%" headers="mcps1.2.5.1.4 "><p id="p55315897"><a name="p55315897"></a><a name="p55315897"></a>The number of pods which reached phase Succeeded.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  spec字段数据结构说明

<a name="table51402650"></a>
<table><thead align="left"><tr id="row2975313"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.5.1.1"><p id="p39673810"><a name="p39673810"></a><a name="p39673810"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p59462043"><a name="p59462043"></a><a name="p59462043"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.5.1.3"><p id="p51696213"><a name="p51696213"></a><a name="p51696213"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42%" id="mcps1.2.5.1.4"><p id="p26643752"><a name="p26643752"></a><a name="p26643752"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row10660283"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p58176566"><a name="p58176566"></a><a name="p58176566"></a>activeDeadlineSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p14681410"><a name="p14681410"></a><a name="p14681410"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p48343558"><a name="p48343558"></a><a name="p48343558"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p23514155"><a name="p23514155"></a><a name="p23514155"></a>Specifies the duration in seconds relative to the startTime that the job may be active before the system tries to terminate it; value must be positive integer</p>
</td>
</tr>
<tr id="row34171955124819"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p64171355194815"><a name="p64171355194815"></a><a name="p64171355194815"></a>backoffLimit</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p6418115515484"><a name="p6418115515484"></a><a name="p6418115515484"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p8418155574814"><a name="p8418155574814"></a><a name="p8418155574814"></a>Integer(int32)</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p74187556484"><a name="p74187556484"></a><a name="p74187556484"></a>Specifies the number of retries before marking this job failed. Defaults to 6.</p>
</td>
</tr>
<tr id="row10300809"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p29059234"><a name="p29059234"></a><a name="p29059234"></a>completions</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p4987759"><a name="p4987759"></a><a name="p4987759"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p1355353"><a name="p1355353"></a><a name="p1355353"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p42674759"><a name="p42674759"></a><a name="p42674759"></a>Specifies the desired number of successfully finished pods the job should be run with. Setting to nil means that the success of any pod signals the success of all pods, and allows parallelism to have any positive value. Setting to 1 means that parallelism is limited to 1 and the success of that pod signals the success of the job.</p>
</td>
</tr>
<tr id="row34103458"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p10916689"><a name="p10916689"></a><a name="p10916689"></a>manualSelector</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p11836605"><a name="p11836605"></a><a name="p11836605"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p19240909"><a name="p19240909"></a><a name="p19240909"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p15009769"><a name="p15009769"></a><a name="p15009769"></a>manualSelector controls generation of pod labels and pod selectors. Leave manualSelector unset unless you are certain what you are doing. When false or unset, the system pick labels unique to this job and appends those labels to the pod template. When true, the user is responsible for picking unique labels and specifying the selector. Failure to pick a unique label may cause this and other jobs to not function correctly. However, You may see manualSelector=true in jobs that were created with the old extensions/v1beta1 API.</p>
</td>
</tr>
<tr id="row7831802"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p30396264"><a name="p30396264"></a><a name="p30396264"></a>parallelism</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p46178330"><a name="p46178330"></a><a name="p46178330"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p49457273"><a name="p49457273"></a><a name="p49457273"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p46616172"><a name="p46616172"></a><a name="p46616172"></a>Specifies the maximum desired number of pods the job should run at any given time. The actual number of pods running in steady state will be less than this number when ((.spec.completions - .status.successful) &lt; .spec.parallelism), i.e. when the work left to do is less than max parallelism.</p>
</td>
</tr>
<tr id="row17813596"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p33615152"><a name="p33615152"></a><a name="p33615152"></a>selector</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p38472785"><a name="p38472785"></a><a name="p38472785"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p29287846"><a name="p29287846"></a><a name="p29287846"></a><a href="#table21755034">表5</a></p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p10221142"><a name="p10221142"></a><a name="p10221142"></a>Selector is a label query over pods that should match the replica count. If empty, defaulted to labels on the pod template.</p>
</td>
</tr>
<tr id="row24881422"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="p2129264"><a name="p2129264"></a><a name="p2129264"></a>template</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p38252711"><a name="p38252711"></a><a name="p38252711"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p11461915"><a name="p11461915"></a><a name="p11461915"></a><a href="#table7743895">表7</a></p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="p34237264"><a name="p34237264"></a><a name="p34237264"></a>Template is the object that describes the pod that will be created if insufficient replicas are detected. Each pod stamped out by the StatefulSet will fulfill this Template, but have a unique identity from the rest of the StatefulSet.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  selector字段数据结构说明

<a name="table21755034"></a>
<table><thead align="left"><tr id="row21376903"><th class="cellrowborder" valign="top" width="22.447755224477554%" id="mcps1.2.5.1.1"><p id="p53807619"><a name="p53807619"></a><a name="p53807619"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.308469153084694%" id="mcps1.2.5.1.2"><p id="p63449850"><a name="p63449850"></a><a name="p63449850"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.3"><p id="p39164246"><a name="p39164246"></a><a name="p39164246"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.85571442855714%" id="mcps1.2.5.1.4"><p id="p18187391"><a name="p18187391"></a><a name="p18187391"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row63892572"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p7915862"><a name="p7915862"></a><a name="p7915862"></a>matchExpressions</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084694%" headers="mcps1.2.5.1.2 "><p id="p37205076"><a name="p37205076"></a><a name="p37205076"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p60821183"><a name="p60821183"></a><a name="p60821183"></a><a href="#table27743911">表6</a></p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p46792305"><a name="p46792305"></a><a name="p46792305"></a>matchExpressions is a list of label selector requirements. The requirements are ANDed.</p>
</td>
</tr>
<tr id="row18477562"><td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.2.5.1.1 "><p id="p20287514"><a name="p20287514"></a><a name="p20287514"></a>matchLabels</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084694%" headers="mcps1.2.5.1.2 "><p id="p32675910"><a name="p32675910"></a><a name="p32675910"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p29503079"><a name="p29503079"></a><a name="p29503079"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42.85571442855714%" headers="mcps1.2.5.1.4 "><p id="p40939237"><a name="p40939237"></a><a name="p40939237"></a>MatchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</p>
</td>
</tr>
</tbody>
</table>

**表 6**  matchExpressions字段数据结构说明

<a name="table27743911"></a>
<table><thead align="left"><tr id="row20896483"><th class="cellrowborder" valign="top" width="22.447755224477547%" id="mcps1.2.5.1.1"><p id="p14893544"><a name="p14893544"></a><a name="p14893544"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.308469153084689%" id="mcps1.2.5.1.2"><p id="p65526430"><a name="p65526430"></a><a name="p65526430"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.40795920407959%" id="mcps1.2.5.1.3"><p id="p6040620"><a name="p6040620"></a><a name="p6040620"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.83581641835816%" id="mcps1.2.5.1.4"><p id="p19528251"><a name="p19528251"></a><a name="p19528251"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row38284531"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p14039291"><a name="p14039291"></a><a name="p14039291"></a>key</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p63440763"><a name="p63440763"></a><a name="p63440763"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p38428188"><a name="p38428188"></a><a name="p38428188"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p25675525"><a name="p25675525"></a><a name="p25675525"></a>key is the label key that the selector applies to.</p>
</td>
</tr>
<tr id="row29753141"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p61194206"><a name="p61194206"></a><a name="p61194206"></a>operator</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p57783652"><a name="p57783652"></a><a name="p57783652"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p49964206"><a name="p49964206"></a><a name="p49964206"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p20568868"><a name="p20568868"></a><a name="p20568868"></a>operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</p>
</td>
</tr>
<tr id="row50902092"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p29428784"><a name="p29428784"></a><a name="p29428784"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p34921333"><a name="p34921333"></a><a name="p34921333"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p10055747"><a name="p10055747"></a><a name="p10055747"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p9209153"><a name="p9209153"></a><a name="p9209153"></a>values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  PodTemplateSpec字段数据结构说明

<a name="table7743895"></a>
<table><thead align="left"><tr id="row20722603"><th class="cellrowborder" valign="top" width="22.447755224477547%" id="mcps1.2.5.1.1"><p id="p809271"><a name="p809271"></a><a name="p809271"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.308469153084689%" id="mcps1.2.5.1.2"><p id="p65550951"><a name="p65550951"></a><a name="p65550951"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.40795920407959%" id="mcps1.2.5.1.3"><p id="p8026787"><a name="p8026787"></a><a name="p8026787"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.83581641835816%" id="mcps1.2.5.1.4"><p id="p46190036"><a name="p46190036"></a><a name="p46190036"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row50405474"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p56311604"><a name="p56311604"></a><a name="p56311604"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p64946099"><a name="p64946099"></a><a name="p64946099"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p26142662"><a name="p26142662"></a><a name="p26142662"></a><a href="公共请求参数.md#zh-cn_topic_0079614925_table47756489">表11</a></p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p66192520"><a name="p66192520"></a><a name="p66192520"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="row58861770"><td class="cellrowborder" valign="top" width="22.447755224477547%" headers="mcps1.2.5.1.1 "><p id="p3074059"><a name="p3074059"></a><a name="p3074059"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="15.308469153084689%" headers="mcps1.2.5.1.2 "><p id="p47672192"><a name="p47672192"></a><a name="p47672192"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.40795920407959%" headers="mcps1.2.5.1.3 "><p id="p36242321"><a name="p36242321"></a><a name="p36242321"></a><a href="公共请求参数.md#zh-cn_topic_0079614925_table66152725">表24</a></p>
</td>
<td class="cellrowborder" valign="top" width="41.83581641835816%" headers="mcps1.2.5.1.4 "><p id="p46869096"><a name="p46869096"></a><a name="p46869096"></a>Specification of the desired behavior of the pod.</p>
</td>
</tr>
</tbody>
</table>

**表 8**  JobCondition字段数据结构说明

<a name="table38300416"></a>
<table><thead align="left"><tr id="row20089490"><th class="cellrowborder" valign="top" width="20.407959204079592%" id="mcps1.2.5.1.1"><p id="p16635979"><a name="p16635979"></a><a name="p16635979"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.5.1.2"><p id="p5337057"><a name="p5337057"></a><a name="p5337057"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="23.46765323467653%" id="mcps1.2.5.1.3"><p id="p29648443"><a name="p29648443"></a><a name="p29648443"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.796020397960206%" id="mcps1.2.5.1.4"><p id="p52713665"><a name="p52713665"></a><a name="p52713665"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row41948509"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p42386036"><a name="p42386036"></a><a name="p42386036"></a>lastProbeTime</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p10716912"><a name="p10716912"></a><a name="p10716912"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="23.46765323467653%" headers="mcps1.2.5.1.3 "><p id="p62763577"><a name="p62763577"></a><a name="p62763577"></a>Time</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p50684982"><a name="p50684982"></a><a name="p50684982"></a>Last time the condition was checked.</p>
</td>
</tr>
<tr id="row53511660"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p39477203"><a name="p39477203"></a><a name="p39477203"></a>lastTransitionTime</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p43536866"><a name="p43536866"></a><a name="p43536866"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="23.46765323467653%" headers="mcps1.2.5.1.3 "><p id="p36825282"><a name="p36825282"></a><a name="p36825282"></a>Time</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p30057883"><a name="p30057883"></a><a name="p30057883"></a>Last time the condition transit from one status to another.</p>
</td>
</tr>
<tr id="row2085492"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p34707124"><a name="p34707124"></a><a name="p34707124"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p59813632"><a name="p59813632"></a><a name="p59813632"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="23.46765323467653%" headers="mcps1.2.5.1.3 "><p id="p13066049"><a name="p13066049"></a><a name="p13066049"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p51717087"><a name="p51717087"></a><a name="p51717087"></a>Human readable message indicating details about last transition</p>
</td>
</tr>
<tr id="row62800604"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p53684176"><a name="p53684176"></a><a name="p53684176"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p53450963"><a name="p53450963"></a><a name="p53450963"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="23.46765323467653%" headers="mcps1.2.5.1.3 "><p id="p34560784"><a name="p34560784"></a><a name="p34560784"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p47960109"><a name="p47960109"></a><a name="p47960109"></a>(brief) reason for the condition's last transition.</p>
</td>
</tr>
<tr id="row28987799"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p66310376"><a name="p66310376"></a><a name="p66310376"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p2431341"><a name="p2431341"></a><a name="p2431341"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="23.46765323467653%" headers="mcps1.2.5.1.3 "><p id="p62720910"><a name="p62720910"></a><a name="p62720910"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p47228981"><a name="p47228981"></a><a name="p47228981"></a>Status of the condition, one of True, False, Unknown.</p>
</td>
</tr>
<tr id="row22407645"><td class="cellrowborder" valign="top" width="20.407959204079592%" headers="mcps1.2.5.1.1 "><p id="p3079941"><a name="p3079941"></a><a name="p3079941"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.5.1.2 "><p id="p48148645"><a name="p48148645"></a><a name="p48148645"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="23.46765323467653%" headers="mcps1.2.5.1.3 "><p id="p7726182"><a name="p7726182"></a><a name="p7726182"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p21841007"><a name="p21841007"></a><a name="p21841007"></a>Type of job condition, Complete or Failed.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
    "apiVersion": "batch/v1",
    "kind": "Job",
    "metadata": {
        "labels": {
            "name": "job-test"
        },
        "name": "job-test"
    },
    "spec": {
        "template": {
            "metadata": {
                "labels": {
                    "name": "job-test"
                },
                "name": "job-test"
            },
            "spec": {
                "containers": [
                    {
                        "image": "172.16.5.235:20202/test/nginx",
                        "name": "job-test"
                    }
                ],
                "imagePullSecrets": [{
                    "name": "default-secret"
                }],
                "restartPolicy": "Never"
            }
        }
    }
}
```

## 响应消息<a name="section18948451"></a>

**响应参数：**

响应参数的详细描述请参见[表2](#table8040885)。

**响应示例：**

```
{
    "kind": "Job",
    "apiVersion": "batch/v1",
    "metadata": {
        "name": "job-test",
        "namespace": "default",
        "selfLink": "/apis/batch/v1/namespaces/default/jobs/job-test",
        "uid": "45444e9b-fc20-11e7-9c3c-fa163eb8ad1a",
        "resourceVersion": "486000",
        "creationTimestamp": "2018-01-18T07:21:58Z",
        "labels": {
            "name": "job-test"
        },
        "enable": true
    },
    "spec": {
        "parallelism": 1,
        "completions": 1,
        "selector": {
            "matchLabels": {
                "controller-uid": "45444e9b-fc20-11e7-9c3c-fa163eb8ad1a"
            }
        },
        "template": {
            "metadata": {
                "name": "job-test",
                "creationTimestamp": null,
                "labels": {
                    "controller-uid": "45444e9b-fc20-11e7-9c3c-fa163eb8ad1a",
                    "job-name": "job-test",
                    "name": "job-test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "job-test",
                        "image": "172.16.5.235:20202/test/nginx",
                        "resources": {},
                        "terminationMessagePath": "/dev/termination-log",
                        "terminationMessagePolicy": "File",
                        "imagePullPolicy": "Always"
                    }
                ],
                "restartPolicy": "Never",
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
        }
    },
    "status": {}
}
```

## 状态码<a name="section36318335"></a>

[表9](#table30003806)描述API的状态码。

**表 9**  状态码

<a name="table30003806"></a>
<table><thead align="left"><tr id="row20731931"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p1564889"><a name="p1564889"></a><a name="p1564889"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p59647195"><a name="p59647195"></a><a name="p59647195"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row66693514"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p33465549"><a name="p33465549"></a><a name="p33465549"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p26354957"><a name="p26354957"></a><a name="p26354957"></a>The request has been fulfilled, resulting in the creation of a new resource.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

