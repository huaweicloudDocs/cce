# 修复Linux内核SACK 漏洞公告<a name="cce_01_0192"></a>

华为云CCE团队已经紧急修复[Linux 内核SACK漏洞](https://www.huaweicloud.com/notice/2018/20190619122553544.html)，并已发布解决方案。

## 漏洞详情<a name="section16102913144819"></a>

2019年6月18日，Redhat发布安全公告，Linux内核处理器TCP SACK模块存在3个安全漏洞\(CVE-2019-11477、CVE-2019-11478、CVE-2019-11479\)，这些漏洞与最大分段大小（MSS）和TCP选择性确认（SACK）功能相关，攻击者可远程发送特殊构造的攻击包造成拒绝服务攻击，导致服务器不可用或崩溃。

参考链接：

[https://www.suse.com/support/kb/doc/?id=7023928](https://www.suse.com/support/kb/doc/?id=7023928)

[https://access.redhat.com/security/vulnerabilities/tcpsack](https://access.redhat.com/security/vulnerabilities/tcpsack)

[https://www.debian.org/lts/security/2019/dla-1823](https://www.debian.org/lts/security/2019/dla-1823)

[https://wiki.ubuntu.com/SecurityTeam/KnowledgeBase/SACKPanic?](https://wiki.ubuntu.com/SecurityTeam/KnowledgeBase/SACKPanic?)

[https://lists.centos.org/pipermail/centos-announce/2019-June/023332.html](https://lists.centos.org/pipermail/centos-announce/2019-June/023332.html)

[https://github.com/Netflix/security-bulletins/blob/master/advisories/third-party/2019-001.md](https://github.com/Netflix/security-bulletins/blob/master/advisories/third-party/2019-001.md)

**表 1**  漏洞信息

<a name="table1565618845915"></a>
<table><thead align="left"><tr id="row065718811595"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p265798165915"><a name="p265798165915"></a><a name="p265798165915"></a>漏洞类型</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.2"><p id="p465798195911"><a name="p465798195911"></a><a name="p465798195911"></a>CVE-ID</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.3"><p id="p365720810595"><a name="p365720810595"></a><a name="p365720810595"></a>披露/发现时间</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="p1365711835912"><a name="p1365711835912"></a><a name="p1365711835912"></a>华为云修复时间</p>
</th>
</tr>
</thead>
<tbody><tr id="row1120510564498"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p177230203311"><a name="p177230203311"></a><a name="p177230203311"></a>输入验证错误</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p1665713818593"><a name="p1665713818593"></a><a name="p1665713818593"></a><a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-11477" target="_blank" rel="noopener noreferrer">CVE-2019-11477</a></p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p7206656134917"><a name="p7206656134917"></a><a name="p7206656134917"></a>2019-06-17</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p12151132413411"><a name="p12151132413411"></a><a name="p12151132413411"></a>2019-07-06</p>
</td>
</tr>
<tr id="row1056225316496"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p85631153164916"><a name="p85631153164916"></a><a name="p85631153164916"></a>资源管理错误</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p756320532491"><a name="p756320532491"></a><a name="p756320532491"></a><a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-11478" target="_blank" rel="noopener noreferrer">CVE-2019-11478</a></p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p1256325344920"><a name="p1256325344920"></a><a name="p1256325344920"></a>2019-06-17</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p1114101117544"><a name="p1114101117544"></a><a name="p1114101117544"></a>2019-07-06</p>
</td>
</tr>
<tr id="row19657198185917"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p185191344145311"><a name="p185191344145311"></a><a name="p185191344145311"></a>资源管理错误</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p12349310588"><a name="p12349310588"></a><a name="p12349310588"></a><a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-11479" target="_blank" rel="noopener noreferrer">CVE-2019-11479</a></p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p206589816592"><a name="p206589816592"></a><a name="p206589816592"></a>2019-06-17</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p05641981462"><a name="p05641981462"></a><a name="p05641981462"></a>2019-07-06</p>
</td>
</tr>
</tbody>
</table>

## 影响范围<a name="section194116513488"></a>

影响Linux 内核2.6.29及以上版本。

## 解决方法<a name="section1446470135915"></a>

升级操作系统内核的方法，请参见[操作系统内核升级](操作系统内核升级.md)。

## 附：TCP SACK介绍<a name="section11904733145410"></a>

TCP是面向连接的协议。当双方希望通过TCP连接进行通信时，他们通过TCP握手交换某些信息建立连接，例如发起一个TCP请求，通过SYN发送初始序列ID，确认ID，连接使用的最大数据包段大小（MSS），认证信息和处理选择性确认（SACK）等。整体TCP连接通过我们熟知的三次握手最终建立。

TCP通过一个数据段单元发送和接收用户数据包。 TCP数据段由TCP头，选项和用户数据组成。每个TCP段都有序列号（SEQ）和确认号（ACK）。

接收方通过SEQ号和ACK号来跟踪成功接收了哪些段。ACK号下一个预期接受的段。

**示例：**

![](figures/zh-cn_image_0178560474.png)

上图中用户A通过13个100字节的段发送1k字节的数据，每个段具有20字节的TCP头，总计是13个段。在接收端，用户B接收了段1,2,4,6,8-13，而段3,5和7丢失，B没有接收到。

通过使用ACK号，用户B告诉A，他需要段3，用户A收到B接收到2，而没有收到3，A将重新发送全部段，尽管B已经收到了4,6和8-13段。所以导致大量重复传输，性能低下。

