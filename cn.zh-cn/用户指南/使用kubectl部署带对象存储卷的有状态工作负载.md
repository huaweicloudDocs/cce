# 使用kubectl部署带对象存储卷的有状态工作负载<a name="cce_10_0328"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的对象存储卷（PersistentVolumeClaim），创建有状态工作负载（StatefulSet）**。**

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.13及以下版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  参照[使用kubectl自动创建对象存储](使用kubectl自动创建对象存储.md)中操作创建对象存储卷，并获取PVC名称。
2.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
3.  新建一个YAML文件，用于创建工作负载。假设文件名为**obs-statefulset-example.yaml**。

    **touch obs-statefulset-example.yaml**

    **vi obs-statefulset-example.yaml**

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
      serviceName: qwqq
      template:
        metadata:
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: "true"
          creationTimestamp: null
          labels:
            app: obs-statefulset-example
        spec:
          affinity: {}
          containers:	
            image: nginx:latest
            imagePullPolicy: Always
            name: container-0
            volumeMounts:
            - mountPath: /tmp
              name: pvc-obs-example
          imagePullSecrets:
          - name: default-secret
          volumes:
            - name: pvc-obs-example
              persistentVolumeClaim:
                claimName: cce-obs-demo
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

4.  创建有状态工作负载。

    **kubectl create -f obs-statefulset-example.yaml**


