# 节点访问\(NodePort\)<a name="cce_01_0142"></a>

节点访问 \( NodePort \)是指在每个节点的IP上开放一个静态端口，通过静态端口对外暴露服务。节点访问 \( NodePort \)会路由到ClusterIP服务，这个ClusterIP服务会自动创建。通过请求 <NodeIP\>:<NodePort\>，可以从集群的外部访问一个NodePort服务。

## 产品约束<a name="section8501151104219"></a>

“节点访问 \( NodePort \)“默认为VPC内网访问，如果需要使用弹性IP通过公网访问该服务，请提前在集群的节点上绑定弹性IP。

## 通过控制台操作<a name="section8124108325"></a>

您可以在创建工作负载时通过控制台设置Service访问方式，本节以nginx为例进行说明。

1.  参考[创建无状态负载\(Deployment\)](创建无状态负载(Deployment).md)、[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)或[创建守护进程集\(DaemonSet\)](创建守护进程集(DaemonSet).md)，在“工作负载访问设置“步骤，单击“添加服务“。
    -   **访问类型：**选择“节点访问 \( NodePort \)“。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >如果需要使用弹性IP通过公网访问该服务，请提前在集群的节点上绑定弹性IP。

    -   **Service名称：**自定义服务名称，可与工作负载名称保持一致。
    -   **服务亲和：**
        -   集群级别：集群下所有节点的IP+访问端口均可以访问到此服务关联的负载，服务访问会因路由跳转导致一定性能损失，且无法获取到客户端源IP。
        -   节点级别：只有通过负载所在节点的IP+访问端口才可以访问此服务关联的负载，服务访问没有因路由跳转导致的性能损失，且可以获取到客户端源IP。

    -   **IPv6：**默认不开启，开启后服务的集群内IP地址（ClusterIP）变为IPv6地址，具体请参见[如何通过CCE搭建IPv4/IPv6双栈集群？](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00222.html)。**该功能仅在1.15及以上版本的混合集群开启IPv6功能后显示。**
    -   **端口配置：**
        -   协议：请根据业务的协议类型选择。
        -   容器端口：容器镜像中工作负载实际监听的端口，取值范围为1-65535。
        -   访问端口：容器端口映射到节点私有IP上的端口，建议选择“自动生成“。
            -   自动生成：系统会自动分配端口号。
            -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。


2.  完成配置后，单击“确定“。
3.  单击“下一步：高级设置“进入高级设置页面，直接单击“创建“。
4.  <a name="li13702330143312"></a>单击“查看工作负载详情“，在访问方式页签下获取访问地址，例如“192.168.0.160:30358“。

## kubectl命令行创建<a name="section813715073217"></a>

您可以通过kubectl命令行设置Service访问方式。本节以nginx为例，说明kubectl命令实现节点访问的方法。

**前提条件**

请参见[通过kubectl或web-terminal插件连接CCE集群](通过kubectl或web-terminal插件连接CCE集群.md)配置kubectl命令，使弹性云服务器连接集群。

**操作步骤**

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
        nodePort: 30000
        port: 80
        protocol: TCP
        targetPort: 80
      selector:
        app: nginx
      type: NodePort
    ```

    **表 1**  关键参数说明

    <a name="table56443210447"></a>
    <table><thead align="left"><tr id="row157011325448"><th class="cellrowborder" valign="top" width="19.009999999999998%" id="mcps1.2.4.1.1"><p id="p127013213445"><a name="p127013213445"></a><a name="p127013213445"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.43%" id="mcps1.2.4.1.2"><p id="p070113234410"><a name="p070113234410"></a><a name="p070113234410"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="62.56%" id="mcps1.2.4.1.3"><p id="p870832124415"><a name="p870832124415"></a><a name="p870832124415"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row19708321446"><td class="cellrowborder" valign="top" width="19.009999999999998%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615000_p41087597"><a name="zh-cn_topic_0079615000_p41087597"></a><a name="zh-cn_topic_0079615000_p41087597"></a>nodePort</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.43%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p66528668"><a name="zh-cn_topic_0079615000_p66528668"></a><a name="zh-cn_topic_0079615000_p66528668"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="62.56%" headers="mcps1.2.4.1.3 "><p id="p164654108492"><a name="p164654108492"></a><a name="p164654108492"></a>对应界面上的访问端口，取值范围为30000 ~ 32767，不填写表示自动生成。</p>
    </td>
    </tr>
    <tr id="row2787832142320"><td class="cellrowborder" valign="top" width="19.009999999999998%" headers="mcps1.2.4.1.1 "><p id="p5788113218236"><a name="p5788113218236"></a><a name="p5788113218236"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.43%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p54093956"><a name="zh-cn_topic_0079615000_p54093956"></a><a name="zh-cn_topic_0079615000_p54093956"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="62.56%" headers="mcps1.2.4.1.3 "><p id="p167881320237"><a name="p167881320237"></a><a name="p167881320237"></a>集群虚拟IP的访问端口，取值范围为1 ~ 65535。</p>
    </td>
    </tr>
    <tr id="row13718321449"><td class="cellrowborder" valign="top" width="19.009999999999998%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615000_p11039195"><a name="zh-cn_topic_0079615000_p11039195"></a><a name="zh-cn_topic_0079615000_p11039195"></a>protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.43%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p17699892"><a name="zh-cn_topic_0079615000_p17699892"></a><a name="zh-cn_topic_0079615000_p17699892"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="62.56%" headers="mcps1.2.4.1.3 "><p id="p835181810259"><a name="p835181810259"></a><a name="p835181810259"></a>该端口的IP协议，支持“TCP”和“UDP”。</p>
    </td>
    </tr>
    <tr id="row1671532144412"><td class="cellrowborder" valign="top" width="19.009999999999998%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079615000_p53639231"><a name="zh-cn_topic_0079615000_p53639231"></a><a name="zh-cn_topic_0079615000_p53639231"></a>targetPort</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.43%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p8117426"><a name="zh-cn_topic_0079615000_p8117426"></a><a name="zh-cn_topic_0079615000_p8117426"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="62.56%" headers="mcps1.2.4.1.3 "><p id="p1262218433513"><a name="p1262218433513"></a><a name="p1262218433513"></a>对应界面上的容器端口，取值范围为1 ~ 65535。</p>
    </td>
    </tr>
    <tr id="row371674812911"><td class="cellrowborder" valign="top" width="19.009999999999998%" headers="mcps1.2.4.1.1 "><p id="p6716134816295"><a name="p6716134816295"></a><a name="p6716134816295"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.43%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p18968549"><a name="zh-cn_topic_0079615000_p18968549"></a><a name="zh-cn_topic_0079615000_p18968549"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="62.56%" headers="mcps1.2.4.1.3 "><p id="p13717148202913"><a name="p13717148202913"></a><a name="p13717148202913"></a>对应界面上的访问类型，NodePort表示“节点私有IP”。</p>
    </td>
    </tr>
    </tbody>
    </table>

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


## 验证访问方式<a name="section851316518140"></a>

1.  在管理控制台首页，单击“计算 \>  弹性云服务器“。
2.  在弹性云服务器页面，找到同一VPC内任意一台云服务器，并确认连接到访问地址中IP与端口的安全组是开放的。

    **图 1**  确认安全组开放<a name="fig4156913155815"></a>  
    ![](figures/确认安全组开放.png "确认安全组开放")

3.  单击“远程登录“，弹出登录页面，输入用户密码登录。
4.  使用curl命令访问工作负载验证工作负载是否可以正常访问。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   节点访问\(NodePort\)会在集群内节点上分配一个虚拟IP，即可以在集群内部通过虚拟IP的验证方式验证。其中，虚拟IP访问端口默认与容器端口一致。
    >-   如果需要使用弹性IP通过公网访问该服务，请提前在集群的节点上绑定弹性IP。

    **curl **_192.168.0.160:_30358

    其中“192.168.0.160:30358“为[4](#li13702330143312)中获取到的访问地址，即节点虚拟IP+访问端口。

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


## 工作负载创建完成后设置<a name="section41290043210"></a>

您可以在工作负载创建完成后对Service进行配置，此配置对工作负载状态无影响，且实时生效。具体操作如下：

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“工作负载 \> 无状态负载 Deployment”，在工作负载列表页单击要设置Service的工作负载名称。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果当前Service被关联到Ingress，则更新Service的端口信息后Ingress将不可用，需要删除重建。

2.  在“访问方式“页签，单击“添加Service”。
3.  在“添加Service“页面，访问类型选择“节点访问 \( NodePort \)“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果需要使用弹性IP通过公网访问该服务，请提前在集群的节点上绑定弹性IP。

4.  设置节点访问参数：
    -   **Service名称：**自定义服务名称，可与工作负载名称保持一致。
    -   **集群名称：**工作负载所在集群的名称，此处不可修改。
    -   **命名空间：**工作负载所在命名空间，此处不可修改。
    -   **关联工作负载：**要添加Service的工作负载，此处不可修改。
    -   **服务亲和：**
        -   集群级别：集群下所有节点的IP+访问端口均可以访问到此服务关联的负载，服务访问会因路由跳转导致一定性能损失，且无法获取到客户端源IP。
        -   节点级别：只有通过负载所在节点的IP+访问端口才可以访问此服务关联的负载，服务访问没有因路由跳转导致的性能损失，且可以获取到客户端源IP。

    -   **IPv6：**默认不开启，开启后服务的集群内IP地址（ClusterIP）变为IPv6地址，具体请参见[如何通过CCE搭建IPv4/IPv6双栈集群？](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_00222.html)。**该功能仅在1.15及以上版本的混合集群开启IPv6功能后显示。**
    -   **端口配置：**
        -   协议：请根据业务的协议类型选择。
        -   容器端口：容器镜像中工作负载程序实际监听的端口，需用户确定。nginx程序实际监听的端口为80。
        -   访问端口：容器端口映射到节点私有IP上的端口，建议选择“自动生成“。
            -   自动生成：系统会自动分配端口号。
            -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。


5.  单击“创建”。工作负载已添加“节点访问 \( NodePort \)”的服务。

## 更新Service<a name="section14145190183217"></a>

您可以在添加完Service后，更新此Service的端口配置，操作步骤如下：

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“资源管理 \> 网络管理“，在Service页签下，选择对应的集群和命名空间，单击需要更新端口配置的Service后的“更新“。
2.  在更新Service页面，访问类型选择“节点访问 \( NodePort \)“。
3.  更新节点访问参数：
    -   **Service名称：**您创建的Service名称，此处不可修改。
    -   **集群名称：**工作负载所在集群的名称，此处不可修改。
    -   **命名空间：**工作负载所在命名空间，此处不可修改。
    -   **关联工作负载：**要添加Service的工作负载，此处不可修改。
    -   **IPv6：**该功能仅在1.15及以上版本的混合集群开启IPv6功能后显示，此处不可修改。
    -   **服务亲和：**
        -   集群级别：集群下所有节点的IP+访问端口均可以访问到此服务关联的负载，服务访问会因路由跳转导致一定性能损失，且无法获取到客户端源IP。
        -   节点级别：只有通过负载所在节点的IP+访问端口才可以访问此服务关联的负载，服务访问没有因路由跳转导致的性能损失，且可以获取到客户端源IP。

    -   **端口配置：**
        -   协议：请根据业务的协议类型选择。
        -   容器端口：容器镜像中工作负载程序实际监听的端口，需用户确定。nginx程序实际监听的端口为80。
        -   访问端口：容器端口映射到节点私有IP上的端口，建议选择“自动生成“。
            -   自动生成：系统会自动分配端口号。
            -   指定端口：指定固定的节点端口，默认取值范围为30000-32767。若指定端口时，请确保同个集群内的端口唯一性。


4.  单击“更新”。工作负载已更新Service。

