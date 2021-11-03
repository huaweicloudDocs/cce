# 删除Deployment<a name="cce_02_0121"></a>

## 功能介绍<a name="section65321233"></a>

This API is used to delete a Deployment resource object.

## URI<a name="section51020189"></a>

DELETE /apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\}

[表1](#table2758112513516)描述该API的参数。

**表 1**  参数解释

<a name="table2758112513516"></a>
<table><thead align="left"><tr id="row65815647"><th class="cellrowborder" valign="top" width="17.348265173482652%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="66.32336766323368%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row5608934"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p51670535"><a name="p51670535"></a><a name="p51670535"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p24563845"><a name="p24563845"></a><a name="p24563845"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p43514439"><a name="p43514439"></a><a name="p43514439"></a>name of the Deployment</p>
</td>
</tr>
<tr id="row56085638"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p46642793"><a name="p46642793"></a><a name="p46642793"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p19969926"><a name="p19969926"></a><a name="p19969926"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p6951299"><a name="p6951299"></a><a name="p6951299"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row62561693"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p34332366"><a name="p34332366"></a><a name="p34332366"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p29458227"><a name="p29458227"></a><a name="p29458227"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p37306164"><a name="p37306164"></a><a name="p37306164"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row211163"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p17104275"><a name="p17104275"></a><a name="p17104275"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p43269019"><a name="p43269019"></a><a name="p43269019"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p15129627"><a name="p15129627"></a><a name="p15129627"></a>The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="row1948920"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p23644832"><a name="p23644832"></a><a name="p23644832"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p36183253"><a name="p36183253"></a><a name="p36183253"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p45162366"><a name="p45162366"></a><a name="p45162366"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="row3808114"><td class="cellrowborder" valign="top" width="17.348265173482652%" headers="mcps1.2.4.1.1 "><p id="p40021797"><a name="p40021797"></a><a name="p40021797"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.4.1.2 "><p id="p20540096"><a name="p20540096"></a><a name="p20540096"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="66.32336766323368%" headers="mcps1.2.4.1.3 "><p id="p8453712"><a name="p8453712"></a><a name="p8453712"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: 'Orphan' - orphan the dependents; 'Background' - allow the garbage collector to delete the dependents in the background; 'Foreground' - a cascading policy that deletes all dependents in the foreground.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section56528519"></a>

**请求参数：**

请求参数的详细描述请参见[表2](删除指定的DaemonSet.md#table191461259175715)。

**请求示例：**

-   只删除Deployment（对应ReplicaSet和Pod不删除）

    ```
    {
        "Kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Orphan"
    }
    ```

-   前台级联删除（按照Pod-\>ReplicaSet-\>Deployment的顺序进行删除）

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Foreground"
    }
    ```

-   后台级联删除（按照Deployment-\>ReplicaSet-\>Pod的顺序进行删除）

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Background"
    }
    ```


## 响应消息<a name="section38994624"></a>

**响应参数：**

响应参数的详细描述请参见[表2](删除Secret.md#table13766144711235)。

**响应示例：**

```
{
    "kind": "Status",
    "apiVersion": "v1",
    "metadata": {},
    "status": "Success",
    "details": {
        "name": "deploy-12130306",
        "group": "extensions",
        "kind": "deployments",
        "uid": "27072a31-dfb3-11e7-9c19-fa163e2d897b"
    },
    "code": 200
}
```

## 状态码<a name="section15407297"></a>

[表2](#d0e35248)描述API的状态码。

**表 2**  状态码

<a name="d0e35248"></a>
<table><thead align="left"><tr id="row25883953"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p16225480"><a name="p16225480"></a><a name="p16225480"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p39195466"><a name="p39195466"></a><a name="p39195466"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row20716193"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p290101"><a name="p290101"></a><a name="p290101"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p23498221"><a name="p23498221"></a><a name="p23498221"></a>Delete a Deployments resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

