# 列出APIGroups<a name="cce_02_0187"></a>

## 功能介绍<a name="section29623150"></a>

This API is used to list APIGroups.

## URI<a name="section65281759"></a>

GET /apis

## 请求消息<a name="section50664922"></a>

N/A.

## 响应消息<a name="section53331121"></a>

**响应参数：**

[表1](#d0e45895)  describes the response parameters.

**表 1**  参数解释

<a name="d0e45895"></a>
<table><thead align="left"><tr id="row2745633"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p21069736"><a name="p21069736"></a><a name="p21069736"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p28927084"><a name="p28927084"></a><a name="p28927084"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p61392468"><a name="p61392468"></a><a name="p61392468"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6734025"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p8585138"><a name="p8585138"></a><a name="p8585138"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p24307576"><a name="p24307576"></a><a name="p24307576"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p22756610"><a name="p22756610"></a><a name="p22756610"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row3482900"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p13679488"><a name="p13679488"></a><a name="p13679488"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p34296740"><a name="p34296740"></a><a name="p34296740"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p26572585"><a name="p26572585"></a><a name="p26572585"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row37826679"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p44062192"><a name="p44062192"></a><a name="p44062192"></a>groups</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p12267805"><a name="p12267805"></a><a name="p12267805"></a><a href="#d0e45945">groups</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p17751458"><a name="p17751458"></a><a name="p17751458"></a>Standard list APIGroup</p>
</td>
</tr>
</tbody>
</table>

**表 2**  groups字段数据结构说明

<a name="d0e45945"></a>
<table><thead align="left"><tr id="row17510563"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p9069460"><a name="p9069460"></a><a name="p9069460"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p63537654"><a name="p63537654"></a><a name="p63537654"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p46276336"><a name="p46276336"></a><a name="p46276336"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row57395755"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p18544591"><a name="p18544591"></a><a name="p18544591"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p25716866"><a name="p25716866"></a><a name="p25716866"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p2691439"><a name="p2691439"></a><a name="p2691439"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row24222954"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p15902238"><a name="p15902238"></a><a name="p15902238"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p13012895"><a name="p13012895"></a><a name="p13012895"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p47411540"><a name="p47411540"></a><a name="p47411540"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="row24050677"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p1947860"><a name="p1947860"></a><a name="p1947860"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p23559004"><a name="p23559004"></a><a name="p23559004"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p29231156"><a name="p29231156"></a><a name="p29231156"></a>name is the name of the group.</p>
</td>
</tr>
<tr id="row61753813"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p36002985"><a name="p36002985"></a><a name="p36002985"></a>preferredVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p30560673"><a name="p30560673"></a><a name="p30560673"></a><a href="#table1222101911189">preferredVersion</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p65697112"><a name="p65697112"></a><a name="p65697112"></a>preferredVersion is the version preferred by the API server, which probably is the storage version.</p>
</td>
</tr>
<tr id="row54403103"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p44575221"><a name="p44575221"></a><a name="p44575221"></a>serverAddressByClientCIDRs</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p53823119"><a name="p53823119"></a><a name="p53823119"></a><a href="#table1531151619177">serverAddressByClientCIDRs</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p45477381"><a name="p45477381"></a><a name="p45477381"></a>a map of client CIDR to server address that is serving this group. This is to help clients reach servers in the most network-efficient way possible. Clients can use the appropriate server address as per the CIDR that they match. In case of multiple matches, clients should use the longest matching CIDR. The server returns only those CIDRs that it thinks that the client can match. For example: the master will return an internal IP CIDR only, if the client reaches the server using an internal IP. Server looks at X-Forwarded-For header or X-Real-Ip header or request.RemoteAddr (in that order) to get the client IP.</p>
</td>
</tr>
<tr id="row6643249"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p1232264"><a name="p1232264"></a><a name="p1232264"></a>versions</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p32704580"><a name="p32704580"></a><a name="p32704580"></a><a href="#table1222101911189">preferredVersion</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p17992762"><a name="p17992762"></a><a name="p17992762"></a>versions are the versions supported in this group.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  serverAddressByClientCIDRs字段数据结构说明

<a name="table1531151619177"></a>
<table><thead align="left"><tr id="row38726134"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p49809167"><a name="p49809167"></a><a name="p49809167"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p8010696"><a name="p8010696"></a><a name="p8010696"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p44886601"><a name="p44886601"></a><a name="p44886601"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row11936059"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p27296709"><a name="p27296709"></a><a name="p27296709"></a>clientCIDR</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p63549840"><a name="p63549840"></a><a name="p63549840"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p47263428"><a name="p47263428"></a><a name="p47263428"></a>The CIDR with which clients can match their IP to figure out the server address that they should use.</p>
</td>
</tr>
<tr id="row22717668"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p28191815"><a name="p28191815"></a><a name="p28191815"></a>serverAddress</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p1835687"><a name="p1835687"></a><a name="p1835687"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p14472939"><a name="p14472939"></a><a name="p14472939"></a>ddress of this server, suitable for a client that matches the above CIDR. This can be a hostname, hostname:port, IP or IP:port.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  preferredVersion字段数据结构说明

<a name="table1222101911189"></a>
<table><thead align="left"><tr id="row63835785"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p3316059"><a name="p3316059"></a><a name="p3316059"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p165378"><a name="p165378"></a><a name="p165378"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p13395686"><a name="p13395686"></a><a name="p13395686"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row11308782"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p43596163"><a name="p43596163"></a><a name="p43596163"></a>groupVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p41628300"><a name="p41628300"></a><a name="p41628300"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p16449138"><a name="p16449138"></a><a name="p16449138"></a>groupVersion specifies the API group and version in the form "group/version"</p>
</td>
</tr>
<tr id="row13824515"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p46043902"><a name="p46043902"></a><a name="p46043902"></a>version</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p38568586"><a name="p38568586"></a><a name="p38568586"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p37047758"><a name="p37047758"></a><a name="p37047758"></a>version specifies the version in the form of "version". This is to save the clients the trouble of splitting the GroupVersion.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIGroupList",
    "apiVersion": "v1",
    "groups": [
        {
            "name": "apiregistration.k8s.io",
            "versions": [
                {
                    "groupVersion": "apiregistration.k8s.io/v1beta1",
                    "version": "v1beta1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "apiregistration.k8s.io/v1beta1",
                "version": "v1beta1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "extensions",
            "versions": [
                {
                    "groupVersion": "extensions/v1beta1",
                    "version": "v1beta1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "extensions/v1beta1",
                "version": "v1beta1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "apps",
            "versions": [
                {
                    "groupVersion": "apps/v1beta1",
                    "version": "v1beta1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "apps/v1beta1",
                "version": "v1beta1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "authentication.k8s.io",
            "versions": [
                {
                    "groupVersion": "authentication.k8s.io/v1",
                    "version": "v1"
                },
                {
                    "groupVersion": "authentication.k8s.io/v1beta1",
                    "version": "v1beta1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "authentication.k8s.io/v1",
                "version": "v1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "authorization.k8s.io",
            "versions": [
                {
                    "groupVersion": "authorization.k8s.io/v1",
                    "version": "v1"
                },
                {
                    "groupVersion": "authorization.k8s.io/v1beta1",
                    "version": "v1beta1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "authorization.k8s.io/v1",
                "version": "v1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "autoscaling",
            "versions": [
                {
                    "groupVersion": "autoscaling/v1",
                    "version": "v1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "autoscaling/v1",
                "version": "v1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "batch",
            "versions": [
                {
                    "groupVersion": "batch/v1",
                    "version": "v1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "batch/v1",
                "version": "v1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "certificates.k8s.io",
            "versions": [
                {
                    "groupVersion": "certificates.k8s.io/v1beta1",
                    "version": "v1beta1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "certificates.k8s.io/v1beta1",
                "version": "v1beta1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "networking.k8s.io",
            "versions": [
                {
                    "groupVersion": "networking.k8s.io/v1",
                    "version": "v1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "networking.k8s.io/v1",
                "version": "v1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "policy",
            "versions": [
                {
                    "groupVersion": "policy/v1beta1",
                    "version": "v1beta1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "policy/v1beta1",
                "version": "v1beta1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "rbac.authorization.k8s.io",
            "versions": [
                {
                    "groupVersion": "rbac.authorization.k8s.io/v1beta1",
                    "version": "v1beta1"
                },
                {
                    "groupVersion": "rbac.authorization.k8s.io/v1alpha1",
                    "version": "v1alpha1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "rbac.authorization.k8s.io/v1beta1",
                "version": "v1beta1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "settings.k8s.io",
            "versions": [
                {
                    "groupVersion": "settings.k8s.io/v1alpha1",
                    "version": "v1alpha1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "settings.k8s.io/v1alpha1",
                "version": "v1alpha1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "storage.k8s.io",
            "versions": [
                {
                    "groupVersion": "storage.k8s.io/v1",
                    "version": "v1"
                },
                {
                    "groupVersion": "storage.k8s.io/v1beta1",
                    "version": "v1beta1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "storage.k8s.io/v1",
                "version": "v1"
            },
            "serverAddressByClientCIDRs": null
        },
        {
            "name": "apiextensions.k8s.io",
            "versions": [
                {
                    "groupVersion": "apiextensions.k8s.io/v1beta1",
                    "version": "v1beta1"
                }
            ],
            "preferredVersion": {
                "groupVersion": "apiextensions.k8s.io/v1beta1",
                "version": "v1beta1"
            },
            "serverAddressByClientCIDRs": null
        }
    ]
}
```

## 状态码<a name="section10218043"></a>

[表5](#d0e46117)描述API的状态码。

**表 5**  状态码

<a name="d0e46117"></a>
<table><thead align="left"><tr id="row24033136"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p527006"><a name="p527006"></a><a name="p527006"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p42687565"><a name="p42687565"></a><a name="p42687565"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row35140773"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p27830349"><a name="p27830349"></a><a name="p27830349"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p39665773"><a name="p39665773"></a><a name="p39665773"></a>This operation succeeds, and a group of APIGroups resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

