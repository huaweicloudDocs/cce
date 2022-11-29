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

1.  登录CCE控制台，进入集群，单击左侧导航栏的“插件管理“，在右侧找到**Volcano**，单击“安装“。
2.  配置参数。

    ```
    {
    	"resource_exporter_enable": "false"
    }
    ```

    resource\_exporter\_enable：是否开启收集节点Numa信息，默认为false，设置为true表示开启。

3.  单击“安装“。

## Volcano 1.0.0版本升级说明<a name="section1363753011313"></a>

Volcano 1.0.0版本与后续版本不兼容，不支持在控制台升级。如想使用新版本Volcano插件，需要先卸载1.0.0版本，然后再在控制台安装新版本。

执行如下命令可以卸载Volcano。

**kubectl  delete  crd  jobs.batch.volcano.sh**

**kubectl  delete  crd commands.bus.volcano.sh**

