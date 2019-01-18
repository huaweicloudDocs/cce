# 删除Job<a name="cce_02_0158"></a>

## 功能介绍<a name="section41928453"></a>

This API is used to delete a Job.

## URI<a name="section41811761"></a>

DELETE /apis/batch/v1/namespaces/\{namespace\}/jobs/\{name\}

[表1](#d0e40914)描述该API的参数。

**表 1**  参数解释

<a name="d0e40914"></a>
<table><thead align="left"><tr id="row55265855"><th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.1"><p id="p65652297517"><a name="p65652297517"></a><a name="p65652297517"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="23%" id="mcps1.2.4.1.2"><p id="p165661629135114"><a name="p165661629135114"></a><a name="p165661629135114"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="44%" id="mcps1.2.4.1.3"><p id="p14567629115114"><a name="p14567629115114"></a><a name="p14567629115114"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row64362693"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p45995684"><a name="p45995684"></a><a name="p45995684"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p34662956"><a name="p34662956"></a><a name="p34662956"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p56236036"><a name="p56236036"></a><a name="p56236036"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="row36362277"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p59663353"><a name="p59663353"></a><a name="p59663353"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p893425"><a name="p893425"></a><a name="p893425"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p5258614"><a name="p5258614"></a><a name="p5258614"></a>name of the Job</p>
</td>
</tr>
<tr id="row47327528"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p8324587"><a name="p8324587"></a><a name="p8324587"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p3202926"><a name="p3202926"></a><a name="p3202926"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p58110425"><a name="p58110425"></a><a name="p58110425"></a>object name and auth scope, such as for teams and projects</p>
</td>
</tr>
<tr id="row53231781"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p16807041"><a name="p16807041"></a><a name="p16807041"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p19193048"><a name="p19193048"></a><a name="p19193048"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p11133076"><a name="p11133076"></a><a name="p11133076"></a>The duration in seconds before the object should be deleted. Value must be a non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
</td>
</tr>
<tr id="row33088828"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p62949386"><a name="p62949386"></a><a name="p62949386"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p65735472"><a name="p65735472"></a><a name="p65735472"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p22973015"><a name="p22973015"></a><a name="p22973015"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="row5430546"><td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.1 "><p id="p37221085"><a name="p37221085"></a><a name="p37221085"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.2 "><p id="p62117884"><a name="p62117884"></a><a name="p62117884"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.3 "><p id="p12794299614"><a name="p12794299614"></a><a name="p12794299614"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: 'Orphan' - orphan the dependents; 'Background' - allow the garbage collector to delete the dependents in the background; 'Foreground' - a cascading policy that deletes all dependents in the foreground.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section40761536"></a>

**请求参数：**

请求参数如[表2](#d0e41006)所示。

**表 2**  参数解释

<a name="d0e41006"></a>
<table><thead align="left"><tr id="row37021524"><th class="cellrowborder" valign="top" width="21.42785721427857%" id="mcps1.2.5.1.1"><p id="p45953457"><a name="p45953457"></a><a name="p45953457"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.2"><p id="p31242518"><a name="p31242518"></a><a name="p31242518"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.3"><p id="p47616044"><a name="p47616044"></a><a name="p47616044"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.796020397960206%" id="mcps1.2.5.1.4"><p id="p31694362"><a name="p31694362"></a><a name="p31694362"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row17106569"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p43454881"><a name="p43454881"></a><a name="p43454881"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p30184457"><a name="p30184457"></a><a name="p30184457"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p29021929"><a name="p29021929"></a><a name="p29021929"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p1966058"><a name="p1966058"></a><a name="p1966058"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
<p id="p17694526"><a name="p17694526"></a><a name="p17694526"></a>The value of this parameter is <strong id="b18351239192313"><a name="b18351239192313"></a><a name="b18351239192313"></a>DeleteOptions</strong>.</p>
</td>
</tr>
<tr id="row23970515"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p62563548"><a name="p62563548"></a><a name="p62563548"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p34482626"><a name="p34482626"></a><a name="p34482626"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p41629292"><a name="p41629292"></a><a name="p41629292"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p16529474"><a name="p16529474"></a><a name="p16529474"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
<p id="p14547546"><a name="p14547546"></a><a name="p14547546"></a>The value of this parameter is <strong id="b63819054"><a name="b63819054"></a><a name="b63819054"></a>v1</strong>.</p>
</td>
</tr>
<tr id="row37500574"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p17647683"><a name="p17647683"></a><a name="p17647683"></a>gracePeriodSeconds</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p20176241"><a name="p20176241"></a><a name="p20176241"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p23662799"><a name="p23662799"></a><a name="p23662799"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p37638533"><a name="p37638533"></a><a name="p37638533"></a>The duration in seconds before the object should be deleted. Value must be a non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately.</p>
<p id="p3202481"><a name="p3202481"></a><a name="p3202481"></a>Value range of this parameter: &gt; 0.</p>
</td>
</tr>
<tr id="row28822332"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p52907547"><a name="p52907547"></a><a name="p52907547"></a>preconditions</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p57652939"><a name="p57652939"></a><a name="p57652939"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p39376500"><a name="p39376500"></a><a name="p39376500"></a><a href="#d0e41122">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p49983653"><a name="p49983653"></a><a name="p49983653"></a>Must be fulfilled before a deletion is carried out. If not possible, a 409 Conflict status will be returned.</p>
</td>
</tr>
<tr id="row47199694"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p65078864"><a name="p65078864"></a><a name="p65078864"></a>orphanDependents</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p36896618"><a name="p36896618"></a><a name="p36896618"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p35836101"><a name="p35836101"></a><a name="p35836101"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p104451656115513"><a name="p104451656115513"></a><a name="p104451656115513"></a>Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both.</p>
</td>
</tr>
<tr id="row19170001"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p9266244"><a name="p9266244"></a><a name="p9266244"></a>propagationPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p12368308"><a name="p12368308"></a><a name="p12368308"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p62308872"><a name="p62308872"></a><a name="p62308872"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p1991018330554"><a name="p1991018330554"></a><a name="p1991018330554"></a>Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: 'Orphan' - orphan the dependents; 'Background' - allow the garbage collector to delete the dependents in the background; 'Foreground' - a cascading policy that deletes all dependents in the foreground.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  preconditions字段数据结构说明

<a name="d0e41122"></a>
<table><thead align="left"><tr id="row62063231"><th class="cellrowborder" valign="top" width="21.42785721427857%" id="mcps1.2.5.1.1"><p id="p61065843"><a name="p61065843"></a><a name="p61065843"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.2"><p id="p47386251"><a name="p47386251"></a><a name="p47386251"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.3"><p id="p13081136"><a name="p13081136"></a><a name="p13081136"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="39.796020397960206%" id="mcps1.2.5.1.4"><p id="p52939081"><a name="p52939081"></a><a name="p52939081"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row60207167"><td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.5.1.1 "><p id="p44942329"><a name="p44942329"></a><a name="p44942329"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.2 "><p id="p16450015"><a name="p16450015"></a><a name="p16450015"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.3 "><p id="p57382875"><a name="p57382875"></a><a name="p57382875"></a>types.UID</p>
</td>
<td class="cellrowborder" valign="top" width="39.796020397960206%" headers="mcps1.2.5.1.4 "><p id="p17501266"><a name="p17501266"></a><a name="p17501266"></a>Specifies the target UID.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

-   只删除Job（对应Pod不删除）：

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "gracePeriodSeconds": 0,
        "propagationPolicy": "Orphan"
    }
    ```

-   前台级联删除（按照Pod-\>Job的顺序进行删除）

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Foreground"
    }
    ```

-   后台级联删除（按照Job-\>Pod的顺序进行删除）

    ```
    {
        "kind": "DeleteOptions",
        "apiVersion": "v1",
        "propagationPolicy": "Background"
    }
    ```


## 响应消息<a name="section31309505"></a>

**响应参数：**

响应参数的详细描述请参见[表4](删除Secret.md#zh-cn_topic_0079615047_table30941925)。

**响应示例：**

```
{
    "kind": "Job",
    "apiVersion": "batch/v1",
    "metadata": {
        "name": "jobs-12130306",
        "namespace": "ns-12130306-s",
        "selfLink": "/apis/batch/v1/namespaces/ns-12130306-s/jobs/jobs-12130306",
        "uid": "eed6b02b-dfb3-11e7-9c19-fa163e2d897b",
        "resourceVersion": "419072",
        "creationTimestamp": "2017-12-13T03:15:55Z",
        "deletionTimestamp": "2017-12-13T03:15:56Z",
        "deletionGracePeriodSeconds": 0,
        "labels": {
            "app": "new-jobs",
            "name": "job-test"
        },
        "finalizers": [
            "orphan"
        ],
        "enable": true
    },
    "spec": {
        "parallelism": 1,
        "completions": 1,
        "selector": {
            "matchLabels": {
                "controller-uid": "eed6b02b-dfb3-11e7-9c19-fa163e2d897b"
            }
        },
        "template": {
            "metadata": {
                "name": "jobs-12130306",
                "creationTimestamp": null,
                "labels": {
                    "controller-uid": "eed6b02b-dfb3-11e7-9c19-fa163e2d897b",
                    "job-name": "jobs-12130306",
                    "name": "job-test"
                },
                "enable": true
            },
            "spec": {
                "containers": [
                    {
                        "name": "jobs-12130306",
                        "image": "172.16.5.235:20202/test/redis:latest",
                        "resources": {},
                        "terminationMessagePath": "/dev/termination-log",
                        "terminationMessagePolicy": "File",
                        "imagePullPolicy": "Always"
                    }
                ],
                "restartPolicy": "Never",
                "terminationGracePeriodSeconds": 30,
                "dnsPolicy": "ClusterFirst",
                "securityContext": {},
                "schedulerName": "default-scheduler"
            }
        }
    },
    "status": {
        "startTime": "2017-12-13T03:15:55Z",
        "active": 1
    }
}
```

## 状态码<a name="section13350095"></a>

[表4](#d0e41189)描述API的状态码。

**表 4**  状态码

<a name="d0e41189"></a>
<table><thead align="left"><tr id="row46934970"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p43636236"><a name="p43636236"></a><a name="p43636236"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p44874251"><a name="p44874251"></a><a name="p44874251"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row10935710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p13377326"><a name="p13377326"></a><a name="p13377326"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p9821602"><a name="p9821602"></a><a name="p9821602"></a>Delete a Job resource object successfully.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

