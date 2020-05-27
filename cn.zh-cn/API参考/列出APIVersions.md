# 列出APIVersions<a name="cce_02_0186"></a>

## 功能介绍<a name="section53754776"></a>

This API is used to list APIversions.

## URI<a name="section14030938"></a>

GET /api

## 请求消息<a name="section59169584"></a>

N/A.

## 响应消息<a name="section62764209"></a>

**响应参数：**

[表1](#d0e45702)  describes the response parameters.

**表 1**  参数解释

<a name="d0e45702"></a>
<table><thead align="left"><tr id="row37210166"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p61233436"><a name="p61233436"></a><a name="p61233436"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p60961283"><a name="p60961283"></a><a name="p60961283"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.4.1.3"><p id="p38916882"><a name="p38916882"></a><a name="p38916882"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row65259762"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p51549387"><a name="p51549387"></a><a name="p51549387"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p14750788"><a name="p14750788"></a><a name="p14750788"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p53963141"><a name="p53963141"></a><a name="p53963141"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="row15906224"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p13335793"><a name="p13335793"></a><a name="p13335793"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p6457487"><a name="p6457487"></a><a name="p6457487"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p53294449"><a name="p53294449"></a><a name="p53294449"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="row9888000"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p62730499"><a name="p62730499"></a><a name="p62730499"></a>serverAddressByClientCIDRs</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p48005696"><a name="p48005696"></a><a name="p48005696"></a><a href="#d0e45762">serverAddressByClientCIDRs</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p32434503"><a name="p32434503"></a><a name="p32434503"></a>a map of client CIDR to server address that is serving this group. This is to help clients reach servers in the most network-efficient way possible. Clients can use the appropriate server address as per the CIDR that they match. In case of multiple matches, clients should use the longest matching CIDR. The server returns only those CIDRs that it thinks that the client can match. For example: the master will return an internal IP CIDR only, if the client reaches the server using an internal IP. Server looks at X-Forwarded-For header or X-Real-Ip header or request.RemoteAddr (in that order) to get the client IP.</p>
</td>
</tr>
<tr id="row23475074"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p22432856"><a name="p22432856"></a><a name="p22432856"></a>versions</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p5122054"><a name="p5122054"></a><a name="p5122054"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.4.1.3 "><p id="p12233269"><a name="p12233269"></a><a name="p12233269"></a>versions are the api versions that are available.</p>
</td>
</tr>
</tbody>
</table>

**表 2**  serverAddressByClientCIDRs字段数据结构说明

<a name="d0e45762"></a>
<table><thead align="left"><tr id="row41026198"><th class="cellrowborder" valign="top" width="25.252525252525253%" id="mcps1.2.4.1.1"><p id="p34787743"><a name="p34787743"></a><a name="p34787743"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.303030303030305%" id="mcps1.2.4.1.2"><p id="p66343833"><a name="p66343833"></a><a name="p66343833"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.44444444444445%" id="mcps1.2.4.1.3"><p id="p5141420"><a name="p5141420"></a><a name="p5141420"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13801855"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p44208442"><a name="p44208442"></a><a name="p44208442"></a>clientCIDR</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p24114054"><a name="p24114054"></a><a name="p24114054"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p7081354"><a name="p7081354"></a><a name="p7081354"></a>The CIDR with which clients can match their IP to figure out the server address that they should use.</p>
</td>
</tr>
<tr id="row63732193"><td class="cellrowborder" valign="top" width="25.252525252525253%" headers="mcps1.2.4.1.1 "><p id="p62034029"><a name="p62034029"></a><a name="p62034029"></a>serverAddress</p>
</td>
<td class="cellrowborder" valign="top" width="30.303030303030305%" headers="mcps1.2.4.1.2 "><p id="p58700486"><a name="p58700486"></a><a name="p58700486"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.44444444444445%" headers="mcps1.2.4.1.3 "><p id="p57118931"><a name="p57118931"></a><a name="p57118931"></a>Address of this server, suitable for a client that matches the above CIDR. This can be a hostname, hostname:port, IP or IP:port.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

```
{
    "kind": "APIVersions",
    "versions": [
        "v1"
    ],
    "serverAddressByClientCIDRs": [
        {
            "clientCIDR": "0.0.0.0/0",
            "serverAddress": "192.168.1.175:6443"
        }
    ]
}
```

## 状态码<a name="section28006976"></a>

[表3](#d0e45813)描述API的状态码。

**表 3**  状态码

<a name="d0e45813"></a>
<table><thead align="left"><tr id="row54035152"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p14771200"><a name="p14771200"></a><a name="p14771200"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p55616532"><a name="p55616532"></a><a name="p55616532"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row8645237"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p29175562"><a name="p29175562"></a><a name="p29175562"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p14410299"><a name="p14410299"></a><a name="p14410299"></a>This operation succeeds, and a group of APIVersions resource objects is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

