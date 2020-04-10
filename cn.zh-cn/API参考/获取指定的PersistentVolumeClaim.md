# 获取指定的PersistentVolumeClaim<a name="cce_02_0069"></a>

## 功能介绍<a name="s0766f38d8a9142d895e93cfb7d977c17"></a>

该API用于获取指定Namespace下的PersistentVolumeClaim对象。

## URI<a name="s6c83b7ac5f8848cdad6aa0f72beb7b0c"></a>

GET /api/v1/namespaces/\{namespace\}/persistentvolumeclaims/\{name\}

[表1](#t905c776ecca443388ba20364de9fe4b1)  描述该API的参数。

**表 1**  参数描述

<a name="t905c776ecca443388ba20364de9fe4b1"></a>
<table><thead align="left"><tr id="re4448348c64e428fb5c1d1cddd8fa39d"><th class="cellrowborder" valign="top" width="21.5%" id="mcps1.2.4.1.1"><p id="a6b56275af4254aa8afbfddfdb98e7a4c"><a name="a6b56275af4254aa8afbfddfdb98e7a4c"></a><a name="a6b56275af4254aa8afbfddfdb98e7a4c"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.98%" id="mcps1.2.4.1.2"><p id="p20093560201657"><a name="p20093560201657"></a><a name="p20093560201657"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="61.519999999999996%" id="mcps1.2.4.1.3"><p id="p16965695201657"><a name="p16965695201657"></a><a name="p16965695201657"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rf8bfcf8618fa4d23a2d2b2e9701e793d"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.2.4.1.1 "><p id="ae865e36f760b43988f36a20ac86d6c15"><a name="ae865e36f760b43988f36a20ac86d6c15"></a><a name="ae865e36f760b43988f36a20ac86d6c15"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="a30e55bc5c7ec47178766a33d9fa345c6"><a name="a30e55bc5c7ec47178766a33d9fa345c6"></a><a name="a30e55bc5c7ec47178766a33d9fa345c6"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61.519999999999996%" headers="mcps1.2.4.1.3 "><p id="a2419edd712cc4ee4b14c50ea5d714a32"><a name="a2419edd712cc4ee4b14c50ea5d714a32"></a><a name="a2419edd712cc4ee4b14c50ea5d714a32"></a>Name of the PersistentVolumeClaim.</p>
</td>
</tr>
<tr id="r5c25aa62af5a438f9eca6cce9fa4cb20"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.2.4.1.1 "><p id="ac42f31a201764e3da1fa67f36ff5b76c"><a name="ac42f31a201764e3da1fa67f36ff5b76c"></a><a name="ac42f31a201764e3da1fa67f36ff5b76c"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="a0c4f368c1c7e4ba8ae902656ba14331a"><a name="a0c4f368c1c7e4ba8ae902656ba14331a"></a><a name="a0c4f368c1c7e4ba8ae902656ba14331a"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="61.519999999999996%" headers="mcps1.2.4.1.3 "><p id="a8c311c3877b94ff2bf98e470ddec0765"><a name="a8c311c3877b94ff2bf98e470ddec0765"></a><a name="a8c311c3877b94ff2bf98e470ddec0765"></a>Object name and auth scope, such as for teams and projects.</p>
</td>
</tr>
<tr id="r688017883dba445cac8b473c7e48d335"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.2.4.1.1 "><p id="af59efb8fedcd4850bb55e382f01d2076"><a name="af59efb8fedcd4850bb55e382f01d2076"></a><a name="af59efb8fedcd4850bb55e382f01d2076"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="abfc66d6f8cd84571845c8d2be8aa5e3d"><a name="abfc66d6f8cd84571845c8d2be8aa5e3d"></a><a name="abfc66d6f8cd84571845c8d2be8aa5e3d"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.519999999999996%" headers="mcps1.2.4.1.3 "><p id="a2d2478fd5ac14c0da905226a4da988ea"><a name="a2d2478fd5ac14c0da905226a4da988ea"></a><a name="a2d2478fd5ac14c0da905226a4da988ea"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
<tr id="rf253f01f49ba458f93f6fecf95ac33a5"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.2.4.1.1 "><p id="a67e7df0587bc4b31a91a8ab83426dd31"><a name="a67e7df0587bc4b31a91a8ab83426dd31"></a><a name="a67e7df0587bc4b31a91a8ab83426dd31"></a>exact</p>
</td>
<td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="a0e21efd5a6ea49ea807b87a72f5e325c"><a name="a0e21efd5a6ea49ea807b87a72f5e325c"></a><a name="a0e21efd5a6ea49ea807b87a72f5e325c"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.519999999999996%" headers="mcps1.2.4.1.3 "><p id="a84b651f574804bf5b0dcb09fb4f1b17d"><a name="a84b651f574804bf5b0dcb09fb4f1b17d"></a><a name="a84b651f574804bf5b0dcb09fb4f1b17d"></a>Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'.</p>
</td>
</tr>
<tr id="rb4021dd42289434f8263c1328e171814"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.2.4.1.1 "><p id="af2440c7693cb4fc19c8e702de5b4f12e"><a name="af2440c7693cb4fc19c8e702de5b4f12e"></a><a name="af2440c7693cb4fc19c8e702de5b4f12e"></a>export</p>
</td>
<td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="a1646fa4fc6ea42979982ad943bf25902"><a name="a1646fa4fc6ea42979982ad943bf25902"></a><a name="a1646fa4fc6ea42979982ad943bf25902"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="61.519999999999996%" headers="mcps1.2.4.1.3 "><p id="ad0fb8de0f1bc4250a089d1456477089d"><a name="ad0fb8de0f1bc4250a089d1456477089d"></a><a name="ad0fb8de0f1bc4250a089d1456477089d"></a>Should this value be exported. Export strips fields that a user can not specify.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sbbfee804cd1441feb02c5b1256f37066"></a>

N/A

## 响应消息<a name="s2c230500e1d545709e0e50812a3d2236"></a>

**响应参数：**

**表 2**  响应参数

<a name="t7aa9de1153e9466cbfcaa9af17a24772"></a>
<table><thead align="left"><tr id="rfd59f4d1ef4645dcbc00db38b6c54ec5"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="ac004438109724f0ea79da803b3ac44a9"><a name="ac004438109724f0ea79da803b3ac44a9"></a><a name="ac004438109724f0ea79da803b3ac44a9"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.14%" id="mcps1.2.4.1.2"><p id="p66405260201657"><a name="p66405260201657"></a><a name="p66405260201657"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.4.1.3"><p id="p10116961201657"><a name="p10116961201657"></a><a name="p10116961201657"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r7ef8f6df13ac4022bf5a19f79ef4708f"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a1127eebfcb6b450781e743fe2cf7409c"><a name="a1127eebfcb6b450781e743fe2cf7409c"></a><a name="a1127eebfcb6b450781e743fe2cf7409c"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="a70e7be48b772450ca20866a4c18e9290"><a name="a70e7be48b772450ca20866a4c18e9290"></a><a name="a70e7be48b772450ca20866a4c18e9290"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="aaff7634098ab4fd5b5bdb0a796205419"><a name="aaff7634098ab4fd5b5bdb0a796205419"></a><a name="aaff7634098ab4fd5b5bdb0a796205419"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="r1a2e9a5b65bd4a7196afc80f456613b3"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="aa36073bd952941c881c80b6c08be456d"><a name="aa36073bd952941c881c80b6c08be456d"></a><a name="aa36073bd952941c881c80b6c08be456d"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="adaf3654a19a04ead85b5e535fc2ac287"><a name="adaf3654a19a04ead85b5e535fc2ac287"></a><a name="adaf3654a19a04ead85b5e535fc2ac287"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a32d3a61b90e84a859d44c4ee0413370f"><a name="a32d3a61b90e84a859d44c4ee0413370f"></a><a name="a32d3a61b90e84a859d44c4ee0413370f"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated.</p>
</td>
</tr>
<tr id="rc9a4369ddb0a4e7585b3771ffdd62fad"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="abead9b50c38d480582f847f6c0cb2283"><a name="abead9b50c38d480582f847f6c0cb2283"></a><a name="abead9b50c38d480582f847f6c0cb2283"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="adf64868001c24986879cc87a8a78ef49"><a name="adf64868001c24986879cc87a8a78ef49"></a><a name="adf64868001c24986879cc87a8a78ef49"></a><a href="请求数据结构.md#zh-cn_topic_0079614925_table47756489">metadata</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a3b00398fdf784e649341b6eced5f23bd"><a name="a3b00398fdf784e649341b6eced5f23bd"></a><a name="a3b00398fdf784e649341b6eced5f23bd"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="ra9f74d235b124f3fac54e4d37a087ccc"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="ad9286ff8d41c4f36be6d6027b7b2fcf0"><a name="ad9286ff8d41c4f36be6d6027b7b2fcf0"></a><a name="ad9286ff8d41c4f36be6d6027b7b2fcf0"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="ac8089743481d43f29e661eb361515a35"><a name="ac8089743481d43f29e661eb361515a35"></a><a name="ac8089743481d43f29e661eb361515a35"></a><a href="#t4164eafb5c9d4390ad675439f474a85e">spec</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a4720c0b59b204bbd8a6df046152927a3"><a name="a4720c0b59b204bbd8a6df046152927a3"></a><a name="a4720c0b59b204bbd8a6df046152927a3"></a>Spec defines the desired characteristics of a volume requested by a pod author.</p>
</td>
</tr>
<tr id="r4c629d1aa6b2423eb36f5f1ac054d93b"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="a21272588efee40558687df6d954e228c"><a name="a21272588efee40558687df6d954e228c"></a><a name="a21272588efee40558687df6d954e228c"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="30.14%" headers="mcps1.2.4.1.2 "><p id="a9f722c132fc84336a6f7270ee364ec2c"><a name="a9f722c132fc84336a6f7270ee364ec2c"></a><a name="a9f722c132fc84336a6f7270ee364ec2c"></a><a href="#t1ca834ff62b74f3998c623e794646bf2">status</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.4.1.3 "><p id="a3f2dfa6a895348dfb0228b1ef4343a9a"><a name="a3f2dfa6a895348dfb0228b1ef4343a9a"></a><a name="a3f2dfa6a895348dfb0228b1ef4343a9a"></a>Status represents the current information/status of a persistent volume claim. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  status字段数据结构说明

<a name="t1ca834ff62b74f3998c623e794646bf2"></a>
<table><thead align="left"><tr id="r98c546e04cf543b5a561af4aabfcd61f"><th class="cellrowborder" valign="top" width="24.872487248724873%" id="mcps1.2.4.1.1"><p id="a242e237592044195919ed0df4e79a4f7"><a name="a242e237592044195919ed0df4e79a4f7"></a><a name="a242e237592044195919ed0df4e79a4f7"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.51305130513051%" id="mcps1.2.4.1.2"><p id="p18886373201657"><a name="p18886373201657"></a><a name="p18886373201657"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.61446144614462%" id="mcps1.2.4.1.3"><p id="p53401283201657"><a name="p53401283201657"></a><a name="p53401283201657"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r2f59ae4ae68046aea6ec46df95dd9c4e"><td class="cellrowborder" valign="top" width="24.872487248724873%" headers="mcps1.2.4.1.1 "><p id="aa0a7abc55eef456ab71e34dc390e859d"><a name="aa0a7abc55eef456ab71e34dc390e859d"></a><a name="aa0a7abc55eef456ab71e34dc390e859d"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="30.51305130513051%" headers="mcps1.2.4.1.2 "><p id="a460e0a5fa5874728b9fd427f0e23fc74"><a name="a460e0a5fa5874728b9fd427f0e23fc74"></a><a name="a460e0a5fa5874728b9fd427f0e23fc74"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.61446144614462%" headers="mcps1.2.4.1.3 "><p id="a25062b3b263144f8b8d8a965cb00b8cd"><a name="a25062b3b263144f8b8d8a965cb00b8cd"></a><a name="a25062b3b263144f8b8d8a965cb00b8cd"></a>AccessModes contains the actual access modes the volume backing the PVC has.</p>
</td>
</tr>
<tr id="radd123ccd2f841f4abc92f243ba42b99"><td class="cellrowborder" valign="top" width="24.872487248724873%" headers="mcps1.2.4.1.1 "><p id="a6b5a20446350477db9e0668ee2abc3e0"><a name="a6b5a20446350477db9e0668ee2abc3e0"></a><a name="a6b5a20446350477db9e0668ee2abc3e0"></a>capacity</p>
</td>
<td class="cellrowborder" valign="top" width="30.51305130513051%" headers="mcps1.2.4.1.2 "><p id="a22a64d6780e143bfa83c88330b8d4e2a"><a name="a22a64d6780e143bfa83c88330b8d4e2a"></a><a name="a22a64d6780e143bfa83c88330b8d4e2a"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.61446144614462%" headers="mcps1.2.4.1.3 "><p id="ad09b5c7bc0ad44fc9c642b277c05d1e9"><a name="ad09b5c7bc0ad44fc9c642b277c05d1e9"></a><a name="ad09b5c7bc0ad44fc9c642b277c05d1e9"></a>Represents the actual resources of the underlying volume.</p>
</td>
</tr>
<tr id="rcb8a76ae1a08456789d2379f4fac6cb0"><td class="cellrowborder" valign="top" width="24.872487248724873%" headers="mcps1.2.4.1.1 "><p id="a9bb3e6082dc4483b8f25b39c79698603"><a name="a9bb3e6082dc4483b8f25b39c79698603"></a><a name="a9bb3e6082dc4483b8f25b39c79698603"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="30.51305130513051%" headers="mcps1.2.4.1.2 "><p id="af7a260a6e40b4033b58845ce255b287f"><a name="af7a260a6e40b4033b58845ce255b287f"></a><a name="af7a260a6e40b4033b58845ce255b287f"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.61446144614462%" headers="mcps1.2.4.1.3 "><p id="a936a111aba3642ca8a18ac3e16a42de9"><a name="a936a111aba3642ca8a18ac3e16a42de9"></a><a name="a936a111aba3642ca8a18ac3e16a42de9"></a>Phase represents the current phase of PersistentVolumeClaim.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  spec字段数据结构说明

<a name="t4164eafb5c9d4390ad675439f474a85e"></a>
<table><thead align="left"><tr id="r05376820b7ad45bf87dafc988b9c4cf8"><th class="cellrowborder" valign="top" width="24.69%" id="mcps1.2.4.1.1"><p id="a7bcbf99a8dce4bab9aa925d83daf6882"><a name="a7bcbf99a8dce4bab9aa925d83daf6882"></a><a name="a7bcbf99a8dce4bab9aa925d83daf6882"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="30.7%" id="mcps1.2.4.1.2"><p id="p62900204201657"><a name="p62900204201657"></a><a name="p62900204201657"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.61%" id="mcps1.2.4.1.3"><p id="p61751746201657"><a name="p61751746201657"></a><a name="p61751746201657"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r05c545d43bf041cca5f04441bda9fd6a"><td class="cellrowborder" valign="top" width="24.69%" headers="mcps1.2.4.1.1 "><p id="a80c0520342cf485c94d7f509bf5b1c9b"><a name="a80c0520342cf485c94d7f509bf5b1c9b"></a><a name="a80c0520342cf485c94d7f509bf5b1c9b"></a>volumeName</p>
</td>
<td class="cellrowborder" valign="top" width="30.7%" headers="mcps1.2.4.1.2 "><p id="aee996aab50d14cd784b88e8783a41062"><a name="aee996aab50d14cd784b88e8783a41062"></a><a name="aee996aab50d14cd784b88e8783a41062"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.61%" headers="mcps1.2.4.1.3 "><p id="af0f41425ef0c444a863c2087a50be67d"><a name="af0f41425ef0c444a863c2087a50be67d"></a><a name="af0f41425ef0c444a863c2087a50be67d"></a>VolumeName is the binding reference to the PersistentVolume backing this claim.</p>
</td>
</tr>
<tr id="rb0944447910642e0a84c9bde36fdc702"><td class="cellrowborder" valign="top" width="24.69%" headers="mcps1.2.4.1.1 "><p id="a527d10ee2d3e4df28aaa628a13cfad85"><a name="a527d10ee2d3e4df28aaa628a13cfad85"></a><a name="a527d10ee2d3e4df28aaa628a13cfad85"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="30.7%" headers="mcps1.2.4.1.2 "><p id="a17e1b834330845478dc85b2e47d598fe"><a name="a17e1b834330845478dc85b2e47d598fe"></a><a name="a17e1b834330845478dc85b2e47d598fe"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.61%" headers="mcps1.2.4.1.3 "><p id="a993289c826674b1c8ed8da69af22ab5b"><a name="a993289c826674b1c8ed8da69af22ab5b"></a><a name="a993289c826674b1c8ed8da69af22ab5b"></a>AccessModes contains the desired access modes the volume should have.</p>
</td>
</tr>
<tr id="r162ed9cdb1a44d7e8f3f75dedac5e011"><td class="cellrowborder" valign="top" width="24.69%" headers="mcps1.2.4.1.1 "><p id="a2e6c2b773c464992a4b4076636585973"><a name="a2e6c2b773c464992a4b4076636585973"></a><a name="a2e6c2b773c464992a4b4076636585973"></a>storageClassName</p>
</td>
<td class="cellrowborder" valign="top" width="30.7%" headers="mcps1.2.4.1.2 "><p id="a4b39a917d88245a789457e06bc683b4e"><a name="a4b39a917d88245a789457e06bc683b4e"></a><a name="a4b39a917d88245a789457e06bc683b4e"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.61%" headers="mcps1.2.4.1.3 "><p id="af1940909a37c4df98a402dfc1a531649"><a name="af1940909a37c4df98a402dfc1a531649"></a><a name="af1940909a37c4df98a402dfc1a531649"></a>Name of the StorageClass required by the claim.</p>
</td>
</tr>
<tr id="rd515c3debae84303875010efa59cc56c"><td class="cellrowborder" valign="top" width="24.69%" headers="mcps1.2.4.1.1 "><p id="a0e2ec7da8cdc4ddeb9bcb96d22c32f9d"><a name="a0e2ec7da8cdc4ddeb9bcb96d22c32f9d"></a><a name="a0e2ec7da8cdc4ddeb9bcb96d22c32f9d"></a>resources</p>
</td>
<td class="cellrowborder" valign="top" width="30.7%" headers="mcps1.2.4.1.2 "><p id="ae293d86539c34ff5850ea69be84b1e0b"><a name="ae293d86539c34ff5850ea69be84b1e0b"></a><a name="ae293d86539c34ff5850ea69be84b1e0b"></a><a href="#t16d10e9c67874eceb0cdea4276fbca5b">resources</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.61%" headers="mcps1.2.4.1.3 "><p id="ab31494d746694ff78a261f5899b45e41"><a name="ab31494d746694ff78a261f5899b45e41"></a><a name="ab31494d746694ff78a261f5899b45e41"></a>Resources represents the minimum resources the volume should have.</p>
</td>
</tr>
<tr id="re90dd6dcb5954f12a9c14df9f118d4e2"><td class="cellrowborder" valign="top" width="24.69%" headers="mcps1.2.4.1.1 "><p id="adeeaf8036a1d4709b074e3f7fe962490"><a name="adeeaf8036a1d4709b074e3f7fe962490"></a><a name="adeeaf8036a1d4709b074e3f7fe962490"></a>selector</p>
</td>
<td class="cellrowborder" valign="top" width="30.7%" headers="mcps1.2.4.1.2 "><p id="a9d6209db7163457498d96e34a7edee96"><a name="a9d6209db7163457498d96e34a7edee96"></a><a name="a9d6209db7163457498d96e34a7edee96"></a><a href="#td9cbaa76e2184972b05c85208ac2d425">selector</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.61%" headers="mcps1.2.4.1.3 "><p id="ad1dcc162e3e648d8adb50e8a7d3c3675"><a name="ad1dcc162e3e648d8adb50e8a7d3c3675"></a><a name="ad1dcc162e3e648d8adb50e8a7d3c3675"></a>A label query over volumes to consider for binding.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  resources字段数据结构说明

<a name="t16d10e9c67874eceb0cdea4276fbca5b"></a>
<table><thead align="left"><tr id="r375e8c94b3534239b5420fcde7a2202b"><th class="cellrowborder" valign="top" width="24.5%" id="mcps1.2.4.1.1"><p id="aaa378f1ef347456b8e805378805a624e"><a name="aaa378f1ef347456b8e805378805a624e"></a><a name="aaa378f1ef347456b8e805378805a624e"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="31.080000000000002%" id="mcps1.2.4.1.2"><p id="p63661054201657"><a name="p63661054201657"></a><a name="p63661054201657"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.42%" id="mcps1.2.4.1.3"><p id="p56271759201657"><a name="p56271759201657"></a><a name="p56271759201657"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r6928c59e30234f689b6231be45473a40"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.4.1.1 "><p id="a5868f30c25f24471af900d87ba12457a"><a name="a5868f30c25f24471af900d87ba12457a"></a><a name="a5868f30c25f24471af900d87ba12457a"></a>limits</p>
</td>
<td class="cellrowborder" valign="top" width="31.080000000000002%" headers="mcps1.2.4.1.2 "><p id="a3b7a410b3c3b45318b6c2a8209e59480"><a name="a3b7a410b3c3b45318b6c2a8209e59480"></a><a name="a3b7a410b3c3b45318b6c2a8209e59480"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.42%" headers="mcps1.2.4.1.3 "><p id="aaad98d488e6e4343b73f92c64694e1ce"><a name="aaad98d488e6e4343b73f92c64694e1ce"></a><a name="aaad98d488e6e4343b73f92c64694e1ce"></a>Limits describes the maximum amount of compute resources allowed.</p>
<div class="note" id="n25be9a768ae14f75b308034d81680de6"><a name="n25be9a768ae14f75b308034d81680de6"></a><a name="n25be9a768ae14f75b308034d81680de6"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="af8ea8976fc664d1aadf81dc7d8407c6f"><a name="af8ea8976fc664d1aadf81dc7d8407c6f"></a><a name="af8ea8976fc664d1aadf81dc7d8407c6f"></a>Parameter <strong id="zh-cn_topic_0079615064_b161542016202"><a name="zh-cn_topic_0079615064_b161542016202"></a><a name="zh-cn_topic_0079615064_b161542016202"></a>limits </strong>is invalid.</p>
</div></div>
</td>
</tr>
<tr id="re750f578d5cc4f539e8e33fcaa8f93dc"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.4.1.1 "><p id="aeb0e26da53334f58ac9656fefdc2fb11"><a name="aeb0e26da53334f58ac9656fefdc2fb11"></a><a name="aeb0e26da53334f58ac9656fefdc2fb11"></a>requests</p>
</td>
<td class="cellrowborder" valign="top" width="31.080000000000002%" headers="mcps1.2.4.1.2 "><p id="a4a07f66840634354af309828fae0a26e"><a name="a4a07f66840634354af309828fae0a26e"></a><a name="a4a07f66840634354af309828fae0a26e"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.42%" headers="mcps1.2.4.1.3 "><p id="abf59e0f363524a30bbdddc7e8f0a0ed4"><a name="abf59e0f363524a30bbdddc7e8f0a0ed4"></a><a name="abf59e0f363524a30bbdddc7e8f0a0ed4"></a>Requests describes the minimum amount of compute resources required. If Requests is omitted for a container, it defaults to Limits if that is explicitly specified, otherwise to an implementation-defined value.</p>
<div class="note" id="n43d1dec6613d4734a9cd27050a32dbb6"><a name="n43d1dec6613d4734a9cd27050a32dbb6"></a><a name="n43d1dec6613d4734a9cd27050a32dbb6"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a8c1ef33d38f04dfd9eb2107e464d3c5a"><a name="a8c1ef33d38f04dfd9eb2107e464d3c5a"></a><a name="a8c1ef33d38f04dfd9eb2107e464d3c5a"></a>Except parameter <strong id="a9d554fa6dbd2425d962d5828115202b2"><a name="a9d554fa6dbd2425d962d5828115202b2"></a><a name="a9d554fa6dbd2425d962d5828115202b2"></a>storage</strong>, the other parameters (such as&nbsp;<strong id="ad37f861af69f4c0c84e4aeb91b3e6299"><a name="ad37f861af69f4c0c84e4aeb91b3e6299"></a><a name="ad37f861af69f4c0c84e4aeb91b3e6299"></a>CPU</strong>&nbsp;and&nbsp;<strong id="zh-cn_topic_0079615064_b123938408205"><a name="zh-cn_topic_0079615064_b123938408205"></a><a name="zh-cn_topic_0079615064_b123938408205"></a>memory</strong>) are invalid.</p>
</div></div>
</td>
</tr>
</tbody>
</table>

**表 6**  selector字段数据结构说明

<a name="td9cbaa76e2184972b05c85208ac2d425"></a>
<table><thead align="left"><tr id="r116b8572509245a5a5dd322eb2116244"><th class="cellrowborder" valign="top" width="24.122412241224122%" id="mcps1.2.4.1.1"><p id="a22993eb1e99b4207b2a1ecc8bdbcee61"><a name="a22993eb1e99b4207b2a1ecc8bdbcee61"></a><a name="a22993eb1e99b4207b2a1ecc8bdbcee61"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="31.643164316431644%" id="mcps1.2.4.1.2"><p id="p23662110201657"><a name="p23662110201657"></a><a name="p23662110201657"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.23442344234424%" id="mcps1.2.4.1.3"><p id="p37582783201657"><a name="p37582783201657"></a><a name="p37582783201657"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="red5d01ac611d4526a6335cfa776ae9dd"><td class="cellrowborder" valign="top" width="24.122412241224122%" headers="mcps1.2.4.1.1 "><p id="ae4c86f3ae172409198db0287b18cd30e"><a name="ae4c86f3ae172409198db0287b18cd30e"></a><a name="ae4c86f3ae172409198db0287b18cd30e"></a>matchExpressions</p>
</td>
<td class="cellrowborder" valign="top" width="31.643164316431644%" headers="mcps1.2.4.1.2 "><p id="a2b6f3af101bf4400b704612830e1e189"><a name="a2b6f3af101bf4400b704612830e1e189"></a><a name="a2b6f3af101bf4400b704612830e1e189"></a><a href="#td834f96ec8e541cc8500b3a2835675b9">matchExpressions</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="44.23442344234424%" headers="mcps1.2.4.1.3 "><p id="ab33d6d16282e47d0828672db3d7f6e07"><a name="ab33d6d16282e47d0828672db3d7f6e07"></a><a name="ab33d6d16282e47d0828672db3d7f6e07"></a>MatchExpressions is a list of label selector requirements. The requirements are ANDed.</p>
</td>
</tr>
<tr id="r2f28075d2d9a432b9b6fc82d99a41635"><td class="cellrowborder" valign="top" width="24.122412241224122%" headers="mcps1.2.4.1.1 "><p id="aabeb686480f04325ab4b14f00d689ae5"><a name="aabeb686480f04325ab4b14f00d689ae5"></a><a name="aabeb686480f04325ab4b14f00d689ae5"></a>matchLabels</p>
</td>
<td class="cellrowborder" valign="top" width="31.643164316431644%" headers="mcps1.2.4.1.2 "><p id="a587dbdd3f04a49cf926f7c147e5f6968"><a name="a587dbdd3f04a49cf926f7c147e5f6968"></a><a name="a587dbdd3f04a49cf926f7c147e5f6968"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="44.23442344234424%" headers="mcps1.2.4.1.3 "><p id="a9b7da58573174c4bacd128c1132836ae"><a name="a9b7da58573174c4bacd128c1132836ae"></a><a name="a9b7da58573174c4bacd128c1132836ae"></a>MatchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  matchExpressions字段数据结构说明

<a name="td834f96ec8e541cc8500b3a2835675b9"></a>
<table><thead align="left"><tr id="r4b21474fc42e44aeb1e99185caf8cd14"><th class="cellrowborder" valign="top" width="23.93760623937606%" id="mcps1.2.4.1.1"><p id="ad215139c7cb440b095ad6bf245a3894f"><a name="ad215139c7cb440b095ad6bf245a3894f"></a><a name="ad215139c7cb440b095ad6bf245a3894f"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="31.82681731826817%" id="mcps1.2.4.1.2"><p id="p52724056201657"><a name="p52724056201657"></a><a name="p52724056201657"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.23557644235576%" id="mcps1.2.4.1.3"><p id="p42790157201657"><a name="p42790157201657"></a><a name="p42790157201657"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r21c36903f5794e5f8670f9aae17950bf"><td class="cellrowborder" valign="top" width="23.93760623937606%" headers="mcps1.2.4.1.1 "><p id="a1e80535a007a478197ce01c800797118"><a name="a1e80535a007a478197ce01c800797118"></a><a name="a1e80535a007a478197ce01c800797118"></a>key</p>
</td>
<td class="cellrowborder" valign="top" width="31.82681731826817%" headers="mcps1.2.4.1.2 "><p id="a183a1d93da044f5e82196f7e37a000b8"><a name="a183a1d93da044f5e82196f7e37a000b8"></a><a name="a183a1d93da044f5e82196f7e37a000b8"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.23557644235576%" headers="mcps1.2.4.1.3 "><p id="a17635daf84d947d08bf8e3f882c60d25"><a name="a17635daf84d947d08bf8e3f882c60d25"></a><a name="a17635daf84d947d08bf8e3f882c60d25"></a>Key is the label key that the selector applies to.</p>
</td>
</tr>
<tr id="rd06b831b54cd4a0186b1060e18a58389"><td class="cellrowborder" valign="top" width="23.93760623937606%" headers="mcps1.2.4.1.1 "><p id="adfc739c8b9294b08983bf0f0765f16b0"><a name="adfc739c8b9294b08983bf0f0765f16b0"></a><a name="adfc739c8b9294b08983bf0f0765f16b0"></a>operator</p>
</td>
<td class="cellrowborder" valign="top" width="31.82681731826817%" headers="mcps1.2.4.1.2 "><p id="a945aa51cefa64154804cd93aec36dd21"><a name="a945aa51cefa64154804cd93aec36dd21"></a><a name="a945aa51cefa64154804cd93aec36dd21"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.23557644235576%" headers="mcps1.2.4.1.3 "><p id="a388496eb5571447c8f62fdd8d916e714"><a name="a388496eb5571447c8f62fdd8d916e714"></a><a name="a388496eb5571447c8f62fdd8d916e714"></a>Operator represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists and DoesNotExist.</p>
</td>
</tr>
<tr id="r8668ebc5d382413c9c9d4c1aa9910a5e"><td class="cellrowborder" valign="top" width="23.93760623937606%" headers="mcps1.2.4.1.1 "><p id="a421dd971a54440b5836aeab0fae077a1"><a name="a421dd971a54440b5836aeab0fae077a1"></a><a name="a421dd971a54440b5836aeab0fae077a1"></a>values</p>
</td>
<td class="cellrowborder" valign="top" width="31.82681731826817%" headers="mcps1.2.4.1.2 "><p id="a2ca033f469734e08bf8045bcafdaee59"><a name="a2ca033f469734e08bf8045bcafdaee59"></a><a name="a2ca033f469734e08bf8045bcafdaee59"></a>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="44.23557644235576%" headers="mcps1.2.4.1.3 "><p id="ad4f842c31a4b4c23bb8e56334db64093"><a name="ad4f842c31a4b4c23bb8e56334db64093"></a><a name="ad4f842c31a4b4c23bb8e56334db64093"></a>Values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.</p>
</td>
</tr>
</tbody>
</table>

**响应示例：**

-   1.15及之后集群版本示例：

    ```
    {
        "kind":"PersistentVolumeClaim",
        "apiVersion":"v1",
        "metadata":{
            "name":"cce-evs-k6m131jj-i1px",
            "namespace":"default",
            "selfLink":"/api/v1/namespaces/default/persistentvolumeclaims/cce-evs-k6m131jj-i1px",
            "uid":"d34f6a93-9eba-4a33-9320-8fa4addd3753",
            "resourceVersion":"2286592",
            "creationTimestamp":"2020-02-14T10:27:43Z",
            "labels":{
                "failure-domain.beta.kubernetes.io/region":"cn-north-5",
                "failure-domain.beta.kubernetes.io/zone":"cn-north-5a"
            },
            "annotations":{
                "everest.io/disk-volume-type":"SATA",
                "pv.kubernetes.io/bind-completed":"yes",
                "pv.kubernetes.io/bound-by-controller":"yes",
                "volume.beta.kubernetes.io/storage-provisioner":"everest-csi-provisioner"
            },
            "finalizers":[
                "kubernetes.io/pvc-protection"
            ]
        },
        "spec":{
            "accessModes":[
                "ReadWriteOnce"
            ],
            "resources":{
                "requests":{
                    "storage":"10Gi"
                }
            },
            "volumeName":"pvc-d34f6a93-9eba-4a33-9320-8fa4addd3753",
            "storageClassName":"csi-disk",
            "volumeMode":"Filesystem"
        },
        "status":{
            "phase":"Bound",
            "accessModes":[
                "ReadWriteOnce"
            ],
            "capacity":{
                "storage":"10Gi"
            }
        }
    }
    ```

-   1.13及之前集群版本示例：

    ```
    {
        "kind": "PersistentVolumeClaim",
        "apiVersion": "v1",
        "metadata": {
            "name": "db-mysql",
            "namespace": "default",
            "selfLink": "/api/v1/namespaces/default/persistentvolumeclaims/db-mysql",
            "uid": "ac34af93-8cdd-11e8-8ee0-fa163e49263c",
            "resourceVersion": "4197709",
            "creationTimestamp": "2018-07-21T12:00:33Z",
            "labels": {
                "failure-domain.beta.kubernetes.io/region": "cn-north-1",
                "failure-domain.beta.kubernetes.io/zone": "cn-north-1a"
            },
            "annotations": {
                "pv.kubernetes.io/bind-completed": "yes",
                "pv.kubernetes.io/bound-by-controller": "yes",
                "volume.beta.kubernetes.io/storage-class": "sata",
                "volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
            }
        },
        "spec": {
            "accessModes": [
                "ReadWriteMany"
            ],
            "resources": {
                "requests": {
                    "storage": "10Gi"
                }
            },
            "volumeName": "pvc-ac34af93-8cdd-11e8-8ee0-fa163e49263c",
            "volumeNamespace": "default"
        },
        "status": {
            "phase": "Bound",
            "accessModes": [
                "ReadWriteMany"
            ],
            "capacity": {
                "storage": "10Gi"
            }
        }
    }
    ```


## 状态码<a name="s5e327306549c4e9883cffd48fd3dd116"></a>

[表8](#t50192f4902814904a2a6aaba297e2318)描述API的状态码。

**表 8**  状态码

<a name="t50192f4902814904a2a6aaba297e2318"></a>
<table><thead align="left"><tr id="rec68d1eaab554ce189b1adad4d5f7042"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p16246668201657"><a name="p16246668201657"></a><a name="p16246668201657"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p40911755201657"><a name="p40911755201657"></a><a name="p40911755201657"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rbcf728b6557a4c4badd2e6ce50865ee5"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="a14d7eb271a044aac83b27ebeb7378432"><a name="a14d7eb271a044aac83b27ebeb7378432"></a><a name="a14d7eb271a044aac83b27ebeb7378432"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="a89d3305a10044770b67608656d17fa5c"><a name="a89d3305a10044770b67608656d17fa5c"></a><a name="a89d3305a10044770b67608656d17fa5c"></a>This operation succeeds, and a PersistentVolumeClaim resource object is returned.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

