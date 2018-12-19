# 创建PersistentVolume<a name="cce_02_0076"></a>

## 功能介绍<a name="sa31140c4c2504d038441a395ac747acc"></a>

该API用于创建一个PersistentVolume。

## URI<a name="sdd6f9681b1594dd49f729d50c2e79843"></a>

POST /api/v1/persistentvolumes

[表1](#tafb73a7dfdee477eb22297a81c5a0323)  描述该API的参数。

**表 1**  参数描述

<a name="tafb73a7dfdee477eb22297a81c5a0323"></a>
<table><thead align="left"><tr id="r4aa74a4e7fdb4e46a05d374c08fe62cb"><th class="cellrowborder" valign="top" width="22.06%" id="mcps1.2.4.1.1"><p id="a740253478e13420dad9c719bf6439fac"><a name="a740253478e13420dad9c719bf6439fac"></a><a name="a740253478e13420dad9c719bf6439fac"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.74%" id="mcps1.2.4.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="57.199999999999996%" id="mcps1.2.4.1.3"><p id="a5c2a9a92c6ea4375bf71cf4eb93f44d6"><a name="a5c2a9a92c6ea4375bf71cf4eb93f44d6"></a><a name="a5c2a9a92c6ea4375bf71cf4eb93f44d6"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rc26b35eafb66455ca9adff25affaa95d"><td class="cellrowborder" valign="top" width="22.06%" headers="mcps1.2.4.1.1 "><p id="aa20582cb4b5e4f98a0ef0d4afff49073"><a name="aa20582cb4b5e4f98a0ef0d4afff49073"></a><a name="aa20582cb4b5e4f98a0ef0d4afff49073"></a>pretty</p>
</td>
<td class="cellrowborder" valign="top" width="20.74%" headers="mcps1.2.4.1.2 "><p id="aa98923902bf34595890a2bbcda8c94af"><a name="aa98923902bf34595890a2bbcda8c94af"></a><a name="aa98923902bf34595890a2bbcda8c94af"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="57.199999999999996%" headers="mcps1.2.4.1.3 "><p id="a0b4e13224daf4066be13ce826ed3994d"><a name="a0b4e13224daf4066be13ce826ed3994d"></a><a name="a0b4e13224daf4066be13ce826ed3994d"></a>If 'true', then the output is pretty printed.</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="sa0f3d331d3db4ecfb93a5e6ac6ba8614"></a>

**请求参数：**

请求参数如[表2](#tfdb73431f39846d4a56ec4eb558e1617)所示。

**表 2**  请求参数

<a name="tfdb73431f39846d4a56ec4eb558e1617"></a>
<table><thead align="left"><tr id="r83d91421306342cb9c99219a8513588f"><th class="cellrowborder" valign="top" width="21.48%" id="mcps1.2.5.1.1"><p id="ae656fc68d4c647108a0d683bf8d51906"><a name="ae656fc68d4c647108a0d683bf8d51906"></a><a name="ae656fc68d4c647108a0d683bf8d51906"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.73%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.05%" id="mcps1.2.5.1.3"><p>类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.74%" id="mcps1.2.5.1.4"><p id="a02ec96a8fd6a472b99e398797499857f"><a name="a02ec96a8fd6a472b99e398797499857f"></a><a name="a02ec96a8fd6a472b99e398797499857f"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r08200704774e4d05aae8c69fe6cc2fef"><td class="cellrowborder" valign="top" width="21.48%" headers="mcps1.2.5.1.1 "><p id="aea1fe20af0a94c248d3916831bd0c939"><a name="aea1fe20af0a94c248d3916831bd0c939"></a><a name="aea1fe20af0a94c248d3916831bd0c939"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.73%" headers="mcps1.2.5.1.2 "><p id="aca44d0fb51e94e56abf09387405aae93"><a name="aca44d0fb51e94e56abf09387405aae93"></a><a name="aca44d0fb51e94e56abf09387405aae93"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.05%" headers="mcps1.2.5.1.3 "><p id="a4faa33955bdf4ded893bf57f3c82881e"><a name="a4faa33955bdf4ded893bf57f3c82881e"></a><a name="a4faa33955bdf4ded893bf57f3c82881e"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.74%" headers="mcps1.2.5.1.4 "><p id="a918b94b3be71446ca1bbed64af2ba21a"><a name="a918b94b3be71446ca1bbed64af2ba21a"></a><a name="a918b94b3be71446ca1bbed64af2ba21a"></a>APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values.</p>
</td>
</tr>
<tr id="r2be9fda9ffe04ac19b9473b274e73a0d"><td class="cellrowborder" valign="top" width="21.48%" headers="mcps1.2.5.1.1 "><p id="a706e6ecbdf7a4148b8fd39e99c292591"><a name="a706e6ecbdf7a4148b8fd39e99c292591"></a><a name="a706e6ecbdf7a4148b8fd39e99c292591"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="16.73%" headers="mcps1.2.5.1.2 "><p id="a63bcd371c09448d18a3bfe048242c22d"><a name="a63bcd371c09448d18a3bfe048242c22d"></a><a name="a63bcd371c09448d18a3bfe048242c22d"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.05%" headers="mcps1.2.5.1.3 "><p id="aa18e5fd8437142e7955bce09f17a08df"><a name="aa18e5fd8437142e7955bce09f17a08df"></a><a name="aa18e5fd8437142e7955bce09f17a08df"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.74%" headers="mcps1.2.5.1.4 "><p id="a2b86022472c64cf3b5acb323bb61787b"><a name="a2b86022472c64cf3b5acb323bb61787b"></a><a name="a2b86022472c64cf3b5acb323bb61787b"></a>Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase.</p>
</td>
</tr>
<tr id="rba776786c8054205b8da77ecc281abaa"><td class="cellrowborder" valign="top" width="21.48%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0079614924_p620733172933"><a name="zh-cn_topic_0079614924_p620733172933"></a><a name="zh-cn_topic_0079614924_p620733172933"></a>metadata</p>
</td>
<td class="cellrowborder" valign="top" width="16.73%" headers="mcps1.2.5.1.2 "><p id="a0faf74610c8440369b4e2414556be495"><a name="a0faf74610c8440369b4e2414556be495"></a><a name="a0faf74610c8440369b4e2414556be495"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.05%" headers="mcps1.2.5.1.3 "><p id="a5a8fe745525644258b1955e09e7fc12a"><a name="a5a8fe745525644258b1955e09e7fc12a"></a><a name="a5a8fe745525644258b1955e09e7fc12a"></a><a href="公共请求参数.md#zh-cn_topic_0079614925_table47756489">表11</a></p>
</td>
<td class="cellrowborder" valign="top" width="41.74%" headers="mcps1.2.5.1.4 "><p id="a9aabf1a007b9447bb565ff542c2095e1"><a name="a9aabf1a007b9447bb565ff542c2095e1"></a><a name="a9aabf1a007b9447bb565ff542c2095e1"></a>Standard object's metadata.</p>
</td>
</tr>
<tr id="r7e8105e003cb4deebacdc67b0f381d06"><td class="cellrowborder" valign="top" width="21.48%" headers="mcps1.2.5.1.1 "><p id="af1001bb599cf40378901fd25e121ea8c"><a name="af1001bb599cf40378901fd25e121ea8c"></a><a name="af1001bb599cf40378901fd25e121ea8c"></a>spec</p>
</td>
<td class="cellrowborder" valign="top" width="16.73%" headers="mcps1.2.5.1.2 "><p id="ad56870e48d7d4489b2917707026dacb6"><a name="ad56870e48d7d4489b2917707026dacb6"></a><a name="ad56870e48d7d4489b2917707026dacb6"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20.05%" headers="mcps1.2.5.1.3 "><p id="aaefeac87a2464d9497236b34fef04084"><a name="aaefeac87a2464d9497236b34fef04084"></a><a name="aaefeac87a2464d9497236b34fef04084"></a><a href="#tb127086a0961458f95fba61c3071d468">表3</a></p>
</td>
<td class="cellrowborder" valign="top" width="41.74%" headers="mcps1.2.5.1.4 "><p id="af33fa6c32187429fadb522ef6094a708"><a name="af33fa6c32187429fadb522ef6094a708"></a><a name="af33fa6c32187429fadb522ef6094a708"></a>Spec defines a specification of a persistent volume owned by the cluster. Provisioned by an administrator.</p>
</td>
</tr>
<tr id="r993bc8fb952c4b098507659526be1710"><td class="cellrowborder" valign="top" width="21.48%" headers="mcps1.2.5.1.1 "><p id="a74ee763a532d45c4a717af166c55bb01"><a name="a74ee763a532d45c4a717af166c55bb01"></a><a name="a74ee763a532d45c4a717af166c55bb01"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="16.73%" headers="mcps1.2.5.1.2 "><p id="afad06b19b664499d9ec7c50945f395b3"><a name="afad06b19b664499d9ec7c50945f395b3"></a><a name="afad06b19b664499d9ec7c50945f395b3"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20.05%" headers="mcps1.2.5.1.3 "><p id="ad81dfe97250c4ab28225761260d5b695"><a name="ad81dfe97250c4ab28225761260d5b695"></a><a name="ad81dfe97250c4ab28225761260d5b695"></a><a href="#tab4eab31a17149b4b5cd8d26c93b5a7e">表4</a></p>
</td>
<td class="cellrowborder" valign="top" width="41.74%" headers="mcps1.2.5.1.4 "><p id="ac0936b4e1e3847f790c3d03aaf1a7b6c"><a name="ac0936b4e1e3847f790c3d03aaf1a7b6c"></a><a name="ac0936b4e1e3847f790c3d03aaf1a7b6c"></a>Status represents the current information/status for the persistent volume. Populated by the system. Read-only.</p>
</td>
</tr>
</tbody>
</table>

**表 3**  spec字段数据结构说明

<a name="tb127086a0961458f95fba61c3071d468"></a>
<table><thead align="left"><tr id="r27367aa0d8e44ad9affc9674330b27c3"><th class="cellrowborder" valign="top" width="22%" id="mcps1.2.5.1.1"><p id="a4e206fbc29c34b908819fdfdc51f603c"><a name="a4e206fbc29c34b908819fdfdc51f603c"></a><a name="a4e206fbc29c34b908819fdfdc51f603c"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42%" id="mcps1.2.5.1.4"><p id="ad4426867f27744389753b92676b6e809"><a name="ad4426867f27744389753b92676b6e809"></a><a name="ad4426867f27744389753b92676b6e809"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r0403545026624f2c9935417fc2662be9"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="a50347bcb13914fc682646031503d95ad"><a name="a50347bcb13914fc682646031503d95ad"></a><a name="a50347bcb13914fc682646031503d95ad"></a>accessModes</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="a5524a8df17714afea2432fed211761eb"><a name="a5524a8df17714afea2432fed211761eb"></a><a name="a5524a8df17714afea2432fed211761eb"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="afbe16c2d348e43b4b82536299f41b835"><a name="afbe16c2d348e43b4b82536299f41b835"></a><a name="afbe16c2d348e43b4b82536299f41b835"></a>String Array</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="a8915073c5f994f15af5505f816234e5b"><a name="a8915073c5f994f15af5505f816234e5b"></a><a name="a8915073c5f994f15af5505f816234e5b"></a>Access mode.</p>
<p id="a03d00dd0c4444bbf9aac17163c9438fb"><a name="a03d00dd0c4444bbf9aac17163c9438fb"></a><a name="a03d00dd0c4444bbf9aac17163c9438fb"></a>Options:</p>
<p id="zh-cn_topic_0079614924_p176517815548"><a name="zh-cn_topic_0079614924_p176517815548"></a><a name="zh-cn_topic_0079614924_p176517815548"></a>ReadWriteOnce: can be read and written by a single node.</p>
<p id="a978d8fea82714215af18162f54354d3f"><a name="a978d8fea82714215af18162f54354d3f"></a><a name="a978d8fea82714215af18162f54354d3f"></a>ReadOnlyMany: can only be read by multiple nodes.</p>
<p id="zh-cn_topic_0079614924_p196521087545"><a name="zh-cn_topic_0079614924_p196521087545"></a><a name="zh-cn_topic_0079614924_p196521087545"></a>ReadWriteMany: can be read and written by multiple nodes.</p>
</td>
</tr>
<tr id="r8cd65ef2bab5408588333d2fed8f42b3"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="afb04146dacb24ebc934eb6c1c071ee72"><a name="afb04146dacb24ebc934eb6c1c071ee72"></a><a name="afb04146dacb24ebc934eb6c1c071ee72"></a>capacity</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="a0313a9f807354c7b9fd16bd5c0d2d2aa"><a name="a0313a9f807354c7b9fd16bd5c0d2d2aa"></a><a name="a0313a9f807354c7b9fd16bd5c0d2d2aa"></a>Yes</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a1b6b3f5fd05742a3a0632019f3effc9f"><a name="a1b6b3f5fd05742a3a0632019f3effc9f"></a><a name="a1b6b3f5fd05742a3a0632019f3effc9f"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="af3fdde5703fa48ffbe089443037827fc"><a name="af3fdde5703fa48ffbe089443037827fc"></a><a name="af3fdde5703fa48ffbe089443037827fc"></a>A description of the persistent volume's resources and capacity.</p>
</td>
</tr>
<tr id="r6c874aaed56f4a9080acc97e62169a0d"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="acc4b6006cbbb4a1fb4cae2dcb0aea4a1"><a name="acc4b6006cbbb4a1fb4cae2dcb0aea4a1"></a><a name="acc4b6006cbbb4a1fb4cae2dcb0aea4a1"></a>claimRef</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="ac0e00a03dd504f6fb22d7d47676f6548"><a name="ac0e00a03dd504f6fb22d7d47676f6548"></a><a name="ac0e00a03dd504f6fb22d7d47676f6548"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a487d3f45865848f7aaea4eeb1df20888"><a name="a487d3f45865848f7aaea4eeb1df20888"></a><a name="a487d3f45865848f7aaea4eeb1df20888"></a><a href="#t5fe2db24d4ee4588b001da6f826e3d3a">表5</a></p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="aa564a4d14fc74b73a60ce98227ad5db5"><a name="aa564a4d14fc74b73a60ce98227ad5db5"></a><a name="aa564a4d14fc74b73a60ce98227ad5db5"></a>ClaimRef is part of a bi-directional binding between PersistentVolume and PersistentVolumeClaim. Expected to be non-nil when bound. claim. VolumeName is the authoritative bind between PV and PVC.</p>
</td>
</tr>
<tr id="r83b704b2c08a446b8ffac782fb3e821e"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="a91aa438e2c92459f946ddd5c793cd6fa"><a name="a91aa438e2c92459f946ddd5c793cd6fa"></a><a name="a91aa438e2c92459f946ddd5c793cd6fa"></a>hostPath</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="a40a75035c80f4d5bbf9a60540d077979"><a name="a40a75035c80f4d5bbf9a60540d077979"></a><a name="a40a75035c80f4d5bbf9a60540d077979"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a044d674a435c46dbb307c1cc4719aa3a"><a name="a044d674a435c46dbb307c1cc4719aa3a"></a><a name="a044d674a435c46dbb307c1cc4719aa3a"></a><a href="#t49e3547d603e4c019abc62b357512bf6">表6</a></p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="adbadf9d4bfdf499aba91ea7fc5f19776"><a name="adbadf9d4bfdf499aba91ea7fc5f19776"></a><a name="adbadf9d4bfdf499aba91ea7fc5f19776"></a>HostPath represents a directory on the host. Provisioned by a developer or tester. This is useful for single-node development and testing only! On-host storage is not supported in any way and WILL NOT WORK in a multi-node cluster.</p>
</td>
</tr>
<tr id="re19b89eeee6b48e795ee1568b09f7c7a"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="ab8e207fc902845e1b2e759a6d8a55c17"><a name="ab8e207fc902845e1b2e759a6d8a55c17"></a><a name="ab8e207fc902845e1b2e759a6d8a55c17"></a>nfs</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="a168651e90a36441bbf867859edf6fbda"><a name="a168651e90a36441bbf867859edf6fbda"></a><a name="a168651e90a36441bbf867859edf6fbda"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a2346991b94c04146931e7cf591c46967"><a name="a2346991b94c04146931e7cf591c46967"></a><a name="a2346991b94c04146931e7cf591c46967"></a><a href="#t2f5e70bc193c4769a21652324f8fec4d">表7</a></p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="ac27b81771d184325a1207786c6900696"><a name="ac27b81771d184325a1207786c6900696"></a><a name="ac27b81771d184325a1207786c6900696"></a>NFS represents an NFS mount on the host. Provisioned by an admin.</p>
</td>
</tr>
<tr id="r5ca08c1e40774604a8aa2549ccbd58d5"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="a2da1b82ec106467caf065cf4cb8eb2fb"><a name="a2da1b82ec106467caf065cf4cb8eb2fb"></a><a name="a2da1b82ec106467caf065cf4cb8eb2fb"></a>persistentVolumeReclaimPolicy</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="aa02cc300c0a14ab99f20d9ba4ed07f5c"><a name="aa02cc300c0a14ab99f20d9ba4ed07f5c"></a><a name="aa02cc300c0a14ab99f20d9ba4ed07f5c"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="ae2d38eeba03f491b8cb7ebc5dc516ecf"><a name="ae2d38eeba03f491b8cb7ebc5dc516ecf"></a><a name="ae2d38eeba03f491b8cb7ebc5dc516ecf"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="aa49502c49fb745e7b6dcb8fe73fdda58"><a name="aa49502c49fb745e7b6dcb8fe73fdda58"></a><a name="aa49502c49fb745e7b6dcb8fe73fdda58"></a>What happens to a persistent volume when released from its claim. Valid options are Retain (default) and Recycle. Recycling must be supported by the volume plugin underlying this persistent volume.</p>
</td>
</tr>
<tr id="r2b242a00cf1a42a7906ea94711576193"><td class="cellrowborder" valign="top" width="22%" headers="mcps1.2.5.1.1 "><p id="af909c2ce83784cb997c466097b352fc0"><a name="af909c2ce83784cb997c466097b352fc0"></a><a name="af909c2ce83784cb997c466097b352fc0"></a>storageClassName</p>
</td>
<td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.2 "><p id="a3b9f154f21a4460892680151124947de"><a name="a3b9f154f21a4460892680151124947de"></a><a name="a3b9f154f21a4460892680151124947de"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614924_p287791992216"><a name="zh-cn_topic_0079614924_p287791992216"></a><a name="zh-cn_topic_0079614924_p287791992216"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614924_p188779198221"><a name="zh-cn_topic_0079614924_p188779198221"></a><a name="zh-cn_topic_0079614924_p188779198221"></a>Name of StorageClass to which this persistent volume belongs. Empty value means that this volume does not belong to any StorageClass.</p>
</td>
</tr>
</tbody>
</table>

**表 4**  status字段数据结构说明

<a name="tab4eab31a17149b4b5cd8d26c93b5a7e"></a>
<table><thead align="left"><tr id="r96f77f4a7bc345b4ab55432cc57a9558"><th class="cellrowborder" valign="top" width="21.61%" id="mcps1.2.5.1.1"><p id="a49f5bd9a5d9d4d7e822a713be20a5bc8"><a name="a49f5bd9a5d9d4d7e822a713be20a5bc8"></a><a name="a49f5bd9a5d9d4d7e822a713be20a5bc8"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.73%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.3"><p>类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.92%" id="mcps1.2.5.1.4"><p id="a0afa5eaa284e46b5acddd174528725cb"><a name="a0afa5eaa284e46b5acddd174528725cb"></a><a name="a0afa5eaa284e46b5acddd174528725cb"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rc7a7a85ee20c43e681f13dc49d357cd4"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="a8628d7b8f18c43619e9ef820db067cee"><a name="a8628d7b8f18c43619e9ef820db067cee"></a><a name="a8628d7b8f18c43619e9ef820db067cee"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="16.73%" headers="mcps1.2.5.1.2 "><p id="a73e6f049fe0c4201833f12ed270815e9"><a name="a73e6f049fe0c4201833f12ed270815e9"></a><a name="a73e6f049fe0c4201833f12ed270815e9"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="a46f1d8327bd54c5aaa321a213cbe1468"><a name="a46f1d8327bd54c5aaa321a213cbe1468"></a><a name="a46f1d8327bd54c5aaa321a213cbe1468"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.92%" headers="mcps1.2.5.1.4 "><p id="a435fa11052194958b3509effae4a0980"><a name="a435fa11052194958b3509effae4a0980"></a><a name="a435fa11052194958b3509effae4a0980"></a>A human-readable message indicating details about why the volume is in this state.</p>
</td>
</tr>
<tr id="ra4c0d54b5ad140619b9dd512b5e7a364"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="ae348237b3b1a4d588236d9dabb550cf1"><a name="ae348237b3b1a4d588236d9dabb550cf1"></a><a name="ae348237b3b1a4d588236d9dabb550cf1"></a>phase</p>
</td>
<td class="cellrowborder" valign="top" width="16.73%" headers="mcps1.2.5.1.2 "><p id="adae8fb3bcd2e414995df0eaebd8aa27b"><a name="adae8fb3bcd2e414995df0eaebd8aa27b"></a><a name="adae8fb3bcd2e414995df0eaebd8aa27b"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614924_p623832172933"><a name="zh-cn_topic_0079614924_p623832172933"></a><a name="zh-cn_topic_0079614924_p623832172933"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.92%" headers="mcps1.2.5.1.4 "><p id="a0b88476b907d44e3b574ad53c21ec02c"><a name="a0b88476b907d44e3b574ad53c21ec02c"></a><a name="a0b88476b907d44e3b574ad53c21ec02c"></a>Phase indicates if a volume is available, bound to a claim, or released by a claim.</p>
</td>
</tr>
<tr id="r9f4a227a36124c688410b8efc26982c1"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="ad0da24a861fe458eb21056243cea3bc5"><a name="ad0da24a861fe458eb21056243cea3bc5"></a><a name="ad0da24a861fe458eb21056243cea3bc5"></a>reason</p>
</td>
<td class="cellrowborder" valign="top" width="16.73%" headers="mcps1.2.5.1.2 "><p id="ad66281fe1d26410d989cbb2590abd08d"><a name="ad66281fe1d26410d989cbb2590abd08d"></a><a name="ad66281fe1d26410d989cbb2590abd08d"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.3 "><p id="ade3542f5b64e4fc9a695a75094861ae0"><a name="ade3542f5b64e4fc9a695a75094861ae0"></a><a name="ade3542f5b64e4fc9a695a75094861ae0"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.92%" headers="mcps1.2.5.1.4 "><p id="a3c27e955529f45a5831f35940ae58bb2"><a name="a3c27e955529f45a5831f35940ae58bb2"></a><a name="a3c27e955529f45a5831f35940ae58bb2"></a>Reason is a brief CamelCase string that describes any failure and is meant for machine parsing and tidy display in the CLI.</p>
</td>
</tr>
</tbody>
</table>

**表 5**  claimRef字段数据结构说明

<a name="t5fe2db24d4ee4588b001da6f826e3d3a"></a>
<table><thead align="left"><tr id="r0c9eacb1d1f44d099edd92ab1ccdc411"><th class="cellrowborder" valign="top" width="21.61%" id="mcps1.2.5.1.1"><p id="adaeb206a9e294ead8a84afe179925760"><a name="adaeb206a9e294ead8a84afe179925760"></a><a name="adaeb206a9e294ead8a84afe179925760"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.919999999999998%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.36%" id="mcps1.2.5.1.3"><p>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.11%" id="mcps1.2.5.1.4"><p id="a25acdc0edc4b4721ac8f6c5bd8303722"><a name="a25acdc0edc4b4721ac8f6c5bd8303722"></a><a name="a25acdc0edc4b4721ac8f6c5bd8303722"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r8d94e5c2b06a49048e0772b09309afa3"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="ab72a484b179a4c67a01718366a3545a2"><a name="ab72a484b179a4c67a01718366a3545a2"></a><a name="ab72a484b179a4c67a01718366a3545a2"></a>apiVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="a420f31b8bccc4faabb15ed4a5e808bcd"><a name="a420f31b8bccc4faabb15ed4a5e808bcd"></a><a name="a420f31b8bccc4faabb15ed4a5e808bcd"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="a09f42c6394a24387b604f4a758af6fb6"><a name="a09f42c6394a24387b604f4a758af6fb6"></a><a name="a09f42c6394a24387b604f4a758af6fb6"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="aac81bd8cc8a245dda1ba6cb44ac638ef"><a name="aac81bd8cc8a245dda1ba6cb44ac638ef"></a><a name="aac81bd8cc8a245dda1ba6cb44ac638ef"></a>API version of the referent.</p>
</td>
</tr>
<tr id="racf54160dc614e1e816b2327b2b01299"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="a196942e98fdc4e79b5a41deed9506d0f"><a name="a196942e98fdc4e79b5a41deed9506d0f"></a><a name="a196942e98fdc4e79b5a41deed9506d0f"></a>fieldPath</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="a97ad88db9b704b5aad87134643f6cac0"><a name="a97ad88db9b704b5aad87134643f6cac0"></a><a name="a97ad88db9b704b5aad87134643f6cac0"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="abdad0b5457b347db8c177e1feca0ad0b"><a name="abdad0b5457b347db8c177e1feca0ad0b"></a><a name="abdad0b5457b347db8c177e1feca0ad0b"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="a9f77c2267201402e9ec40cb07cb90df4"><a name="a9f77c2267201402e9ec40cb07cb90df4"></a><a name="a9f77c2267201402e9ec40cb07cb90df4"></a>If referring to a piece of an object instead of an entire object, this string should contain a valid JSON/Go field access statement, such as desiredState.manifest.containers[2]. For example, if the object reference is to a container within a pod, this would take on a value like: "spec.containers{name}" (where "name" refers to the name of the container that triggered the event) or if no container name is specified "spec.containers[2]" (container with index 2 in this pod). This syntax is chosen only to have some well-defined way of referencing a part of an object.</p>
</td>
</tr>
<tr id="r09a1a88d5d734b2ab26bb0d06acd3a68"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="af41593e5fff74f71b72a93681958c592"><a name="af41593e5fff74f71b72a93681958c592"></a><a name="af41593e5fff74f71b72a93681958c592"></a>kind</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="a59368126755e43a68b684dd2596b9d53"><a name="a59368126755e43a68b684dd2596b9d53"></a><a name="a59368126755e43a68b684dd2596b9d53"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="afa50c262387b4320a5a822fe1e5ba158"><a name="afa50c262387b4320a5a822fe1e5ba158"></a><a name="afa50c262387b4320a5a822fe1e5ba158"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="ac715a49a280d411893cb8e61bcbeb1bf"><a name="ac715a49a280d411893cb8e61bcbeb1bf"></a><a name="ac715a49a280d411893cb8e61bcbeb1bf"></a>Kind of the referent.</p>
</td>
</tr>
<tr id="r9b1eaa9a4c85447390a0d9615a7b0166"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="abb41cad359c8467fa5e856b0c0baaa18"><a name="abb41cad359c8467fa5e856b0c0baaa18"></a><a name="abb41cad359c8467fa5e856b0c0baaa18"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="a9955f73594b046c8b44ad9ed6a879705"><a name="a9955f73594b046c8b44ad9ed6a879705"></a><a name="a9955f73594b046c8b44ad9ed6a879705"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="a744fd92bed914a14b2ab554a011f16f5"><a name="a744fd92bed914a14b2ab554a011f16f5"></a><a name="a744fd92bed914a14b2ab554a011f16f5"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="aed7be3988a89464197b33683a61e3a05"><a name="aed7be3988a89464197b33683a61e3a05"></a><a name="aed7be3988a89464197b33683a61e3a05"></a>Name of the referent.</p>
</td>
</tr>
<tr id="r54b4238fa80c44f68bc933c4b7780867"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="a894a3898bf8146e98eed722ff68cfc75"><a name="a894a3898bf8146e98eed722ff68cfc75"></a><a name="a894a3898bf8146e98eed722ff68cfc75"></a>namespace</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="a3f676502fc814c2bb2e6273552d60d81"><a name="a3f676502fc814c2bb2e6273552d60d81"></a><a name="a3f676502fc814c2bb2e6273552d60d81"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="a1f25ecd62f7a4e74aa49cb98802d82e1"><a name="a1f25ecd62f7a4e74aa49cb98802d82e1"></a><a name="a1f25ecd62f7a4e74aa49cb98802d82e1"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="a2d567f0678c8435f8a121a522dfcffa9"><a name="a2d567f0678c8435f8a121a522dfcffa9"></a><a name="a2d567f0678c8435f8a121a522dfcffa9"></a>Namespace of the referent.</p>
</td>
</tr>
<tr id="rb97454377bc440eeb48980bbb379fb0f"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="a50d2ef30d7834b70be836ba3e9befb83"><a name="a50d2ef30d7834b70be836ba3e9befb83"></a><a name="a50d2ef30d7834b70be836ba3e9befb83"></a>resourceVersion</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="abab1246833154f1aaecde5212a52aa88"><a name="abab1246833154f1aaecde5212a52aa88"></a><a name="abab1246833154f1aaecde5212a52aa88"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="ab485b2338dbf4f08a65fd28ed05c257b"><a name="ab485b2338dbf4f08a65fd28ed05c257b"></a><a name="ab485b2338dbf4f08a65fd28ed05c257b"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="a67b4721a85744a1493073acf237a1818"><a name="a67b4721a85744a1493073acf237a1818"></a><a name="a67b4721a85744a1493073acf237a1818"></a>Specific resourceVersion to which this reference is made, if any.</p>
</td>
</tr>
<tr id="r15a080213357496287a072eed9804c57"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="ac590104402024a9da42fb279e3e8ae6c"><a name="ac590104402024a9da42fb279e3e8ae6c"></a><a name="ac590104402024a9da42fb279e3e8ae6c"></a>uid</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="a3e578b4026e1435e8a83b48ca611b620"><a name="a3e578b4026e1435e8a83b48ca611b620"></a><a name="a3e578b4026e1435e8a83b48ca611b620"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="a985db1fdf39b476c862dc2f34b36380d"><a name="a985db1fdf39b476c862dc2f34b36380d"></a><a name="a985db1fdf39b476c862dc2f34b36380d"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="a630c7c888ae44330815339b069c6988a"><a name="a630c7c888ae44330815339b069c6988a"></a><a name="a630c7c888ae44330815339b069c6988a"></a>UID of the referent.</p>
</td>
</tr>
</tbody>
</table>

**表 6**  hostPath字段数据结构说明

<a name="t49e3547d603e4c019abc62b357512bf6"></a>
<table><thead align="left"><tr id="rf9e8a0fc08f342b1877bad35e8767d4e"><th class="cellrowborder" valign="top" width="21.607839216078393%" id="mcps1.2.5.1.1"><p id="aac066a194f5a4c43b31933fd1ae24c13"><a name="aac066a194f5a4c43b31933fd1ae24c13"></a><a name="aac066a194f5a4c43b31933fd1ae24c13"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.10828917108289%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.988101189881014%" id="mcps1.2.5.1.3"><p>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.2957704229577%" id="mcps1.2.5.1.4"><p id="aba968fcdb2d0485da9b48face280c1d9"><a name="aba968fcdb2d0485da9b48face280c1d9"></a><a name="aba968fcdb2d0485da9b48face280c1d9"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r89870a35b0354475868bbd0f9e480e92"><td class="cellrowborder" valign="top" width="21.607839216078393%" headers="mcps1.2.5.1.1 "><p id="a61baae9b9bfc4d46b4d8bd7ded5098aa"><a name="a61baae9b9bfc4d46b4d8bd7ded5098aa"></a><a name="a61baae9b9bfc4d46b4d8bd7ded5098aa"></a>path</p>
</td>
<td class="cellrowborder" valign="top" width="17.10828917108289%" headers="mcps1.2.5.1.2 "><p id="a7f8cb15dee1d4b23b6ff227489a8cc1d"><a name="a7f8cb15dee1d4b23b6ff227489a8cc1d"></a><a name="a7f8cb15dee1d4b23b6ff227489a8cc1d"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="18.988101189881014%" headers="mcps1.2.5.1.3 "><p id="a2363d8740edc425290488f8ce234a9f0"><a name="a2363d8740edc425290488f8ce234a9f0"></a><a name="a2363d8740edc425290488f8ce234a9f0"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.2957704229577%" headers="mcps1.2.5.1.4 "><p id="ac0c3654642024c0aa1fa753e5d174f7e"><a name="ac0c3654642024c0aa1fa753e5d174f7e"></a><a name="ac0c3654642024c0aa1fa753e5d174f7e"></a>Path of the directory on the host.</p>
</td>
</tr>
</tbody>
</table>

**表 7**  nfs字段数据结构说明

<a name="t2f5e70bc193c4769a21652324f8fec4d"></a>
<table><thead align="left"><tr id="r1067814d8e7f4472ae3269ecd5155dd3"><th class="cellrowborder" valign="top" width="21.61%" id="mcps1.2.5.1.1"><p id="a4a18517e98684fb683a58e73d22ef6e4"><a name="a4a18517e98684fb683a58e73d22ef6e4"></a><a name="a4a18517e98684fb683a58e73d22ef6e4"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="16.919999999999998%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.36%" id="mcps1.2.5.1.3"><p>类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.11%" id="mcps1.2.5.1.4"><p id="ace0f23cc1099489a8de79f944bd8e372"><a name="ace0f23cc1099489a8de79f944bd8e372"></a><a name="ace0f23cc1099489a8de79f944bd8e372"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r35b95237f466499ea71f769f296a6269"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="adf05bf9e9eb24f61a7ca6072c0c2361e"><a name="adf05bf9e9eb24f61a7ca6072c0c2361e"></a><a name="adf05bf9e9eb24f61a7ca6072c0c2361e"></a>path</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="a5b06fcff8424404faba5b652d56f5ac0"><a name="a5b06fcff8424404faba5b652d56f5ac0"></a><a name="a5b06fcff8424404faba5b652d56f5ac0"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="acdd1d345103543b8934cc80317ccb338"><a name="acdd1d345103543b8934cc80317ccb338"></a><a name="acdd1d345103543b8934cc80317ccb338"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="afffa62a91c97422d9ba28acb79904f94"><a name="afffa62a91c97422d9ba28acb79904f94"></a><a name="afffa62a91c97422d9ba28acb79904f94"></a>Path that is exported by the NFS server.</p>
</td>
</tr>
<tr id="r898e9fe994de4476b20741a64441366b"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="a52eae370cf3d4f9c947e735708f34264"><a name="a52eae370cf3d4f9c947e735708f34264"></a><a name="a52eae370cf3d4f9c947e735708f34264"></a>readOnly</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="a7b0fa9034fa846aa9feae5f5a17d6030"><a name="a7b0fa9034fa846aa9feae5f5a17d6030"></a><a name="a7b0fa9034fa846aa9feae5f5a17d6030"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0079614924_p436639917128"><a name="zh-cn_topic_0079614924_p436639917128"></a><a name="zh-cn_topic_0079614924_p436639917128"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="afa12313c954546a1adc58c78a244cd04"><a name="afa12313c954546a1adc58c78a244cd04"></a><a name="afa12313c954546a1adc58c78a244cd04"></a>ReadOnly here will force the NFS export to be mounted with read-only permissions. Defaults to false.</p>
</td>
</tr>
<tr id="ref82ffa16dfc4686beff8b64c5f285f9"><td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.2.5.1.1 "><p id="ac1f9e5a70630464b950a84efd5874d7d"><a name="ac1f9e5a70630464b950a84efd5874d7d"></a><a name="ac1f9e5a70630464b950a84efd5874d7d"></a>server</p>
</td>
<td class="cellrowborder" valign="top" width="16.919999999999998%" headers="mcps1.2.5.1.2 "><p id="a7366e25c79344ad1a4c9a12ec12006a5"><a name="a7366e25c79344ad1a4c9a12ec12006a5"></a><a name="a7366e25c79344ad1a4c9a12ec12006a5"></a>No</p>
</td>
<td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.5.1.3 "><p id="ad0fe28d4b8354bd6afd457cf754582b7"><a name="ad0fe28d4b8354bd6afd457cf754582b7"></a><a name="ad0fe28d4b8354bd6afd457cf754582b7"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="42.11%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0079614924_p528750817137"><a name="zh-cn_topic_0079614924_p528750817137"></a><a name="zh-cn_topic_0079614924_p528750817137"></a>Server is the hostname or IP address of the NFS server.</p>
</td>
</tr>
</tbody>
</table>

**请求示例：**

```
{ 
    "apiVersion": "v1", 
    "kind": "PersistentVolume", 
    "metadata": { 
        "labels": { 
	"failure-domain.beta.kubernetes.io/region": "cn-north-1",
	"failure-domain.beta.kubernetes.io/zone": "cn-north-1a",
            "name": "pv-test-02" 
        }, 
        "name": "pv-test-02",
        "annotations": {
	"volume.beta.kubernetes.io/storage-class": "sata",
	"volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
        }
    }, 
    "spec": { 
        "accessModes": [ 
            "ReadWriteMany" 
        ], 
        "capacity": { 
            "storage": "10Gi" 
        }, 
        "hostPath": { 
            "path": "/home" 
        }, 
        "persistentVolumeReclaimPolicy": "Delete" 
    } 
}
```

## 响应消息<a name="s10a5fb14ddb8474d98072b106aef5bf9"></a>

**响应参数：**

响应参数的详细描述请参见[15.2-Table2 Request parameter](#tfdb73431f39846d4a56ec4eb558e1617).

**响应示例：**

```
{
    "kind": "PersistentVolume",
    "apiVersion": "v1",
    "metadata": {
        "name": "pv-test-02",
        "namespace": "default",
        "selfLink": "/api/v1/namespaces/default/persistentvolumes/pv-test-02",
        "uid": "98efd6aa-920a-11e8-81cc-fa163e49263c",
        "resourceVersion": "5672675",
        "creationTimestamp": "2018-07-28T02:04:44Z",
        "labels": {
            "failure-domain.beta.kubernetes.io/region": "cn-north-1",
            "failure-domain.beta.kubernetes.io/zone": "cn-north-1a",
            "name": "pv-test-02"
        },
        "annotations": {
            "volume.beta.kubernetes.io/storage-class": "sata",
            "volume.beta.kubernetes.io/storage-provisioner": "flexvolume-huawei.com/fuxivol"
        }
    },
    "spec": {
        "capacity": {
            "storage": "10Gi"
        },
        "hostPath": {
            "path": "/home",
            "type": ""
        },
        "accessModes": [
            "ReadWriteMany"
        ],
        "persistentVolumeReclaimPolicy": "Delete"
    },
    "status": {
        "phase": "Pending"
    }
}
```

## 状态码<a name="s9bf8cf335c8b4ceda65a73e0447ae83f"></a>

[表8](#teef67263b8ad4388911a1071b7457482)描述API的状态码。

**表 8**  状态码

<a name="teef67263b8ad4388911a1071b7457482"></a>
<table><thead align="left"><tr id="r3b2414a3fe4b46bb9e39039567404d32"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="aceb99f5f86954f389c5f1d49a77db226"><a name="aceb99f5f86954f389c5f1d49a77db226"></a><a name="aceb99f5f86954f389c5f1d49a77db226"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rc9c9d39fe7f747ada330decba6fe2ce3"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="a75721a25b43d41099ac4cbfce5b64af4"><a name="a75721a25b43d41099ac4cbfce5b64af4"></a><a name="a75721a25b43d41099ac4cbfce5b64af4"></a>201</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="a2c08ae6cf4b1443faaa56b7c81c533f5"><a name="a2c08ae6cf4b1443faaa56b7c81c533f5"></a><a name="a2c08ae6cf4b1443faaa56b7c81c533f5"></a>The request has been fulfilled, resulting in the creation of a new resource.</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

