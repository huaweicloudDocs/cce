# virtual-kubelet<a name="cce_02_0367"></a>

## 插件介绍<a name="section5841216112318"></a>

Virtual Kubelet是基于社区Virtual Kubelet开源项目开发的插件，该插件支持用户在短时高负载场景下，将部署在CCE上的无状态负载（Deployment）、有状态负载（StatefulSet）、普通任务（Job）三种资源类型的容器实例（Pod），弹性创建到华为云云容器实例CCI服务上，以减少集群扩容带来的消耗。详情请参见[virtual kubelet](https://support.huaweicloud.com/usermanual-cce/cce_01_0135.html)。

## 字段说明<a name="section13564204912269"></a>

**表 1**  参数描述

<a name="table7237514152812"></a>
<table><thead align="left"><tr id="row152371514142818"><th class="cellrowborder" valign="top" width="16.650000000000002%" id="mcps1.2.5.1.1"><p id="p8237101412810"><a name="p8237101412810"></a><a name="p8237101412810"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.61%" id="mcps1.2.5.1.2"><p id="p4237131416284"><a name="p4237131416284"></a><a name="p4237131416284"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.919999999999998%" id="mcps1.2.5.1.3"><p id="p15237171413287"><a name="p15237171413287"></a><a name="p15237171413287"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.82%" id="mcps1.2.5.1.4"><p id="p1237171432815"><a name="p1237171432815"></a><a name="p1237171432815"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row4237101416283"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p3237141418281"><a name="p3237141418281"></a><a name="p3237141418281"></a>basic</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p723710140287"><a name="p723710140287"></a><a name="p723710140287"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p1237111472817"><a name="p1237111472817"></a><a name="p1237111472817"></a><a href="#table11218194183015">表2</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p1723741413286"><a name="p1723741413286"></a><a name="p1723741413286"></a>插件基础配置参数</p>
</td>
</tr>
<tr id="row112371214112815"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p12237814102816"><a name="p12237814102816"></a><a name="p12237814102816"></a>flavor</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p162375146285"><a name="p162375146285"></a><a name="p162375146285"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p523731410289"><a name="p523731410289"></a><a name="p523731410289"></a><a href="#table8149147344">表3</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p423721402811"><a name="p423721402811"></a><a name="p423721402811"></a>插件规格参数</p>
</td>
</tr>
<tr id="row5237914182816"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p112371214132813"><a name="p112371214132813"></a><a name="p112371214132813"></a>custom</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p192371914182813"><a name="p192371914182813"></a><a name="p192371914182813"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p4237181416289"><a name="p4237181416289"></a><a name="p4237181416289"></a><a href="#table109631116113412">表4</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p02371514192810"><a name="p02371514192810"></a><a name="p02371514192810"></a>插件自定义参数</p>
</td>
</tr>
</tbody>
</table>

**表 2**  basic

<a name="table11218194183015"></a>
<table><thead align="left"><tr id="row1221864193016"><th class="cellrowborder" valign="top" width="16.650000000000002%" id="mcps1.2.5.1.1"><p id="p021815414303"><a name="p021815414303"></a><a name="p021815414303"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.61%" id="mcps1.2.5.1.2"><p id="p14218104111302"><a name="p14218104111302"></a><a name="p14218104111302"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.919999999999998%" id="mcps1.2.5.1.3"><p id="p172181641143010"><a name="p172181641143010"></a><a name="p172181641143010"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.82%" id="mcps1.2.5.1.4"><p id="p132182418307"><a name="p132182418307"></a><a name="p132182418307"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row721834183010"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p1051955711340"><a name="p1051955711340"></a><a name="p1051955711340"></a>available_zone</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p6218144113307"><a name="p6218144113307"></a><a name="p6218144113307"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p1221814114306"><a name="p1221814114306"></a><a name="p1221814114306"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p83871449134211"><a name="p83871449134211"></a><a name="p83871449134211"></a>插件所在可用区。</p>
<p id="p2218441193019"><a name="p2218441193019"></a><a name="p2218441193019"></a>如：cn-north-4a</p>
</td>
</tr>
<tr id="row132182413304"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p1518257163419"><a name="p1518257163419"></a><a name="p1518257163419"></a>cci_address</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p72181041173011"><a name="p72181041173011"></a><a name="p72181041173011"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p667313816185"><a name="p667313816185"></a><a name="p667313816185"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p1341210535421"><a name="p1341210535421"></a><a name="p1341210535421"></a>CCI的访问地址和端口。</p>
<p id="p11218141103019"><a name="p11218141103019"></a><a name="p11218141103019"></a>如：https://cci.cn-north-4.myhuaweicloud.com:443</p>
</td>
</tr>
<tr id="row4219154133018"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p15181357143412"><a name="p15181357143412"></a><a name="p15181357143412"></a>euleros_version</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p5795143511715"><a name="p5795143511715"></a><a name="p5795143511715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p3673193810189"><a name="p3673193810189"></a><a name="p3673193810189"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p72191741103019"><a name="p72191741103019"></a><a name="p72191741103019"></a>欧拉OS的版本，固定为：2.2.5</p>
</td>
</tr>
<tr id="row8337536143615"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p183378368364"><a name="p183378368364"></a><a name="p183378368364"></a>iam_address</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p179553518172"><a name="p179553518172"></a><a name="p179553518172"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p767333813180"><a name="p767333813180"></a><a name="p767333813180"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p78625572420"><a name="p78625572420"></a><a name="p78625572420"></a>IAM的访问地址和端口。</p>
<p id="p7337636133617"><a name="p7337636133617"></a><a name="p7337636133617"></a>如：https://iam.cn-north-4.myhuaweicloud.com:443</p>
</td>
</tr>
<tr id="row16337193613367"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p1533753619362"><a name="p1533753619362"></a><a name="p1533753619362"></a>swr_addr</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p103121647161715"><a name="p103121647161715"></a><a name="p103121647161715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p20673338201819"><a name="p20673338201819"></a><a name="p20673338201819"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p1821115154318"><a name="p1821115154318"></a><a name="p1821115154318"></a>SWR的访问地址。</p>
<p id="p0337133614369"><a name="p0337133614369"></a><a name="p0337133614369"></a>如：swr.cn-north-4.myhuaweicloud.com</p>
</td>
</tr>
<tr id="row15337143613611"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p1033883615361"><a name="p1033883615361"></a><a name="p1033883615361"></a>swr_user</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p231224718179"><a name="p231224718179"></a><a name="p231224718179"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p18674123891811"><a name="p18674123891811"></a><a name="p18674123891811"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p7338123663611"><a name="p7338123663611"></a><a name="p7338123663611"></a>SWR的用户名，官方插件默认为：hwofficial</p>
</td>
</tr>
<tr id="row9169194233616"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p11169104293616"><a name="p11169104293616"></a><a name="p11169104293616"></a>rbac_enabled</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p1631264710177"><a name="p1631264710177"></a><a name="p1631264710177"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p7674838181820"><a name="p7674838181820"></a><a name="p7674838181820"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p62951872445"><a name="p62951872445"></a><a name="p62951872445"></a>是否支持RBAC，支持则值为：true</p>
</td>
</tr>
<tr id="row131692042173619"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p7169194233618"><a name="p7169194233618"></a><a name="p7169194233618"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p631244781718"><a name="p631244781718"></a><a name="p631244781718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p416954223616"><a name="p416954223616"></a><a name="p416954223616"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p916911420368"><a name="p916911420368"></a><a name="p916911420368"></a>集群ID</p>
</td>
</tr>
<tr id="row1916918429369"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p317064211363"><a name="p317064211363"></a><a name="p317064211363"></a>cluster_name</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p1170174217369"><a name="p1170174217369"></a><a name="p1170174217369"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p161705426365"><a name="p161705426365"></a><a name="p161705426365"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p7170204223610"><a name="p7170204223610"></a><a name="p7170204223610"></a>集群的名称</p>
</td>
</tr>
<tr id="row101700421360"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p161701842113615"><a name="p161701842113615"></a><a name="p161701842113615"></a>vpc_id</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p1136254991713"><a name="p1136254991713"></a><a name="p1136254991713"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p18170342123613"><a name="p18170342123613"></a><a name="p18170342123613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p18170184213615"><a name="p18170184213615"></a><a name="p18170184213615"></a>虚拟私有云ID</p>
</td>
</tr>
<tr id="row1217034253610"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p3170542173618"><a name="p3170542173618"></a><a name="p3170542173618"></a>network_id</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p536224916179"><a name="p536224916179"></a><a name="p536224916179"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p617012426365"><a name="p617012426365"></a><a name="p617012426365"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p1817014283613"><a name="p1817014283613"></a><a name="p1817014283613"></a>子网ID</p>
</td>
</tr>
<tr id="row51705425362"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p31708428365"><a name="p31708428365"></a><a name="p31708428365"></a>security_group_id</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p183621649101719"><a name="p183621649101719"></a><a name="p183621649101719"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p517064223614"><a name="p517064223614"></a><a name="p517064223614"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p4170342163614"><a name="p4170342163614"></a><a name="p4170342163614"></a>安全组ID</p>
</td>
</tr>
<tr id="row5688134103717"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p1568864117370"><a name="p1568864117370"></a><a name="p1568864117370"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p1836214916175"><a name="p1836214916175"></a><a name="p1836214916175"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p568824114374"><a name="p568824114374"></a><a name="p568824114374"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p6688184173713"><a name="p6688184173713"></a><a name="p6688184173713"></a>项目ID</p>
</td>
</tr>
<tr id="row068819411376"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p1668874112378"><a name="p1668874112378"></a><a name="p1668874112378"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p106881041183717"><a name="p106881041183717"></a><a name="p106881041183717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p126882411376"><a name="p126882411376"></a><a name="p126882411376"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p168884143715"><a name="p168884143715"></a><a name="p168884143715"></a>所在区域。</p>
<p id="p121191429164612"><a name="p121191429164612"></a><a name="p121191429164612"></a>如：cn-north-4</p>
</td>
</tr>
</tbody>
</table>

**表 3**  flavor

<a name="table8149147344"></a>
<table><thead align="left"><tr id="row2014214123415"><th class="cellrowborder" valign="top" width="16.650000000000002%" id="mcps1.2.5.1.1"><p id="p11141314163419"><a name="p11141314163419"></a><a name="p11141314163419"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.61%" id="mcps1.2.5.1.2"><p id="p1314121443418"><a name="p1314121443418"></a><a name="p1314121443418"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.919999999999998%" id="mcps1.2.5.1.3"><p id="p201412148342"><a name="p201412148342"></a><a name="p201412148342"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.82%" id="mcps1.2.5.1.4"><p id="p101414142344"><a name="p101414142344"></a><a name="p101414142344"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row121471493417"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p453114559345"><a name="p453114559345"></a><a name="p453114559345"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p614121423419"><a name="p614121423419"></a><a name="p614121423419"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p1114114143415"><a name="p1114114143415"></a><a name="p1114114143415"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p18144148344"><a name="p18144148344"></a><a name="p18144148344"></a>插件相关的描述信息</p>
</td>
</tr>
<tr id="row1614101463413"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p18530165511346"><a name="p18530165511346"></a><a name="p18530165511346"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p31451413342"><a name="p31451413342"></a><a name="p31451413342"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p20142143343"><a name="p20142143343"></a><a name="p20142143343"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p1314314143410"><a name="p1314314143410"></a><a name="p1314314143410"></a>插件规格名称，固定为：Single-instance</p>
</td>
</tr>
<tr id="row1514131419347"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p85051552340"><a name="p85051552340"></a><a name="p85051552340"></a>replicas</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p1014114183417"><a name="p1014114183417"></a><a name="p1014114183417"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p16141714163415"><a name="p16141714163415"></a><a name="p16141714163415"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p514714143416"><a name="p514714143416"></a><a name="p514714143416"></a>实例数，默认为：1</p>
</td>
</tr>
<tr id="row1320482115386"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p6204221103813"><a name="p6204221103813"></a><a name="p6204221103813"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p14204122123813"><a name="p14204122123813"></a><a name="p14204122123813"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p15204921153814"><a name="p15204921153814"></a><a name="p15204921153814"></a><a href="#table136520220346">resources</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p1520482113810"><a name="p1520482113810"></a><a name="p1520482113810"></a>容器资源（CPU、内存）配额。</p>
</td>
</tr>
</tbody>
</table>

**表 4**  custom

<a name="table109631116113412"></a>
<table><thead align="left"><tr id="row1696361663418"><th class="cellrowborder" valign="top" width="16.650000000000002%" id="mcps1.2.5.1.1"><p id="p79633167341"><a name="p79633167341"></a><a name="p79633167341"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.61%" id="mcps1.2.5.1.2"><p id="p139631416173412"><a name="p139631416173412"></a><a name="p139631416173412"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.919999999999998%" id="mcps1.2.5.1.3"><p id="p17963111616348"><a name="p17963111616348"></a><a name="p17963111616348"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.82%" id="mcps1.2.5.1.4"><p id="p1696351619347"><a name="p1696351619347"></a><a name="p1696351619347"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row196318165349"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p06393538345"><a name="p06393538345"></a><a name="p06393538345"></a>isInstallProxy</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p169631416103416"><a name="p169631416103416"></a><a name="p169631416103416"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p4963016153419"><a name="p4963016153419"></a><a name="p4963016153419"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p102057473559"><a name="p102057473559"></a><a name="p102057473559"></a>跨服务互通。</p>
<p id="p1396371683413"><a name="p1396371683413"></a><a name="p1396371683413"></a>true：支持CCE集群中的Pod与CCI集群中的Pod通过Kubernetes Service互通。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  resources字段数据结构说明

<a name="table136520220346"></a>
<table><thead align="left"><tr id="row665212223419"><th class="cellrowborder" valign="top" width="16.650000000000002%" id="mcps1.2.5.1.1"><p id="p206521822183413"><a name="p206521822183413"></a><a name="p206521822183413"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.61%" id="mcps1.2.5.1.2"><p id="p7652202219346"><a name="p7652202219346"></a><a name="p7652202219346"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.919999999999998%" id="mcps1.2.5.1.3"><p id="p465212233417"><a name="p465212233417"></a><a name="p465212233417"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.82%" id="mcps1.2.5.1.4"><p id="p12652132216348"><a name="p12652132216348"></a><a name="p12652132216348"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1965252203413"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p290761215395"><a name="p290761215395"></a><a name="p290761215395"></a>limitsCpu</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p165217221342"><a name="p165217221342"></a><a name="p165217221342"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p024818327510"><a name="p024818327510"></a><a name="p024818327510"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p950122712488"><a name="p950122712488"></a><a name="p950122712488"></a>CPU大小限制，单位：m</p>
<p id="p0653172211341"><a name="p0653172211341"></a><a name="p0653172211341"></a>默认为：250m</p>
</td>
</tr>
<tr id="row1265362211348"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p199071412173919"><a name="p199071412173919"></a><a name="p199071412173919"></a>limitsMem</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p965319224347"><a name="p965319224347"></a><a name="p965319224347"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p22481532185116"><a name="p22481532185116"></a><a name="p22481532185116"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p11653822173411"><a name="p11653822173411"></a><a name="p11653822173411"></a>内存大小限制，单位：Mi</p>
<p id="p79551335164810"><a name="p79551335164810"></a><a name="p79551335164810"></a>默认为：512Mi</p>
</td>
</tr>
<tr id="row16121539104016"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p126126399406"><a name="p126126399406"></a><a name="p126126399406"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p126121839134010"><a name="p126121839134010"></a><a name="p126121839134010"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p132481322511"><a name="p132481322511"></a><a name="p132481322511"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p3612139114012"><a name="p3612139114012"></a><a name="p3612139114012"></a>插件名称，固定为：virtual-kubelet</p>
</td>
</tr>
<tr id="row113481236124011"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p9348133617407"><a name="p9348133617407"></a><a name="p9348133617407"></a>requestsCpu</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p134893611405"><a name="p134893611405"></a><a name="p134893611405"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p192481532205113"><a name="p192481532205113"></a><a name="p192481532205113"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p3348153617405"><a name="p3348153617405"></a><a name="p3348153617405"></a>申请的CPU大小，单位：m</p>
<p id="p13838112224915"><a name="p13838112224915"></a><a name="p13838112224915"></a>默认为：250m</p>
</td>
</tr>
<tr id="row1665362213412"><td class="cellrowborder" valign="top" width="16.650000000000002%" headers="mcps1.2.5.1.1 "><p id="p129061012153914"><a name="p129061012153914"></a><a name="p129061012153914"></a>requestsMem</p>
</td>
<td class="cellrowborder" valign="top" width="17.61%" headers="mcps1.2.5.1.2 "><p id="p36531122163418"><a name="p36531122163418"></a><a name="p36531122163418"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p12248193210518"><a name="p12248193210518"></a><a name="p12248193210518"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="48.82%" headers="mcps1.2.5.1.4 "><p id="p565362293414"><a name="p565362293414"></a><a name="p565362293414"></a>申请的内存大小，单位：Mi</p>
<p id="p9797829115015"><a name="p9797829115015"></a><a name="p9797829115015"></a>默认为：512Mi</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section5790442114119"></a>

```
{
	"metadata": {
		"annotations": {
			"addon.install/type": "install"
		}
	},
	"spec": {
		"clusterID": "ccbe7bdf-4**9-3**b-b**4-0********78",
		"version": "1.0.3",
		"addonTemplateName": "virtual-kubelet",
		"values": {
			"basic": {
				"available_zone": "cn-north-4a",
				"cci_address": "https://cci.cn-north-4.myhuaweicloud.com:443",
				"euleros_version": "2.2.5",
				"iam_address": "https://iam.cn-north-4.myhuaweicloud.com:443",
				"swr_addr": "swr.cn-north-4.myhuaweicloud.com",
				"swr_user": "hwofficial",
				"rbac_enabled": true,
				"cluster_id": "ccbe7bdf-4**9-3**b-b**4-0********78",
				"cluster_name": "test-vk",
				"vpc_id": "2372199f-e6e0-48be-9437-e774aae6bd70",
				"network_id": "863a5e6c-e4f5-45f8-80d9-5090f17a767b",
				"security_group_id": "ac3c1a82-f320-495a-b81d-e7aaa6b304a4",
				"project_id": "085a4*********00a9ccf7fba",
				"region": "cn-north-4"
			},
			"flavor": {
				"description": "Redundancy backup is not available for the add-on.",
				"name": "Single-instance",
				"replicas": 1,
				"resources": [{
					"limitsCpu": "250m",
					"limitsMem": "512Mi",
					"name": "virtual-kubelet",
					"requestsCpu": "250m",
					"requestsMem": "512Mi"
				}]
			},
			"custom": {
				"isInstallProxy": true
			}
		}
	}
}
```

