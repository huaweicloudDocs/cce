# iptables与IPVS如何选择<a name="cce_01_0349"></a>

kube-proxy是Kubernetes集群的关键组件，负责Service和其后端容器Pod之间进行负载均衡转发。

CCE当前支持iptables和IPVS两种转发模式，各有优缺点。

-   IPVS: 吞吐更高，速度更快的转发模式。适用于集群规模较大或Service数量较多的场景。
-   iptables: 社区传统的kube-proxy模式。适用于Service数量较少或客户端会出现大量并发短链接的场景。

## iptables<a name="section13695343122418"></a>

iptables 是一个 Linux 内核功能，提供了大量的数据包处理和过滤方面的能力。它可以在核心数据包处理管线上用 Hook 挂接一系列的规则。iptables 模式中 kube-proxy 在 NAT pre-routing Hook 中实现它的 NAT 和负载均衡功能。

kube-proxy 的用法是一种 O\(n\) 算法，其中的 n 随集群规模同步增长，这里的集群规模，更明确的说就是服务和后端 Pod 的数量。

## IPVS<a name="section580312573262"></a>

IPVS\(IP Virtual Server\)是在Netfilter上层构建的，并作为Linux内核的一部分，实现传输层负载均衡。IPVS可以将基于TCP和UDP服务的请求定向到真实服务器，并使真实服务器的服务在单个IP地址上显示为虚拟服务。

IPVS 模式下，kube-proxy 使用 IPVS 负载均衡代替了 iptable。这种模式同样有效，IPVS 的设计就是用来为大量服务进行负载均衡的，它有一套优化过的 API，使用优化的查找算法，而不是简单的从列表中查找规则。

kube-proxy 在 IPVS 模式下，其连接过程的复杂度为 O\(1\)。换句话说，多数情况下，他的连接处理效率是和集群规模无关的。

IPVS 包含了多种不同的负载均衡算法，例如轮询、最短期望延迟、最少连接以及各种哈希方法等。而 iptables 就只有一种随机平等的选择算法。

IPVS相较于iptables的优势大致如下：

1.  为大型集群提供了更好的可扩展性和性能
2.  支持比iptables更好的负载均衡算法
3.  支持服务器健康检查和连接重试等功能

