# 使用kubectl部署带云硬盘存储卷的工作负载<a name="cce_01_0257"></a>

## 操作场景<a name="section1789161805617"></a>

云硬盘创建或导入CCE后，可以在工作负载中挂载云硬盘。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>云硬盘不支持跨可用区挂载。在挂载前，您可以使用** kubectl get pvc**  命令查询当前集群所在分区下可用PVC。

## 操作步骤<a name="section421772310564"></a>

1.  执行如下命令，配置名为“evs-pod-example.yaml“的创建无状态工作负载的yaml文件。

    **touch evs-pod-example.yaml**

    **vi evs-pod-example.yaml**

    在无状态工作负载中基于pvc共享式使用云硬盘存储示例：

    ```
    apiVersion: apps/v1 
    kind: Deployment 
    metadata: 
      name: evs-pod-example 
      namespace: default 
    spec: 
      replicas: 1 
      selector: 
        matchLabels: 
          app: evs-pod-example 
      template: 
        metadata: 
          labels: 
            app: evs-pod-example 
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
    <table><thead align="left"><tr id="row1519121663519"><th class="cellrowborder" valign="top" width="32.73017562533263%" id="mcps1.2.4.1.1"><p id="p525814169813"><a name="p525814169813"></a><a name="p525814169813"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.147951037786054%" id="mcps1.2.4.1.2"><p id="p18191161619356"><a name="p18191161619356"></a><a name="p18191161619356"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="49.12187333688132%" id="mcps1.2.4.1.3"><p id="p1919116161353"><a name="p1919116161353"></a><a name="p1919116161353"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row7430236123515"><td class="cellrowborder" valign="top" width="32.73017562533263%" headers="mcps1.2.4.1.1 "><p id="p92591716583"><a name="p92591716583"></a><a name="p92591716583"></a>spec.template.spec.containers.volumeMounts</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.147951037786054%" headers="mcps1.2.4.1.2 "><p id="p116341334126"><a name="p116341334126"></a><a name="p116341334126"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.12187333688132%" headers="mcps1.2.4.1.3 "><p id="p1927814583433"><a name="p1927814583433"></a><a name="p1927814583433"></a>容器内挂载卷的名称。</p>
    </td>
    </tr>
    <tr id="row10639194016187"><td class="cellrowborder" valign="top" width="32.73017562533263%" headers="mcps1.2.4.1.1 "><p id="p54664413187"><a name="p54664413187"></a><a name="p54664413187"></a>spec.template.spec.containers.volumeMounts</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.147951037786054%" headers="mcps1.2.4.1.2 "><p id="p1946674110189"><a name="p1946674110189"></a><a name="p1946674110189"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.12187333688132%" headers="mcps1.2.4.1.3 "><p id="p546684111182"><a name="p546684111182"></a><a name="p546684111182"></a>容器内挂载路径，示例中挂载到“/tmp”路径。</p>
    </td>
    </tr>
    <tr id="row6232511129"><td class="cellrowborder" valign="top" width="32.73017562533263%" headers="mcps1.2.4.1.1 "><p id="p72592169811"><a name="p72592169811"></a><a name="p72592169811"></a>spec.template.spec.volumes</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.147951037786054%" headers="mcps1.2.4.1.2 "><p id="p192525131213"><a name="p192525131213"></a><a name="p192525131213"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.12187333688132%" headers="mcps1.2.4.1.3 "><p id="p132182510120"><a name="p132182510120"></a><a name="p132182510120"></a>卷的名称。</p>
    </td>
    </tr>
    <tr id="row163191830121220"><td class="cellrowborder" valign="top" width="32.73017562533263%" headers="mcps1.2.4.1.1 "><p id="p425991613812"><a name="p425991613812"></a><a name="p425991613812"></a>spec.template.spec.volumes.persistentVolumeClaim</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.147951037786054%" headers="mcps1.2.4.1.2 "><p id="p14319143031212"><a name="p14319143031212"></a><a name="p14319143031212"></a>claimName</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.12187333688132%" headers="mcps1.2.4.1.3 "><p id="p18319530131211"><a name="p18319530131211"></a><a name="p18319530131211"></a>已有PVC名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name ”和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

    在有状态工作负载中基于PVCTemplate独占式使用云硬盘存储示例：

    -   **1.15及以上版本的集群，yaml示例如下：**

        ```
        apiVersion: apps/v1
        kind: StatefulSet
        metadata:
          name: deploy-evs-sata-in
          namespace: default
          generation: 1
          labels:
            appgroup: ''
          annotations:
            container.io/container-0: https://console.huaweicloud.com/swr/dockerimage/nginx.png
            description: ''
        spec:
          replicas: 1
          selector:
            matchLabels:
              app: deploy-evs-sata-in
              failure-domain.beta.kubernetes.io/region: cn-north-4
              failure-domain.beta.kubernetes.io/zone: cn-north-4a
          template:
            metadata:
              labels:
                app: deploy-evs-sata-in
                failure-domain.beta.kubernetes.io/region: cn-north-4
                failure-domain.beta.kubernetes.io/zone: cn-north-4a
              annotations:
                metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
                pod.alpha.kubernetes.io/initialized: 'true'
            spec:
              containers:
                - name: container-0
                  image: 'nginx:1.12-alpine-perl'
                  env:
                    - name: PAAS_APP_NAME
                      value: deploy-evs-sata-in
                    - name: PAAS_NAMESPACE
                      value: default
                    - name: PAAS_PROJECT_ID
                      value: a2cd8e998dca42e98a41f596c636dbda
                  resources: {}
                  volumeMounts:
                    - name: bs-sata-mountoptionpvc
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
                name: bs-sata-mountoptionpvc
                namespace: default
                annotations:
                  everest.io/disk-volume-type: SATA
              spec:
                accessModes:
                  - ReadWriteOnce
                resources:
                  requests:
                    storage: 10Gi
                storageClassName: csi-disk   
          serviceName: wwww
          podManagementPolicy: OrderedReady
          updateStrategy:
            type: RollingUpdate
          revisionHistoryLimit: 10
        ```

        **表 2**  关键参数说明

        <a name="table178541528175011"></a>
        <table><thead align="left"><tr id="row148549288509"><th class="cellrowborder" valign="top" width="30.565275908479144%" id="mcps1.2.4.1.1"><p id="p151822347237"><a name="p151822347237"></a><a name="p151822347237"></a>前置路径</p>
        </th>
        <th class="cellrowborder" valign="top" width="16.150740242261104%" id="mcps1.2.4.1.2"><p id="p1285412815015"><a name="p1285412815015"></a><a name="p1285412815015"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="53.28398384925976%" id="mcps1.2.4.1.3"><p id="p9854162825019"><a name="p9854162825019"></a><a name="p9854162825019"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1485422813506"><td class="cellrowborder" valign="top" width="30.565275908479144%" headers="mcps1.2.4.1.1 "><p id="p18182034202319"><a name="p18182034202319"></a><a name="p18182034202319"></a>metadata</p>
        </td>
        <td class="cellrowborder" valign="top" width="16.150740242261104%" headers="mcps1.2.4.1.2 "><p id="p58541728145016"><a name="p58541728145016"></a><a name="p58541728145016"></a>name</p>
        </td>
        <td class="cellrowborder" valign="top" width="53.28398384925976%" headers="mcps1.2.4.1.3 "><p id="p88541128115014"><a name="p88541128115014"></a><a name="p88541128115014"></a>创建的工作负载名称。</p>
        </td>
        </tr>
        <tr id="row1185413289501"><td class="cellrowborder" valign="top" width="30.565275908479144%" headers="mcps1.2.4.1.1 "><p id="p81821534152313"><a name="p81821534152313"></a><a name="p81821534152313"></a>spec.template.spec.containers</p>
        </td>
        <td class="cellrowborder" valign="top" width="16.150740242261104%" headers="mcps1.2.4.1.2 "><p id="p385452810506"><a name="p385452810506"></a><a name="p385452810506"></a>image</p>
        </td>
        <td class="cellrowborder" valign="top" width="53.28398384925976%" headers="mcps1.2.4.1.3 "><p id="p685442865018"><a name="p685442865018"></a><a name="p685442865018"></a>工作负载的镜像。</p>
        </td>
        </tr>
        <tr id="row385415281508"><td class="cellrowborder" valign="top" width="30.565275908479144%" headers="mcps1.2.4.1.1 "><p id="p518313482317"><a name="p518313482317"></a><a name="p518313482317"></a>spec.template.spec.containers.volumeMount</p>
        </td>
        <td class="cellrowborder" valign="top" width="16.150740242261104%" headers="mcps1.2.4.1.2 "><p id="p38541928175017"><a name="p38541928175017"></a><a name="p38541928175017"></a>mountPath</p>
        </td>
        <td class="cellrowborder" valign="top" width="53.28398384925976%" headers="mcps1.2.4.1.3 "><p id="p1485518283507"><a name="p1485518283507"></a><a name="p1485518283507"></a>容器内挂载路径，示例中挂载到“/tmp”路径。</p>
        </td>
        </tr>
        <tr id="row1585562835012"><td class="cellrowborder" valign="top" width="30.565275908479144%" headers="mcps1.2.4.1.1 "><p id="p1718323482320"><a name="p1718323482320"></a><a name="p1718323482320"></a>spec</p>
        </td>
        <td class="cellrowborder" valign="top" width="16.150740242261104%" headers="mcps1.2.4.1.2 "><p id="p1285512281506"><a name="p1285512281506"></a><a name="p1285512281506"></a>serviceName</p>
        </td>
        <td class="cellrowborder" valign="top" width="53.28398384925976%" headers="mcps1.2.4.1.3 "><p id="p17855152895015"><a name="p17855152895015"></a><a name="p17855152895015"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
        </td>
        </tr>
        </tbody>
        </table>

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >“spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

    -   **1.13及之前版本，yaml示例如下：**

        ```
        apiVersion: apps/v1
        kind: StatefulSet
        metadata:
          name: deploy-evs-sata-in
          namespace: default
          generation: 1
          labels:
            appgroup: ''
          annotations:
            container.io/container-0: https://console.huaweicloud.com/swr/dockerimage/nginx.png
            description: ''
        spec:
          replicas: 1
          selector:
            matchLabels:
              app: deploy-evs-sata-in
              failure-domain.beta.kubernetes.io/region: cn-north-4
              failure-domain.beta.kubernetes.io/zone: cn-north-4a
          template:
            metadata:
              labels:
                app: deploy-evs-sata-in
                failure-domain.beta.kubernetes.io/region: cn-north-4
                failure-domain.beta.kubernetes.io/zone: cn-north-4a
              annotations:
                metrics.alpha.kubernetes.io/custom-endpoints: '[{"api":"","path":"","port":"","names":""}]'
                pod.alpha.kubernetes.io/initialized: 'true'
            spec:
              containers:
                - name: container-0
                  image: 'nginx:1.12-alpine-perl'
                  env:
                    - name: PAAS_APP_NAME
                      value: deploy-evs-sata-in
                    - name: PAAS_NAMESPACE
                      value: default
                    - name: PAAS_PROJECT_ID
                      value: a2cd8e998dca42e98a41f596c636dbda
                  resources: {}
                  volumeMounts:
                    - name: bs-sata-mountoptionpvc
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
                name: bs-sata-mountoptionpvc
                annotations:
                  volume.beta.kubernetes.io/storage-class: sata
                  volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxivol
        
              spec:
                accessModes:
                  - ReadWriteMany
                resources:
                  requests:
                    storage: 10Gi
          serviceName: wwww
          podManagementPolicy: OrderedReady
          updateStrategy:
            type: RollingUpdate
          revisionHistoryLimit: 10
        ```

        **表 3**  关键参数说明

        <a name="table628368131916"></a>
        <table><thead align="left"><tr id="row122837851917"><th class="cellrowborder" valign="top" width="27.011109623878998%" id="mcps1.2.4.1.1"><p id="p24390324267"><a name="p24390324267"></a><a name="p24390324267"></a>前置路径</p>
        </th>
        <th class="cellrowborder" valign="top" width="17.588006960246286%" id="mcps1.2.4.1.2"><p id="p42830816196"><a name="p42830816196"></a><a name="p42830816196"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="55.400883415874716%" id="mcps1.2.4.1.3"><p id="p16284108101912"><a name="p16284108101912"></a><a name="p16284108101912"></a>描述</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1428438101916"><td class="cellrowborder" valign="top" width="27.011109623878998%" headers="mcps1.2.4.1.1 "><p id="p143914327264"><a name="p143914327264"></a><a name="p143914327264"></a>metadata</p>
        </td>
        <td class="cellrowborder" valign="top" width="17.588006960246286%" headers="mcps1.2.4.1.2 "><p id="p142843811197"><a name="p142843811197"></a><a name="p142843811197"></a>name</p>
        </td>
        <td class="cellrowborder" valign="top" width="55.400883415874716%" headers="mcps1.2.4.1.3 "><p id="p14367283124"><a name="p14367283124"></a><a name="p14367283124"></a>创建的工作负载名称。</p>
        </td>
        </tr>
        <tr id="row428458201916"><td class="cellrowborder" valign="top" width="27.011109623878998%" headers="mcps1.2.4.1.1 "><p id="p104391325267"><a name="p104391325267"></a><a name="p104391325267"></a>spec.template.spec.containers</p>
        </td>
        <td class="cellrowborder" valign="top" width="17.588006960246286%" headers="mcps1.2.4.1.2 "><p id="p202841483196"><a name="p202841483196"></a><a name="p202841483196"></a>image</p>
        </td>
        <td class="cellrowborder" valign="top" width="55.400883415874716%" headers="mcps1.2.4.1.3 "><p id="p11284585196"><a name="p11284585196"></a><a name="p11284585196"></a>工作负载的镜像。</p>
        </td>
        </tr>
        <tr id="row192841589190"><td class="cellrowborder" valign="top" width="27.011109623878998%" headers="mcps1.2.4.1.1 "><p id="p243920327269"><a name="p243920327269"></a><a name="p243920327269"></a>spec.template.spec.containers.volumeMount</p>
        </td>
        <td class="cellrowborder" valign="top" width="17.588006960246286%" headers="mcps1.2.4.1.2 "><p id="p32847817196"><a name="p32847817196"></a><a name="p32847817196"></a>mountPath</p>
        </td>
        <td class="cellrowborder" valign="top" width="55.400883415874716%" headers="mcps1.2.4.1.3 "><p id="p112851818196"><a name="p112851818196"></a><a name="p112851818196"></a>容器内挂载路径，示例中挂载到“/tmp”路径。</p>
        </td>
        </tr>
        <tr id="row6285158191916"><td class="cellrowborder" valign="top" width="27.011109623878998%" headers="mcps1.2.4.1.1 "><p id="p2043914322263"><a name="p2043914322263"></a><a name="p2043914322263"></a>spec</p>
        </td>
        <td class="cellrowborder" valign="top" width="17.588006960246286%" headers="mcps1.2.4.1.2 "><p id="p1828558101912"><a name="p1828558101912"></a><a name="p1828558101912"></a>serviceName</p>
        </td>
        <td class="cellrowborder" valign="top" width="55.400883415874716%" headers="mcps1.2.4.1.3 "><p id="p415683820207"><a name="p415683820207"></a><a name="p415683820207"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
        </td>
        </tr>
        </tbody>
        </table>

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >“spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。


2.  执行如下命令创建Pod。

    **kubectl create -f evs-pod-example.yaml**

    创建完成后，登录CCE控制台，在左侧导航栏中选择“存储管理 \> 云硬盘存储卷“。单击PVC名称，在PVC详情页面可查看云硬盘和PVC的绑定关系。


