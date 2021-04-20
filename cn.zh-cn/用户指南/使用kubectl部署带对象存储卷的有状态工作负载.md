# 使用kubectl部署带对象存储卷的有状态工作负载<a name="cce_01_0268"></a>

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的对象存储卷（PersistentVolumeClaim），创建有状态工作负载（StatefulSet）**。**

## 操作步骤<a name="section1530655595611"></a>

1.  参照[创建对象存储卷](使用对象存储卷.md#section172788131291)中操作创建对象存储卷，并获取PVC名称。
2.  请参见[通过kubectl或web-terminal插件操作CCE集群](通过kubectl或web-terminal插件操作CCE集群.md)配置kubectl命令。
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
      podManagementPolicy: OrderedReady
      replicas: 1
      revisionHistoryLimit: 10
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
          - env:
            - name: PAAS_APP_NAME
              value: obs-statefulset-example
            - name: PAAS_NAMESPACE
              value: default
            - name: PAAS_PROJECT_ID
              value: b7bb7d77a2974a8fa8985cbfb63f23c0
            image: nginx:latest
            imagePullPolicy: Always
            name: container-0
            resources: {}
            terminationMessagePath: /dev/termination-log
            terminationMessagePolicy: File
            volumeMounts:
            - mountPath: /tmp
              name: pvc-obs-example
          dnsPolicy: ClusterFirst
          imagePullSecrets:
          - name: default-secret
          restartPolicy: Always
          schedulerName: default-scheduler
          securityContext: {}
          terminationGracePeriodSeconds: 30
          volumes:
            - name: pvc-obs-example
              persistentVolumeClaim:
                claimName: cce-obs-demo
          tolerations:
          - effect: NoExecute
            key: node.kubernetes.io/not-ready
            operator: Exists
            tolerationSeconds: 300
          - effect: NoExecute
            key: node.kubernetes.io/unreachable
            operator: Exists
            tolerationSeconds: 300
      updateStrategy:
        type: RollingUpdate
    ```

    **表 1**  关键参数说明

    <a name="table19249175815503"></a>
    <table><thead align="left"><tr id="row1425005815020"><th class="cellrowborder" valign="top" width="26.42980935875217%" id="mcps1.2.3.1.1"><p id="p1525045817501"><a name="p1525045817501"></a><a name="p1525045817501"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="73.57019064124783%" id="mcps1.2.3.1.2"><p id="p162501858165014"><a name="p162501858165014"></a><a name="p162501858165014"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row725065865014"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p152504582506"><a name="p152504582506"></a><a name="p152504582506"></a>replicas</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1425185812509"><a name="p1425185812509"></a><a name="p1425185812509"></a>实例数。</p>
    </td>
    </tr>
    <tr id="row1025175814505"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p1825125813505"><a name="p1825125813505"></a><a name="p1825125813505"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1178914555417"><a name="p1178914555417"></a><a name="p1178914555417"></a>新建工作负载的名称。</p>
    </td>
    </tr>
    <tr id="row17251115805017"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p2025185817509"><a name="p2025185817509"></a><a name="p2025185817509"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p9251125875017"><a name="p9251125875017"></a><a name="p9251125875017"></a>新建工作负载使用的镜像。</p>
    </td>
    </tr>
    <tr id="row8251165845018"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p22521858135013"><a name="p22521858135013"></a><a name="p22521858135013"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1525285819508"><a name="p1525285819508"></a><a name="p1525285819508"></a>容器内挂载路径。</p>
    </td>
    </tr>
    <tr id="row848562355515"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p144666233557"><a name="p144666233557"></a><a name="p144666233557"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1090712121565"><a name="p1090712121565"></a><a name="p1090712121565"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    <tr id="row8483182315551"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p846772375512"><a name="p846772375512"></a><a name="p846772375512"></a>claimName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p346792375514"><a name="p346792375514"></a><a name="p346792375514"></a>已有PVC名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  创建有状态工作负载。

    **kubectl create -f obs-statefulset-example.yaml**


