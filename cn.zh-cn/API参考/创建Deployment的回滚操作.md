# 创建Deployment的回滚操作<a name="cce_02_0120"></a>

## 功能介绍<a name="section41398477"></a>

This API is used to create rollback of a Deployment Rollback.

## URI<a name="section37041974"></a>

POST /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/rollback \(Compatible\)

POST /apis/apps/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/rollback \(Supports only1.7\)

[表1](#d0e34843)描述该API的参数。

**表 1**  参数解释

<a name="d0e34843"></a>
<table><thead align="left"><tr id="row27299130"><th class="cellrowborder" valign="top" width="16.16%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.16%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="67.67999999999999%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row41719447"><td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.1 "><p id="p23832023"><a name="p23832023"></a><a name="p23832023"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p51345720"><a name="p51345720"></a><a name="p51345720"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.4.1.3 "><p id="p65362657"><a name="p65362657"></a><a name="p65362657"></a>name of the DeploymentRollback</p>
</td>
</tr>
<tr id="row51393009"><td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.1 "><p id="p2084186"><a name="p2084186"></a><a name="p2084186"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p34601376"><a name="p34601376"></a><a name="p34601376"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.4.1.3 "><p id="p51248042"><a name="p51248042"></a><a name="p51248042"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row58579196"><td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.1 "><p id="p47294440"><a name="p47294440"></a><a name="p47294440"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.16%" headers="mcps1.2.4.1.2 "><p id="p5644428"><a name="p5644428"></a><a name="p5644428"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="67.67999999999999%" headers="mcps1.2.4.1.3 "><p id="p54545553"><a name="p54545553"></a><a name="p54545553"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section64942310"></a>

**请求参数：**

请求参数如[表2](#table10173552218)所示。

**表 2**  请求参数

<a name="table10173552218"></a>
<table><thead align="left"><tr id="row31887193"><th class="cellrowborder" valign="top" width="19%" id="mcps1.2.5.1.1"><p id="p32725858"><a name="p32725858"></a><a name="p32725858"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.2"><p id="p33548811"><a name="p33548811"></a><a name="p33548811"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="22%" id="mcps1.2.5.1.3"><p id="p33099132"><a name="p33099132"></a><a name="p33099132"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="43%" id="mcps1.2.5.1.4"><p id="p63784030"><a name="p63784030"></a><a name="p63784030"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row66232792"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p63255955"><a name="p63255955"></a><a name="p63255955"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p23458743"><a name="p23458743"></a><a name="p23458743"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p21109994"><a name="p21109994"></a><a name="p21109994"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.5.1.4 "><p id="p32187991"><a name="p32187991"></a><a name="p32187991"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row21256466"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p44052166"><a name="p44052166"></a><a name="p44052166"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p11455687"><a name="p11455687"></a><a name="p11455687"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p55495420"><a name="p55495420"></a><a name="p55495420"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.5.1.4 "><p id="p65944013"><a name="p65944013"></a><a name="p65944013"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="row56625212"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p23239492"><a name="p23239492"></a><a name="p23239492"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p3350684"><a name="p3350684"></a><a name="p3350684"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p2969964"><a name="p2969964"></a><a name="p2969964"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.5.1.4 "><p id="p39240541"><a name="p39240541"></a><a name="p39240541"></a>Required: This must match the Name of a deployment.</p>
</td>
</tr>
<tr id="row17620553"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p17978702"><a name="p17978702"></a><a name="p17978702"></a>rollbackTo</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p46988743"><a name="p46988743"></a><a name="p46988743"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p47991837"><a name="p47991837"></a><a name="p47991837"></a><a href="#table3169229152410">rollbackTo</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.5.1.4 "><p id="p22331121"><a name="p22331121"></a><a name="p22331121"></a>The config of this deployment rollback.</p>
</td>
</tr>
<tr id="row66762365"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p39042521"><a name="p39042521"></a><a name="p39042521"></a>updatedAnnotations</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p8327600"><a name="p8327600"></a><a name="p8327600"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p3447020"><a name="p3447020"></a><a name="p3447020"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.5.1.4 "><p id="p10773237"><a name="p10773237"></a><a name="p10773237"></a>The annotations to be updated to a deployment</p>
</td>
</tr>
</tbody>
</table>

**表 3**  rollbackTo字段数据结构说明

<a name="table3169229152410"></a>
<table><thead align="left"><tr id="row49859166"><th class="cellrowborder" valign="top" width="19%" id="mcps1.2.5.1.1"><p id="p12060663"><a name="p12060663"></a><a name="p12060663"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.2"><p id="p37389616"><a name="p37389616"></a><a name="p37389616"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.5.1.3"><p id="p8660017"><a name="p8660017"></a><a name="p8660017"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44%" id="mcps1.2.5.1.4"><p id="p30372771"><a name="p30372771"></a><a name="p30372771"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row44275373"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p29535480"><a name="p29535480"></a><a name="p29535480"></a>revision</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p43563692"><a name="p43563692"></a><a name="p43563692"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p38998127"><a name="p38998127"></a><a name="p38998127"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.5.1.4 "><p id="p4731756"><a name="p4731756"></a><a name="p4731756"></a>The revision to rollback to. If set to 0, rollbck to the last revision.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{
    "kind": "DeploymentRollback",
    "apiVersion": "extensions/v1beta1",
    "name": "deploy-ex-12130306",
    "rollbackTo": {
        "revision": 0
    }
}
```

## 响应消息<a name="section47609878"></a>

**响应参数：**

响应参数的详细描述请参见[表2](#table10173552218)

**响应示例：**

```
{
    "kind": "Status",
    "apiVersion": "v1",
    "metadata": {},
    "status": "Success",
    "message": "rollback request for deployment \"deploy-ex-12130306\" succeeded",
    "code": 201
}
```

## 状态码<a name="section25835719"></a>

[表4](#d0e35052)描述API的状态码。

**表 4**  状态码

<a name="d0e35052"></a>
<table><thead align="left"><tr id="row49033913"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p12324050"><a name="p12324050"></a><a name="p12324050"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p58723999"><a name="p58723999"></a><a name="p58723999"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row59023497"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p16173943"><a name="p16173943"></a><a name="p16173943"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p35021010"><a name="p35021010"></a><a name="p35021010"></a>The request has been fulfilled, resulting in the creation of a new resource.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

