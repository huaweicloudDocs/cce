# 使用kubectl自动创建云硬盘<a name="cce_01_0255"></a>

## 操作场景<a name="section16500136145518"></a>

CCE支持使用PersistentVolumeClaim（PVC）的形式创建云硬盘。

## 前提条件<a name="section13181839131510"></a>

-   您已经创建好一个CCE集群，并且在该集群中安装CSI插件（[Everest](Everest（系统资源插件-必装）.md)）。
-   您已通过kubectl连接到集群。具体操作请参见[通过kubectl连接集群](通过kubectl连接集群.md)。

## 约束与限制<a name="section946015116135"></a>

如下配置示例适用于Kubernetes 1.15及以上版本的集群。

## 操作步骤<a name="section15671218115516"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，配置名为“pvc-evs-auto-example.yaml”的创建PVC的yaml文件。

    **touch pvc-evs-auto-example.yaml**

    **vi pvc-evs-auto-example.yaml**

    **yaml文件配置示例如下：**

    ```
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      name: pvc-evs-auto-example
      namespace: default
      annotations:
        everest.io/disk-volume-type: SSD
      labels:
        failure-domain.beta.kubernetes.io/region: cn-north-4
        failure-domain.beta.kubernetes.io/zone: cn-north-4b
    spec:
      accessModes:
      - ReadWriteOnce
      resources:
        requests:
          storage: 10Gi
      storageClassName: csi-disk
    ```

    **表 1**  关键参数说明

    <a name="table1819001615355"></a>
    <table><thead align="left"><tr id="row1519121663519"><th class="cellrowborder" valign="top" width="45.34%" id="mcps1.2.3.1.1"><p id="p18191161619356"><a name="p18191161619356"></a><a name="p18191161619356"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="54.66%" id="mcps1.2.3.1.2"><p id="p1919116161353"><a name="p1919116161353"></a><a name="p1919116161353"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row7430236123515"><td class="cellrowborder" valign="top" width="45.34%" headers="mcps1.2.3.1.1 "><p id="p165804616264"><a name="p165804616264"></a><a name="p165804616264"></a>everest.io/disk-volume-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.66%" headers="mcps1.2.3.1.2 "><p id="p94061429143512"><a name="p94061429143512"></a><a name="p94061429143512"></a>云硬盘类型，全大写。</p>
    <p id="p16215174822610"><a name="p16215174822610"></a><a name="p16215174822610"></a>当前支持<span id="text112910427219"><a name="text112910427219"></a><a name="text112910427219"></a>高I/O（SAS）、超高I/O（SSD）</span>。</p>
    </td>
    </tr>
    <tr id="row6232511129"><td class="cellrowborder" valign="top" width="45.34%" headers="mcps1.2.3.1.1 "><p id="p857144622619"><a name="p857144622619"></a><a name="p857144622619"></a>failure-domain.beta.kubernetes.io/region</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.66%" headers="mcps1.2.3.1.2 "><p id="p1880711437456"><a name="p1880711437456"></a><a name="p1880711437456"></a>集群所在的region。</p>
    <p id="p92141648132614"><a name="p92141648132614"></a><a name="p92141648132614"></a>Region对应的值请参见<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。</p>
    </td>
    </tr>
    <tr id="row2318123021219"><td class="cellrowborder" valign="top" width="45.34%" headers="mcps1.2.3.1.1 "><p id="p957446102612"><a name="p957446102612"></a><a name="p957446102612"></a>failure-domain.beta.kubernetes.io/zone</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.66%" headers="mcps1.2.3.1.2 "><p id="p1231415454452"><a name="p1231415454452"></a><a name="p1231415454452"></a>创建云硬盘所在的可用区，必须和工作负载规划的可用区保持一致。</p>
    <p id="p11213204892611"><a name="p11213204892611"></a><a name="p11213204892611"></a>zone对应的值请参见<a href="https://developer.huaweicloud.com/endpoint" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。</p>
    </td>
    </tr>
    <tr id="row163191830121220"><td class="cellrowborder" valign="top" width="45.34%" headers="mcps1.2.3.1.1 "><p id="p4541546112618"><a name="p4541546112618"></a><a name="p4541546112618"></a>storage</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.66%" headers="mcps1.2.3.1.2 "><p id="p1721244813266"><a name="p1721244813266"></a><a name="p1721244813266"></a>存储容量，单位为Gi。</p>
    </td>
    </tr>
    <tr id="row239395619278"><td class="cellrowborder" valign="top" width="45.34%" headers="mcps1.2.3.1.1 "><p id="p1239395612712"><a name="p1239395612712"></a><a name="p1239395612712"></a>storageClassName</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.66%" headers="mcps1.2.3.1.2 "><p id="p6676117163617"><a name="p6676117163617"></a><a name="p6676117163617"></a>存储卷动态供应关联的k8s storage class名称。</p>
    <p id="p739313568271"><a name="p739313568271"></a><a name="p739313568271"></a>v1.15集群使用的csi关联的storage class名称：csi-disk。</p>
    </td>
    </tr>
    <tr id="row2039318566273"><td class="cellrowborder" valign="top" width="45.34%" headers="mcps1.2.3.1.1 "><p id="p8393756112713"><a name="p8393756112713"></a><a name="p8393756112713"></a>accessModes</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.66%" headers="mcps1.2.3.1.2 "><p id="p686319556379"><a name="p686319556379"></a><a name="p686319556379"></a>指定读写模式，显示volume实际具有的访问模式。</p>
    <p id="p183947563277"><a name="p183947563277"></a><a name="p183947563277"></a>1.15集群版本只支持非共享卷，此字段设置为“ReadWriteOnce”。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  执行如下命令创建PVC。

    **kubectl create -f pvc-evs-auto-example.yaml**

    命令执行完成后，会在集群所在分区创建EVS云硬盘，您可以在“存储管理 \> 云硬盘存储卷“中查看该云硬盘，也可以在EVS的控制台中根据卷名称查看该硬盘。


