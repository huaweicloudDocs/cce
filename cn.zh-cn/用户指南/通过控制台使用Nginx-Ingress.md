# 通过控制台使用Nginx Ingress<a name="cce_10_0390"></a>

## 前提条件<a name="section7120205117104"></a>

-   Ingress为后端工作负载提供网络访问，因此集群中需提前部署可用的工作负载。若您无可用工作负载，可参考[创建无状态负载\(Deployment\)](创建无状态负载(Deployment).md)、[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)或[创建守护进程集\(DaemonSet\)](创建守护进程集(DaemonSet).md)部署工作负载。
-   添加Nginx Ingress时，需在集群中提前安装nginx-ingress插件，具体操作可参考[安装插件](nginx-ingress.md#section1152424015224)。

## 注意事项<a name="section2042610683912"></a>

-   **不建议在ELB服务页面修改ELB实例的任何配置，否则将导致服务异常。**如果您已经误操作，请卸载Nginx Ingress插件后重装。
-   Ingress转发策略中注册的URL需与后端应用暴露的URL一致，否则将返回404错误。
-   负载均衡实例需与当前集群处于相同VPC 且为相同公网或私网类型。
-   负载均衡实例需要拥有至少两个监听器配额，且端口80和443没有被监听器占用。

## 添加Nginx Ingress<a name="section13728162710151"></a>

本节以Nginx作为工作负载并添加Nginx Ingress为例进行说明。

1.  登录CCE控制台，单击集群名称进入集群。
2.  选择左侧导航栏的“服务发现“，在右侧选择“路由“页签，单击右上角“创建路由“。
3.  设置Ingress参数。
    -   **名称：**自定义Ingress名称，例如nginx-ingress-demo。
    -   **命名空间：**选择需要添加Ingress的命名空间。
    -   **对接Nginx：**集群中已安装[nginx-ingress](nginx-ingress.md)插件后显示此选项，未安装nginx-ingress模板时本选项不显示。

        单击![](figures/zh-cn_image_0000001243981197.png)开启后将对接nginx-ingress提供7层访问，可配置如下参数。

        **TLS配置**：nginx-ingress支持HTTP和HTTPS，安装nginx-ingress时预留的监听端口，默认HTTP为80，HTTPS为443。使用HTTPS需要配置相关证书。

        -   服务器证书：创建HTTPS协议监听时需要绑定IngressTLS类型的密钥证书，以支持HTTPS数据传输加密认证，创建密钥的方法请参见[创建密钥](创建密钥.md)。
        -   SNI：SNI（Server Name Indication）是TLS的扩展协议，在该协议下允许同一个IP地址和端口号下对外提供多个基于TLS的访问域名，且不同的域名可以使用不同的安全证书。开启SNI后，允许客户端在发起TLS握手请求时就提交请求的域名信息。负载均衡收到TLS请求后，会根据请求的域名去查找证书：若找到域名对应的证书，则返回该证书认证鉴权；否则，返回缺省证书（服务器证书）认证鉴权。

    -   **转发策略配置：**请求的访问地址与转发规则匹配时（转发规则由域名、URL组成），此请求将被转发到对应的目标Service处理。单击“添加转发策略“按钮可添加多条转发策略。
        -   域名：实际访问的域名地址。请确保所填写的域名已注册并备案，在Ingress创建完成后，将域名与自动创建的负载均衡实例的IP（即Ingress访问地址的IP部分）绑定。一旦配置了域名规则，则必须使用域名访问。
        -   URL：需要注册的访问路径，例如：/healthz。社区v1.2.0版本（对应CCE nginx-ingress插件2.1.0版本）后修复CVE-2021-25745\(https://github.com/kubernetes/ingress-nginx/issues/8502\)漏洞，新增规则（https://github.com/kubernetes/ingress-nginx/blame/main/internal/ingress/inspector/rules.go）禁用一些存在越权风险的访问路径。

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >Nginx Ingress的URL匹配规则是基于“/”符号分隔的路径前缀匹配，并区分大小写。只要访问路径以“/”符号分隔后的子路径匹配此前缀，均可正常访问，但如果该前缀仅是子路径中的部分字符串，则不会匹配。例如URL设置为/healthz，则匹配/healthz/v1，但不匹配/healthzv1。

        -   目标服务名称：请选择已有Service或新建Service。页面列表中的查询结果已自动过滤不符合要求的Service。
        -   目标服务访问端口：可选择目标Service的访问端口。
        -   操作：可单击“删除“按钮删除该配置。

    -   **注解**：以“key: value”形式设置，可通过[Annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/)查询nginx-ingress支持的配置。社区v1.2.0版本（对应CCE nginx-ingress插件2.1.0版本）后修复CVE-2021-25746\(https://github.com/kubernetes/ingress-nginx/issues/8503\)漏洞，新增规则（https://github.com/kubernetes/ingress-nginx/blame/main/internal/ingress/inspector/rules.go）禁用一些存在越权风险的Anntotations值。

4.  配置完成后，单击“创建“。

    创建完成后，在Ingress列表可查看到已添加的Ingress。


## 相关操作<a name="section59831252163212"></a>

[部署多个Nginx Ingress Controller](https://support.huaweicloud.com/bestpractice-cce/cce_bestpractice_0342.html)

