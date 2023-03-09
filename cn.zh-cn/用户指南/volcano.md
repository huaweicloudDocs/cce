# volcano<a name="cce_10_0193"></a>

## 插件简介<a name="section173631312185614"></a>

Volcano是一个基于Kubernetes的批处理平台，提供了机器学习、深度学习、生物信息学、基因组学及其他大数据应用所需要而Kubernetes当前缺失的一系列特性。

Volcano提供了高性能任务调度引擎、高性能异构芯片管理、高性能任务运行管理等通用计算能力，通过接入AI、大数据、基因、渲染等诸多行业计算框架服务终端用户。\(目前Volcano项目已经在Github开源\)

Volcano针对计算型应用提供了作业调度、作业管理、队列管理等多项功能，主要特性包括：

-   丰富的计算框架支持：通过CRD提供了批量计算任务的通用API，通过提供丰富的插件及作业生命周期高级管理，支持TensorFlow，MPI，Spark等计算框架容器化运行在Kubernetes上。
-   高级调度：面向批量计算、高性能计算场景提供丰富的高级调度能力，包括成组调度，优先级抢占、装箱、资源预留、任务拓扑关系等。
-   队列管理：支持分队列调度，提供队列优先级、多级队列等复杂任务调度能力。

项目开源地址：[https://github.com/volcano-sh/volcano](https://github.com/volcano-sh/volcano)

## 安装插件<a name="section564214328158"></a>

1.  登录CCE控制台，单击集群名称进入集群，单击左侧导航栏的“插件管理“，在右侧找到**Volcano**，单击“安装“。
2.  该插件可配置“单实例“、“高可用“或自定义规格。

    选择自定义时，volcano-controller和volcano-scheduler的建议值如下：

    -   小于100个节点，可使用默认配置，即CPU的申请值为500m，限制值为2000m；内存的申请值为500Mi，限制值为2000Mi。
    -   高于100个节点，每增加100个节点（10000个Pod），建议CPU的申请值增加500m，内存的申请值增加1000Mi；CPU的限制值建议比申请值多1500m，内存的限制值建议比申请值多1000Mi。

        **表 1**  volcano-controller和volcano-scheduler的建议值

        <a name="table4742829185912"></a>
        <table><thead align="left"><tr id="row07431329145911"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.1"><p id="p187511737155914"><a name="p187511737155914"></a><a name="p187511737155914"></a>节点/Pods规模</p>
        </th>
        <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.2"><p id="p10751123712590"><a name="p10751123712590"></a><a name="p10751123712590"></a>CPU Request(m)</p>
        </th>
        <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.3"><p id="p975163785912"><a name="p975163785912"></a><a name="p975163785912"></a>CPU Limit(m)</p>
        </th>
        <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.4"><p id="p7751437195915"><a name="p7751437195915"></a><a name="p7751437195915"></a>Memory Request(Mi)</p>
        </th>
        <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="p15751737185918"><a name="p15751737185918"></a><a name="p15751737185918"></a>Memory Limit(Mi)</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row107432029175915"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.1 "><p id="p17440104313599"><a name="p17440104313599"></a><a name="p17440104313599"></a>50/5k</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.2 "><p id="p144064365912"><a name="p144064365912"></a><a name="p144064365912"></a>500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="p1244034395911"><a name="p1244034395911"></a><a name="p1244034395911"></a>2000</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="p844034310592"><a name="p844034310592"></a><a name="p844034310592"></a>500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p4440124305918"><a name="p4440124305918"></a><a name="p4440124305918"></a>2000</p>
        </td>
        </tr>
        <tr id="row67438296598"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.1 "><p id="p144034313592"><a name="p144034313592"></a><a name="p144034313592"></a>100/1w</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.2 "><p id="p1344018435599"><a name="p1344018435599"></a><a name="p1344018435599"></a>1000</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="p24401243175910"><a name="p24401243175910"></a><a name="p24401243175910"></a>2500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="p134409438593"><a name="p134409438593"></a><a name="p134409438593"></a>1500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p544018434594"><a name="p544018434594"></a><a name="p544018434594"></a>2500</p>
        </td>
        </tr>
        <tr id="row1974318297599"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.1 "><p id="p8440843175911"><a name="p8440843175911"></a><a name="p8440843175911"></a>200/2w</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.2 "><p id="p16440104310592"><a name="p16440104310592"></a><a name="p16440104310592"></a>1500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="p124401439592"><a name="p124401439592"></a><a name="p124401439592"></a>3000</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="p11440843175915"><a name="p11440843175915"></a><a name="p11440843175915"></a>2500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p184403436591"><a name="p184403436591"></a><a name="p184403436591"></a>3500</p>
        </td>
        </tr>
        <tr id="row8743202985917"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.1 "><p id="p14401343115919"><a name="p14401343115919"></a><a name="p14401343115919"></a>300/3w</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.2 "><p id="p7440174320597"><a name="p7440174320597"></a><a name="p7440174320597"></a>2000</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="p7440184311599"><a name="p7440184311599"></a><a name="p7440184311599"></a>3500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="p74401543125911"><a name="p74401543125911"></a><a name="p74401543125911"></a>3500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p2440543155915"><a name="p2440543155915"></a><a name="p2440543155915"></a>4500</p>
        </td>
        </tr>
        <tr id="row67432029155914"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.1 "><p id="p2440204375918"><a name="p2440204375918"></a><a name="p2440204375918"></a>400/4w</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.2 "><p id="p114401043105917"><a name="p114401043105917"></a><a name="p114401043105917"></a>2500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="p14401543195915"><a name="p14401543195915"></a><a name="p14401543195915"></a>4000</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="p154401435593"><a name="p154401435593"></a><a name="p154401435593"></a>4500</p>
        </td>
        <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p10440164316595"><a name="p10440164316595"></a><a name="p10440164316595"></a>5500</p>
        </td>
        </tr>
        </tbody>
        </table>

3.  配置volcano默认调度器配置参数，详情请参见[表2](#table562185146)。

    ```
    ca_cert: ''
    default_scheduler_conf:
      actions: 'allocate, backfill'
      tiers:
        - plugins:
            - name: 'priority'
            - name: 'gang'
            - name: 'conformance'
        - plugins:
            - name: 'drf'
            - name: 'predicates'
            - name: 'nodeorder'
        - plugins:
            - name: 'cce-gpu-topology-predicate'
            - name: 'cce-gpu-topology-priority'
            - name: 'cce-gpu'
        - plugins:
            - name: 'nodelocalvolume'
            - name: 'nodeemptydirvolume'
            - name: 'nodeCSIscheduling'
            - name: 'networkresource'
    server_cert: ''
    server_key: ''
    ```

    **表 2**  Volcano插件配置参数说明

    <a name="table562185146"></a>
    <table><thead align="left"><tr id="row1161711510412"><th class="cellrowborder" valign="top" width="12.778722127787221%" id="mcps1.2.5.1.1"><p id="p1861712513416"><a name="p1861712513416"></a><a name="p1861712513416"></a>插件</p>
    </th>
    <th class="cellrowborder" valign="top" width="22.4977502249775%" id="mcps1.2.5.1.2"><p id="p56171511414"><a name="p56171511414"></a><a name="p56171511414"></a>功能</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.38666133386661%" id="mcps1.2.5.1.3"><p id="p19617157416"><a name="p19617157416"></a><a name="p19617157416"></a>参数说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="31.336866313368667%" id="mcps1.2.5.1.4"><p id="p13617195947"><a name="p13617195947"></a><a name="p13617195947"></a>用法演示</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row9618157412"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p06171553418"><a name="p06171553418"></a><a name="p06171553418"></a>binpack</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p136171657420"><a name="p136171657420"></a><a name="p136171657420"></a>将pod调度到资源使用较高的节点以减少资源碎片</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><a name="ul8870121613411"></a><a name="ul8870121613411"></a><ul id="ul8870121613411"><li>binpack.weight：binpack插件本身在所有插件打分中的权重</li><li>binpack.cpu：cpu资源在资源比重的比例，默认是1</li><li>binpack.memory：memory资源在所有资源中的比例，默认是1</li><li>binpack.resources：</li></ul>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><pre class="screen" id="screen4192214191819"><a name="screen4192214191819"></a><a name="screen4192214191819"></a>- plugins:
      - name: binpack
        arguments:
          binpack.weight: 10
          binpack.cpu: 1
          binpack.memory: 1
          binpack.resources: nvidia.com/gpu, example.com/foo
          binpack.resources.nvidia.com/gpu: 2
          binpack.resources.example.com/foo: 3</pre>
    </td>
    </tr>
    <tr id="row13618357412"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p86181651146"><a name="p86181651146"></a><a name="p86181651146"></a>conformance</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p16188516417"><a name="p16188516417"></a><a name="p16188516417"></a>跳过关键Pod，比如在kube-system命名空间的Pod，防止这些Pod被驱逐</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p86181515412"><a name="p86181515412"></a><a name="p86181515412"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p16618851346"><a name="p16618851346"></a><a name="p16618851346"></a>-</p>
    </td>
    </tr>
    <tr id="row1761812517413"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p161811515419"><a name="p161811515419"></a><a name="p161811515419"></a>gang</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p7618125943"><a name="p7618125943"></a><a name="p7618125943"></a>将一组pod看做一个整体去分配资源</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p16181759415"><a name="p16181759415"></a><a name="p16181759415"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p196181751145"><a name="p196181751145"></a><a name="p196181751145"></a>-</p>
    </td>
    </tr>
    <tr id="row1661811514419"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p1361814510419"><a name="p1361814510419"></a><a name="p1361814510419"></a>priority</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p96181251748"><a name="p96181251748"></a><a name="p96181251748"></a>使用用户自定义负载的优先级进行调度</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p76181151248"><a name="p76181151248"></a><a name="p76181151248"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p14618253419"><a name="p14618253419"></a><a name="p14618253419"></a>-</p>
    </td>
    </tr>
    <tr id="row5618351648"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p16181751412"><a name="p16181751412"></a><a name="p16181751412"></a>overcommit</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p176181757410"><a name="p176181757410"></a><a name="p176181757410"></a>将集群的资源放到一定倍数后调度，提高负载入队效率。负载都是deployment的时候，建议去掉此插件或者设置扩大因子为2.0。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p146188516411"><a name="p146188516411"></a><a name="p146188516411"></a>overcommit-factor: 扩大因子，默认是1.2</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><pre class="screen" id="screen1943123716187"><a name="screen1943123716187"></a><a name="screen1943123716187"></a>- plugins:
      - name: overcommit
        arguments:
          overcommit-factor: 2.0</pre>
    </td>
    </tr>
    <tr id="row10618105849"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p9618952417"><a name="p9618952417"></a><a name="p9618952417"></a>drf</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p4618652418"><a name="p4618652418"></a><a name="p4618652418"></a>根据作业使用的主导资源份额进行调度，用的越少的优先</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p46181351549"><a name="p46181351549"></a><a name="p46181351549"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p11618355418"><a name="p11618355418"></a><a name="p11618355418"></a>-</p>
    </td>
    </tr>
    <tr id="row2618251544"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p5618551445"><a name="p5618551445"></a><a name="p5618551445"></a>predicates</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p166184512417"><a name="p166184512417"></a><a name="p166184512417"></a>预选节点的常用算法，包括节点亲和，pod亲和，污点容忍，node ports重复，volume limits，volume zone匹配等一系列基础算法</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p18618105642"><a name="p18618105642"></a><a name="p18618105642"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p12618659419"><a name="p12618659419"></a><a name="p12618659419"></a>-</p>
    </td>
    </tr>
    <tr id="row14619155343"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p7619151411"><a name="p7619151411"></a><a name="p7619151411"></a>nodeorder</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p361975849"><a name="p361975849"></a><a name="p361975849"></a>优选节点的常用算法</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><a name="ul1127020488717"></a><a name="ul1127020488717"></a><ul id="ul1127020488717"><li>nodeaffinity.weight：节点亲和性优先调度，默认值是1</li><li>podaffinity.weight：pod亲和性优先调度，默认值是1</li><li>leastrequested.weight：资源分配最少的的节点优先，默认值是1</li><li>balancedresource.weight：node上面的不同资源分配平衡的优先，默认值是1</li><li>mostrequested.weight：资源分配最多的的节点优先，默认值是0</li><li>tainttoleration.weight：污点容忍高的优先调度，默认值是1</li><li>imagelocality.weight：node上面有pod需要镜像的优先调度，默认值是1</li><li>selectorspread.weight: 把pod均匀调度到不同的节点上，默认值是0</li><li>volumebinding.weight: local pv延迟绑定调度，默认值是1</li><li>podtopologyspread.weight: pod拓扑调度，默认值是2</li></ul>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><pre class="screen" id="screen1171374419183"><a name="screen1171374419183"></a><a name="screen1171374419183"></a>- plugins:
      - name: nodeorder
        arguments:
          leastrequested.weight: 1
          mostrequested.weight: 0
          nodeaffinity.weight: 1
          podaffinity.weight: 1
          balancedresource.weight: 1
          tainttoleration.weight: 1
          imagelocality.weight: 1
          volumebinding.weight: 1
          podtopologyspread.weight: 2</pre>
    </td>
    </tr>
    <tr id="row156191958412"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p17619551441"><a name="p17619551441"></a><a name="p17619551441"></a>cce-gpu-topology-predicate</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p176191252412"><a name="p176191252412"></a><a name="p176191252412"></a>GPU拓扑调度预选算法</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p161965649"><a name="p161965649"></a><a name="p161965649"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p10619115447"><a name="p10619115447"></a><a name="p10619115447"></a>-</p>
    </td>
    </tr>
    <tr id="row10619851748"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p11619151648"><a name="p11619151648"></a><a name="p11619151648"></a>cce-gpu-topology-priority</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p161925843"><a name="p161925843"></a><a name="p161925843"></a>GPU拓扑调度优选算法</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p10619752413"><a name="p10619752413"></a><a name="p10619752413"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p19619185844"><a name="p19619185844"></a><a name="p19619185844"></a>-</p>
    </td>
    </tr>
    <tr id="row146201351747"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p11619851345"><a name="p11619851345"></a><a name="p11619851345"></a>cce-gpu</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p56191451643"><a name="p56191451643"></a><a name="p56191451643"></a>结合CCE的GPU插件支持GPU资源分配，支持小数GPU配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p3619185643"><a name="p3619185643"></a><a name="p3619185643"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p136201553415"><a name="p136201553415"></a><a name="p136201553415"></a>-</p>
    </td>
    </tr>
    <tr id="row96201451643"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p2620175142"><a name="p2620175142"></a><a name="p2620175142"></a>numaaware</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p1062055244"><a name="p1062055244"></a><a name="p1062055244"></a>numa拓扑调度</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p6620552412"><a name="p6620552412"></a><a name="p6620552412"></a>weight: 插件的权重</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p3620135947"><a name="p3620135947"></a><a name="p3620135947"></a>-</p>
    </td>
    </tr>
    <tr id="row5620125141"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p18620251413"><a name="p18620251413"></a><a name="p18620251413"></a>networkresource</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p17620651046"><a name="p17620651046"></a><a name="p17620651046"></a>支持预选过滤ENI需求节点，参数由CCE传递，不需要手动配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p1762035945"><a name="p1762035945"></a><a name="p1762035945"></a>NetworkType: 网络类型（eni或者vpc-router类型）</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p106208519410"><a name="p106208519410"></a><a name="p106208519410"></a>-</p>
    </td>
    </tr>
    <tr id="row1562017510417"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p1762035443"><a name="p1762035443"></a><a name="p1762035443"></a>nodelocalvolume</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p66201557413"><a name="p66201557413"></a><a name="p66201557413"></a>支持预选过滤不符合local volume需求节点</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p7620357412"><a name="p7620357412"></a><a name="p7620357412"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p116203518416"><a name="p116203518416"></a><a name="p116203518416"></a>-</p>
    </td>
    </tr>
    <tr id="row86211951949"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p0621145648"><a name="p0621145648"></a><a name="p0621145648"></a>nodeemptydirvolume</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p186219515411"><a name="p186219515411"></a><a name="p186219515411"></a>支持预选过滤不符合emptydir需求节点</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p12621351147"><a name="p12621351147"></a><a name="p12621351147"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p106211151845"><a name="p106211151845"></a><a name="p106211151845"></a>-</p>
    </td>
    </tr>
    <tr id="row15621957412"><td class="cellrowborder" valign="top" width="12.778722127787221%" headers="mcps1.2.5.1.1 "><p id="p126218515417"><a name="p126218515417"></a><a name="p126218515417"></a>nodeCSIscheduling</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.4977502249775%" headers="mcps1.2.5.1.2 "><p id="p46211852047"><a name="p46211852047"></a><a name="p46211852047"></a>支持预选过滤everest组件异常节点</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.38666133386661%" headers="mcps1.2.5.1.3 "><p id="p12621105844"><a name="p12621105844"></a><a name="p12621105844"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="31.336866313368667%" headers="mcps1.2.5.1.4 "><p id="p362113515411"><a name="p362113515411"></a><a name="p362113515411"></a>-</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“安装“。

## 在控制台中修改volcano-scheduler配置<a name="section03891044143310"></a>

Volcano允许用户在安装，升级，编辑时，编写Volcano调度器配置信息，并将配置内容同步到volcano-scheduler-configmap里。

当前小节介绍如何使用自定义配置，以便用户让volcano-scheduler能更适合自己的场景。

>![](public_sys-resources/icon-note.gif) **说明：** 
>仅Volcano 1.7.1及以上版本支持该功能。在新版插件界面上合并了原plugins.eas\_service和resource\_exporter\_enable等选项，以新选项default\_scheduler\_conf代替。

您可登录CCE控制台，单击集群名称进入集群，单击左侧导航栏的“插件管理“，在右侧找到**Volcano**，单击“安装“或“升级“，并在“参数配置“中设置Volcano调度器配置参数。

-   使用resource\_exporter配置，示例如下：

    ```
    {
        "ca_cert": "",
        "default_scheduler_conf": {
            "actions": "allocate, backfill",
            "tiers": [
                {
                    "plugins": [
                        {
                            "name": "priority"
                        },
                        {
                            "name": "gang"
                        },
                        {
                            "name": "conformance"
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "drf"
                        },
                        {
                            "name": "predicates"
                        },
                        {
                            "name": "nodeorder"
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "cce-gpu-topology-predicate"
                        },
                        {
                            "name": "cce-gpu-topology-priority"
                        },
                        {
                            "name": "cce-gpu"
                        },
                        {
                            "name": "numa-aware" # add this also enable resource_exporter
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "nodelocalvolume"
                        },
                        {
                            "name": "nodeemptydirvolume"
                        },
                        {
                            "name": "nodeCSIscheduling"
                        },
                        {
                            "name": "networkresource"
                        }
                    ]
                }
            ]
        },
        "server_cert": "",
        "server_key": ""
    }
    ```

    开启后可以同时使用volcano-scheduler的numa-aware插件功能和resource\_exporter功能。


-   使用eas\_service配置，示例如下：

    ```
    {
        "ca_cert": "",
        "default_scheduler_conf": {
            "actions": "allocate, backfill",
            "tiers": [
                {
                    "plugins": [
                        {
                            "name": "priority"
                        },
                        {
                            "name": "gang"
                        },
                        {
                            "name": "conformance"
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "drf"
                        },
                        {
                            "name": "predicates"
                        },
                        {
                            "name": "nodeorder"
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "cce-gpu-topology-predicate"
                        },
                        {
                            "name": "cce-gpu-topology-priority"
                        },
                        {
                            "name": "cce-gpu"
                        },
                        {
                            "name": "eas",
                            "custom": {
                                "availability_zone_id": "",
                                "driver_id": "",
                                "endpoint": "",
                                "flavor_id": "",
                                "network_type": "",
                                "network_virtual_subnet_id": "",
                                "pool_id": "",
                                "project_id": "",
                                "secret_name": "eas-service-secret"
                            }
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "nodelocalvolume"
                        },
                        {
                            "name": "nodeemptydirvolume"
                        },
                        {
                            "name": "nodeCSIscheduling"
                        },
                        {
                            "name": "networkresource"
                        }
                    ]
                }
            ]
        },
        "server_cert": "",
        "server_key": ""
    }
    ```

-   使用ief配置，示例如下：

    ```
    {
        "ca_cert": "",
        "default_scheduler_conf": {
            "actions": "allocate, backfill",
            "tiers": [
                {
                    "plugins": [
                        {
                            "name": "priority"
                        },
                        {
                            "name": "gang"
                        },
                        {
                            "name": "conformance"
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "drf"
                        },
                        {
                            "name": "predicates"
                        },
                        {
                            "name": "nodeorder"
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "cce-gpu-topology-predicate"
                        },
                        {
                            "name": "cce-gpu-topology-priority"
                        },
                        {
                            "name": "cce-gpu"
                        },
                        {
                            "name": "ief",
                            "enableBestNode": true
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "nodelocalvolume"
                        },
                        {
                            "name": "nodeemptydirvolume"
                        },
                        {
                            "name": "nodeCSIscheduling"
                        },
                        {
                            "name": "networkresource"
                        }
                    ]
                }
            ]
        },
        "server_cert": "",
        "server_key": ""
    }
    ```


## 保留原volcano-scheduler-configmap配置<a name="section101061845325"></a>

假如在某场景下希望插件升级后时沿用原配置，可参考以下步骤：

1.  查看原volcano-scheduler-configmap配置，并备份。

    示例如下：

    ```
    # kubectl edit cm volcano-scheduler-configmap -n kube-system
    apiVersion: v1
    data:
      default-scheduler.conf: |-
        actions: "enqueue, allocate, backfill"
        tiers:
        - plugins:
          - name: priority
          - name: gang
          - name: conformance
        - plugins:
          - name: drf
          - name: predicates
          - name: nodeorder
          - name: binpack
            arguments:
              binpack.cpu: 100
              binpack.weight: 10
              binpack.resources: nvidia.com/gpu
              binpack.resources.nvidia.com/gpu: 10000
        - plugins:
          - name: cce-gpu-topology-predicate
          - name: cce-gpu-topology-priority
          - name: cce-gpu
        - plugins:
          - name: nodelocalvolume
          - name: nodeemptydirvolume
          - name: nodeCSIscheduling
          - name: networkresource
    ```

2.  在控制台“参数配置“中填写自定义修改的内容：

    ```
    {
        "ca_cert": "",
        "default_scheduler_conf": {
            "actions": "enqueue, allocate, backfill",
            "tiers": [
                {
                    "plugins": [
                        {
                            "name": "priority"
                        },
                        {
                            "name": "gang"
                        },
                        {
                            "name": "conformance"
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "drf"
                        },
                        {
                            "name": "predicates"
                        },
                        {
                            "name": "nodeorder"
                        },
                        {
                            "name": "binpack",
                            "arguments": {
                                "binpack.cpu": 100,
                                "binpack.weight": 10,
                                "binpack.resources": "nvidia.com/gpu",
                                "binpack.resources.nvidia.com/gpu": 10000
                            }
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "cce-gpu-topology-predicate"
                        },
                        {
                            "name": "cce-gpu-topology-priority"
                        },
                        {
                            "name": "cce-gpu"
                        }
                    ]
                },
                {
                    "plugins": [
                        {
                            "name": "nodelocalvolume"
                        },
                        {
                            "name": "nodeemptydirvolume"
                        },
                        {
                            "name": "nodeCSIscheduling"
                        },
                        {
                            "name": "networkresource"
                        }
                    ]
                }
            ]
        },
        "server_cert": "",
        "server_key": ""
    }
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >使用该功能时会覆盖原volcano-scheduler-configmap中内容，所以升级时务必检查是否在volcano-scheduler-configmap做过修改。如果是，需要把修改内容同步到升级界面里。


## 相关操作<a name="section715510208618"></a>

-   [在线离线作业混合部署](在线离线作业混合部署.md)
-   [NUMA亲和性调度](NUMA亲和性调度.md)

## Volcano 1.0.0版本升级说明<a name="section1363753011313"></a>

Volcano 1.0.0版本与后续版本不兼容，不支持在控制台升级。如想使用新版本Volcano插件，需要先卸载1.0.0版本，然后再在控制台安装新版本。

执行如下命令可以卸载Volcano。

**kubectl  delete  crd  jobs.batch.volcano.sh**

**kubectl  delete  crd commands.bus.volcano.sh**

## 版本记录<a name="section183121449435"></a>

**表 3**  CCE插件版本记录

<a name="table88489551792"></a>
<table><thead align="left"><tr id="row139251455994"><th class="cellrowborder" valign="top" width="37.50531236719082%" id="mcps1.2.3.1.1"><p id="p13601510205420"><a name="p13601510205420"></a><a name="p13601510205420"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="62.494687632809175%" id="mcps1.2.3.1.2"><p id="p156011107542"><a name="p156011107542"></a><a name="p156011107542"></a>支持的集群版本</p>
</th>
</tr>
</thead>
<tbody><tr id="row328716461974"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p132879461770"><a name="p132879461770"></a><a name="p132879461770"></a>1.7.1</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p1628719467714"><a name="p1628719467714"></a><a name="p1628719467714"></a>/v1.19.16.*|v1.21.*|v1.23.*|v1.25.*/</p>
</td>
</tr>
<tr id="row8757710175517"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p860211610418"><a name="p860211610418"></a><a name="p860211610418"></a>1.6.5</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p12592415517"><a name="p12592415517"></a><a name="p12592415517"></a>/v1.19.*|v1.21.*|v1.23.*/</p>
</td>
</tr>
<tr id="row723201855819"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p13603269412"><a name="p13603269412"></a><a name="p13603269412"></a>1.4.2</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p14167755105513"><a name="p14167755105513"></a><a name="p14167755105513"></a>/v1.15.*|v1.17.*|v1.19.*|v1.21.*/</p>
</td>
</tr>
<tr id="row1331711107"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p19603196340"><a name="p19603196340"></a><a name="p19603196340"></a>1.3.3</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p11196621115612"><a name="p11196621115612"></a><a name="p11196621115612"></a>/v1.15.*|v1.17.*|v1.19.*/</p>
</td>
</tr>
<tr id="row97371611105"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p1960306444"><a name="p1960306444"></a><a name="p1960306444"></a>1.3.1</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p1958984265614"><a name="p1958984265614"></a><a name="p1958984265614"></a>/v1.15.*|v1.17.*|v1.19.*/</p>
</td>
</tr>
<tr id="row1387891111011"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p14604164414"><a name="p14604164414"></a><a name="p14604164414"></a>1.2.5</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p19195155625619"><a name="p19195155625619"></a><a name="p19195155625619"></a>/v1.15.*|v1.17.*|v1.19.*/</p>
</td>
</tr>
<tr id="row108141216015"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p176041361840"><a name="p176041361840"></a><a name="p176041361840"></a>1.2.3</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p9199185614563"><a name="p9199185614563"></a><a name="p9199185614563"></a>/v1.15.*|v1.17.*|v1.19.*/</p>
</td>
</tr>
</tbody>
</table>

