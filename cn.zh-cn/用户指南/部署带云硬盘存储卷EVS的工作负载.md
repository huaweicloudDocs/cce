# 部署带云硬盘存储卷EVS的工作负载<a name="cce_10_0257"></a>

## 操作场景<a name="section1789161805617"></a>

云硬盘创建或导入CCE后，可以在工作负载中挂载云硬盘。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>云硬盘不支持跨可用区挂载。在挂载前，您可以使用** kubectl get pvc**  命令查询当前集群所在分区下可用PVC。

## 前提条件<a name="section13181839131510"></a>

您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](everest（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 无状态负载使用云硬盘<a name="section421772310564"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
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

3.  执行如下命令创建工作负载。

    **kubectl create -f evs-deployment-example.yaml**


## 有状态负载使用云硬盘<a name="section1104163720107"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，配置名为“evs-statefulset-example.yaml“的创建有状态工作负载的yaml文件。

    **touch evs-statefulset-example.yaml**

    **vi evs-statefulset-example.yaml**

    在有状态工作负载中基于PVCTemplate独占式使用云硬盘存储。

    **yaml示例如下：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: evs-statefulset-example
      namespace: default
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: evs-statefulset-example
      template:
        metadata:
          labels:
            app: evs-statefulset-example
        spec:
          containers:
            - name: container-0
              image: 'nginx:latest'
              volumeMounts:
                - name: pvc-evs-auto-example
                  mountPath: /tmp
          restartPolicy: Always
          imagePullSecrets:
            - name: default-secret
      volumeClaimTemplates:
        - metadata:
            name: pvc-evs-auto-example
            namespace: default
            labels:
              failure-domain.beta.kubernetes.io/region: cn-north-4
              failure-domain.beta.kubernetes.io/zone: cn-north-4b
            annotations:
              everest.io/disk-volume-type: SAS
          spec:
            accessModes:
              - ReadWriteOnce
            resources:
              requests:
                storage: 10Gi
            storageClassName: csi-disk   
      serviceName: evs-statefulset-example-headless
      updateStrategy:
        type: RollingUpdate
    ```

    **表 2**  关键参数说明

    <a name="table37966951119"></a>
    <table><thead align="left"><tr id="row17796159151117"><th class="cellrowborder" valign="top" width="30.570000000000004%" id="mcps1.2.4.1.1"><p id="p779629181113"><a name="p779629181113"></a><a name="p779629181113"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.150000000000002%" id="mcps1.2.4.1.2"><p id="p079615917118"><a name="p079615917118"></a><a name="p079615917118"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.28000000000001%" id="mcps1.2.4.1.3"><p id="p1179619111112"><a name="p1179619111112"></a><a name="p1179619111112"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row079615921119"><td class="cellrowborder" valign="top" width="30.570000000000004%" headers="mcps1.2.4.1.1 "><p id="p20796691110"><a name="p20796691110"></a><a name="p20796691110"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.150000000000002%" headers="mcps1.2.4.1.2 "><p id="p179617921112"><a name="p179617921112"></a><a name="p179617921112"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.28000000000001%" headers="mcps1.2.4.1.3 "><p id="p1979620951115"><a name="p1979620951115"></a><a name="p1979620951115"></a>创建的工作负载名称。</p>
    </td>
    </tr>
    <tr id="row177961797115"><td class="cellrowborder" valign="top" width="30.570000000000004%" headers="mcps1.2.4.1.1 "><p id="p4796119161110"><a name="p4796119161110"></a><a name="p4796119161110"></a>spec.template.spec.containers</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.150000000000002%" headers="mcps1.2.4.1.2 "><p id="p879699101113"><a name="p879699101113"></a><a name="p879699101113"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.28000000000001%" headers="mcps1.2.4.1.3 "><p id="p979689131114"><a name="p979689131114"></a><a name="p979689131114"></a>工作负载的镜像。</p>
    </td>
    </tr>
    <tr id="row179617915117"><td class="cellrowborder" valign="top" width="30.570000000000004%" headers="mcps1.2.4.1.1 "><p id="p13796189161112"><a name="p13796189161112"></a><a name="p13796189161112"></a>spec.template.spec.containers.volumeMount</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.150000000000002%" headers="mcps1.2.4.1.2 "><p id="p157966913118"><a name="p157966913118"></a><a name="p157966913118"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.28000000000001%" headers="mcps1.2.4.1.3 "><p id="p1796189101112"><a name="p1796189101112"></a><a name="p1796189101112"></a>容器内挂载路径，示例中挂载到“/tmp”路径。</p>
    </td>
    </tr>
    <tr id="row197963921111"><td class="cellrowborder" valign="top" width="30.570000000000004%" headers="mcps1.2.4.1.1 "><p id="p379618918119"><a name="p379618918119"></a><a name="p379618918119"></a>spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.150000000000002%" headers="mcps1.2.4.1.2 "><p id="p579610915115"><a name="p579610915115"></a><a name="p579610915115"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.28000000000001%" headers="mcps1.2.4.1.3 "><p id="p079610971112"><a name="p079610971112"></a><a name="p079610971112"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

3.  执行如下命令创建工作负载。

    **kubectl create -f evs-statefulset-example.yaml**


## 验证云硬盘的持久化存储<a name="section1347793033917"></a>

1.  查询部署的工作负载（以**evs-statefulset-example**为例）的实例和云硬盘文件。
    1.  执行以下命令，查看工作负载对应的实例名称。

        ```
        kubectl get po | grep evs-statefulset-example
        ```

        期望输出：

        ```
        evs-statefulset-example-0   1/1     Running   0          22h
        ```

    2.  执行以下命令，查看/tmp目录下是否挂载了云硬盘。

        ```
        kubectl exec evs-statefulset-example-0 -- df tmp
        ```

        期望输出：

        ```
        /dev/sda        10255636 36888  10202364   1% /tmp
        ```

2.  执行以下命令，在/tmp路径下创建问题test。

    ```
    kubectl exec evs-statefulset-example-0 -- touch /tmp/test
    ```

3.  执行以下命令，查看/tmp路径下的文件。

    ```
    kubectl exec evs-statefulset-example-0 -- ls -l /tmp
    ```

    预期输出：

    ```
    -rw-r--r-- 1 root root     0 Jun  1 02:50 test
    ```

4.  执行以下命令，删除名称为evs-statefulset-example-0的实例

    ```
    kubectl delete po evs-statefulset-example-0
    ```

5.  验证重建后的实例，文件是否仍然存在
    1.  执行以下命令，查看重建的实例名称

        ```
        kubectl get po
        ```

        预期输出：

        ```
        evs-statefulset-example-0   1/1     Running   0          2m
        ```

    2.  执行以下命令，查看/tmp路径下的文件

        ```
        kubectl exec evs-statefulset-example-0 -- ls -l /tmp
        ```

        预期输出：

        ```
        -rw-r--r-- 1 root root     0 Jun  1 02:50 test
        ```

    3.  test文件在实例重建之后仍然存在，说明云硬盘数据可持久化保存


