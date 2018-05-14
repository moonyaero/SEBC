Using username "ec2-user".
Authenticating with public key "imported-openssh-key-aws-admin-key-pair-sg"
Passphrase for key "imported-openssh-key-aws-admin-key-pair-sg":
Last login: Mon May 14 00:09:13 2018 from 66.96.221.165
[ec2-user@ip-172-31-16-48 ~]$ sudo su
[root@ip-172-31-16-48 ec2-user]# vm.swappiness
bash: vm.swappiness: command not found
[root@ip-172-31-16-48 ec2-user]# sudo sysctl -w vm.swappiness=1
vm.swappiness = 1
[root@ip-172-31-16-48 ec2-user]# mount
/dev/xvda1 on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw)
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)
sunrpc on /var/lib/nfs/rpc_pipefs type rpc_pipefs (rw)
[root@ip-172-31-16-48 ec2-user]# lsblk
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  40G  0 disk
└─xvda1 202:1    0  40G  0 part /
[root@ip-172-31-16-48 ec2-user]# lsblk -fs
NAME   FSTYPE LABEL  UUID                                 MOUNTPOINT
xvda1  ext4   rootfs bd7a0daf-89a3-4342-bcd1-7d35d14a18b3 /
└─xvda
[root@ip-172-31-16-48 ec2-user]# sudo tune2fs -m 0 /dev/xvda1
tune2fs 1.41.12 (17-May-2010)
Setting reserved blocks percentage to 0% (0 blocks)
[root@ip-172-31-16-48 ec2-user]# sudo tune2fs -l /dev/xvda1 | grep ‘Re            served block count’
grep: block: No such file or directory
grep: count’: No such file or directory
[root@ip-172-31-16-48 ec2-user]# sudo tune2fs -l /dev/xvda1
tune2fs 1.41.12 (17-May-2010)
Filesystem volume name:   rootfs
Last mounted on:          /
Filesystem UUID:          bd7a0daf-89a3-4342-bcd1-7d35d14a18b3
Filesystem magic number:  0xEF53
Filesystem revision #:    1 (dynamic)
Filesystem features:      has_journal ext_attr resize_inode dir_index             filetype needs_recovery extent flex_bg sparse_super large_file huge_fi            le uninit_bg dir_nlink extra_isize
Filesystem flags:         signed_directory_hash
Default mount options:    user_xattr acl
Filesystem state:         clean
Errors behavior:          Continue
Filesystem OS type:       Linux
Inode count:              2585600
Block count:              10484412
Reserved block count:     0
Free blocks:              9853519
Free inodes:              2490294
First block:              0
Block size:               4096
Fragment size:            4096
Reserved GDT blocks:      510
Blocks per group:         32768
Fragments per group:      32768
Inodes per group:         8080
Inode blocks per group:   505
Flex block group size:    16
Filesystem created:       Thu Aug 16 01:08:08 2012
Last mount time:          Sun May 13 22:20:23 2018
Last write time:          Mon May 14 00:24:22 2018
Mount count:              16
Maximum mount count:      -1
Last checked:             Thu Aug 16 01:08:08 2012
Check interval:           0 (<none>)
Lifetime writes:          8 GB
Reserved blocks uid:      0 (user root)
Reserved blocks gid:      0 (group root)
First inode:              11
Inode size:               256
Required extra isize:     28
Desired extra isize:      28
Journal inode:            8
Default directory hash:   half_md4
Directory Hash Seed:      1895459c-5ae3-4b36-bb15-77383182ce7a
Journal backup:           inode blocks
[root@ip-172-31-16-48 ec2-user]# sudo tune2fs -l /dev/xvda1 | grep 'Re            served block count'
Reserved block count:     0
[root@ip-172-31-16-48 ec2-user]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       40G  1.7G   38G   5% /
tmpfs           7.8G     0  7.8G   0% /dev/shm
[root@ip-172-31-16-48 ec2-user]# vi /etc/rc.d/rc.local

[1]+  Stopped                 vi /etc/rc.d/rc.local
[root@ip-172-31-16-48 ec2-user]# vi /etc/rc.d/rc.local
[root@ip-172-31-16-48 ec2-user]# cat /etc/rc.d/rc.local
#!/bin/sh
#
# This script will be executed *after* all the other init scripts.
# You can put your own initialization stuff in here if you don't
# want to do the full Sys V style init stuff.

# bz 707364
if [ ! -f /etc/blkid/blkid.tab ] ; then
        blkid /dev/xvda &>/dev/null
fi

touch /var/lock/subsys/local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag

[root@ip-172-31-16-48 ec2-user]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:bf:e9:b9:9b:a6 brd ff:ff:ff:ff:ff:ff
    inet 172.31.16.48/20 brd 172.31.31.255 scope global eth0
    inet6 fe80::bf:e9ff:feb9:9ba6/64 scope link
       valid_lft forever preferred_lft forever
[root@ip-172-31-16-48 ec2-user]#
