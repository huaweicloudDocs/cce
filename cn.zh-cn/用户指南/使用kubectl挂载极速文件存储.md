# 使用kubectl挂载极速文件存储<a name="cce_01_0274"></a>

-   [操作场景](#section1062914713566)
-   [操作步骤](#section1530655595611)

## 操作场景<a name="section1062914713566"></a>

极速文件存储创建或导入CCE后，可以在工作负载中挂载极速文件存储。

## 操作步骤<a name="section1530655595611"></a>

1.  执行如下命令，配置名为“efs-pod-example.yaml”的创建Pod的yaml文件。

    **_touch efs-pod-example.yaml_**

    **_vi efs-pod-example.yaml_**

    在无状态工作负载中基于pvc共享式使用极速文件存储示例：

    ```
    apiVersion: apps/v1  
    kind: Deployment  
    metadata:  
      name: efs-pod-example                                # 工作负载名称 
      namespace: default  
    spec:  
      replicas: 1  
      selector:  
        matchLabels:  
          app: efs-pod-example  
      template:  
        metadata:  
          labels:  
            app: efs-pod-example  
        spec:  
          containers:  
          - image: nginx  
            name: container-0  
            volumeMounts:  
            - mountPath: /tmp                                # 挂载路径 
              name: pvc-efs-example  
          restartPolicy: Always  
          volumes:  
          - name: pvc-efs-example  
            persistentVolumeClaim:  
              claimName: pvc-sfs-auto-example                # 挂载PVC
    ```

    **表 1**  关键参数说明

    <a name="table1739110557150"></a>
    <table><thead align="left"><tr id="row439135512158"><th class="cellrowborder" valign="top" width="26.42980935875217%" id="mcps1.2.3.1.1"><p id="p11391105571516"><a name="p11391105571516"></a><a name="p11391105571516"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="73.57019064124783%" id="mcps1.2.3.1.2"><p id="p439255513157"><a name="p439255513157"></a><a name="p439255513157"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row18143134041612"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p11431840161611"><a name="p11431840161611"></a><a name="p11431840161611"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p714434016164"><a name="p714434016164"></a><a name="p714434016164"></a>为创建的Pod名称。</p>
    </td>
    </tr>
    <tr id="row1339295514152"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p83921559156"><a name="p83921559156"></a><a name="p83921559156"></a>app</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p1839395518152"><a name="p1839395518152"></a><a name="p1839395518152"></a>为Pod工作负载名称。</p>
    </td>
    </tr>
    <tr id="row1339365571519"><td class="cellrowborder" valign="top" width="26.42980935875217%" headers="mcps1.2.3.1.1 "><p id="p239365513155"><a name="p239365513155"></a><a name="p239365513155"></a>mountPath</p>
    </td>
    <td class="cellrowborder" valign="top" width="73.57019064124783%" headers="mcps1.2.3.1.2 "><p id="p98841828192311"><a name="p98841828192311"></a><a name="p98841828192311"></a>为容器内挂载路径，此处示例中为“/tmp”。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name” 和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

2.  执行如下命令创建Pod。

    **kubectl create -f efs-pod-example.yaml**

    创建完成后，在CCE界面“存储管理 \> 极速文件存储卷”中单击PVC名称，在PVC详情页面可查看极速文件存储服务和PVC的绑定关系。


