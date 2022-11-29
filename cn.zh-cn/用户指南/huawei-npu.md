# huawei-npu<a name="cce_10_0239"></a>

## 插件简介<a name="section173631312185614"></a>

huawei-npu是支持容器里使用huawei NPU设备的管理插件。

安装本插件后，可创建“AI加速型“节点，实现快速高效地处理推理和图像识别等工作。

## 约束与限制<a name="section11172124718374"></a>

集群中使用“AI加速型“节点时必须安装huawei-npu插件。

## 安装插件<a name="section189463341114"></a>

1.  登录CCE控制台，进入集群，单击左侧导航栏的“插件管理“，在右侧好到**huawei-npu**，单击“安装“。
2.  该插件默认使用如下参数。

    ```
    {
    	"check_frequency_failed_threshold": 100,
    	"check_frequency_fall_times": 3,
    	"check_frequency_gate": false,
    	"check_frequency_recover_threshold": 100,
    	"check_frequency_rise_times": 2,
    	"container_path": "/usr/local/HiAI_unused",
    	"host_path": "/usr/local/HiAI_unused"
    }
    ```

3.  单击“安装“。

## 版本记录<a name="section183121449435"></a>

**表 1**  CCE插件版本记录

<a name="table88489551792"></a>
<table><thead align="left"><tr id="row139251455994"><th class="cellrowborder" valign="top" width="37.50531236719082%" id="mcps1.2.3.1.1"><p id="p13601510205420"><a name="p13601510205420"></a><a name="p13601510205420"></a>插件版本</p>
</th>
<th class="cellrowborder" valign="top" width="62.494687632809175%" id="mcps1.2.3.1.2"><p id="p156011107542"><a name="p156011107542"></a><a name="p156011107542"></a>支持的集群版本</p>
</th>
</tr>
</thead>
<tbody><tr id="row8757710175517"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p1867015556216"><a name="p1867015556216"></a><a name="p1867015556216"></a>1.2.2</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p1596191345312"><a name="p1596191345312"></a><a name="p1596191345312"></a>CCE集群/v1.(19|21|23).*/</p>
<p id="p3596313105318"><a name="p3596313105318"></a><a name="p3596313105318"></a>鲲鹏集群/v1.(19|21|23).*/</p>
</td>
</tr>
<tr id="row17276317105810"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p126701155428"><a name="p126701155428"></a><a name="p126701155428"></a>1.2.1</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p107851028195312"><a name="p107851028195312"></a><a name="p107851028195312"></a>CCE集群/v1.(19|21|23).*/</p>
<p id="p77851028125311"><a name="p77851028125311"></a><a name="p77851028125311"></a>鲲鹏集群/v1.(19|21|23).*/</p>
</td>
</tr>
<tr id="row723201855819"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p186701655921"><a name="p186701655921"></a><a name="p186701655921"></a>1.1.8</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p10225434145311"><a name="p10225434145311"></a><a name="p10225434145311"></a>CCE集群/v1.(15|17|19|21).*/</p>
<p id="p1822514344539"><a name="p1822514344539"></a><a name="p1822514344539"></a>鲲鹏集群/v1.(15|17|19|21).*/</p>
</td>
</tr>
<tr id="row19850201865813"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p19670155622"><a name="p19670155622"></a><a name="p19670155622"></a>1.1.2</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p21865255311"><a name="p21865255311"></a><a name="p21865255311"></a>CCE集群/v1.(15|17|19).*/</p>
<p id="p9187529530"><a name="p9187529530"></a><a name="p9187529530"></a>鲲鹏集群/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row1331711107"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p116711155224"><a name="p116711155224"></a><a name="p116711155224"></a>1.1.1</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p101643615546"><a name="p101643615546"></a><a name="p101643615546"></a>CCE集群/v1.(15|17|19).*/</p>
<p id="p71641766547"><a name="p71641766547"></a><a name="p71641766547"></a>鲲鹏集群/v1.(15|17|19).*/</p>
</td>
</tr>
<tr id="row56109111006"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p267114551522"><a name="p267114551522"></a><a name="p267114551522"></a>1.1.0</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p10829910105415"><a name="p10829910105415"></a><a name="p10829910105415"></a>CCE集群/v1.(17|19).*/</p>
<p id="p182916100544"><a name="p182916100544"></a><a name="p182916100544"></a>鲲鹏集群/v1.(17|19).*/</p>
</td>
</tr>
<tr id="row97371611105"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p176711955925"><a name="p176711955925"></a><a name="p176711955925"></a>1.0.8</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p124771025185418"><a name="p124771025185418"></a><a name="p124771025185418"></a>CCE集群/v1.(13|15|17).*/</p>
<p id="p15477122535413"><a name="p15477122535413"></a><a name="p15477122535413"></a>鲲鹏集群/v1.(13|15|17).*/</p>
</td>
</tr>
<tr id="row1387891111011"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p2671175513219"><a name="p2671175513219"></a><a name="p2671175513219"></a>1.0.6</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p1811116469542"><a name="p1811116469542"></a><a name="p1811116469542"></a>CCE集群/v1.(13|15|17).*/</p>
<p id="p151110460548"><a name="p151110460548"></a><a name="p151110460548"></a>鲲鹏集群/v1.(13|15|17).*/</p>
</td>
</tr>
<tr id="row108141216015"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p1667118551122"><a name="p1667118551122"></a><a name="p1667118551122"></a>1.0.5</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p911644610541"><a name="p911644610541"></a><a name="p911644610541"></a>CCE集群/v1.(13|15|17).*/</p>
<p id="p0116154616542"><a name="p0116154616542"></a><a name="p0116154616542"></a>鲲鹏集群/v1.(13|15|17).*/</p>
</td>
</tr>
<tr id="row11604175314219"><td class="cellrowborder" valign="top" width="37.50531236719082%" headers="mcps1.2.3.1.1 "><p id="p2671125516210"><a name="p2671125516210"></a><a name="p2671125516210"></a>1.0.3</p>
</td>
<td class="cellrowborder" valign="top" width="62.494687632809175%" headers="mcps1.2.3.1.2 "><p id="p811734645417"><a name="p811734645417"></a><a name="p811734645417"></a>CCE集群/v1.(13|15|17).*/</p>
<p id="p20117134617546"><a name="p20117134617546"></a><a name="p20117134617546"></a>鲲鹏集群/v1.(13|15|17).*/</p>
</td>
</tr>
</tbody>
</table>

