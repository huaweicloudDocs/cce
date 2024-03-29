# CCE权限概述<a name="cce_10_0187"></a>

CCE权限管理是在统一身份认证服务（IAM）与Kubernetes的角色访问控制（RBAC）的能力基础上，打造的细粒度权限管理功能，支持基于IAM的细粒度权限控制和IAM Token认证，支持集群级别、命名空间级别的权限控制，帮助用户便捷灵活的对租户下的IAM用户、用户组设定不同的操作权限。

如果您需要对CCE集群及相关资源进行精细的权限管理，例如限制不同部门的员工拥有部门内资源的细粒度权限，您可以使用CCE权限管理提供的增强能力进行多维度的权限管理。

本章节将介绍CCE权限管理机制及其涉及到的基本概念。如果当前帐号已经能满足您的要求，您可以跳过本章节，不影响您使用CCE服务的其它功能。

## CCE支持的权限管理能力<a name="section3911182131810"></a>

CCE的权限管理包括“集群权限”和“命名空间权限”两种能力，能够从集群和命名空间层面对用户组或用户进行细粒度授权，具体解释如下：

-   **集群权限：**是基于IAM系统策略的授权，可以通过用户组功能实现IAM用户的授权。用户组是用户的集合，通过集群权限设置可以让某些用户组操作集群（如创建/删除集群、节点、节点池、模板、插件等），而让某些用户组仅能查看集群。

    集群权限涉及CCE非Kubernetes API，支持IAM细粒度策略、企业项目管理相关能力。

-   **命名空间权限：**是基于Kubernetes RBAC（Role-Based Access Control，基于角色的访问控制）能力的授权，通过权限设置可以让不同的用户或用户组拥有操作不同Kubernetes资源的权限。同时CCE基于开源能力进行了增强，可以支持基于IAM用户或用户组粒度进行RBAC授权、IAM token直接访问API进行RBAC认证鉴权。

    命名空间权限涉及CCE Kubernetes API，基于Kubernetes RBAC能力进行增强，支持对接IAM用户/用户组进行授权和认证鉴权，但与IAM细粒度策略独立。

    CCE从v1.11.7-r2版本起的集群支持配置命名空间权限，1.11.7-r2之前的版本默认拥有全部命名空间权限。


CCE的权限可以从使用的阶段分为两个阶段来看，第一个阶段是创建和管理集群的权限，也就是拥有创建/删除集群、节点等资源的权限。第二个阶段是使用集群Kubernetes资源（如工作负载、Service等）的权限。

**图 1**  权限示例图<a name="fig11818185173613"></a>  
![](figures/权限示例图.png "权限示例图")

清楚了集群权限和命名空间权限后，您就可以通过这两步授权，做到精细化的权限控制。

## 集群权限（IAM授权）与命名空间权限（Kubernetes RBAC授权）的关系<a name="section1464135853519"></a>

拥有不同集群权限（IAM授权）的用户，其拥有的命名空间权限（Kubernetes RBAC授权）不同。[表1](#table886210176509)给出了不同用户拥有的命名空间权限详情。

**表 1**  不同用户拥有的命名空间权限

<a name="table886210176509"></a>
<table><thead align="left"><tr id="row14863201719502"><th class="cellrowborder" valign="top" width="46.54%" id="mcps1.2.3.1.1"><p id="p14863111718502"><a name="p14863111718502"></a><a name="p14863111718502"></a>用户类型</p>
</th>
<th class="cellrowborder" valign="top" width="53.459999999999994%" id="mcps1.2.3.1.2"><p id="p10295153183913"><a name="p10295153183913"></a><a name="p10295153183913"></a>1.13及以上版本的集群</p>
</th>
</tr>
</thead>
<tbody><tr id="row138631617185012"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.2.3.1.1 "><p id="p1787744075015"><a name="p1787744075015"></a><a name="p1787744075015"></a>拥有Tenant Administrator权限的用户（例如帐号）</p>
</td>
<td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.2.3.1.2 "><p id="p1829523133913"><a name="p1829523133913"></a><a name="p1829523133913"></a>全部命名空间权限</p>
</td>
</tr>
<tr id="row138631317205019"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.2.3.1.1 "><p id="p3878104075018"><a name="p3878104075018"></a><a name="p3878104075018"></a>拥有CCE Administrator权限的IAM用户</p>
</td>
<td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.2.3.1.2 "><p id="p172951435393"><a name="p172951435393"></a><a name="p172951435393"></a>全部命名空间权限</p>
</td>
</tr>
<tr id="row1386412176506"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.2.3.1.1 "><p id="p187854025013"><a name="p187854025013"></a><a name="p187854025013"></a>拥有CCE&nbsp;FullAccess或者CCE&nbsp;ReadOnlyAccess权限的IAM用户</p>
</td>
<td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.2.3.1.2 "><p id="p7321956194312"><a name="p7321956194312"></a><a name="p7321956194312"></a>按Kubernetes RBAC授权</p>
</td>
</tr>
<tr id="row28641117145019"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.2.3.1.1 "><p id="p11879440195014"><a name="p11879440195014"></a><a name="p11879440195014"></a>拥有Tenant Guest权限的IAM用户</p>
</td>
<td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.2.3.1.2 "><p id="p1932115664317"><a name="p1932115664317"></a><a name="p1932115664317"></a>按Kubernetes RBAC授权</p>
</td>
</tr>
</tbody>
</table>

## kubectl权限说明<a name="section118521730124516"></a>

您可以通过[kubectl访问集群](通过kubectl连接集群.md)的Kubernetes资源，那kubectl拥有哪些Kubernetes资源的权限呢？

kubectl访问CCE集群是通过集群上生成的配置文件（kubeconfig.json）进行认证，kubeconfig.json文件内包含用户信息，CCE根据用户信息的权限判断kubectl有权限访问哪些Kubernetes资源。即哪个用户获取的kubeconfig.json文件，kubeconfig.json就拥有哪个用户的信息，这样使用kubectl访问时就拥有这个用户的权限。而用户拥有的权限就是[表1](#table886210176509)所示的权限。

## 联邦用户支持说明<a name="section56708321158"></a>

IAM支持基于SAML、OIDC协议的单点登录，如果您已经有自己的企业管理系统，同时您的用户需要使用您帐号内的云服务资源，您可以使用IAM的身份提供商功能，实现用户使用企业管理系统帐号单点登录，这一过程称之为联邦身份认证。

通过联邦身份认证访问的用户称为联邦用户，联邦用户相当于IAM用户。

联邦用户使用CCE时需要注意如下两点。

-   用户创建CCE集群时，会在集群中默认为该用户创建一个cluster-admin权限（管理员权限），联邦用户由于每次登录注销都会改变用户ID，所以在CCE控制台权限管理处，权限用户会显示已删除，请勿删除该权限，否则会导致鉴权失败。此种情况下建议在CCE为某个用户组创建cluster-admin权限，将联邦用户加入此用户组。
-   联邦用户不支持创建永久访问密钥AK/SK，在需要使用AK/SK的场景（如创建OBS类型PV/PVC时），只能由帐号或是实体IAM用户创建密钥，共享给联邦用户。由于密钥表示用户所拥有的权限，因此建议由与联邦用户同在一个用户组的实体IAM用户创建并分享密钥。

## IAM支持的授权项<a name="section56179126518"></a>

策略包含系统策略和自定义策略，如果系统策略不满足授权要求，管理员可以创建自定义策略，并通过给用户组授予自定义策略来进行精细的访问控制。策略支持的操作与API相对应，授权项列表说明如下：

-   权限：允许或拒绝某项操作。
-   对应API接口：自定义策略实际调用的API接口。
-   授权项：自定义策略中支持的Action，在自定义策略中的Action中写入授权项，可以实现授权项对应的权限功能。
-   依赖的授权项：部分Action存在对其他Action的依赖，需要将依赖的Action同时写入授权项，才能实现对应的权限功能。
-   IAM项目\(Project\)/企业项目\(Enterprise Project\)：自定义策略的授权范围，包括IAM项目与企业项目。授权范围如果同时支持IAM项目和企业项目，表示此授权项对应的自定义策略，可以在IAM和企业管理两个服务中给用户组授权并生效。如果仅支持IAM项目，不支持企业项目，表示仅能在IAM中给用户组授权并生效，如果在企业管理中授权，则该自定义策略不生效。关于IAM项目与企业项目的区别，详情请参见：[IAM与企业管理的区别](https://support.huaweicloud.com/iam_faq/iam_01_0101.html)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>“√”表示支持，“x”表示暂不支持。

云容器引擎（CCE）支持的自定义策略授权项如下所示：

**表 2**  Cluster

<a name="zh-cn_topic_0272459940_table2746927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0272459940_row5041122"><th class="cellrowborder" valign="top" width="18.74187418741874%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0272459940_p5677776"><a name="zh-cn_topic_0272459940_p5677776"></a><a name="zh-cn_topic_0272459940_p5677776"></a>权限</p>
</th>
<th class="cellrowborder" valign="top" width="32.503250325032504%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0272459940_p54545236"><a name="zh-cn_topic_0272459940_p54545236"></a><a name="zh-cn_topic_0272459940_p54545236"></a>对应API接口</p>
</th>
<th class="cellrowborder" valign="top" width="17.431743174317432%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0272459940_p57246722"><a name="zh-cn_topic_0272459940_p57246722"></a><a name="zh-cn_topic_0272459940_p57246722"></a>授权项（Action）</p>
</th>
<th class="cellrowborder" valign="top" width="13.511351135113511%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0272459940_p6472929"><a name="zh-cn_topic_0272459940_p6472929"></a><a name="zh-cn_topic_0272459940_p6472929"></a>IAM项目(Project)</p>
</th>
<th class="cellrowborder" valign="top" width="17.811781178117812%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0272459940_p1543964512230"><a name="zh-cn_topic_0272459940_p1543964512230"></a><a name="zh-cn_topic_0272459940_p1543964512230"></a>企业项目 (Enterprise Project)</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0272459940_row6218729231"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1121922162320"><a name="zh-cn_topic_0272459940_p1121922162320"></a><a name="zh-cn_topic_0272459940_p1121922162320"></a>获取指定项目下的集群</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p12219102172319"><a name="zh-cn_topic_0272459940_p12219102172319"></a><a name="zh-cn_topic_0272459940_p12219102172319"></a>GET /api/v3/projects/{project_id}/clusters</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p11811740142814"><a name="zh-cn_topic_0272459940_p11811740142814"></a><a name="zh-cn_topic_0272459940_p11811740142814"></a>cce:cluster:list</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p1127552282613"><a name="zh-cn_topic_0272459940_p1127552282613"></a><a name="zh-cn_topic_0272459940_p1127552282613"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p14439164572311"><a name="zh-cn_topic_0272459940_p14439164572311"></a><a name="zh-cn_topic_0272459940_p14439164572311"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row60174342914"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p160184313297"><a name="zh-cn_topic_0272459940_p160184313297"></a><a name="zh-cn_topic_0272459940_p160184313297"></a>获取指定的集群</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p140174319298"><a name="zh-cn_topic_0272459940_p140174319298"></a><a name="zh-cn_topic_0272459940_p140174319298"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p11841940182811"><a name="zh-cn_topic_0272459940_p11841940182811"></a><a name="zh-cn_topic_0272459940_p11841940182811"></a>cce:cluster:get</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p108721628142617"><a name="zh-cn_topic_0272459940_p108721628142617"></a><a name="zh-cn_topic_0272459940_p108721628142617"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1787213285268"><a name="zh-cn_topic_0272459940_p1787213285268"></a><a name="zh-cn_topic_0272459940_p1787213285268"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row1930454173014"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p63049414303"><a name="zh-cn_topic_0272459940_p63049414303"></a><a name="zh-cn_topic_0272459940_p63049414303"></a>创建集群</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p113042493011"><a name="zh-cn_topic_0272459940_p113042493011"></a><a name="zh-cn_topic_0272459940_p113042493011"></a>POST /api/v3/projects/{project_id}/clusters</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p131861940132813"><a name="zh-cn_topic_0272459940_p131861940132813"></a><a name="zh-cn_topic_0272459940_p131861940132813"></a>cce:cluster:create</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p13553320267"><a name="zh-cn_topic_0272459940_p13553320267"></a><a name="zh-cn_topic_0272459940_p13553320267"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p183515339262"><a name="zh-cn_topic_0272459940_p183515339262"></a><a name="zh-cn_topic_0272459940_p183515339262"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row47112191304"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p177161912304"><a name="zh-cn_topic_0272459940_p177161912304"></a><a name="zh-cn_topic_0272459940_p177161912304"></a>更新指定的集群</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p2071191943010"><a name="zh-cn_topic_0272459940_p2071191943010"></a><a name="zh-cn_topic_0272459940_p2071191943010"></a>PUT /api/v3/projects/{project_id}/clusters/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p618964012812"><a name="zh-cn_topic_0272459940_p618964012812"></a><a name="zh-cn_topic_0272459940_p618964012812"></a>cce:cluster:update</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p6367331266"><a name="zh-cn_topic_0272459940_p6367331266"></a><a name="zh-cn_topic_0272459940_p6367331266"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p16362033142617"><a name="zh-cn_topic_0272459940_p16362033142617"></a><a name="zh-cn_topic_0272459940_p16362033142617"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row12227515103011"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1422715151309"><a name="zh-cn_topic_0272459940_p1422715151309"></a><a name="zh-cn_topic_0272459940_p1422715151309"></a>删除集群</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p3227101553017"><a name="zh-cn_topic_0272459940_p3227101553017"></a><a name="zh-cn_topic_0272459940_p3227101553017"></a>DELETE /api/v3/projects/{project_id}/clusters/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1819154012288"><a name="zh-cn_topic_0272459940_p1819154012288"></a><a name="zh-cn_topic_0272459940_p1819154012288"></a>cce:cluster:delete</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p725116372268"><a name="zh-cn_topic_0272459940_p725116372268"></a><a name="zh-cn_topic_0272459940_p725116372268"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p132511837132611"><a name="zh-cn_topic_0272459940_p132511837132611"></a><a name="zh-cn_topic_0272459940_p132511837132611"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row08371357151013"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p13837357151010"><a name="zh-cn_topic_0272459940_p13837357151010"></a><a name="zh-cn_topic_0272459940_p13837357151010"></a>升级集群</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p58371957141017"><a name="zh-cn_topic_0272459940_p58371957141017"></a><a name="zh-cn_topic_0272459940_p58371957141017"></a>POST /api/v2/projects/:projectid/clusters/:clusterid/upgrade</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p208371657101020"><a name="zh-cn_topic_0272459940_p208371657101020"></a><a name="zh-cn_topic_0272459940_p208371657101020"></a>cce:cluster:upgrade</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p425143714263"><a name="zh-cn_topic_0272459940_p425143714263"></a><a name="zh-cn_topic_0272459940_p425143714263"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1251123752618"><a name="zh-cn_topic_0272459940_p1251123752618"></a><a name="zh-cn_topic_0272459940_p1251123752618"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row44931332122"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1249433181210"><a name="zh-cn_topic_0272459940_p1249433181210"></a><a name="zh-cn_topic_0272459940_p1249433181210"></a>唤醒集群</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p18494183101215"><a name="zh-cn_topic_0272459940_p18494183101215"></a><a name="zh-cn_topic_0272459940_p18494183101215"></a>POST /api/v3/projects/{project_id}/clusters/{cluster_id}/operation/awake</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1494163111210"><a name="zh-cn_topic_0272459940_p1494163111210"></a><a name="zh-cn_topic_0272459940_p1494163111210"></a>cce:cluster:start</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p5204193902613"><a name="zh-cn_topic_0272459940_p5204193902613"></a><a name="zh-cn_topic_0272459940_p5204193902613"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1420412391269"><a name="zh-cn_topic_0272459940_p1420412391269"></a><a name="zh-cn_topic_0272459940_p1420412391269"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row111668189129"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p216619181124"><a name="zh-cn_topic_0272459940_p216619181124"></a><a name="zh-cn_topic_0272459940_p216619181124"></a>休眠集群</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p916681851220"><a name="zh-cn_topic_0272459940_p916681851220"></a><a name="zh-cn_topic_0272459940_p916681851220"></a>POST /api/v3/projects/{project_id}/clusters/{cluster_id}/operation/hibernate</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p15166101814129"><a name="zh-cn_topic_0272459940_p15166101814129"></a><a name="zh-cn_topic_0272459940_p15166101814129"></a>cce:cluster:stop</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p1120413396262"><a name="zh-cn_topic_0272459940_p1120413396262"></a><a name="zh-cn_topic_0272459940_p1120413396262"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p10204183962613"><a name="zh-cn_topic_0272459940_p10204183962613"></a><a name="zh-cn_topic_0272459940_p10204183962613"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row1841934513124"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p17419945181214"><a name="zh-cn_topic_0272459940_p17419945181214"></a><a name="zh-cn_topic_0272459940_p17419945181214"></a>变更集群规格</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p0419745121214"><a name="zh-cn_topic_0272459940_p0419745121214"></a><a name="zh-cn_topic_0272459940_p0419745121214"></a>POST /api/v2/projects/{project_id}/clusters/:clusterid/resize</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p841919453128"><a name="zh-cn_topic_0272459940_p841919453128"></a><a name="zh-cn_topic_0272459940_p841919453128"></a>cce:cluster:resize</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p1340141112610"><a name="zh-cn_topic_0272459940_p1340141112610"></a><a name="zh-cn_topic_0272459940_p1340141112610"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1740134110269"><a name="zh-cn_topic_0272459940_p1740134110269"></a><a name="zh-cn_topic_0272459940_p1740134110269"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row3113121214304"><td class="cellrowborder" valign="top" width="18.74187418741874%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1114201211303"><a name="zh-cn_topic_0272459940_p1114201211303"></a><a name="zh-cn_topic_0272459940_p1114201211303"></a>获取集群证书</p>
</td>
<td class="cellrowborder" valign="top" width="32.503250325032504%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p6114111223018"><a name="zh-cn_topic_0272459940_p6114111223018"></a><a name="zh-cn_topic_0272459940_p6114111223018"></a>POST /api/v3/projects/{project_id}/clusters/{cluster_id}/clustercert</p>
</td>
<td class="cellrowborder" valign="top" width="17.431743174317432%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1919204020283"><a name="zh-cn_topic_0272459940_p1919204020283"></a><a name="zh-cn_topic_0272459940_p1919204020283"></a>cce:cluster:get</p>
</td>
<td class="cellrowborder" valign="top" width="13.511351135113511%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p1740341102617"><a name="zh-cn_topic_0272459940_p1740341102617"></a><a name="zh-cn_topic_0272459940_p1740341102617"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="17.811781178117812%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p114024110261"><a name="zh-cn_topic_0272459940_p114024110261"></a><a name="zh-cn_topic_0272459940_p114024110261"></a>√</p>
</td>
</tr>
</tbody>
</table>

**表 3**  Node

<a name="zh-cn_topic_0272459940_table1746903216815"></a>
<table><thead align="left"><tr id="zh-cn_topic_0272459940_row1547020324819"><th class="cellrowborder" valign="top" width="18.66%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0272459940_p19470143217816"><a name="zh-cn_topic_0272459940_p19470143217816"></a><a name="zh-cn_topic_0272459940_p19470143217816"></a>权限</p>
</th>
<th class="cellrowborder" valign="top" width="32.42%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0272459940_p1247011322815"><a name="zh-cn_topic_0272459940_p1247011322815"></a><a name="zh-cn_topic_0272459940_p1247011322815"></a>对应API接口</p>
</th>
<th class="cellrowborder" valign="top" width="17.540000000000003%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0272459940_p54701732389"><a name="zh-cn_topic_0272459940_p54701732389"></a><a name="zh-cn_topic_0272459940_p54701732389"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="13.330000000000004%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0272459940_p194352379271"><a name="zh-cn_topic_0272459940_p194352379271"></a><a name="zh-cn_topic_0272459940_p194352379271"></a>IAM项目(Project)</p>
</th>
<th class="cellrowborder" valign="top" width="18.05%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0272459940_p18435437122710"><a name="zh-cn_topic_0272459940_p18435437122710"></a><a name="zh-cn_topic_0272459940_p18435437122710"></a>企业项目 (Enterprise Project)</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0272459940_row1847116323811"><td class="cellrowborder" valign="top" width="18.66%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p2471113214815"><a name="zh-cn_topic_0272459940_p2471113214815"></a><a name="zh-cn_topic_0272459940_p2471113214815"></a>获取集群下所有节点</p>
</td>
<td class="cellrowborder" valign="top" width="32.42%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p184711532386"><a name="zh-cn_topic_0272459940_p184711532386"></a><a name="zh-cn_topic_0272459940_p184711532386"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes</p>
</td>
<td class="cellrowborder" valign="top" width="17.540000000000003%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1847119321818"><a name="zh-cn_topic_0272459940_p1847119321818"></a><a name="zh-cn_topic_0272459940_p1847119321818"></a>cce:node:list</p>
</td>
<td class="cellrowborder" valign="top" width="13.330000000000004%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p64351937192711"><a name="zh-cn_topic_0272459940_p64351937192711"></a><a name="zh-cn_topic_0272459940_p64351937192711"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p843619370275"><a name="zh-cn_topic_0272459940_p843619370275"></a><a name="zh-cn_topic_0272459940_p843619370275"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row84718324816"><td class="cellrowborder" valign="top" width="18.66%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p94711932386"><a name="zh-cn_topic_0272459940_p94711932386"></a><a name="zh-cn_topic_0272459940_p94711932386"></a>获取指定的节点</p>
</td>
<td class="cellrowborder" valign="top" width="32.42%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p847115326819"><a name="zh-cn_topic_0272459940_p847115326819"></a><a name="zh-cn_topic_0272459940_p847115326819"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes/{node_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.540000000000003%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1347123212818"><a name="zh-cn_topic_0272459940_p1347123212818"></a><a name="zh-cn_topic_0272459940_p1347123212818"></a>cce:node:get</p>
</td>
<td class="cellrowborder" valign="top" width="13.330000000000004%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p194365370274"><a name="zh-cn_topic_0272459940_p194365370274"></a><a name="zh-cn_topic_0272459940_p194365370274"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p9436133762714"><a name="zh-cn_topic_0272459940_p9436133762714"></a><a name="zh-cn_topic_0272459940_p9436133762714"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row16472153216811"><td class="cellrowborder" valign="top" width="18.66%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p124721132189"><a name="zh-cn_topic_0272459940_p124721132189"></a><a name="zh-cn_topic_0272459940_p124721132189"></a>创建节点</p>
</td>
<td class="cellrowborder" valign="top" width="32.42%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p1547273216814"><a name="zh-cn_topic_0272459940_p1547273216814"></a><a name="zh-cn_topic_0272459940_p1547273216814"></a>POST /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes</p>
</td>
<td class="cellrowborder" valign="top" width="17.540000000000003%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p124721323819"><a name="zh-cn_topic_0272459940_p124721323819"></a><a name="zh-cn_topic_0272459940_p124721323819"></a>cce:node:create</p>
</td>
<td class="cellrowborder" valign="top" width="13.330000000000004%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p3436183792712"><a name="zh-cn_topic_0272459940_p3436183792712"></a><a name="zh-cn_topic_0272459940_p3436183792712"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p14436437142713"><a name="zh-cn_topic_0272459940_p14436437142713"></a><a name="zh-cn_topic_0272459940_p14436437142713"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row44727324814"><td class="cellrowborder" valign="top" width="18.66%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p164723320819"><a name="zh-cn_topic_0272459940_p164723320819"></a><a name="zh-cn_topic_0272459940_p164723320819"></a>更新指定的节点</p>
</td>
<td class="cellrowborder" valign="top" width="32.42%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p747283218816"><a name="zh-cn_topic_0272459940_p747283218816"></a><a name="zh-cn_topic_0272459940_p747283218816"></a>PUT /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes/{node_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.540000000000003%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p947253217816"><a name="zh-cn_topic_0272459940_p947253217816"></a><a name="zh-cn_topic_0272459940_p947253217816"></a>cce:node:update</p>
</td>
<td class="cellrowborder" valign="top" width="13.330000000000004%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p24361837162719"><a name="zh-cn_topic_0272459940_p24361837162719"></a><a name="zh-cn_topic_0272459940_p24361837162719"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p34367377273"><a name="zh-cn_topic_0272459940_p34367377273"></a><a name="zh-cn_topic_0272459940_p34367377273"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row184721532483"><td class="cellrowborder" valign="top" width="18.66%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p134723323811"><a name="zh-cn_topic_0272459940_p134723323811"></a><a name="zh-cn_topic_0272459940_p134723323811"></a>删除节点</p>
</td>
<td class="cellrowborder" valign="top" width="32.42%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p1847283214811"><a name="zh-cn_topic_0272459940_p1847283214811"></a><a name="zh-cn_topic_0272459940_p1847283214811"></a>DELETE /api/v3/projects/{project_id}/clusters/{cluster_id}/nodes/{node_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.540000000000003%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p184721321481"><a name="zh-cn_topic_0272459940_p184721321481"></a><a name="zh-cn_topic_0272459940_p184721321481"></a>cce:node:delete</p>
</td>
<td class="cellrowborder" valign="top" width="13.330000000000004%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p743683719271"><a name="zh-cn_topic_0272459940_p743683719271"></a><a name="zh-cn_topic_0272459940_p743683719271"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p243663712718"><a name="zh-cn_topic_0272459940_p243663712718"></a><a name="zh-cn_topic_0272459940_p243663712718"></a>√</p>
</td>
</tr>
</tbody>
</table>

**表 4**  Job

<a name="zh-cn_topic_0272459940_table178226341483"></a>
<table><thead align="left"><tr id="zh-cn_topic_0272459940_row118231534784"><th class="cellrowborder" valign="top" width="18.47%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0272459940_p1182316340811"><a name="zh-cn_topic_0272459940_p1182316340811"></a><a name="zh-cn_topic_0272459940_p1182316340811"></a>权限</p>
</th>
<th class="cellrowborder" valign="top" width="32.35%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0272459940_p20823434988"><a name="zh-cn_topic_0272459940_p20823434988"></a><a name="zh-cn_topic_0272459940_p20823434988"></a>对应API接口</p>
</th>
<th class="cellrowborder" valign="top" width="17.72%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0272459940_p1382317341287"><a name="zh-cn_topic_0272459940_p1382317341287"></a><a name="zh-cn_topic_0272459940_p1382317341287"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="13.41%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0272459940_p398120015299"><a name="zh-cn_topic_0272459940_p398120015299"></a><a name="zh-cn_topic_0272459940_p398120015299"></a>IAM项目(Project)</p>
</th>
<th class="cellrowborder" valign="top" width="18.05%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0272459940_p1598112072916"><a name="zh-cn_topic_0272459940_p1598112072916"></a><a name="zh-cn_topic_0272459940_p1598112072916"></a>企业项目 (Enterprise Project)</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0272459940_row2826163416814"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p118261434681"><a name="zh-cn_topic_0272459940_p118261434681"></a><a name="zh-cn_topic_0272459940_p118261434681"></a>获取任务信息</p>
</td>
<td class="cellrowborder" valign="top" width="32.35%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p98261345811"><a name="zh-cn_topic_0272459940_p98261345811"></a><a name="zh-cn_topic_0272459940_p98261345811"></a>GET /api/v3/projects/{project_id}/jobs/{job_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p682611349817"><a name="zh-cn_topic_0272459940_p682611349817"></a><a name="zh-cn_topic_0272459940_p682611349817"></a>cce:job:get</p>
</td>
<td class="cellrowborder" valign="top" width="13.41%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p39812003293"><a name="zh-cn_topic_0272459940_p39812003293"></a><a name="zh-cn_topic_0272459940_p39812003293"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p7981190122915"><a name="zh-cn_topic_0272459940_p7981190122915"></a><a name="zh-cn_topic_0272459940_p7981190122915"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row98269343810"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1182693416819"><a name="zh-cn_topic_0272459940_p1182693416819"></a><a name="zh-cn_topic_0272459940_p1182693416819"></a>列出所有任务</p>
</td>
<td class="cellrowborder" valign="top" width="32.35%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p7827434280"><a name="zh-cn_topic_0272459940_p7827434280"></a><a name="zh-cn_topic_0272459940_p7827434280"></a>GET /api/v2/projects/{project_id}/jobs</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p14826183418817"><a name="zh-cn_topic_0272459940_p14826183418817"></a><a name="zh-cn_topic_0272459940_p14826183418817"></a>cce:job:list</p>
</td>
<td class="cellrowborder" valign="top" width="13.41%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p4981130172917"><a name="zh-cn_topic_0272459940_p4981130172917"></a><a name="zh-cn_topic_0272459940_p4981130172917"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p4981190132916"><a name="zh-cn_topic_0272459940_p4981190132916"></a><a name="zh-cn_topic_0272459940_p4981190132916"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row148275341788"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p14827834686"><a name="zh-cn_topic_0272459940_p14827834686"></a><a name="zh-cn_topic_0272459940_p14827834686"></a>删除所有任务或删除单个任务</p>
</td>
<td class="cellrowborder" valign="top" width="32.35%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p88271134184"><a name="zh-cn_topic_0272459940_p88271134184"></a><a name="zh-cn_topic_0272459940_p88271134184"></a>DELETE /api/v2/projects/{project_id}/jobs</p>
<p id="zh-cn_topic_0272459940_p1482713341184"><a name="zh-cn_topic_0272459940_p1482713341184"></a><a name="zh-cn_topic_0272459940_p1482713341184"></a>DELETE /api/v2/projects/{project_id}/jobs/{job_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p108274345812"><a name="zh-cn_topic_0272459940_p108274345812"></a><a name="zh-cn_topic_0272459940_p108274345812"></a>cce:job:delete</p>
</td>
<td class="cellrowborder" valign="top" width="13.41%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p189810011299"><a name="zh-cn_topic_0272459940_p189810011299"></a><a name="zh-cn_topic_0272459940_p189810011299"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p149827011299"><a name="zh-cn_topic_0272459940_p149827011299"></a><a name="zh-cn_topic_0272459940_p149827011299"></a>√</p>
</td>
</tr>
</tbody>
</table>

**表 5**  Nodepool

<a name="zh-cn_topic_0272459940_table1829914374813"></a>
<table><thead align="left"><tr id="zh-cn_topic_0272459940_row1929910371383"><th class="cellrowborder" valign="top" width="18.47%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0272459940_p1529983716816"><a name="zh-cn_topic_0272459940_p1529983716816"></a><a name="zh-cn_topic_0272459940_p1529983716816"></a>权限</p>
</th>
<th class="cellrowborder" valign="top" width="32.35%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0272459940_p102991937987"><a name="zh-cn_topic_0272459940_p102991937987"></a><a name="zh-cn_topic_0272459940_p102991937987"></a>对应API接口</p>
</th>
<th class="cellrowborder" valign="top" width="17.72%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0272459940_p172991375812"><a name="zh-cn_topic_0272459940_p172991375812"></a><a name="zh-cn_topic_0272459940_p172991375812"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="13.15%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0272459940_p1060816464291"><a name="zh-cn_topic_0272459940_p1060816464291"></a><a name="zh-cn_topic_0272459940_p1060816464291"></a>IAM项目(Project)</p>
</th>
<th class="cellrowborder" valign="top" width="18.310000000000002%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0272459940_p19609146202913"><a name="zh-cn_topic_0272459940_p19609146202913"></a><a name="zh-cn_topic_0272459940_p19609146202913"></a>企业项目 (Enterprise Project)</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0272459940_row1230410371989"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1304337184"><a name="zh-cn_topic_0272459940_p1304337184"></a><a name="zh-cn_topic_0272459940_p1304337184"></a>获取集群下所有节点池</p>
</td>
<td class="cellrowborder" valign="top" width="32.35%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p1930516371815"><a name="zh-cn_topic_0272459940_p1930516371815"></a><a name="zh-cn_topic_0272459940_p1930516371815"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}/nodepools</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1630416371818"><a name="zh-cn_topic_0272459940_p1630416371818"></a><a name="zh-cn_topic_0272459940_p1630416371818"></a>cce:nodepool:list</p>
</td>
<td class="cellrowborder" valign="top" width="13.15%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p76097460298"><a name="zh-cn_topic_0272459940_p76097460298"></a><a name="zh-cn_topic_0272459940_p76097460298"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p126097469294"><a name="zh-cn_topic_0272459940_p126097469294"></a><a name="zh-cn_topic_0272459940_p126097469294"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row93056379817"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p53055371982"><a name="zh-cn_topic_0272459940_p53055371982"></a><a name="zh-cn_topic_0272459940_p53055371982"></a>获取节点池</p>
</td>
<td class="cellrowborder" valign="top" width="32.35%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p930533710817"><a name="zh-cn_topic_0272459940_p930533710817"></a><a name="zh-cn_topic_0272459940_p930533710817"></a>GET /api/v3/projects/{project_id}/clusters/{cluster_id}/nodepools/{nodepool_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1130515371284"><a name="zh-cn_topic_0272459940_p1130515371284"></a><a name="zh-cn_topic_0272459940_p1130515371284"></a>cce:nodepool:get</p>
</td>
<td class="cellrowborder" valign="top" width="13.15%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p116097464293"><a name="zh-cn_topic_0272459940_p116097464293"></a><a name="zh-cn_topic_0272459940_p116097464293"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1960924610293"><a name="zh-cn_topic_0272459940_p1960924610293"></a><a name="zh-cn_topic_0272459940_p1960924610293"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row1530513370816"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1730503714816"><a name="zh-cn_topic_0272459940_p1730503714816"></a><a name="zh-cn_topic_0272459940_p1730503714816"></a>创建节点池</p>
</td>
<td class="cellrowborder" valign="top" width="32.35%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p230573713812"><a name="zh-cn_topic_0272459940_p230573713812"></a><a name="zh-cn_topic_0272459940_p230573713812"></a>POST /api/v3/projects/{project_id}/clusters/{cluster_id}/nodepools</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p7305937182"><a name="zh-cn_topic_0272459940_p7305937182"></a><a name="zh-cn_topic_0272459940_p7305937182"></a>cce:nodepool:create</p>
</td>
<td class="cellrowborder" valign="top" width="13.15%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p146098465290"><a name="zh-cn_topic_0272459940_p146098465290"></a><a name="zh-cn_topic_0272459940_p146098465290"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p46091462296"><a name="zh-cn_topic_0272459940_p46091462296"></a><a name="zh-cn_topic_0272459940_p46091462296"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row43051437685"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p19305203710815"><a name="zh-cn_topic_0272459940_p19305203710815"></a><a name="zh-cn_topic_0272459940_p19305203710815"></a>更新节点池信息</p>
</td>
<td class="cellrowborder" valign="top" width="32.35%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p63053371586"><a name="zh-cn_topic_0272459940_p63053371586"></a><a name="zh-cn_topic_0272459940_p63053371586"></a>PUT /api/v3/projects/{project_id}/clusters/{cluster_id}/nodepools/{nodepool_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p2305113716811"><a name="zh-cn_topic_0272459940_p2305113716811"></a><a name="zh-cn_topic_0272459940_p2305113716811"></a>cce:nodepool:update</p>
</td>
<td class="cellrowborder" valign="top" width="13.15%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p1360934662914"><a name="zh-cn_topic_0272459940_p1360934662914"></a><a name="zh-cn_topic_0272459940_p1360934662914"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p4609246142918"><a name="zh-cn_topic_0272459940_p4609246142918"></a><a name="zh-cn_topic_0272459940_p4609246142918"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row1130518373815"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1730573716817"><a name="zh-cn_topic_0272459940_p1730573716817"></a><a name="zh-cn_topic_0272459940_p1730573716817"></a>删除节点池</p>
</td>
<td class="cellrowborder" valign="top" width="32.35%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p18305437084"><a name="zh-cn_topic_0272459940_p18305437084"></a><a name="zh-cn_topic_0272459940_p18305437084"></a>DELETE /api/v3/projects/{project_id}/clusters/{cluster_id}/nodepools/{nodepool_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1630512379814"><a name="zh-cn_topic_0272459940_p1630512379814"></a><a name="zh-cn_topic_0272459940_p1630512379814"></a>cce:nodepool:delete</p>
</td>
<td class="cellrowborder" valign="top" width="13.15%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p3609146112912"><a name="zh-cn_topic_0272459940_p3609146112912"></a><a name="zh-cn_topic_0272459940_p3609146112912"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1860924692912"><a name="zh-cn_topic_0272459940_p1860924692912"></a><a name="zh-cn_topic_0272459940_p1860924692912"></a>√</p>
</td>
</tr>
</tbody>
</table>

**表 6**  Chart

<a name="zh-cn_topic_0272459940_table368013422089"></a>
<table><thead align="left"><tr id="zh-cn_topic_0272459940_row1168194213814"><th class="cellrowborder" valign="top" width="18.47%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0272459940_p126811424814"><a name="zh-cn_topic_0272459940_p126811424814"></a><a name="zh-cn_topic_0272459940_p126811424814"></a>权限</p>
</th>
<th class="cellrowborder" valign="top" width="32.43%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0272459940_p66814422818"><a name="zh-cn_topic_0272459940_p66814422818"></a><a name="zh-cn_topic_0272459940_p66814422818"></a>对应API接口</p>
</th>
<th class="cellrowborder" valign="top" width="17.46%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0272459940_p1068184220818"><a name="zh-cn_topic_0272459940_p1068184220818"></a><a name="zh-cn_topic_0272459940_p1068184220818"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="13.33%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0272459940_p4637102519306"><a name="zh-cn_topic_0272459940_p4637102519306"></a><a name="zh-cn_topic_0272459940_p4637102519306"></a>IAM项目(Project)</p>
</th>
<th class="cellrowborder" valign="top" width="18.310000000000002%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0272459940_p10637192533010"><a name="zh-cn_topic_0272459940_p10637192533010"></a><a name="zh-cn_topic_0272459940_p10637192533010"></a>企业项目 (Enterprise Project)</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0272459940_row1368415426810"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p668404210816"><a name="zh-cn_topic_0272459940_p668404210816"></a><a name="zh-cn_topic_0272459940_p668404210816"></a>更新模板</p>
</td>
<td class="cellrowborder" valign="top" width="32.43%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p16841342289"><a name="zh-cn_topic_0272459940_p16841342289"></a><a name="zh-cn_topic_0272459940_p16841342289"></a>PUT /v2/charts/{id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1868417423811"><a name="zh-cn_topic_0272459940_p1868417423811"></a><a name="zh-cn_topic_0272459940_p1868417423811"></a>cce:chart:update</p>
</td>
<td class="cellrowborder" valign="top" width="13.33%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p16371425153010"><a name="zh-cn_topic_0272459940_p16371425153010"></a><a name="zh-cn_topic_0272459940_p16371425153010"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p3637182593019"><a name="zh-cn_topic_0272459940_p3637182593019"></a><a name="zh-cn_topic_0272459940_p3637182593019"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row2068464217811"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p868444218811"><a name="zh-cn_topic_0272459940_p868444218811"></a><a name="zh-cn_topic_0272459940_p868444218811"></a>上传模板</p>
</td>
<td class="cellrowborder" valign="top" width="32.43%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p16684164214814"><a name="zh-cn_topic_0272459940_p16684164214814"></a><a name="zh-cn_topic_0272459940_p16684164214814"></a>POST /v2/charts</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p2684642586"><a name="zh-cn_topic_0272459940_p2684642586"></a><a name="zh-cn_topic_0272459940_p2684642586"></a>cce:chart:upload</p>
</td>
<td class="cellrowborder" valign="top" width="13.33%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p363710253306"><a name="zh-cn_topic_0272459940_p363710253306"></a><a name="zh-cn_topic_0272459940_p363710253306"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p83478580265"><a name="zh-cn_topic_0272459940_p83478580265"></a><a name="zh-cn_topic_0272459940_p83478580265"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row9684194215810"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p196845422083"><a name="zh-cn_topic_0272459940_p196845422083"></a><a name="zh-cn_topic_0272459940_p196845422083"></a>列出所有模板</p>
</td>
<td class="cellrowborder" valign="top" width="32.43%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p1368413421585"><a name="zh-cn_topic_0272459940_p1368413421585"></a><a name="zh-cn_topic_0272459940_p1368413421585"></a>GET /v2/charts</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p106841542886"><a name="zh-cn_topic_0272459940_p106841542886"></a><a name="zh-cn_topic_0272459940_p106841542886"></a>cce:chart:list</p>
</td>
<td class="cellrowborder" valign="top" width="13.33%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p11637132515305"><a name="zh-cn_topic_0272459940_p11637132515305"></a><a name="zh-cn_topic_0272459940_p11637132515305"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p737515583269"><a name="zh-cn_topic_0272459940_p737515583269"></a><a name="zh-cn_topic_0272459940_p737515583269"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row168411421085"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p7684144215820"><a name="zh-cn_topic_0272459940_p7684144215820"></a><a name="zh-cn_topic_0272459940_p7684144215820"></a>获取模板信息</p>
</td>
<td class="cellrowborder" valign="top" width="32.43%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p868434218819"><a name="zh-cn_topic_0272459940_p868434218819"></a><a name="zh-cn_topic_0272459940_p868434218819"></a>GET /v2/charts/{id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p768420421484"><a name="zh-cn_topic_0272459940_p768420421484"></a><a name="zh-cn_topic_0272459940_p768420421484"></a>cce:chart:get</p>
</td>
<td class="cellrowborder" valign="top" width="13.33%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p36370253309"><a name="zh-cn_topic_0272459940_p36370253309"></a><a name="zh-cn_topic_0272459940_p36370253309"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p740195818262"><a name="zh-cn_topic_0272459940_p740195818262"></a><a name="zh-cn_topic_0272459940_p740195818262"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row168420421686"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p168512421682"><a name="zh-cn_topic_0272459940_p168512421682"></a><a name="zh-cn_topic_0272459940_p168512421682"></a>删除模板</p>
</td>
<td class="cellrowborder" valign="top" width="32.43%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p12685144220812"><a name="zh-cn_topic_0272459940_p12685144220812"></a><a name="zh-cn_topic_0272459940_p12685144220812"></a>DELETE /v2/charts/{id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p116854421587"><a name="zh-cn_topic_0272459940_p116854421587"></a><a name="zh-cn_topic_0272459940_p116854421587"></a>cce:chart:delete</p>
</td>
<td class="cellrowborder" valign="top" width="13.33%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p116381725173017"><a name="zh-cn_topic_0272459940_p116381725173017"></a><a name="zh-cn_topic_0272459940_p116381725173017"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.310000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p6412758112612"><a name="zh-cn_topic_0272459940_p6412758112612"></a><a name="zh-cn_topic_0272459940_p6412758112612"></a>×</p>
</td>
</tr>
</tbody>
</table>

**表 7**  Release

<a name="zh-cn_topic_0272459940_table113998457819"></a>
<table><thead align="left"><tr id="zh-cn_topic_0272459940_row1039918456810"><th class="cellrowborder" valign="top" width="18.47%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0272459940_p139912458811"><a name="zh-cn_topic_0272459940_p139912458811"></a><a name="zh-cn_topic_0272459940_p139912458811"></a>权限</p>
</th>
<th class="cellrowborder" valign="top" width="32.61%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0272459940_p1039919451080"><a name="zh-cn_topic_0272459940_p1039919451080"></a><a name="zh-cn_topic_0272459940_p1039919451080"></a>对应API接口</p>
</th>
<th class="cellrowborder" valign="top" width="17.46%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0272459940_p10399164510818"><a name="zh-cn_topic_0272459940_p10399164510818"></a><a name="zh-cn_topic_0272459940_p10399164510818"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="12.97%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0272459940_p1530345653019"><a name="zh-cn_topic_0272459940_p1530345653019"></a><a name="zh-cn_topic_0272459940_p1530345653019"></a>IAM项目(Project)</p>
</th>
<th class="cellrowborder" valign="top" width="18.490000000000002%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0272459940_p83031567306"><a name="zh-cn_topic_0272459940_p83031567306"></a><a name="zh-cn_topic_0272459940_p83031567306"></a>企业项目 (Enterprise Project)</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0272459940_row1640320451087"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p12403134510819"><a name="zh-cn_topic_0272459940_p12403134510819"></a><a name="zh-cn_topic_0272459940_p12403134510819"></a>更新升级模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p1940320451286"><a name="zh-cn_topic_0272459940_p1940320451286"></a><a name="zh-cn_topic_0272459940_p1940320451286"></a>PUT /v2/releases/{name}</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p174033451088"><a name="zh-cn_topic_0272459940_p174033451088"></a><a name="zh-cn_topic_0272459940_p174033451088"></a>cce:release:update</p>
</td>
<td class="cellrowborder" valign="top" width="12.97%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p133038560309"><a name="zh-cn_topic_0272459940_p133038560309"></a><a name="zh-cn_topic_0272459940_p133038560309"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p7303956133017"><a name="zh-cn_topic_0272459940_p7303956133017"></a><a name="zh-cn_topic_0272459940_p7303956133017"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row84031459816"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p164031845188"><a name="zh-cn_topic_0272459940_p164031845188"></a><a name="zh-cn_topic_0272459940_p164031845188"></a>列出所有模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p940313453818"><a name="zh-cn_topic_0272459940_p940313453818"></a><a name="zh-cn_topic_0272459940_p940313453818"></a>GET /v2/releases</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p14403104513815"><a name="zh-cn_topic_0272459940_p14403104513815"></a><a name="zh-cn_topic_0272459940_p14403104513815"></a>cce:release:list</p>
</td>
<td class="cellrowborder" valign="top" width="12.97%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p17303115643014"><a name="zh-cn_topic_0272459940_p17303115643014"></a><a name="zh-cn_topic_0272459940_p17303115643014"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1730335617309"><a name="zh-cn_topic_0272459940_p1730335617309"></a><a name="zh-cn_topic_0272459940_p1730335617309"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row040384517813"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1240364510811"><a name="zh-cn_topic_0272459940_p1240364510811"></a><a name="zh-cn_topic_0272459940_p1240364510811"></a>创建模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p64041545988"><a name="zh-cn_topic_0272459940_p64041545988"></a><a name="zh-cn_topic_0272459940_p64041545988"></a>POST /v2/releases</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p164039452088"><a name="zh-cn_topic_0272459940_p164039452088"></a><a name="zh-cn_topic_0272459940_p164039452088"></a>cce:release:create</p>
</td>
<td class="cellrowborder" valign="top" width="12.97%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p1830312563304"><a name="zh-cn_topic_0272459940_p1830312563304"></a><a name="zh-cn_topic_0272459940_p1830312563304"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p17303135683017"><a name="zh-cn_topic_0272459940_p17303135683017"></a><a name="zh-cn_topic_0272459940_p17303135683017"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row1540474517818"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p18404345483"><a name="zh-cn_topic_0272459940_p18404345483"></a><a name="zh-cn_topic_0272459940_p18404345483"></a>获取模板实例信息</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p54041045889"><a name="zh-cn_topic_0272459940_p54041045889"></a><a name="zh-cn_topic_0272459940_p54041045889"></a>GET /v2/releases/{name}</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1940419452082"><a name="zh-cn_topic_0272459940_p1940419452082"></a><a name="zh-cn_topic_0272459940_p1940419452082"></a>cce:release:get</p>
</td>
<td class="cellrowborder" valign="top" width="12.97%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p93031456183018"><a name="zh-cn_topic_0272459940_p93031456183018"></a><a name="zh-cn_topic_0272459940_p93031456183018"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p0303656123013"><a name="zh-cn_topic_0272459940_p0303656123013"></a><a name="zh-cn_topic_0272459940_p0303656123013"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row164043451489"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p6404645987"><a name="zh-cn_topic_0272459940_p6404645987"></a><a name="zh-cn_topic_0272459940_p6404645987"></a>删除模板实例</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p940418452814"><a name="zh-cn_topic_0272459940_p940418452814"></a><a name="zh-cn_topic_0272459940_p940418452814"></a>DELETE /v2/releases/{name}</p>
</td>
<td class="cellrowborder" valign="top" width="17.46%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p10404124514820"><a name="zh-cn_topic_0272459940_p10404124514820"></a><a name="zh-cn_topic_0272459940_p10404124514820"></a>cce:release:delete</p>
</td>
<td class="cellrowborder" valign="top" width="12.97%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p1330415673015"><a name="zh-cn_topic_0272459940_p1330415673015"></a><a name="zh-cn_topic_0272459940_p1330415673015"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p16304155614301"><a name="zh-cn_topic_0272459940_p16304155614301"></a><a name="zh-cn_topic_0272459940_p16304155614301"></a>√</p>
</td>
</tr>
</tbody>
</table>

**表 8**  Storage

<a name="zh-cn_topic_0272459940_table656017594127"></a>
<table><thead align="left"><tr id="zh-cn_topic_0272459940_row256025917122"><th class="cellrowborder" valign="top" width="18.47%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0272459940_p1256011592123"><a name="zh-cn_topic_0272459940_p1256011592123"></a><a name="zh-cn_topic_0272459940_p1256011592123"></a>权限</p>
</th>
<th class="cellrowborder" valign="top" width="32.519999999999996%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0272459940_p1156025918125"><a name="zh-cn_topic_0272459940_p1156025918125"></a><a name="zh-cn_topic_0272459940_p1156025918125"></a>对应API接口</p>
</th>
<th class="cellrowborder" valign="top" width="17.44%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0272459940_p95607594129"><a name="zh-cn_topic_0272459940_p95607594129"></a><a name="zh-cn_topic_0272459940_p95607594129"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="13%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0272459940_p1049953613110"><a name="zh-cn_topic_0272459940_p1049953613110"></a><a name="zh-cn_topic_0272459940_p1049953613110"></a>IAM项目(Project)</p>
</th>
<th class="cellrowborder" valign="top" width="18.57%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0272459940_p349912367314"><a name="zh-cn_topic_0272459940_p349912367314"></a><a name="zh-cn_topic_0272459940_p349912367314"></a>企业项目 (Enterprise Project)</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0272459940_row95611059181211"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p1356165916124"><a name="zh-cn_topic_0272459940_p1356165916124"></a><a name="zh-cn_topic_0272459940_p1356165916124"></a>创建PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" width="32.519999999999996%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p7561185981210"><a name="zh-cn_topic_0272459940_p7561185981210"></a><a name="zh-cn_topic_0272459940_p7561185981210"></a>POST /api/v1/namespaces/{namespace}/cloudpersistentvolumeclaims</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p10561659161214"><a name="zh-cn_topic_0272459940_p10561659161214"></a><a name="zh-cn_topic_0272459940_p10561659161214"></a>cce:storage:create</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p124999368316"><a name="zh-cn_topic_0272459940_p124999368316"></a><a name="zh-cn_topic_0272459940_p124999368316"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.57%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1849973663110"><a name="zh-cn_topic_0272459940_p1849973663110"></a><a name="zh-cn_topic_0272459940_p1849973663110"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row15561259191219"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p55611059181213"><a name="zh-cn_topic_0272459940_p55611059181213"></a><a name="zh-cn_topic_0272459940_p55611059181213"></a>删除PersistentVolumeClaim</p>
</td>
<td class="cellrowborder" valign="top" width="32.519999999999996%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p55611859101213"><a name="zh-cn_topic_0272459940_p55611859101213"></a><a name="zh-cn_topic_0272459940_p55611859101213"></a>DELETE /api/v1/namespaces/{namespace}/cloudpersistentvolumeclaims/{name}</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p056165916125"><a name="zh-cn_topic_0272459940_p056165916125"></a><a name="zh-cn_topic_0272459940_p056165916125"></a>cce:storage:delete</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p649953613310"><a name="zh-cn_topic_0272459940_p649953613310"></a><a name="zh-cn_topic_0272459940_p649953613310"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.57%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p144991536113117"><a name="zh-cn_topic_0272459940_p144991536113117"></a><a name="zh-cn_topic_0272459940_p144991536113117"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row2065421302"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p0694210019"><a name="zh-cn_topic_0272459940_p0694210019"></a><a name="zh-cn_topic_0272459940_p0694210019"></a>列出所有磁盘</p>
</td>
<td class="cellrowborder" valign="top" width="32.519999999999996%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p776421011"><a name="zh-cn_topic_0272459940_p776421011"></a><a name="zh-cn_topic_0272459940_p776421011"></a>GET /storage/api/v1/namespaces/{namespace}/listvolumes</p>
</td>
<td class="cellrowborder" valign="top" width="17.44%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p15714424010"><a name="zh-cn_topic_0272459940_p15714424010"></a><a name="zh-cn_topic_0272459940_p15714424010"></a>cce:storage:list</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p2711428010"><a name="zh-cn_topic_0272459940_p2711428010"></a><a name="zh-cn_topic_0272459940_p2711428010"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.57%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1679423018"><a name="zh-cn_topic_0272459940_p1679423018"></a><a name="zh-cn_topic_0272459940_p1679423018"></a>√</p>
</td>
</tr>
</tbody>
</table>

**表 9**  Addon

<a name="zh-cn_topic_0272459940_table19377213131"></a>
<table><thead align="left"><tr id="zh-cn_topic_0272459940_row1137711110131"><th class="cellrowborder" valign="top" width="18.47%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0272459940_p173771114132"><a name="zh-cn_topic_0272459940_p173771114132"></a><a name="zh-cn_topic_0272459940_p173771114132"></a>权限</p>
</th>
<th class="cellrowborder" valign="top" width="32.61%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0272459940_p237718111311"><a name="zh-cn_topic_0272459940_p237718111311"></a><a name="zh-cn_topic_0272459940_p237718111311"></a>对应API接口</p>
</th>
<th class="cellrowborder" valign="top" width="17.37%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0272459940_p15377161121311"><a name="zh-cn_topic_0272459940_p15377161121311"></a><a name="zh-cn_topic_0272459940_p15377161121311"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="13.059999999999999%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0272459940_p2089831883215"><a name="zh-cn_topic_0272459940_p2089831883215"></a><a name="zh-cn_topic_0272459940_p2089831883215"></a>IAM项目(Project)</p>
</th>
<th class="cellrowborder" valign="top" width="18.490000000000002%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0272459940_p12898218193213"><a name="zh-cn_topic_0272459940_p12898218193213"></a><a name="zh-cn_topic_0272459940_p12898218193213"></a>企业项目 (Enterprise Project)</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0272459940_row1379511136"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p123791214132"><a name="zh-cn_topic_0272459940_p123791214132"></a><a name="zh-cn_topic_0272459940_p123791214132"></a>创建插件实例</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p237913151314"><a name="zh-cn_topic_0272459940_p237913151314"></a><a name="zh-cn_topic_0272459940_p237913151314"></a>POST /api/v3/addons</p>
</td>
<td class="cellrowborder" valign="top" width="17.37%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p113791015130"><a name="zh-cn_topic_0272459940_p113791015130"></a><a name="zh-cn_topic_0272459940_p113791015130"></a>cce:addonInstance:create</p>
</td>
<td class="cellrowborder" valign="top" width="13.059999999999999%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p1489921863210"><a name="zh-cn_topic_0272459940_p1489921863210"></a><a name="zh-cn_topic_0272459940_p1489921863210"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p188999185326"><a name="zh-cn_topic_0272459940_p188999185326"></a><a name="zh-cn_topic_0272459940_p188999185326"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row33795131318"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p63799117138"><a name="zh-cn_topic_0272459940_p63799117138"></a><a name="zh-cn_topic_0272459940_p63799117138"></a>获取插件实例</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p23799181311"><a name="zh-cn_topic_0272459940_p23799181311"></a><a name="zh-cn_topic_0272459940_p23799181311"></a>GET /api/v3/addons/{id}?cluster_id={cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.37%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1137941191311"><a name="zh-cn_topic_0272459940_p1137941191311"></a><a name="zh-cn_topic_0272459940_p1137941191311"></a>cce:addonInstance:get</p>
</td>
<td class="cellrowborder" valign="top" width="13.059999999999999%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p489971843219"><a name="zh-cn_topic_0272459940_p489971843219"></a><a name="zh-cn_topic_0272459940_p489971843219"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p1899151833219"><a name="zh-cn_topic_0272459940_p1899151833219"></a><a name="zh-cn_topic_0272459940_p1899151833219"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row437941181310"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p14379121151317"><a name="zh-cn_topic_0272459940_p14379121151317"></a><a name="zh-cn_topic_0272459940_p14379121151317"></a>列出所有插件实例</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p1837941101318"><a name="zh-cn_topic_0272459940_p1837941101318"></a><a name="zh-cn_topic_0272459940_p1837941101318"></a>GET /api/v3/addons?cluster_id={cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.37%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p93791019139"><a name="zh-cn_topic_0272459940_p93791019139"></a><a name="zh-cn_topic_0272459940_p93791019139"></a>cce:addonInstance:list</p>
</td>
<td class="cellrowborder" valign="top" width="13.059999999999999%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p16899118163211"><a name="zh-cn_topic_0272459940_p16899118163211"></a><a name="zh-cn_topic_0272459940_p16899118163211"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p2899131813327"><a name="zh-cn_topic_0272459940_p2899131813327"></a><a name="zh-cn_topic_0272459940_p2899131813327"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row337911171317"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p838015110138"><a name="zh-cn_topic_0272459940_p838015110138"></a><a name="zh-cn_topic_0272459940_p838015110138"></a>删除插件实例</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p2038019115130"><a name="zh-cn_topic_0272459940_p2038019115130"></a><a name="zh-cn_topic_0272459940_p2038019115130"></a>DELETE /api/v3/addons/{id}?cluster_id={cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.37%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p133807118134"><a name="zh-cn_topic_0272459940_p133807118134"></a><a name="zh-cn_topic_0272459940_p133807118134"></a>cce:addonInstance:delete</p>
</td>
<td class="cellrowborder" valign="top" width="13.059999999999999%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p18454102753216"><a name="zh-cn_topic_0272459940_p18454102753216"></a><a name="zh-cn_topic_0272459940_p18454102753216"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p845442783213"><a name="zh-cn_topic_0272459940_p845442783213"></a><a name="zh-cn_topic_0272459940_p845442783213"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0272459940_row838015113136"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p103802016132"><a name="zh-cn_topic_0272459940_p103802016132"></a><a name="zh-cn_topic_0272459940_p103802016132"></a>更新升级插件实例</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p1738071131314"><a name="zh-cn_topic_0272459940_p1738071131314"></a><a name="zh-cn_topic_0272459940_p1738071131314"></a>PUT /api/v3/addons/{id}</p>
</td>
<td class="cellrowborder" valign="top" width="17.37%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p53801812138"><a name="zh-cn_topic_0272459940_p53801812138"></a><a name="zh-cn_topic_0272459940_p53801812138"></a>cce:addonInstance:update</p>
</td>
<td class="cellrowborder" valign="top" width="13.059999999999999%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p545422718321"><a name="zh-cn_topic_0272459940_p545422718321"></a><a name="zh-cn_topic_0272459940_p545422718321"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p16454102723217"><a name="zh-cn_topic_0272459940_p16454102723217"></a><a name="zh-cn_topic_0272459940_p16454102723217"></a>√</p>
</td>
</tr>
</tbody>
</table>

**表 10**  Quota

<a name="zh-cn_topic_0272459940_table1791821463611"></a>
<table><thead align="left"><tr id="zh-cn_topic_0272459940_row1891881493618"><th class="cellrowborder" valign="top" width="18.47%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0272459940_p1191810148361"><a name="zh-cn_topic_0272459940_p1191810148361"></a><a name="zh-cn_topic_0272459940_p1191810148361"></a>权限</p>
</th>
<th class="cellrowborder" valign="top" width="32.61%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0272459940_p1391831411365"><a name="zh-cn_topic_0272459940_p1391831411365"></a><a name="zh-cn_topic_0272459940_p1391831411365"></a>对应API接口</p>
</th>
<th class="cellrowborder" valign="top" width="17.37%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0272459940_p7919814103620"><a name="zh-cn_topic_0272459940_p7919814103620"></a><a name="zh-cn_topic_0272459940_p7919814103620"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="13.059999999999999%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0272459940_p12919161463617"><a name="zh-cn_topic_0272459940_p12919161463617"></a><a name="zh-cn_topic_0272459940_p12919161463617"></a>IAM项目(Project)</p>
</th>
<th class="cellrowborder" valign="top" width="18.490000000000002%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0272459940_p12919131463616"><a name="zh-cn_topic_0272459940_p12919131463616"></a><a name="zh-cn_topic_0272459940_p12919131463616"></a>企业项目 (Enterprise Project)</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0272459940_row3919181416368"><td class="cellrowborder" valign="top" width="18.47%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0272459940_p159197141361"><a name="zh-cn_topic_0272459940_p159197141361"></a><a name="zh-cn_topic_0272459940_p159197141361"></a>查询配额详情</p>
</td>
<td class="cellrowborder" valign="top" width="32.61%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0272459940_p591912144365"><a name="zh-cn_topic_0272459940_p591912144365"></a><a name="zh-cn_topic_0272459940_p591912144365"></a>GET /api/v3/projects/{project_id}/quotas</p>
</td>
<td class="cellrowborder" valign="top" width="17.37%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0272459940_p1691951418363"><a name="zh-cn_topic_0272459940_p1691951418363"></a><a name="zh-cn_topic_0272459940_p1691951418363"></a>cce:quota:get</p>
</td>
<td class="cellrowborder" valign="top" width="13.059999999999999%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0272459940_p391911453619"><a name="zh-cn_topic_0272459940_p391911453619"></a><a name="zh-cn_topic_0272459940_p391911453619"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.490000000000002%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0272459940_p6919214123619"><a name="zh-cn_topic_0272459940_p6919214123619"></a><a name="zh-cn_topic_0272459940_p6919214123619"></a>√</p>
</td>
</tr>
</tbody>
</table>

