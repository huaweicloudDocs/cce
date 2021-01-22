# 使用已有PVC创建有状态工作负载<a name="cce_01_0273"></a>

-   [操作场景](#section1062914713566)
-   [操作步骤](#section1530655595611)

## 操作场景<a name="section1062914713566"></a>

CCE支持使用已有的极速文件存储（SFS Turbo），创建有状态工作负载（StatefulSet）**。**

## 操作步骤<a name="section1530655595611"></a>

1.  参照创建文件存储卷中操作创建极速文件存储卷，记录极速文件存储卷名称。
2.  请参见[通过kubectl或web-terminal插件操作CCE集群](通过kubectl或web-terminal插件操作CCE集群.md)配置kubectl命令。
3.  新建一个文件，用于创建工作负载。假设文件名为**efs-statefulset-example**.**yaml**。

    **touch efs-statefulset-example.yaml**

    **vi efs-statefulset-example.yaml**

    配置示例：

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: efs-statefulset-example
      namespace: default
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: efs-statefulset-example
      template:
        metadata:
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: 'true'
          labels:
            app: efs-statefulset-example
        spec:
          containers:
            - image: 'nginx:1.0.0'
              name: container-0
              resources:
                requests: {}
                limits: {}
              env:
                - name: PAAS_APP_NAME
                  value: efs-statefulset-example
                - name: PAAS_NAMESPACE
                  value: default
                - name: PAAS_PROJECT_ID
                  value: b18296881cc34f929baa8b9e95abf88b
              volumeMounts:
                - name: efs-statefulset-example
                  mountPath: /tmp
                  readOnly: false
                  subPath: ''
          imagePullSecrets:
            - name: default-secret
          terminationGracePeriodSeconds: 30
          volumes:
            - persistentVolumeClaim:
                claimName: cce-efs-import-jnr481gm-3y5o
              name: efs-statefulset-example
          affinity: {}
          tolerations:
            - key: node.kubernetes.io/not-ready
              operator: Exists
              effect: NoExecute
              tolerationSeconds: 300
            - key: node.kubernetes.io/unreachable
              operator: Exists
              effect: NoExecute
              tolerationSeconds: 300
      podManagementPolicy: OrderedReady
      serviceName: test
      updateStrategy:
        type: RollingUpdate
    ```

    **表 1**  关键参数说明

    <a name="table1739110557150"></a>
    <table><thead align="left"><tr id="row439135512158"><th class="cellrowborder" valign="top" width="26.42980935875217%" id="mcps1.2.3.1.1"><p id="p11391105571516"><a name="p11391105571516"></a><a name="p11391105571516"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="73.57019064124783%" id="mcps1.2.3.1.2"><p id="p439255513157"><a name="p439255513157"></a><a name="p439255513157"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row739215556154"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p10106112010189"><a name="p10106112010189"></a><a name="p10106112010189"></a>replicas</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p23923555150"><a name="p23923555150"></a><a name="p23923555150"></a>实例数。</p>
    </td>
    </tr>
    <tr id="row18143134041612"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p11431840161611"><a name="p11431840161611"></a><a name="p11431840161611"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p714434016164"><a name="p714434016164"></a><a name="p714434016164"></a>新建工作负载的名称。</p>
    </td>
    </tr>
    <tr id="row1339295514152"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p83921559156"><a name="p83921559156"></a><a name="p83921559156"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1839395518152"><a name="p1839395518152"></a><a name="p1839395518152"></a>新建工作负载使用的镜像。</p>
    </td>
    </tr>
    <tr id="row1339365571519"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p239365513155"><a name="p239365513155"></a><a name="p239365513155"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p10393455131513"><a name="p10393455131513"></a><a name="p10393455131513"></a>容器内挂载路径。</p>
    </td>
    </tr>
    <tr id="row19843742102014"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p131115042015"><a name="p131115042015"></a><a name="p131115042015"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p15831142152010"><a name="p15831142152010"></a><a name="p15831142152010"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    <tr id="row12841184262014"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p15151719152119"><a name="p15151719152119"></a><a name="p15151719152119"></a>claimName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p2831114232019"><a name="p2831114232019"></a><a name="p2831114232019"></a>已有PVC名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >spec.template.spec.containers.volumeMounts.name和spec.template.spec.volumes.name有映射关系，必须保持一致。

4.  创建有状态工作负载。

    **kubectl create -f  efs-statefulset-example.yaml**


