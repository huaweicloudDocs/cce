# Helm模板检查<a name="cce_10_0434"></a>

## 检查项内容<a name="section114556206613"></a>

当前检查当前HelmRelease记录中是否含有目标集群版本不支持的K8s废弃API，可能导致升级后helm模板不可用。

## 解决方案<a name="section13127211472"></a>

将HelmRelease记录中K8s废弃API转换为源版本和目标版本均兼容的API。

>![](public_sys-resources/icon-note.gif) **说明：** 
>该检查项解决方案已在升级流程中自动兼容处理，此检查不再限制。您无需关注并处理。

