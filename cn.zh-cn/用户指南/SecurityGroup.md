# SecurityGroup<a name="cce_01_0288"></a>

-   [约束与限制](#section21791218165310)
-   [通过界面创建](#section11870154492516)
-   [通过kubectl命令行创建](#section16951511152313)
-   [其他操作](#section682403717222)

为实现云原生网络2.0网络模式下，CCE对接VPC的SecurityGroup能力，华为云在kubernetes层面设计了一个以SecurityGroup为核心的新的crd资源对象。支持用户自定义特定需求的工作负载的安全组，并对外提供服务。

## 约束与限制<a name="section21791218165310"></a>

-   v1.19及以上的CCE Turbo集群支持此功能，v1.19以下版本CCE Turbo集群需要升级到v1.19及以上版本后才能启用此功能。
-   1个工作负载最多可绑定5个安全组。

## 通过界面创建<a name="section11870154492516"></a>

1.  单击CCE左侧导航栏的“资源管理 \> 网络管理”。
2.  在“SecurityGroup“页签下，在右上角选择框中点选要操作的集群，单击“添加SecurityGroup“。
3.  根据界面提示，配置参数， 具体如[表1](#table572616321913)所示。

    **表 1**  配置参数

    <a name="table572616321913"></a>
    <table><thead align="left"><tr id="row207274322093"><th class="cellrowborder" valign="top" width="27.49274927492749%" id="mcps1.2.4.1.1"><p id="p77276326911"><a name="p77276326911"></a><a name="p77276326911"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="38.943894389438945%" id="mcps1.2.4.1.2"><p id="p0728113212917"><a name="p0728113212917"></a><a name="p0728113212917"></a>描述</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.563356335633564%" id="mcps1.2.4.1.3"><p id="p1372820323916"><a name="p1372820323916"></a><a name="p1372820323916"></a>示例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1772883218911"><td class="cellrowborder" valign="top" width="27.49274927492749%" headers="mcps1.2.4.1.1 "><p id="p1972843218919"><a name="p1972843218919"></a><a name="p1972843218919"></a>SecurityGroup名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="38.943894389438945%" headers="mcps1.2.4.1.2 "><p id="p1272819324915"><a name="p1272819324915"></a><a name="p1272819324915"></a>输入SecurityGroup名称。</p>
    <p id="p4881951142411"><a name="p4881951142411"></a><a name="p4881951142411"></a>请输入4-63个字符，以小写字母开头，由小写字母、数字、连接符（-）组成，且不能以连接符（-）结尾。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.563356335633564%" headers="mcps1.2.4.1.3 "><p id="p972814326910"><a name="p972814326910"></a><a name="p972814326910"></a>security-group</p>
    </td>
    </tr>
    <tr id="row872812321194"><td class="cellrowborder" valign="top" width="27.49274927492749%" headers="mcps1.2.4.1.1 "><p id="p14728133219910"><a name="p14728133219910"></a><a name="p14728133219910"></a>集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="38.943894389438945%" headers="mcps1.2.4.1.2 "><p id="p372814324915"><a name="p372814324915"></a><a name="p372814324915"></a>选择集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.563356335633564%" headers="mcps1.2.4.1.3 "><p id="p2728832094"><a name="p2728832094"></a><a name="p2728832094"></a>cce-turbo</p>
    </td>
    </tr>
    <tr id="row1573293217917"><td class="cellrowborder" valign="top" width="27.49274927492749%" headers="mcps1.2.4.1.1 "><p id="p5732203215913"><a name="p5732203215913"></a><a name="p5732203215913"></a>命名空间</p>
    </td>
    <td class="cellrowborder" valign="top" width="38.943894389438945%" headers="mcps1.2.4.1.2 "><p id="p8732632390"><a name="p8732632390"></a><a name="p8732632390"></a>选择命名空间。如未创建，可单击“创建命名空间”。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.563356335633564%" headers="mcps1.2.4.1.3 "><p id="p573211323919"><a name="p573211323919"></a><a name="p573211323919"></a>default</p>
    </td>
    </tr>
    <tr id="row873219323913"><td class="cellrowborder" valign="top" width="27.49274927492749%" headers="mcps1.2.4.1.1 "><p id="p27320321598"><a name="p27320321598"></a><a name="p27320321598"></a>关联工作负载</p>
    </td>
    <td class="cellrowborder" valign="top" width="38.943894389438945%" headers="mcps1.2.4.1.2 "><p id="p1173273219910"><a name="p1173273219910"></a><a name="p1173273219910"></a>选择工作负载。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.563356335633564%" headers="mcps1.2.4.1.3 "><p id="p715010280425"><a name="p715010280425"></a><a name="p715010280425"></a>web-terminal</p>
    </td>
    </tr>
    <tr id="row18733153211911"><td class="cellrowborder" valign="top" width="27.49274927492749%" headers="mcps1.2.4.1.1 "><p id="p187338321199"><a name="p187338321199"></a><a name="p187338321199"></a>安全组</p>
    </td>
    <td class="cellrowborder" valign="top" width="38.943894389438945%" headers="mcps1.2.4.1.2 "><p id="p1328632118575"><a name="p1328632118575"></a><a name="p1328632118575"></a>安全组给选中的工作负载的弹性网卡提供访问策略，在下拉框中最多可以选择5条，安全组必选，不可缺省。</p>
    <p id="p147335320917"><a name="p147335320917"></a><a name="p147335320917"></a>如未创建，可单击“创建安全组”，完成创建后单击刷新按钮。</p>
    <div class="notice" id="note1159255716127"><a name="note1159255716127"></a><a name="note1159255716127"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><a name="ul1543718137385"></a><a name="ul1543718137385"></a><ul id="ul1543718137385"><li>最多可选择5个安全组。</li><li>鼠标悬浮在安全组名称上，可查看安全组的详细信息。</li><li>安全组的出方向需放通ICMP协议（用于容器网络可用性检查）</li></ul>
    </div></div>
    </td>
    <td class="cellrowborder" valign="top" width="33.563356335633564%" headers="mcps1.2.4.1.3 "><p id="p1973319321791"><a name="p1973319321791"></a><a name="p1973319321791"></a>hddjj-930-cce-node-f05td</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  参数配置后，单击“创建”。

    创建完成后页面将自动返回到SecurityGroup列表页，可以看到新添加的SecurityGroup已在列表中。


## 通过kubectl命令行创建<a name="section16951511152313"></a>

**前提条件**

请参见[通过kubectl或web-terminal插件操作CCE集群](通过kubectl或web-terminal插件操作CCE集群.md)配置kubectl命令，使弹性云服务器连接集群。

**操作步骤**

1.  登录已配置好kubectl命令的弹性云服务器。登录方法请参见[登录Linux弹性云服务器](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0013771089.html)。
2.  创建创建一个名为securitygroup-test.yaml的描述文件。其中，securitygroup-test.yaml为自定义名称。

    **vi securitygroup-test.yaml**

    例如，用户创建如下的SecurityGroup资源对象，给所有的app：db业务绑定上对应的已经存在的64566556-bd6f-48fb-b2c6-df8f44617953，5451f1b0-bd6f-48fb-b2c6-df8f44617953的两个安全组。示例如下：

    ```
    apiVersion: crd.yangtse.cni/v1
    kind: SecurityGroup
    metadata:
      name: user-security-group
      namespace: default
    spec:
      podSelector:
        matchLabels:
          app: db    
      securityGroups:
      - id: 64566556-bd6f-48fb-b2c6-df8f44617953
      - id: 5451f1b0-bd6f-48fb-b2c6-df8f44617953
    ```

    以上yaml参数说明如[表2](#table132326831016)。

    **表 2**  参数说明

    <a name="table132326831016"></a>
    <table><thead align="left"><tr id="row523318817104"><th class="cellrowborder" valign="top" width="36.75%" id="mcps1.2.4.1.1"><p id="p162344817100"><a name="p162344817100"></a><a name="p162344817100"></a>字段名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="47.25%" id="mcps1.2.4.1.2"><p id="p16234138161012"><a name="p16234138161012"></a><a name="p16234138161012"></a>字段说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="16%" id="mcps1.2.4.1.3"><p id="p102881159151016"><a name="p102881159151016"></a><a name="p102881159151016"></a>必选/可选</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row112346841018"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.4.1.1 "><p id="p182345811107"><a name="p182345811107"></a><a name="p182345811107"></a>apiVersion</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.25%" headers="mcps1.2.4.1.2 "><p id="p2023458141014"><a name="p2023458141014"></a><a name="p2023458141014"></a>表示API的版本号，版本号为crd.yangtse.cni/v1。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p6234158101019"><a name="p6234158101019"></a><a name="p6234158101019"></a>必选</p>
    </td>
    </tr>
    <tr id="row202347814100"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.4.1.1 "><p id="p172342815109"><a name="p172342815109"></a><a name="p172342815109"></a>kind</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.25%" headers="mcps1.2.4.1.2 "><p id="p142346871019"><a name="p142346871019"></a><a name="p142346871019"></a>创建的对象类别。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p2023416841019"><a name="p2023416841019"></a><a name="p2023416841019"></a>必选</p>
    </td>
    </tr>
    <tr id="row1459172931315"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.4.1.1 "><p id="p1659232941311"><a name="p1659232941311"></a><a name="p1659232941311"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.25%" headers="mcps1.2.4.1.2 "><p id="p165932298137"><a name="p165932298137"></a><a name="p165932298137"></a>资源对象的元数据定义。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p16593112941310"><a name="p16593112941310"></a><a name="p16593112941310"></a>必选</p>
    </td>
    </tr>
    <tr id="row33638545115"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.4.1.1 "><p id="p036575412114"><a name="p036575412114"></a><a name="p036575412114"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.25%" headers="mcps1.2.4.1.2 "><p id="p1036510541116"><a name="p1036510541116"></a><a name="p1036510541116"></a>SecurityGroup的名称。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p1936585415110"><a name="p1936585415110"></a><a name="p1936585415110"></a>必选</p>
    </td>
    </tr>
    <tr id="row126231712194217"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.4.1.1 "><p id="p1692614369427"><a name="p1692614369427"></a><a name="p1692614369427"></a>namespace</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.25%" headers="mcps1.2.4.1.2 "><p id="p7625512194216"><a name="p7625512194216"></a><a name="p7625512194216"></a>工作空间名称。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p142617117439"><a name="p142617117439"></a><a name="p142617117439"></a>必选</p>
    </td>
    </tr>
    <tr id="row52341382109"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.4.1.1 "><p id="p2234188171017"><a name="p2234188171017"></a><a name="p2234188171017"></a>Spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.25%" headers="mcps1.2.4.1.2 "><p id="p1023414811012"><a name="p1023414811012"></a><a name="p1023414811012"></a>用户对SecurityGroup的详细描述的主体部分都在spec中给出。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p92341186101"><a name="p92341186101"></a><a name="p92341186101"></a>必选</p>
    </td>
    </tr>
    <tr id="row29372135139"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.4.1.1 "><p id="p1493821315132"><a name="p1493821315132"></a><a name="p1493821315132"></a>podselector</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.25%" headers="mcps1.2.4.1.2 "><p id="p10938171341312"><a name="p10938171341312"></a><a name="p10938171341312"></a>定义SecurityGroup可管理的容器实例。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p5939181320135"><a name="p5939181320135"></a><a name="p5939181320135"></a>必选</p>
    </td>
    </tr>
    <tr id="row69398139139"><td class="cellrowborder" valign="top" width="36.75%" headers="mcps1.2.4.1.1 "><p id="p14452947144819"><a name="p14452947144819"></a><a name="p14452947144819"></a>SecurityGroups</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.25%" headers="mcps1.2.4.1.2 "><p id="p10939121391317"><a name="p10939121391317"></a><a name="p10939121391317"></a>id为安全组的ID。</p>
    </td>
    <td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.4.1.3 "><p id="p4939161321314"><a name="p4939161321314"></a><a name="p4939161321314"></a>必选</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  执行以下命令，创建SecurityGroup。

    **kubectl create -f securitygroup-test.yaml**

    回显如下表示已开始创建SecurityGroup

    ```
    securitygroup.crd.yangtse.cni/user-security-group created
    ```

4.  执行以下命令，查看SecurityGroup。

    **kubectl get sg**

    回显信息中有创建的SecurityGroup名称为user-security-group，表示SecurityGroup已创建成功。

    ```
    NAME                       POD-SELECTOR                      AGE
    all-no                     map[matchLabels:map[app:nginx]]   4h1m
    s001test                   map[matchLabels:map[app:nginx]]   19m
    user-security-group        map[matchLabels:map[app:nginx]]   2m9s
    ```


## 其他操作<a name="section682403717222"></a>

**表 3**  其他操作

<a name="table394616495249"></a>
<table><thead align="left"><tr id="row49471249162418"><th class="cellrowborder" valign="top" width="24.5%" id="mcps1.2.3.1.1"><p id="p189471749182410"><a name="p189471749182410"></a><a name="p189471749182410"></a>操作项</p>
</th>
<th class="cellrowborder" valign="top" width="75.5%" id="mcps1.2.3.1.2"><p id="p16947114913245"><a name="p16947114913245"></a><a name="p16947114913245"></a>操作步骤</p>
</th>
</tr>
</thead>
<tbody><tr id="row6139155142516"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p5140451132520"><a name="p5140451132520"></a><a name="p5140451132520"></a>删除</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><a name="ol1639531782718"></a><a name="ol1639531782718"></a><ol id="ol1639531782718"><li>单击CCE左侧导航栏的“资源管理 &gt; 网络管理”。</li><li>在<span class="uicontrol" id="uicontrol5155161022719"><a name="uicontrol5155161022719"></a><a name="uicontrol5155161022719"></a>“SecurityGroup”</span>页签下，勾选SecurityGroup名称。</li><li>单击“删除”，即可删除SecurityGroup。</li></ol>
</td>
</tr>
<tr id="row694712493245"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p89473498241"><a name="p89473498241"></a><a name="p89473498241"></a>更新</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><a name="ol5931555183617"></a><a name="ol5931555183617"></a><ol id="ol5931555183617"><li>单击CCE左侧导航栏的“资源管理 &gt; 网络管理”。</li><li>在<span class="uicontrol" id="uicontrol20931155593619"><a name="uicontrol20931155593619"></a><a name="uicontrol20931155593619"></a>“SecurityGroup”</span>页签下，单击SecurityGroup列表后的“更新”。<p id="p399219043815"><a name="p399219043815"></a><a name="p399219043815"></a>可更新安全组ID和工作负载。</p>
</li></ol>
</td>
</tr>
<tr id="row7947349202412"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p1594713497241"><a name="p1594713497241"></a><a name="p1594713497241"></a>查看YAML</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><a name="ol184959289353"></a><a name="ol184959289353"></a><ol id="ol184959289353"><li>单击CCE左侧导航栏的“资源管理 &gt; 网络管理”。</li><li>在<span class="uicontrol" id="uicontrol14496628153511"><a name="uicontrol14496628153511"></a><a name="uicontrol14496628153511"></a>“SecurityGroup”</span>页签下，单击SecurityGroup列表后的“查看YAML”。<p id="p367182203813"><a name="p367182203813"></a><a name="p367182203813"></a>可查看、复制和下载YAML文件。</p>
</li></ol>
</td>
</tr>
<tr id="row884419237424"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p784482354213"><a name="p784482354213"></a><a name="p784482354213"></a>查看事件</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><a name="ol2341203144310"></a><a name="ol2341203144310"></a><ol id="ol2341203144310"><li>单击CCE左侧导航栏的“资源管理 &gt; 网络管理”。</li><li>在<span class="uicontrol" id="uicontrol83411831114310"><a name="uicontrol83411831114310"></a><a name="uicontrol83411831114310"></a>“SecurityGroup”</span>页签下，单击“查看事件”。<p id="p16341103113432"><a name="p16341103113432"></a><a name="p16341103113432"></a>可查看事件信息。</p>
</li></ol>
</td>
</tr>
</tbody>
</table>

