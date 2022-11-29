# 使用kubectl部署带对象存储卷的无状态工作负载<a name="cce_10_0327"></a>

## 操作场景<a name="section1062914713566"></a>

对象存储卷创建或导入CCE后，可以在工作负载中挂载对象存储卷。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.13及以下版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，配置名为“obs-deployment-example.yaml“的创建Pod的yaml文件。

    **touch obs-deployment-example.yaml**

    **vi obs-deployment-example.yaml**

    在无状态工作负载中基于pvc共享式使用对象存储示例：

    ```
    apiVersion: apps/v1 
    kind: Deployment 
    metadata: 
      name: obs-deployment-example                        # 工作负载名称
      namespace: default 
    spec: 
      replicas: 1 
      selector: 
        matchLabels: 
          app: obs-deployment-example 
      template: 
        metadata: 
          labels: 
            app: obs-deployment-example 
        spec: 
          containers: 
          - image: nginx 
            name: container-0 
            volumeMounts: 
            - mountPath: /tmp                       # 挂载路径
              name: pvc-obs-example 
          restartPolicy: Always
          imagePullSecrets:
            - name: default-secret
          volumes: 
          - name: pvc-obs-example  
            persistentVolumeClaim: 
              claimName: pvc-obs-auto-example       # PVC名称
    ```

    **表 1**  关键参数说明

    <a name="table19249175815503"></a>
    <table><thead align="left"><tr id="row1425005815020"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p1525045817501"><a name="p1525045817501"></a><a name="p1525045817501"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p162501858165014"><a name="p162501858165014"></a><a name="p162501858165014"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1025175814505"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1825125813505"><a name="p1825125813505"></a><a name="p1825125813505"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1134463635714"><a name="p1134463635714"></a><a name="p1134463635714"></a>创建的Pod名称。</p>
    </td>
    </tr>
    <tr id="row17251115805017"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p2025185817509"><a name="p2025185817509"></a><a name="p2025185817509"></a>app</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p9251125875017"><a name="p9251125875017"></a><a name="p9251125875017"></a>Pod工作负载名称。</p>
    </td>
    </tr>
    <tr id="row8251165845018"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p22521858135013"><a name="p22521858135013"></a><a name="p22521858135013"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1525285819508"><a name="p1525285819508"></a><a name="p1525285819508"></a>容器内挂载路径。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name”和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

    在有状态工作负载中基于PVCTemplate独占式使用对象存储。

    **yaml示例如下：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: deploy-obs-standard-in
      namespace: default
      generation: 1
      labels:
        appgroup: ''
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: deploy-obs-standard-in
      template:
        metadata:
          labels:
            app: deploy-obs-standard-in
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: 'true'
        spec:
          containers:
            - name: container-0
              image: 'nginx:1.12-alpine-perl'
              env:
                - name: PAAS_APP_NAME
                  value: deploy-obs-standard-in
                - name: PAAS_NAMESPACE
                  value: default
                - name: PAAS_PROJECT_ID
                  value: a2cd8e998dca42e98a41f596c636dbda
              resources: {}
              volumeMounts:
                - name: obs-bs-standard-mountoptionpvc
                  mountPath: /tmp
              terminationMessagePath: /dev/termination-log
              terminationMessagePolicy: File
              imagePullPolicy: IfNotPresent
          restartPolicy: Always
          terminationGracePeriodSeconds: 30
          dnsPolicy: ClusterFirst
          securityContext: {}
          imagePullSecrets:
            - name: default-secret
          affinity: {}
          schedulerName: default-scheduler
      volumeClaimTemplates:
        - metadata:
            name: obs-bs-standard-mountoptionpvc
            annotations:
              volume.beta.kubernetes.io/storage-class: obs-standard
              volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxiobs
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 1Gi
      serviceName: wwww
      podManagementPolicy: OrderedReady
      updateStrategy:
        type: RollingUpdate
      revisionHistoryLimit: 10
    ```

    **表 2**  关键参数说明

    <a name="table953204119"></a>
    <table><thead align="left"><tr id="row1666206115"><th class="cellrowborder" valign="top" width="26.43%" id="mcps1.2.3.1.1"><p id="p1662017116"><a name="p1662017116"></a><a name="p1662017116"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="73.57000000000001%" id="mcps1.2.3.1.2"><p id="p56820513"><a name="p56820513"></a><a name="p56820513"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1061620713"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p56120115"><a name="p56120115"></a><a name="p56120115"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p911192017111"><a name="p911192017111"></a><a name="p911192017111"></a>创建的工作负载名称。</p>
    </td>
    </tr>
    <tr id="row6115201810"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p1911172013115"><a name="p1911172013115"></a><a name="p1911172013115"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p1812132017111"><a name="p1812132017111"></a><a name="p1812132017111"></a>工作负载的镜像。</p>
    </td>
    </tr>
    <tr id="row181217201317"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p2127205115"><a name="p2127205115"></a><a name="p2127205115"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p151216208112"><a name="p151216208112"></a><a name="p151216208112"></a>容器内挂载路径，示例中挂载到<span class="uicontrol" id="uicontrol712142012120"><a name="uicontrol712142012120"></a><a name="uicontrol712142012120"></a>“/tmp”</span>路径。</p>
    </td>
    </tr>
    <tr id="row101220201616"><td class="cellrowborder" valign="top" width="26.43%" headers="mcps1.2.3.1.1 "><p id="p4121201717"><a name="p4121201717"></a><a name="p4121201717"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p8126203112"><a name="p8126203112"></a><a name="p8126203112"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

3.  执行如下命令创建Pod。

    **kubectl create -f obs-deployment-example.yaml**

    创建完成后，在CCE界面“存储管理 \> 对象存储卷”中单击PVC名称，在PVC详情页面可查看对象存储服务和PVC的绑定关系。


