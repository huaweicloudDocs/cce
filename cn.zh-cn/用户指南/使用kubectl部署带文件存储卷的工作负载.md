# 使用kubectl部署带文件存储卷的工作负载<a name="cce_01_0263"></a>

-   [操作场景](#section1062914713566)
-   [操作步骤](#section1530655595611)

## 操作场景<a name="section1062914713566"></a>

文件存储卷创建或导入CCE后，可以在工作负载中挂载文件存储卷。

## 操作步骤<a name="section1530655595611"></a>

1.  执行如下命令，配置名为“sfs-pod-example.yaml”的创建Pod的yaml文件。

    **_touch sfs-pod-example.yaml_**

    **_vi sfs-pod-example.yaml_**

    在无状态工作负载中基于pvc共享式使用文件存储示例：

    ```
    apiVersion: apps/v1 
    kind: Deployment 
    metadata: 
      name: sfs-pod-example                                # 工作负载名称
      namespace: default 
    spec: 
      replicas: 1 
      selector: 
        matchLabels: 
          app: sfs-pod-example 
      template: 
        metadata: 
          labels: 
            app: sfs-pod-example 
        spec: 
          containers: 
          - image: nginx 
            name: container-0 
            volumeMounts: 
            - mountPath: /tmp                                # 挂载路径
              name: pvc-sfs-example 
          restartPolicy: Always 
          volumes: 
          - name: pvc-sfs-example 
            persistentVolumeClaim: 
              claimName: pvc-sfs-auto-example                # 挂载PVC
    ```

    **表 1**  关键参数说明

    <a name="table397913279106"></a>
    <table><thead align="left"><tr id="row119803273101"><th class="cellrowborder" valign="top" width="38.240815231965676%" id="mcps1.2.4.1.1"><p id="p1615192114317"><a name="p1615192114317"></a><a name="p1615192114317"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.908018235451863%" id="mcps1.2.4.1.2"><p id="p12980132717103"><a name="p12980132717103"></a><a name="p12980132717103"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="44.85116653258247%" id="mcps1.2.4.1.3"><p id="p7981172710104"><a name="p7981172710104"></a><a name="p7981172710104"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row99818271102"><td class="cellrowborder" valign="top" width="38.240815231965676%" headers="mcps1.2.4.1.1 "><p id="p2151921153117"><a name="p2151921153117"></a><a name="p2151921153117"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.908018235451863%" headers="mcps1.2.4.1.2 "><p id="p345291413122"><a name="p345291413122"></a><a name="p345291413122"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="44.85116653258247%" headers="mcps1.2.4.1.3 "><p id="p119811427161017"><a name="p119811427161017"></a><a name="p119811427161017"></a>创建的Pod名称。</p>
    </td>
    </tr>
    <tr id="row15983132715104"><td class="cellrowborder" valign="top" width="38.240815231965676%" headers="mcps1.2.4.1.1 "><p id="p8151102118311"><a name="p8151102118311"></a><a name="p8151102118311"></a>spec.template.spec.containers.volumeMounts</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.908018235451863%" headers="mcps1.2.4.1.2 "><p id="p18404174281219"><a name="p18404174281219"></a><a name="p18404174281219"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="44.85116653258247%" headers="mcps1.2.4.1.3 "><p id="p2098372713107"><a name="p2098372713107"></a><a name="p2098372713107"></a>容器内挂载路径，此处示例中为<span class="uicontrol" id="uicontrol7512144151615"><a name="uicontrol7512144151615"></a><a name="uicontrol7512144151615"></a>“/tmp”</span>。</p>
    </td>
    </tr>
    <tr id="row188911550183213"><td class="cellrowborder" valign="top" width="38.240815231965676%" headers="mcps1.2.4.1.1 "><p id="p425991613812"><a name="p425991613812"></a><a name="p425991613812"></a>spec.template.spec.volumes.persistentVolumeClaim</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.908018235451863%" headers="mcps1.2.4.1.2 "><p id="p14319143031212"><a name="p14319143031212"></a><a name="p14319143031212"></a>claimName</p>
    </td>
    <td class="cellrowborder" valign="top" width="44.85116653258247%" headers="mcps1.2.4.1.3 "><p id="p18319530131211"><a name="p18319530131211"></a><a name="p18319530131211"></a>已有PVC名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name” 和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

    在有状态工作负载中基于PVCTemplate独占式使用文件存储：

    **1.15及以上版本的集群，yaml配置示例如下：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: deploy-sfs-nfs-rw-in
      namespace: default
      generation: 1
      labels:
        appgroup: ''
      annotations:
        container.io/container-0: 'https://console.huaweicloud.com/swr/dockerimage/nginx.png'
        description: ''
    spec:
      replicas: 2
      selector:
        matchLabels:
          app: deploy-sfs-nfs-rw-in
      template:
        metadata:
          labels:
            app: deploy-sfs-nfs-rw-in
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: 'true'
        spec:
          containers:
            - name: container-0
              image: 'nginx:1.12-alpine-perl'
              env:
                - name: PAAS_APP_NAME
                  value: deploy-sfs-nfs-rw-in
                - name: PAAS_NAMESPACE
                  value: default
                - name: PAAS_PROJECT_ID
                  value: 8190a2a1692c46f284585c56fc0e2fb9
              resources: {}
              volumeMounts:
                - name: bs-nfs-rw-mountoptionpvc
                  mountPath: /aaa
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
            name: bs-nfs-rw-mountoptionpvc
            namespace: default
            annotations: {}
            enable: true
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 11Gi
            storageClassName: csi-nas
      serviceName: wwww
      podManagementPolicy: OrderedReady
      updateStrategy:
        type: RollingUpdate
      revisionHistoryLimit: 10
    ```

    **表 2**  关键参数说明

    <a name="table1313172852817"></a>
    <table><thead align="left"><tr id="row31321128132813"><th class="cellrowborder" valign="top" width="34.387351778656125%" id="mcps1.2.4.1.1"><p id="p151822347237"><a name="p151822347237"></a><a name="p151822347237"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.563899868247695%" id="mcps1.2.4.1.2"><p id="p013322819283"><a name="p013322819283"></a><a name="p013322819283"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="47.04874835309617%" id="mcps1.2.4.1.3"><p id="p1713316285282"><a name="p1713316285282"></a><a name="p1713316285282"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row2013332817286"><td class="cellrowborder" valign="top" width="34.387351778656125%" headers="mcps1.2.4.1.1 "><p id="p18182034202319"><a name="p18182034202319"></a><a name="p18182034202319"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.563899868247695%" headers="mcps1.2.4.1.2 "><p id="p181338289284"><a name="p181338289284"></a><a name="p181338289284"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.04874835309617%" headers="mcps1.2.4.1.3 "><p id="p16133128102816"><a name="p16133128102816"></a><a name="p16133128102816"></a>创建的工作负载名称。</p>
    </td>
    </tr>
    <tr id="row2133182815281"><td class="cellrowborder" valign="top" width="34.387351778656125%" headers="mcps1.2.4.1.1 "><p id="p81821534152313"><a name="p81821534152313"></a><a name="p81821534152313"></a>spec.template.spec.containers</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.563899868247695%" headers="mcps1.2.4.1.2 "><p id="p5133128202812"><a name="p5133128202812"></a><a name="p5133128202812"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.04874835309617%" headers="mcps1.2.4.1.3 "><p id="p1813462862814"><a name="p1813462862814"></a><a name="p1813462862814"></a>工作负载的镜像。</p>
    </td>
    </tr>
    <tr id="row11134192816288"><td class="cellrowborder" valign="top" width="34.387351778656125%" headers="mcps1.2.4.1.1 "><p id="p518313482317"><a name="p518313482317"></a><a name="p518313482317"></a>spec.template.spec.containers.volumeMount</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.563899868247695%" headers="mcps1.2.4.1.2 "><p id="p111341428182816"><a name="p111341428182816"></a><a name="p111341428182816"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.04874835309617%" headers="mcps1.2.4.1.3 "><p id="p15134728192813"><a name="p15134728192813"></a><a name="p15134728192813"></a>容器内挂载路径，此处示例中为<span class="uicontrol" id="uicontrol11134162815284"><a name="uicontrol11134162815284"></a><a name="uicontrol11134162815284"></a>“/tmp”</span>。</p>
    </td>
    </tr>
    <tr id="row196132910295"><td class="cellrowborder" valign="top" width="34.387351778656125%" headers="mcps1.2.4.1.1 "><p id="p1718323482320"><a name="p1718323482320"></a><a name="p1718323482320"></a>spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.563899868247695%" headers="mcps1.2.4.1.2 "><p id="p1549152913292"><a name="p1549152913292"></a><a name="p1549152913292"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.04874835309617%" headers="mcps1.2.4.1.3 "><p id="p1796717445293"><a name="p1796717445293"></a><a name="p1796717445293"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

    **1.13及之前集群版本示例：**

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    
    metadata:
      name: deploy-sfs-nfs-rw-in
      namespace: default
      generation: 1
      labels:
        appgroup: ''
      annotations:
        container.io/container-0: 'https://console.huaweicloud.com/swr/dockerimage/nginx.png'
        description: ''
    spec:
      replicas: 2
      selector:
        matchLabels:
          app: deploy-sfs-nfs-rw-in
      template:
        metadata:
          labels:
            app: deploy-sfs-nfs-rw-in
          annotations:
            metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
            pod.alpha.kubernetes.io/initialized: 'true'
        spec:
          containers:
            - name: container-0
              image: 'nginx:1.12-alpine-perl'
              env:
                - name: PAAS_APP_NAME
                  value: deploy-sfs-nfs-rw-in
                - name: PAAS_NAMESPACE
                  value: default
                - name: PAAS_PROJECT_ID
                  value: 8190a2a1692c46f284585c56fc0e2fb9
              resources: {}
              volumeMounts:
                - name: bs-nfs-rw-mountoptionpvc
                  mountPath: /aaa
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
            name: bs-nfs-rw-mountoptionpvc
            creationTimestamp: null
            annotations:
              volume.beta.kubernetes.io/storage-class: nfs-rw
              volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxinfs
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 11Gi
      serviceName: wwww
      podManagementPolicy: OrderedReady
      updateStrategy:
        type: RollingUpdate
      revisionHistoryLimit: 10
    ```

    **表 3**  关键参数说明

    <a name="table14312339123018"></a>
    <table><thead align="left"><tr id="row8312153953015"><th class="cellrowborder" valign="top" width="38.510754151919414%" id="mcps1.2.4.1.1"><p id="p1237415107350"><a name="p1237415107350"></a><a name="p1237415107350"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="20.44650149741356%" id="mcps1.2.4.1.2"><p id="p11312143923015"><a name="p11312143923015"></a><a name="p11312143923015"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="41.04274435066703%" id="mcps1.2.4.1.3"><p id="p13313153914304"><a name="p13313153914304"></a><a name="p13313153914304"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1031311395306"><td class="cellrowborder" valign="top" width="38.510754151919414%" headers="mcps1.2.4.1.1 "><p id="p137431017353"><a name="p137431017353"></a><a name="p137431017353"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.44650149741356%" headers="mcps1.2.4.1.2 "><p id="p10313203914303"><a name="p10313203914303"></a><a name="p10313203914303"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.04274435066703%" headers="mcps1.2.4.1.3 "><p id="p2313133916301"><a name="p2313133916301"></a><a name="p2313133916301"></a>创建的工作负载名称。</p>
    </td>
    </tr>
    <tr id="row731393993011"><td class="cellrowborder" valign="top" width="38.510754151919414%" headers="mcps1.2.4.1.1 "><p id="p237441033513"><a name="p237441033513"></a><a name="p237441033513"></a>spec.template.spec.containers</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.44650149741356%" headers="mcps1.2.4.1.2 "><p id="p143141539123014"><a name="p143141539123014"></a><a name="p143141539123014"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.04274435066703%" headers="mcps1.2.4.1.3 "><p id="p1231423983016"><a name="p1231423983016"></a><a name="p1231423983016"></a>工作负载的镜像。</p>
    </td>
    </tr>
    <tr id="row33147398308"><td class="cellrowborder" valign="top" width="38.510754151919414%" headers="mcps1.2.4.1.1 "><p id="p1237431018356"><a name="p1237431018356"></a><a name="p1237431018356"></a>spec.template.spec.containers.volumeMount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.44650149741356%" headers="mcps1.2.4.1.2 "><p id="p18314439163011"><a name="p18314439163011"></a><a name="p18314439163011"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.04274435066703%" headers="mcps1.2.4.1.3 "><p id="p20314183973011"><a name="p20314183973011"></a><a name="p20314183973011"></a>容器内挂载路径，此处示例中为<span class="uicontrol" id="uicontrol8314239143013"><a name="uicontrol8314239143013"></a><a name="uicontrol8314239143013"></a>“/tmp”</span>。</p>
    </td>
    </tr>
    <tr id="row931415398304"><td class="cellrowborder" valign="top" width="38.510754151919414%" headers="mcps1.2.4.1.1 "><p id="p13374111053511"><a name="p13374111053511"></a><a name="p13374111053511"></a>spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.44650149741356%" headers="mcps1.2.4.1.2 "><p id="p1731415391302"><a name="p1731415391302"></a><a name="p1731415391302"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.04274435066703%" headers="mcps1.2.4.1.3 "><p id="p163146397302"><a name="p163146397302"></a><a name="p163146397302"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

2.  执行如下命令创建Pod。

    **kubectl create -f sfs-pod-example.yaml**

    创建完成后，登录CCE控制台，在左侧导航栏中选择“存储管理 \> 文件存储卷”。单击PVC名称，在PVC详情页面可查看文件存储服务和PVC的绑定关系。


