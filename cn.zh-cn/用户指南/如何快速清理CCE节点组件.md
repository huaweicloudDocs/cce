# 如何快速清理CCE节点组件？<a name="cce_01_0132"></a>

## 使用场景<a name="section173631312185614"></a>

若集群中包含包周期节点或纳管节点，删除对应集群和节点不会删除对应的ECS，此时请按照界面提示清理节点上CCE组件。若未按照提示清理节点组件，后续需要清理ECS时，可按照如下操作进行清理。

执行清理操作前，若有关键数据需要保留，请提前备份或提交工单联系客服咨询。

## 操作步骤<a name="section268022815614"></a>

1.  以**root**用户登录待清理的ECS，获取对应节点版本信息。

    **VER=$\(gawk -F'.sp' '\{print $1\}' /var/paas/kubernetes/version\); echo "CCE Node Version: $VER";**

2.  下载版本对应卸载脚本。

    **curl -k http://cce-north.obs.myhuaweicloud.com/cluster-versions/$\{VER\}/node-uninstall.tgz -1 -O; tar zxf node-uninstall.tgz;**

3.  执行卸载脚本，清理CCE组件。

    清理操作包括卸载docker服务、删除paas用户、删除组件目录。

    **TMOUT=0; bash uninstall\_node.sh;**

    若上述命令执行失败，请联系客服处理。


