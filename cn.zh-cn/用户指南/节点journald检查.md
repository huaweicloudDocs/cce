# 节点journald检查<a name="cce_10_0456"></a>

## 检查项内容<a name="section76841181396"></a>

检查节点上的journald状态是否正常。

## 解决方案<a name="section14292182710397"></a>

请登陆该节点，执行**systemctl is-active systemd-journald**命令查询journald服务运行状态。若回显状态异常，请执行**systemctl restart systemd-journald**命令后重新查询状态。

以下为正常回显：

![](figures/jounald.png)

若重启journald服务无法解决该问题，请联系技术支持人员。

