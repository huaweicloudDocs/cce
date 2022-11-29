# 部署带对象存储卷OBS的有状态工作负载<a name="cce_10_0268"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用对象存储卷（PersistentVolumeClaim），创建有状态工作负载（StatefulSet）**。**

## 前提条件<a name="section13181839131510"></a>

您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](Everest（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  参照[存储卷声明PVC](存储卷声明PVC.md)中操作创建对象存储卷，并获取PVC名称。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建一个YAML文件，用于创建工作负载。假设文件名为**obs-statefulset-example.yaml**。

    **touch obs-statefulset-example.yaml**

    **vi obs-statefulset-example.yaml**

    配置示例：

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: obs-statefulset-example
      namespace: default
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: obs-statefulset-example
      template:
        metadata:
          labels:
            app: obs-statefulset-example
        spec:
          volumes: 
          - name: pvc-obs-example 
            persistentVolumeClaim:
              claimName: pvc-obs-example     
          containers:
          - name: container-0
            image: 'nginx:latest'
            volumeMounts:
              - name: pvc-obs-example
                mountPath: /tmp
          restartPolicy: Always
          imagePullSecrets:
          - name: default-secret 
      serviceName: obs-statefulset-example-headless    # Headless Service的名称
    ```

    **表 1**  关键参数说明

    <a name="table19249175815503"></a>
    <table><thead align="left"><tr id="row1425005815020"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p1525045817501"><a name="p1525045817501"></a><a name="p1525045817501"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p162501858165014"><a name="p162501858165014"></a><a name="p162501858165014"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row725065865014"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p152504582506"><a name="p152504582506"></a><a name="p152504582506"></a>replicas</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1425185812509"><a name="p1425185812509"></a><a name="p1425185812509"></a>实例数。</p>
    </td>
    </tr>
    <tr id="row1025175814505"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1825125813505"><a name="p1825125813505"></a><a name="p1825125813505"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1178914555417"><a name="p1178914555417"></a><a name="p1178914555417"></a>新建工作负载的名称。</p>
    </td>
    </tr>
    <tr id="row17251115805017"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p2025185817509"><a name="p2025185817509"></a><a name="p2025185817509"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p9251125875017"><a name="p9251125875017"></a><a name="p9251125875017"></a>新建工作负载使用的镜像。</p>
    </td>
    </tr>
    <tr id="row8251165845018"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p22521858135013"><a name="p22521858135013"></a><a name="p22521858135013"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1525285819508"><a name="p1525285819508"></a><a name="p1525285819508"></a>容器内挂载路径。</p>
    </td>
    </tr>
    <tr id="row848562355515"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p144666233557"><a name="p144666233557"></a><a name="p144666233557"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1090712121565"><a name="p1090712121565"></a><a name="p1090712121565"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    <tr id="row8483182315551"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p846772375512"><a name="p846772375512"></a><a name="p846772375512"></a>claimName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p346792375514"><a name="p346792375514"></a><a name="p346792375514"></a>已有PVC名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

    在有状态工作负载中基于PVCTemplate独占式使用对象存储。

    **yaml示例如下：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: obs-statefulset-example
      namespace: default
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: obs-statefulset-example
      template:
        metadata:
          labels:
            app: obs-statefulset-example
        spec:
          containers:
            - name: container-0
              image: 'nginx:latest'
              volumeMounts:
                - name: pvc-obs-auto-example
                  mountPath: /tmp
          restartPolicy: Always
          imagePullSecrets:
            - name: default-secret
      volumeClaimTemplates:
        - metadata:
            name: pvc-obs-auto-example
            namespace: default
            annotations:
              everest.io/obs-volume-type: STANDARD
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 1Gi
            storageClassName: csi-obs  
      serviceName: obs-statefulset-example-headless
    ```

4.  创建有状态工作负载。

    **kubectl create -f obs-statefulset-example.yaml**


## 验证对象存储的持久化存储<a name="section179416310352"></a>

1.  查询部署的工作负载（以**obs-statefulset-example**为例）的实例和对象存储。
    1.  执行以下命令，查看工作负载对应的实例名称。

        ```
        kubectl get po | grep obs-statefulset-example
        ```

        期望输出：

        ```
        obs-statefulset-example-0   1/1     Running   0          2m5s
        ```

    2.  执行以下命令，查看/tmp目录下是否挂载了对象存储。

        ```
        kubectl exec obs-statefulset-example-0 -- mount|grep /tmp
        ```

        期望输出：

        ```
        s3fs on /tmp type fuse.s3fs (rw,nosuid,nodev,relatime,user_id=0,group_id=0,allow_other)
        ```

2.  执行以下命令，在/tmp路径下创建文件test。

    ```
    kubectl exec obs-statefulset-example-0 -- touch /tmp/test
    ```

3.  执行以下命令，查看/tmp路径下的文件。

    ```
    kubectl exec obs-statefulset-example-0 -- ls -l /tmp
    ```

    预期输出：

    ```
    -rw-r--r-- 1 root root     0 Jun  1 02:50 test
    ```

4.  执行以下命令，删除名称为obs-statefulset-example-0的实例

    ```
    kubectl delete po obs-statefulset-example-0
    ```

5.  验证重建后的实例，文件是否仍然存在。
    1.  执行以下命令，查看重建的实例名称

        ```
        kubectl get po
        ```

        预期输出：

        ```
        obs-statefulset-example-0   1/1     Running   0          2m
        ```

    2.  执行以下命令，查看/tmp路径下的文件

        ```
        kubectl exec obs-statefulset-example-0 -- ls -l /tmp
        ```

        预期输出：

        ```
        -rw-r--r-- 1 root root     0 Jun  1 02:50 test
        ```

    3.  test文件在实例重建之后仍然存在，说明对象存储数据可持久化保存。


