# 给CCE集群的节点添加第二块数据盘<a name="cce_01_0344"></a>

您可以使用“安装前执行脚本“功能来配置CCE集群节点（弹性云服务器ECS），配置方法请参见[创建集群-高级配置](https://support.huaweicloud.com/usermanual-cce/cce_01_0028.html#cce_01_0028__li1824844253210)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   1.13.10及更高版本的集群创建节点时，若未开启LVM管理的数据盘，请参考本章节的介绍填写安装前执行脚本进行格式化，否则该数据盘仍会被LVM管理。
>-   1.13.10之前版本的集群创建节点时，若未开启LVM管理的数据盘请务必格式化，否则会与第一块数据盘进行二选一被LVM管理，进而导致与预期不符的情况。

在使用“安装前执行脚本“功能前，请预先编写一个可以格式化数据盘的脚本（**该脚本需以root用户执行**）。

**输入参数：**

1.  设定该脚本名字为formatdisk.sh，将formatdisk.sh保存到您的OBS中，获取该文件在OBS中的地址，获取方式请参见[通过对象URL访问对象](https://support.huaweicloud.com/usermanual-obs/obs_03_0319.html)。
2.  需要指定docker数据盘（使用LVM管理的数据盘称之为docker数据盘）的大小，且docker盘不能与第二块盘大小一致。例如：100G的docker盘，110G的第二块数据盘。
3.  第二块数据盘的挂载路径。例如：/data/code。

在“安装前执行脚本“中执行以下命令来实现格式化能力：

```
cd /tmp;curl -k -X GET OBS的地址/formatdisk.sh -1 -O;fdisk -l;sleep 30;bash -x formatdisk.sh 100 /data/code;fdisk -l
```

**formatdisk.sh脚本示例如下：**

```
dockerdisksize=$1
mountdir=$2
systemdisksize=40
i=0
while [ 20 -gt $i ]; do 
    echo $i; 
    if [ $(lsblk -o KNAME,TYPE | grep disk | grep -v nvme | awk '{print $1}' | awk '{ print "/dev/"$1}' |wc -l) -ge 3 ]; then 
        break 
    else 
        sleep 5 
    fi; 
    i=$[i+1] 
done 
all_devices=$(lsblk -o KNAME,TYPE | grep disk | grep -v nvme | awk '{print $1}' | awk '{ print "/dev/"$1}')
for device in ${all_devices[@]}; do
    isRawDisk=$(lsblk -n $device 2>/dev/null | grep disk | wc -l)
    if [[ ${isRawDisk} > 0 ]]; then
        # is it partitioned ?
        match=$(lsblk -n $device 2>/dev/null | grep -v disk | wc -l)
        if [[ ${match} > 0 ]]; then
            # already partited
            [[ -n "${DOCKER_BLOCK_DEVICES}" ]] && echo "Raw disk ${device} has been partition, will skip this device"
            continue
        fi
    else
        isPart=$(lsblk -n $device 2>/dev/null | grep part | wc -l)
        if [[ ${isPart} -ne 1 ]]; then
            # not parted
            [[ -n "${DOCKER_BLOCK_DEVICES}" ]] && echo "Disk ${device} has not been partition, will skip this device"
            continue
        fi
        # is used ?
        match=$(lsblk -n $device 2>/dev/null | grep -v part | wc -l)
        if [[ ${match} > 0 ]]; then
            # already used
            [[ -n "${DOCKER_BLOCK_DEVICES}" ]] && echo "Disk ${device} has been used, will skip this device"
            continue
        fi
        isMount=$(lsblk -n -o MOUNTPOINT $device 2>/dev/null)
        if [[ -n ${isMount} ]]; then
            # already used
            [[ -n "${DOCKER_BLOCK_DEVICES}" ]] && echo "Disk ${device} has been used, will skip this device"
            continue
        fi
        isLvm=$(sfdisk -lqL 2>>/dev/null | grep $device | grep "8e.*Linux LVM")
        if [[ ! -n ${isLvm} ]]; then
            # part system type is not Linux LVM
            [[ -n "${DOCKER_BLOCK_DEVICES}" ]] && echo "Disk ${device} system type is not Linux LVM, will skip this device"
            continue
        fi
    fi
    block_devices_size=$(lsblk -n -o SIZE $device 2>/dev/null | awk '{ print $1}')
    if [[ ${block_devices_size}"x" != "${dockerdisksize}Gx" ]] && [[ ${block_devices_size}"x" != "${systemdisksize}Gx" ]]; then
echo "n
p
1


w
" | fdisk $device
        mkfs -t ext4 ${device}1
        mkdir -p $mountdir
	uuid=$(blkid ${device}1 |awk '{print $2}')
	echo "${uuid}  $mountdir ext4  noatime  0 0" | tee -a /etc/fstab >/dev/null
        mount $mountdir
    fi
done
```

>![](public_sys-resources/icon-note.gif) **说明：** 
>如果直接拷贝上方示例不能正常执行，请使用dos2unix工具进行格式转换。

