# 使用kubectl挂载极速文件存储<a name="cce_01_0274"></a>

1.  执行如下命令，配置名为“efs-pod-example.yaml”的创建Pod的yaml文件。

    **_touch efs-pod-example.yaml_**

    **_vi efs-pod-example.yaml_**

    在无状态工作负载中基于pvc共享式使用极速文件存储示例：

    ```
    apiVersion: extensions/v1beta1  
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

    其中：

    -   name：为创建的Pod名称。
    -   app：为Pod工作负载名称。
    -   mountPath：为容器内挂载路径，此处示例中为“/tmp”。
    -   “spec.template.spec.containers.volumeMounts.name” 和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

2.  执行如下命令创建Pod。

    **kubectl create -f efs-pod-example.yaml**

    创建完成后，在CCE界面“存储管理 \> 极速文件存储卷”中单击PVC名称，在PVC详情页面可查看极速文件存储服务和PVC的绑定关系。


