# CCE权限说明<a name="cce_01_0187"></a>

CCE权限管理是在Kubernetes的角色访问控制（RBAC）与统一身份认证服务（IAM）的能力基础上，打造的细粒度权限管理功能，支持基于IAM的细粒度权限控制和IAM Token认证，支持集群级别、命名空间级别的权限控制，帮助用户便捷灵活的对租户下的IAM用户、用户组设定不同的操作权限。

CCE的权限管理包括“集群权限“和“命名空间权限“两种能力，能够从集群和命名空间层面对用户组或用户进行细粒度授权，具体解释如下：

-   **[集群权限](#section824312412013)：**是基于IAM系统策略的授权，可以通过用户组功能实现IAM用户的授权。用户组是用户的集合，通过集群权限设置可以让某些用户组操作集群（如创建、删除集群等），而让某些用户组仅能查看集群。
-   **[命名空间权限](#section944114820217)：**是基于Kubernetes RBAC能力的授权。通过权限设置可以让不同的用户或用户组拥有操作不同Kubernetes资源的权限。

**图 1**  CCE权限管理<a name="fig338584562419"></a>  
![](figures/CCE权限管理.png "CCE权限管理")

## 集群权限<a name="section824312412013"></a>

集群权限是基于IAM系统策略的授权，可以通过用户组功能实现IAM用户的授权，当前包含**CCE FullAccess**和**CCE ReadOnlyAccess**两种策略。

CCE FullAccess策略权限如下：

**表 1**  CCE FullAccess策略主要权限

<a name="table65762630"></a>
<table><thead align="left"><tr id="row64098000"><th class="cellrowborder" valign="top" width="20.4%" id="mcps1.2.4.1.1"><p id="p324219918470"><a name="p324219918470"></a><a name="p324219918470"></a>操作（Action）</p>
</th>
<th class="cellrowborder" valign="top" width="26.6%" id="mcps1.2.4.1.2"><p id="p181345334206"><a name="p181345334206"></a><a name="p181345334206"></a>Action详情</p>
</th>
<th class="cellrowborder" valign="top" width="53%" id="mcps1.2.4.1.3"><p id="p24555510"><a name="p24555510"></a><a name="p24555510"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row33671837142011"><td class="cellrowborder" rowspan="19" valign="top" width="20.4%" headers="mcps1.2.4.1.1 "><p id="p1224309164711"><a name="p1224309164711"></a><a name="p1224309164711"></a>cce:*:*</p>
</td>
<td class="cellrowborder" valign="top" width="26.6%" headers="mcps1.2.4.1.2 "><p id="p1676861712325"><a name="p1676861712325"></a><a name="p1676861712325"></a>cce:cluster:create</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p17681517143220"><a name="p17681517143220"></a><a name="p17681517143220"></a>创建集群</p>
</td>
</tr>
<tr id="row1136803716207"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p476951710329"><a name="p476951710329"></a><a name="p476951710329"></a>cce:cluster:delete</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p15769181710326"><a name="p15769181710326"></a><a name="p15769181710326"></a>删除集群</p>
</td>
</tr>
<tr id="row236893713200"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1876918172329"><a name="p1876918172329"></a><a name="p1876918172329"></a>cce:cluster:update</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p157698171326"><a name="p157698171326"></a><a name="p157698171326"></a>更新集群，如后续允许集群支持RBAC，调度参数更新等</p>
</td>
</tr>
<tr id="row14369237182014"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1876971713322"><a name="p1876971713322"></a><a name="p1876971713322"></a>cce:cluster:upgrade</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16770181763217"><a name="p16770181763217"></a><a name="p16770181763217"></a>升级集群</p>
</td>
</tr>
<tr id="row336911371201"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p20770131713323"><a name="p20770131713323"></a><a name="p20770131713323"></a>cce:cluster:start</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p97708172320"><a name="p97708172320"></a><a name="p97708172320"></a>唤醒集群</p>
</td>
</tr>
<tr id="row10369173792011"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6770111743216"><a name="p6770111743216"></a><a name="p6770111743216"></a>cce:cluster:stop</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p477121710323"><a name="p477121710323"></a><a name="p477121710323"></a>休眠集群</p>
</td>
</tr>
<tr id="row9371153720209"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p10772181753213"><a name="p10772181753213"></a><a name="p10772181753213"></a>cce:cluster:list</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p10772817153214"><a name="p10772817153214"></a><a name="p10772817153214"></a>查询集群列表</p>
</td>
</tr>
<tr id="row1337193719205"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1377251712329"><a name="p1377251712329"></a><a name="p1377251712329"></a>cce:cluster:get</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1877361717328"><a name="p1877361717328"></a><a name="p1877361717328"></a>查询集群详情</p>
</td>
</tr>
<tr id="row183721437152013"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p27731617163219"><a name="p27731617163219"></a><a name="p27731617163219"></a>cce:node:create</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p107738172328"><a name="p107738172328"></a><a name="p107738172328"></a>添加节点</p>
</td>
</tr>
<tr id="row1337223782012"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p20773017103210"><a name="p20773017103210"></a><a name="p20773017103210"></a>cce:node:delete</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p10774717183215"><a name="p10774717183215"></a><a name="p10774717183215"></a>删除节点/批量删除节点</p>
</td>
</tr>
<tr id="row537316378201"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1177471718323"><a name="p1177471718323"></a><a name="p1177471718323"></a>cce:node:update</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p187751317163218"><a name="p187751317163218"></a><a name="p187751317163218"></a>更新节点，如更新节点名称</p>
</td>
</tr>
<tr id="row9374137182017"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p077512178326"><a name="p077512178326"></a><a name="p077512178326"></a>cce:node:get</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2775131773214"><a name="p2775131773214"></a><a name="p2775131773214"></a>查询节点详情</p>
</td>
</tr>
<tr id="row95581429192015"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1777551743217"><a name="p1777551743217"></a><a name="p1777551743217"></a>cce:node:list</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p5775181718326"><a name="p5775181718326"></a><a name="p5775181718326"></a>查询节点列表</p>
</td>
</tr>
<tr id="row4559162992016"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p177641773220"><a name="p177641773220"></a><a name="p177641773220"></a>cce:job:list</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17776517113217"><a name="p17776517113217"></a><a name="p17776517113217"></a>查询任务列表（集群层面的job）</p>
</td>
</tr>
<tr id="row195591929132018"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1877691723215"><a name="p1877691723215"></a><a name="p1877691723215"></a>cce:job:delete</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2777817153217"><a name="p2777817153217"></a><a name="p2777817153217"></a>删除任务/批量删除任务（集群层面的job）</p>
</td>
</tr>
<tr id="row2056082962010"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p77771517193210"><a name="p77771517193210"></a><a name="p77771517193210"></a>cce:job:get</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p777718179327"><a name="p777718179327"></a><a name="p777718179327"></a>查询任务详情（集群层面的job）</p>
</td>
</tr>
<tr id="row176811342112812"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p568154232816"><a name="p568154232816"></a><a name="p568154232816"></a><span>cce:storage:create</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16681642142819"><a name="p16681642142819"></a><a name="p16681642142819"></a>创建存储</p>
</td>
</tr>
<tr id="row17431133642816"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6432636162813"><a name="p6432636162813"></a><a name="p6432636162813"></a><span>cce:storage:delete</span></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p9432133662812"><a name="p9432133662812"></a><a name="p9432133662812"></a>删除存储</p>
</td>
</tr>
<tr id="row1355001813192"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p13551111818196"><a name="p13551111818196"></a><a name="p13551111818196"></a>cce:kubernetes:*</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p19551121810199"><a name="p19551121810199"></a><a name="p19551121810199"></a>操作所有kubernetes资源，具体权限请在<a href="#section944114820217">命名空间权限</a>中配置。</p>
</td>
</tr>
<tr id="row7655154602020"><td class="cellrowborder" valign="top" width="20.4%" headers="mcps1.2.4.1.1 "><p id="p1592752614810"><a name="p1592752614810"></a><a name="p1592752614810"></a>ecs:*:*</p>
</td>
<td class="cellrowborder" valign="top" width="26.6%" headers="mcps1.2.4.1.2 "><p id="p52094246485"><a name="p52094246485"></a><a name="p52094246485"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p540810333219"><a name="p540810333219"></a><a name="p540810333219"></a>ECS（弹性云服务器）服务的所有权限。</p>
</td>
</tr>
<tr id="row13685854112019"><td class="cellrowborder" valign="top" width="20.4%" headers="mcps1.2.4.1.1 "><p id="p5243793476"><a name="p5243793476"></a><a name="p5243793476"></a>evs:*:*</p>
</td>
<td class="cellrowborder" valign="top" width="26.6%" headers="mcps1.2.4.1.2 "><p id="p1668516546206"><a name="p1668516546206"></a><a name="p1668516546206"></a>具体action详见：<a href="https://support.huaweicloud.com/api-evs/evs_04_0026.html" target="_blank" rel="noopener noreferrer">云硬盘v2接口的授权信息</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p5545230133217"><a name="p5545230133217"></a><a name="p5545230133217"></a>EVS（云硬盘）的所有权限。</p>
<p id="p1666335113594"><a name="p1666335113594"></a><a name="p1666335113594"></a>可以将云硬盘挂载到云服务器，并可以随时扩容云硬盘容量</p>
</td>
</tr>
<tr id="row1222410528205"><td class="cellrowborder" valign="top" width="20.4%" headers="mcps1.2.4.1.1 "><p id="p7243119174718"><a name="p7243119174718"></a><a name="p7243119174718"></a>vpc:*:*</p>
</td>
<td class="cellrowborder" valign="top" width="26.6%" headers="mcps1.2.4.1.2 "><p id="p48939132447"><a name="p48939132447"></a><a name="p48939132447"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p112083121013"><a name="p112083121013"></a><a name="p112083121013"></a>VPC（虚拟私有云，包含二代ELB）的所有权限。</p>
<p id="p8937625175814"><a name="p8937625175814"></a><a name="p8937625175814"></a>创建的集群需要运行在虚拟私有云中，创建命名空间时，需要创建或关联VPC，创建在命名空间的容器都运行在VPC之内。</p>
</td>
</tr>
<tr id="row11629359101313"><td class="cellrowborder" valign="top" width="20.4%" headers="mcps1.2.4.1.1 "><p id="p1624315964717"><a name="p1624315964717"></a><a name="p1624315964717"></a>sfs:*:get*</p>
</td>
<td class="cellrowborder" valign="top" width="26.6%" headers="mcps1.2.4.1.2 "><p id="p17630135981318"><a name="p17630135981318"></a><a name="p17630135981318"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p16630659191317"><a name="p16630659191317"></a><a name="p16630659191317"></a>SFS（弹性文件服务）资源详情的查看权限。</p>
</td>
</tr>
<tr id="row630418590147"><td class="cellrowborder" valign="top" width="20.4%" headers="mcps1.2.4.1.1 "><p id="p14243598475"><a name="p14243598475"></a><a name="p14243598475"></a>aom:*:get</p>
</td>
<td class="cellrowborder" valign="top" width="26.6%" headers="mcps1.2.4.1.2 "><p id="p630419599143"><a name="p630419599143"></a><a name="p630419599143"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p630475941416"><a name="p630475941416"></a><a name="p630475941416"></a>AOM（应用运维管理）资源详情的查看权限。</p>
</td>
</tr>
<tr id="row1767414251516"><td class="cellrowborder" valign="top" width="20.4%" headers="mcps1.2.4.1.1 "><p id="p6244119134714"><a name="p6244119134714"></a><a name="p6244119134714"></a>aom:*:list</p>
</td>
<td class="cellrowborder" valign="top" width="26.6%" headers="mcps1.2.4.1.2 "><p id="p26757261518"><a name="p26757261518"></a><a name="p26757261518"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p116753241514"><a name="p116753241514"></a><a name="p116753241514"></a>AOM（应用运维管理）资源列表的查看权限。</p>
</td>
</tr>
<tr id="row873810362151"><td class="cellrowborder" valign="top" width="20.4%" headers="mcps1.2.4.1.1 "><p id="p182440912479"><a name="p182440912479"></a><a name="p182440912479"></a>aom:autoScalingRule:*</p>
</td>
<td class="cellrowborder" valign="top" width="26.6%" headers="mcps1.2.4.1.2 "><p id="p177391236101516"><a name="p177391236101516"></a><a name="p177391236101516"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p2739836171516"><a name="p2739836171516"></a><a name="p2739836171516"></a>AOM（应用运维管理）自动扩缩容规则的所有操作权限。</p>
</td>
</tr>
</tbody>
</table>

CCE ReadOnlyAccess策略权限如下：

**表 2**  CCE ReadOnlyAccess策略主要权限

<a name="table11562191511348"></a>
<table><thead align="left"><tr id="row156351513348"><th class="cellrowborder" valign="top" width="19.97%" id="mcps1.2.4.1.1"><p id="p19661557182112"><a name="p19661557182112"></a><a name="p19661557182112"></a>操作（Action）</p>
</th>
<th class="cellrowborder" valign="top" width="27.029999999999998%" id="mcps1.2.4.1.2"><p id="p3563121543416"><a name="p3563121543416"></a><a name="p3563121543416"></a>操作（Action）</p>
</th>
<th class="cellrowborder" valign="top" width="53%" id="mcps1.2.4.1.3"><p id="p16563171517347"><a name="p16563171517347"></a><a name="p16563171517347"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row20566115103417"><td class="cellrowborder" rowspan="3" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p2966115711217"><a name="p2966115711217"></a><a name="p2966115711217"></a>cce:*:get</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p13566141543417"><a name="p13566141543417"></a><a name="p13566141543417"></a>cce:cluster:get</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p1356651553417"><a name="p1356651553417"></a><a name="p1356651553417"></a>查询集群详情</p>
</td>
</tr>
<tr id="row1356613154348"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1756601513346"><a name="p1756601513346"></a><a name="p1756601513346"></a>cce:node:get</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p956719151343"><a name="p956719151343"></a><a name="p956719151343"></a>查询节点详情</p>
</td>
</tr>
<tr id="row5568101519341"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p16568111523419"><a name="p16568111523419"></a><a name="p16568111523419"></a>cce:job:get</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p55681415203415"><a name="p55681415203415"></a><a name="p55681415203415"></a>查询任务详情（集群层面的job）</p>
</td>
</tr>
<tr id="row155691015153414"><td class="cellrowborder" rowspan="3" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p79669573215"><a name="p79669573215"></a><a name="p79669573215"></a>cce:*:list</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p135694150342"><a name="p135694150342"></a><a name="p135694150342"></a>cce:cluster:list</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p75691115123419"><a name="p75691115123419"></a><a name="p75691115123419"></a>查询集群列表</p>
</td>
</tr>
<tr id="row95691715183418"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p556931517348"><a name="p556931517348"></a><a name="p556931517348"></a>cce:node:list</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1256915155349"><a name="p1256915155349"></a><a name="p1256915155349"></a>查询节点列表</p>
</td>
</tr>
<tr id="row65691715113412"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p17569131533419"><a name="p17569131533419"></a><a name="p17569131533419"></a>cce:job:list</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p456915157347"><a name="p456915157347"></a><a name="p456915157347"></a>查询任务列表（集群层面的job）</p>
</td>
</tr>
<tr id="row170241171817"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p159661457192112"><a name="p159661457192112"></a><a name="p159661457192112"></a>cce:kubernetes:*</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p77016415184"><a name="p77016415184"></a><a name="p77016415184"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p18702412180"><a name="p18702412180"></a><a name="p18702412180"></a>操作所有kubernetes资源，具体权限请在<a href="#section944114820217">命名空间权限</a>中配置。</p>
</td>
</tr>
<tr id="row1557101593414"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p15966145792119"><a name="p15966145792119"></a><a name="p15966145792119"></a>ecs:*:get</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p1457113151345"><a name="p1457113151345"></a><a name="p1457113151345"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p1357112152343"><a name="p1357112152343"></a><a name="p1357112152343"></a>ECS（弹性云服务器）所有资源详情的查看权限。</p>
<p id="p957215152348"><a name="p957215152348"></a><a name="p957215152348"></a>CCE中的一个节点就是具有多个云硬盘的一台弹性云服务器</p>
</td>
</tr>
<tr id="row486071571816"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p14966175712219"><a name="p14966175712219"></a><a name="p14966175712219"></a>ecs:*:list</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p786101511810"><a name="p786101511810"></a><a name="p786101511810"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p118611115101816"><a name="p118611115101816"></a><a name="p118611115101816"></a>ECS（弹性云服务器）所有资源列表的查看权限。</p>
</td>
</tr>
<tr id="row2572115143411"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p4966195742117"><a name="p4966195742117"></a><a name="p4966195742117"></a>evs:*:get</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p135727155348"><a name="p135727155348"></a><a name="p135727155348"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p1957301523411"><a name="p1957301523411"></a><a name="p1957301523411"></a>EVS（云硬盘）所有资源详情的查看权限。可以将云硬盘挂载到云服务器，并可以随时扩容云硬盘容量</p>
</td>
</tr>
<tr id="row4788111418218"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p4966357132115"><a name="p4966357132115"></a><a name="p4966357132115"></a>evs:*:list</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p578813141211"><a name="p578813141211"></a><a name="p578813141211"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p11788141442118"><a name="p11788141442118"></a><a name="p11788141442118"></a>EVS（云硬盘）所有资源列表的查看权限。</p>
</td>
</tr>
<tr id="row17392173118217"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p109661579216"><a name="p109661579216"></a><a name="p109661579216"></a>evs:*:count</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p16392103172111"><a name="p16392103172111"></a><a name="p16392103172111"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p1239210311211"><a name="p1239210311211"></a><a name="p1239210311211"></a>-</p>
</td>
</tr>
<tr id="row12573171515343"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p296715782120"><a name="p296715782120"></a><a name="p296715782120"></a>vpc:*:get</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p65732151343"><a name="p65732151343"></a><a name="p65732151343"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p55734154348"><a name="p55734154348"></a><a name="p55734154348"></a>VPC（虚拟私有云，包含二代ELB）所有资源详情的查看权限。</p>
<p id="p1557361573415"><a name="p1557361573415"></a><a name="p1557361573415"></a>创建的集群需要运行在虚拟私有云中，创建命名空间时，需要创建或关联VPC，创建在命名空间的容器都运行在VPC之内</p>
</td>
</tr>
<tr id="row178108018228"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p296725702114"><a name="p296725702114"></a><a name="p296725702114"></a>vpc:*:list</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p19810120192214"><a name="p19810120192214"></a><a name="p19810120192214"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p48104012227"><a name="p48104012227"></a><a name="p48104012227"></a>VPC（虚拟私有云，包含二代ELB）所有资源列表的查看权限。</p>
</td>
</tr>
<tr id="row12542155562412"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p896735715219"><a name="p896735715219"></a><a name="p896735715219"></a>sfs:*:get*</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p554285511240"><a name="p554285511240"></a><a name="p554285511240"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p1954215550240"><a name="p1954215550240"></a><a name="p1954215550240"></a>SFS（弹性文件服务）服务所有资源详情的查看权限。</p>
</td>
</tr>
<tr id="row5862111011257"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p2096735718214"><a name="p2096735718214"></a><a name="p2096735718214"></a>aom:*:get</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p28624105258"><a name="p28624105258"></a><a name="p28624105258"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p28621210162516"><a name="p28621210162516"></a><a name="p28621210162516"></a>AOM（应用运维管理）服务所有资源详情的查看权限。</p>
</td>
</tr>
<tr id="row1197081652510"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p99674573218"><a name="p99674573218"></a><a name="p99674573218"></a>aom:*:list</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p7970416152513"><a name="p7970416152513"></a><a name="p7970416152513"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p10970151614255"><a name="p10970151614255"></a><a name="p10970151614255"></a>AOM（应用运维管理）服务所有资源列表的查看权限。</p>
</td>
</tr>
<tr id="row107584135256"><td class="cellrowborder" valign="top" width="19.97%" headers="mcps1.2.4.1.1 "><p id="p3967205716219"><a name="p3967205716219"></a><a name="p3967205716219"></a>aom:autoScalingRule:*</p>
</td>
<td class="cellrowborder" valign="top" width="27.029999999999998%" headers="mcps1.2.4.1.2 "><p id="p475811392517"><a name="p475811392517"></a><a name="p475811392517"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.4.1.3 "><p id="p575812138257"><a name="p575812138257"></a><a name="p575812138257"></a>AOM（应用运维管理）服务自动扩缩容规则的所有操作权限。</p>
</td>
</tr>
</tbody>
</table>

## 命名空间权限<a name="section944114820217"></a>

Kubernetes RBAC API定义了四种类型：Role、ClusterRole、RoleBinding与ClusterRoleBinding，这四种类型之间的关系和简要说明如下：

-   **Role和ClusterRole：**描述角色和权限的关系。在Kubernetes的RBAC API中，一个角色定义了一组特定权限的规则。命名空间范围内的角色由Role对象定义，而整个Kubernetes集群范围内有效的角色则通过ClusterRole对象实现。
-   **RoleBinding和ClusterRoleBinding：**描述 subjects （包含users, groups, service accounts）和 角色的关系。角色绑定将一个角色中定义的各种权限授予一个或者一组用户，则该用户或用户组则具有对应绑定的Role或ClusterRole定义的权限。

**表 3**  RBAC API所定义的四种类型

<a name="table7143142111614"></a>
<table><thead align="left"><tr id="row1914410211164"><th class="cellrowborder" valign="top" width="30.620000000000005%" id="mcps1.2.3.1.1"><p id="p614452101611"><a name="p614452101611"></a><a name="p614452101611"></a>类型名称</p>
</th>
<th class="cellrowborder" valign="top" width="69.38%" id="mcps1.2.3.1.2"><p id="p12144622163"><a name="p12144622163"></a><a name="p12144622163"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1014417217164"><td class="cellrowborder" valign="top" width="30.620000000000005%" headers="mcps1.2.3.1.1 "><p id="p153732040131712"><a name="p153732040131712"></a><a name="p153732040131712"></a>Role</p>
</td>
<td class="cellrowborder" valign="top" width="69.38%" headers="mcps1.2.3.1.2 "><p id="p714414221614"><a name="p714414221614"></a><a name="p714414221614"></a>Role对象只能用于授予对某一namespace中资源的访问权限。</p>
</td>
</tr>
<tr id="row2014418219161"><td class="cellrowborder" valign="top" width="30.620000000000005%" headers="mcps1.2.3.1.1 "><p id="p4498748131713"><a name="p4498748131713"></a><a name="p4498748131713"></a>ClusterRole</p>
</td>
<td class="cellrowborder" valign="top" width="69.38%" headers="mcps1.2.3.1.2 "><p id="p176330155212"><a name="p176330155212"></a><a name="p176330155212"></a>ClusterRole对象可以授予整个集群范围内资源访问权限， 也可以对以下几种资源的授予访问权限：</p>
<a name="ul11279114152116"></a><a name="ul11279114152116"></a><ul id="ul11279114152116"><li>集群范围资源（例如节点，即node）。</li><li>非资源类型endpoint（例如”/healthz”）。</li><li>跨所有namespaces的范围资源（例如pod，需要运行命令kubectl get pods --all-namespaces来查询集群中所有的pod)。</li></ul>
</td>
</tr>
<tr id="row16145329168"><td class="cellrowborder" valign="top" width="30.620000000000005%" headers="mcps1.2.3.1.1 "><p id="p13145527161"><a name="p13145527161"></a><a name="p13145527161"></a>RoleBinding</p>
</td>
<td class="cellrowborder" valign="top" width="69.38%" headers="mcps1.2.3.1.2 "><p id="p1214572201610"><a name="p1214572201610"></a><a name="p1214572201610"></a>RoleBinding可以将同一namespace中的subject（用户）绑定到某个具有特定权限的Role下，则此subject即具有该Role定义的权限。</p>
</td>
</tr>
<tr id="row121452211165"><td class="cellrowborder" valign="top" width="30.620000000000005%" headers="mcps1.2.3.1.1 "><p id="p81450211617"><a name="p81450211617"></a><a name="p81450211617"></a>ClusterRoleBinding</p>
</td>
<td class="cellrowborder" valign="top" width="69.38%" headers="mcps1.2.3.1.2 "><p id="p10145525168"><a name="p10145525168"></a><a name="p10145525168"></a>ClusterRoleBinding在整个集群级别和所有namespaces将特定的subject与ClusterRole绑定，授予权限。</p>
</td>
</tr>
</tbody>
</table>

**CCE命名空间权限**

CCE中的命名空间权限是基于Kubernetes RBAC能力的授权，通过权限设置可以让不同的用户或用户组拥有操作不同Kubernetes资源的权限。

CCE的kubernetes资源通过命名空间进行权限设置，目前包含**admin**、**edit**、**view**三种角色，详见[表4](#table174765455252)。

**表 4**  用户/用户组角色说明

<a name="table174765455252"></a>
<table><thead align="left"><tr id="row19540194512257"><th class="cellrowborder" valign="top" width="34.300000000000004%" id="mcps1.2.3.1.1"><p id="p1654017455258"><a name="p1654017455258"></a><a name="p1654017455258"></a>默认的ClusterRole</p>
</th>
<th class="cellrowborder" valign="top" width="65.7%" id="mcps1.2.3.1.2"><p id="p0540144517258"><a name="p0540144517258"></a><a name="p0540144517258"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row195412454251"><td class="cellrowborder" valign="top" width="34.300000000000004%" headers="mcps1.2.3.1.1 "><p id="p4541104518251"><a name="p4541104518251"></a><a name="p4541104518251"></a>admin</p>
</td>
<td class="cellrowborder" valign="top" width="65.7%" headers="mcps1.2.3.1.2 "><p id="p154117452251"><a name="p154117452251"></a><a name="p154117452251"></a>允许admin访问，可以限制在一个namespace中使用RoleBinding。如果在RoleBinding中使用，则允许对namespace中大多数资源进行读写访问，其中包含创建角色和角色绑定的能力。这一角色不允许操作namespace本身，也不能写入资源限额。</p>
</td>
</tr>
<tr id="row12541445182514"><td class="cellrowborder" valign="top" width="34.300000000000004%" headers="mcps1.2.3.1.1 "><p id="p55415459252"><a name="p55415459252"></a><a name="p55415459252"></a>edit</p>
</td>
<td class="cellrowborder" valign="top" width="65.7%" headers="mcps1.2.3.1.2 "><p id="p20541545152519"><a name="p20541545152519"></a><a name="p20541545152519"></a>允许对命名空间内的大多数资源进行读写操作，不允许查看或修改角色，以及角色绑定。</p>
</td>
</tr>
<tr id="row15541154516259"><td class="cellrowborder" valign="top" width="34.300000000000004%" headers="mcps1.2.3.1.1 "><p id="p20541194582515"><a name="p20541194582515"></a><a name="p20541194582515"></a>view</p>
</td>
<td class="cellrowborder" valign="top" width="65.7%" headers="mcps1.2.3.1.2 "><p id="p65420455258"><a name="p65420455258"></a><a name="p65420455258"></a>允许对多数对象进行只读操作，但是对角色、角色绑定及secret是不可访问的。</p>
</td>
</tr>
</tbody>
</table>

更多Kubernetes RBAC授权的内容可以参考[Kubernetes RBAC官方文档](https://kubernetes.io/docs/admin/authorization/rbac/)。

