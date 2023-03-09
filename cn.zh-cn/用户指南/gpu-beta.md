# gpu-beta<a name="cce_10_0141"></a>

## 插件简介<a name="section26181722164712"></a>

gpu-beta插件是支持在容器中使用GPU显卡的设备管理插件，集群中使用GPU节点时必须安装gpu-beta插件。

## 约束与限制<a name="section3200193614201"></a>

-   下载的驱动必须是后缀为“.run“的文件。
-   仅支持Nvidia Tesla驱动，不支持GRID驱动。
-   安装或重装插件时，需要保证驱动下载链接正确且可正常访问，插件对链接有效性不做额外校验。
-   gpu-beta插件仅提供驱动的下载及安装脚本执行功能，插件的状态仅代表插件本身功能正常，与驱动是否安装成功无关。

## 安装插件<a name="section14115341020"></a>

1.  登录CCE控制台，单击集群名称进入集群，在左侧导航栏中选择“插件管理“，在右侧找到**gpu-beta**，单击“安装“。
2.  配置驱动链接地址。

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >-   如果下载链接为公网地址，如nvidia官网地址https://us.download.nvidia.com/tesla/470.103.01/NVIDIA-Linux-x86\_64-470.103.01.run，各GPU节点均需要绑定EIP。获取驱动链接方法请参考[获取驱动链接-公网地址](#section95451728192112)。
    >-   若下载链接为OBS上的链接，无需绑定EIP 。获取驱动链接方法请参考[获取驱动链接-OBS地址](#section14922133914508)。
    >-   请确保Nvidia驱动版本与GPU节点适配。
    >-   更改驱动版本后，需要重启节点才能生效。
    >-   对于linux 5.x内核系统，如Huawei Cloud EulerOS 2.0或ubuntu 22.04，建议使用470及以上版本驱动。

3.  单击“安装“，安装gpu-beta插件的任务即可提交成功。

## 验证插件<a name="section2651166191915"></a>

插件安装完成后，在GPU节点及调度了GPU资源的容器中执行nvidia-smi命令，验证GPU设备及驱动的可用性。

GPU节点

```
cd /opt/cloud/cce/nvidia/bin && ./nvidia-smi
```

容器

```
cd /usr/local/nvidia/bin && ./nvidia-smi
```

能正常返回GPU信息，说明设备可用，插件安装成功。

![](figures/zh-cn_image_0000001238225460.png)

## 获取驱动链接-公网地址<a name="section95451728192112"></a>

1.  登录CCE控制台。
2.  创建节点，在节点规格处选择要创建的GPU节点，选中后下方显示的信息中可以看到节点的GPU显卡型号。

    **图 1**  查看显卡型号<a name="fig21391259134916"></a>  
    ![](figures/查看显卡型号.png "查看显卡型号")


1.  登录到_[https://www.nvidia.com/Download/Find.aspx?lang=cn](https://www.nvidia.com/Download/Find.aspx?lang=cn)_网站。
2.  如[图2](#fig11696366517)所示，在“NVIDIA驱动程序下载“框内选择对应的驱动信息。其中“操作系统“必须选**Linux 64-bit**。

    **图 2**  参数选择<a name="fig11696366517"></a>  
    ![](figures/参数选择.png "参数选择")

3.  驱动信息确认完毕，单击“搜索“按钮，会跳转到驱动信息展示页面，该页面会显示驱动的版本信息如[图3](#fig7873421145213)，单击“下载“到下载页面。

    **图 3**  驱动信息<a name="fig7873421145213"></a>  
    ![](figures/驱动信息.png "驱动信息")

4.  获取驱动软件链接方式分两种：
    -   方式一：如[图4](#fig5901194614534)，在浏览器的链接中找到路径为_url=/tesla/470.103.01/NVIDIA-Linux-x86\_64-470.103.01.run_的路径，补齐全路径[https://us.download.nvidia.com/tesla/470.103.01/NVIDIA-Linux-x86\_64-470.103.01.run](https://us.download.nvidia.com/tesla/470.103.01/NVIDIA-Linux-x86_64-470.103.01.run)该方式节点需要绑定EIP 。
    -   方式二：如[图4](#fig5901194614534)，单击“下载“按钮下载驱动，然后上传到OBS，获取软件的链接，该方式节点不需要绑定EIP。

        **图 4**  获取链接<a name="fig5901194614534"></a>  
        ![](figures/获取链接.png "获取链接")



## 获取驱动链接-OBS地址<a name="section14922133914508"></a>

1.  将驱动上传到对象存储服务OBS中，并将驱动文件设置为公共读，方法请参见[上传文件](https://support.huaweicloud.com/usermanual-obs/zh-cn_topic_0045829661.html)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >节点重启时会重新下载驱动进行安装，请保证驱动的OBS桶链接长期有效。

2.  在OBS管理控制台左侧导航栏选择“对象存储”。
3.  在桶列表单击待操作的桶，进入“概览”页面。
4.  在左侧导航栏，单击“对象”。
5.  选中目标对象，在对象详情页复制驱动链接。

    ![](figures/001.png)


## 相关链接<a name="section16392113515592"></a>

-   [gpu-beta插件及GPU驱动相关问题的排查思路](https://support.huaweicloud.com/cce_faq/cce_faq_00020.html)
-   [工作负载异常：GPU相关](https://support.huaweicloud.com/cce_faq/cce_faq_00109.html)
-   [GPU调度](GPU调度.md)

## 版本记录<a name="section183121449435"></a>

**表 1**  CCE插件版本记录

<a name="table88489551792"></a>
<table><thead align="left"><tr id="row139251455994"><th class="cellrowborder" valign="top" width="37.50531236719082%" id="mcps1.2.3.1.1"><p id="p13601510205420"><a name="p13601510205420"></a><a name="p13601510205420"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="62.494687632809175%" id="mcps1.2.3.1.2"><p id="p156011107542"><a name="p156011107542"></a><a name="p156011107542"></a>支持的集群版本</p>
</th>
</tr>
</thead>
<tbody><tr id="row211118715"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p1670965873"><a name="p1670965873"></a><a name="p1670965873"></a>1.2.20</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p7709356712"><a name="p7709356712"></a><a name="p7709356712"></a>/v1.(19|21|23|25).*/</p>
</td>
</tr>
<tr id="row8757710175517"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p68069151704"><a name="p68069151704"></a><a name="p68069151704"></a>1.2.17</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p1545245719502"><a name="p1545245719502"></a><a name="p1545245719502"></a>/v1.(15|17|19|21|23).*/</p>
</td>
</tr>
<tr id="row17276317105810"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p168067151507"><a name="p168067151507"></a><a name="p168067151507"></a>1.2.15</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p8838386560"><a name="p8838386560"></a><a name="p8838386560"></a>/v1.(15|17|19|21|23).*/</p>
</td>
</tr>
<tr id="row1387115599169"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p887116592167"><a name="p887116592167"></a><a name="p887116592167"></a>1.2.11</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p146501243105614"><a name="p146501243105614"></a><a name="p146501243105614"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row723201855819"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p58061215404"><a name="p58061215404"></a><a name="p58061215404"></a>1.2.10</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p465494345620"><a name="p465494345620"></a><a name="p465494345620"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row19850201865813"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p180611510016"><a name="p180611510016"></a><a name="p180611510016"></a>1.2.9</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p665854385611"><a name="p665854385611"></a><a name="p665854385611"></a>/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row1331711107"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p16807151519016"><a name="p16807151519016"></a><a name="p16807151519016"></a>1.2.2</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p6483174955614"><a name="p6483174955614"></a><a name="p6483174955614"></a>/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row56109111006"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p148078151506"><a name="p148078151506"></a><a name="p148078151506"></a>1.2.1</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p2048784955613"><a name="p2048784955613"></a><a name="p2048784955613"></a>/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row97371611105"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p16807121516018"><a name="p16807121516018"></a><a name="p16807121516018"></a>1.1.13</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p198076155013"><a name="p198076155013"></a><a name="p198076155013"></a>/v1.(13|15|17).*/</p>
</td>
</tr>
<tr id="row1387891111011"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p1480716158015"><a name="p1480716158015"></a><a name="p1480716158015"></a>1.1.11</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p16807515608"><a name="p16807515608"></a><a name="p16807515608"></a>/v1.(15|17).*/</p>
</td>
</tr>
</tbody>
</table>

