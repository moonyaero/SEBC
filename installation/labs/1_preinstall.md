Using username "ec2-user".
Authenticating with public key "imported-openssh-key-aws-admin-key-pair-sg"
Passphrase for key "imported-openssh-key-aws-admin-key-pair-sg":
Last login: Mon May 14 00:09:13 2018 from 66.96.221.165
[ec2-user@ip-172-31-16-48 ~]$ sudo su

# Changing vm.swappiness
## Changing vm.swappiness
####### Changing vm.swappiness

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
[root@ip-172-31-16-48 ec2-user]# vi /etc/hosts
[root@ip-172-31-16-48 ec2-user]# cat /etc/hosts
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
ec2-13-250-104-43.ap-southeast-1.compute.amazonaws.com  namenode
ec2-13-250-121-131.ap-southeast-1.compute.amazonaws.com cm
ec2-54-169-75-184.ap-southeast-1.compute.amazonaws.com  datanode1
ec2-54-251-176-98.ap-southeast-1.compute.amazonaws.com  datanode2
ec2-54-255-205-156.ap-southeast-1.compute.amazonaws.com datanode3
[root@ip-172-31-16-48 ec2-user]# nslookup datanode1
Server:         172.31.0.2
Address:        172.31.0.2#53

** server can't find datanode1: NXDOMAIN

[root@ip-172-31-16-48 ec2-user]# nslookup ec2-54-255-205-156.ap-southeast-1.compute.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-54-255-205-156.ap-southeast-1.compute.amazonaws.com
Address: 172.31.29.155

[root@ip-172-31-16-48 ec2-user]# nslookup ec2-13-250-104-43.ap-southeast-1.compute.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-13-250-104-43.ap-southeast-1.compute.amazonaws.com
Address: 172.31.26.120

[root@ip-172-31-16-48 ec2-user]# nslookup 172.31.26.120
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
120.26.31.172.in-addr.arpa      name = ip-172-31-26-120.ap-southeast-1.compute.internal.

Authoritative answers can be found from:

[root@ip-172-31-16-48 ec2-user]# nslookup 13.250.104.43
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
43.104.250.13.in-addr.arpa      name = ec2-13-250-104-43.ap-southeast-1.compute.amazonaws.com.

Authoritative answers can be found from:

[root@ip-172-31-16-48 ec2-user]# service nscd status
nscd: unrecognized service
[root@ip-172-31-16-48 ec2-user]# service ntpd status
ntpd (pid  1324) is running...
[root@ip-172-31-16-48 ec2-user]# yum -y install nscd
Loaded plugins: fastestmirror, security
Setting up Install Process
Determining fastest mirrors
 * base: centos.usonyx.net
 * extras: centos.usonyx.net
 * updates: centos.usonyx.net
base                                                       | 3.7 kB     00:00
base/primary_db                                            | 4.7 MB     00:00
extras                                                     | 3.4 kB     00:00
extras/primary_db                                          |  30 kB     00:00
updates                                                    | 3.4 kB     00:00
updates/primary_db                                         | 7.5 MB     00:00
Resolving Dependencies
--> Running transaction check
---> Package nscd.x86_64 0:2.12-1.209.el6_9.2 will be installed
--> Processing Dependency: glibc = 2.12-1.209.el6_9.2 for package: nscd-2.12-1.209.el6_9.2.x86_64
--> Running transaction check
---> Package glibc.i686 0:2.12-1.192.el6 will be updated
--> Processing Dependency: glibc = 2.12-1.192.el6 for package: glibc-common-2.12-1.192.el6.x86_64
---> Package glibc.x86_64 0:2.12-1.192.el6 will be updated
---> Package glibc.i686 0:2.12-1.209.el6_9.2 will be an update
---> Package glibc.x86_64 0:2.12-1.209.el6_9.2 will be an update
--> Running transaction check
---> Package glibc-common.x86_64 0:2.12-1.192.el6 will be updated
---> Package glibc-common.x86_64 0:2.12-1.209.el6_9.2 will be an update
--> Finished Dependency Resolution

Dependencies Resolved

==================================================================================
 Package             Arch          Version                   Repository      Size
==================================================================================
Installing:
 nscd                x86_64        2.12-1.209.el6_9.2        updates        232 k
Updating for dependencies:
 glibc               i686          2.12-1.209.el6_9.2        updates        4.4 M
 glibc               x86_64        2.12-1.209.el6_9.2        updates        3.8 M
 glibc-common        x86_64        2.12-1.209.el6_9.2        updates         14 M

Transaction Summary
==================================================================================
Install       1 Package(s)
Upgrade       3 Package(s)

Total download size: 23 M
Downloading Packages:
(1/4): glibc-2.12-1.209.el6_9.2.i686.rpm                   | 4.4 MB     00:00
(2/4): glibc-2.12-1.209.el6_9.2.x86_64.rpm                 | 3.8 MB     00:00
(3/4): glibc-common-2.12-1.209.el6_9.2.x86_64.rpm          |  14 MB     00:01
(4/4): nscd-2.12-1.209.el6_9.2.x86_64.rpm                  | 232 kB     00:00
----------------------------------------------------------------------------------
Total                                             7.9 MB/s |  23 MB     00:02
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Updating   : glibc-2.12-1.209.el6_9.2.x86_64                                1/7
  Updating   : glibc-common-2.12-1.209.el6_9.2.x86_64                         2/7
  Installing : nscd-2.12-1.209.el6_9.2.x86_64                                 3/7
  Updating   : glibc-2.12-1.209.el6_9.2.i686                                  4/7
  Cleanup    : glibc-2.12-1.192.el6                                           5/7
  Cleanup    : glibc-2.12-1.192.el6                                           6/7
  Cleanup    : glibc-common-2.12-1.192.el6.x86_64                             7/7
  Verifying  : glibc-2.12-1.209.el6_9.2.i686                                  1/7
  Verifying  : glibc-common-2.12-1.209.el6_9.2.x86_64                         2/7
  Verifying  : nscd-2.12-1.209.el6_9.2.x86_64                                 3/7
  Verifying  : glibc-2.12-1.209.el6_9.2.x86_64                                4/7
  Verifying  : glibc-2.12-1.192.el6.i686                                      5/7
  Verifying  : glibc-2.12-1.192.el6.x86_64                                    6/7
  Verifying  : glibc-common-2.12-1.192.el6.x86_64                             7/7

Installed:
  nscd.x86_64 0:2.12-1.209.el6_9.2

Dependency Updated:
  glibc.i686 0:2.12-1.209.el6_9.2             glibc.x86_64 0:2.12-1.209.el6_9.2
  glibc-common.x86_64 0:2.12-1.209.el6_9.2

Complete!
[root@ip-172-31-16-48 ec2-user]# service nscd status
nscd is stopped
[root@ip-172-31-16-48 ec2-user]# service nscd staart
Usage: /etc/init.d/nscd {start|stop|status|restart|reload|condrestart}
[root@ip-172-31-16-48 ec2-user]# service nscd start
Starting nscd:                                             [  OK  ]
[root@ip-172-31-16-48 ec2-user]# service nscd status
nscd (pid 5948) is running...
