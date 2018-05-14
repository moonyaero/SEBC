# Pre-installation tasks
Using username "ec2-user". <br>
Authenticating with public key "imported-openssh-key-aws-admin-key-pair-sg" <br>
Passphrase for key "imported-openssh-key-aws-admin-key-pair-sg": <br>
Last login: Mon May 14 00:09:13 2018 from 66.96.221.165 <br>
[ec2-user@ip-172-31-16-48 ~]$ sudo su 

## Cloudera Pre-requisites

### 1) Setting vm.swappiness = 1

[root@ip-172-31-16-48 ec2-user]# sudo sysctl -w vm.swappiness=1 <br>
vm.swappiness = 1

### 2) Show the mount attributes of your volume(s)

[root@ip-172-31-16-48 ec2-user]# mount <br>
/dev/xvda1 on / type ext4 (rw) <br>
proc on /proc type proc (rw) <br>
sysfs on /sys type sysfs (rw) <br>
devpts on /dev/pts type devpts (rw,gid=5,mode=620) <br>
tmpfs on /dev/shm type tmpfs (rw) <br>
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw) <br>
sunrpc on /var/lib/nfs/rpc_pipefs type rpc_pipefs (rw) <br>

[root@ip-172-31-16-48 ec2-user]# lsblk <br>
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT <br>
xvda    202:0    0  40G  0 disk <br>
└─xvda1 202:1    0  40G  0 part / <br>

[root@ip-172-31-16-48 ec2-user]# lsblk -fs
NAME   FSTYPE LABEL  UUID                                 MOUNTPOINT
xvda1  ext4   rootfs bd7a0daf-89a3-4342-bcd1-7d35d14a18b3 /
└─xvda

### 3) Removing Reserved Block Count on ext4

[root@ip-172-31-16-48 ec2-user]# sudo tune2fs -m 0 /dev/xvda1 <br>
tune2fs 1.41.12 (17-May-2010) <br>
Setting reserved blocks percentage to 0% (0 blocks) <br>

[root@ip-172-31-16-48 ec2-user]# sudo tune2fs -l /dev/xvda1 <br>
tune2fs 1.41.12 (17-May-2010) <br>
Filesystem volume name:   rootfs <br>
Last mounted on:          / <br>
Filesystem UUID:          bd7a0daf-89a3-4342-bcd1-7d35d14a18b3 <br>
Filesystem magic number:  0xEF53 <br>
Filesystem revision #:    1 (dynamic) <br>
Filesystem features:      has_journal ext_attr resize_inode dir_index             filetype needs_recovery extent flex_bg sparse_super large_file huge_fi            le uninit_bg dir_nlink extra_isize <br>
Filesystem flags:         signed_directory_hash <br>
Default mount options:    user_xattr acl <br>
Filesystem state:         clean <br>
Errors behavior:          Continue <br>
Filesystem OS type:       Linux <br>
Inode count:              2585600 <br>
Block count:              10484412 <br>
Reserved block count:     0 <br>
Free blocks:              9853519 <br>
Free inodes:              2490294 <br>
First block:              0 <br>
Block size:               4096 <br>
Fragment size:            4096 <br>
Reserved GDT blocks:      510 <br>
Blocks per group:         32768 <br>
Fragments per group:      32768 <br>
Inodes per group:         8080 <br>
Inode blocks per group:   505 <br>
Flex block group size:    16 <br>
Filesystem created:       Thu Aug 16 01:08:08 2012 <br>
Last mount time:          Sun May 13 22:20:23 2018 <br>
Last write time:          Mon May 14 00:24:22 2018 <br>
Mount count:              16 <br>
Maximum mount count:      -1 <br>
Last checked:             Thu Aug 16 01:08:08 2012 <br>
Check interval:           0 (<none>) <br>
Lifetime writes:          8 GB <br>
Reserved blocks uid:      0 (user root) <br>
Reserved blocks gid:      0 (group root) <br>
First inode:              11 <br>
Inode size:               256 <br>
Required extra isize:     28 <br>
Desired extra isize:      28 <br>
Journal inode:            8 <br>
Default directory hash:   half_md4 <br>
Directory Hash Seed:      1895459c-5ae3-4b36-bb15-77383182ce7a <br>
Journal backup:           inode blocks <br>

[root@ip-172-31-16-48 ec2-user]# sudo tune2fs -l /dev/xvda1 | grep 'Reserved block count' <br>
Reserved block count:     0

[root@ip-172-31-16-48 ec2-user]# df -h <br>
Filesystem      Size  Used Avail Use% Mounted on <br>
/dev/xvda1      40G  1.7G   38G   <tab> 5% / <br>
tmpfs           7.8G     0  7.8G   0% /dev/shm <br>

### 4) Disabling Transparent Huge Page

[root@ip-172-31-16-48 ec2-user]# vi /etc/rc.d/rc.local <br>
[root@ip-172-31-16-48 ec2-user]# cat /etc/rc.d/rc.local <br>
!/bin/sh <br>

This script will be executed *after* all the other init scripts. <br>
You can put your own initialization stuff in here if you don't <br>
want to do the full Sys V style init stuff. <br>

bz 707364 <br>
if [ ! -f /etc/blkid/blkid.tab ] ; then <br>
        blkid /dev/xvda &>/dev/null <br>
fi

touch /var/lock/subsys/local <br>
echo never > /sys/kernel/mm/transparent_hugepage/enabled <br>
echo never > /sys/kernel/mm/transparent_hugepage/defrag <br>

### 5) List your network interface configuration

[root@ip-172-31-16-48 ec2-user]# vi /etc/hosts <br>
[root@ip-172-31-16-48 ec2-user]# cat /etc/hosts <br>
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4 <br>
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6 <br>
ec2-13-250-104-43.ap-southeast-1.compute.amazonaws.com  namenode <br>
ec2-13-250-121-131.ap-southeast-1.compute.amazonaws.com cm <br>
ec2-54-169-75-184.ap-southeast-1.compute.amazonaws.com  datanode1 <br>
ec2-54-251-176-98.ap-southeast-1.compute.amazonaws.com  datanode2 <br>
ec2-54-255-205-156.ap-southeast-1.compute.amazonaws.com datanode3 <br>

### 6) Show that forward and reverse host lookups are correctly resolved

[root@ip-172-31-16-48 ec2-user]# nslookup ec2-54-255-205-156.ap-southeast-1.compute.amazonaws.com <br>
Server:         172.31.0.2 <br>
Address:        172.31.0.2#53 <br>

Non-authoritative answer: <br>
Name:   ec2-54-255-205-156.ap-southeast-1.compute.amazonaws.com <br>
Address: 172.31.29.155

[root@ip-172-31-16-48 ec2-user]# nslookup ec2-13-250-104-43.ap-southeast-1.compute.amazonaws.com<br>
Server:         172.31.0.2 <br>
Address:        172.31.0.2#53 

Non-authoritative answer: <br>
Name:   ec2-13-250-104-43.ap-southeast-1.compute.amazonaws.com <br>
Address: 172.31.26.120


[root@ip-172-31-16-48 ec2-user]# nslookup 172.31.26.120 <br>
Server:         172.31.0.2 <br>
Address:        172.31.0.2#53

Non-authoritative answer: <br>
120.26.31.172.in-addr.arpa      name = ip-172-31-26-120.ap-southeast-1.compute.internal. <br>

Authoritative answers can be found from:

[root@ip-172-31-16-48 ec2-user]# nslookup 13.250.104.43 <br>
Server:         172.31.0.2 <br>
Address:        172.31.0.2#53

Non-authoritative answer: <br>
43.104.250.13.in-addr.arpa      name = ec2-13-250-104-43.ap-southeast-1.compute.amazonaws.com.

Authoritative answers can be found from:

### 7)Show the **nscd** and **ntpd** service is running

[root@ip-172-31-16-48 ec2-user]# service nscd status <br>
nscd: unrecognized service

[root@ip-172-31-16-48 ec2-user]# service ntpd status <br>
ntpd (pid  1324) is running...

[root@ip-172-31-16-48 ec2-user]# yum -y install nscd <br>
Loaded plugins: fastestmirror, security
Setting up Install Process
Determining fastest mirrors
 * base: centos.usonyx.net
 * extras: centos.usonyx.net
 * updates: centos.usonyx.net <br>
base                                                       | 3.7 kB     00:00 <br>
base/primary_db                                            | 4.7 MB     00:00 <br>
extras                                                     | 3.4 kB     00:00 <br>
extras/primary_db                                          |  30 kB     00:00 <br>
updates                                                    | 3.4 kB     00:00 <br>
updates/primary_db                                         | 7.5 MB     00:00 <br>
Resolving Dependencies
--> Running transaction check <br>
---> Package nscd.x86_64 0:2.12-1.209.el6_9.2 will be installed <br>
--> Processing Dependency: glibc = 2.12-1.209.el6_9.2 for package: nscd-2.12-1.209.el6_9.2.x86_64 <br>
--> Running transaction check <br>
---> Package glibc.i686 0:2.12-1.192.el6 will be updated <br>
--> Processing Dependency: glibc = 2.12-1.192.el6 for package: glibc-common-2.12-1.192.el6.x86_64 <br>
---> Package glibc.x86_64 0:2.12-1.192.el6 will be updated <br>
---> Package glibc.i686 0:2.12-1.209.el6_9.2 will be an update <br>
---> Package glibc.x86_64 0:2.12-1.209.el6_9.2 will be an update <br>
--> Running transaction check <br>
---> Package glibc-common.x86_64 0:2.12-1.192.el6 will be updated <br>
---> Package glibc-common.x86_64 0:2.12-1.209.el6_9.2 will be an update <br>
--> Finished Dependency Resolution <br>

Dependencies Resolved <br>
\===================================================  <br>
 Package             Arch          Version                   Repository      Size  <br>
\=================================================== <br>
Installing: <br>
 nscd                x86_64        2.12-1.209.el6_9.2        updates        232 k <br>
Updating for dependencies: <br>
 glibc               i686          2.12-1.209.el6_9.2        updates        4.4 M <br>
 glibc               x86_64        2.12-1.209.el6_9.2        updates        3.8 M <br>
 glibc-common        x86_64        2.12-1.209.el6_9.2        updates         14 M <br>

Transaction Summary <br>
\================================================================================== <br>
Install       1 Package(s) <br>
Upgrade       3 Package(s) <br>

Total download size: 23 M <br>

Downloading Packages:  <br>
(1/4): glibc-2.12-1.209.el6_9.2.i686.rpm                   | 4.4 MB     00:00 <br>
(2/4): glibc-2.12-1.209.el6_9.2.x86_64.rpm                 | 3.8 MB     00:00 <br>
(3/4): glibc-common-2.12-1.209.el6_9.2.x86_64.rpm          |  14 MB     00:01 <br>
(4/4): nscd-2.12-1.209.el6_9.2.x86_64.rpm                  | 232 kB     00:00 <br>
---------------------------------------------------------------------------------- <br>
Total                                             7.9 MB/s |  23 MB     00:02 <br>
Running rpm_check_debug <br>
Running Transaction Test <br>
Transaction Test Succeeded <br>
Running Transaction <br>
  Updating   : glibc-2.12-1.209.el6_9.2.x86_64                                1/7 <br>
  Updating   : glibc-common-2.12-1.209.el6_9.2.x86_64                         2/7 <br>
  Installing : nscd-2.12-1.209.el6_9.2.x86_64                                 3/7 <br>
  Updating   : glibc-2.12-1.209.el6_9.2.i686                                  4/7 <br>
  Cleanup    : glibc-2.12-1.192.el6                                           5/7 <br>
  Cleanup    : glibc-2.12-1.192.el6                                           6/7 <br>
  Cleanup    : glibc-common-2.12-1.192.el6.x86_64                             7/7 <br>
  Verifying  : glibc-2.12-1.209.el6_9.2.i686                                  1/7 <br>
  Verifying  : glibc-common-2.12-1.209.el6_9.2.x86_64                         2/7 <br>
  Verifying  : nscd-2.12-1.209.el6_9.2.x86_64                                 3/7 <br>
  Verifying  : glibc-2.12-1.209.el6_9.2.x86_64                                4/7 <br>
  Verifying  : glibc-2.12-1.192.el6.i686                                      5/7 <br>
  Verifying  : glibc-2.12-1.192.el6.x86_64                                    6/7 <br>
  Verifying  : glibc-common-2.12-1.192.el6.x86_64                             7/7 <br>

Installed: <br>
  nscd.x86_64 0:2.12-1.209.el6_9.2 <br>

Dependency Updated: <br>
  glibc.i686 0:2.12-1.209.el6_9.2             glibc.x86_64 0:2.12-1.209.el6_9.2 <br>
  glibc-common.x86_64 0:2.12-1.209.el6_9.2 <br>

Complete! <br>

[root@ip-172-31-16-48 ec2-user]# service nscd status <br>
nscd is stopped

[root@ip-172-31-16-48 ec2-user]# service nscd start <br>
Starting nscd:                                             [  OK  ]

[root@ip-172-31-16-48 ec2-user]# service nscd status <br>
nscd (pid 5948) is running...
