# CCE安全使用指引<a name="cce_01_0165"></a>

CCE给用户提供的是一个独享集群，不建议以共享集群方式为多租户使用。当用户以共享集群的方式提供给多租户使用时，请参考如下容器安全使用建议进行安全加固。

**表 1**  容器安全使用建议

<a name="table12889543132716"></a>
<table><thead align="left"><tr id="row293124312279"><th class="cellrowborder" valign="top" width="22.7%" id="mcps1.2.3.1.1"><p id="p538513235313"><a name="p538513235313"></a><a name="p538513235313"></a>分类</p>
</th>
<th class="cellrowborder" valign="top" width="77.3%" id="mcps1.2.3.1.2"><p id="p29311043102715"><a name="p29311043102715"></a><a name="p29311043102715"></a>安全使用建议</p>
</th>
</tr>
</thead>
<tbody><tr id="row179310439273"><td class="cellrowborder" rowspan="2" valign="top" width="22.7%" headers="mcps1.2.3.1.1 "><p id="p438532393116"><a name="p438532393116"></a><a name="p438532393116"></a>权限最小化</p>
</td>
<td class="cellrowborder" valign="top" width="77.3%" headers="mcps1.2.3.1.2 "><p id="p89311643192711"><a name="p89311643192711"></a><a name="p89311643192711"></a>1. 容器中通过sudo白名单的方式限制普通用户可以执行的docker命令（白名单）。</p>
<p id="p12288531242"><a name="p12288531242"></a><a name="p12288531242"></a>2. 建议Kubernetes pod限制使用特权容器，即不要使用如下方式：</p>
<pre class="screen" id="screen2046819020510"><a name="screen2046819020510"></a><a name="screen2046819020510"></a>apiVersion: v1
kind: Pod
metadata:
  name: hello-world
spec:
  containers:
    - name: hello-world-container
      # The container definition
      # ...
      securityContext:
        privileged: true</pre>
</td>
</tr>
<tr id="row5931174332711"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p181046481678"><a name="p181046481678"></a><a name="p181046481678"></a>默认不使用default serviceaccount下的Token。</p>
<p id="p10931194362717"><a name="p10931194362717"></a><a name="p10931194362717"></a>1、默认关闭default serviceaccount下的自动挂载开关。完成automountServiceAccountToken: false设置后，创建的工作负载将不会默认挂载token。</p>
<div class="caution" id="note17827144619475"><a name="note17827144619475"></a><a name="note17827144619475"></a><span class="cautiontitle"> 注意： </span><div class="cautionbody"><p id="p19827164619475"><a name="p19827164619475"></a><a name="p19827164619475"></a>每个命名空间都要按需设置；设置完毕后滚动重启相应命名空间下的pod。</p>
</div></div>
<pre class="screen" id="screen7403193114818"><a name="screen7403193114818"></a><a name="screen7403193114818"></a>apiVersion: v1
kind: ServiceAccount
metadata:
  name: default
automountServiceAccountToken: false</pre>
<p id="p1493174310271"><a name="p1493174310271"></a><a name="p1493174310271"></a>2、有选择性的在工作负载中挂载default serviceaccount下的Token：</p>
<pre class="screen" id="screen1420484854820"><a name="screen1420484854820"></a><a name="screen1420484854820"></a>...
spec:
  template:
    spec:
      serviceAccountName: default
      automountServiceAccountToken: true
      ...</pre>
</td>
</tr>
<tr id="row13931134372717"><td class="cellrowborder" valign="top" width="22.7%" headers="mcps1.2.3.1.1 "><p id="p4385172313313"><a name="p4385172313313"></a><a name="p4385172313313"></a>网络隔离</p>
</td>
<td class="cellrowborder" valign="top" width="77.3%" headers="mcps1.2.3.1.2 "><p id="p5931204372714"><a name="p5931204372714"></a><a name="p5931204372714"></a><strong id="b162110169587"><a name="b162110169587"></a><a name="b162110169587"></a>集群内容器之间的网络隔离安全加固：</strong></p>
<p id="p14850354185012"><a name="p14850354185012"></a><a name="p14850354185012"></a>通过networkpolicy策略实现访问控制，详情请参见<a href="网络策略(NetworkPolicy).md">网络策略(NetworkPolicy)</a>。</p>
<p id="p1065965481317"><a name="p1065965481317"></a><a name="p1065965481317"></a><strong id="b1567219115814"><a name="b1567219115814"></a><a name="b1567219115814"></a>容器和集群外主机的网络隔离安全加固：</strong></p>
<p id="p1617622419134"><a name="p1617622419134"></a><a name="p1617622419134"></a>通过VPC内的安全组实现访问控制，详情请参见<a href="https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0081124350.html" target="_blank" rel="noopener noreferrer">安全组配置示例</a>。</p>
<p id="p1392313521313"><a name="p1392313521313"></a><a name="p1392313521313"></a>在特定业务场景下，如需实现容器和宿主机之间的网络隔离，建议优先考虑使用CCI安全容器，详情请参见<a href="https://support.huaweicloud.com/cci/index.html" target="_blank" rel="noopener noreferrer">云容器实例CCI</a>。</p>
</td>
</tr>
<tr id="row59326432276"><td class="cellrowborder" valign="top" width="22.7%" headers="mcps1.2.3.1.1 "><p id="p1238552320312"><a name="p1238552320312"></a><a name="p1238552320312"></a>禁止挂载敏感主机目录</p>
</td>
<td class="cellrowborder" valign="top" width="77.3%" headers="mcps1.2.3.1.2 "><p id="p36067411629"><a name="p36067411629"></a><a name="p36067411629"></a>1、如非必须，在启动容器时请不要挂载主机上的/var/run/docker.sock文件到容器内。</p>
<p id="p1293210436271"><a name="p1293210436271"></a><a name="p1293210436271"></a>2、不要将主机上的hostPath目录挂载到容器中，如确有必要，则以只读的方式挂载，例如：/、/boot、/dev、/etc、/lib、/proc、/sys、/usr等。</p>
</td>
</tr>
</tbody>
</table>

