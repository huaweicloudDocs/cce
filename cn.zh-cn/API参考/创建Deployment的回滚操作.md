# 创建Deployment的回滚操作<a name="cce_02_0120"></a>

## 功能介绍<a name="section41398477"></a>

This API is used to create rollback of a Deployment Rollback.

## URI<a name="section37041974"></a>

PATCH /apis/apps/v1/namespaces/\{namespace\}/deployments/\{name\} \(Supports only 1.17 and 1.17+\)

POST /apis/extensions/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/rollback \(Compatible\)

POST /apis/apps/v1beta1/namespaces/\{namespace\}/deployments/\{name\}/rollback \(Supports only 1.7\)

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
</tbody>
</table>

## 请求消息<a name="section64942310"></a>

**请求参数：**

请求参数如[表2](#table165001054142614)、[表3](#table10173552218)所示。

**表 2**  请求Header参数说明

<a name="table165001054142614"></a>
<table><thead align="left"><tr id="row55001954122614"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p115009545264"><a name="p115009545264"></a><a name="p115009545264"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.4.1.2"><p id="p175001547265"><a name="p175001547265"></a><a name="p175001547265"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61%" id="mcps1.2.4.1.3"><p id="p16500154162611"><a name="p16500154162611"></a><a name="p16500154162611"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row199801811203412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p69808112344"><a name="p69808112344"></a><a name="p69808112344"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="p3980111103414"><a name="p3980111103414"></a><a name="p3980111103414"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61%" headers="mcps1.2.4.1.3 "><p id="p169801011203416"><a name="p169801011203416"></a><a name="p169801011203416"></a>消息体的类型（格式），取值：</p>
<a name="ul7385444163617"></a><a name="ul7385444163617"></a><ul id="ul7385444163617"><li>application/json-patch+json</li></ul>
<p id="p27583298516"><a name="p27583298516"></a><a name="p27583298516"></a><strong id="b12794172325012"><a name="b12794172325012"></a><a name="b12794172325012"></a>仅1.17版本的patch请求需要该header</strong>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  请求参数

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
<tr id="row12767935115620"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p1718704495718"><a name="p1718704495718"></a><a name="p1718704495718"></a>op</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p2018774413576"><a name="p2018774413576"></a><a name="p2018774413576"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p1418714485710"><a name="p1418714485710"></a><a name="p1418714485710"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.5.1.4 "><p id="p6187144135720"><a name="p6187144135720"></a><a name="p6187144135720"></a>Operation for this patch, value must be “replace”.</p>
</td>
</tr>
<tr id="row876713512567"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p0188154465717"><a name="p0188154465717"></a><a name="p0188154465717"></a>path</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p81881044115713"><a name="p81881044115713"></a><a name="p81881044115713"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p10188204495713"><a name="p10188204495713"></a><a name="p10188204495713"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.5.1.4 "><p id="p61881544195714"><a name="p61881544195714"></a><a name="p61881544195714"></a>Path to replace for this deployment, must be “/spec/template” or “/metadata/annotations”</p>
</td>
</tr>
<tr id="row1576793520563"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p10188134410573"><a name="p10188134410573"></a><a name="p10188134410573"></a>value</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p418824418571"><a name="p418824418571"></a><a name="p418824418571"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.3 "><p id="p1518816448572"><a name="p1518816448572"></a><a name="p1518816448572"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table52089545">template</a> object</p>
<p id="p14188744185714"><a name="p14188744185714"></a><a name="p14188744185714"></a>or</p>
<p id="p61883444575"><a name="p61883444575"></a><a name="p61883444575"></a>revision object</p>
</td>
<td class="cellrowborder" valign="top" width="43%" headers="mcps1.2.5.1.4 "><p id="p12188174417575"><a name="p12188174417575"></a><a name="p12188174417575"></a>Template describes the pods’ template that will be rollback which can be got from certain replicset.spec.template, template correspond to path “/spec/template”.</p>
<p id="p8188174435719"><a name="p8188174435719"></a><a name="p8188174435719"></a>Revision describes the revision of replicset to rollback, revision correspond to path “/metadata/annotations”</p>
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

**表 4**  rollbackTo字段数据结构说明

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

**表 5**  revision字段说明

<a name="table113892521219"></a>
<table><thead align="left"><tr id="row1538965210113"><th class="cellrowborder" valign="top" width="19%" id="mcps1.2.5.1.1"><p id="p163898521118"><a name="p163898521118"></a><a name="p163898521118"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.2"><p id="p73892052917"><a name="p73892052917"></a><a name="p73892052917"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.5.1.3"><p id="p838915522112"><a name="p838915522112"></a><a name="p838915522112"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44%" id="mcps1.2.5.1.4"><p id="p1438916521312"><a name="p1438916521312"></a><a name="p1438916521312"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1738965217117"><td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.5.1.1 "><p id="p1720715511212"><a name="p1720715511212"></a><a name="p1720715511212"></a>deployment.kubernetes.io/revision</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="p18207145829"><a name="p18207145829"></a><a name="p18207145829"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.5.1.3 "><p id="p920714512211"><a name="p920714512211"></a><a name="p920714512211"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.5.1.4 "><p id="p202078511215"><a name="p202078511215"></a><a name="p202078511215"></a>The revision of replicset to rollback.</p>
</td>
</tr>
</tbody>
</table>

**1.17及以上版本请求示例：**

```
[
	{
		"op": "replace",
		"path": "/spec/template",
		"value": {
			"metadata": {
				"creationTimestamp": null,
				"labels": {
					"app": "test-roll"
				},
				"annotations": {
					"metrics.alpha.kubernetes.io/custom-endpoints": "[{\"api\":\"\",\"path\":\"\",\"port\":\"\",\"names\":\"\"}]"
				}
			},
			"spec": {
				"containers": [
					{
						"name": "container-0",
						"image": "1*.*.*.*:20202/peedssw/nginx:latest",
						"env": [
							{
								"name": "PAAS_APP_NAME",
								"value": "test-roll"
							},
							{
								"name": "PAAS_NAMESPACE",
								"value": "default"
							},
							{
								"name": "PAAS_PROJECT_ID",
								"value": "47eb1d64cbeb45cfa01ae20af4f4b563"
							}
						],
						"resources": {
							"limits": {
								"cpu": "250m",
								"memory": "512Mi"
							},
							"requests": {
								"cpu": "100m",
								"memory": "100Mi"
							}
						},
						"terminationMessagePath": "/dev/termination-log",
						"terminationMessagePolicy": "File",
						"imagePullPolicy": "Always"
					}
				],
				"restartPolicy": "Always",
				"terminationGracePeriodSeconds": 30,
				"dnsPolicy": "ClusterFirst",
				"securityContext": {},
				"imagePullSecrets": [
					{
						"name": "default-secret"
					}
				],
				"affinity": {},
				"schedulerName": "default-scheduler",
				"tolerations": [
					{
						"key": "node.kubernetes.io/not-ready",
						"operator": "Exists",
						"effect": "NoExecute",
						"tolerationSeconds": 300
					},
					{
						"key": "node.kubernetes.io/unreachable",
						"operator": "Exists",
						"effect": "NoExecute",
						"tolerationSeconds": 300
					}
				],
				"dnsConfig": {
					"options": [
						{
							"name": "timeout",
							"value": ""
						},
						{
							"name": "ndots",
							"value": "5"
						},
						{
							"name": "single-request-reopen"
						}
					]
				}
			}
		}
	},
	{
		"op": "replace",
		"path": "/metadata/annotations",
		"value": {
			"deployment.kubernetes.io/revision": "6"
		}
	}
]
```

**1.17以下版本请求示例：**

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

响应参数的详细描述请参见[表3](#table10173552218)

**1.17及以上版本请求示例：**

```
{
	"kind": "Deployment",
	"apiVersion": "apps/v1",
	"metadata": {
		"name": "test-roll",
		"namespace": "default",
		"selfLink": "/apis/apps/v1/namespaces/default/deployments/test-roll",
		"uid": "f5722cc7-1144-4834-9970-dcb505323d64",
		"resourceVersion": "2821114",
		"generation": 7,
		"creationTimestamp": "2020-06-22T07:14:40Z",
		"labels": {
			"appgroup": ""
		},
		"annotations": {
			"deployment.kubernetes.io/revision": "6"
		}
	},
	"spec": {
		"replicas": 1,
		"selector": {
			"matchLabels": {
				"app": "test-roll"
			}
		},
		"template": {
			"metadata": {
				"creationTimestamp": null,
				"labels": {
					"app": "test-roll"
				},
				"annotations": {
					"metrics.alpha.kubernetes.io/custom-endpoints": "[{\"api\":\"\",\"path\":\"\",\"port\":\"\",\"names\":\"\"}]"
				}
			},
			"spec": {
				"containers": [
					{
						"name": "container-0",
						"image": "1*.*.*.*:20202/peedssw/nginx:latest",
						"env": [
							{
								"name": "PAAS_APP_NAME",
								"value": "test-roll"
							},
							{
								"name": "PAAS_NAMESPACE",
								"value": "default"
							},
							{
								"name": "PAAS_PROJECT_ID",
								"value": "47eb1d64cbeb45cfa01ae20af4f4b563"
							}
						],
						"resources": {
							"limits": {
								"cpu": "250m",
								"memory": "512Mi"
							},
							"requests": {
								"cpu": "100m",
								"memory": "100Mi"
							}
						},
						"terminationMessagePath": "/dev/termination-log",
						"terminationMessagePolicy": "File",
						"imagePullPolicy": "Always"
					}
				],
				"restartPolicy": "Always",
				"terminationGracePeriodSeconds": 30,
				"dnsPolicy": "ClusterFirst",
				"securityContext": {},
				"imagePullSecrets": [
					{
						"name": "default-secret"
					}
				],
				"affinity": {},
				"schedulerName": "default-scheduler",
				"tolerations": [
					{
						"key": "node.kubernetes.io/not-ready",
						"operator": "Exists",
						"effect": "NoExecute",
						"tolerationSeconds": 300
					},
					{
						"key": "node.kubernetes.io/unreachable",
						"operator": "Exists",
						"effect": "NoExecute",
						"tolerationSeconds": 300
					}
				],
				"dnsConfig": {
					"options": [
						{
							"name": "timeout",
							"value": ""
						},
						{
							"name": "ndots",
							"value": "5"
						},
						{
							"name": "single-request-reopen"
						}
					]
				}
			}
		},
		"strategy": {
			"type": "Recreate"
		},
		"revisionHistoryLimit": 10,
		"progressDeadlineSeconds": 600
	},
	"status": {
		"observedGeneration": 6,
		"replicas": 1,
		"updatedReplicas": 1,
		"readyReplicas": 1,
		"availableReplicas": 1,
		"conditions": [
			{
				"type": "Available",
				"status": "True",
				"lastUpdateTime": "2020-06-22T08:08:42Z",
				"lastTransitionTime": "2020-06-22T08:08:42Z",
				"reason": "MinimumReplicasAvailable",
				"message": "Deployment has minimum availability."
			},
			{
				"type": "Progressing",
				"status": "True",
				"lastUpdateTime": "2020-06-22T08:08:42Z",
				"lastTransitionTime": "2020-06-22T07:14:40Z",
				"reason": "NewReplicaSetAvailable",
				"message": "ReplicaSet \"test-roll-74dd548fb8\" has successfully progressed."
			}
		]
	}
}
```

**1.17以下版本响应示例：**

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

[表6](#d0e35052)描述API的状态码。

**表 6**  状态码

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

