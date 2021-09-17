# 通过Kubectl命令行添加Nginx型Ingress<a name="cce_01_0364"></a>

## 操作场景<a name="section1728513718343"></a>

本节以[nginx工作负载](创建无状态负载(Deployment).md#section155246177178)为例，说明kubectl命令添加Nginx型Ingress的方法。

## 前提条件<a name="section105428232391"></a>

-   集群必须已安装nginx-ingress插件，具体操作可参考[安装插件](nginx-ingress.md#section3590245124519)。
-   Ingress为后端工作负载提供网络访问，因此集群中需提前部署可用的工作负载。若您无可用工作负载，可参考[创建无状态负载\(Deployment\)](创建无状态负载(Deployment).md)、[创建有状态负载\(StatefulSet\)](创建有状态负载(StatefulSet).md)或[创建守护进程集\(DaemonSet\)](创建守护进程集(DaemonSet).md)部署示例nginx工作负载。
-   为上述工作负载配置ClusterIP类型或NodePort类型的Service，可参考[集群内访问\(ClusterIP\)](集群内访问(ClusterIP).md)或[节点访问\(NodePort\)](节点访问(NodePort).md)配置示例Service。
-   选择HTTPS协议对外提供访问时，需要提前创建IngressTLS类型的密钥证书，创建密钥的方法请参见[创建密钥](创建密钥.md)。

## 添加Nginx型Ingress<a name="section659917556394"></a>

1.  请参见[通过kubectl连接集群](通过kubectl连接集群.md)，使用kubectl连接集群。
2.  执行如下命令，创建名为“**ingress-test.yaml**”的yaml文件。

    **vi ingress-test.yaml**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   1.15及以上集群版本中的apiVersion为: networking.k8s.io/v1beta1
    >-   1.13及以下集群版本中的apiVersion为: extensions/v1beta1

    **以HTTP协议访问为例，yaml文件配置如下：**

    ```
    apiVersion: networking.k8s.io/v1beta1
    kind: Ingress
    metadata:
      name: ingress-test
      namespace: default
      annotations:
        kubernetes.io/ingress.class: nginx
        kubernetes.io/elb.port: '80' 
    spec:
      rules:
        - host: ''
          http:
            paths:
              - path: '/'
                backend:
                  serviceName: <your_service_name>  #替换为您的目标服务名称
                  servicePort: 80
    ```

    **表 1**  关键参数说明

    <a name="table1863255917310"></a>
    <table><thead align="left"><tr id="row186321759239"><th class="cellrowborder" valign="top" width="24.772477247724773%" id="mcps1.2.5.1.1"><p id="p1263235917316"><a name="p1263235917316"></a><a name="p1263235917316"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="13.691369136913693%" id="mcps1.2.5.1.2"><p id="p963214591737"><a name="p963214591737"></a><a name="p963214591737"></a>是否必填</p>
    </th>
    <th class="cellrowborder" valign="top" width="13.821382138213819%" id="mcps1.2.5.1.3"><p id="p1363265910318"><a name="p1363265910318"></a><a name="p1363265910318"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="47.714771477147714%" id="mcps1.2.5.1.4"><p id="p76329592316"><a name="p76329592316"></a><a name="p76329592316"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row4197149162017"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p4505037165119"><a name="p4505037165119"></a><a name="p4505037165119"></a>kubernetes.io/ingress.class</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p16505937115119"><a name="p16505937115119"></a><a name="p16505937115119"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p6505203725114"><a name="p6505203725114"></a><a name="p6505203725114"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p28212029154917"><a name="p28212029154917"></a><a name="p28212029154917"></a>nginx：表示使用Nginx型Ingress，未安装nginx-ingress插件时无法使用。</p>
    <p id="p5505173745116"><a name="p5505173745116"></a><a name="p5505173745116"></a>通过API接口创建Ingress时必须增加该参数。</p>
    </td>
    </tr>
    <tr id="row113371784472"><td class="cellrowborder" valign="top" width="24.772477247724773%" headers="mcps1.2.5.1.1 "><p id="p1650563711514"><a name="p1650563711514"></a><a name="p1650563711514"></a>kubernetes.io/elb.port</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.691369136913693%" headers="mcps1.2.5.1.2 "><p id="p12505163715111"><a name="p12505163715111"></a><a name="p12505163715111"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.821382138213819%" headers="mcps1.2.5.1.3 "><p id="p35051037195115"><a name="p35051037195115"></a><a name="p35051037195115"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.714771477147714%" headers="mcps1.2.5.1.4 "><p id="p13505537155117"><a name="p13505537155117"></a><a name="p13505537155117"></a>界面上的对外端口，为注册到负载均衡服务地址上的端口。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  执行如下命令创建Ingress。

    **kubectl create -f ingress-test.yaml**

    回显如下，表示Ingress服务已创建。

    ```
    ingress/ingress-test created
    ```

    **kubectl get ingress**

    回显如下，表示Ingress服务创建成功，工作负载可访问。

    ```
    NAME             HOSTS     ADDRESS          PORTS   AGE
    ingress-test     *         121.**.**.**     80      10s
    ```

4.  访问工作负载（例如[nginx工作负载](创建无状态负载(Deployment).md#section155246177178)），在浏览器中输入访问地址http://121.\*\*.\*\*.\*\*:80进行验证。

    其中，121.\*\*.\*\*.\*\*为统一负载均衡实例的IP地址。


## 配置HTTPS证书<a name="section9190660134"></a>

支持配置HTTPS证书提供安全服务，YAML配置示例如下：

```
apiVersion: networking.k8s.io/v1beta1
kind: Ingress 
metadata: 
  name: ingress-test
  annotations: 
    kubernetes.io/ingress.class: nginx
    kubernetes.io/elb.port: '443'
spec:
  tls: 
  - hosts: 
    - foo.bar.com
    secretName: ingress-test-secret
  rules: 
  - host: ''
    http: 
      paths: 
      - path: '/'
        backend: 
          serviceName: <your_service_name>  #替换为您的目标服务名称
          servicePort: 80
```

## Rewrite<a name="section142741813151619"></a>

在一些使用场景中后端服务暴露的URL与Ingress规则中指定的路径不同，如果不进行Rewrite配置，所有访问都将返回404。Rewrite配置可以使用inginx.ingress.kubernetes.io/rewrite-target 注解实现，如下所示：

```
apiVersion: networking.k8s.io/v1beta1
kind: Ingress
metadata:
  name: ingress-test
  namespace: default
  annotations:
    kubernetes.io/ingress.class: nginx
    nginx.ingress.kubernetes.io/rewrite-target: /$2
spec:
  rules:
    - host: 'rewrite.bar.com'
      http:
        paths:
          - path: '/something(/|$)(.*)'
            backend:
              serviceName: <your_service_name>  #替换为您的目标服务名称
              servicePort: 80
```

以上示例中，占位符$2表示匹配第二个括号即\(.\*\)中捕获到的任何字符，然后将其用作重写目标注释中的参数。

例如，上面的Ingress定义将导致以下重写：

-   rewrite.bar.com/something 重写为 rewrite.bar.com/
-   rewrite.bar.com/something/ 重写为 rewrite.bar.com/
-   rewrite.bar.com/something/new 重写为 rewrite.bar.com/new

nginx-ingress-controller容器中，/etc/nginx路径下的nginx.conf文件可查看所有ingress配置，示例中rewrite指令生成的nginx.conf相关字段如下所示：

```
## start server rewrite.bar.com
        server {
                server_name rewrite.bar.com ;
                ...
                location ~* "^/something(/|$)(.*)" {
                        set $namespace      "default";
                        set $ingress_name   "ingress-test";
                        set $service_name   "<your_service_name>";
                        set $service_port   "80";
                        ...
                        rewrite "(?i)/something(/|$)(.*)" /$2 break;
                        ...
                }
        }
        ## end server rewrite.bar.com
```

对于一些复杂高级的Rewrite需求，可以通过如下注解来实现，其本质是修改Nginx的配置。

-   nginx.ingress.kubernetes.io/server-snippet：扩展到Nginx配置的Server章节。
-   nginx.ingress.kubernetes.io/configuration-snippet：扩展到Nginx配置的Location章节。

Server和Location配置中通过rewrite指令完成URL的重写，其基本语法结构为：

```
rewrite regex replacement flag;
```

-   regex：匹配URI的正则表达式。
-   replacement：重写内容。
-   flag：表示重写形式的标记。

flag标记包括：

-   last：本条规则匹配完成后继续向下匹配。
-   break：本条规则匹配完成后停止匹配。
-   redirect：临时重定向，返回状态码302。
-   permanent：永久重定向，返回状态码301。

rewrite指令示例如下：

```
annotations:
     kubernetes.io/ingress.class: "nginx"
     nginx.ingress.kubernetes.io/configuration-snippet: |
        rewrite ^/stylesheets/(.*)$ /something/stylesheets/$1 redirect;  # 添加 /something 前缀
        rewrite ^/images/(.*)$ /something/images/$1 redirect;  # 添加 /something 前缀
```

如上两条规则在访问URL中加了/something：

-   当用户访问rewrite.bar.com/stylesheets/new.css时，重写为rewrite.bar.com/something/stylesheets/new.css
-   当用户访问rewrite.bar.com/images/new.jpg时，重写为rewrite.bar.com/something/images/new.jpg

## 后端一致性哈希<a name="section794018299413"></a>

一致性哈希算法可以有效解决动态增删节点带来的负载均衡问题。在增加一台服务器时，新的服务器会尽量分担其他所有服务器的压力；同样，在减少一台服务器时，其他所有服务器也可以尽量分担它的资源，可以有效减少集群局部节点的压力，防止由于某一节点宕机带来的集群雪崩效应。

Nginx Ingress支持为后端服务配置一致性哈希规则，可以通过nginx.ingress.kubernetes.io/upstream-hash-by注解实现，如下所示：

```
apiVersion: networking.k8s.io/v1beta1
kind: Ingress
metadata:
  name: ingress-test
  namespace: default
  annotations:
    kubernetes.io/ingress.class: nginx
    nginx.ingress.kubernetes.io/upstream-hash-by: "$request_uri"  #按照请求uri进行hash
spec:
  rules:
    - host: ''
      http:
        paths:
          - path: '/'
            backend:
              serviceName: <your_service_name>  #替换为您的目标服务名称
              servicePort: 80
```

注解nginx.ingress.kubernetes.io/upstream-hash-by的参数值支持nginx参数、文本值或任意组合，例如：

-   nginx.ingress.kubernetes.io/upstream-hash-by: "$request\_uri"代表按照请求uri进行hash。
-   nginx.ingress.kubernetes.io/upstream-hash-by: "$request\_uri$host"代表按照请求uri和域名进行hash。
-   nginx.ingress.kubernetes.io/upstream-hash-by: "$\{request\_uri\}-text-value"代表按照请求uri和文本值进行hash。

