# gpu-beta<a name="cce_01_0141"></a>

-   [插件简介](#section26181722164712)
-   [约束与限制](#section3200193614201)
-   [安装插件](#section14115341020)
-   [获取驱动链接-公网地址](#section95451728192112)
-   [获取驱动链接-OBS地址](#section14922133914508)
-   [升级插件](#section23441939916)
-   [卸载插件](#section5548228142111)
-   [版本记录](#section144262219109)
-   [相关链接](#section16392113515592)

## 插件简介<a name="section26181722164712"></a>

gpu-beta插件是支持在容器中使用GPU显卡的设备管理插件，仅支持Nvidia驱动。

## 约束与限制<a name="section3200193614201"></a>

-   安装gpu-beta插件的集群中必须包含GPU节点。
-   下载的驱动必须是后缀为“.run“的文件。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>-   若下载链接为公网地址，如Nvidia官网，各GPU节点均需要绑定EIP。
>-   若下载链接为OBS上的链接，无需绑定EIP 。
>-   请确保Nvidia驱动版本与GPU节点适配。
>-   更改驱动版本后，需要重启节点才能生效。

## 安装插件<a name="section14115341020"></a>

1.  登录CCE控制台，在左侧导航栏中选择“插件管理”。在“插件市场”页签下，单击gpu-beta插件下的“安装插件”。
2.  在安装插件页面，选择安装的集群和插件版本，单击“下一步：规格配置”。
3.  在规格配置页面，配置驱动链接地址。

    >![](public_sys-resources/icon-caution.gif) **注意：** 
    >-   如果下载链接为公网地址，如nvidia官网地址https://us.download.nvidia.com/tesla/396.37/NVIDIA-Linux-x86\_64-396.37.run，各GPU节点均需要绑定EIP。获取驱动链接方法请参考[获取驱动链接-公网地址](#section95451728192112)。
    >-   如果下载链接为OBS上的链接，无需绑定EIP。获取驱动链接方法请参考[获取驱动链接-OBS地址](#section14922133914508)。

4.  单击“安装”，安装gpu-beta插件的任务即可提交成功。

    待插件安装完成后，单击“返回“，在“插件实例“页签下，选择对应的集群，可查看到运行中的实例，这表明该插件已在当前集群中各GPU节点上安装。


## 获取驱动链接-公网地址<a name="section95451728192112"></a>

1.  登录到_[https://www.nvidia.cn/Download/Find.aspx?lang=cn](https://www.nvidia.cn/Download/Find.aspx?lang=cn)_网站。
2.  如[图1](#fig11696366517)所示，在“NVIDIA驱动程序下载“框内选择对应的驱动信息。其中“操作系统“必须选**Linux 64-bit**。

    **图 1**  参数选择<a name="fig11696366517"></a>  
    ![](figures/参数选择.png "参数选择")

3.  驱动信息确认完毕，单击“搜索“按钮，会跳转到驱动信息展示页面，该页面会显示驱动的版本信息如[图2](#fig7873421145213)，单击“下载“到下载页面。

    **图 2**  驱动信息<a name="fig7873421145213"></a>  
    ![](figures/驱动信息.png "驱动信息")

4.  获取驱动软件链接方式分两种：
    -   方式一：如[图3](#fig5901194614534)，在浏览器的链接中找到路径为_url=/tesla/396.37/NVIDIA-Linux-x86\_64-396.37.run_的路径，补齐全路径[https://us.download.nvidia.com/tesla/396.37/NVIDIA-Linux-x86\_64-396.37.run](https://us.download.nvidia.com/tesla/396.37/NVIDIA-Linux-x86_64-396.37.run)该方式节点需要绑定EIP 。
    -   方式二：如[图3](#fig5901194614534)，单击“下载“按钮下载驱动，然后上传到OBS，获取软件的链接，该方式节点不需要绑定EIP。

        **图 3**  获取链接<a name="fig5901194614534"></a>  
        ![](figures/获取链接.png "获取链接")



## 获取驱动链接-OBS地址<a name="section14922133914508"></a>

1.  将驱动上传到对象存储服务OBS中，方法请参见[上传文件](https://support.huaweicloud.com/usermanual-obs/zh-cn_topic_0045829661.html)。
2.  在OBS管理控制台左侧导航栏选择“对象存储”。
3.  在桶列表单击待操作的桶，进入“概览”页面。
4.  在左侧导航栏，单击“对象”。
5.  选中目标对象，在对象详情页复制驱动链接。

    ![](figures/001.png)


## 升级插件<a name="section23441939916"></a>

1.  登录[CCE控制台](https://console.huaweicloud.com/cce2.0/?utm_source=helpcenter)，在左侧导航栏中选择“插件管理“，在“插件实例“页签下，选择对应的集群，单击“gpu-beta“下的“升级“。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果升级按钮处于冻结状态，则说明当前插件版本是最新的版本，不需要进行升级操作。
    >-   升级“gpu-beta“插件时，会替换原先节点上的旧版本的“gpu-beta“插件，安装最新版本的“gpu-beta“插件以实现功能的快速升级。

2.  在基本信息页面选择插件版本，单击“下一步“。
3.  参考[安装插件](#section14115341020)中参数说明配置参数后，单击“升级“即可升级“gpu-beta“插件。

## 卸载插件<a name="section5548228142111"></a>

1.  登录CCE控制台，在左侧导航栏中选择“插件管理”。在“插件实例”页签下，选择对应的集群，单击“gpu-beta“下的“卸载“。
2.  在弹出的窗口中，单击“是”，可卸载该插件。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >卸载gpu-beta插件不会卸载驱动。若重新安装了驱动，需重启所有GPU节点。


## 版本记录<a name="section144262219109"></a>

**表 1**  gpu-beta版本记录

<a name="table178175952310"></a>
<table><thead align="left"><tr id="row278175916234"><th class="cellrowborder" valign="top" width="12.148785121487851%" id="mcps1.2.5.1.1"><p id="p37875972314"><a name="p37875972314"></a><a name="p37875972314"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="24.457554244575544%" id="mcps1.2.5.1.2"><p id="p1178135932311"><a name="p1178135932311"></a><a name="p1178135932311"></a>支持的集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="16.60833916608339%" id="mcps1.2.5.1.3"><p id="p178185952316"><a name="p178185952316"></a><a name="p178185952316"></a>更新时间</p>
</th>
<th class="cellrowborder" valign="top" width="46.785321467853215%" id="mcps1.2.5.1.4"><p id="p2078175942320"><a name="p2078175942320"></a><a name="p2078175942320"></a>更新特性</p>
</th>
</tr>
</thead>
<tbody><tr id="row119493597524"><td class="cellrowborder" valign="top" width="12.148785121487851%" headers="mcps1.2.5.1.1 "><p id="p4950195919526"><a name="p4950195919526"></a><a name="p4950195919526"></a>1.1.13</p>
</td>
<td class="cellrowborder" valign="top" width="24.457554244575544%" headers="mcps1.2.5.1.2 "><p id="p18950155919524"><a name="p18950155919524"></a><a name="p18950155919524"></a>混合集群 v1.(13|15|17).*</p>
</td>
<td class="cellrowborder" valign="top" width="16.60833916608339%" headers="mcps1.2.5.1.3 "><p id="p49516599521"><a name="p49516599521"></a><a name="p49516599521"></a>2020/12/16</p>
</td>
<td class="cellrowborder" valign="top" width="46.785321467853215%" headers="mcps1.2.5.1.4 "><p id="p165152910535"><a name="p165152910535"></a><a name="p165152910535"></a>支持Centos76 3.10.0-1127.19.1.el7.x86_64内核系统</p>
</td>
</tr>
<tr id="row152684214528"><td class="cellrowborder" valign="top" width="12.148785121487851%" headers="mcps1.2.5.1.1 "><p id="p16677192210181"><a name="p16677192210181"></a><a name="p16677192210181"></a>1.1.11</p>
</td>
<td class="cellrowborder" valign="top" width="24.457554244575544%" headers="mcps1.2.5.1.2 "><p id="p66771922201811"><a name="p66771922201811"></a><a name="p66771922201811"></a>混合集群 v1.(15|17).*</p>
</td>
<td class="cellrowborder" valign="top" width="16.60833916608339%" headers="mcps1.2.5.1.3 "><p id="p18677172211183"><a name="p18677172211183"></a><a name="p18677172211183"></a>2020/09/19</p>
</td>
<td class="cellrowborder" valign="top" width="46.785321467853215%" headers="mcps1.2.5.1.4 "><p id="p116193110190"><a name="p116193110190"></a><a name="p116193110190"></a>支持用户自定义驱动地址下载驱动，支持1.15，1.17集群</p>
</td>
</tr>
<tr id="row7335155311559"><td class="cellrowborder" valign="top" width="12.148785121487851%" headers="mcps1.2.5.1.1 "><p id="p66776221188"><a name="p66776221188"></a><a name="p66776221188"></a>1.1.10</p>
</td>
<td class="cellrowborder" valign="top" width="24.457554244575544%" headers="mcps1.2.5.1.2 "><p id="p9677822151813"><a name="p9677822151813"></a><a name="p9677822151813"></a>混合集群 v1.(11|13|15|17).*</p>
</td>
<td class="cellrowborder" valign="top" width="16.60833916608339%" headers="mcps1.2.5.1.3 "><p id="p17677622171816"><a name="p17677622171816"></a><a name="p17677622171816"></a>2020/08/19</p>
</td>
<td class="cellrowborder" valign="top" width="46.785321467853215%" headers="mcps1.2.5.1.4 "><p id="p7165531181918"><a name="p7165531181918"></a><a name="p7165531181918"></a>支持用户自定义驱动地址下载驱动，支持1.13，1.15，1.17集群</p>
</td>
</tr>
<tr id="row17524111141813"><td class="cellrowborder" valign="top" width="12.148785121487851%" headers="mcps1.2.5.1.1 "><p id="p10677102212180"><a name="p10677102212180"></a><a name="p10677102212180"></a>1.1.6</p>
</td>
<td class="cellrowborder" valign="top" width="24.457554244575544%" headers="mcps1.2.5.1.2 "><p id="p5677132211182"><a name="p5677132211182"></a><a name="p5677132211182"></a>混合集群 v1.(11|13|15).*</p>
</td>
<td class="cellrowborder" valign="top" width="16.60833916608339%" headers="mcps1.2.5.1.3 "><p id="p1767742231813"><a name="p1767742231813"></a><a name="p1767742231813"></a>2020/02/06</p>
</td>
<td class="cellrowborder" valign="top" width="46.785321467853215%" headers="mcps1.2.5.1.4 "><p id="p0165143118198"><a name="p0165143118198"></a><a name="p0165143118198"></a>同时支持默认的驱动链接地址和用户可自定义驱动地址下载驱动，支持1.13, 1.15集群</p>
</td>
</tr>
<tr id="row20524711182"><td class="cellrowborder" valign="top" width="12.148785121487851%" headers="mcps1.2.5.1.1 "><p id="p1467719222185"><a name="p1467719222185"></a><a name="p1467719222185"></a>1.1.5</p>
</td>
<td class="cellrowborder" valign="top" width="24.457554244575544%" headers="mcps1.2.5.1.2 "><p id="p1282516331918"><a name="p1282516331918"></a><a name="p1282516331918"></a>混合集群 v1.(11|13|15).*</p>
</td>
<td class="cellrowborder" valign="top" width="16.60833916608339%" headers="mcps1.2.5.1.3 "><p id="p196771322101817"><a name="p196771322101817"></a><a name="p196771322101817"></a>2019/12/16</p>
</td>
<td class="cellrowborder" valign="top" width="46.785321467853215%" headers="mcps1.2.5.1.4 "><p id="p6166231161912"><a name="p6166231161912"></a><a name="p6166231161912"></a>同时支持默认的驱动链接地址和用户可自定义驱动地址下载驱动，支持1.13，1.15集群</p>
</td>
</tr>
<tr id="row9487166161815"><td class="cellrowborder" valign="top" width="12.148785121487851%" headers="mcps1.2.5.1.1 "><p id="p867712220180"><a name="p867712220180"></a><a name="p867712220180"></a>1.1.3</p>
</td>
<td class="cellrowborder" valign="top" width="24.457554244575544%" headers="mcps1.2.5.1.2 "><p id="p667732261810"><a name="p667732261810"></a><a name="p667732261810"></a>混合集群 v1.(11|13).*</p>
</td>
<td class="cellrowborder" valign="top" width="16.60833916608339%" headers="mcps1.2.5.1.3 "><p id="p3677182291817"><a name="p3677182291817"></a><a name="p3677182291817"></a>2019/10/17</p>
</td>
<td class="cellrowborder" valign="top" width="46.785321467853215%" headers="mcps1.2.5.1.4 "><p id="p71678315192"><a name="p71678315192"></a><a name="p71678315192"></a>同时支持默认的驱动链接地址和用户可自定义驱动地址下载驱动，支持1.13集群</p>
</td>
</tr>
<tr id="row748718651814"><td class="cellrowborder" valign="top" width="12.148785121487851%" headers="mcps1.2.5.1.1 "><p id="p8677122212183"><a name="p8677122212183"></a><a name="p8677122212183"></a>1.1.2</p>
</td>
<td class="cellrowborder" valign="top" width="24.457554244575544%" headers="mcps1.2.5.1.2 "><p id="p10179191791912"><a name="p10179191791912"></a><a name="p10179191791912"></a>混合集群 v1.(11|13).*</p>
</td>
<td class="cellrowborder" valign="top" width="16.60833916608339%" headers="mcps1.2.5.1.3 "><p id="p1667710221181"><a name="p1667710221181"></a><a name="p1667710221181"></a>2019/09/10</p>
</td>
<td class="cellrowborder" valign="top" width="46.785321467853215%" headers="mcps1.2.5.1.4 "><p id="p191671131101917"><a name="p191671131101917"></a><a name="p191671131101917"></a>同时支持默认的驱动链接地址和用户可自定义驱动地址下载驱动，支持1.13集群</p>
</td>
</tr>
<tr id="row148866181814"><td class="cellrowborder" valign="top" width="12.148785121487851%" headers="mcps1.2.5.1.1 "><p id="p46771322111812"><a name="p46771322111812"></a><a name="p46771322111812"></a>1.1.0</p>
</td>
<td class="cellrowborder" valign="top" width="24.457554244575544%" headers="mcps1.2.5.1.2 "><p id="p16331020171919"><a name="p16331020171919"></a><a name="p16331020171919"></a>混合集群 v1.11.*</p>
</td>
<td class="cellrowborder" valign="top" width="16.60833916608339%" headers="mcps1.2.5.1.3 "><p id="p206771822131812"><a name="p206771822131812"></a><a name="p206771822131812"></a>2019/10/31</p>
</td>
<td class="cellrowborder" valign="top" width="46.785321467853215%" headers="mcps1.2.5.1.4 "><p id="p31684316196"><a name="p31684316196"></a><a name="p31684316196"></a>支持容器里使用GPU显卡的设备管理插件，仅支持nvidia驱动</p>
</td>
</tr>
</tbody>
</table>

## 相关链接<a name="section16392113515592"></a>

-   [gpu-beta插件及GPU驱动相关问题的排查思路](https://support.huaweicloud.com/cce_faq/cce_faq_00020.html)
-   [工作负载异常：GPU相关](https://support.huaweicloud.com/cce_faq/cce_faq_00109.html)

