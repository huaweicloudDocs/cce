# 创建普通任务\(Job\)<a name="cce_10_0150"></a>

## 操作场景<a name="section142417128434"></a>

普通任务是一次性运行的短任务，部署完成后即可执行。正常退出（exit 0）后，任务即执行完成。

普通任务是用来控制批处理型任务的资源对象。批处理业务与长期伺服业务（Deployment、Statefulset）的主要区别是：

批处理业务的运行有头有尾，而长期伺服业务在用户不停止的情况下永远运行。Job管理的Pod根据用户的设置把任务成功完成就自动退出了。成功完成的标志根据不同的spec.completions策略而不同，即：

-   单Pod型任务有一个Pod成功就标志完成。
-   定数成功型任务保证有N个任务全部成功。
-   工作队列型任务根据应用确认的全局成功而标志成功。

## 前提条件<a name="s50bf087555b1437aa249c1259138706c"></a>

已创建资源，具体操作请参见[创建节点](创建节点.md)。若已有集群和节点资源，无需重复操作。

## 通过控制台创建<a name="sb8a02965b2624dbbabab320046ca4973"></a>

1.  登录CCE控制台。
2.  单击集群名称进入集群，在左侧选择“工作负载“，在右上角单击“创建负载“。
3.  配置工作负载的信息。

    **基本信息**

    -   负载类型：选择任务Job。工作负载类型的介绍请参见[工作负载概述](工作负载概述.md)。
    -   负载名称：填写工作负载的名称。
    -   命名空间：选择工作负载的命名空间，默认为default。您可以单击后面的“创建命名空间“，命名空间的详细介绍请参见[创建命名空间](创建命名空间.md)。
    -   实例数量：填写实例的数量，也就是Pod的数量。
    -   容器运行时：CCE集群默认使用普通运行时，CCE Turbo集群可以使用普通运行时或安全运行时。具体区别请参见[安全容器与普通容器](安全容器与普通容器.md)。

    **容器配置**

    -   容器信息

        Pod中可以配置多个容器，您可以单击右侧“添加容器“为Pod配置多个容器。

        -   基本信息：[容器基本信息](容器基本信息.md)
        -   生命周期：[设置容器生命周期](设置容器生命周期.md)
        -   环境变量：[设置环境变量](设置环境变量.md)
        -   数据存储：[存储概述](存储概述.md)

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >负载实例数大于1时，不支持挂载云硬盘类型的存储。

        -   容器日志：[使用ICAgent采集容器日志](使用ICAgent采集容器日志.md)

    -   镜像访问凭证：用于访问镜像仓库的凭证，默认取值为default-secret，使用default-secret可访问SWR镜像仓库的镜像。default-secret详细说明请参见[default-secret](集群系统密钥说明.md#section11760122012591)。
    -   GPU显卡：默认为不限制。当集群中存在GPU节点时，工作负载实例可以调度到指定GPU显卡类型的节点上。

    **高级配置**

    -   标签与注解：[Pod标签与注解](Pod标签与注解.md)
    -   任务设置：
        -   并行数：任务负载执行过程中允许同时创建的最大实例数，并行数应不大于实例数。
        -   超时时间（秒）：当任务执行超出该时间时，任务将会被标识为执行失败，任务下的所有实例都会被删除。为空时表示不设置超时时间。

4.  单击右下角“创建工作负载“。

## 使用kubectl创建Job<a name="section450152719412"></a>

Job的配置参数如下所示。

-   spec.template格式与Pod相同。
-   RestartPolicy仅支持Never或OnFailure。
-   单个Pod时，默认Pod成功运行后Job即结束。
-   .spec.completions表示Job结束需要成功运行的Pod个数，默认为1。
-   .spec.parallelism表示并行运行的Pod的个数，默认为1。
-   spec.backoffLimit表示失败Pod的重试最大次数，超过这个次数不会继续重试。
-   .spec.activeDeadlineSeconds表示Pod运行时间，一旦达到这个时间，Job即其所有的Pod都会停止。且activeDeadlineSeconds优先级高于backoffLimit，即到达activeDeadlineSeconds的Job会忽略backoffLimit的设置。

根据.spec.completions和.spec.Parallelism的设置，可以将Job划分为以下几种类型。

**表 1**  任务类型

<a name="table19214202022111"></a>
<table><thead align="left"><tr id="row221419208210"><th class="cellrowborder" valign="top" width="21%" id="mcps1.2.4.1.1"><p id="p192146200219"><a name="p192146200219"></a><a name="p192146200219"></a>Job类型</p>
</th>
<th class="cellrowborder" valign="top" width="39%" id="mcps1.2.4.1.2"><p id="p0214720122118"><a name="p0214720122118"></a><a name="p0214720122118"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.4.1.3"><p id="p62149208219"><a name="p62149208219"></a><a name="p62149208219"></a>使用示例</p>
</th>
</tr>
</thead>
<tbody><tr id="row82141620152119"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p2050935122113"><a name="p2050935122113"></a><a name="p2050935122113"></a>一次性Job</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.4.1.2 "><p id="p124101856162110"><a name="p124101856162110"></a><a name="p124101856162110"></a>创建一个Pod直至其成功结束</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p58403110224"><a name="p58403110224"></a><a name="p58403110224"></a>数据库迁移</p>
</td>
</tr>
<tr id="row1221432052118"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p14512351132120"><a name="p14512351132120"></a><a name="p14512351132120"></a>固定结束次数的Job</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.4.1.2 "><p id="p741405662112"><a name="p741405662112"></a><a name="p741405662112"></a>依次创建一个Pod运行直至completions个成功结束</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p1284481192220"><a name="p1284481192220"></a><a name="p1284481192220"></a>处理工作队列的Pod</p>
</td>
</tr>
<tr id="row1321432013217"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p195159512216"><a name="p195159512216"></a><a name="p195159512216"></a>固定结束次数的并行Job</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.4.1.2 "><p id="p134205562218"><a name="p134205562218"></a><a name="p134205562218"></a>依次创建多个Pod运行直至completions个成功结束</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p3847512224"><a name="p3847512224"></a><a name="p3847512224"></a>多个Pod同时处理工作队列</p>
</td>
</tr>
<tr id="row8214192020217"><td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.4.1.1 "><p id="p115209514218"><a name="p115209514218"></a><a name="p115209514218"></a>并行Job</p>
</td>
<td class="cellrowborder" valign="top" width="39%" headers="mcps1.2.4.1.2 "><p id="p12424856142114"><a name="p12424856142114"></a><a name="p12424856142114"></a>创建一个或多个Pod直至有一个成功结束</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.4.1.3 "><p id="p285251142217"><a name="p285251142217"></a><a name="p285251142217"></a>多个Pod同时处理工作队列</p>
</td>
</tr>
</tbody>
</table>

以下是一个Job配置示例，保存在myjob.yaml中，其计算π到2000位并打印输出。

```
apiVersion: batch/v1
kind: Job
metadata:
  name: myjob
spec:
  completions: 50        # Job结束需要运行50个Pod，这个示例中就是打印π 50次
  parallelism: 5        # 并行5个Pod
  backoffLimit: 5        # 最多重试5次
  template:
    spec:
      containers:
      - name: pi
        image: perl
        command: ["perl",  "-Mbignum=bpi", "-wle", "print bpi(2000)"]
      restartPolicy: Never
```

**说明：**

-   apiVersion: batch/v1 是当前job的Version
-   kind: Job：指定当前资源的类型时Job
-   restartPolicy: Never：是指当前的重启策略。对于Job，只能设置为Never或者OnFailure。对于其他controller（比如Deployment）可以设置为Always。

**运行该任务，如下：**

1.  启动这个job。

    ```
    [root@k8s-master k8s]# kubectl apply -f myjob.yaml
    job.batch/myjob created
    ```

2.  查看这个job。

    **kubectl get job**

    ```
    [root@k8s-master k8s]# kubectl get job
    NAME    COMPLETIONS   DURATION   AGE
    myjob   50/50         23s        3m45s
    ```

    completions为 50/50 表示成功运行了这个job。

3.  查看pod的状态。

    **kubectl get pod**

    ```
    [root@k8s-master k8s]# kubectl get pod
    NAME          READY   STATUS      RESTARTS   AGE
    myjob-29qlw   0/1     Completed   0          4m5s
    ...
    ```

    状态为Completed表示这个job已经运行完成。

4.  查看这个pod的日志。

    **kubectl  logs**

    ```
    # kubectl logs myjob-29qlw
    3.1415926535897932384626433832795028841971693993751058209749445923078164062862089986280348253421170679821480865132823066470938446095505822317253594081284811174502841027019385211055596446229489549303819644288109756659334461284756482337867831652712019091456485669234603486104543266482133936072602491412737245870066063155881748815209209628292540917153643678925903600113305305488204665213841469519415116094330572703657595919530921861173819326117931051185480744623799627495673518857527248912279381830119491298336733624406566430860213949463952247371907021798609437027705392171762931767523846748184676694051320005681271452635608277857713427577896091736371787214684409012249534301465495853710507922796892589235420199561121290219608640344181598136297747713099605187072113499999983729780499510597317328160963185950244594553469083026425223082533446850352619311881710100031378387528865875332083814206171776691473035982534904287554687311595628638823537875937519577818577805321712268066130019278766111959092164201989380952572010654858632788659361533818279682303019520353018529689957736225994138912497217752834791315155748572424541506959508295331168617278558890750983817546374649393192550604009277016711390098488240128583616035637076601047101819429555961989467678374494482553797747268471040475346462080466842590694912933136770289891521047521620569660240580381501935112533824300355876402474964732639141992726042699227967823547816360093417216412199245863150302861829745557067498385054945885869269956909272107975093029553211653449872027559602364806654991198818347977535663698074265425278625518184175746728909777727938000816470600161452491921732172147723501414419735685481613611573525521334757418494684385233239073941433345477624168625189835694855620992192221842725502542568876717904946016534668049886272327917860857843838279679766814541009538837863609506800642251252051173929848960841284886269456042419652850222106611863067442786220391949450471237137869609563643719172874677646575739624138908658326459958133904780275901
    ```


## 相关操作<a name="s9bef0428158a4935b466ea150ccae961"></a>

普通任务创建完成后，您还可执行[表2](#t84075653e7544394939d13740fad0c20)中操作。

**表 2**  其他操作

<a name="t84075653e7544394939d13740fad0c20"></a>
<table><thead align="left"><tr id="r83819c2bd882441798d949cbee32fa6a"><th class="cellrowborder" valign="top" width="28.999999999999996%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0093532761_p92150167611"><a name="zh-cn_topic_0093532761_p92150167611"></a><a name="zh-cn_topic_0093532761_p92150167611"></a>操作</p>
</th>
<th class="cellrowborder" valign="top" width="71%" id="mcps1.2.3.1.2"><p id="a6b27fdd2dcc340f3baa6024edb5b3ae9"><a name="a6b27fdd2dcc340f3baa6024edb5b3ae9"></a><a name="a6b27fdd2dcc340f3baa6024edb5b3ae9"></a>操作说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row17717577287"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="p147711757162810"><a name="p147711757162810"></a><a name="p147711757162810"></a>编辑YAML</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><p id="p15771257142816"><a name="p15771257142816"></a><a name="p15771257142816"></a>单击任务名称后的<span class="uicontrol" id="uicontrol33801326152917"><a name="uicontrol33801326152917"></a><a name="uicontrol33801326152917"></a>“更多 &gt; 编辑YAML”</span>，可编辑当前任务对应的YAML文件。</p>
</td>
</tr>
<tr id="r27a8f438ed1d4cbba2ad07f7a08acb06"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="a1f9f2bb06252439c82b01c1d4bbb9ab0"><a name="a1f9f2bb06252439c82b01c1d4bbb9ab0"></a><a name="a1f9f2bb06252439c82b01c1d4bbb9ab0"></a>删除普通任务</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><a name="od5720c015360452491819af825ce5845"></a><a name="od5720c015360452491819af825ce5845"></a><ol id="od5720c015360452491819af825ce5845"><li>选择待删除的任务，单击操作列的<span class="uicontrol" id="u6db22cf752d54806adb4997e43ca3376"><a name="u6db22cf752d54806adb4997e43ca3376"></a><a name="u6db22cf752d54806adb4997e43ca3376"></a>“删除”</span>。</li><li>单击“确定”。<p id="aad27c67674e84e898611af0725bfe1cf"><a name="aad27c67674e84e898611af0725bfe1cf"></a><a name="aad27c67674e84e898611af0725bfe1cf"></a>任务删除后将无法恢复，请谨慎操作。</p>
</li></ol>
</td>
</tr>
</tbody>
</table>

