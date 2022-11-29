# 通过Helm v2客户端部署应用<a name="cce_10_0420"></a>

>![](public_sys-resources/icon-notice.gif) **须知：** 
>CCE从2022年9月开始，各region将逐步切换至Helm v3。模板管理不再支持Helm v2版本的模板，若您在短期内不能切换至Helm v3，可通过Helm v2 客户端在后台管理v2版本的模板。

## 前提条件<a name="zh-cn_topic_0226102212_zh-cn_topic_0179003017_section121301535620"></a>

在CCE中创建的Kubernetes集群已对接kubectl，具体请参见[使用kubectl连接集群](通过kubectl连接集群.md#section37321625113110)。

## 注意事项<a name="section0109769307"></a>

CCE当前会尝试转换v2模板实例到v3模板实例。若在后台操作Helm v2模板实例，删除实例后，发现CCE 模板管理页面仍有实例信息，单击删除即可。

## 安装Helm v2<a name="section82115226241"></a>

本文以Helm v2.17.0为例进行演示。

如需选择其他合适的版本，请访问[https://github.com/helm/helm/releases](https://github.com/helm/helm/releases)。

1.  在连接集群的虚拟机上下载Helm客户端。

    ```
    wget https://get.helm.sh/helm-v2.17.0-linux-amd64.tar.gz
    ```

2.  解压Helm包。

    ```
    tar -xzvf helm-v2.17.0-linux-amd64.tar.gz
    ```

3.  将helm拷贝到系统path路径下，以下为/usr/local/bin/helm。

    ```
    mv linux-amd64/helm /usr/local/bin/helm
    ```

4.  因为Kubernetes APIServer开启了RBAC访问控制，所以需创建tiller使用的service account:tiller并给其分配cluster-admin这个集群内置的ClusterRole。按如下创建tiller的资源账户。

    **vim tiller-rbac.yaml**

    ```
    apiVersion: v1
    kind: ServiceAccount
    metadata:
      name: tiller
      namespace: kube-system
    ---
    apiVersion: rbac.authorization.k8s.io/v1
    kind: ClusterRoleBinding
    metadata:
      name: tiller
    roleRef:
      apiGroup: rbac.authorization.k8s.io
      kind: ClusterRole
      name: cluster-admin
    subjects:
      - kind: ServiceAccount
        name: tiller
        namespace: kube-system
    ```

5.  部署tiller资源账户。

    ```
    kubectl apply -f tiller-rbac.yaml
    ```

6.  初始化Helm, 部署tiller的Pod。

    ```
    helm init --service-account tiller --skip-refresh
    ```

7.  查看状态。

    ```
    kubectl get pod -n kube-system -l app=helm
    ```

    回显如下

    ```
    NAME                             READY   STATUS    RESTARTS   AGE
    tiller-deploy-7b56c8dfb7-fxk5g   1/1     Running   1          23h
    ```

8.  查看helm版本。

    ```
    # helm version
    Client: &version.Version{SemVer:"v2.17.0", GitCommit:"a690bad98af45b015bd3da1a41f6218b1a451dbe", GitTreeState:"clean"}
    Server: &version.Version{SemVer:"v2.17.0", GitCommit:"a690bad98af45b015bd3da1a41f6218b1a451dbe", GitTreeState:"clean"}
    ```


## 安装Helm模板chart包<a name="zh-cn_topic_0226102212_zh-cn_topic_0179003017_section31686282119"></a>

CCE提供的模板不能满足要求时，可下载模板的chart包进行安装。

**在https://github.com/helm/charts的stable目录中查找您需要的chart包，下载后将chart包上传至节点。**

1.  下载并解压已获取的chart包，一般chart包格式为.zip。

    ```
    unzip chart.zip
    ```

2.  安装Helm模板。

    ```
    helm install aerospike/
    ```

3.  安装完成后，执行**helm list**查看已经安装的模板实例状态。

## 常见问题<a name="zh-cn_topic_0226102212_zh-cn_topic_0179003017_section563894210221"></a>

-   **执行Helm version时，提示如下错误信息：**

    ```
    Client:
    &version.Version{SemVer:"v2.17.0",
    GitCommit:"a690bad98af45b015bd3da1a41f6218b1a451dbe", GitTreeState:"clean"}
    E0718 11:46:10.132102    7023 portforward.go:332] an error occurred
    forwarding 41458 -> 44134: error forwarding port 44134 to pod
    d566b78f997eea6c4b1c0322b34ce8052c6c2001e8edff243647748464cd7919, uid : unable
    to do port forwarding: socat not found.
    Error: cannot connect to Tiller
    ```

    出现上述问题，说明未安装socat，请执行如下命令安装socat。

    ```
    yum install socat -y
    ```

-   **在操作系统为EulerOS 2.9的节点执行yum install socat –y，如报如下错误：**

    No match for argument: socat

    Error: Unable to find a match: socat

    说明镜像未自带socat镜像，请从[https://repo.huaweicloud.com/openeuler/openEuler-20.03-LTS-SP3/everything/x86\_64/Packages/socat-1.7.3.2-8.oe1.x86\_64.rpm](https://repo.huaweicloud.com/openeuler/openEuler-20.03-LTS-SP3/everything/x86_64/Packages/socat-1.7.3.2-8.oe1.x86_64.rpm)  下载rpm包，执行以下命令安装：

    rpm -i socat-1.7.3.2-8.oe1.x86\_64.rpm

-   **socat已安装，执行Helm version时，提示如下错误信息：**

    ```
    test@local:~/k8s/helm/test$ helm version
    Client: &version.Version{SemVer:"v3.3.0", GitCommit:"021cb0ac1a1b2f888144ef5a67b8dab6c2d45be6", GitTreeState:"clean"}
    Error: cannot connect to Tiller
    ```

    Helm模板从“.Kube/config”中读取配置证书和kubernetes进行通讯，出现上述错误信息说明kubectl配置有误，请重新对接kubectl，具体请参见[使用kubectl连接集群](通过kubectl连接集群.md#section37321625113110)。

-   **对接云存储后，存储未创建成功。**

    出现上述问题可能是创建的pvc中annotation字段导致的，请修改模板名称后再次进行安装。

-   **如果kubectl没有配置好，helm install时会出现如下报错：**

    ```
    [root@prometheus-57046 ~]# helm install prometheus/ --generate-name
    WARNING: This chart is deprecated
    Error: Kubernetes cluster unreachable: Get "http://localhost:8080/version?timeout=32s": dial tcp [::1]:8080: connect: connection refused
    ```

    **解决办法：**给节点配置kubeconfig，配置方法请参见[使用kubectl连接集群](通过kubectl连接集群.md#section37321625113110)。


