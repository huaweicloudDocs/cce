# 使用kubectl部署带极速文件存储卷的有状态工作负载<a name="cce_01_0273"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的极速文件存储（SFS Turbo），创建有状态工作负载（StatefulSet）**。**

## 前提条件<a name="section13181839131510"></a>

您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](Everest（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  参照创建文件存储卷中操作创建极速文件存储卷，记录极速文件存储卷名称。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建一个文件，用于创建工作负载。假设文件名为**sfsturbo-statefulset-example**.**yaml**。

    **touch sfsturbo-statefulset-example.yaml**

    **vi sfsturbo-statefulset-example.yaml**

    配置示例：

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: sfsturbo-statefulset-example
      namespace: default
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: sfsturbo-statefulset-example
      template:
        metadata:
          labels:
            app: sfsturbo-statefulset-example
        spec:
          volumes: 
          - name: pvc-sfsturbo-example 
            persistentVolumeClaim:
              claimName: pvc-sfsturbo-example     
          containers:
          - name: container-0
            image: 'nginx:latest'
            volumeMounts:
              - name: pvc-sfsturbo-example
                mountPath: /tmp
          restartPolicy: Always
          imagePullSecrets:
          - name: default-secret 
      serviceName: sfsturbo-statefulset-example-headless
      updateStrategy:
        type: RollingUpdate
    ```

    **表 1**  关键参数说明

    <a name="table1739110557150"></a>
    <table><thead align="left"><tr id="row439135512158"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p11391105571516"><a name="p11391105571516"></a><a name="p11391105571516"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p439255513157"><a name="p439255513157"></a><a name="p439255513157"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row739215556154"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p10106112010189"><a name="p10106112010189"></a><a name="p10106112010189"></a>replicas</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p23923555150"><a name="p23923555150"></a><a name="p23923555150"></a>实例数。</p>
    </td>
    </tr>
    <tr id="row18143134041612"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p11431840161611"><a name="p11431840161611"></a><a name="p11431840161611"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p714434016164"><a name="p714434016164"></a><a name="p714434016164"></a>新建工作负载的名称。</p>
    </td>
    </tr>
    <tr id="row1339295514152"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p83921559156"><a name="p83921559156"></a><a name="p83921559156"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1839395518152"><a name="p1839395518152"></a><a name="p1839395518152"></a>新建工作负载使用的镜像。</p>
    </td>
    </tr>
    <tr id="row1339365571519"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p239365513155"><a name="p239365513155"></a><a name="p239365513155"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p10393455131513"><a name="p10393455131513"></a><a name="p10393455131513"></a>容器内挂载路径。</p>
    </td>
    </tr>
    <tr id="row19843742102014"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p131115042015"><a name="p131115042015"></a><a name="p131115042015"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p15831142152010"><a name="p15831142152010"></a><a name="p15831142152010"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    <tr id="row12841184262014"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p15151719152119"><a name="p15151719152119"></a><a name="p15151719152119"></a>claimName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p2831114232019"><a name="p2831114232019"></a><a name="p2831114232019"></a>已有PVC名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >spec.template.spec.containers.volumeMounts.name和spec.template.spec.volumes.name有映射关系，必须保持一致。

4.  创建有状态工作负载。

    **kubectl create -f  sfsturbo-statefulset-example.yaml**


## 验证极速文件系统的持久化存储<a name="section179416310352"></a>

1.  查询部署的工作负载（以**sfsturbo-statefulset-example**为例）的实例和极速文件存储文件。
    1.  执行以下命令，查看工作负载对应的实例名称。

        ```
        kubectl get po | grep sfsturbo-statefulset-example
        ```

        期望输出：

        ```
        sfsturbo-statefulset-example-0   1/1     Running   0          2m5s
        ```

    2.  执行以下命令，查看/tmp目录下是否挂载了极速文件存储。

        ```
        kubectl exec sfsturbo-statefulset-example-0 -- mount|grep /tmp
        ```

        期望输出：

        ```
        192.168.0.108:/ on /tmp type nfs (rw,relatime,vers=3,rsize=1048576,wsize=1048576,namlen=255,hard,nolock,noresvport,proto=tcp,timeo=600,retrans=2,sec=sys,mountaddr=192.168.0.108,mountvers=3,mountport=20048,mountproto=tcp,local_lock=all,addr=192.168.0.108)
        ```

2.  执行以下命令，在/tmp路径下创建问题test。

    ```
    kubectl exec sfsturbo-statefulset-example-0 -- touch /tmp/test
    ```

3.  执行以下命令，查看/tmp路径下的文件。

    ```
    kubectl exec sfsturbo-statefulset-example-0 -- ls -l /tmp
    ```

    预期输出：

    ```
    -rw-r--r-- 1 root root     0 Jun  1 02:50 test
    ```

4.  执行以下命令，删除名称为sfsturbo-statefulset-example-0的实例。

    ```
    kubectl delete po sfsturbo-statefulset-example-0
    ```

5.  验证重建后的实例，文件是否仍然存在。
    1.  执行以下命令，查看重建的实例名称。

        ```
        kubectl get po
        ```

        预期输出：

        ```
        sfsturbo-statefulset-example-0   1/1     Running   0          2m
        ```

    2.  执行以下命令，查看/tmp路径下的文件。

        ```
        kubectl exec sfsturbo-statefulset-example-0 -- ls -l /tmp
        ```

        预期输出：

        ```
        -rw-r--r-- 1 root root     0 Jun  1 02:50 test
        ```

        test文件在实例重建之后仍然存在，说明极速文件系统数据可持久化保存。



## 相关操作<a name="section184741309122"></a>

[使用subpath类型动态创建SFS Turbo存储卷](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00253.html)

