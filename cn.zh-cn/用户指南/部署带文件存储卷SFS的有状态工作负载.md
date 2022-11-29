# 部署带文件存储卷SFS的有状态工作负载<a name="cce_10_0262"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用文件存储（PersistentVolumeClaim），创建有状态工作负载（StatefulSet）**。**

## 前提条件<a name="section13181839131510"></a>

您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](Everest（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  参照[存储卷声明PVC](存储卷声明PVC.md)中操作创建文件存储卷，记录文件存储卷名称。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建一个YAML文件，用于创建工作负载。假设文件名为**sfs-statefulset-example**.**yaml**。

    **touch sfs-statefulset-example.yaml**

    **vi sfs-statefulset-example.yaml**

    配置示例：

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: sfs-statefulset-example
      namespace: default
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: sfs-statefulset-example
      template:
        metadata:
          labels:
            app: sfs-statefulset-example
        spec:
          volumes: 
          - name: pvc-sfs-example 
            persistentVolumeClaim:
              claimName: pvc-sfs-example     
          containers:
          - name: container-0
            image: 'nginx:latest'
            volumeMounts:
              - name: pvc-sfs-example
                mountPath: /tmp
          restartPolicy: Always
          imagePullSecrets:
          - name: default-secret 
      serviceName: sfs-statefulset-example-headless
      updateStrategy:
        type: RollingUpdate
    ```

    **表 1**  关键参数说明

    <a name="table397913279106"></a>
    <table><thead align="left"><tr id="row119803273101"><th class="cellrowborder" valign="top" width="35.61%" id="mcps1.2.4.1.1"><p id="p711172811283"><a name="p711172811283"></a><a name="p711172811283"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="19.139999999999997%" id="mcps1.2.4.1.2"><p id="p12980132717103"><a name="p12980132717103"></a><a name="p12980132717103"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="45.25%" id="mcps1.2.4.1.3"><p id="p7981172710104"><a name="p7981172710104"></a><a name="p7981172710104"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row99818271102"><td class="cellrowborder" valign="top" width="35.61%" headers="mcps1.2.4.1.1 "><p id="p5111428152813"><a name="p5111428152813"></a><a name="p5111428152813"></a>spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.139999999999997%" headers="mcps1.2.4.1.2 "><p id="p345291413122"><a name="p345291413122"></a><a name="p345291413122"></a>replicas</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.25%" headers="mcps1.2.4.1.3 "><p id="p119811427161017"><a name="p119811427161017"></a><a name="p119811427161017"></a>实例数。</p>
    </td>
    </tr>
    <tr id="row14981102761010"><td class="cellrowborder" valign="top" width="35.61%" headers="mcps1.2.4.1.1 "><p id="p01172810283"><a name="p01172810283"></a><a name="p01172810283"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.139999999999997%" headers="mcps1.2.4.1.2 "><p id="p1258410114111"><a name="p1258410114111"></a><a name="p1258410114111"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.25%" headers="mcps1.2.4.1.3 "><p id="p14983152711100"><a name="p14983152711100"></a><a name="p14983152711100"></a>新建工作负载的名称。</p>
    </td>
    </tr>
    <tr id="row15983132715104"><td class="cellrowborder" valign="top" width="35.61%" headers="mcps1.2.4.1.1 "><p id="p111110287288"><a name="p111110287288"></a><a name="p111110287288"></a>spec.template.spec.containers</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.139999999999997%" headers="mcps1.2.4.1.2 "><p id="p18404174281219"><a name="p18404174281219"></a><a name="p18404174281219"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.25%" headers="mcps1.2.4.1.3 "><p id="p2098372713107"><a name="p2098372713107"></a><a name="p2098372713107"></a>新建工作负载使用的镜像。</p>
    </td>
    </tr>
    <tr id="row17983427181013"><td class="cellrowborder" valign="top" width="35.61%" headers="mcps1.2.4.1.1 "><p id="p211182811286"><a name="p211182811286"></a><a name="p211182811286"></a>spec.template.spec.containers.volumeMounts</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.139999999999997%" headers="mcps1.2.4.1.2 "><p id="p383919212135"><a name="p383919212135"></a><a name="p383919212135"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.25%" headers="mcps1.2.4.1.3 "><p id="p3983142712105"><a name="p3983142712105"></a><a name="p3983142712105"></a>容器内挂载路径。</p>
    </td>
    </tr>
    <tr id="row17159179171318"><td class="cellrowborder" valign="top" width="35.61%" headers="mcps1.2.4.1.1 "><p id="p1011102862812"><a name="p1011102862812"></a><a name="p1011102862812"></a>spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.139999999999997%" headers="mcps1.2.4.1.2 "><p id="p6104899138"><a name="p6104899138"></a><a name="p6104899138"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.25%" headers="mcps1.2.4.1.3 "><p id="p1210449101314"><a name="p1210449101314"></a><a name="p1210449101314"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    <tr id="row51546961311"><td class="cellrowborder" valign="top" width="35.61%" headers="mcps1.2.4.1.1 "><p id="p711728102820"><a name="p711728102820"></a><a name="p711728102820"></a>spec.template.spec.volumes.persistentVolumeClaim</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.139999999999997%" headers="mcps1.2.4.1.2 "><p id="p246811218141"><a name="p246811218141"></a><a name="p246811218141"></a>claimName</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.25%" headers="mcps1.2.4.1.3 "><p id="p14105139131316"><a name="p14105139131316"></a><a name="p14105139131316"></a>已有PVC名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

    在有状态工作负载中基于PVCTemplate独占式使用文件存储：

    **yaml配置示例如下：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: sfs-statefulset-example
      namespace: default
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: sfs-statefulset-example
      template:
        metadata:
          labels:
            app: sfs-statefulset-example
        spec:
          containers:
            - name: container-0
              image: 'nginx:latest'
              volumeMounts:
                - name: pvc-sfs-auto-example
                  mountPath: /tmp
          restartPolicy: Always
          imagePullSecrets:
            - name: default-secret
      volumeClaimTemplates:
        - metadata:
            name: pvc-sfs-auto-example
            namespace: default
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 10Gi
            storageClassName: csi-nas
      serviceName: sfs-statefulset-example-headless
      updateStrategy:
        type: RollingUpdate
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >spec.template.spec.containers.volumeMounts.name和spec.template.spec.volumes.name有映射关系，必须保持一致。

4.  创建有状态工作负载。

    **kubectl create -f  sfs-statefulset-example.yaml**


## 验证文件系统的持久化存储<a name="section179416310352"></a>

1.  查询部署的工作负载（以**sfs-statefulset-example**为例）的实例和文件存储。
    1.  执行以下命令，查看工作负载对应的实例名称。

        ```
        kubectl get po | grep sfs-statefulset-example
        ```

        期望输出：

        ```
        sfs-statefulset-example-0   1/1     Running   0          2m5s
        ```

    2.  执行以下命令，查看/tmp目录下是否挂载了文件存储。

        ```
        kubectl exec sfs-statefulset-example-0 -- mount|grep /tmp
        ```

        期望输出：

        ```
        sfs-nas01.cn-north-4.myhuaweicloud.com:/share-c56b9aa4 on /tmp type nfs (rw,relatime,vers=3,rsize=1048576,wsize=1048576,namlen=255,hard,nolock,noresvport,proto=tcp,timeo=600,retrans=2,sec=sys,mountaddr=10.79.96.32,mountvers=3,mountport=2050,mountproto=tcp,local_lock=all,addr=10.79.96.32)
        ```

2.  执行以下命令，在/tmp路径下创建问题test。

    ```
    kubectl exec sfs-statefulset-example-0 -- touch /tmp/test
    ```

3.  执行以下命令，查看/tmp路径下的文件。

    ```
    kubectl exec sfs-statefulset-example-0 -- ls -l /tmp
    ```

    预期输出：

    ```
    -rw-r--r-- 1 root root     0 Jun  1 02:50 test
    ```

4.  执行以下命令，删除名称为sfs-statefulset-example-0的实例

    ```
    kubectl delete po sfs-statefulset-example-0
    ```

5.  验证重建后的实例，文件存储卷内的数据文件会否仍然存在
    1.  执行以下命令，查看重建的实例名称

        ```
        kubectl get po
        ```

        预期输出：

        ```
        sfs-statefulset-example-0   1/1     Running   0          2m
        ```

    2.  执行以下命令，查看/tmp路径下的文件

        ```
        kubectl exec sfs-statefulset-example-0 -- ls -l /tmp
        ```

        预期输出：

        ```
        -rw-r--r-- 1 root root     0 Jun  1 02:50 test
        ```

    3.  test文件在实例重建之后仍然存在，说明文件系统数据可持久化保存


