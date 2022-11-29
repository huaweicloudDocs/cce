# dolphin<a name="cce_10_0371"></a>

## 插件简介<a name="section13441104311208"></a>

dolphin是一款容器网络流量监控管理插件，当前版本可支持从CCE Turbo集群安全容器以及运行时为containerd的普通容器的流量统计。

当前支持流量统计信息ipv4发送公网报文数和字节数、ipv4接收报文数和字节数以及ipv4发送报文数和字节数，且支持通过PodSelector来对监控后端作选择，支持多监控任务、可选监控指标，且支持用户获取Pod的label标签信息。监控信息已适配Prometheus格式，可以通过调用Prometheus接口查看监控数据。

## 使用约束<a name="section9717216192118"></a>

-   仅支持在1.19及以上版本的CCE Turbo集群中安装此插件。
-   仅支持统计CCE Turbo集群**安全容器**（容器运行时为kata）以及普通容器（容器运行时为runc）的流量。
-   安装插件后默认将不进行流量监控，用户需通过创建CR来配置监控任务进行流量监控。
-   安装时请确保节点有足够的资源安装本插件。
-   监控标签及用户标签的来源必须为新创建Pod时就具有的。

## 安装插件<a name="section8920259152115"></a>

1.  登录CCE控制台，单击左侧导航栏的“插件市场”，在“插件市场”中，单击dolphin插件下的“安装”。
2.  在安装插件页面，在“选择集群”步骤中选择集群即可。

## 下发监控任务<a name="section112539251411"></a>

当前用户可通过创建CR的方式下发监控任务，当前用户可以通过API或登录工作节点kubectl apply的方式创建CR，后续将支持前端界面的创建。一个CR代表着一个监控任务，提供selector、podLabel、ip4Tx等可选参数，具体参考以下CR的创建模板：

```
apiVersion: crd.dolphin.io/v1
kind: MonitorPolicy
metadata:
  name: example-task            #监控任务名
  namespace: kube-system        #必填，namespace必须为kube-system
spec:
  selector:                     #选填，配置dolphin插件监控的后端，形如labelSelector格式，默认将监控本节点所有容器
    matchLabels:
      app: nginx
    matchExpressions:
      - key: app
        operator: In
        values:
          - nginx
  podLabel: [app]               #选填，用户标签
  ip4Tx:                        #选填，ipv4发送报文数和发送字节数这两个指标的开关，默认不开
    enable: true
  ip4Rx:                        #选填，ipv4接收报文数和发送字节数这两个指标的开关，默认不开
    enable: true
  ip4TxInternet:                #选填，ipv4发送公网报文数和发送公网字节数这两个指标的开关，默认不开
    enable: true
```

用户标签podLabel：可输入多个Pod的Label标签，以逗号分隔，如\[app, version\]。

标签需符合以下规则，对应正则表达式为\(^\[a-zA-Z\_\]$\)|\(^\(\[a-zA-Z\]\[a-zA-Z0-9\_\]|\_\[a-zA-Z0-9\]\)\(\[a-zA-Z0-9\_\]\)\{0,254\}$\)：

-   支持输入最多5个标签，单个标签长度最长256个字符。
-   不能以数字和双下划线\_\_开头。
-   单个标签格式需符合A-Za-z\_0-9。

示例1：

```
apiVersion: crd.dolphin.io/v1
kind: MonitorPolicy
metadata:
  name: example-task  
  namespace: kube-system        
spec:
  podLabel: [app]
  ip4Tx:
    enable: true
```

上述监控任务名为example-task，将监控节点上所有Pod，生成ipv4发送报文数和发送字节数这两个指标，若监控的容器携带app这个标签，将在监控指标上携带对应label的key-value信息，否则对应label的value为“not found”。

示例2：

```
apiVersion: crd.dolphin.io/v1
kind: MonitorPolicy
metadata:
  name: example-task
  namespace: kube-system
spec:
  selector:
    matchLabels:
      app: nginx
  podLabel: [test, app]
  ip4Tx:
    enable: true
  ip4Rx:
    enable: true
  ip4TxInternet:      
    enable: true
```

上述监控任务名为example-task，将监控节点上满足app=nginx的labelselector的所有Pod，生成全部六个指标，若监控的容器携带test及app这两个标签，将在监控指标上携带对应label的key-value信息，否则对应label的value为“not found”。

用户可以按照上述格式对监控任务进行创建、修改、及删除，当前仅支持最多10个监控任务的创建，且多个监控任务匹配到同一个监控后端时，每一个监控后端将会产生监控任务数量的监控指标。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   修改或删除监控任务，都将导致丢失原有监控任务所采集的监控数据，请谨慎操作。
>-   用户卸载插件后，用户之前配置的监控任务CR将随着插件卸载一并销毁。

## 查看流量统计<a name="section1488381316344"></a>

dolphin插件的监控信息以普罗米修斯exporter格式输出，有两种方式获取dolphin插件的监控信息：

-   安装prometheus插件，prometheus插件会自动对接dolphin插件并周期性采集监控信息。
-   直接访问dophin插件提供的服务端口10001，形如http://\{POD\_IP\}:10001/metrics

注意，如果在节点上访问dolphin服务端口，需要放通节点和pod的安全组限制。

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
<tr id="row1374583031213"><td class="cellrowborder" valign="top" width="40.79%" headers="mcps1.2.3.1.1 "><p id="p1174513091214"><a name="p1174513091214"></a><a name="p1174513091214"></a>ipv4接收报文数</p>
</td>
<td class="cellrowborder" valign="top" width="59.209999999999994%" headers="mcps1.2.3.1.2 "><p id="p13745330181212"><a name="p13745330181212"></a><a name="p13745330181212"></a>ip4_rcv_pkt</p>
</td>
</tr>
<tr id="row67451830151219"><td class="cellrowborder" valign="top" width="40.79%" headers="mcps1.2.3.1.1 "><p id="p674543017121"><a name="p674543017121"></a><a name="p674543017121"></a>ipv4接收字节数</p>
</td>
<td class="cellrowborder" valign="top" width="59.209999999999994%" headers="mcps1.2.3.1.2 "><p id="p1174513014129"><a name="p1174513014129"></a><a name="p1174513014129"></a>ip4_rcv_byte</p>
</td>
</tr>
<tr id="row010017385128"><td class="cellrowborder" valign="top" width="40.79%" headers="mcps1.2.3.1.1 "><p id="p14100163811120"><a name="p14100163811120"></a><a name="p14100163811120"></a>ipv4发送报文数</p>
</td>
<td class="cellrowborder" valign="top" width="59.209999999999994%" headers="mcps1.2.3.1.2 "><p id="p310053871219"><a name="p310053871219"></a><a name="p310053871219"></a>ip4_send_pkt</p>
</td>
</tr>
<tr id="row1610063871220"><td class="cellrowborder" valign="top" width="40.79%" headers="mcps1.2.3.1.1 "><p id="p5100133891215"><a name="p5100133891215"></a><a name="p5100133891215"></a>ipv4发送字节数</p>
</td>
<td class="cellrowborder" valign="top" width="59.209999999999994%" headers="mcps1.2.3.1.2 "><p id="p110053820121"><a name="p110053820121"></a><a name="p110053820121"></a>ip4_send_byte</p>
</td>
</tr>
</tbody>
</table>

-   示例1（ipv4发送公网报文数）：

    ```
    dolphin_ip4_send_pkt_internet{app="nginx",pod="default/nginx-66c9c65dbf-zjg24",task="kube-system/example-task "} 241
    ```

    如上示例中，pod所在命名空间为default，pod名称为nginx-66c9c65dbf-zjg24，用户指定label为app，其值对应为nginx，该监控指标由名称为example-task的监控任务创建，该pod的发送公网报文数为241。

-   示例2（ipv4发送公网字节数）：

    ```
    dolphin_ip4_send_byte_internet{app="nginx",pod="default/nginx-66c9c65dbf-zjg24",task="kube-system/example-task" } 23618
    ```

    如上示例中，pod所在命名空间为default，pod名称为nginx-66c9c65dbf-zjg24，用户指定label为app，其值对应为nginx，该监控指标由名称为example-task的监控任务创建，该pod的发送公网字节数为23618。

-   示例3（ipv4发送报文数）：

    ```
    dolphin_ip4_send_pkt{app="nginx",pod="default/nginx-66c9c65dbf-zjg24",task="kube-system/example-task "} 379
    ```

    如上示例中，pod所在命名空间为default，pod名称为nginx-66c9c65dbf-zjg24，用户指定label为app，其值对应为nginx，该监控指标由名称为example-task的监控任务创建，该pod的发送报文数为379。

-   示例4（ipv4发送字节数）：

    ```
    dolphin_ip4_send_byte{app="nginx",pod="default/nginx-66c9c65dbf-zjg24",task="kube-system/example-task "} 33129
    ```

    如上示例中，pod所在命名空间为default，pod名称为nginx-66c9c65dbf-zjg24，用户指定label为app，其值对应为nginx，该监控指标由名称为example-task的监控任务创建，该pod的发送字节数为33129。


-   示例5（ipv4接收报文数）：

    ```
    dolphin_ip4_rcv_pkt{app="nginx",pod="default/nginx-66c9c65dbf-zjg24",task="kube-system/example-task "} 464
    ```

    如上示例中，pod所在命名空间为default，pod名称为nginx-66c9c65dbf-zjg24，用户指定label为app，其值对应为nginx，该监控指标由名称为example-task的监控任务创建，该pod的接收报文数为464。

-   示例6（ipv4接收字节数）：

    ```
    dolphin_ip4_rcv_byte{app="nginx",pod="default/nginx-66c9c65dbf-zjg24",task="kube-system/example-task "} 34654
    ```

    如上示例中，pod所在命名空间为default，pod名称为nginx-66c9c65dbf-zjg24，用户指定label为app，其值对应为nginx，该监控指标由名称为example-task的监控任务创建，该pod的接收字节数为34654。


>![](public_sys-resources/icon-note.gif) **说明：** 
>若容器无用户指定的标签，返回体中标签值为not found。形如：
>dolphin\_ip4\_send\_byte\_internet\{test="not found", pod="default/nginx-66c9c65dbf-zjg24",task="default" \} 23618

