# dolphin<a name="cce_01_0371"></a>

## 插件简介<a name="section13441104311208"></a>

dolphin是一款容器网络流量监控管理插件，当前版本可支持从CCE Turbo集群安全容器发往公网的流量统计。

当前支持流量统计信息ipv4发送公网报文数和字节数，且支持用户获取Pod的label标签信息。监控信息已适配Prometheus格式，可以通过调用Prometheus接口查看监控数据。

## 使用约束<a name="section9717216192118"></a>

-   仅支持在1.19及以上版本的CCE Turbo集群中安装此插件。
-   仅支持统计CCE Turbo集群**安全容器**（容器运行时为kata）发送到公网的流量。
-   默认监控集群内所有命名空间下的安全容器的流量。

## 安装插件<a name="section8920259152115"></a>

1.  登录CCE控制台，单击左侧导航栏的“插件市场”，在“插件市场”中，单击dolphin插件下的“安装”。
2.  在安装插件页面，在“选择集群”步骤中选择集群。
3.  在”参数配置”步骤中，配置以下参数。
    -   **用户标签**：可输入多个Pod的label标签，以逗号分隔。如”app,version”。

        标签需符合以下规则：

        -   支持输入最多5个标签，单个标签长度最长256个字符
        -   不能以数字和双下划线\_\_开头
        -   单个标签格式需符合A-Za-z\_0-9

        ```
        {
           "user_labels": "app,version"
        }
        ```



## 查看流量统计<a name="section1488381316344"></a>

dolphin插件的监控信息已适配Prometheus格式，您可通过访问Pod的10001端口获取监控信息，如http://\{Pod IP\}:10001/metrics。

您可以通过安装Prometheus插件查看监控信息，Prometheus插件的使用方法请参见[使用Prometheus插件监控](使用Prometheus插件监控.md)。

**表 1**  当前支持的监控指标

<a name="table2561193015209"></a>
<table><thead align="left"><tr id="row2064912306209"><th class="cellrowborder" valign="top" width="40.79%" id="mcps1.2.3.1.1"><p id="p164963012203"><a name="p164963012203"></a><a name="p164963012203"></a>监控指标</p>
</th>
<th class="cellrowborder" valign="top" width="59.209999999999994%" id="mcps1.2.3.1.2"><p id="p2649830192018"><a name="p2649830192018"></a><a name="p2649830192018"></a>对应参数</p>
</th>
</tr>
</thead>
<tbody><tr id="row3649103019209"><td class="cellrowborder" valign="top" width="40.79%" headers="mcps1.2.3.1.1 "><p id="p3649330172011"><a name="p3649330172011"></a><a name="p3649330172011"></a>ipv4发送公网报文数</p>
</td>
<td class="cellrowborder" valign="top" width="59.209999999999994%" headers="mcps1.2.3.1.2 "><p id="p1664923012011"><a name="p1664923012011"></a><a name="p1664923012011"></a>ip4_send_pkt_internet</p>
</td>
</tr>
<tr id="row1964973012201"><td class="cellrowborder" valign="top" width="40.79%" headers="mcps1.2.3.1.1 "><p id="p19649103019204"><a name="p19649103019204"></a><a name="p19649103019204"></a>ipv4发送公网字节数</p>
</td>
<td class="cellrowborder" valign="top" width="59.209999999999994%" headers="mcps1.2.3.1.2 "><p id="p17649123032019"><a name="p17649123032019"></a><a name="p17649123032019"></a>ip4_send_byte_internet</p>
</td>
</tr>
</tbody>
</table>

-   示例1（ipv4发送公网报文数）：

    ```
    dolphin_ip4_send_pkt_internet{app="nginx",pod="default/nginx-66c9c65dbf-zjg24",task="default"} 241
    ```

    如上示例中，Pod所在命名空间为default，Pod名称为nginx-66c9c65dbf-zjg24，Pod的label为app，其值对应为nginx，该Pod的发送公网报文数为241。

-   示例2（ipv4发送公网字节数）：

    ```
    dolphin_ip4_send_byte_internet{app="nginx",pod="default/nginx-66c9c65dbf-zjg24",task="default" } 23618
    ```

    如上示例中，pod所在命名空间为default，pod名称为nginx-66c9c65dbf-zjg24，Pod的label为app，其值对应为nginx，该Pod的发送公网字节数为23618。


>![](public_sys-resources/icon-note.gif) **说明：** 
>若安全容器无用户指定的标签，返回体中标签值为not found。形如：
>dolphin\_ip4\_send\_byte\_internet\{test="not found", pod="default/nginx-66c9c65dbf-zjg24",task="default" \} 23618

## 编辑插件<a name="section098812424361"></a>

当前可通过编辑插件，修改用户标签user\_labels, 获取所需label标签信息。

>![](public_sys-resources/icon-note.gif) **说明：** 
>编辑插件，会先删除原插件，再以新配置信息重新安装插件。安装后所监控pod的流量统计会从零开始重新进行计算。

1.  登录CCE控制台，选择集群，在左侧导航栏中选择“ 插件管理”，在已安装插件中，单击dolphin下的“编辑”。
2.  在弹出的窗口中，修改配置参数后，点击“确定”。

## 卸载插件<a name="section1838144883615"></a>

1.  登录CCE新控制台，选择集群，在左侧导航栏中选择“ 插件管理”，在已安装插件中，单击dolphin下的“卸载”。
2.  在弹出的窗口中，单击“是”，可卸载该插件。

