# 创建Endpoints<a name="cce_02_0059"></a>

## 功能介绍<a name="s4743dec6326d484385d24d33a722ecf0"></a>

该API用于创建一个Endpoints资源对象。

## URI<a name="s236613da374043a585acfb8324569e98"></a>

POST /api/v1/namespaces/\{namespace\}/endpoints

[表1](#zh-cn_topic_0079614955_table38374806)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614955_table38374806"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614955_row39471735"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614955_p43093956"><a name="zh-cn_topic_0079614955_p43093956"></a><a name="zh-cn_topic_0079614955_p43093956"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p4291370921252"><a name="p4291370921252"></a><a name="p4291370921252"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p5345843021252"><a name="p5345843021252"></a><a name="p5345843021252"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614955_row55848701"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614955_p27450972"><a name="zh-cn_topic_0079614955_p27450972"></a><a name="zh-cn_topic_0079614955_p27450972"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614955_p8936292"><a name="zh-cn_topic_0079614955_p8936292"></a><a name="zh-cn_topic_0079614955_p8936292"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614955_p52751036"><a name="zh-cn_topic_0079614955_p52751036"></a><a name="zh-cn_topic_0079614955_p52751036"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row4997277"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614955_p2126321"><a name="zh-cn_topic_0079614955_p2126321"></a><a name="zh-cn_topic_0079614955_p2126321"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614955_p38014313"><a name="zh-cn_topic_0079614955_p38014313"></a><a name="zh-cn_topic_0079614955_p38014313"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614955_p59260526"><a name="zh-cn_topic_0079614955_p59260526"></a><a name="zh-cn_topic_0079614955_p59260526"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="zh-cn_topic_0079614955_ref458690767"></a>

请求参数：

请求参数如[表2](#zh-cn_topic_0079614955_ref458759912)所示。

**表 2**  参数描述

<a name="zh-cn_topic_0079614955_ref458759912"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614955_row59140623"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614955_p25661150"><a name="zh-cn_topic_0079614955_p25661150"></a><a name="zh-cn_topic_0079614955_p25661150"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p2502403321252"><a name="p2502403321252"></a><a name="p2502403321252"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p1368077221252"><a name="p1368077221252"></a><a name="p1368077221252"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p3440071921252"><a name="p3440071921252"></a><a name="p3440071921252"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614955_row55864401"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p28722627"><a name="zh-cn_topic_0079614955_p28722627"></a><a name="zh-cn_topic_0079614955_p28722627"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p44831437"><a name="zh-cn_topic_0079614955_p44831437"></a><a name="zh-cn_topic_0079614955_p44831437"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p7467800"><a name="zh-cn_topic_0079614955_p7467800"></a><a name="zh-cn_topic_0079614955_p7467800"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p912076"><a name="zh-cn_topic_0079614955_p912076"></a><a name="zh-cn_topic_0079614955_p912076"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="zh-cn_topic_0079614955_p8208684"><a name="zh-cn_topic_0079614955_p8208684"></a><a name="zh-cn_topic_0079614955_p8208684"></a>The value of this parameter is <strong id="zh-cn_topic_0079614955_b6769295"><a name="zh-cn_topic_0079614955_b6769295"></a><a name="zh-cn_topic_0079614955_b6769295"></a>Endpoints</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row60923663"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p35869679"><a name="zh-cn_topic_0079614955_p35869679"></a><a name="zh-cn_topic_0079614955_p35869679"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p19762867"><a name="zh-cn_topic_0079614955_p19762867"></a><a name="zh-cn_topic_0079614955_p19762867"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p57288388"><a name="zh-cn_topic_0079614955_p57288388"></a><a name="zh-cn_topic_0079614955_p57288388"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p9847817"><a name="zh-cn_topic_0079614955_p9847817"></a><a name="zh-cn_topic_0079614955_p9847817"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="zh-cn_topic_0079614955_p21521490"><a name="zh-cn_topic_0079614955_p21521490"></a><a name="zh-cn_topic_0079614955_p21521490"></a>The value of this parameter is <strong id="zh-cn_topic_0079614955_b59475690"><a name="zh-cn_topic_0079614955_b59475690"></a><a name="zh-cn_topic_0079614955_b59475690"></a>v1</strong>.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row65519169"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p5452505"><a name="zh-cn_topic_0079614955_p5452505"></a><a name="zh-cn_topic_0079614955_p5452505"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p38999745"><a name="zh-cn_topic_0079614955_p38999745"></a><a name="zh-cn_topic_0079614955_p38999745"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a9f7829944cb7499095d6f6c87771205f"><a name="a9f7829944cb7499095d6f6c87771205f"></a><a name="a9f7829944cb7499095d6f6c87771205f"></a><a href="公共请求参数.md#zh-cn_topic_0079614925_table47756489">表11</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p58338722"><a name="zh-cn_topic_0079614955_p58338722"></a><a name="zh-cn_topic_0079614955_p58338722"></a>-</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row55286454"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p49017803"><a name="zh-cn_topic_0079614955_p49017803"></a><a name="zh-cn_topic_0079614955_p49017803"></a>subsets</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p11019092"><a name="zh-cn_topic_0079614955_p11019092"></a><a name="zh-cn_topic_0079614955_p11019092"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a70ceaed44bfe4d5386b09a6aa0598138"><a name="a70ceaed44bfe4d5386b09a6aa0598138"></a><a name="a70ceaed44bfe4d5386b09a6aa0598138"></a><a href="#zh-cn_topic_0079614955_table9828942">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p20019172"><a name="zh-cn_topic_0079614955_p20019172"></a><a name="zh-cn_topic_0079614955_p20019172"></a>The set of all endpoints is the union of all subsets. Addresses are placed into subsets according to the IPs they share. A single address with multiple ports, some of which are ready and some of which are not (because they come from different containers) will result in the address being displayed in different subsets for the different ports. No address will appear in both Addresses and NotReadyAddresses in the same subset. Sets of addresses and ports that comprise a service.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  subsets字段数据结构说明

<a name="zh-cn_topic_0079614955_table9828942"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614955_row38322367"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614955_p17103984"><a name="zh-cn_topic_0079614955_p17103984"></a><a name="zh-cn_topic_0079614955_p17103984"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p5958596121252"><a name="p5958596121252"></a><a name="p5958596121252"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p6173357121252"><a name="p6173357121252"></a><a name="p6173357121252"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p3436338221252"><a name="p3436338221252"></a><a name="p3436338221252"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614955_row39619499"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p55062814"><a name="zh-cn_topic_0079614955_p55062814"></a><a name="zh-cn_topic_0079614955_p55062814"></a>addresses</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p30902987"><a name="zh-cn_topic_0079614955_p30902987"></a><a name="zh-cn_topic_0079614955_p30902987"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a6b3970fd76624efab415cf6763a93523"><a name="a6b3970fd76624efab415cf6763a93523"></a><a name="a6b3970fd76624efab415cf6763a93523"></a><a href="#zh-cn_topic_0079614955_table21351620">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p18621933"><a name="zh-cn_topic_0079614955_p18621933"></a><a name="zh-cn_topic_0079614955_p18621933"></a>IP addresses which offer the related ports that are marked as ready. These endpoints should be considered safe for load balancers and clients to utilize.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row33379675"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p19399120"><a name="zh-cn_topic_0079614955_p19399120"></a><a name="zh-cn_topic_0079614955_p19399120"></a>notReadyAddresses</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p27824865"><a name="zh-cn_topic_0079614955_p27824865"></a><a name="zh-cn_topic_0079614955_p27824865"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a68c1195d05b945c4b02599aec95682e0"><a name="a68c1195d05b945c4b02599aec95682e0"></a><a name="a68c1195d05b945c4b02599aec95682e0"></a><a href="#zh-cn_topic_0079614955_table21351620">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p22834938"><a name="zh-cn_topic_0079614955_p22834938"></a><a name="zh-cn_topic_0079614955_p22834938"></a>IP addresses which offer the related ports but are not currently marked as ready because they have not yet finished starting, have recently failed a readiness check, or have recently failed a liveness check.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row4187856"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p3672032"><a name="zh-cn_topic_0079614955_p3672032"></a><a name="zh-cn_topic_0079614955_p3672032"></a>ports</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p28999185"><a name="zh-cn_topic_0079614955_p28999185"></a><a name="zh-cn_topic_0079614955_p28999185"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a26c6fe496154497eb38ba89f858d1b97"><a name="a26c6fe496154497eb38ba89f858d1b97"></a><a name="a26c6fe496154497eb38ba89f858d1b97"></a><a href="#zh-cn_topic_0079614955_table57946857">表5</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p10026740"><a name="zh-cn_topic_0079614955_p10026740"></a><a name="zh-cn_topic_0079614955_p10026740"></a>Port numbers available on the related IP addresses.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  addresses字段数据结构说明

<a name="zh-cn_topic_0079614955_table21351620"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614955_row52426669"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614955_p18701764"><a name="zh-cn_topic_0079614955_p18701764"></a><a name="zh-cn_topic_0079614955_p18701764"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p3545388921252"><a name="p3545388921252"></a><a name="p3545388921252"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p5319277521252"><a name="p5319277521252"></a><a name="p5319277521252"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p1364752521252"><a name="p1364752521252"></a><a name="p1364752521252"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614955_row39998624"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p18663102"><a name="zh-cn_topic_0079614955_p18663102"></a><a name="zh-cn_topic_0079614955_p18663102"></a>ip</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p35316297"><a name="zh-cn_topic_0079614955_p35316297"></a><a name="zh-cn_topic_0079614955_p35316297"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p42047784"><a name="zh-cn_topic_0079614955_p42047784"></a><a name="zh-cn_topic_0079614955_p42047784"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p50427332"><a name="zh-cn_topic_0079614955_p50427332"></a><a name="zh-cn_topic_0079614955_p50427332"></a>The IP of this endpoint.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row51192804"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p52976421"><a name="zh-cn_topic_0079614955_p52976421"></a><a name="zh-cn_topic_0079614955_p52976421"></a>targetRef</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p63231703"><a name="zh-cn_topic_0079614955_p63231703"></a><a name="zh-cn_topic_0079614955_p63231703"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p21494305"><a name="zh-cn_topic_0079614955_p21494305"></a><a name="zh-cn_topic_0079614955_p21494305"></a><a href="#zh-cn_topic_0079614955_table51759670">表6</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p63317164"><a name="zh-cn_topic_0079614955_p63317164"></a><a name="zh-cn_topic_0079614955_p63317164"></a>-</p>
</td>
</tr>
<tr id="r4d8f7ae9a6da49eb9f18c6c06c4aec07"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="a71aaf7c7c84d46bdad88b83a33f929d2"><a name="a71aaf7c7c84d46bdad88b83a33f929d2"></a><a name="a71aaf7c7c84d46bdad88b83a33f929d2"></a>hostname</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p19565237482"><a name="zh-cn_topic_0079614955_p19565237482"></a><a name="zh-cn_topic_0079614955_p19565237482"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a7ad0d857ec4a4a41b591ac17dff62b87"><a name="a7ad0d857ec4a4a41b591ac17dff62b87"></a><a name="a7ad0d857ec4a4a41b591ac17dff62b87"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="adb1ff4d28c5843648d1a7acb2a02971b"><a name="adb1ff4d28c5843648d1a7acb2a02971b"></a><a name="adb1ff4d28c5843648d1a7acb2a02971b"></a>Hostname of this endpoint.eant to be used by DNS servers etc.</p>
</td>
</tr>
<tr id="r6223a7b8909b4420a46f1658dd8772be"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p339572313717"><a name="zh-cn_topic_0079614955_p339572313717"></a><a name="zh-cn_topic_0079614955_p339572313717"></a>nodeName</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="a7bb3e06cca354358bc199b4a8427fdbf"><a name="a7bb3e06cca354358bc199b4a8427fdbf"></a><a name="a7bb3e06cca354358bc199b4a8427fdbf"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a2a21dc5a796d4ac4a97d239e9fc47e3c"><a name="a2a21dc5a796d4ac4a97d239e9fc47e3c"></a><a name="a2a21dc5a796d4ac4a97d239e9fc47e3c"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p133953236377"><a name="zh-cn_topic_0079614955_p133953236377"></a><a name="zh-cn_topic_0079614955_p133953236377"></a>Optional: Node hosting this endpoint. This can be used to determine endpoints local to a node.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  ports字段数据结构说明

<a name="zh-cn_topic_0079614955_table57946857"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614955_row9471463"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614955_p28991032"><a name="zh-cn_topic_0079614955_p28991032"></a><a name="zh-cn_topic_0079614955_p28991032"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p6633662821252"><a name="p6633662821252"></a><a name="p6633662821252"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p455775121252"><a name="p455775121252"></a><a name="p455775121252"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p3363358821252"><a name="p3363358821252"></a><a name="p3363358821252"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614955_row18696727"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p38039934"><a name="zh-cn_topic_0079614955_p38039934"></a><a name="zh-cn_topic_0079614955_p38039934"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p61335842"><a name="zh-cn_topic_0079614955_p61335842"></a><a name="zh-cn_topic_0079614955_p61335842"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p2147306"><a name="zh-cn_topic_0079614955_p2147306"></a><a name="zh-cn_topic_0079614955_p2147306"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p39714111"><a name="zh-cn_topic_0079614955_p39714111"></a><a name="zh-cn_topic_0079614955_p39714111"></a>The name of this port (corresponds to ServicePort.Name). Must be a DNS_LABEL. Optional only if one port is defined.</p>
<p id="zh-cn_topic_0079614955_p21882681"><a name="zh-cn_topic_0079614955_p21882681"></a><a name="zh-cn_topic_0079614955_p21882681"></a>Value length: 0 character &lt; String length ≤ 63 characters.</p>
<p id="zh-cn_topic_0079614955_p62726408"><a name="zh-cn_topic_0079614955_p62726408"></a><a name="zh-cn_topic_0079614955_p62726408"></a>The string must comply with regular expression [a-z0-9]([-a-z0-9]*[a-z0-9])?.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row27666764"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p26415391"><a name="zh-cn_topic_0079614955_p26415391"></a><a name="zh-cn_topic_0079614955_p26415391"></a>port</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p59271898"><a name="zh-cn_topic_0079614955_p59271898"></a><a name="zh-cn_topic_0079614955_p59271898"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p36294438"><a name="zh-cn_topic_0079614955_p36294438"></a><a name="zh-cn_topic_0079614955_p36294438"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p54168362"><a name="zh-cn_topic_0079614955_p54168362"></a><a name="zh-cn_topic_0079614955_p54168362"></a>The port number of the endpoint.</p>
<p id="zh-cn_topic_0079614955_p17753217"><a name="zh-cn_topic_0079614955_p17753217"></a><a name="zh-cn_topic_0079614955_p17753217"></a>Value range: (0, 65535].</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row25561231"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p57193853"><a name="zh-cn_topic_0079614955_p57193853"></a><a name="zh-cn_topic_0079614955_p57193853"></a>protocol</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p2190491"><a name="zh-cn_topic_0079614955_p2190491"></a><a name="zh-cn_topic_0079614955_p2190491"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p43212049"><a name="zh-cn_topic_0079614955_p43212049"></a><a name="zh-cn_topic_0079614955_p43212049"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p10515080"><a name="zh-cn_topic_0079614955_p10515080"></a><a name="zh-cn_topic_0079614955_p10515080"></a>The IP protocol for this port.</p>
<p id="zh-cn_topic_0079614955_p27526859"><a name="zh-cn_topic_0079614955_p27526859"></a><a name="zh-cn_topic_0079614955_p27526859"></a>This parameter can be set to:</p>
<a name="zh-cn_topic_0079614955_ul46415143"></a><a name="zh-cn_topic_0079614955_ul46415143"></a><ul id="zh-cn_topic_0079614955_ul46415143"><li>TCP</li><li>UDP<p id="zh-cn_topic_0079614955_p13772373"><a name="zh-cn_topic_0079614955_p13772373"></a><a name="zh-cn_topic_0079614955_p13772373"></a>Default: TCP.</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

**表 6**  targetRef字段数据结构说明

<a name="zh-cn_topic_0079614955_table51759670"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614955_row4307190"><th class="cellrowborder" valign="top" width="21.8%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0079614955_p13338129"><a name="zh-cn_topic_0079614955_p13338129"></a><a name="zh-cn_topic_0079614955_p13338129"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.17%" id="mcps1.2.5.1.2"><p id="p500299721252"><a name="p500299721252"></a><a name="p500299721252"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p id="p258957321252"><a name="p258957321252"></a><a name="p258957321252"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.290000000000006%" id="mcps1.2.5.1.4"><p id="p842883321252"><a name="p842883321252"></a><a name="p842883321252"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614955_row41640866"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p17466967"><a name="zh-cn_topic_0079614955_p17466967"></a><a name="zh-cn_topic_0079614955_p17466967"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p5538237"><a name="zh-cn_topic_0079614955_p5538237"></a><a name="zh-cn_topic_0079614955_p5538237"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p45944059"><a name="zh-cn_topic_0079614955_p45944059"></a><a name="zh-cn_topic_0079614955_p45944059"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p30481338"><a name="zh-cn_topic_0079614955_p30481338"></a><a name="zh-cn_topic_0079614955_p30481338"></a>Phase is the current lifecycle phase of the namespace.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row5896594"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p7862068"><a name="zh-cn_topic_0079614955_p7862068"></a><a name="zh-cn_topic_0079614955_p7862068"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p32847787"><a name="zh-cn_topic_0079614955_p32847787"></a><a name="zh-cn_topic_0079614955_p32847787"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p43425119"><a name="zh-cn_topic_0079614955_p43425119"></a><a name="zh-cn_topic_0079614955_p43425119"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p27773751"><a name="zh-cn_topic_0079614955_p27773751"></a><a name="zh-cn_topic_0079614955_p27773751"></a>Namespace of the referent.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row48637172"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p47296894"><a name="zh-cn_topic_0079614955_p47296894"></a><a name="zh-cn_topic_0079614955_p47296894"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p5843233"><a name="zh-cn_topic_0079614955_p5843233"></a><a name="zh-cn_topic_0079614955_p5843233"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p3539844"><a name="zh-cn_topic_0079614955_p3539844"></a><a name="zh-cn_topic_0079614955_p3539844"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p18291919"><a name="zh-cn_topic_0079614955_p18291919"></a><a name="zh-cn_topic_0079614955_p18291919"></a>Name of the referent.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row30409547"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p47254279"><a name="zh-cn_topic_0079614955_p47254279"></a><a name="zh-cn_topic_0079614955_p47254279"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p2391358"><a name="zh-cn_topic_0079614955_p2391358"></a><a name="zh-cn_topic_0079614955_p2391358"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p59482330"><a name="zh-cn_topic_0079614955_p59482330"></a><a name="zh-cn_topic_0079614955_p59482330"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p53339459"><a name="zh-cn_topic_0079614955_p53339459"></a><a name="zh-cn_topic_0079614955_p53339459"></a>UID of the referent.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row10293088"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p28433766"><a name="zh-cn_topic_0079614955_p28433766"></a><a name="zh-cn_topic_0079614955_p28433766"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p21433709"><a name="zh-cn_topic_0079614955_p21433709"></a><a name="zh-cn_topic_0079614955_p21433709"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p58408860"><a name="zh-cn_topic_0079614955_p58408860"></a><a name="zh-cn_topic_0079614955_p58408860"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p33497244"><a name="zh-cn_topic_0079614955_p33497244"></a><a name="zh-cn_topic_0079614955_p33497244"></a>API version of the referent.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row33039746"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p58973758"><a name="zh-cn_topic_0079614955_p58973758"></a><a name="zh-cn_topic_0079614955_p58973758"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p12145054"><a name="zh-cn_topic_0079614955_p12145054"></a><a name="zh-cn_topic_0079614955_p12145054"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p44225290"><a name="zh-cn_topic_0079614955_p44225290"></a><a name="zh-cn_topic_0079614955_p44225290"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p25478763"><a name="zh-cn_topic_0079614955_p25478763"></a><a name="zh-cn_topic_0079614955_p25478763"></a>Specific resourceVersion to which this reference is made, if any.</p>
<div class="note" id="zh-cn_topic_0079614955_note27982283"><a name="zh-cn_topic_0079614955_note27982283"></a><a name="zh-cn_topic_0079614955_note27982283"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0079614955_p50513961"><a name="zh-cn_topic_0079614955_p50513961"></a><a name="zh-cn_topic_0079614955_p50513961"></a>This parameter is automatically generated. Do not assign values to this parameter. Otherwise, the API fails to be called.</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0079614955_row51972470"><td class="cellrowborder" valign="top" width="21.8%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614955_p49020554"><a name="zh-cn_topic_0079614955_p49020554"></a><a name="zh-cn_topic_0079614955_p49020554"></a>fieldPath</p>
</td>
<td class="cellrowborder" valign="top" width="19.17%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0079614955_p11241901"><a name="zh-cn_topic_0079614955_p11241901"></a><a name="zh-cn_topic_0079614955_p11241901"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614955_p38178826"><a name="zh-cn_topic_0079614955_p38178826"></a><a name="zh-cn_topic_0079614955_p38178826"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.290000000000006%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614955_p5477191"><a name="zh-cn_topic_0079614955_p5477191"></a><a name="zh-cn_topic_0079614955_p5477191"></a>If referring to a piece of an object instead of an entire object, this string should contain a valid JSON/Go field access statement, such as desiredState.manifest.containers[2]. For example, if the object reference is to a container within a pod, this would take on a value like: "spec.containers{name}" (where "name" refers to the name of the container that triggered the event) or if no container name is specified "spec.containers[2]" (container with index 2 in this pod). This syntax is chosen only to have some well-defined way of referencing a part of an object.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{ 
   "kind": "Endpoints", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "cluster-test" 
   }, 
   "subsets": [ 
     { 
       "addresses": [ 
         { 
           "ip": "172.16.106.152" 
         } 
       ], 
       "ports": [ 
         { 
           "port": 1 
         } 
       ] 
     }, 
     { 
       "addresses": [ 
         { 
           "ip": "172.16.79.157" 
         } 
       ], 
       "ports": [ 
         { 
           "port": 1 
         } 
       ] 
     } 
   ] 
 }
```

## 响应消息<a name="s34ea2b204bdc4a7cb419d86e3acc4bcd"></a>

**响应参数：**

响应参数的详细描述请参见[请求消息](#zh-cn_topic_0079614955_ref458690767)。

**响应示例：**

```
{ 
   "kind": "Endpoints", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "cluster-test", 
     "namespace": "default", 
     "selfLink": "/api/v1/namespaces/default/endpoints/cluster-test", 
     "uid": "81b1503d-5960-11e6-b444-286ed488fafe", 
     "resourceVersion": "18186", 
     "creationTimestamp": "2016-08-03T09:56:10Z" 
   }, 
   "subsets": [ 
     { 
       "addresses": [ 
         { 
           "ip": "172.16.106.152" 
         }, 
         { 
           "ip": "172.16.79.157" 
         } 
       ], 
       "ports": [ 
         { 
           "port": 1, 
           "protocol": "TCP" 
         } 
       ] 
     } 
   ] 
 }
```

## 状态码<a name="s9408111be52d43649a461e0c20204dc3"></a>

[表7](#zh-cn_topic_0079614955_table63183853)描述API的状态码。

**表 7**  状态码

<a name="zh-cn_topic_0079614955_table63183853"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614955_row33779294"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p310219521252"><a name="p310219521252"></a><a name="p310219521252"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p4995125221252"><a name="p4995125221252"></a><a name="p4995125221252"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614955_row14044750"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614955_p63882937"><a name="zh-cn_topic_0079614955_p63882937"></a><a name="zh-cn_topic_0079614955_p63882937"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614955_p7135413"><a name="zh-cn_topic_0079614955_p7135413"></a><a name="zh-cn_topic_0079614955_p7135413"></a>This operation succeeds, and an Endpoint resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

