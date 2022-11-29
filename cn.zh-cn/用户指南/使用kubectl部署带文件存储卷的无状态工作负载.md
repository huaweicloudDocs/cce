# 使用kubectl部署带文件存储卷的无状态工作负载<a name="cce_10_0320"></a>

## 操作场景<a name="section1062914713566"></a>

文件存储卷创建或导入CCE后，可以在工作负载中挂载文件存储卷。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.13及以下版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，配置名为“sfs-deployment-example.yaml”的创建Pod的yaml文件。

    **_touch sfs-deployment-example.yaml_**

    **_vi sfs-deployment-example.yaml_**

    在无状态工作负载中基于pvc共享式使用文件存储示例：

    ```
    apiVersion: apps/v1 
    kind: Deployment 
    metadata: 
      name: sfs-deployment-example                                # 工作负载名称
      namespace: default 
    spec: 
      replicas: 1 
      selector: 
        matchLabels: 
          app: sfs-deployment-example 
      template: 
        metadata: 
          labels: 
            app: sfs-deployment-example 
        spec: 
          containers: 
          - image: nginx 
            name: container-0 
            volumeMounts: 
            - mountPath: /tmp                                # 挂载路径
              name: pvc-sfs-example 
          imagePullSecrets:
            - name: default-secret
          restartPolicy: Always 
          volumes: 
          - name: pvc-sfs-example 
            persistentVolumeClaim: 
              claimName: pvc-sfs-auto-example                # 挂载PVC
    ```

    **表 1**  关键参数说明

    <a name="table397913279106"></a>
    <table><thead align="left"><tr id="row119803273101"><th class="cellrowborder" valign="top" width="38.24%" id="mcps1.2.4.1.1"><p id="p1615192114317"><a name="p1615192114317"></a><a name="p1615192114317"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.91%" id="mcps1.2.4.1.2"><p id="p12980132717103"><a name="p12980132717103"></a><a name="p12980132717103"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="44.85%" id="mcps1.2.4.1.3"><p id="p7981172710104"><a name="p7981172710104"></a><a name="p7981172710104"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row99818271102"><td class="cellrowborder" valign="top" width="38.24%" headers="mcps1.2.4.1.1 "><p id="p2151921153117"><a name="p2151921153117"></a><a name="p2151921153117"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.91%" headers="mcps1.2.4.1.2 "><p id="p345291413122"><a name="p345291413122"></a><a name="p345291413122"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="44.85%" headers="mcps1.2.4.1.3 "><p id="p119811427161017"><a name="p119811427161017"></a><a name="p119811427161017"></a>创建的Pod名称。</p>
    </td>
    </tr>
    <tr id="row15983132715104"><td class="cellrowborder" valign="top" width="38.24%" headers="mcps1.2.4.1.1 "><p id="p8151102118311"><a name="p8151102118311"></a><a name="p8151102118311"></a>spec.template.spec.containers.volumeMounts</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.91%" headers="mcps1.2.4.1.2 "><p id="p18404174281219"><a name="p18404174281219"></a><a name="p18404174281219"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="44.85%" headers="mcps1.2.4.1.3 "><p id="p2098372713107"><a name="p2098372713107"></a><a name="p2098372713107"></a>容器内挂载路径，此处示例中为<span class="uicontrol" id="uicontrol7512144151615"><a name="uicontrol7512144151615"></a><a name="uicontrol7512144151615"></a>“/tmp”</span>。</p>
    </td>
    </tr>
    <tr id="row188911550183213"><td class="cellrowborder" valign="top" width="38.24%" headers="mcps1.2.4.1.1 "><p id="p425991613812"><a name="p425991613812"></a><a name="p425991613812"></a>spec.template.spec.volumes.persistentVolumeClaim</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.91%" headers="mcps1.2.4.1.2 "><p id="p14319143031212"><a name="p14319143031212"></a><a name="p14319143031212"></a>claimName</p>
    </td>
    <td class="cellrowborder" valign="top" width="44.85%" headers="mcps1.2.4.1.3 "><p id="p18319530131211"><a name="p18319530131211"></a><a name="p18319530131211"></a>已有PVC名称。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name” 和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

    在有状态工作负载中基于PVCTemplate独占式使用文件存储。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >当前SFS文件存储处于售罄状态，暂时不支持PVCTemplate独占式使用文件存储。

    yaml示例如下：

    ```
    apiVersion: apps/v1
    kind: StatefulSet
    metadata:
      name: deploy-sfs-nfs-rw-in
      namespace: default
      labels:
        appgroup: ''
    spec:
      replicas: 2
      selector:
        matchLabels:
          app: deploy-sfs-nfs-rw-in
      template:
        metadata:
          labels:
            app: deploy-sfs-nfs-rw-in
        spec:
          containers:
            - name: container-0
              image: 'nginx:1.12-alpine-perl'
              volumeMounts:
                - name: bs-nfs-rw-mountoptionpvc
                  mountPath: /aaa
          imagePullSecrets:
            - name: default-secret
      volumeClaimTemplates:
        - metadata:
            name: bs-nfs-rw-mountoptionpvc
            annotations:
              volume.beta.kubernetes.io/storage-class: nfs-rw
              volume.beta.kubernetes.io/storage-provisioner: flexvolume-huawei.com/fuxinfs
          spec:
            accessModes:
              - ReadWriteMany
            resources:
              requests:
                storage: 1Gi
      serviceName: wwww
    ```

    **表 2**  关键参数说明

    <a name="table14312339123018"></a>
    <table><thead align="left"><tr id="row8312153953015"><th class="cellrowborder" valign="top" width="30.45%" id="mcps1.2.4.1.1"><p id="p1237415107350"><a name="p1237415107350"></a><a name="p1237415107350"></a>前置路径</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.04%" id="mcps1.2.4.1.2"><p id="p11312143923015"><a name="p11312143923015"></a><a name="p11312143923015"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="51.51%" id="mcps1.2.4.1.3"><p id="p13313153914304"><a name="p13313153914304"></a><a name="p13313153914304"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1031311395306"><td class="cellrowborder" valign="top" width="30.45%" headers="mcps1.2.4.1.1 "><p id="p137431017353"><a name="p137431017353"></a><a name="p137431017353"></a>metadata</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.4.1.2 "><p id="p10313203914303"><a name="p10313203914303"></a><a name="p10313203914303"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.51%" headers="mcps1.2.4.1.3 "><p id="p2313133916301"><a name="p2313133916301"></a><a name="p2313133916301"></a>创建的工作负载名称。</p>
    </td>
    </tr>
    <tr id="row731393993011"><td class="cellrowborder" valign="top" width="30.45%" headers="mcps1.2.4.1.1 "><p id="p237441033513"><a name="p237441033513"></a><a name="p237441033513"></a>spec.template.spec.containers</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.4.1.2 "><p id="p143141539123014"><a name="p143141539123014"></a><a name="p143141539123014"></a>image</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.51%" headers="mcps1.2.4.1.3 "><p id="p1231423983016"><a name="p1231423983016"></a><a name="p1231423983016"></a>工作负载的镜像。</p>
    </td>
    </tr>
    <tr id="row33147398308"><td class="cellrowborder" valign="top" width="30.45%" headers="mcps1.2.4.1.1 "><p id="p1237431018356"><a name="p1237431018356"></a><a name="p1237431018356"></a>spec.template.spec.containers.volumeMount</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.4.1.2 "><p id="p18314439163011"><a name="p18314439163011"></a><a name="p18314439163011"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.51%" headers="mcps1.2.4.1.3 "><p id="p20314183973011"><a name="p20314183973011"></a><a name="p20314183973011"></a>容器内挂载路径，此处示例中为<span class="uicontrol" id="uicontrol8314239143013"><a name="uicontrol8314239143013"></a><a name="uicontrol8314239143013"></a>“/tmp”</span>。</p>
    </td>
    </tr>
    <tr id="row931415398304"><td class="cellrowborder" valign="top" width="30.45%" headers="mcps1.2.4.1.1 "><p id="p13374111053511"><a name="p13374111053511"></a><a name="p13374111053511"></a>spec</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.04%" headers="mcps1.2.4.1.2 "><p id="p1731415391302"><a name="p1731415391302"></a><a name="p1731415391302"></a>serviceName</p>
    </td>
    <td class="cellrowborder" valign="top" width="51.51%" headers="mcps1.2.4.1.3 "><p id="p163146397302"><a name="p163146397302"></a><a name="p163146397302"></a>工作负载对应的服务，服务创建过程请参见<a href="创建有状态负载(StatefulSet).md">创建有状态负载(StatefulSet)</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name ”和 “spec.volumeClaimTemplates.metadata.name”有映射关系，必须保持一致。

3.  执行如下命令创建Pod。

    **kubectl create -f sfs-deployment-example.yaml**

    创建完成后，登录CCE控制台，在左侧导航栏中选择“存储管理 \> 文件存储卷”。单击PVC名称，在PVC详情页面可查看文件存储服务和PVC的绑定关系。


