# 通过Helm v3客户端部署应用<a name="cce_10_0144"></a>

## 前提条件<a name="zh-cn_topic_0226102212_zh-cn_topic_0179003017_section121301535620"></a>

在CCE中创建的Kubernetes集群已对接kubectl，具体请参见[使用kubectl连接集群](通过kubectl连接集群.md#section37321625113110)。

## 安装Helm v3<a name="zh-cn_topic_0226102212_zh-cn_topic_0179003017_section3719193213815"></a>

本文以Helm v3.3.0为例进行演示。

如需选择其他合适的版本，请访问[https://github.com/helm/helm/releases](https://github.com/helm/helm/releases)。

1.  在连接集群的虚拟机上下载Helm客户端。

    ```
    wget https://get.helm.sh/helm-v3.3.0-linux-amd64.tar.gz
    ```

2.  解压Helm包。

    ```
    tar -xzvf helm-v3.3.0-linux-amd64.tar.gz
    ```

3.  将Helm拷贝到系统path路径下，以下为/usr/local/bin/helm。

    ```
    mv linux-amd64/helm /usr/local/bin/helm
    ```

4.  查看Helm版本。

    ```
    helm version
    version.BuildInfo{Version:"v3.3.0", GitCommit:"e29ce2a54e96cd02ccfce88bee4f58bb6e2a28b6", GitTreeState:"clean", GoVersion:"go1.13.4"}
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
    helm install aerospike/ --generate-name
    ```

3.  安装完成后，执行**helm list**查看已经安装的模板实例状态。

## 常见问题<a name="zh-cn_topic_0226102212_zh-cn_topic_0179003017_section563894210221"></a>

-   **执行Helm version时，提示如下错误信息：**

    ```
    Client:
    &version.Version{SemVer:"v3.3.0",
    GitCommit:"012cb0ac1a1b2f888144ef5a67b8dab6c2d45be6", GitTreeState:"clean"}
    E0718 11:46:10.132102    7023 portforward.go:332] an error occurred
    forwarding 41458 -> 44134: error forwarding port 44134 to pod
    d566b78f997eea6c4b1c0322b34ce8052c6c2001e8edff243647748464cd7919, uid : unable
    to do port forwarding: socat not found.
    Error: cannot connect to Tiller
    ```

    出现上述问题，说明未安装socat，请执行如下命令安装socat。

    **yum install socat -y**

-   **在操作系统为EulerOS 2.9的节点执行yum install socat –y，如报如下错误：**

    No match for argument: socat

    Error: Unable to find a match: socat

    说明镜像未自带socat镜像，请从[https://repo.huaweicloud.com/openeuler/openEuler-20.03-LTS-SP3/everything/x86\_64/Packages/socat-1.7.3.2-8.oe1.x86\_64.rpm](https://repo.huaweicloud.com/openeuler/openEuler-20.03-LTS-SP3/everything/x86_64/Packages/socat-1.7.3.2-8.oe1.x86_64.rpm)  下载rpm包，执行以下命令安装：

    **rpm -i socat-1.7.3.2-8.oe1.x86\_64.rpm**

-   **socat已安装，执行Helm version时，提示如下错误信息：**

    ```
    $ helm version
    Client: &version.Version{SemVer:"v3.3.0", GitCommit:"021cb0ac1a1b2f888144ef5a67b8dab6c2d45be6", GitTreeState:"clean"}
    Error: cannot connect to Tiller
    ```

    Helm模板从“.Kube/config”中读取配置证书和kubernetes进行通讯，出现上述错误信息说明kubectl配置有误，请重新对接kubectl，具体请参见[使用kubectl连接集群](通过kubectl连接集群.md#section37321625113110)。

-   **对接云存储后，存储未创建成功。**

    出现上述问题可能是创建的pvc中annotation字段导致的，请修改模板名称后再次进行安装。

-   **如果kubectl没有配置好，helm install时会出现如下报错：**

    ```
    # helm install prometheus/ --generate-name
    WARNING: This chart is deprecated
    Error: Kubernetes cluster unreachable: Get "http://localhost:8080/version?timeout=32s": dial tcp [::1]:8080: connect: connection refused
    ```

    **解决办法：**给节点配置kubeconfig，配置方法请参见[使用kubectl连接集群](通过kubectl连接集群.md#section37321625113110)。


