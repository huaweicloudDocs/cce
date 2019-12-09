# Ingress官方模板介绍<a name="cce_01_0193"></a>

## Ingress模板简介<a name="section6030335144321"></a>

Ingress模板能够一键式部署7层负载组件，负责应用请求的7层转发。

其由ingress-controller和nginx组件组成：

-   ingress-controller：负责监听Kubernetes的Ingress对象，更新nginx配置。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >Ingress的具体说明，请参见[https://kubernetes.io/docs/concepts/services-networking/ingress/](https://kubernetes.io/docs/concepts/services-networking/ingress/)。  

-   nginx：负责请求负载均衡，支持7层转发能力。

Ingress模板支持默认参数安装，也可以在安装界面展开参数进行设置。

## 使用样例<a name="section2467865145551"></a>

以下以安装Ingress模板时选择负载均衡方式为例。

1.  <a name="li4701750163812"></a>部署Ingress模板应用，部署方法请参见[官方模板](官方模板.md)。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >若您需要从Internet访问应用，在安装模板时，请参见[6](官方模板.md#li1358211362176)，选择自定义安装模板，并将访问方式设置为“负载均衡 \( LoadBalancer \)”。  

2.  部署应用。
    1.  <a name="li52420453153421"></a>创建deploy.yaml文件。

        ```
        apiVersion: extensions/v1beta1
        kind: Deployment
        metadata:
          name: test
          labels:
            app: test
        spec:
          replicas: 1
          selector:
            matchLabels:
              app: test
          strategy:
            rollingUpdate:
              maxSurge: 0
              maxUnavailable: 1
            type: RollingUpdate
          template:
            metadata:
              labels:
                app: test
            spec:
              containers:
              - image: ingress-test:1.0
                imagePullPolicy: IfNotPresent
                name: container-0
        ```

        其中，

        -   name：应用名称，用户自定义设置。
        -   selector：通过selector标签匹配应用实例。
        -   labels：应用实例标签，需和selector参数下设置的标签一致。
        -   image：应用镜像地址，用户自定义设置。

    2.  执行如下命令，创建应用。

        **kubectl create -f deploy.yaml**

3.  发布服务。
    1.  <a name="li29175263114238"></a>创建service.yaml文件。

        ```
        apiVersion: v1
        kind: Service
        metadata:
          name: test 
        spec:
          selector:
            app: test
          ports:
          - name: https
            port: 8888
            protocol: TCP
            targetPort: 8888 
          sessionAffinity: ClientIP
          type: ClusterIP
        ```

        其中

        -   name：服务名称，用户自定义设置。
        -   selector：通过selector标签匹配后端应用实例，与[2.a](#li52420453153421)中为selector设置的标签保持一致。
        -   port：服务端口，用户自定义设置。
        -   targetPort：应用本身开放服务端口，用户自定义设置
        -   type：选择服务类型为集群虚拟IP（ClusterIP）类型。

    2.  执行如下命令，创建服务。

        **kubectl create -f service.yaml**

4.  <a name="li46308750165152"></a>（可选）创建secret对象。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >若对外协议为HTTP，则忽略此步骤。  

    1.  创建secret.yaml文件。

        ```
        apiVersion: v1
        data:
          tls.crt: xxxx 
          tls.key: xxxx 
        kind: Secret
        metadata:
          name: test
        type: IngressTLS
        ```

        其中：

        -   tls.crt：base64编码过的证书内容，请确保证书里包含ingress host域名信息，否则无法使用。
        -   tls.key：base64编码过的证书私钥内容。
        -   name：secret对象的名称，用户自定义设置。

    2.  执行如下命令，创建服务。

        **kubectl create -f secret.yaml**

5.  创建Ingress对象。
    1.  <a name="li3879002412919"></a>创建ingress.yaml文件。

        ```
        apiVersion: extensions/v1beta1
        kind: Ingress
        metadata:
          annotations:
            ingress.kubernetes.io/secure-backends: 'false'
            ingress.beta.kubernetes.io/role: data
          labels:
            zone: "data"
            isExternal: "true"
          name: test-ingress
        spec:
          rules:
          - http:
              paths:
              - backend:
                  serviceName: test
                  servicePort: 8888
                path: "/hello"
            host: test.com
          tls:
          - secretName: test
            hosts:
            - test.com
        ```

        其中：

        -   ingress.kubernetes.io/secure-backends：若您的后端协议是HTTP协议，则填写false；若后端协议是HTTPS协议，则填写true。
        -   name：ingress名称，用户自定义设置。
        -   rules：
            -   serviceName：为[3.a](#li29175263114238)设置的服务名称。

            -   servicePort：为[3.a](#li29175263114238)设置的服务端口。
            -   path：为应用路由，用户自定义设置。

            -   host：ingress host域名信息，用户自定义设置。

                若您已申请域名地址，请选择域名方式访问您的应用。


        -   tls：如选择对外协议为HTTPS协议，则根据如下参数说明填写，否则不填写。
            -   secretName：[4](#li46308750165152)创建的secret名称

            -   hosts：与rules下host的值一致。

    2.  执行以下命令，创建Ingress应用。

        **kubectl create -f ingress.yaml**

6.  在浏览器中，输入以下访问地址访问应用。
    -   当选择对外协议为HTTPS协议时：

        _https://\{host\}:\{servicePort\}/\{path\}_

        其中，

        -   \{host\}替换为[5.a](#li3879002412919)中设置的host的值。
        -   \{servicePort\}替换为在[1](#li4701750163812)中配置访问方式时设置的HTTPS服务端口。
        -   \{path\}替换为[5.a](#li3879002412919)中设置的path的值。

    -   当选择对外协议为HTTP协议时：

        _http://\{host\}:\{servicePort\}/\{path\}_

        其中，\{servicePort\}替换为在[1](#li4701750163812)中配置访问方式时设置的HTTP服务端口。



