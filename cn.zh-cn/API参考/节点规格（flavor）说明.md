# 节点规格（flavor）说明<a name="cce_02_0368"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>不同区域支持的节点规格（flavor）不同，且节点规格存在新增、售罄下线等情况，建议您在使用前登录CCE控制台，在创建节点界面查看您需要的节点规格是否支持。

-   **CCE集群**

    -   x86节点：CCE集群支持ai1、ct3、t6、s2、s3、s6、c3、ir3、cx3、c3ne、cx3ne、c6、c6s、m2、m3、m6、h3、d2、hc2、i3、p1、pi1、pi2、p2v、p2vs、g5、g5r、g6、Si2、Si3、sn3类型的服务器，具体节点规格名称请参见[规格清单](https://support.huaweicloud.com/productdesc-ecs/zh-cn_topic_0159822360.html)，且只支持**2U4G以上**的规格。
    -   鲲鹏节点：支持所有类型的鲲鹏节点，具体规格名称请参见[规格清单](https://support.huaweicloud.com/productdesc-ecs/ecs_01_0066.html)。

    在填写flavor时，需要填写具体规格名称，如**c6.large.2**。

    另外IPv6双栈类型的节点，仅支持s3、c3、c3ne、sn3、cx3ne类型服务器，且在不同区域可选的规格不同，具体请参见[支持IPv6服务器约束与限制](https://support.huaweicloud.com/usermanual-ecs/ecs_03_0508.html#section1)。

-   **CCE Turbo集群**

    CCE Turbo集群支持c6ne和c7类型服务器。支持c6、v7类型共池裸机。


