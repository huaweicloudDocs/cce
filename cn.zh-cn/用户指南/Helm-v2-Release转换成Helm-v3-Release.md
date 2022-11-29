# Helm v2 Release转换成Helm v3 Release<a name="cce_10_0422"></a>

## 背景介绍<a name="section4905192753813"></a>

当前CCE已全面支持Helm v3版本，用户可通过本指南将已创建的v2 release转换成v3 release，从而更好地使用v3的特性。因Helm v3底层相对于Helm v2来说，一些功能已被弃用或重构，因此转换会有一定风险，需转换前进行模拟转换。

该指南参考社区文档：[https://github.com/helm/helm-2to3](https://github.com/helm/helm-2to3)

## 注意事项：<a name="section15437204914385"></a>

-   Helm v2 release信息存储在configmap中，Helm v3 release信息存储在secrets中。
-   若用户通过前端console操作，在获取实例、更新实例等操作中CCE会自动尝试转换v2模板实例到v3模板实例。若用户仅在后台操作实例，需通过该指南进行转换操作。

## 转换流程（不使用Helm v3客户端）<a name="section10289287395"></a>

1.  在CCE节点上下载helm 2to3 转换插件。

    ```
    wget https://github.com/helm/helm-2to3/releases/download/v0.10.2/helm-2to3_0.10.2_linux_amd64.tar.gz
    ```


1.  解压插件包。

    ```
    tar -xzvf helm-2to3_0.10.2_linux_amd64.tar.gz
    ```


1.  模拟转换。

    以test-convert实例为例，执行以下命令进行转换的模拟。若出现以下提示，说明模拟转换成功。

    ```
    # ./2to3 convert --dry-run --tiller-out-cluster -s configmaps test-convert
    NOTE: This is in dry-run mode, the following actions will not be executed.
    Run without --dry-run to take the actions described below:
    Release "test-convert" will be converted from Helm v2 to Helm v3.
    [Helm 3] Release "test-convert" will be created.
    [Helm 3] ReleaseVersion "test-convert.v1" will be created.
    ```

2.  执行正式转换。若出现以下提示，说明转换成功。

    ```
    # ./2to3 convert --tiller-out-cluster -s configmaps test-convert
    Release "test-convert" will be converted from Helm v2 to Helm v3.
    [Helm 3] Release "test-convert" will be created.
    [Helm 3] ReleaseVersion "test-convert.v1" will be created.
    [Helm 3] ReleaseVersion "test-convert.v1" created.
    [Helm 3] Release "test-convert" created.
    Release "test-convert" was converted successfully from Helm v2 to Helm v3.
    Note: The v2 release information still remains and should be removed to avoid conflicts with the migrated v3 release.
    v2 release information should only be removed using `helm 2to3` cleanup and when all releases have been migrated over.
    ```

3.  转换完成后进行v2 release资源的清理，同样先进行模拟清理，成功后正式清理v2 release资源。

    模拟清理：

    ```
    # ./2to3 cleanup --dry-run --tiller-out-cluster -s configmaps --name test-convert
    NOTE: This is in dry-run mode, the following actions will not be executed.
    Run without --dry-run to take the actions described below:
    WARNING: "Release 'test-convert' Data" will be removed. 
     
    [Cleanup/confirm] Are you sure you want to cleanup Helm v2 data? [y/N]: y
    Helm v2 data will be cleaned up.
    [Helm 2] Release 'test-convert' will be deleted.
    [Helm 2] ReleaseVersion "test-convert.v1" will be deleted.
    ```

    正式清理：

    ```
    # ./2to3 cleanup --tiller-out-cluster -s configmaps --name test-convert
    WARNING: "Release 'test-convert' Data" will be removed. 
     
    [Cleanup/confirm] Are you sure you want to cleanup Helm v2 data? [y/N]: y
    Helm v2 data will be cleaned up.
    [Helm 2] Release 'test-convert' will be deleted.
    [Helm 2] ReleaseVersion "test-convert.v1" will be deleted.
    [Helm 2] ReleaseVersion "test-convert.v1" d
    ```


## 转换流程（使用Helm v3客户端）<a name="section572270144012"></a>

1.  安装Helm v3客户端，参见[安装Helm v3](通过Helm-v3客户端部署应用.md#zh-cn_topic_0226102212_zh-cn_topic_0179003017_section3719193213815)。
2.  安装转换插件。

    ```
    # helm plugin install https://github.com/helm/helm-2to3
    Downloading and installing helm-2to3 v0.10.2 ...
    https://github.com/helm/helm-2to3/releases/download/v0.10.2/helm-2to3_0.10.2_linux_amd64.tar.gz
    Installed plugin: 2to3
    ```

3.  查看已安装的插件，确认插件已安装。

    ```
    # helm plugin list
    NAME VERSION DESCRIPTION                                                               
    2to3  0.10.2      migrate and cleanup Helm v2 configuration and releases in-place to Helm v3
    ```

4.  模拟转换。

    以test-convert实例为例，执行以下命令进行转换的模拟。若出现以下相关提示，说明模拟转换成功。

    ```
    # helm 2to3 convert --dry-run --tiller-out-cluster -s configmaps test-convert
    NOTE: This is in dry-run mode, the following actions will not be executed.
    Run without --dry-run to take the actions described below:
    Release "test-convert" will be converted from Helm v2 to Helm v3.
    [Helm 3] Release "test-convert" will be created.
    [Helm 3] ReleaseVersion "test-convert.v1" will be created.
    ```

5.  执行正式转换。若出现以下提示，说明转换成功。

    ```
    # helm 2to3 convert --tiller-out-cluster -s configmaps test-convert
    Release "test-convert" will be converted from Helm v2 to Helm v3.
    [Helm 3] Release "test-convert" will be created.
    [Helm 3] ReleaseVersion "test-convert.v1" will be created.
    [Helm 3] ReleaseVersion "test-convert.v1" created.
    [Helm 3] Release "test-convert" created.
    Release "test-convert" was converted successfully from Helm v2 to Helm v3.
    Note: The v2 release information still remains and should be removed to avoid conflicts with the migrated v3 release.
    v2 release information should only be removed using `helm 2to3` cleanup and when all releases have been migrated over.
    ```

6.  正式转换成功后，用户可通过helm list查看已转换成功的模板实例。

    ```
    # helm list
    NAME                NAMESPACE    REVISION UPDATED                           STATUS      CHART              APP VERSION
    test-convert      default   1                2022-08-29 06:56:28.166918487 +0000 UTC       deployed    test-helmold-1 
    ```

7.  转换完成后进行V2 release资源的清理，同样先进行模拟清理，成功后正式清理V2 release资源。

    模拟清理：

    ```
    # helm 2to3 cleanup --dry-run --tiller-out-cluster -s configmaps --name test-convert
    NOTE: This is in dry-run mode, the following actions will not be executed.
    Run without --dry-run to take the actions described below:
    WARNING: "Release 'test-convert' Data" will be removed. 
     
    [Cleanup/confirm] Are you sure you want to cleanup Helm v2 data? [y/N]: y
    Helm v2 data will be cleaned up.
    [Helm 2] Release 'test-convert' will be deleted.
    [Helm 2] ReleaseVersion "test-convert.v1" will be deleted.
    ```

    正式清理：

    ```
    # helm 2to3 cleanup --tiller-out-cluster -s configmaps --name test-convert
    WARNING: "Release 'test-convert' Data" will be removed. 
     
    [Cleanup/confirm] Are you sure you want to cleanup Helm v2 data? [y/N]: y
    Helm v2 data will be cleaned up.
    [Helm 2] Release 'test-convert' will be deleted.
    [Helm 2] ReleaseVersion "test-convert.v1" will be deleted.
    [Helm 2] ReleaseVersion "test-convert.v1" deleted.
    [Helm 2] Release 'test-convert' deleted.
    Helm v2 data was cleaned up successfully.
    ```


