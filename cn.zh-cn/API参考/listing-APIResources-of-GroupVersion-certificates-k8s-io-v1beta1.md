# listing APIResources of GroupVersion certificates.k8s.io/v1beta1<a name="cce_02_0197"></a>

## 功能介绍<a name="section41689235"></a>

This API is used to list GroupVersion "certificates.k8s.io/v1beta1".

## URI<a name="section39658796"></a>

GET /apis/certificates.k8s.io/v1beta1

## 请求消息<a name="section21384849"></a>

N/A.

## 响应消息<a name="section58245913"></a>

**响应参数：**

[表1](#d0e48269)  describes the response parameters.

**表 1**  参数解释

<a name="d0e48269"></a>
<table><thead align="left"><tr id="row5591710"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p50275403"><a name="p50275403"></a><a name="p50275403"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p45775832"><a name="p45775832"></a><a name="p45775832"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p16854893"><a name="p16854893"></a><a name="p16854893"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row23069107"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p56658385"><a name="p56658385"></a><a name="p56658385"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p25926512"><a name="p25926512"></a><a name="p25926512"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p19672760"><a name="p19672760"></a><a name="p19672760"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row42837114"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p47254225"><a name="p47254225"></a><a name="p47254225"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p2387045"><a name="p2387045"></a><a name="p2387045"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p59132957"><a name="p59132957"></a><a name="p59132957"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row62434570"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p24035444"><a name="p24035444"></a><a name="p24035444"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p713975"><a name="p713975"></a><a name="p713975"></a><a href="#cce_02_0197__d0e48319">表2</a></p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p50725899"><a name="p50725899"></a><a name="p50725899"></a>Standard list resource</p>
</td>
</tr>
</tbody>
</table>

**表 2**  resources字段数据结构说明

<a name="d0e48319"></a>
<table><thead align="left"><tr id="row47597760"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p30213385"><a name="p30213385"></a><a name="p30213385"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p31365126"><a name="p31365126"></a><a name="p31365126"></a>Type</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p57547296"><a name="p57547296"></a><a name="p57547296"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row30819390"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p13342665"><a name="p13342665"></a><a name="p13342665"></a>categories</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p7014056"><a name="p7014056"></a><a name="p7014056"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p31267652"><a name="p31267652"></a><a name="p31267652"></a>categories is a list of the grouped resources this resource belongs to (e.g. 'all')</p>
</td>
</tr>
<tr id="row12973412"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p44213413"><a name="p44213413"></a><a name="p44213413"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p24516695"><a name="p24516695"></a><a name="p24516695"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p39695265"><a name="p39695265"></a><a name="p39695265"></a>kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')</p>
</td>
</tr>
<tr id="row21713071"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p13928337"><a name="p13928337"></a><a name="p13928337"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p54453536"><a name="p54453536"></a><a name="p54453536"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p48660291"><a name="p48660291"></a><a name="p48660291"></a>name is the plural name of the resource.</p>
</td>
</tr>
<tr id="row35289440"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p39872381"><a name="p39872381"></a><a name="p39872381"></a>namespaced</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p8437410"><a name="p8437410"></a><a name="p8437410"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p12341624"><a name="p12341624"></a><a name="p12341624"></a>namespaced indicates if a resource is namespaced or not.</p>
</td>
</tr>
<tr id="row43965757"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p4456542"><a name="p4456542"></a><a name="p4456542"></a>shortNames</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p25435653"><a name="p25435653"></a><a name="p25435653"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p47021975"><a name="p47021975"></a><a name="p47021975"></a>shortNames is a list of suggested short names of the resource.</p>
</td>
</tr>
<tr id="row20544597"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p53499637"><a name="p53499637"></a><a name="p53499637"></a>singularName</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p38503350"><a name="p38503350"></a><a name="p38503350"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p31763647"><a name="p31763647"></a><a name="p31763647"></a>singularName is the singular name of the resource. This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.</p>
</td>
</tr>
<tr id="row17437375"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p3141256"><a name="p3141256"></a><a name="p3141256"></a>verbs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p53115182"><a name="p53115182"></a><a name="p53115182"></a>String array</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p7362456"><a name="p7362456"></a><a name="p7362456"></a>verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIResourceList",
    "apiVersion": "v1",
    "groupVersion": "certificates.k8s.io/v1beta1",
    "resources": [
        {
            "name": "certificatesigningrequests",
            "singularName": "",
            "namespaced": false,
            "kind": "CertificateSigningRequest",
            "verbs": [
                "create",
                "delete",
                "deletecollection",
                "get",
                "list",
                "patch",
                "update",
                "watch"
            ],
            "shortNames": [
                "csr"
            ]
        },
        {
            "name": "certificatesigningrequests/approval",
            "singularName": "",
            "namespaced": false,
            "kind": "CertificateSigningRequest",
            "verbs": [
                "update"
            ]
        },
        {
            "name": "certificatesigningrequests/status",
            "singularName": "",
            "namespaced": false,
            "kind": "CertificateSigningRequest",
            "verbs": [
                "update"
            ]
        }
    ]
}
```

## 状态码<a name="section54451175"></a>

[表3](#d0e48420)描述API的状态码。

**表 3**  状态码

<a name="d0e48420"></a>
<table><thead align="left"><tr id="row12429495"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p156188"><a name="p156188"></a><a name="p156188"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p12651253"><a name="p12651253"></a><a name="p12651253"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18118571"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p58318117"><a name="p58318117"></a><a name="p58318117"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p26147019"><a name="p26147019"></a><a name="p26147019"></a>This operation succeeds, and a list of APIResources is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

