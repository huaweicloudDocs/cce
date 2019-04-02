# 节点访问 \( NodePort \)<a name="cce_01_0142"></a>

节点访问 \( NodePort \)是指在每个节点的IP上开放一个静态端口，通过静态端口对外暴露服务。节点访问 \( NodePort \)会路由到ClusterIP服务，这个ClusterIP服务会自动创建。通过请求 <NodeIP\>:<NodePort\>，可以从集群的外部访问一个NodePort服务。

节点访问有VPC内网访问或弹性公网IP访问两种方式。

**VPC内网访问**

VPC内网访问是指工作负载可以让同一VPC内其他工作负载访问，通过“集群节点的IP“的服务地址访问。

主要场景：同一VPC内其他工作负载需要访问kubernetes集群内部的工作负载。

**图 1**  VPC内网访问（通过集群节点IP访问）<a name="fig32443742164859"></a>  
![](figures/VPC内网访问（通过集群节点IP访问）.png "VPC内网访问（通过集群节点IP访问）")

**弹性公网IP访问**

弹性公网IP访问可以通过弹性IP从公网访问工作负载，一般用于系统中需要暴露到公网的服务。

弹性IP访问方式需要给集群内任一节点绑定弹性IP，并设置一个映射在节点上的端口，其中节点端口的范围在30000-32767之间，例如访问地址为10.117.117.117:30000。

**图 2**  弹性公网IP访问<a name="fig57690358164948"></a>  
![](figures/弹性公网IP访问.png "弹性公网IP访问")

## 添加方式<a name="section10392205822818"></a>

您可以在创建工作负载时设置访问方式，也可以工作负载创建完成后添加访问方式。

-   方式一：创建工作负载时配置，请参见[通过界面创建](#section8124108325)、[kubectl命令行创建-集群内网访问](#section813715073217)和[kubectl命令行创建-弹性公网IP](#section178584033417)。
-   方式二：工作负载创建完成后设置，请参见[工作负载创建完成后设置](#section41290043210)。

## 更新方式<a name="section8805341122"></a>

您可以在添加完Service后，更新此Service的端口配置，请参见[更新Service端口配置](#section14145190183217)。

## 通过界面创建<a name="section8124108325"></a>

本节以nginx为例进行说明。

1.  参考[创建无状态工作负载](创建无状态工作负载.md)或[创建有状态工作负载](创建有状态工作负载.md)，在“工作负载访问设置“步骤，单击“添加服务“。
    -   访问类型：选择“节点访问 \( NodePort \)“。
    -   服务名称：自定义服务名称，可与工作负载名称保持一致。
    -   端口配置：
        -   协议：请根据业务的协议类型选择。
        -   容器端口：容器镜像中工作负载实际监听的端口，需用户确定。nginx程序实际监听的端口为80。
        -   访问端口：
            -   集群内网访问：容器端口映射到节点私有IP上的端口，用私有IP访问工作负载时使用，端口范围为30000-32767，建议选择“自动生成“。
                -   自动生成：系统会自动分配端口号。
                -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。

            -   弹性公网IP访问：容器端口映射到弹性IP上的端口，用私有IP访问工作负载时使用，端口范围为30000-32767，建议选择“自动生成“。
                -   自动生成：系统会自动分配端口号。
                -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。




2.  单击“下一步“进入“高级设置“页面，直接单击“创建“。
3.  <a name="li13702330143312"></a>单击“查看工作负载详情“，在访问方式页签中获取访问地址，例如“192.168.0.160:30358“。

## 验证访问方式<a name="section851316518140"></a>

**VPC内网访问验证**：

1.  在华为云控制台首页，单击“计算 \>  弹性云服务器“。
2.  在弹性云服务器页面，找到同一VPC内任意一台云服务器，并确认连接到访问地址中IP与端口的安全组是开放的。

    **图 3**  确认安全组开放<a name="fig4156913155815"></a>  
    ![](figures/确认安全组开放.png "确认安全组开放")

3.  单击“远程登录“，弹出登录页面，输入用户密码登录。
4.  使用curl命令访问工作负载验证工作负载是否可以正常访问。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >VPC内网访问方式在集群内也会分配一个集群虚拟IP，即可以在集群内部通过集群虚拟IP的验证方式验证。其中，集群虚拟IP访问端口默认与容器端口一致，例如此示例的访问端口为80端口。  

    **curl **_192.168.0.160:_30358

    其中“192.168.0.160:30358“为[3](#li13702330143312)中获取到的访问地址。

    回显如下表示访问成功。

    ```
    <html>
    <head>
    <title>Welcome to nginx!</title>
    <style>
        body {
            width: 35em;
            margin: 0 auto;
            font-family: Tahoma, Verdana, Arial, sans-serif;
        }
    </style>
    </head>
    <body>
    <h1>Welcome to nginx!</h1>
    <p>If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.</p>
    
    <p>For online documentation and support please refer to
    <a href="http://nginx.org/">nginx.org</a>.<br/>
    Commercial support is available at
    <a href="http://nginx.com/">nginx.com</a>.</p>
    
    <p><em>Thank you for using nginx.</em></p>
    </body>
    </html>
    ```


**弹性公网IP访问验证：**

1.  工作负载创建成功后，单击“工作负载 \> 无状态（Deployment）“或“工作负载 \> 有状态（StatefulSet）“，在工作负载列表页面，单击“查看工作负载详情“进入工作负载详情页，在“访问方式“页签下，获取方式地址，例如“10.78.27.59:30911“。
2.  单击访问地址，即可跳转到访问页面。

    **图 4**  通过弹性IP访问nginx（一）<a name="fig1543716518012"></a>  
    ![](figures/通过弹性IP访问nginx（一）.png "通过弹性IP访问nginx（一）")


## 工作负载创建完成后设置<a name="section41290043210"></a>

登录CCE控制台，选择左侧导航栏的“资源管理 \> 网络管理”，在**Service**页签下，单击“添加Service”。选择类型为“节点访问 \( NodePort \)”。

1.  设置节点访问参数。
    -   服务名称：自定义服务名称，可与工作负载名称保持一致。
    -   集群名称：服务所在集群。
    -   命名空间：服务所在命名空间。
    -   关联工作负载：选择需要添加Service的工作负载。
    -   端口配置：
        -   协议：请根据业务的协议类型选择。
        -   容器端口：容器镜像中工作负载程序实际监听的端口，需用户确定。nginx程序实际监听的端口为80。
        -   访问端口：
            -   集群内网访问：容器端口映射到节点私有IP上的端口，用私有IP访问工作负载时使用，端口范围为30000-32767，建议选择“自动生成“。
                -   自动生成：系统会自动分配端口号。
                -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。

            -   弹性公网IP访问：容器端口映射到弹性IP上的端口，用私有IP访问工作负载时使用，端口范围为30000-32767，建议选择“自动生成“。
                -   自动生成：系统会自动分配端口号。
                -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。




2.  单击“创建”。工作负载已添加“节点访问 \( NodePort \)”的服务。验证操作与[验证访问方式](#section851316518140)相同。

## kubectl命令行创建-集群内网访问<a name="section813715073217"></a>

本节以nginx为例，说明kubectl命令实现VPC内访问的方法。

**前提条件**

请参见[通过Kubectl连接集群](通过Kubectl连接集群.md)配置kubectl命令，使弹性云服务器连接集群。

1.  登录已配置好kubectl命令的弹性云服务器。登录方法请参见[登录Linux弹性云服务器](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0013771089.html)。
2.  创建并编辑nginx-deployment.yaml以及nginx-nodeport-svc.yaml文件。

    其中，nginx-deployment.yaml和nginx-nodeport-svc.yaml为自定义名称，您可以随意命名。

    **vi nginx-deployment.yaml**

    ```
    apiVersion: extensions/v1beta1
    kind: Deployment
    metadata:
      name: nginx
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: nginx
      strategy:
        type: RollingUpdate
      template:
        metadata:
          labels:
            app: nginx
        spec:
          containers:
          - image: nginx 
            imagePullPolicy: Always
            name: nginx
          imagePullSecrets:
          - name: default-secret
    ```

    **vi nginx-nodeport-svc.yaml**

    ```
    apiVersion: v1
    kind: Service
    metadata:
      labels:
        app: nginx
      name: nginx-nodeport
    spec:
      ports:
      - name: service
    #   nodePort: 30000      #对应界面上的访问端口，不填写表示自动生成
        port: 80             #集群虚拟IP的访问端口
        protocol: TCP
        targetPort: 80       #对应界面上的容器端口
      selector:
        app: nginx
      type: NodePort        #对应界面上的访问类型，NodePort表示“节点私有IP”
    ```

3.  创建工作负载。

    **kubectl create -f nginx-deployment.yaml**

    回显如下，表示工作负载已开始创建。

    ```
    deployment "nginx" created
    ```

    **kubectl get po**

    回显如下，工作负载状态为Running，表示工作负载已处于运行状态。

    ```
    NAME                     READY     STATUS             RESTARTS   AGE
    etcd-0                   0/1       ImagePullBackOff   0          48m
    icagent-m9dkt            0/0       Running            0          3d
    nginx-2601814895-qhxqv   1/1       Running            0          9s
    ```

4.  创建服务。

    **kubectl create -f nginx-nodeport-svc.yaml**

    回显如下，表示服务开始创建。

    ```
    service "nginx-nodeport" created
    ```

    **kubectl get svc**

    回显如下，表示服务已创建完成。

    ```
    NAME             TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
    etcd-svc         ClusterIP   None           <none>        3120/TCP       49m
    kubernetes       ClusterIP   10.247.0.1     <none>        443/TCP        3d
    nginx-nodeport   NodePort    10.247.4.225   <none>        80:30000/TCP   7s
    ```

5.  采用curl命令访问工作负载验证工作负载是否可以正常访问。

    **curl **_192.168.2.240:30000_

    其中192.168.2.240为集群中任意一个节点的IP地址，30000为节点开放的端口号。

    回显如下，表示可正常访问。

    ```
    <html>
    <head>
    <title>Welcome to nginx!</title>
    <style>
        body {
            width: 35em;
            margin: 0 auto;
            font-family: Tahoma, Verdana, Arial, sans-serif;
        }
    </style>
    </head>
    <body>
    <h1>Welcome to nginx!</h1>
    <p>If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.</p>
    
    <p>For online documentation and support please refer to
    <a href="http://nginx.org/">nginx.org</a>.<br/>
    Commercial support is available at
    <a href="http://nginx.com/">nginx.com</a>.</p>
    
    <p><em>Thank you for using nginx.</em></p>
    </body>
    </html>
    ```


## kubectl命令行创建-弹性公网IP<a name="section178584033417"></a>

本节以nginx为例，说明kubectl命令实现公网访问的方法。

**前提条件**

请参见[通过Kubectl连接集群](通过Kubectl连接集群.md)配置kubectl命令，使弹性云服务器连接集群。

1.  登录已配置好kubectl命令的弹性云服务器。登录方法请参见[登录Linux弹性云服务器](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0013771089.html)。
2.  创建并编辑nginx-deployment.yaml以及nginx-eip-svc.yaml文件。

    其中，nginx-deployment.yaml和nginx-eip-svc.yaml为自定义名称，您可以随意命名。

    **vi nginx-deployment.yaml**

    ```
    apiVersion: extensions/v1beta1
    kind: Deployment
    metadata:
      name: nginx
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: nginx
      strategy:
        type: RollingUpdate
      template:
        metadata:
          labels:
            app: nginx
        spec:
          containers:
          - image: nginx 
            imagePullPolicy: Always
            name: nginx
          imagePullSecrets:
          - name: default-secret
    ```

    **vi nginx-eip-svc.yaml**

    ```
    apiVersion: v1
    kind: Service
    metadata:
      annotations:
        service.protal.kubernetes.io/type: EIP                #指定外部访问类型为弹性IP
      labels:
        app: nginx
      name: nginx-eip
    spec:
      ports:
      - name: service0
        nodePort: 30000      #对应界面上的访问端口，不填写表示自动生成
        port: 80             #集群虚拟IP的访问端口
        protocol: TCP
        targetPort: 80       #对应界面上的容器端口
      selector:
        app: nginx
      type: NodePort         #弹性IP需要基于NodePort类型的服务
    ```

3.  创建工作负载。

    **kubectl create -f nginx-deployment.yaml**

    回显如下表示工作负载开始创建。

    ```
    deployment "nginx" created
    ```

    **kubectl get po**

    回显如下，工作负载状态为Running，表示工作负载已运行中。

    ```
    NAME                     READY     STATUS             RESTARTS   AGE
    etcd-0                   0/1       ImagePullBackOff   0          59m
    icagent-m9dkt            0/0       Running            0          3d
    nginx-2601814895-sf71t   1/1       Running            0          8s
    ```

4.  创建服务。

    **kubectl create -f nginx-eip-svc.yaml**

    回显如下表示服务已创建成功。

    ```
    service "nginx-eip" created
    ```

    **kubectl get svc**

    回显如下表示服务访问方式已设置成功。

    ```
    NAME         TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
    etcd-svc     ClusterIP   None             <none>        3120/TCP       59m
    kubernetes   ClusterIP   10.247.0.1       <none>        443/TCP        3d
    nginx-eip    NodePort    10.247.120.135   <none>        80:30000/TCP   7s
    ```

5.  在浏览器中输入访问地址，例如为10.78.44.60:30000访问地址。

    其中10.78.44.60为弹性IP地址，30000为上一步中获取的节点端口号。

    **图 5**  通过弹性IP访问nginx（二）<a name="fig6924134814251"></a>  
    ![](figures/通过弹性IP访问nginx（二）.png "通过弹性IP访问nginx（二）")


## 更新Service端口配置<a name="section14145190183217"></a>

1.  登录CCE控制台，选择左侧导航栏的“资源管理 \> 网络管理”，在Service页签下，单击需要更新端口配置的Service的“更新”。
2.  更新端口配置参数。
    -   协议：请根据业务的协议类型选择。
    -   容器端口：工作负载程序实际监听的端口，需用户确定。nginx程序实际监听的端口为80。
    -   访问端口：
        -   集群内网访问：容器端口映射到节点私有IP上的端口，用私有IP访问工作负载时使用，端口范围为30000-32767，建议选择“自动生成“。
            -   自动生成：系统会自动分配端口号。
            -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。

        -   弹性公网IP访问：容器端口映射到弹性IP上的端口，用私有IP访问工作负载时使用，端口范围为30000-32767，建议选择“自动生成“。
            -   自动生成：系统会自动分配端口号。
            -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。



3.  单击“更新”。工作负载已更新Service。验证操作与[验证访问方式](#section851316518140)相同。

