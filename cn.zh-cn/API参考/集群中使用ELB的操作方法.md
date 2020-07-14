# 集群中使用ELB的操作方法<a name="cce_02_0087"></a>

本章节介绍在CCE创建的集群中使用ELB时的操作方法。

## 操作方法<a name="section50156865193415"></a>

创建对应的service。开源接口的使用方法请参见[创建Service](创建Service.md)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>若需要开启会话保持，需要满足如下条件：
>-   工作负载协议为TCP。
>-   工作负载的各实例已设置反亲和部署，即所有的实例都部署在不同节点上。详细请参见[工作负载和节点的反亲和性](https://support.huaweicloud.com/usermanual-cce/cce_01_0226.html)。

自动创建ELB：

```
apiVersion: v1 
kind: Service 
metadata: 
  annotations:   
    kubernetes.io/elb.class: union
    kubernetes.io/session-affinity-mode: SOURCE_IP
    kubernetes.io/elb.subnet-id: 5083f225-9bf8-48fa-9c8b-67bd9693c4c0
    kubernetes.io/elb.autocreate: "{\"type\":\"public\",\"bandwidth_name\":\"cce-bandwidth-1551163379627\",\"bandwidth_chargemode\":\"bandwidth\",\"bandwidth_size\":5,\"bandwidth_sharetype\":\"PER\",\"eip_type\":\"5_bgp\",\"name\":\"james\"}"
  labels: 
    app: nginx 
  name: nginx 
spec: 
  externalTrafficPolicy: Local
  ports: 
  - name: service0 
    port: 80
    protocol: TCP 
    targetPort: 80
  selector: 
    app: nginx 
  type: LoadBalancer
```

使用已有ELB：

```
apiVersion: v1 
kind: Service 
metadata: 
  annotations:   
    kubernetes.io/elb.class: union
    kubernetes.io/session-affinity-mode: SOURCE_IP
    kubernetes.io/elb.id: 3c7caa5a-a641-4bff-801a-feace27424b6
    kubernetes.io/elb.subnet-id: 5083f225-9bf8-48fa-9c8b-67bd9693c4c0
  labels: 
    app: nginx 
  name: nginx 
spec: 
  loadBalancerIP: 10.78.42.242
  externalTrafficPolicy: Local
  ports: 
  - name: service0 
    port: 80
    protocol: TCP 
    targetPort: 80
  selector: 
    app: nginx 
  type: LoadBalancer
```

**表 1**  关键参数说明

<a name="table1819001615355"></a>
<table><thead align="left"><tr id="row1519121663519"><th class="cellrowborder" valign="top" width="34.28657134286571%" id="mcps1.2.4.1.1"><p id="p18191161619356"><a name="p18191161619356"></a><a name="p18191161619356"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.118588141185882%" id="mcps1.2.4.1.2"><p id="p1191141613357"><a name="p1191141613357"></a><a name="p1191141613357"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="51.594840515948405%" id="mcps1.2.4.1.3"><p id="p1919116161353"><a name="p1919116161353"></a><a name="p1919116161353"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row7430236123515"><td class="cellrowborder" valign="top" width="34.28657134286571%" headers="mcps1.2.4.1.1 "><p id="p2430336153520"><a name="p2430336153520"></a><a name="p2430336153520"></a>kubernetes.io/elb.class</p>
</td>
<td class="cellrowborder" valign="top" width="14.118588141185882%" headers="mcps1.2.4.1.2 "><p id="p19430103693512"><a name="p19430103693512"></a><a name="p19430103693512"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1380805311426"><a name="p1380805311426"></a><a name="p1380805311426"></a>对接共享型负载均衡时需要增加此参数，值为<span class="uicontrol" id="uicontrol349572644413"><a name="uicontrol349572644413"></a><a name="uicontrol349572644413"></a>“union”</span>。</p>
</td>
</tr>
<tr id="row15191171618357"><td class="cellrowborder" valign="top" width="34.28657134286571%" headers="mcps1.2.4.1.1 "><p id="p204451615124716"><a name="p204451615124716"></a><a name="p204451615124716"></a>kubernetes.io/session-affinity-mode</p>
</td>
<td class="cellrowborder" valign="top" width="14.118588141185882%" headers="mcps1.2.4.1.2 "><p id="p1090683224719"><a name="p1090683224719"></a><a name="p1090683224719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p12830929125713"><a name="p12830929125713"></a><a name="p12830929125713"></a>可选，若需要开启会话保持，需增加该参数。</p>
<p id="p16904132104710"><a name="p16904132104710"></a><a name="p16904132104710"></a>取值“SOURCE_IP”表示基于源IP。</p>
</td>
</tr>
<tr id="row81941516153513"><td class="cellrowborder" valign="top" width="34.28657134286571%" headers="mcps1.2.4.1.1 "><p id="p4764162894719"><a name="p4764162894719"></a><a name="p4764162894719"></a>kubernetes.io/elb.id</p>
</td>
<td class="cellrowborder" valign="top" width="14.118588141185882%" headers="mcps1.2.4.1.2 "><p id="p77621528184710"><a name="p77621528184710"></a><a name="p77621528184710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p59344376579"><a name="p59344376579"></a><a name="p59344376579"></a>可选，但使用已有ELB时必填。</p>
<p id="p416573016509"><a name="p416573016509"></a><a name="p416573016509"></a>为共享型负载均衡实例的ID。</p>
</td>
</tr>
<tr id="row201957167350"><td class="cellrowborder" valign="top" width="34.28657134286571%" headers="mcps1.2.4.1.1 "><p id="p18758202864719"><a name="p18758202864719"></a><a name="p18758202864719"></a>kubernetes.io/elb.subnet-id</p>
</td>
<td class="cellrowborder" valign="top" width="14.118588141185882%" headers="mcps1.2.4.1.2 "><p id="p336744055219"><a name="p336744055219"></a><a name="p336744055219"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p2075662814474"><a name="p2075662814474"></a><a name="p2075662814474"></a>可选，但自动创建时必填，Kubernetes v1.11.7-r0以上版本的集群可不填。</p>
</td>
</tr>
<tr id="row1719518169356"><td class="cellrowborder" valign="top" width="34.28657134286571%" headers="mcps1.2.4.1.1 "><p id="p9754162844712"><a name="p9754162844712"></a><a name="p9754162844712"></a>kubernetes.io/elb.autocreate</p>
</td>
<td class="cellrowborder" valign="top" width="14.118588141185882%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p32706975"><a name="zh-cn_topic_0079615000_p32706975"></a><a name="zh-cn_topic_0079615000_p32706975"></a><a href="#table19417184671919">elb.autocreate</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p127521028194718"><a name="p127521028194718"></a><a name="p127521028194718"></a>可选，但公网自动创建时必填，将自动创建ELB所绑定的EIP。私网自动创建时必填，将自动创建ELB。</p>
<p id="p115519391615"><a name="p115519391615"></a><a name="p115519391615"></a><strong id="b158091351266"><a name="b158091351266"></a><a name="b158091351266"></a>示例：</strong></p>
<a name="ul286913611614"></a><a name="ul286913611614"></a><ul id="ul286913611614"><li>公网自动创建：值为 "{\"type\":\"public\",\"bandwidth_name\":\"cce-bandwidth-1551163379627\",\"bandwidth_chargemode\":\"bandwidth\",\"bandwidth_size\":5,\"bandwidth_sharetype\":\"PER\",\"eip_type\":\"5_bgp\",\"name\":\"james\"}"</li><li>私网自动创建：值为 "{\"type\":\"inner\"}"</li></ul>
</td>
</tr>
<tr id="row121515334113"><td class="cellrowborder" valign="top" width="34.28657134286571%" headers="mcps1.2.4.1.1 "><p id="p92162033131111"><a name="p92162033131111"></a><a name="p92162033131111"></a>loadBalancerIP</p>
</td>
<td class="cellrowborder" valign="top" width="14.118588141185882%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079615000_p47822814"><a name="zh-cn_topic_0079615000_p47822814"></a><a name="zh-cn_topic_0079615000_p47822814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p7217113331120"><a name="p7217113331120"></a><a name="p7217113331120"></a>配置为ELB的IP地址，私网ELB配置私有IP，公网ELB配置为公网IP。</p>
</td>
</tr>
<tr id="row14980162901115"><td class="cellrowborder" valign="top" width="34.28657134286571%" headers="mcps1.2.4.1.1 "><p id="p398162913117"><a name="p398162913117"></a><a name="p398162913117"></a>externalTrafficPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="14.118588141185882%" headers="mcps1.2.4.1.2 "><p id="p142173231413"><a name="p142173231413"></a><a name="p142173231413"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p119811329111112"><a name="p119811329111112"></a><a name="p119811329111112"></a>可选，若需要开启会话保持，需增加该参数，表示请求转到固定节点；若某个服务发布成ELB服务且为Local模式，客户端如果在集群内，那么必须与服务端在同一个节点上才能正常访问。</p>
</td>
</tr>
<tr id="row17120113981313"><td class="cellrowborder" valign="top" width="34.28657134286571%" headers="mcps1.2.4.1.1 "><p id="p17120639161311"><a name="p17120639161311"></a><a name="p17120639161311"></a>port</p>
</td>
<td class="cellrowborder" valign="top" width="14.118588141185882%" headers="mcps1.2.4.1.2 "><p id="p1120939161311"><a name="p1120939161311"></a><a name="p1120939161311"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p1120163961310"><a name="p1120163961310"></a><a name="p1120163961310"></a>集群虚拟IP的访问端口，也是注册到负载均衡上的端口。</p>
</td>
</tr>
<tr id="row02694357138"><td class="cellrowborder" valign="top" width="34.28657134286571%" headers="mcps1.2.4.1.1 "><p id="p627233515132"><a name="p627233515132"></a><a name="p627233515132"></a>targetPort</p>
</td>
<td class="cellrowborder" valign="top" width="14.118588141185882%" headers="mcps1.2.4.1.2 "><p id="p19272143531318"><a name="p19272143531318"></a><a name="p19272143531318"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p8272035161316"><a name="p8272035161316"></a><a name="p8272035161316"></a>对应界面上的容器端口</p>
</td>
</tr>
</tbody>
</table>

**表 2**  elb.autocreate字段数据结构说明

<a name="table19417184671919"></a>
<table><thead align="left"><tr id="row14418174611912"><th class="cellrowborder" valign="top" width="29.727027297270276%" id="mcps1.2.4.1.1"><p id="p1141924611199"><a name="p1141924611199"></a><a name="p1141924611199"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.678132186781323%" id="mcps1.2.4.1.2"><p id="p1641911466191"><a name="p1641911466191"></a><a name="p1641911466191"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="51.594840515948405%" id="mcps1.2.4.1.3"><p id="p1941920463197"><a name="p1941920463197"></a><a name="p1941920463197"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row194191846181915"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p152321411112318"><a name="p152321411112318"></a><a name="p152321411112318"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p7419646171920"><a name="p7419646171920"></a><a name="p7419646171920"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p87791494919"><a name="p87791494919"></a><a name="p87791494919"></a>自动创建的负载均衡的名称。</p>
<p id="p9912132016296"><a name="p9912132016296"></a><a name="p9912132016296"></a>取值范围：1-64个字符，中英文，数字，下划线，中划线。</p>
</td>
</tr>
<tr id="row142064681919"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p20862285225"><a name="p20862285225"></a><a name="p20862285225"></a>type</p>
</td>
<td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p8420746101918"><a name="p8420746101918"></a><a name="p8420746101918"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p4703183013491"><a name="p4703183013491"></a><a name="p4703183013491"></a>负载均衡实例网络类型，公网或者私网。</p>
<a name="ul152311045124913"></a><a name="ul152311045124913"></a><ul id="ul152311045124913"><li>public：公网型负载均衡</li><li>inner：私网型负载均衡</li></ul>
</td>
</tr>
<tr id="row194201046151910"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p128042817221"><a name="p128042817221"></a><a name="p128042817221"></a>bandwidth_name</p>
</td>
<td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p1142084619195"><a name="p1142084619195"></a><a name="p1142084619195"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p6964103318220"><a name="p6964103318220"></a><a name="p6964103318220"></a>带宽的名称，默认值为：cce-bandwidth-******。</p>
<p id="p1236952875020"><a name="p1236952875020"></a><a name="p1236952875020"></a>1-64 字符，中文、英文字符、数字、下划线、中划线或点组成。</p>
</td>
</tr>
<tr id="row942194619199"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p77502811221"><a name="p77502811221"></a><a name="p77502811221"></a>bandwidth_chargemode</p>
</td>
<td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p11421446191914"><a name="p11421446191914"></a><a name="p11421446191914"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p3178181495216"><a name="p3178181495216"></a><a name="p3178181495216"></a>带宽付费模式。</p>
<a name="ul567215235528"></a><a name="ul567215235528"></a><ul id="ul567215235528"><li>bandwidth：按带宽计费</li><li>traffic：按流量计费</li></ul>
</td>
</tr>
<tr id="row124211046101910"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p187492819229"><a name="p187492819229"></a><a name="p187492819229"></a>bandwidth_size</p>
</td>
<td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p114229463196"><a name="p114229463196"></a><a name="p114229463196"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p12958233152218"><a name="p12958233152218"></a><a name="p12958233152218"></a>带宽大小，请根据具体region带宽支持范围设置，详情请参考<a href="https://support.huaweicloud.com/api-eip/eip_api_0001.html" target="_blank" rel="noopener noreferrer">申请弹性公网IP</a>中<strong id="b198591928137"><a name="b198591928137"></a><a name="b198591928137"></a>表4 bandwidth字段说明中size字段</strong>。</p>
</td>
</tr>
<tr id="row1942224601917"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p16731228202214"><a name="p16731228202214"></a><a name="p16731228202214"></a>bandwidth_sharetype</p>
</td>
<td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p84221246111913"><a name="p84221246111913"></a><a name="p84221246111913"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p59311192057"><a name="p59311192057"></a><a name="p59311192057"></a>功能说明：带宽类型，标识是否是共享带宽。</p>
<p id="p188864421731"><a name="p188864421731"></a><a name="p188864421731"></a>取值范围：</p>
<a name="ul165751761277"></a><a name="ul165751761277"></a><ul id="ul165751761277"><li>WHOLE：共享带宽</li><li>PER：独享带宽</li></ul>
</td>
</tr>
<tr id="row1242219461193"><td class="cellrowborder" valign="top" width="29.727027297270276%" headers="mcps1.2.4.1.1 "><p id="p1972102872220"><a name="p1972102872220"></a><a name="p1972102872220"></a>eip_type</p>
</td>
<td class="cellrowborder" valign="top" width="18.678132186781323%" headers="mcps1.2.4.1.2 "><p id="p132201811174611"><a name="p132201811174611"></a><a name="p132201811174611"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="51.594840515948405%" headers="mcps1.2.4.1.3 "><p id="p11956103372218"><a name="p11956103372218"></a><a name="p11956103372218"></a>弹性公网IP类型，请参考ELB支持的弹性公网IP类型，详情请参考<a href="https://support.huaweicloud.com/api-eip/eip_api_0001.html" target="_blank" rel="noopener noreferrer">申请弹性公网IP</a>中<strong id="b11814520410"><a name="b11814520410"></a><a name="b11814520410"></a>表3 publicip字段说明type字段</strong>。</p>
</td>
</tr>
</tbody>
</table>

