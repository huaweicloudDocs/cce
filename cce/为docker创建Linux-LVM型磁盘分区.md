# 为docker创建Linux LVM型磁盘分区<a name="cce_01_0200"></a>

指导用户检查是否存在“可用裸盘“和“Linux LVM型磁盘分区“，并提供创建Linux LVM型磁盘分区的方法。

## 准备工作<a name="section19834182211494"></a>

为了使系统更加稳定，请给docker单独挂载数据盘，使用direct-lvm模式。挂载磁盘方法请参见[这里](https://support.huaweicloud.com/qs-evs/evs_01_0037.html)

## 操作步骤<a name="section18184888105"></a>

1.  <a name="li139011015111020"></a>检查当前节点是否存在可用的裸盘。
    1.  以root用户登录目标节点。
    2.  查看存在的裸盘设备。

        **lsblk -l | grep disk**

        若回显如下，表示节点存在名为xvda和xvdb的裸盘。

        ```
        xvda  202:0    0   40G  0 disk
        xvdb  202:16   0  100G  0 disk
        ```

    3.  检查裸盘是否已经被使用。

        **lsblk /dev/**_<devicename\>_

        _devicename_为裸盘名称，例如上个步骤的xvda和xvdb。

        分别执行**lsblk /dev/xvda**和**lsblk /dev/xvdb**，回显如下，表示xvda已被分区并使用，而裸盘xvdb可用。若没有可用裸盘，请为该节点绑定云硬盘，建议不小于80G。

        ```
        NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
        xvda    202:0    0   40G  0 disk
        ├─xvda1 202:1    0  100M  0 part /boot
        └─xvda2 202:2    0 39.9G  0 part /
        ```

        ```
        NAME MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
        xvdb 202:16   0  100G  0 disk
        ```

2.  检查是否存在可用区，当前仅支持Linux LVM型分区。
    1.  以root用户登录目标节点。
    2.  查看当前系统类型为Linux LVM的分区。

        **sfdisk -l 2\>\>/dev/null| grep "Linux LVM"**

        回显如下，表示当前系统有“/dev/nvme0n1p1“和“/dev/nvme0n1p2“两个Linux LVM分区。

        ```
        /dev/nvme0n1p1          1  204800  204800  209715200   8e  Linux LVM
        /dev/nvme0n1p2     204801  409600  204800  209715200   8e  Linux LVM
        ```

    3.  检查分区是否被使用。

        **lsblk  _<partdevice\>_**

        _<partdevice\>_为上个步骤中查到的Linux LVM分区。

        本例中，分别执行**lsblk /dev/nvme0n1p1**和**lsblk /dev/nvme0n1p2**，回显如下，表示nvme0n1p1分区已被使用，nvme0n1p2可用。

        ```
        NAME                       MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
        nvme0n1p1                   259:3    0  200G  0 part
        └─vgpaas-thinpool_tdata   251:8    0  360G  0 lvm
          └─vgpaas-thinpool       251:10   0  360G  0 lvm
        ```

        ```
        NAME      MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
        nvme0n1p2 259:1    0  100G  0 part
        ```

        若无可用区，请执行[3](#li111391316141612)为docker创建可用区。

3.  <a name="li111391316141612"></a>为docker创建Linux LVM型磁盘分区。
    1.  执行如下命令，创建磁盘分区。其中devicename为可用的裸盘名，如[1](#li139011015111020)中的xvdb。

        **fdisk /dev/_devicename_**

    2.  输入**n**创建新分区，输入**p**展示主分区号，输入**4**表示第4个主分区。

        **图 1**  创建分区<a name="fig14533113219112"></a>  
        ![](figures/创建分区.png "创建分区")

    3.  例如起始扇区和Last扇区配置如下：

        ```
        起始 扇区 (1048578048-4294967295，默认为 1048578048)：
        将使用默认值 1048578048
        Last 扇区, +扇区 or +size{K,M,G} (1048578048-4294967294，默认为 4294967294)：+100G
        ```

        表示分区4已设置为Linux类型，大小为100GiB。

    4.  输入**t**，修改分区系统类型，并在提示输入时输入Hex代码8e将系统修改为Linux LVM型。

        ```
        命令(输入 m 获取帮助)：t
        分区号 (1-4，默认 4)：4
        Hex 代码(输入 L 列出所有代码)：8e
        已将分区“Linux”的类型更改为“Linux LVM”
        ```

    5.  输入**w**，保存新建分区修改。

        ```
        命令(输入 m 获取帮助)：w
        The partition table has been altered!
        ```

    6.  执行**partprobe**命令，刷新磁盘分区。


