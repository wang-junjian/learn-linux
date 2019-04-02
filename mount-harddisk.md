# 挂载硬盘

## 查看分区和未挂载分区
* df -T 查看已经挂载的分区和文件系统类型
```bash
# df -T
文件系统       类型          1K-块     已用       可用 已用% 挂载点
udev           devtmpfs   32835892        0   32835892    0% /dev
tmpfs          tmpfs       6573236     3304    6569932    1% /run
/dev/sda2      ext4      243948900 62807680  168679652   28% /
tmpfs          tmpfs      32866164        0   32866164    0% /dev/shm
tmpfs          tmpfs          5120        4       5116    1% /run/lock
tmpfs          tmpfs      32866164        0   32866164    0% /sys/fs/cgroup
/dev/loop0     squashfs      13312    13312          0  100% /snap/gnome-characters/103
/dev/loop1     squashfs      35712    35712          0  100% /snap/gtk-common-themes/1122
/dev/loop3     squashfs       2304     2304          0  100% /snap/gnome-calculator/260
/dev/loop4     squashfs       3840     3840          0  100% /snap/gnome-system-monitor/51
/dev/loop2     squashfs     144128   144128          0  100% /snap/gnome-3-26-1604/78
/dev/loop5     squashfs      36224    36224          0  100% /snap/gtk-common-themes/1198
/dev/loop6     squashfs      14976    14976          0  100% /snap/gnome-logs/45
/dev/loop10    squashfs       3840     3840          0  100% /snap/gnome-system-monitor/57
/dev/loop9     squashfs      14848    14848          0  100% /snap/gnome-logs/37
/dev/loop8     squashfs      13312    13312          0  100% /snap/gnome-characters/139
/dev/loop7     squashfs     144128   144128          0  100% /snap/gnome-3-26-1604/82
/dev/loop12    squashfs     144128   144128          0  100% /snap/gnome-3-26-1604/74
/dev/loop13    squashfs       2432     2432          0  100% /snap/gnome-calculator/180
/dev/loop15    squashfs      93184    93184          0  100% /snap/core/6405
/dev/loop14    squashfs      93312    93312          0  100% /snap/core/6531
/dev/loop16    squashfs      35456    35456          0  100% /snap/gtk-common-themes/818
/dev/sda1      vfat         523248     6240     517008    2% /boot/efi
overlay        overlay   243948900 62807680  168679652   28% /var/lib/docker/overlay2/e6ad2fcaa72b7f21932660d3b9af4d44f2d67e8889a5e8a82e62c73c5841e22d/merged
shm            tmpfs         65536        0      65536    0% /var/lib/docker/containers/6bc82e908b45c9a58514a3491b70dac71085a04187b5a5e016546e6b9d10e77e/mounts/shm
tmpfs          tmpfs       6573232       32    6573200    1% /run/user/124
/dev/loop17    squashfs      55040    55040          0  100% /snap/core18/782
/dev/loop18    squashfs       1024     1024          0  100% /snap/gnome-logs/57
/dev/loop19    squashfs       3840     3840          0  100% /snap/gnome-system-monitor/70
/dev/loop20    squashfs       4224     4224          0  100% /snap/gnome-calculator/352
/dev/loop21    squashfs      15104    15104          0  100% /snap/gnome-characters/206
/dev/loop22    squashfs     146944   146944          0  100% /snap/gnome-3-28-1804/23
overlay        overlay   243948900 62807680  168679652   28% /var/lib/docker/overlay2/8d661bbb1b06a4faa7026fa2c49071dd9077056c48c7522e352829e1c0cb5f19/merged
shm            tmpfs         65536        0      65536    0% /var/lib/docker/containers/2f9bdad8b136db092b08c6e910f6434649e63fb53abb828bc5a5e752415d0d44/mounts/shm
/dev/loop23    squashfs      91392    91392          0  100% /snap/core/6673
overlay        overlay   243948900 62807680  168679652   28% /var/lib/docker/overlay2/eeabe07745279bfefd0687d71cac51884511a1cfc8eae12babc7e81578652e34/merged
shm            tmpfs         65536        0      65536    0% /var/lib/docker/containers/cc796da78db9784ecb606099be318c2d6c05bc3c8064267a03e922115171e941/mounts/shm
overlay        overlay   243948900 62807680  168679652   28% /var/lib/docker/overlay2/2fbbf5f13579edb835d1e1fd7aa234bd8f4d42f5f9a589c61a6af114a0c98b8e/merged
shm            tmpfs         65536        0      65536    0% /var/lib/docker/containers/93f473e4f261f3d046d8fea13aa65cc6a745eed36da194b3019109cd4b446531/mounts/shm
/dev/sdb1      ext4     1922197316 54038960 1770493388    3% /home/ailab
tmpfs          tmpfs       6573232        0    6573232    0% /run/user/1000
```

* fdisk -l 显示出所有挂载和未挂载的分区，但不显示文件系统类型
```bash
# fdisk -l
Disk /dev/sda：237.9 GiB，255416336384 字节，498860032 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节
磁盘标签类型：gpt
磁盘标识符：642F61A3-1D06-4B37-96C6-D4C0F270DA43

设备          起点      末尾      扇区   大小 类型
/dev/sda1     2048   1050623   1048576   512M EFI 系统
/dev/sda2  1050624 498857983 497807360 237.4G Linux 文件系统


Disk /dev/sdb：1.8 TiB，1999844147200 字节，3905945600 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 4096 字节
I/O 大小(最小/最佳)：4096 字节 / 4096 字节
磁盘标签类型：gpt
磁盘标识符：0AEF9C6C-11C7-4552-84B5-BCACB81AF798

设备        起点       末尾       扇区  大小 类型
/dev/sdb1   2048 3905945566 3905943519  1.8T Linux 文件系统
```

* parted -l 查看未挂载的文件系统类型，以及哪些分区尚未格式化
```bash
# parted -l
Model: DELL PERC H330 Adp (scsi)
磁盘 /dev/sda: 255GB
Sector size (logical/physical): 512B/512B
分区表：gpt
Disk Flags: 

数字  开始：  End    大小   文件系统  Name                  标志
 1    1049kB  538MB  537MB  fat32     EFI System Partition  启动, esp
 2    538MB   255GB  255GB  ext4


Model: DELL PERC H330 Adp (scsi)
磁盘 /dev/sdb: 2000GB
Sector size (logical/physical): 512B/4096B
分区表：gpt
Disk Flags: 

数字  开始：  End     大小    文件系统  Name  标志
 1    1049kB  2000GB  2000GB  ext4
 ```

* lsblk -f 查看未挂载的文件系统类型
```bash
# lsblk -f
NAME   FSTYPE   LABEL UUID                                 MOUNTPOINT
loop0  squashfs                                            /snap/gnome-characters/103
loop1  squashfs                                            /snap/gtk-common-themes/1122
loop2  squashfs                                            /snap/gnome-3-26-1604/78
loop3  squashfs                                            /snap/gnome-calculator/260
loop4  squashfs                                            /snap/gnome-system-monitor/51
loop5  squashfs                                            /snap/gtk-common-themes/1198
loop6  squashfs                                            /snap/gnome-logs/45
loop7  squashfs                                            /snap/gnome-3-26-1604/82
loop8  squashfs                                            /snap/gnome-characters/139
loop9  squashfs                                            /snap/gnome-logs/37
loop10 squashfs                                            /snap/gnome-system-monitor/57
loop12 squashfs                                            /snap/gnome-3-26-1604/74
loop13 squashfs                                            /snap/gnome-calculator/180
loop14 squashfs                                            /snap/core/6531
loop15 squashfs                                            /snap/core/6405
loop16 squashfs                                            /snap/gtk-common-themes/818
loop17 squashfs                                            /snap/core18/782
loop18 squashfs                                            /snap/gnome-logs/57
loop19 squashfs                                            /snap/gnome-system-monitor/70
loop20 squashfs                                            /snap/gnome-calculator/352
loop21 squashfs                                            /snap/gnome-characters/206
loop22 squashfs                                            /snap/gnome-3-28-1804/23
loop23 squashfs                                            /snap/core/6673
sda                                                        
├─sda1 vfat           2A30-FDFD                            /boot/efi
└─sda2 ext4           fff41461-581f-400b-bb88-fac0816643b8 /
sdb                                                        
└─sdb1 ext4           19b1746f-57d8-49b4-9703-5ce37debe2a5 /home/ailab
sr0                                                        
```

## 手动挂载
```bash
# mount /dev/sdb1 /home/ailab
```

## 自动挂载
```bash
# nano /etc/fstab

追加文本
# /home/ailab/ was on /dev/sdb1 during installation
UUID=19b1746f-57d8-49b4-9703-5ce37debe2a5 /home/ailab/ ext4 errors=remount-ro 0 1
```

## 显示文件系统的磁盘空间
```bash
# df -h /
文件系统        容量  已用  可用 已用% 挂载点
/dev/sda2       233G   60G  161G   28% /

# df -h /home/ailab/
文件系统        容量  已用  可用 已用% 挂载点
/dev/sdb1       1.8T   52G  1.7T    3% /home/ailab
```

## 测量文件系统的使用空间
```bash
# du -sh
62G	.

测量当前目录下的子目录使用空间
# du -h -d 1
4.3G	./log
4.0K	./local
4.0K	./opt
5.3M	./backups
4.0K	./crash
38G	./lib
4.0K	./mail
52K	./spool
1.9M	./tmp
4.0K	./metrics
54M	./nccl-repo-2.3.7-ga-cuda10.0
8.0K	./data
168K	./snap
129M	./cache
43G	.
```

## 参考资料
* [Linux 查看分区、未挂载分区](https://www.jianshu.com/p/67b53444a5cd)
* [linux下磁盘分区、挂载知多少](https://www.jianshu.com/p/ce31ae7da616)
* [linux查看目录大小 linux统计目录大小并排序 查看目录下所有一级子目录文件夹大小 du -h --max-depth=1 |grep](https://blog.csdn.net/learner198461/article/details/54602324)
