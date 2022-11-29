# 创建定时任务\(CronJob\)<a name="cce_10_0151"></a>

## 操作场景<a name="section6515233144317"></a>

定时任务是按照指定时间周期运行的短任务。使用场景为在某个固定时间点，为所有运行中的节点做时间同步。

定时任务是基于时间的Job，就类似于Linux系统的crontab，在指定的时间周期运行指定的Job，即：

-   在给定时间点只运行一次。
-   在给定时间点周期性地运行。

CronJob的典型用法如下所示：

-   在给定的时间点调度Job运行。
-   创建周期性运行的Job，例如数据库备份、发送邮件。

## 前提条件<a name="s50bf087555b1437aa249c1259138706c"></a>

已创建资源，具体操作请参见[创建节点](创建节点.md)。

## 通过控制台创建<a name="section345135735520"></a>

1.  登录CCE控制台。
2.  进入集群，在左侧选择“工作负载“，在右上角单击“创建负载“。
3.  配置工作负载的信息。

    **基本信息**

    -   负载类型：选择定时任务CronJob。工作负载类型的介绍请参见[工作负载概述](工作负载概述.md)。
    -   负载名称：填写工作负载的名称。
    -   命名空间：选择工作负载的命名空间，默认为default。您可以单击后面的“创建命名空间“，命名空间的详细介绍请参见[创建命名空间](创建命名空间.md)。
    -   容器运行时：CCE集群默认使用普通运行时，CCE Turbo集群可以使用普通运行时或安全运行时。具体区别请参见[安全容器与普通容器](安全容器与普通容器.md)。

    **容器配置**

    -   容器信息

        Pod中可以配置多个容器，您可以单击右侧“添加容器“为Pod配置多个容器。

        -   基本信息：[容器基本信息](容器基本信息.md)
        -   生命周期：[设置容器生命周期](设置容器生命周期.md)
        -   环境变量：[设置环境变量](设置环境变量.md)
        -   容器日志：[容器日志](容器日志.md)

    -   镜像访问凭证：用于访问镜像仓库的凭证，默认取值为default-secret，使用default-secret可访问SWR镜像仓库的镜像。default-secret详细说明请参见[default-secret](集群系统密钥说明.md#section11760122012591)。
    -   GPU显卡：默认为不限制。当集群中存在GPU节点时，工作负载实例可以调度到指定GPU显卡类型的节点上。

    **定时规则**

    -   并发策略：支持如下三种模式。
        -   Forbid：在前一个任务未完成时，不创建新任务。
        -   Allow：定时任务不断新建Job，会抢占集群资源。
        -   Replace：已到新任务创建时间点，但前一个任务还未完成，新的任务会取代前一个任务。

    -   定时规则：指定新建定时任务在何时执行，YAML中的定时规则通过CRON表达式实现。

        -   以固定周期执行定时任务，支持的周期单位为分钟、小时、日、月。例如，每30分钟执行一次任务，对应的CRON表达式为“\*/30 \* \* \* \*“，执行时间将从单位范围内的0值开始计算，如**00:00:00**、**00:30:00**、**01:00:00**、**...**。
        -   以固定时间（按月）执行定时任务。例如，在每个月1日的0时0分执行任务，对应的CRON表达式为“0 0 1 \*/1 \*“，执行时间为**\*\*\*\*-01-01 00:00:00**、**\*\*\*\*-02-01 00:00:00**、**...**。
        -   以固定时间（按周）执行定时任务。例如，在每周一的0时0分执行任务，对应的CRON表达式为“0 0 \* \* 1“，执行时间为**\*\*\*\*-\*\*-01 周一 00:00:00**、**\*\*\*\*-\*\*-08 周一 00:00:00**、**...**。
        -   自定义CRON表达式：关于CRON表达式的用法，可参考[CRON](https://en.wikipedia.org/wiki/Cron)。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >-   以固定时间（按月）执行定时任务时，在某月的天数不存在的情况下，任务将不会在该月执行。例如设置天数为30，而2月份没有30号，任务将跳过该月份，在3月30号继续执行。
        >-   由于CRON表达式的定义，这里的固定周期并非严格意义的周期。将从0开始按周期对其时间单位范围（例如单位为分钟时，则范围为0\~59）进行划分，无法整除时最后一个周期会被重置。因此仅在周期能够平均划分其时间单位范围时，才能表示准确的周期。
        >    举个例子，周期单位为小时，因为“/2、/3、/4、/6、/8和/12“可将24小时整除，所以可以表示准确的周期；而使用其他周期时，在新的一天开始时，最后一个周期将会被重置。比如CRON式为“\* \*/12 \* \* \*“时为准确的周期，每天的执行时间为**00:00:00**和**12:00:00**；而CRON式为“\* \*/13 \* \* \*“时，每天的执行时间为**00:00:00**和**13:00:00**，在第二天0时，虽然没到13个小时的周期还是会被刷新。

    -   任务记录：可以设置保留执行成功或执行失败的任务个数，设置为0表示不保留。

    **高级配置**

    -   标签与注解：[Pod标签与注解](Pod标签与注解.md)

4.  单击右下角“创建工作负载“。

## 使用kubectl创建CronJob<a name="section13519162224919"></a>

CronJob的配置参数如下所示：

-   .spec.schedule指定任务运行时间与周期，参数格式请参见[Cron](https://kubernetes.io/zh-cn/docs/concepts/workloads/controllers/cron-jobs/#cron-schedule-syntax)，例如“0 \* \* \* \* “或“@hourly“。
-   .spec.jobTemplate指定需要运行的任务，格式与[使用kubectl创建Job](创建普通任务(Job).md#section450152719412)相同。
-   .spec.startingDeadlineSeconds指定任务开始的截止期限。
-   .spec.concurrencyPolicy指定任务的并发策略，支持Allow、Forbid和Replace三个选项。
    -   Allow（默认）：允许并发运行 Job。
    -   Forbid：禁止并发运行，如果前一个还没有完成，则直接跳过下一个。
    -   Replace：取消当前正在运行的Job，用一个新的来替换。


下面是一个CronJob的示例，保存在cronjob.yaml文件中。

```
apiVersion: batch/v1beta1
kind: CronJob
metadata:
  name: hello
spec:
  schedule: "*/1 * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: hello
            image: busybox
            args:
            - /bin/sh
            - -c
            - date; echo Hello from the Kubernetes cluster
          restartPolicy: OnFailure
```

**运行该任务，如下：**

1.  创建CronJob。

    **kubectl create -f cronjob.yaml**

    命令行终端显示如下信息：

    ```
    cronjob.batch/hello created
    ```

2.  执行如下命令，查看执行情况。

    **kubectl get cronjob**

    ```
    NAME      SCHEDULE      SUSPEND   ACTIVE    LAST SCHEDULE   AGE
    hello     */1 * * * *   False     0         <none>          9s
    ```

    **kubectl get jobs**

    ```
    NAME               COMPLETIONS   DURATION   AGE
    hello-1597387980   1/1           27s        45s
    ```

    **kubectl get pod**

    ```
    NAME                           READY     STATUS      RESTARTS   AGE
    hello-1597387980-tjv8f         0/1       Completed   0          114s
    hello-1597388040-lckg9         0/1       Completed   0          39s
    ```

    **kubectl logs hello-1597387980-tjv8f**

    ```
    Fri Aug 14 06:56:31 UTC 2020
    Hello from the Kubernetes cluster
    ```

    **kubectl delete cronjob hello**

    ```
    cronjob.batch "hello" deleted
    ```

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >删除CronJob时，对应的普通任务及相关的Pod都会被删除。


## 相关操作<a name="s28175da725cf46d49a4cfca59155a5d2"></a>

定时任务创建完成后，您还可执行[表1](#t6d520710097a4ee098eae42bcb508608)中操作。

**表 1**  其他操作

<a name="t6d520710097a4ee098eae42bcb508608"></a>
<table><thead align="left"><tr id="r8d59bf3aa5394e84ae626a36c585013d"><th class="cellrowborder" valign="top" width="28.999999999999996%" id="mcps1.2.3.1.1"><p id="a8245dffabcbf4810a7333d8ce9a67789"><a name="a8245dffabcbf4810a7333d8ce9a67789"></a><a name="a8245dffabcbf4810a7333d8ce9a67789"></a>操作</p>
</th>
<th class="cellrowborder" valign="top" width="71%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0093532762_p685713442569"><a name="zh-cn_topic_0093532762_p685713442569"></a><a name="zh-cn_topic_0093532762_p685713442569"></a>操作说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row82414466296"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="p147711757162810"><a name="p147711757162810"></a><a name="p147711757162810"></a>编辑YAML</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><p id="p15771257142816"><a name="p15771257142816"></a><a name="p15771257142816"></a>单击定时任务名称后的<span class="uicontrol" id="uicontrol33801326152917"><a name="uicontrol33801326152917"></a><a name="uicontrol33801326152917"></a>“更多 &gt; 编辑YAML”</span>，可修改当前任务对应的YAML文件。</p>
</td>
</tr>
<tr id="r25f2ff5451494127b1af5ab34b807936"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="a6abaef816404455581dc7dbaddf656ee"><a name="a6abaef816404455581dc7dbaddf656ee"></a><a name="a6abaef816404455581dc7dbaddf656ee"></a>停止定时任务</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><a name="obe7516d58ade42a389e52e27f663e03d"></a><a name="obe7516d58ade42a389e52e27f663e03d"></a><ol id="obe7516d58ade42a389e52e27f663e03d"><li>选择待停止的任务，单击操作列的“停止”。</li><li>单击“确定”。</li></ol>
</td>
</tr>
<tr id="r9fec8c34ebbb44e3888c677862a174e0"><td class="cellrowborder" valign="top" width="28.999999999999996%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0093532762_p685874410564"><a name="zh-cn_topic_0093532762_p685874410564"></a><a name="zh-cn_topic_0093532762_p685874410564"></a>删除定时任务</p>
</td>
<td class="cellrowborder" valign="top" width="71%" headers="mcps1.2.3.1.2 "><a name="o9409a54b32c14e4799c05e5f0a643633"></a><a name="o9409a54b32c14e4799c05e5f0a643633"></a><ol id="o9409a54b32c14e4799c05e5f0a643633"><li>选择待删除的任务，单击操作列的<span class="uicontrol" id="ub5a9da6130d04758b1d07c5b9e4f06e0"><a name="ub5a9da6130d04758b1d07c5b9e4f06e0"></a><a name="ub5a9da6130d04758b1d07c5b9e4f06e0"></a>“删除”</span>。</li><li>单击“确定”。<p id="a3be1d4db3fa4464dbc950b89a31d57aa"><a name="a3be1d4db3fa4464dbc950b89a31d57aa"></a><a name="a3be1d4db3fa4464dbc950b89a31d57aa"></a>任务删除后将无法恢复，请谨慎操作。</p>
</li></ol>
</td>
</tr>
</tbody>
</table>

