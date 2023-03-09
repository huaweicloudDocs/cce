# 节点干扰ContainerdSock检查<a name="cce_10_0457"></a>

## 检查项内容<a name="section9430173019423"></a>

检查节点上是否存在干扰的Containerd.Sock文件。该文件影响euler操作系统下的容器运行时启动。

## 解决方案<a name="section1616565816422"></a>

**问题场景：节点使用的docker为定制的Euler-dokcer而非社区的docker**

1.  登录相关节点。
2.  执行**rpm -qa | grep docker | grep euleros**命令，如果结果不为空，说明节点上使用的docker为Euler-docker
3.  执行**ls /run/containerd/containerd.sock**命令，若发现存在该文件则会导致docker启动失败。
4.  执行**rm -rf /run/containerd/containerd.sock**命令，然后重新进行集群升级检查。

