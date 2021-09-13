# 使用kubectl部署带文件存储卷的无状态工作负载<a name="cce_01_0263"></a>

## 操作场景<a name="section1062914713566"></a>

文件存储卷创建或导入CCE后，可以在工作负载中挂载文件存储卷。

## 前提条件<a name="section13181839131510"></a>

您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](Everest（系统资源插件-必装）.md)）。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 操作步骤<a name="section1530655595611"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，配置名为“sfs-deployment-example.yaml”的创建Pod的yaml文件。

    **touch sfs-deployment-example.yaml**

    **vi sfs-deployment-example.yaml**

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

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“spec.template.spec.containers.volumeMounts.name” 和 “spec.template.spec.volumes.name”有映射关系，必须保持一致。

3.  执行如下命令创建Pod。

    **kubectl create -f sfs-deployment-example.yaml**

    创建完成后，登录CCE控制台，在左侧导航栏中选择“存储管理 \> 文件存储卷”。单击PVC名称，在PVC详情页面可查看文件存储服务和PVC的绑定关系。


## 相关操作<a name="section184741309122"></a>

[使用subpath类型动态创建SFS Turbo存储卷](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00253.html)

