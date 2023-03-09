# 启用istio<a name="cce_01_1213"></a>

## 操作场景<a name="section160213214302"></a>

应用服务网格（Application Service Mesh，简称ASM）是华为云基于开源Istio推出的服务网格平台，它深度、无缝对接了华为云的企业级Kubernetes集群服务云容器引擎（Cloud Container Engine，简称CCE），在易用性、可靠性、可视化等方面进行了一系列增强，可为客户提供开箱即用的上手体验。

应用服务网格提供非侵入式的微服务治理解决方案，支持完整的生命周期管理和流量治理，兼容Kubernetes和Istio生态，其功能包括负载均衡、熔断、限流等多种治理能力。应用服务网格内置金丝雀、蓝绿、A/B Test等多种灰度发布流程，提供一站式自动化的发布管理。应用服务网格基于无侵入的监控数据采集，提供实时流量拓扑、调用链等服务性能监控和运行诊断，构建全景的服务运行视图。

## 启用Istio<a name="section9231550479"></a>

1.  登录CCE控制台，在左侧导航栏中选择“资源管理 \> 集群管理”。
2.  在集群列表页面中，单击对应集群后的“更多 \> 启用Istio“。

    **图 1**  启用Istio<a name="fig522977933"></a>  
    ![](figures/启用Istio.png "启用Istio")

3.  界面会跳转到购买网格页面，购买网格的操作，具体请参见[应用服务网格](https://support.huaweicloud.com/asm/index.html)。
4.  在集群开启istio服务网格功能后，您使用Istio命令行工具Istioctl配置多种路由策略，从而管理服务流量，包括流量转移、故障注入、限流熔断等。具体操作请参见[通过Istioctl配置路由策略](#section4651449376)。

## 通过Istioctl配置路由策略<a name="section4651449376"></a>

配置Istio命令行工具前必须先配置kubectl命令，详细信息请参见[使用kubectl操作集群](通过kubectl连接集群-7.md#section37321625113110)。

1.  登录CCE控制台，在左侧导航栏中选择“资源管理 \> 集群管理”，单击待连接集群的名称。

    **图 2**  单击集群名称<a name="fig118327236614"></a>  
    ![](figures/单击集群名称.png "单击集群名称")

2.  在集群详情页中的“Istioctl“页签下，请参照界面中的提示信息完成Istioctl的安装和配置。

    **图 3**  使用Istioctl配置路由策略<a name="fig1366811551535"></a>  
    ![](figures/使用Istioctl配置路由策略.png "使用Istioctl配置路由策略")


