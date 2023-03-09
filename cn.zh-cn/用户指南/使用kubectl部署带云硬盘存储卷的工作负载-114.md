# 使用kubectl部署带云硬盘存储卷的工作负载<a name="cce_01_0314"></a>

## 操作场景<a name="section1789161805617"></a>

云硬盘创建或导入CCE后，可以在工作负载中挂载云硬盘。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>云硬盘不支持跨可用区挂载。在挂载前，您可以使用** kubectl get pvc**  命令查询当前集群所在分区下可用PVC。

## 前提条件<a name="section1640173074515"></a>

您已经创建好一个CCE集群，并且在该集群中安装Flexvolume插件（[storage-driver](storage-driver（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.13及以下版本的集群。

## 操作步骤<a name="section421772310564"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群-7.md)，使用kubectl连接集群。
2.  执行如下命令，配置名为“evs-deployment-example.yaml“的创建无状态工作负载的yaml文件。

    **touch evs-deployment-example.yaml**

    **vi evs-deployment-example.yaml**

    在无状态工作负载中基于pvc共享式使用云硬盘存储示例：

    ```
    apiVersion: apps/v1 
    kind: Deployment 
    metadata: 
      name: evs-deployment-example 
      namespace: default 
    spec: 
      replicas: 1 
      selector: 
        matchLabels: 
          app: evs-deployment-example 
      template: 
        metadata: 
          labels: 
            app: evs-deployment-example 
        spec: 
          containers: 
          - image: nginx
            name: container-0 
            volumeMounts: 
            - mountPath: /tmp 
              name: pvc-evs-example 
          imagePullSecrets:
            - name: default-secret
          restartPolicy: Always 
          volumes: 
          - name: pvc-evs-example 
            persistentVolumeClaim: 
              claimName: pvc-evs-auto-example
    ```

    **表 1**  关键参数说明

    <a name="table1819001615355"></a>
    <table><thead align="left"><tr id="row1519121663519"><th class="cellrowborder" valign="top" width="32.73%" id="mcps1.2.4.1.1"><p id="p525814169813"><a name="p525814169813"></a><a name="p525814169813"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.15%" id="mcps1.2.4.1.2"><p id="p18191161619356"><a name="p18191161619356"></a><a name="p18191161619356"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="49.120000000000005%" id="mcps1.2.4.1.3"><p id="p1919116161353"><a name="p1919116161353"></a><a name="p1919116161353"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row7430236123515"><td class="cellrowborder" valign="top" width="32.73%" headers="mcps1.2.4.1.1 "><p id="p92591716583"><a name="p92591716583"></a><a name="p92591716583"></a>spec.template.spec.containers.volumeMounts</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.4.1.2 "><p id="p116341334126"><a name="p116341334126"></a><a name="p116341334126"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.120000000000005%" headers="mcps1.2.4.1.3 "><p id="p1927814583433"><a name="p1927814583433"></a><a name="p1927814583433"></a>容器内挂载卷的名称。</p>
    </td>
    </tr>
    <tr id="row10639194016187"><td class="cellrowborder" valign="top" width="32.73%" headers="mcps1.2.4.1.1 "><p id="p54664413187"><a name="p54664413187"></a><a name="p54664413187"></a>spec.template.spec.containers.volumeMounts</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.4.1.2 "><p id="p1946674110189"><a name="p1946674110189"></a><a name="p1946674110189"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.120000000000005%" headers="mcps1.2.4.1.3 "><p id="p546684111182"><a name="p546684111182"></a><a name="p546684111182"></a>容器内挂载路径，示例中挂载到“/tmp”路径。</p>
    </td>
    </tr>
    <tr id="row6232511129"><td class="cellrowborder" valign="top" width="32.73%" headers="mcps1.2.4.1.1 "><p id="p72592169811"><a name="p72592169811"></a><a name="p72592169811"></a>spec.template.spec.volumes</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.4.1.2 "><p id="p192525131213"><a name="p192525131213"></a><a name="p192525131213"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.120000000000005%" headers="mcps1.2.4.1.3 "><p id="p132182510120"><a name="p132182510120"></a><a name="p132182510120"></a>卷的名称。</p>
    </td>
    </tr>
    <tr id="row163191830121220"><td class="cellrowborder" valign="top" width="32.73%" headers="mcps1.2.4.1.1 "><p id="p425991613812"><a name="p425991613812"></a><a name="p425991613812"></a>spec.template.spec.volumes.persistentVolumeClaim</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.4.1.2 "><p id="p14319143031212"><a name="p14319143031212"></a><a name="p14319143031212"></a>claimName</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.120000000000005%" headers="mcps1.2.4.1.3 "><p id="p18319530131211"><a name="p18319530131211"></a><a name="p18319530131211"></a>已有PVC名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name ”和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

    在有状态工作负载中基于PVCTemplate独占式使用云硬盘存储。

    **yaml示例如下：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: deploy-evs-sas-in
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: deploy-evs-sata-in
      template:
        metadata:
          labels:
            app: deploy-evs-sata-in
            failure-domain.beta.kubernetes.io/region: cn-north-4
            failure-domain.beta.kubernetes.io/zone: cn-north-4b
        spec:
          containers:
            - name: container-0
              image: 'nginx:1.12-alpine-perl'
              volumeMounts:
                - name: bs-sas-mountoptionpvc
                  mountPath: /tmp
          imagePullSecrets:
            - name: default-secret
      volumeClaimTemplates:
        - metadata:
            name: bs-sas-mountoptionpvc
            annotations:
              volume.beta.kubernetes.io/storage-class: sas
              volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxivol
          spec:
            accessModes:
              - ReadWriteOnce
            resources:
              requests:
                storage: 10Gi
      serviceName: wwww
    ```

    **表 2**  关键参数说明

    <a name="table628368131916"></a>
    <table><thead align="left"><tr id="row122837851917"><th class="cellrowborder" valign="top" width="27.01%" id="mcps1.2.4.1.1"><p id="p24390324267"><a name="p24390324267"></a><a name="p24390324267"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.59%" id="mcps1.2.4.1.2"><p id="p42830816196"><a name="p42830816196"></a><a name="p42830816196"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="55.400000000000006%" id="mcps1.2.4.1.3"><p id="p16284108101912"><a name="p16284108101912"></a><a name="p16284108101912"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1428438101916"><td class="cellrowborder" valign="top" width="27.01%" headers="mcps1.2.4.1.1 "><p id="p143914327264"><a name="p143914327264"></a><a name="p143914327264"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.59%" headers="mcps1.2.4.1.2 "><p id="p142843811197"><a name="p142843811197"></a><a name="p142843811197"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="55.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p14367283124"><a name="p14367283124"></a><a name="p14367283124"></a>创建的工作负载名称。</p>
    </td>
    </tr>
    <tr id="row428458201916"><td class="cellrowborder" valign="top" width="27.01%" headers="mcps1.2.4.1.1 "><p id="p104391325267"><a name="p104391325267"></a><a name="p104391325267"></a>spec.template.spec.containers</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.59%" headers="mcps1.2.4.1.2 "><p id="p202841483196"><a name="p202841483196"></a><a name="p202841483196"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="55.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p11284585196"><a name="p11284585196"></a><a name="p11284585196"></a>工作负载的镜像。</p>
    </td>
    </tr>
    <tr id="row192841589190"><td class="cellrowborder" valign="top" width="27.01%" headers="mcps1.2.4.1.1 "><p id="p243920327269"><a name="p243920327269"></a><a name="p243920327269"></a>spec.template.spec.containers.volumeMount</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.59%" headers="mcps1.2.4.1.2 "><p id="p32847817196"><a name="p32847817196"></a><a name="p32847817196"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="55.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p112851818196"><a name="p112851818196"></a><a name="p112851818196"></a>容器内挂载路径，示例中挂载到“/tmp”路径。</p>
    </td>
    </tr>
    <tr id="row6285158191916"><td class="cellrowborder" valign="top" width="27.01%" headers="mcps1.2.4.1.1 "><p id="p2043914322263"><a name="p2043914322263"></a><a name="p2043914322263"></a>spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.59%" headers="mcps1.2.4.1.2 "><p id="p1828558101912"><a name="p1828558101912"></a><a name="p1828558101912"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="55.400000000000006%" headers="mcps1.2.4.1.3 "><p id="p415683820207"><a name="p415683820207"></a><a name="p415683820207"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet)-41.md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

3.  执行如下命令创建Pod。

    **kubectl create -f evs-deployment-example.yaml**

    创建完成后，登录CCE控制台，在左侧导航栏中选择“存储管理 \> 云硬盘存储卷“。单击PVC名称，在PVC详情页面可查看云硬盘和PVC的绑定关系。


