# 更新指定的Endpoints<a name="cce_02_0065"></a>

## 功能介绍<a name="sac12fa31d2e14eb987df783ddacf3321"></a>

该API用于更新指定Namespace下的Endpoints对象。

其中以下字段支持更新：

-   metadata.name
-   metadata.namespace
-   metadata.selfLink
-   metadata.resourceVersion
-   metadata.uid
-   metadata.labels
-   metadata.clusterName
-   metadata.generateName
-   metadata.annotations
-   subnet.\*
-   metadata.deletionGracePeriodSeconds

## URI<a name="sf83f35293a2a41608535afbee14767bf"></a>

PATCH /api/v1/namespaces/\{namespace\}/endpoints/\{name\}

[表1](#zh-cn_topic_0079614972_table5045213)  描述该API的参数。

**表 1**  参数描述

<a name="zh-cn_topic_0079614972_table5045213"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614972_row25584516"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0079614972_p59079892"><a name="zh-cn_topic_0079614972_p59079892"></a><a name="zh-cn_topic_0079614972_p59079892"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p11272818201654"><a name="p11272818201654"></a><a name="p11272818201654"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p40683062201654"><a name="p40683062201654"></a><a name="p40683062201654"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614972_row58315944"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614972_p25971051"><a name="zh-cn_topic_0079614972_p25971051"></a><a name="zh-cn_topic_0079614972_p25971051"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614972_p23280366"><a name="zh-cn_topic_0079614972_p23280366"></a><a name="zh-cn_topic_0079614972_p23280366"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614972_p6661465"><a name="zh-cn_topic_0079614972_p6661465"></a><a name="zh-cn_topic_0079614972_p6661465"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614972_row19216572"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614972_p13038474"><a name="zh-cn_topic_0079614972_p13038474"></a><a name="zh-cn_topic_0079614972_p13038474"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614972_p49483440"><a name="zh-cn_topic_0079614972_p49483440"></a><a name="zh-cn_topic_0079614972_p49483440"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614972_p48735703"><a name="zh-cn_topic_0079614972_p48735703"></a><a name="zh-cn_topic_0079614972_p48735703"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="zh-cn_topic_0079614972_row35968146"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0079614972_p27738717"><a name="zh-cn_topic_0079614972_p27738717"></a><a name="zh-cn_topic_0079614972_p27738717"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0079614972_p32243580"><a name="zh-cn_topic_0079614972_p32243580"></a><a name="zh-cn_topic_0079614972_p32243580"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0079614972_p61593176"><a name="zh-cn_topic_0079614972_p61593176"></a><a name="zh-cn_topic_0079614972_p61593176"></a>Name of the Endpoints.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="s657fd059fab74bb29d05f8f4cac1d327"></a>

**请求参数：**

“Content-Type“的详细描述请参见 [PATCH请求方法操作说明](PATCH请求方法操作说明.md)。

**请求示例：**

```
Content-Type: application/merge-patch+json
```

```
{
    "subsets": [
        {
            "addresses": [
                {
                    "ip": "172.16.106.154"
                }
            ],
            "ports": [
                {
                    "port": 1
                }
            ]
        }
    ]
}
```

## 响应消息<a name="s6b95f47c4ccf4cbd996626e8962eb127"></a>

**响应参数：**

响应参数的详细描述请参见[表2](创建Endpoints.md#zh-cn_topic_0079614955_ref458759912).

**响应示例：**

```
{ 
   "kind": "Endpoints", 
   "apiVersion": "v1", 
   "metadata": { 
     "name": "cluster-test", 
     "namespace": "default", 
   "selfLink": "/api/v1/namespaces/default/endpoints/cluster-test", 
     "uid": "88a7230f-5d36-11e6-aeb9-286ed488fafe", 
     "resourceVersion": "3182", 
     "creationTimestamp": "2016-08-08T07:05:48Z" 
   }, 
   "subsets": [ 
     { 
       "addresses": [ 
         { 
           "ip": "172.16.106.150" 
         }, 
         { 
           "ip": "172.16.106.154" 
         }, 
         { 
           "ip": "172.16.79.123" 
         } 
       ], 
       "ports": [ 
         { 
           "port": 1, 
           "protocol": "TCP" 
         } 
       ] 
     } 
   ] 
 }
```

## 状态码<a name="s06eee481d5564d248bb167cb6c41cd47"></a>

[表2](#zh-cn_topic_0079614972_table6009104)描述API的状态码。

**表 2**  状态码

<a name="zh-cn_topic_0079614972_table6009104"></a>
<table><thead align="left"><tr id="zh-cn_topic_0079614972_row2835298"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p36832557201654"><a name="p36832557201654"></a><a name="p36832557201654"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p30647120201654"><a name="p30647120201654"></a><a name="p30647120201654"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0079614972_row65623433"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0079614972_p13897850"><a name="zh-cn_topic_0079614972_p13897850"></a><a name="zh-cn_topic_0079614972_p13897850"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0079614972_p51984031"><a name="zh-cn_topic_0079614972_p51984031"></a><a name="zh-cn_topic_0079614972_p51984031"></a>This operation succeeds, and an Endpoint resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

