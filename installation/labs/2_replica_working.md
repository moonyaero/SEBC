[root@ip-172-31-16-48 ec2-user]# cd /etc/yum.repos.d
[root@ip-172-31-16-48 yum.repos.d]# ll
total 32
-rw-r--r-- 1 root root 1991 May 18  2016 CentOS-Base.repo
-rw-r--r-- 1 root root  647 May 18  2016 CentOS-Debuginfo.repo
-rw-r--r-- 1 root root  289 May 18  2016 CentOS-fasttrack.repo
-rw-r--r-- 1 root root  630 May 18  2016 CentOS-Media.repo
-rw-r--r-- 1 root root 6259 May 18  2016 CentOS-Vault.repo
-rw-r--r-- 1 root root  957 Feb 14  2013 epel.repo
-rw-r--r-- 1 root root 1056 Nov  4  2012 epel-testing.repo
[root@ip-172-31-16-48 yum.repos.d]# wget https://dev.mysql.com/get/mysql80-community-release-el6-1.noarch.rpm
--2018-05-14 00:47:11--  https://dev.mysql.com/get/mysql80-community-release-el6-1.noarch.rpm
Resolving dev.mysql.com... 137.254.60.11
Connecting to dev.mysql.com|137.254.60.11|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://repo.mysql.com//mysql80-community-release-el6-1.noarch.rpm [following]
--2018-05-14 00:47:13--  https://repo.mysql.com//mysql80-community-release-el6-1.noarch.rpm
Resolving repo.mysql.com... 104.116.25.237
Connecting to repo.mysql.com|104.116.25.237|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 25800 (25K) [application/x-redhat-package-manager]
Saving to: “mysql80-community-release-el6-1.noarch.rpm”

100%[========================================>] 25,800      --.-K/s   in 0.002s

2018-05-14 00:47:13 (14.2 MB/s) - “mysql80-community-release-el6-1.noarch.rpm” saved [25800/25800]

[root@ip-172-31-16-48 yum.repos.d]# rpm -qa | grep mysql
mysql-libs-5.1.73-8.el6_8.x86_64
[root@ip-172-31-16-48 yum.repos.d]# ll
total 60
-rw-r--r-- 1 root root  1991 May 18  2016 CentOS-Base.repo
-rw-r--r-- 1 root root   647 May 18  2016 CentOS-Debuginfo.repo
-rw-r--r-- 1 root root   289 May 18  2016 CentOS-fasttrack.repo
-rw-r--r-- 1 root root   630 May 18  2016 CentOS-Media.repo
-rw-r--r-- 1 root root  6259 May 18  2016 CentOS-Vault.repo
-rw-r--r-- 1 root root   957 Feb 14  2013 epel.repo
-rw-r--r-- 1 root root  1056 Nov  4  2012 epel-testing.repo
-rw-r--r-- 1 root root 25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.rpm
[root@ip-172-31-16-48 yum.repos.d]# rm mysql80-community-release-el6-1.noarch.rpm
[root@ip-172-31-16-48 yum.repos.d]# cd /
[root@ip-172-31-16-48 /]# ls
bin          cgroup  home   lost+found  opt   run      srv  usr
boot         dev     lib    media       proc  sbin     sys  var
certsbundle  etc     lib64  mnt         root  selinux  tmp
[root@ip-172-31-16-48 /]# mkdir repofiles
[root@ip-172-31-16-48 /]# ls
bin          cgroup  home   lost+found  opt        root  selinux  tmp
boot         dev     lib    media       proc       run   srv      usr
certsbundle  etc     lib64  mnt         repofiles  sbin  sys      var
[root@ip-172-31-16-48 /]# cd repofiles/
[root@ip-172-31-16-48 repofiles]# wget https://dev.mysql.com/get/mysql80-community-release-el6-1.noarch.rpm
--2018-05-14 00:48:40--  https://dev.mysql.com/get/mysql80-community-release-el6-1.noarch.rpm
Resolving dev.mysql.com... 137.254.60.11
Connecting to dev.mysql.com|137.254.60.11|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://repo.mysql.com//mysql80-community-release-el6-1.noarch.rpm [following]
--2018-05-14 00:48:41--  https://repo.mysql.com//mysql80-community-release-el6-1.noarch.rpm
Resolving repo.mysql.com... 104.116.25.237
Connecting to repo.mysql.com|104.116.25.237|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 25800 (25K) [application/x-redhat-package-manager]
Saving to: “mysql80-community-release-el6-1.noarch.rpm”

100%[========================================>] 25,800      --.-K/s   in 0.002s

2018-05-14 00:48:41 (15.1 MB/s) - “mysql80-community-release-el6-1.noarch.rpm” saved [25800/25800]

[root@ip-172-31-16-48 repofiles]# ll
total 28
-rw-r--r-- 1 root root 25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.rpm
[root@ip-172-31-16-48 repofiles]# rpm mysql80-community-release-el6-1.noarch.rpm
RPM version 4.8.0
Copyright (C) 1998-2002 - Red Hat, Inc.
This program may be freely redistributed under the terms of the GNU GPL

Usage: rpm [-aKfgpWHqVcdilsKiv?] [-a|--all] [-f|--file] [-g|--group]
        [-p|--package] [-W|--ftswalk] [--pkgid] [--hdrid] [--fileid]
        [--specfile] [--triggeredby] [--whatrequires] [--whatprovides]
        [--nomanifest] [-c|--configfiles] [-d|--docfiles] [--dump] [-l|--list]
        [--queryformat=QUERYFORMAT] [-s|--state] [--nofiledigest] [--nomd5]
        [--nofiles] [--nodeps] [--noscript] [--comfollow] [--logical]
        [--nochdir] [--nostat] [--physical] [--seedot] [--xdev] [--whiteout]
        [--addsign] [-K|--checksig] [--delsign] [--import] [--resign]
        [--nodigest] [--nosignature] [--initdb] [--rebuilddb] [--aid]
        [--allfiles] [--allmatches] [--badreloc] [-e|--erase <package>+]
        [--excludedocs] [--excludepath=<path>] [--fileconflicts] [--force]
        [-F|--freshen <packagefile>+] [-h|--hash] [--ignorearch] [--ignoreos]
        [--ignoresize] [-i|--install] [--justdb] [--nodeps] [--nofiledigest]
        [--nomd5] [--nocontexts] [--noorder] [--nosuggest] [--noscripts]
        [--notriggers] [--oldpackage] [--percent] [--prefix=<dir>]
        [--relocate=<old>=<new>] [--replacefiles] [--replacepkgs] [--test]
        [-U|--upgrade <packagefile>+] [--quiet] [-D|--define 'MACRO EXPR']
        [-E|--eval 'EXPR'] [--macros=<FILE:...>] [--nodigest] [--nosignature]
        [--rcfile=<FILE:...>] [-r|--root ROOT] [--querytags] [--showrc]
        [--quiet] [-v|--verbose] [--version] [-?|--help] [--usage] [--scripts]
        [--setperms] [--setugids] [--conflicts] [--obsoletes] [--provides]
        [--requires] [--info] [--changelog] [--xml] [--triggers] [--last]
        [--dupes] [--filesbypkg] [--fileclass] [--filecolor] [--fscontext]
        [--fileprovide] [--filerequire] [--filecaps]
[root@ip-172-31-16-48 repofiles]# yum -y localinstall mysql80-community-release-el6-1.noarch.rpm
Loaded plugins: fastestmirror, security
Setting up Local Package Process
Examining mysql80-community-release-el6-1.noarch.rpm: mysql80-community-release-el6-1.noarch
Marking mysql80-community-release-el6-1.noarch.rpm to be installed
Loading mirror speeds from cached hostfile
 * base: centos.usonyx.net
 * extras: centos.usonyx.net
 * updates: centos.usonyx.net
Resolving Dependencies
--> Running transaction check
---> Package mysql80-community-release.noarch 0:el6-1 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

==================================================================================
 Package               Arch   Version
                                    Repository                               Size
==================================================================================
Installing:
 mysql80-community-release
                       noarch el6-1 /mysql80-community-release-el6-1.noarch  31 k

Transaction Summary
==================================================================================
Install       1 Package(s)

Total size: 31 k
Installed size: 31 k
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : mysql80-community-release-el6-1.noarch                         1/1
  Verifying  : mysql80-community-release-el6-1.noarch                         1/1

Installed:
  mysql80-community-release.noarch 0:el6-1

Complete!

[root@ip-172-31-16-48 repofiles]# wget https://dev.mysql.com/get/mysql80-community                                                                                      -release-el6-1.noarch.rpm
--2018-05-14 00:48:40--  https://dev.mysql.com/get/mysql80-community-release-el6-1                                                                                      .noarch.rpm
Resolving dev.mysql.com... 137.254.60.11
Connecting to dev.mysql.com|137.254.60.11|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://repo.mysql.com//mysql80-community-release-el6-1.noarch.rpm [foll                                                                                      owing]
--2018-05-14 00:48:41--  https://repo.mysql.com//mysql80-community-release-el6-1.n                                                                                      oarch.rpm
Resolving repo.mysql.com... 104.116.25.237
Connecting to repo.mysql.com|104.116.25.237|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 25800 (25K) [application/x-redhat-package-manager]
Saving to: “mysql80-community-release-el6-1.noarch.rpm”

100%[========================================>] 25,800      --.-K/s   in 0.002s

2018-05-14 00:48:41 (15.1 MB/s) - “mysql80-community-release-el6-1.noarch.rpm” sav                                                                                      ed [25800/25800]

[root@ip-172-31-16-48 repofiles]# ll
total 28
-rw-r--r-- 1 root root 25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.r                                                                                      pm
[root@ip-172-31-16-48 repofiles]# rpm mysql80-community-release-el6-1.noarch.rpm
RPM version 4.8.0
Copyright (C) 1998-2002 - Red Hat, Inc.
This program may be freely redistributed under the terms of the GNU GPL

Usage: rpm [-aKfgpWHqVcdilsKiv?] [-a|--all] [-f|--file] [-g|--group]
        [-p|--package] [-W|--ftswalk] [--pkgid] [--hdrid] [--fileid]
        [--specfile] [--triggeredby] [--whatrequires] [--whatprovides]
        [--nomanifest] [-c|--configfiles] [-d|--docfiles] [--dump] [-l|--list]
        [--queryformat=QUERYFORMAT] [-s|--state] [--nofiledigest] [--nomd5]
        [--nofiles] [--nodeps] [--noscript] [--comfollow] [--logical]
        [--nochdir] [--nostat] [--physical] [--seedot] [--xdev] [--whiteout]
        [--addsign] [-K|--checksig] [--delsign] [--import] [--resign]
        [--nodigest] [--nosignature] [--initdb] [--rebuilddb] [--aid]
        [--allfiles] [--allmatches] [--badreloc] [-e|--erase <package>+]
        [--excludedocs] [--excludepath=<path>] [--fileconflicts] [--force]
        [-F|--freshen <packagefile>+] [-h|--hash] [--ignorearch] [--ignoreos]
        [--ignoresize] [-i|--install] [--justdb] [--nodeps] [--nofiledigest]
        [--nomd5] [--nocontexts] [--noorder] [--nosuggest] [--noscripts]
        [--notriggers] [--oldpackage] [--percent] [--prefix=<dir>]
        [--relocate=<old>=<new>] [--replacefiles] [--replacepkgs] [--test]
        [-U|--upgrade <packagefile>+] [--quiet] [-D|--define 'MACRO EXPR']
        [-E|--eval 'EXPR'] [--macros=<FILE:...>] [--nodigest] [--nosignature]
        [--rcfile=<FILE:...>] [-r|--root ROOT] [--querytags] [--showrc]
        [--quiet] [-v|--verbose] [--version] [-?|--help] [--usage] [--scripts]
        [--setperms] [--setugids] [--conflicts] [--obsoletes] [--provides]
        [--requires] [--info] [--changelog] [--xml] [--triggers] [--last]
        [--dupes] [--filesbypkg] [--fileclass] [--filecolor] [--fscontext]
        [--fileprovide] [--filerequire] [--filecaps]
[root@ip-172-31-16-48 repofiles]# yum -y localinstall mysql80-community-release-el                                                                                      6-1.noarch.rpm
Loaded plugins: fastestmirror, security
Setting up Local Package Process
Examining mysql80-community-release-el6-1.noarch.rpm: mysql80-community-release-el                                                                                      6-1.noarch
Marking mysql80-community-release-el6-1.noarch.rpm to be installed
Loading mirror speeds from cached hostfile
 * base: centos.usonyx.net
 * extras: centos.usonyx.net
 * updates: centos.usonyx.net
Resolving Dependencies
--> Running transaction check
---> Package mysql80-community-release.noarch 0:el6-1 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

==================================================================================
 Package               Arch   Version
                                    Repository                               Size
==================================================================================
Installing:
 mysql80-community-release
                       noarch el6-1 /mysql80-community-release-el6-1.noarch  31 k

Transaction Summary
==================================================================================
Install       1 Package(s)

Total size: 31 k
Installed size: 31 k
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : mysql80-community-release-el6-1.noarch                         1/1
  Verifying  : mysql80-community-release-el6-1.noarch                         1/1

Installed:
  mysql80-community-release.noarch 0:el6-1

Complete!
[root@ip-172-31-16-48 repofiles]# mysql
bash: mysql: command not found
[root@ip-172-31-16-48 repofiles]# ^C
[root@ip-172-31-16-48 repofiles]# rpm -qa | grep mysql-server
[root@ip-172-31-16-48 repofiles]# rpm -qa | grep mysql
mysql80-community-release-el6-1.noarch
mysql-libs-5.1.73-8.el6_8.x86_64
[root@ip-172-31-16-48 repofiles]# mysql -V
bash: mysql: command not found
[root@ip-172-31-16-48 repofiles]# mysql
bash: mysql: command not found
[root@ip-172-31-16-48 repofiles]# pwd
/repofiles
[root@ip-172-31-16-48 repofiles]# cat ^C
[root@ip-172-31-16-48 repofiles]# ll /etc/yum.repos.d/
total 40
-rw-r--r-- 1 root root 1991 May 18  2016 CentOS-Base.repo
-rw-r--r-- 1 root root  647 May 18  2016 CentOS-Debuginfo.repo
-rw-r--r-- 1 root root  289 May 18  2016 CentOS-fasttrack.repo
-rw-r--r-- 1 root root  630 May 18  2016 CentOS-Media.repo
-rw-r--r-- 1 root root 6259 May 18  2016 CentOS-Vault.repo
-rw-r--r-- 1 root root  957 Feb 14  2013 epel.repo
-rw-r--r-- 1 root root 1056 Nov  4  2012 epel-testing.repo
-rw-r--r-- 1 root root 1862 Feb 22 00:36 mysql-community.repo
-rw-r--r-- 1 root root 1885 Feb 22 00:36 mysql-community-source.repo
[root@ip-172-31-16-48 repofiles]# cat /etc/yum.repos.d/mysql-community.repo
# Enable to use MySQL 5.5
[mysql55-community]
name=MySQL 5.5 Community Server
baseurl=http://repo.mysql.com/yum/mysql-5.5-community/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

# Enable to use MySQL 5.6
[mysql56-community]
name=MySQL 5.6 Community Server
baseurl=http://repo.mysql.com/yum/mysql-5.6-community/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

# Enable to use MySQL 5.7
[mysql57-community]
name=MySQL 5.7 Community Server
baseurl=http://repo.mysql.com/yum/mysql-5.7-community/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql80-community]
name=MySQL 8.0 Community Server
baseurl=http://repo.mysql.com/yum/mysql-8.0-community/el/6/$basearch/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-connectors-community]
name=MySQL Connectors Community
baseurl=http://repo.mysql.com/yum/mysql-connectors-community/el/6/$basearch/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-tools-community]
name=MySQL Tools Community
baseurl=http://repo.mysql.com/yum/mysql-tools-community/el/6/$basearch/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-tools-preview]
name=MySQL Tools Preview
baseurl=http://repo.mysql.com/yum/mysql-tools-preview/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:/etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-cluster-7.5-community]
name=MySQL Cluster 7.5 Community
baseurl=http://repo.mysql.com/yum/mysql-cluster-7.5-community/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-cluster-7.6-community]
name=MySQL Cluster 7.6 Community
baseurl=http://repo.mysql.com/yum/mysql-cluster-7.6-community/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
[root@ip-172-31-16-48 repofiles]# cat /etc/redhat-release
CentOS release 6.8 (Final)
[root@ip-172-31-16-48 repofiles]#
[root@ip-172-31-16-48 repofiles]# yum list mysql-server
Loaded plugins: fastestmirror, security
Loading mirror speeds from cached hostfile
 * base: centos.usonyx.net
 * extras: centos.usonyx.net
 * updates: centos.usonyx.net
mysql-connectors-community                                 | 2.5 kB     00:00
mysql-connectors-community/primary_db                      |  20 kB     00:00
mysql-tools-community                                      | 2.5 kB     00:00
mysql-tools-community/primary_db                           |  41 kB     00:00
mysql80-community                                          | 2.5 kB     00:00
mysql80-community/primary_db                               |  17 kB     00:00
Available Packages
mysql-server.x86_64                      5.1.73-8.el6_8                       base
[root@ip-172-31-16-48 repofiles]# vim /etc/yum.repos.d/mysql-community.repo
[root@ip-172-31-16-48 repofiles]# yum list mysql-server
Loaded plugins: fastestmirror, security
Loading mirror speeds from cached hostfile
 * base: centos.usonyx.net
 * extras: centos.usonyx.net
 * updates: centos.usonyx.net
mysql-connectors-community                                 | 2.5 kB     00:00
mysql-tools-community                                      | 2.5 kB     00:00
mysql80-community                                          | 2.5 kB     00:00
Available Packages
mysql-server.x86_64                      5.1.73-8.el6_8                       base
[root@ip-172-31-16-48 repofiles]# yum clean all
Loaded plugins: fastestmirror, security
Cleaning repos: base extras mysql-connectors-community mysql-tools-community
              : mysql80-community updates
Cleaning up Everything
Cleaning up list of fastest mirrors
[root@ip-172-31-16-48 repofiles]# yum list mysql-server
Loaded plugins: fastestmirror, security
Determining fastest mirrors
 * base: mirror.0x.sg
 * extras: mirror.0x.sg
 * updates: mirror.0x.sg
base                                                       | 3.7 kB     00:00
base/primary_db                                            | 4.7 MB     00:00
extras                                                     | 3.4 kB     00:00
extras/primary_db                                          |  30 kB     00:00
mysql-connectors-community                                 | 2.5 kB     00:00
mysql-connectors-community/primary_db                      |  20 kB     00:00
mysql-tools-community                                      | 2.5 kB     00:00
mysql-tools-community/primary_db                           |  41 kB     00:00
mysql80-community                                          | 2.5 kB     00:00
mysql80-community/primary_db                               |  17 kB     00:00
updates                                                    | 3.4 kB     00:00
updates/primary_db                                         | 7.5 MB     00:00
Available Packages
mysql-server.x86_64                      5.1.73-8.el6_8                       base
[root@ip-172-31-16-48 repofiles]# yum list all | grep -i mysql
mysql-libs.x86_64                           5.1.73-8.el6_8              @updates
mysql80-community-release.noarch            el6-1                       @/mysql80-                                                                                      community-release-el6-1.noarch
MySQL-python.x86_64                         1.2.3-0.3.c1.1.el6          base
apr-util-mysql.x86_64                       1.3.9-3.el6_0.1             base
bacula-director-mysql.x86_64                5.0.0-13.el6                base
bacula-storage-mysql.x86_64                 5.0.0-13.el6                base
dovecot-mysql.x86_64                        1:2.0.9-22.el6              base
freeradius-mysql.x86_64                     2.2.6-7.el6_9               updates
libdbi-dbd-mysql.x86_64                     0.8.3-5.1.el6               base
mod_auth_mysql.x86_64                       1:3.0.0-11.el6_0.1          base
mysql.x86_64                                5.1.73-8.el6_8              base
mysql-bench.x86_64                          5.1.73-8.el6_8              base
mysql-community-client.i686                 8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-client.x86_64               8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-common.i686                 8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-common.x86_64               8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-devel.i686                  8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-devel.x86_64                8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-libs.i686                   8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-libs.x86_64                 8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-libs-compat.i686            8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-libs-compat.x86_64          8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-release.noarch              el6-5                       mysql-conn                                                                                      ectors-community
mysql-community-server.x86_64               8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-community-test.x86_64                 8.0.11-1.el6                mysql80-co                                                                                      mmunity
mysql-connector-java.noarch                 1:5.1.17-6.el6              base
mysql-connector-odbc.x86_64                 8.0.11-1.el6                mysql-conn                                                                                      ectors-community
mysql-connector-odbc-debuginfo.x86_64       8.0.11-1.el6                mysql-conn                                                                                      ectors-community
mysql-connector-odbc-setup.x86_64           8.0.11-1.el6                mysql-conn                                                                                      ectors-community
mysql-connector-python.noarch               2.0.4-1.el6                 mysql-conn                                                                                      ectors-community
mysql-connector-python.x86_64               2.1.7-1.el6                 mysql-conn                                                                                      ectors-community
mysql-connector-python-cext.x86_64          2.1.7-1.el6                 mysql-conn                                                                                      ectors-community
mysql-connector-python-debuginfo.x86_64     2.1.7-1.el6                 mysql-conn                                                                                      ectors-community
mysql-devel.i686                            5.1.73-8.el6_8              base
mysql-devel.x86_64                          5.1.73-8.el6_8              base
mysql-embedded.i686                         5.1.73-8.el6_8              base
mysql-embedded.x86_64                       5.1.73-8.el6_8              base
mysql-embedded-devel.i686                   5.1.73-8.el6_8              base
mysql-embedded-devel.x86_64                 5.1.73-8.el6_8              base
mysql-libs.i686                             5.1.73-8.el6_8              base
mysql-ref-manual-8.0-en-html-chapter.noarch 1-20180420                  mysql80-co                                                                                      mmunity
mysql-ref-manual-8.0-en-pdf.noarch          1-20180420                  mysql80-co                                                                                      mmunity
mysql-router.x86_64                         8.0.11-1.el6                mysql-tool                                                                                      s-community
mysql-router-debuginfo.x86_64               8.0.11-1.el6                mysql-tool                                                                                      s-community
mysql-server.x86_64                         5.1.73-8.el6_8              base
mysql-shell.x86_64                          8.0.11-1.el6                mysql-tool                                                                                      s-community
mysql-shell-debuginfo.x86_64                8.0.11-1.el6                mysql-tool                                                                                      s-community
mysql-test.x86_64                           5.1.73-8.el6_8              base
mysql-utilities.noarch                      1.6.5-1.el6                 mysql-tool                                                                                      s-community
mysql-utilities-extra.noarch                1.5.6-1.el6                 mysql-tool                                                                                      s-community
mysql-workbench-community.x86_64            6.3.8-1.el6                 mysql-tool                                                                                      s-community
mysql-workbench-community-debuginfo.x86_64  6.3.8-1.el6                 mysql-tool                                                                                      s-community
pcp-pmda-mysql.x86_64                       3.10.9-9.el6                base
perl-DBD-MySQL.x86_64                       4.013-3.el6                 base
php-mysql.x86_64                            5.3.3-49.el6                base
qt-mysql.i686                               1:4.6.2-28.el6_5            base
qt-mysql.x86_64                             1:4.6.2-28.el6_5            base
qt3-MySQL.i686                              3.3.8b-30.el6               base
qt3-MySQL.x86_64                            3.3.8b-30.el6               base
rsyslog-mysql.x86_64                        5.8.10-10.el6_6             base
rsyslog7-mysql.x86_64                       7.4.10-7.el6                base
[root@ip-172-31-16-48 repofiles]# yum list all | grep -i mysql |less
[root@ip-172-31-16-48 repofiles]# cd /etc/yum.repos.d/
[root@ip-172-31-16-48 yum.repos.d]#
[root@ip-172-31-16-48 yum.repos.d]# ll
total 40
-rw-r--r-- 1 root root 1991 May 18  2016 CentOS-Base.repo
-rw-r--r-- 1 root root  647 May 18  2016 CentOS-Debuginfo.repo
-rw-r--r-- 1 root root  289 May 18  2016 CentOS-fasttrack.repo
-rw-r--r-- 1 root root  630 May 18  2016 CentOS-Media.repo
-rw-r--r-- 1 root root 6259 May 18  2016 CentOS-Vault.repo
-rw-r--r-- 1 root root  957 Feb 14  2013 epel.repo
-rw-r--r-- 1 root root 1056 Nov  4  2012 epel-testing.repo
-rw-r--r-- 1 root root 1873 May 14 01:05 mysql-community.repo
-rw-r--r-- 1 root root 1885 Feb 22 00:36 mysql-community-source.repo
[root@ip-172-31-16-48 yum.repos.d]# cat mysql-community.repo
# Enable to use MySQL 5.5
[mysql55-community]
name=MySQL 5.5 Community Server
baseurl=http://repo.mysql.com/yum/mysql-5.5-community/el/6/$basearch/
enabled=0
gpgcheck=1
priority=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

# Enable to use MySQL 5.6
[mysql56-community]
name=MySQL 5.6 Community Server
baseurl=http://repo.mysql.com/yum/mysql-5.6-community/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

# Enable to use MySQL 5.7
[mysql57-community]
name=MySQL 5.7 Community Server
baseurl=http://repo.mysql.com/yum/mysql-5.7-community/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql80-community]
name=MySQL 8.0 Community Server
baseurl=http://repo.mysql.com/yum/mysql-8.0-community/el/6/$basearch/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-connectors-community]
name=MySQL Connectors Community
baseurl=http://repo.mysql.com/yum/mysql-connectors-community/el/6/$basearch/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-tools-community]
name=MySQL Tools Community
baseurl=http://repo.mysql.com/yum/mysql-tools-community/el/6/$basearch/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-tools-preview]
name=MySQL Tools Preview
baseurl=http://repo.mysql.com/yum/mysql-tools-preview/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:/etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-cluster-7.5-community]
name=MySQL Cluster 7.5 Community
baseurl=http://repo.mysql.com/yum/mysql-cluster-7.5-community/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[mysql-cluster-7.6-community]
name=MySQL Cluster 7.6 Community
baseurl=http://repo.mysql.com/yum/mysql-cluster-7.6-community/el/6/$basearch/
enabled=0
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
[root@ip-172-31-16-48 yum.repos.d]# vim mysql-community.repo
[root@ip-172-31-16-48 yum.repos.d]# yum clean all
Loaded plugins: fastestmirror, security
Cleaning repos: base extras mysql-connectors-community mysql-tools-community mysql55-community updates
Cleaning up Everything
Cleaning up list of fastest mirrors
[root@ip-172-31-16-48 yum.repos.d]# yum repolist
Loaded plugins: fastestmirror, security
Determining fastest mirrors
 * base: mirror.0x.sg
 * extras: mirror.0x.sg
 * updates: mirror.0x.sg
base                                                                                                                                             | 3.7 kB     00:00
base/primary_db                                                                                                                                  | 4.7 MB     00:00
extras                                                                                                                                           | 3.4 kB     00:00
extras/primary_db                                                                                                                                |  30 kB     00:00
mysql-connectors-community                                                                                                                       | 2.5 kB     00:00
mysql-connectors-community/primary_db                                                                                                            |  20 kB     00:00
mysql-tools-community                                                                                                                            | 2.5 kB     00:00
mysql-tools-community/primary_db                                                                                                                 |  41 kB     00:00
mysql55-community                                                                                                                                | 2.5 kB     00:00
mysql55-community/primary_db                                                                                                                     | 206 kB     00:00
updates                                                                                                                                          | 3.4 kB     00:00
updates/primary_db                                                                                                                               | 7.5 MB     00:00
repo id                                                                          repo name                                                                        status
base                                                                             CentOS-6 - Base                                                                  6,706
extras                                                                           CentOS-6 - Extras                                                                   53
mysql-connectors-community                                                       MySQL Connectors Community                                                          49
mysql-tools-community                                                            MySQL Tools Community                                                               61
mysql55-community                                                                MySQL 5.5 Community Server                                                         449
updates                                                                          CentOS-6 - Updates                                                               1,248
repolist: 8,566
[root@ip-172-31-16-48 yum.repos.d]# yum list mysql-community-server
Loaded plugins: fastestmirror, security
Loading mirror speeds from cached hostfile
 * base: mirror.0x.sg
 * extras: mirror.0x.sg
 * updates: mirror.0x.sg
Available Packages
mysql-community-server.x86_64                                                       5.5.60-2.el6                                                       mysql55-community
[root@ip-172-31-16-48 yum.repos.d]# yum -y localinstall mysql-community-server.x86_64
Loaded plugins: fastestmirror, security
Setting up Local Package Process
Skipping: mysql-community-server.x86_64, filename does not end in .rpm.
Nothing to do
[root@ip-172-31-16-48 yum.repos.d]# yum -y localinstall mysql-community-server
Loaded plugins: fastestmirror, security
Setting up Local Package Process
Skipping: mysql-community-server, filename does not end in .rpm.
Nothing to do
[root@ip-172-31-16-48 yum.repos.d]# yum -y localinstall mysql155-community
Loaded plugins: fastestmirror, security
Setting up Local Package Process
Skipping: mysql155-community, filename does not end in .rpm.
Nothing to do
[root@ip-172-31-16-48 yum.repos.d]# yum install mysql-community-server.x86_64
Loaded plugins: fastestmirror, security
Setting up Install Process
Loading mirror speeds from cached hostfile
 * base: mirror.0x.sg
 * extras: mirror.0x.sg
 * updates: mirror.0x.sg
Resolving Dependencies
--> Running transaction check
---> Package mysql-community-server.x86_64 0:5.5.60-2.el6 will be installed
--> Processing Dependency: mysql-community-common(x86-64) = 5.5.60-2.el6 for package: mysql-community-server-5.5.60-2.el6.x86_64
--> Processing Dependency: mysql-community-client(x86-64) >= 5.5.8 for package: mysql-community-server-5.5.60-2.el6.x86_64
--> Processing Dependency: perl(DBI) for package: mysql-community-server-5.5.60-2.el6.x86_64
--> Running transaction check
---> Package mysql-community-client.x86_64 0:5.5.60-2.el6 will be installed
--> Processing Dependency: mysql-community-libs(x86-64) >= 5.5.8 for package: mysql-community-client-5.5.60-2.el6.x86_64
---> Package mysql-community-common.x86_64 0:5.5.60-2.el6 will be installed
---> Package perl-DBI.x86_64 0:1.609-4.el6 will be installed
--> Running transaction check
---> Package mysql-community-libs.x86_64 0:5.5.60-2.el6 will be obsoleting
---> Package mysql-libs.x86_64 0:5.1.73-8.el6_8 will be obsoleted
--> Processing Dependency: libmysqlclient.so.16()(64bit) for package: 2:postfix-2.6.6-6.el6_7.1.x86_64
--> Processing Dependency: libmysqlclient.so.16(libmysqlclient_16)(64bit) for package: 2:postfix-2.6.6-6.el6_7.1.x86_64
--> Running transaction check
---> Package mysql-community-libs-compat.x86_64 0:5.5.60-2.el6 will be obsoleting
---> Package postfix.x86_64 2:2.6.6-6.el6_7.1 will be updated
---> Package postfix.x86_64 2:2.6.6-8.el6 will be an update
--> Finished Dependency Resolution

Dependencies Resolved

========================================================================================================================================================================
 Package                                            Arch                          Version                                Repository                                Size
========================================================================================================================================================================
Installing:
 mysql-community-libs                               x86_64                        5.5.60-2.el6                           mysql55-community                        1.7 M
     replacing  mysql-libs.x86_64 5.1.73-8.el6_8
 mysql-community-libs-compat                        x86_64                        5.5.60-2.el6                           mysql55-community                        1.6 M
     replacing  mysql-libs.x86_64 5.1.73-8.el6_8
 mysql-community-server                             x86_64                        5.5.60-2.el6                           mysql55-community                         38 M
Installing for dependencies:
 mysql-community-client                             x86_64                        5.5.60-2.el6                           mysql55-community                         15 M
 mysql-community-common                             x86_64                        5.5.60-2.el6                           mysql55-community                        277 k
 perl-DBI                                           x86_64                        1.609-4.el6                            base                                     705 k
Updating for dependencies:
 postfix                                            x86_64                        2:2.6.6-8.el6                          base                                     2.0 M

Transaction Summary
========================================================================================================================================================================
Install       6 Package(s)
Upgrade       1 Package(s)

Total download size: 59 M
Is this ok [y/N]: y
Downloading Packages:
(1/7): mysql-community-client-5.5.60-2.el6.x86_64.rpm                                                                                            |  15 MB     00:00
(2/7): mysql-community-common-5.5.60-2.el6.x86_64.rpm                                                                                            | 277 kB     00:00
(3/7): mysql-community-libs-5.5.60-2.el6.x86_64.rpm                                                                                              | 1.7 MB     00:00
(4/7): mysql-community-libs-compat-5.5.60-2.el6.x86_64.rpm                                                                                       | 1.6 MB     00:00
(5/7): mysql-community-server-5.5.60-2.el6.x86_64.rpm                                                                                            |  38 MB     00:02
(6/7): perl-DBI-1.609-4.el6.x86_64.rpm                                                                                                           | 705 kB     00:00
(7/7): postfix-2.6.6-8.el6.x86_64.rpm                                                                                                            | 2.0 MB     00:00
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                    16 MB/s |  59 MB     00:03
warning: rpmts_HdrFromFdno: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Retrieving key from file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
Importing GPG key 0x5072E1F5:
 Userid : MySQL Release Engineering <mysql-build@oss.oracle.com>
 Package: mysql80-community-release-el6-1.noarch (@/mysql80-community-release-el6-1.noarch)
 From   : /etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
Is this ok [y/N]: y
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : mysql-community-common-5.5.60-2.el6.x86_64                                                                                                           1/9
  Installing : mysql-community-libs-5.5.60-2.el6.x86_64                                                                                                             2/9
  Installing : mysql-community-client-5.5.60-2.el6.x86_64                                                                                                           3/9
  Installing : mysql-community-libs-compat-5.5.60-2.el6.x86_64                                                                                                      4/9
  Installing : perl-DBI-1.609-4.el6.x86_64                                                                                                                          5/9
  Installing : mysql-community-server-5.5.60-2.el6.x86_64                                                                                                           6/9
  Updating   : 2:postfix-2.6.6-8.el6.x86_64                                                                                                                         7/9
  Cleanup    : 2:postfix-2.6.6-6.el6_7.1.x86_64                                                                                                                     8/9
  Erasing    : mysql-libs-5.1.73-8.el6_8.x86_64                                                                                                                     9/9
  Verifying  : mysql-community-server-5.5.60-2.el6.x86_64                                                                                                           1/9
  Verifying  : mysql-community-libs-5.5.60-2.el6.x86_64                                                                                                             2/9
  Verifying  : mysql-community-client-5.5.60-2.el6.x86_64                                                                                                           3/9
  Verifying  : 2:postfix-2.6.6-8.el6.x86_64                                                                                                                         4/9
  Verifying  : perl-DBI-1.609-4.el6.x86_64                                                                                                                          5/9
  Verifying  : mysql-community-common-5.5.60-2.el6.x86_64                                                                                                           6/9
  Verifying  : mysql-community-libs-compat-5.5.60-2.el6.x86_64                                                                                                      7/9
  Verifying  : 2:postfix-2.6.6-6.el6_7.1.x86_64                                                                                                                     8/9
  Verifying  : mysql-libs-5.1.73-8.el6_8.x86_64                                                                                                                     9/9

Installed:
  mysql-community-libs.x86_64 0:5.5.60-2.el6          mysql-community-libs-compat.x86_64 0:5.5.60-2.el6          mysql-community-server.x86_64 0:5.5.60-2.el6

Dependency Installed:
  mysql-community-client.x86_64 0:5.5.60-2.el6                mysql-community-common.x86_64 0:5.5.60-2.el6                perl-DBI.x86_64 0:1.609-4.el6

Dependency Updated:
  postfix.x86_64 2:2.6.6-8.el6

Replaced:
  mysql-libs.x86_64 0:5.1.73-8.el6_8

Complete!
[root@ip-172-31-16-48 yum.repos.d]# mysql -V
mysql  Ver 14.14 Distrib 5.5.60, for Linux (x86_64) using readline 5.1
[root@ip-172-31-16-48 yum.repos.d]# yum list mysql-connector-java
Loaded plugins: fastestmirror, security
Loading mirror speeds from cached hostfile
 * base: mirror.0x.sg
 * extras: mirror.0x.sg
 * updates: mirror.0x.sg
Available Packages
mysql-connector-java.noarch                                                             1:5.1.17-6.el6                                                              base
[root@ip-172-31-16-48 yum.repos.d]# yum -y install mysql-connector-java
Loaded plugins: fastestmirror, security
Setting up Install Process
Loading mirror speeds from cached hostfile
 * base: mirror.0x.sg
 * extras: mirror.0x.sg
 * updates: mirror.0x.sg
Resolving Dependencies
--> Running transaction check
---> Package mysql-connector-java.noarch 1:5.1.17-6.el6 will be installed
--> Processing Dependency: jta >= 1.0 for package: 1:mysql-connector-java-5.1.17-6.el6.noarch
--> Processing Dependency: slf4j for package: 1:mysql-connector-java-5.1.17-6.el6.noarch
--> Running transaction check
---> Package geronimo-specs-compat.noarch 0:1.0-3.5.M2.el6 will be installed
--> Processing Dependency: geronimo-specs = 1.0-3.5.M2.el6 for package: geronimo-specs-compat-1.0-3.5.M2.el6.noarch
---> Package slf4j.noarch 0:1.5.8-8.el6 will be installed
--> Running transaction check
---> Package geronimo-specs.noarch 0:1.0-3.5.M2.el6 will be installed
--> Processing Dependency: mx4j >= 2.0.1 for package: geronimo-specs-1.0-3.5.M2.el6.noarch
--> Processing Dependency: apache-tomcat-apis for package: geronimo-specs-1.0-3.5.M2.el6.noarch
--> Running transaction check
---> Package apache-tomcat-apis.noarch 0:0.1-1.el6 will be installed
---> Package mx4j.noarch 1:3.0.1-9.13.el6 will be installed
--> Processing Dependency: log4j >= 1.2.7 for package: 1:mx4j-3.0.1-9.13.el6.noarch
--> Processing Dependency: javamail >= 1.2-5jpp for package: 1:mx4j-3.0.1-9.13.el6.noarch
--> Processing Dependency: jakarta-commons-logging >= 1.0.1 for package: 1:mx4j-3.0.1-9.13.el6.noarch
--> Processing Dependency: bcel >= 5.0 for package: 1:mx4j-3.0.1-9.13.el6.noarch
--> Processing Dependency: axis >= 1.1 for package: 1:mx4j-3.0.1-9.13.el6.noarch
--> Processing Dependency: xml-commons-resolver for package: 1:mx4j-3.0.1-9.13.el6.noarch
--> Processing Dependency: xml-commons-apis for package: 1:mx4j-3.0.1-9.13.el6.noarch
--> Processing Dependency: xml-commons for package: 1:mx4j-3.0.1-9.13.el6.noarch
--> Processing Dependency: jaf for package: 1:mx4j-3.0.1-9.13.el6.noarch
--> Running transaction check
---> Package axis.noarch 0:1.2.1-7.5.el6_5 will be installed
--> Processing Dependency: wsdl4j for package: axis-1.2.1-7.5.el6_5.noarch
--> Processing Dependency: jaxp_parser_impl for package: axis-1.2.1-7.5.el6_5.noarch
--> Processing Dependency: jakarta-commons-httpclient for package: axis-1.2.1-7.5.el6_5.noarch
--> Processing Dependency: jakarta-commons-discovery for package: axis-1.2.1-7.5.el6_5.noarch
---> Package bcel.x86_64 0:5.2-7.2.el6 will be installed
--> Processing Dependency: regexp for package: bcel-5.2-7.2.el6.x86_64
--> Processing Dependency: libgcj_bc.so.1()(64bit) for package: bcel-5.2-7.2.el6.x86_64
---> Package classpathx-jaf.x86_64 0:1.0-15.4.el6 will be installed
---> Package classpathx-mail.noarch 0:1.1.1-9.4.el6 will be installed
---> Package jakarta-commons-logging.noarch 0:1.0.4-10.el6 will be installed
---> Package log4j.x86_64 0:1.2.14-6.4.el6 will be installed
---> Package xml-commons-apis.x86_64 0:1.3.04-3.6.el6 will be installed
---> Package xml-commons-resolver.x86_64 0:1.1-4.18.el6 will be installed
--> Running transaction check
---> Package jakarta-commons-discovery.noarch 1:0.4-5.4.el6 will be installed
---> Package jakarta-commons-httpclient.x86_64 1:3.1-0.9.el6_5 will be installed
---> Package java-1.5.0-gcj.x86_64 0:1.5.0.0-29.1.el6 will be installed
base/filelists_db                                                                                                                                | 6.4 MB     00:00
extras/filelists_db                                                                                                                              |  26 kB     00:00
mysql-connectors-community/filelists_db                                                                                                          |  25 kB     00:00
mysql-tools-community/filelists_db                                                                                                               | 116 kB     00:00
mysql55-community/filelists_db                                                                                                                   | 338 kB     00:00
updates/filelists_db                                                                                                                             | 4.7 MB     00:00
--> Processing Dependency: sinjdoc for package: java-1.5.0-gcj-1.5.0.0-29.1.el6.x86_64
---> Package libgcj.x86_64 0:4.4.7-18.el6_9.2 will be installed
--> Processing Dependency: libart_lgpl >= 2.1.0 for package: libgcj-4.4.7-18.el6_9.2.x86_64
---> Package regexp.x86_64 0:1.5-4.4.el6 will be installed
---> Package wsdl4j.noarch 0:1.5.2-7.8.el6 will be installed
--> Running transaction check
---> Package libart_lgpl.x86_64 0:2.3.20-5.1.el6 will be installed
---> Package sinjdoc.x86_64 0:0.5-9.1.el6 will be installed
--> Processing Dependency: java_cup >= 0.10 for package: sinjdoc-0.5-9.1.el6.x86_64
--> Running transaction check
---> Package java_cup.x86_64 1:0.10k-5.el6 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

========================================================================================================================================================================
 Package                                             Arch                            Version                                     Repository                        Size
========================================================================================================================================================================
Installing:
 mysql-connector-java                                noarch                          1:5.1.17-6.el6                              base                             1.4 M
Installing for dependencies:
 apache-tomcat-apis                                  noarch                          0.1-1.el6                                   base                             164 k
 axis                                                noarch                          1.2.1-7.5.el6_5                             base                             1.5 M
 bcel                                                x86_64                          5.2-7.2.el6                                 base                             1.4 M
 classpathx-jaf                                      x86_64                          1.0-15.4.el6                                base                             100 k
 classpathx-mail                                     noarch                          1.1.1-9.4.el6                               base                             479 k
 geronimo-specs                                      noarch                          1.0-3.5.M2.el6                              base                             111 k
 geronimo-specs-compat                               noarch                          1.0-3.5.M2.el6                              base                             7.1 k
 jakarta-commons-discovery                           noarch                          1:0.4-5.4.el6                               base                              73 k
 jakarta-commons-httpclient                          x86_64                          1:3.1-0.9.el6_5                             base                             593 k
 jakarta-commons-logging                             noarch                          1.0.4-10.el6                                base                              52 k
 java-1.5.0-gcj                                      x86_64                          1.5.0.0-29.1.el6                            base                             139 k
 java_cup                                            x86_64                          1:0.10k-5.el6                               base                             197 k
 libart_lgpl                                         x86_64                          2.3.20-5.1.el6                              base                              65 k
 libgcj                                              x86_64                          4.4.7-18.el6_9.2                            updates                           19 M
 log4j                                               x86_64                          1.2.14-6.4.el6                              base                             679 k
 mx4j                                                noarch                          1:3.0.1-9.13.el6                            base                             1.1 M
 regexp                                              x86_64                          1.5-4.4.el6                                 base                             105 k
 sinjdoc                                             x86_64                          0.5-9.1.el6                                 base                             705 k
 slf4j                                               noarch                          1.5.8-8.el6                                 base                             131 k
 wsdl4j                                              noarch                          1.5.2-7.8.el6                               base                             157 k
 xml-commons-apis                                    x86_64                          1.3.04-3.6.el6                              base                             439 k
 xml-commons-resolver                                x86_64                          1.1-4.18.el6                                base                             145 k

Transaction Summary
========================================================================================================================================================================
Install      23 Package(s)

Total download size: 28 M
Installed size: 95 M
Downloading Packages:
(1/23): apache-tomcat-apis-0.1-1.el6.noarch.rpm                                                                                                  | 164 kB     00:00
(2/23): axis-1.2.1-7.5.el6_5.noarch.rpm                                                                                                          | 1.5 MB     00:00
(3/23): bcel-5.2-7.2.el6.x86_64.rpm                                                                                                              | 1.4 MB     00:00
(4/23): classpathx-jaf-1.0-15.4.el6.x86_64.rpm                                                                                                   | 100 kB     00:00
(5/23): classpathx-mail-1.1.1-9.4.el6.noarch.rpm                                                                                                 | 479 kB     00:00
(6/23): geronimo-specs-1.0-3.5.M2.el6.noarch.rpm                                                                                                 | 111 kB     00:00
(7/23): geronimo-specs-compat-1.0-3.5.M2.el6.noarch.rpm                                                                                          | 7.1 kB     00:00
(8/23): jakarta-commons-discovery-0.4-5.4.el6.noarch.rpm                                                                                         |  73 kB     00:00
(9/23): jakarta-commons-httpclient-3.1-0.9.el6_5.x86_64.rpm                                                                                      | 593 kB     00:00
(10/23): jakarta-commons-logging-1.0.4-10.el6.noarch.rpm                                                                                         |  52 kB     00:00
(11/23): java-1.5.0-gcj-1.5.0.0-29.1.el6.x86_64.rpm                                                                                              | 139 kB     00:00
(12/23): java_cup-0.10k-5.el6.x86_64.rpm                                                                                                         | 197 kB     00:00
(13/23): libart_lgpl-2.3.20-5.1.el6.x86_64.rpm                                                                                                   |  65 kB     00:00
(14/23): libgcj-4.4.7-18.el6_9.2.x86_64.rpm                                                                                                      |  19 MB     00:00
(15/23): log4j-1.2.14-6.4.el6.x86_64.rpm                                                                                                         | 679 kB     00:00
(16/23): mx4j-3.0.1-9.13.el6.noarch.rpm                                                                                                          | 1.1 MB     00:00
(17/23): mysql-connector-java-5.1.17-6.el6.noarch.rpm                                                                                            | 1.4 MB     00:00
(18/23): regexp-1.5-4.4.el6.x86_64.rpm                                                                                                           | 105 kB     00:00
(19/23): sinjdoc-0.5-9.1.el6.x86_64.rpm                                                                                                          | 705 kB     00:00
(20/23): slf4j-1.5.8-8.el6.noarch.rpm                                                                                                            | 131 kB     00:00
(21/23): wsdl4j-1.5.2-7.8.el6.noarch.rpm                                                                                                         | 157 kB     00:00
(22/23): xml-commons-apis-1.3.04-3.6.el6.x86_64.rpm                                                                                              | 439 kB     00:00
(23/23): xml-commons-resolver-1.1-4.18.el6.x86_64.rpm                                                                                            | 145 kB     00:00
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                    15 MB/s |  28 MB     00:01
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : jakarta-commons-logging-1.0.4-10.el6.noarch                                                                                                         1/23
  Installing : 1:jakarta-commons-discovery-0.4-5.4.el6.noarch                                                                                                      2/23
  Installing : apache-tomcat-apis-0.1-1.el6.noarch                                                                                                                 3/23
  Installing : libart_lgpl-2.3.20-5.1.el6.x86_64                                                                                                                   4/23
  Installing : libgcj-4.4.7-18.el6_9.2.x86_64                                                                                                                      5/23
  Installing : java-1.5.0-gcj-1.5.0.0-29.1.el6.x86_64                                                                                                              6/23
  Installing : 1:java_cup-0.10k-5.el6.x86_64                                                                                                                       7/23
  Installing : sinjdoc-0.5-9.1.el6.x86_64                                                                                                                          8/23
  Installing : classpathx-jaf-1.0-15.4.el6.x86_64                                                                                                                  9/23
  Installing : xml-commons-apis-1.3.04-3.6.el6.x86_64                                                                                                             10/23
  Installing : log4j-1.2.14-6.4.el6.x86_64                                                                                                                        11/23
  Installing : classpathx-mail-1.1.1-9.4.el6.noarch                                                                                                               12/23
  Installing : xml-commons-resolver-1.1-4.18.el6.x86_64                                                                                                           13/23
  Installing : 1:jakarta-commons-httpclient-3.1-0.9.el6_5.x86_64                                                                                                  14/23
  Installing : regexp-1.5-4.4.el6.x86_64                                                                                                                          15/23
  Installing : bcel-5.2-7.2.el6.x86_64                                                                                                                            16/23
  Installing : wsdl4j-1.5.2-7.8.el6.noarch                                                                                                                        17/23
  Installing : axis-1.2.1-7.5.el6_5.noarch                                                                                                                        18/23
  Installing : 1:mx4j-3.0.1-9.13.el6.noarch                                                                                                                       19/23
  Installing : geronimo-specs-1.0-3.5.M2.el6.noarch                                                                                                               20/23
  Installing : geronimo-specs-compat-1.0-3.5.M2.el6.noarch                                                                                                        21/23
  Installing : slf4j-1.5.8-8.el6.noarch                                                                                                                           22/23
  Installing : 1:mysql-connector-java-5.1.17-6.el6.noarch                                                                                                         23/23
  Verifying  : geronimo-specs-1.0-3.5.M2.el6.noarch                                                                                                                1/23
  Verifying  : axis-1.2.1-7.5.el6_5.noarch                                                                                                                         2/23
  Verifying  : classpathx-mail-1.1.1-9.4.el6.noarch                                                                                                                3/23
  Verifying  : 1:jakarta-commons-discovery-0.4-5.4.el6.noarch                                                                                                      4/23
  Verifying  : 1:java_cup-0.10k-5.el6.x86_64                                                                                                                       5/23
  Verifying  : libart_lgpl-2.3.20-5.1.el6.x86_64                                                                                                                   6/23
  Verifying  : sinjdoc-0.5-9.1.el6.x86_64                                                                                                                          7/23
  Verifying  : bcel-5.2-7.2.el6.x86_64                                                                                                                             8/23
  Verifying  : 1:jakarta-commons-httpclient-3.1-0.9.el6_5.x86_64                                                                                                   9/23
  Verifying  : regexp-1.5-4.4.el6.x86_64                                                                                                                          10/23
  Verifying  : jakarta-commons-logging-1.0.4-10.el6.noarch                                                                                                        11/23
  Verifying  : wsdl4j-1.5.2-7.8.el6.noarch                                                                                                                        12/23
  Verifying  : log4j-1.2.14-6.4.el6.x86_64                                                                                                                        13/23
  Verifying  : 1:mx4j-3.0.1-9.13.el6.noarch                                                                                                                       14/23
  Verifying  : classpathx-jaf-1.0-15.4.el6.x86_64                                                                                                                 15/23
  Verifying  : libgcj-4.4.7-18.el6_9.2.x86_64                                                                                                                     16/23
  Verifying  : java-1.5.0-gcj-1.5.0.0-29.1.el6.x86_64                                                                                                             17/23
  Verifying  : slf4j-1.5.8-8.el6.noarch                                                                                                                           18/23
  Verifying  : xml-commons-apis-1.3.04-3.6.el6.x86_64                                                                                                             19/23
  Verifying  : geronimo-specs-compat-1.0-3.5.M2.el6.noarch                                                                                                        20/23
  Verifying  : 1:mysql-connector-java-5.1.17-6.el6.noarch                                                                                                         21/23
  Verifying  : xml-commons-resolver-1.1-4.18.el6.x86_64                                                                                                           22/23
  Verifying  : apache-tomcat-apis-0.1-1.el6.noarch                                                                                                                23/23

Installed:
  mysql-connector-java.noarch 1:5.1.17-6.el6

Dependency Installed:
  apache-tomcat-apis.noarch 0:0.1-1.el6                 axis.noarch 0:1.2.1-7.5.el6_5                          bcel.x86_64 0:5.2-7.2.el6
  classpathx-jaf.x86_64 0:1.0-15.4.el6                  classpathx-mail.noarch 0:1.1.1-9.4.el6                 geronimo-specs.noarch 0:1.0-3.5.M2.el6
  geronimo-specs-compat.noarch 0:1.0-3.5.M2.el6         jakarta-commons-discovery.noarch 1:0.4-5.4.el6         jakarta-commons-httpclient.x86_64 1:3.1-0.9.el6_5
  jakarta-commons-logging.noarch 0:1.0.4-10.el6         java-1.5.0-gcj.x86_64 0:1.5.0.0-29.1.el6               java_cup.x86_64 1:0.10k-5.el6
  libart_lgpl.x86_64 0:2.3.20-5.1.el6                   libgcj.x86_64 0:4.4.7-18.el6_9.2                       log4j.x86_64 0:1.2.14-6.4.el6
  mx4j.noarch 1:3.0.1-9.13.el6                          regexp.x86_64 0:1.5-4.4.el6                            sinjdoc.x86_64 0:0.5-9.1.el6
  slf4j.noarch 0:1.5.8-8.el6                            wsdl4j.noarch 0:1.5.2-7.8.el6                          xml-commons-apis.x86_64 0:1.3.04-3.6.el6
  xml-commons-resolver.x86_64 0:1.1-4.18.el6

Complete!

###########################
### Configuring MySQL #####
###########################

[root@ip-172-31-16-48 yum.repos.d]# service mysqld status
mysqld is stopped
[root@ip-172-31-16-48 yum.repos.d]# service mysqld staart
Usage: /etc/init.d/mysqld {start|stop|status|restart|condrestart|try-restart|reload|force-reload}
[root@ip-172-31-16-48 yum.repos.d]# service mysqld start
Initializing MySQL database:  180514  1:27:04 [Note] Ignoring --secure-file-priv value as server is running with --bootstrap.
180514  1:27:04 [Note] /usr/sbin/mysqld (mysqld 5.5.60) starting as process 8148 ...
180514  1:27:05 [Note] Ignoring --secure-file-priv value as server is running with --bootstrap.
180514  1:27:05 [Note] /usr/sbin/mysqld (mysqld 5.5.60) starting as process 8155 ...

PLEASE REMEMBER TO SET A PASSWORD FOR THE MySQL root USER !
To do so, start the server, then issue the following commands:

/usr/bin/mysqladmin -u root password 'new-password'
/usr/bin/mysqladmin -u root -h ip-172-31-16-48 password 'new-password'

Alternatively you can run:
/usr/bin/mysql_secure_installation

which will also give you the option of removing the test
databases and anonymous user created by default.  This is
strongly recommended for production servers.

See the manual for more instructions.

Please report any problems at http://bugs.mysql.com/

                                                           [  OK  ]
Starting mysqld:                                           [  OK  ]
[root@ip-172-31-16-48 yum.repos.d]#

###############

[root@ip-172-31-16-48 yum.repos.d]# sudo /usr/bin/mysql_secure_installation




NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MySQL
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!


In order to log into MySQL to secure it, we'll need the current
password for the root user.  If you've just installed MySQL, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none):
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MySQL
root user without the proper authorisation.

Set root password? [Y/n] xQc42u75
Set root password? [Y/n] xQc42u75
Set root password? [Y/n] y
New password:
Re-enter new password:
Password updated successfully!
Reloading privilege tables..
 ... Success!


By default, a MySQL installation has an anonymous user, allowing anyone
to log into MySQL without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] n
 ... skipping.

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] y
 ... Success!

By default, MySQL comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] y
 ... Success!

Cleaning up...



All done!  If you've completed all of the above steps, your MySQL
installation should now be secure.

Thanks for using MySQL!


[root@ip-172-31-16-48 yum.repos.d]# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 5.5.60 MySQL Community Server (GPL)

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>

[root@ip-172-31-16-48 yum.repos.d]# yum list cloudera-manager.repo
Loaded plugins: fastestmirror, security
Loading mirror speeds from cached hostfile
 * base: mirror.0x.sg
 * extras: mirror.0x.sg
 * updates: mirror.0x.sg
Error: No matching Packages to list
[root@ip-172-31-16-48 yum.repos.d]# yum install | grep cloudera-manager
Error: Need to pass a list of pkgs to install
[root@ip-172-31-16-48 yum.repos.d]# cd
[root@ip-172-31-16-48 ~]# yum list all | grep -i openjdk
java-1.6.0-openjdk.x86_64                   1:1.6.0.41-1.13.13.1.el6_8  @updates
java-1.6.0-openjdk-demo.x86_64              1:1.6.0.41-1.13.13.1.el6_8  base
java-1.6.0-openjdk-devel.x86_64             1:1.6.0.41-1.13.13.1.el6_8  base
java-1.6.0-openjdk-javadoc.x86_64           1:1.6.0.41-1.13.13.1.el6_8  base
java-1.6.0-openjdk-src.x86_64               1:1.6.0.41-1.13.13.1.el6_8  base
java-1.7.0-openjdk.x86_64                   1:1.7.0.181-2.6.14.1.el6_9  updates
java-1.7.0-openjdk-demo.x86_64              1:1.7.0.181-2.6.14.1.el6_9  updates
java-1.7.0-openjdk-devel.x86_64             1:1.7.0.181-2.6.14.1.el6_9  updates
java-1.7.0-openjdk-javadoc.noarch           1:1.7.0.181-2.6.14.1.el6_9  updates
java-1.7.0-openjdk-src.x86_64               1:1.7.0.181-2.6.14.1.el6_9  updates
java-1.8.0-openjdk.x86_64                   1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-debug.x86_64             1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-demo.x86_64              1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-demo-debug.x86_64        1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-devel.x86_64             1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-devel-debug.x86_64       1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-headless.x86_64          1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-headless-debug.x86_64    1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-javadoc.noarch           1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-javadoc-debug.noarch     1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-src.x86_64               1:1.8.0.171-3.b10.el6_9     updates
java-1.8.0-openjdk-src-debug.x86_64         1:1.8.0.171-3.b10.el6_9     updates
[root@ip-172-31-16-48 ~]# yum remove java-1.6.0-openjdk.x86_64
Loaded plugins: fastestmirror, security
Setting up Remove Process
Resolving Dependencies
--> Running transaction check
---> Package java-1.6.0-openjdk.x86_64 1:1.6.0.41-1.13.13.1.el6_8 will be erased
--> Finished Dependency Resolution

Dependencies Resolved

========================================================================================================================================================================
 Package                                    Arch                           Version                                               Repository                        Size
========================================================================================================================================================================
Removing:
 java-1.6.0-openjdk                         x86_64                         1:1.6.0.41-1.13.13.1.el6_8                            @updates                          76 M

Transaction Summary
========================================================================================================================================================================
Remove        1 Package(s)

Installed size: 76 M
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Erasing    : 1:java-1.6.0-openjdk-1.6.0.41-1.13.13.1.el6_8.x86_64                                                                                                 1/1
  Verifying  : 1:java-1.6.0-openjdk-1.6.0.41-1.13.13.1.el6_8.x86_64                                                                                                 1/1

Removed:
  java-1.6.0-openjdk.x86_64 1:1.6.0.41-1.13.13.1.el6_8

Complete!
[root@ip-172-31-16-48 ~]#
[root@ip-172-31-16-48 ~]# yum list all | grep -i j2sdk
oracle-j2sdk1.7.x86_64                      1.7.0+update67-1            cloudera-manager
[root@ip-172-31-16-48 ~]# yum install oracle-j2sdk1.7.x86_64
Loaded plugins: fastestmirror, security
Setting up Install Process
Loading mirror speeds from cached hostfile
 * base: mirror.0x.sg
 * extras: mirror.0x.sg
 * updates: mirror.0x.sg
Resolving Dependencies
--> Running transaction check
---> Package oracle-j2sdk1.7.x86_64 0:1.7.0+update67-1 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

========================================================================================================================================================================
 Package                                   Arch                             Version                                    Repository                                  Size
========================================================================================================================================================================
Installing:
 oracle-j2sdk1.7                           x86_64                           1.7.0+update67-1                           cloudera-manager                           135 M

Transaction Summary
========================================================================================================================================================================
Install       1 Package(s)

Total download size: 135 M
Installed size: 279 M
Is this ok [y/N]: y
Downloading Packages:
oracle-j2sdk1.7-1.7.0+update67-1.x86_64.rpm                                                                                                      | 135 MB     00:02
warning: rpmts_HdrFromFdno: Header V4 DSA/SHA1 Signature, key ID e8f86acd: NOKEY
Retrieving key from https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/RPM-GPG-KEY-cloudera
Importing GPG key 0xE8F86ACD:
 Userid: "Yum Maintainer <webmaster@cloudera.com>"
 From  : https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/RPM-GPG-KEY-cloudera
Is this ok [y/N]: y
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : oracle-j2sdk1.7-1.7.0+update67-1.x86_64                                                                                                              1/1
  Verifying  : oracle-j2sdk1.7-1.7.0+update67-1.x86_64                                                                                                              1/1

Installed:
  oracle-j2sdk1.7.x86_64 0:1.7.0+update67-1

Complete!
[root@ip-172-31-16-48 ~]# cd /repofiles/
[root@ip-172-31-16-48 repofiles]# ll
total 28
-rw-r--r-- 1 root root 25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.rpm
[root@ip-172-31-16-48 repofiles]# wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz
--2018-05-14 02:00:26--  https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz
Resolving dev.mysql.com... 137.254.60.11
Connecting to dev.mysql.com|137.254.60.11|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://cdn.mysql.com//Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz [following]
--2018-05-14 02:00:27--  https://cdn.mysql.com//Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz
Resolving cdn.mysql.com... 104.116.25.237
Connecting to cdn.mysql.com|104.116.25.237|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4434926 (4.2M) [application/x-tar-gz]
Saving to: “mysql-connector-java-5.1.46.tar.gz”

100%[==============================================================================================================================>] 4,434,926   --.-K/s   in 0.06s

2018-05-14 02:00:27 (73.0 MB/s) - “mysql-connector-java-5.1.46.tar.gz” saved [4434926/4434926]

[root@ip-172-31-16-48 repofiles]# ll
total 4360
-rw-r--r-- 1 root root   25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.rpm
-rw-r--r-- 1 root root 4434926 Feb 26 04:28 mysql-connector-java-5.1.46.tar.gz
[root@ip-172-31-16-48 repofiles]# tar zxvf mysql-connector-java-5.1.46.tar.gz
mysql-connector-java-5.1.46/
mysql-connector-java-5.1.46/src/
mysql-connector-java-5.1.46/src/com/
mysql-connector-java-5.1.46/src/com/mysql/
mysql-connector-java-5.1.46/src/com/mysql/fabric/
mysql-connector-java-5.1.46/src/com/mysql/fabric/hibernate/
mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/
mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/
mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/exceptions/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/c3p0/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/jboss/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/interceptors/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/profiler/
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/
mysql-connector-java-5.1.46/src/demo/
mysql-connector-java-5.1.46/src/demo/fabric/
mysql-connector-java-5.1.46/src/demo/fabric/resources/
mysql-connector-java-5.1.46/src/demo/fabric/resources/com/
mysql-connector-java-5.1.46/src/demo/fabric/resources/com/mysql/
mysql-connector-java-5.1.46/src/demo/fabric/resources/com/mysql/fabric/
mysql-connector-java-5.1.46/src/demo/fabric/resources/com/mysql/fabric/demo/
mysql-connector-java-5.1.46/src/doc/
mysql-connector-java-5.1.46/src/doc/sources/
mysql-connector-java-5.1.46/src/lib/
mysql-connector-java-5.1.46/src/org/
mysql-connector-java-5.1.46/src/org/gjt/
mysql-connector-java-5.1.46/src/org/gjt/mm/
mysql-connector-java-5.1.46/src/org/gjt/mm/mysql/
mysql-connector-java-5.1.46/src/testsuite/
mysql-connector-java-5.1.46/src/testsuite/fabric/
mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/
mysql-connector-java-5.1.46/src/testsuite/perf/
mysql-connector-java-5.1.46/src/testsuite/regression/
mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/
mysql-connector-java-5.1.46/src/testsuite/regression/jdbc42/
mysql-connector-java-5.1.46/src/testsuite/simple/
mysql-connector-java-5.1.46/src/testsuite/simple/jdbc4/
mysql-connector-java-5.1.46/src/testsuite/simple/jdbc42/
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/
mysql-connector-java-5.1.46/CHANGES
mysql-connector-java-5.1.46/COPYING
mysql-connector-java-5.1.46/README
mysql-connector-java-5.1.46/README.txt
mysql-connector-java-5.1.46/build.xml
mysql-connector-java-5.1.46/mysql-connector-java-5.1.46-bin.jar
mysql-connector-java-5.1.46/mysql-connector-java-5.1.46.jar
mysql-connector-java-5.1.46/src/com/mysql/fabric/FabricCommunicationException.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/FabricConnection.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/FabricStateResponse.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/HashShardMapping.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/RangeShardMapping.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/Response.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/Server.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/ServerGroup.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/ServerMode.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/ServerRole.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardIndex.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardMapping.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardMappingFactory.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardTable.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardingType.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/hibernate/FabricMultiTenantConnectionProvider.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/ErrorReportingExceptionInterceptor.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLConnectionProperties.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLConnectionProxy.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLDataSource.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLDriver.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/JDBC4FabricMySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/JDBC4FabricMySQLConnectionProxy.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/AuthenticatedXmlRpcMethodCaller.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/DigestAuthentication.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/InternalXmlRpcMethodCaller.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/ResultSetParser.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/XmlRpcClient.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/XmlRpcMethodCaller.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/Client.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Array.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Data.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Fault.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Member.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/MethodCall.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/MethodResponse.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Param.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Params.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/ResponseParser.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Struct.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Value.java
mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/exceptions/MySQLFabricException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/AbandonedConnectionCleanupThread.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/AssertionFailedException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/AuthenticationPlugin.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/BalanceStrategy.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/BestResponseTimeBalanceStrategy.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Blob.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/BlobFromLocator.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Buffer.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/BufferRow.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ByteArrayRow.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/CacheAdapter.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/CacheAdapterFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/CachedResultSetMetaData.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/CallableStatement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/CharsetMapping.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Charsets.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Clob.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/CommunicationsException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/CompressedInputStream.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Connection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionFeatureNotAvailableException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionGroup.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionGroupManager.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionImpl.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionLifecycleInterceptor.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionProperties.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionPropertiesImpl.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionPropertiesTransform.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Constants.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/DatabaseMetaData.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/DatabaseMetaDataUsingInfoSchema.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/DocsConnectionPropsHelper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Driver.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/EscapeProcessor.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/EscapeProcessorResult.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/EscapeTokenizer.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ExceptionInterceptor.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ExportControlled.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Extension.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/FailoverConnectionProxy.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Field.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/IterateBlock.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42CallableStatement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42Helper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42PreparedStatement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42ResultSet.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42ServerPreparedStatement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42UpdatableResultSet.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4CallableStatement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ClientInfoProvider.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ClientInfoProviderSP.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4CommentClientInfoProvider.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4Connection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4DatabaseMetaData.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4DatabaseMetaDataUsingInfoSchema.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4LoadBalancedMySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4MultiHostMySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4MySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4MysqlSQLXML.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4NClob.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4PreparedStatement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4PreparedStatementHelper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ReplicationMySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ResultSet.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ServerPreparedStatement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4UpdatableResultSet.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/LicenseConfiguration.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalanceExceptionChecker.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalancedAutoCommitInterceptor.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalancedConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalancedConnectionProxy.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalancedMySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/LocalizedErrorMessages.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Messages.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MiniAdmin.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MultiHostConnectionProxy.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MultiHostMySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlDataTruncation.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlDefs.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlErrorNumbers.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlIO.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlParameterMetadata.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlSavepoint.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/NamedPipeSocketFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/NdbLoadBalanceExceptionChecker.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/NetworkResources.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/NoSubInterceptorWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/NonRegisteringDriver.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/NonRegisteringReplicationDriver.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/NotImplemented.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/NotUpdatable.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/OperationNotSupportedException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/OutputStreamWatcher.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/PacketTooBigException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ParameterBindings.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/PerConnectionLRUFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/PerVmServerConfigCacheFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/PingTarget.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/PreparedStatement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ProfilerEventHandlerFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/RandomBalanceStrategy.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReflectiveStatementInterceptorAdapter.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationConnectionGroup.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationConnectionGroupManager.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationConnectionProxy.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationDriver.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationMySQLConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ResultSetImpl.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ResultSetInternalMethods.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ResultSetMetaData.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ResultSetRow.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/RowData.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/RowDataCursor.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/RowDataDynamic.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/RowDataStatic.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/SQLError.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Security.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/SequentialBalanceStrategy.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ServerAffinityStrategy.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/ServerPreparedStatement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/SingleByteCharsetConverter.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/SocketFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/SocketMetadata.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/SocksProxySocketFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/StandardLoadBalanceExceptionChecker.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/StandardSocketFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Statement.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/StatementImpl.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/StatementInterceptor.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/StatementInterceptorV2.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/StreamingNotifiable.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/StringUtils.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/TimeUtil.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/TimeZoneMapping.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/UpdatableResultSet.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Util.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/V1toV2StatementInterceptorAdapter.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/WatchableOutputStream.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/WatchableWriter.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/Wrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/WriterWatcher.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/CachingSha2PasswordPlugin.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/MysqlClearPasswordPlugin.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/MysqlNativePasswordPlugin.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/MysqlOldPasswordPlugin.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/Sha256PasswordPlugin.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/3-0-Compat.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/5-0-Compat.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/clusterBase.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/coldFusion.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/fullDebug.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/maxPerformance.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/solarisMaxPerformance.properties
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/DeadlockTimeoutRollbackMarker.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLDataException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLIntegrityConstraintViolationException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLInvalidAuthorizationSpecException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLNonTransientConnectionException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLNonTransientException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLQueryInterruptedException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLStatementCancelledException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLSyntaxErrorException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLTimeoutException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLTransactionRollbackException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLTransientConnectionException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLTransientException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/CommunicationsException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLDataException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLIntegrityConstraintViolationException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLInvalidAuthorizationSpecException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLNonTransientConnectionException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLNonTransientException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLQueryInterruptedException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLSyntaxErrorException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLTimeoutException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLTransactionRollbackException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLTransientConnectionException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLTransientException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/c3p0/MysqlConnectionTester.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/jboss/ExtendedMysqlExceptionSorter.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/jboss/MysqlValidConnectionChecker.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/interceptors/ResultSetScannerInterceptor.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/interceptors/ServerStatusDiffInterceptor.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/interceptors/SessionAssociationInterceptor.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/CallableStatementWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/ConnectionWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC42CallableStatementWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC42PreparedStatementWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4CallableStatementWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4ConnectionWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4MysqlPooledConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4MysqlXAConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4PreparedStatementWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4StatementWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4SuspendableXAConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlConnectionPoolDataSource.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlDataSource.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlDataSourceFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlPooledConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlXAConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlXADataSource.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlXAException.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlXid.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/PreparedStatementWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/StatementWrapper.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/SuspendableXAConnection.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/WrapperBase.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/LoadBalanceConnectionGroupManager.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/LoadBalanceConnectionGroupManagerMBean.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/ReplicationGroupManager.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/ReplicationGroupManagerMBean.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/Jdk14Logger.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/Log.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/LogFactory.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/LogUtils.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/NullLogger.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/Slf4JLogger.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/StandardLogger.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/profiler/LoggingProfilerEventHandler.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/profiler/ProfilerEvent.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/profiler/ProfilerEventHandler.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/Base64Decoder.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/BaseBugReport.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/ErrorMappingsDocGenerator.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/LRUCache.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/PropertiesDocGenerator.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/ReadAheadInputStream.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/ResultSetUtil.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/ServerController.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/TimezoneDump.java
mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/VersionFSHierarchyMaker.java
mysql-connector-java-5.1.46/src/demo/fabric/Client1_Fabric.java
mysql-connector-java-5.1.46/src/demo/fabric/Employee.java
mysql-connector-java-5.1.46/src/demo/fabric/EmployeesDataSource.java
mysql-connector-java-5.1.46/src/demo/fabric/EmployeesJdbc.java
mysql-connector-java-5.1.46/src/demo/fabric/HibernateFabric.java
mysql-connector-java-5.1.46/src/demo/fabric/resources/com/mysql/fabric/demo/employee.hbm.xml
mysql-connector-java-5.1.46/src/doc/sources/pom.xml
mysql-connector-java-5.1.46/src/lib/c3p0-0.9.1-pre6.jar
mysql-connector-java-5.1.46/src/lib/c3p0-0.9.1-pre6.src.zip
mysql-connector-java-5.1.46/src/lib/jboss-common-jdbc-wrapper-src.jar
mysql-connector-java-5.1.46/src/lib/jboss-common-jdbc-wrapper.jar
mysql-connector-java-5.1.46/src/lib/slf4j-api-1.6.1.jar
mysql-connector-java-5.1.46/src/org/gjt/mm/mysql/Driver.java
mysql-connector-java-5.1.46/src/testsuite/BaseStatementInterceptor.java
mysql-connector-java-5.1.46/src/testsuite/BaseTestCase.java
mysql-connector-java-5.1.46/src/testsuite/UnreliableSocketFactory.java
mysql-connector-java-5.1.46/src/testsuite/fabric/BaseFabricTestCase.java
mysql-connector-java-5.1.46/src/testsuite/fabric/SetupFabricTestsuite.java
mysql-connector-java-5.1.46/src/testsuite/fabric/TestAdminCommands.java
mysql-connector-java-5.1.46/src/testsuite/fabric/TestDumpCommands.java
mysql-connector-java-5.1.46/src/testsuite/fabric/TestResultSetParser.java
mysql-connector-java-5.1.46/src/testsuite/fabric/TestShardMapping.java
mysql-connector-java-5.1.46/src/testsuite/fabric/TestXmlRpcCore.java
mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestBasicConnection.java
mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestFabricMySQLConnectionSharding.java
mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestHABasics.java
mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestHashSharding.java
mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestRegressions.java
mysql-connector-java-5.1.46/src/testsuite/perf/BasePerfTest.java
mysql-connector-java-5.1.46/src/testsuite/perf/LoadStorePerfTest.java
mysql-connector-java-5.1.46/src/testsuite/perf/RetrievalPerfTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/BlobRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/CachedRowsetTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/CallableStatementRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/CharsetRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/ConnectionRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/DataSourceRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/EscapeProcessorRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/MetaDataRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/MicroPerformanceRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/NumbersRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/PooledConnectionRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/ResultSetRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/StatementRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/StressRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/StringRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/SubqueriesRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/SyntaxRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/UtilsRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/ConnectionRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/ExceptionSubclassesTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/MetaDataRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/StatementRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/jdbc42/ConnectionRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/jdbc42/ResultSetRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/regression/jdbc42/StatementRegressionTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/BlobTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/CallableStatementTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/CharsetTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/ConnectionTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/DataSourceTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/DateTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/EscapeProcessingTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/MetadataTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/MiniAdminTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/MultiHostConnectionTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/NumbersTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/ReadOnlyCallableStatementTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/ResultSetTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/SSLTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/ServerControllerTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/SimpleTransformer.java
mysql-connector-java-5.1.46/src/testsuite/simple/SplitDBdotNameTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/StatementsTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/StringUtilsTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/TestBug57662Logger.java
mysql-connector-java-5.1.46/src/testsuite/simple/TestLifecycleInterceptor.java
mysql-connector-java-5.1.46/src/testsuite/simple/TransactionTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/TraversalTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/UpdatabilityTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/UtilsTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/XATest.java
mysql-connector-java-5.1.46/src/testsuite/simple/jdbc4/StatementsTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/jdbc42/ConnectionTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/jdbc42/ResultSetTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/jdbc42/StatementsTest.java
mysql-connector-java-5.1.46/src/testsuite/simple/tb2-data.txt.gz
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/ca-cert.pem
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/ca-key.pem
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/ca-truststore
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/certs_howto.txt
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/client-cert.pem
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/client-key.pem
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/client-keystore
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/mykey.pem
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/mykey.pub
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/server-cert.pem
mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/server-key.pem
[root@ip-172-31-16-48 repofiles]# ll
total 4364
-rw-r--r-- 1 root root   25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.rpm
drwxr-xr-x 3 root root    4096 Feb 26 05:28 mysql-connector-java-5.1.46
-rw-r--r-- 1 root root 4434926 Feb 26 04:28 mysql-connector-java-5.1.46.tar.gz
[root@ip-172-31-16-48 repofiles]# cd mysql-connector-java-5.1.46
[root@ip-172-31-16-48 mysql-connector-java-5.1.46]# ll
total 2452
-rw-r--r-- 1 root root   91845 Feb 26 05:28 build.xml
-rw-r--r-- 1 root root  247456 Feb 26 05:28 CHANGES
-rw-r--r-- 1 root root   18122 Feb 26 05:28 COPYING
-rw-r--r-- 1 root root 1004840 Feb 26 05:28 mysql-connector-java-5.1.46-bin.jar
-rw-r--r-- 1 root root 1004838 Feb 26 05:28 mysql-connector-java-5.1.46.jar
-rw-r--r-- 1 root root   61407 Feb 26 05:28 README
-rw-r--r-- 1 root root   63658 Feb 26 05:28 README.txt
drwxr-xr-x 8 root root    4096 Feb 26 05:28 src
[root@ip-172-31-16-48 mysql-connector-java-5.1.46]# cd /usr/share
[root@ip-172-31-16-48 share]# ls
abrt          desktop-directories  gnats                        info        java-utils    magic      pixmaps           sos                     vim
aclocal       dict                 gnome                        java        javazi        man        pkgconfig         sounds                  wallpapers
alsa          doc                  gnome-background-properties  java-1.3.1  javazi-1.8    maven2     pki               sssd                    X11
anaconda      dracut               gnupg                        java-1.4.0  jvm           mime       plymouth          system-config-firewall  xsessions
applications  emacs                groff                        java-1.4.1  jvm-commmon   mime-info  polkit-1          system-config-network   yum-cli
augeas        empty                grub                         java-1.4.2  kde4          misc       python-dmidecode  system-config-selinux   yum-plugins
authconfig    file                 gtk-2.0                      java-1.5.0  kde-settings  myspell    screen            systemtap               zoneinfo
awk           firstboot            hal                          java-1.6.0  kdump         mysql      selinux           tabset
backgrounds   fonts                hwdata                       java-1.7.0  keyutils      nano       setools-3.3       tc
cracklib      games                i18n                         java-1.8.0  libthai       omf        setuptool         terminfo
cups          ghostscript          icons                        javadoc     locale        p11-kit    sgml              themes
dbus-1        glib-2.0             idl                          java-ext    lua           perl5      smartmontools     trace-cmd
[root@ip-172-31-16-48 share]# cd java
[root@ip-172-31-16-48 java]# ll
total 14924
lrwxrwxrwx 1 root root       28 May 14 01:24 activation.jar -> /etc/alternatives/activation
drwxr-xr-x 2 root root     4096 May 14 01:24 apache-tomcat-apis
drwxr-xr-x 2 root root     4096 May 14 01:24 axis
-rw-r--r-- 1 root root   528000 Nov 10  2010 bcel-5.2.jar
lrwxrwxrwx 1 root root       12 May 14 01:24 bcel.jar -> bcel-5.2.jar
-rw-r--r-- 1 root root    46341 Nov 10  2010 classpathx-jaf-1.0.jar
lrwxrwxrwx 1 root root       22 May 14 01:24 classpathx-jaf.jar -> classpathx-jaf-1.0.jar
drwxr-xr-x 2 root root     4096 May 14 01:24 classpathx-mail
-rw-r--r-- 1 root root   403631 Nov 10  2010 classpathx-mail-1.3.1-monolithic-1.1.1.jar
lrwxrwxrwx 1 root root       42 May 14 01:24 classpathx-mail-1.3.1-monolithic.jar -> classpathx-mail-1.3.1-monolithic-1.1.1.jar
lrwxrwxrwx 1 root root       33 May 14 01:24 commons-discovery-0.4.jar -> jakarta-commons-discovery-0.4.jar
lrwxrwxrwx 1 root root       25 May 14 01:24 commons-discovery.jar -> commons-discovery-0.4.jar
lrwxrwxrwx 1 root root       34 May 14 01:24 commons-httpclient-3.1.jar -> jakarta-commons-httpclient-3.1.jar
lrwxrwxrwx 1 root root       22 May 14 01:24 commons-httpclient3.jar -> commons-httpclient.jar
lrwxrwxrwx 1 root root       26 May 14 01:24 commons-httpclient.jar -> commons-httpclient-3.1.jar
lrwxrwxrwx 1 root root       33 May 14 01:24 commons-logging-1.0.4.jar -> jakarta-commons-logging-1.0.4.jar
lrwxrwxrwx 1 root root       37 May 14 01:24 commons-logging-api-1.0.4.jar -> jakarta-commons-logging-api-1.0.4.jar
lrwxrwxrwx 1 root root       29 May 14 01:24 commons-logging-api.jar -> commons-logging-api-1.0.4.jar
lrwxrwxrwx 1 root root       25 May 14 01:24 commons-logging.jar -> commons-logging-1.0.4.jar
lrwxrwxrwx 1 root root       27 May 14 01:24 dom3-xml-commons-apis-1.3.04.jar -> xml-commons-apis-1.3.04.jar
lrwxrwxrwx 1 root root       32 May 14 01:24 dom3-xml-commons-apis.jar -> dom3-xml-commons-apis-1.3.04.jar
lrwxrwxrwx 1 root root       25 May 14 01:24 ejb.jar -> geronimo/spec-ejb-2.1.jar
drwxr-xr-x 2 root root     4096 Mar 13 11:49 gcj-endorsed
drwxr-xr-x 2 root root     4096 May 14 01:24 geronimo
lrwxrwxrwx 1 root root       36 May 14 01:24 j2ee-connector.jar -> geronimo/spec-j2ee-connector-1.5.jar
lrwxrwxrwx 1 root root       37 May 14 01:24 j2ee-deployment.jar -> geronimo/spec-j2ee-deployment-1.1.jar
lrwxrwxrwx 1 root root       37 May 14 01:24 j2ee-management.jar -> geronimo/spec-j2ee-management-1.0.jar
lrwxrwxrwx 1 root root       31 May 14 01:24 jacc.jar -> geronimo/spec-j2ee-jacc-1.0.jar
lrwxrwxrwx 1 root root       21 May 14 01:24 jaf.jar -> /etc/alternatives/jaf
-rw-r--r-- 1 root root    73278 Nov 11  2010 jakarta-commons-discovery-0.4.jar
lrwxrwxrwx 1 root root       33 May 14 01:24 jakarta-commons-discovery.jar -> jakarta-commons-discovery-0.4.jar
-rw-r--r-- 1 root root   303763 Sep  8  2014 jakarta-commons-httpclient-3.1.jar
lrwxrwxrwx 1 root root       34 May 14 01:24 jakarta-commons-httpclient.jar -> jakarta-commons-httpclient-3.1.jar
-rw-r--r-- 1 root root    38870 Aug 22  2010 jakarta-commons-logging-1.0.4.jar
-rw-r--r-- 1 root root    25443 Aug 22  2010 jakarta-commons-logging-api-1.0.4.jar
lrwxrwxrwx 1 root root       37 May 14 01:24 jakarta-commons-logging-api.jar -> jakarta-commons-logging-api-1.0.4.jar
lrwxrwxrwx 1 root root       33 May 14 01:24 jakarta-commons-logging.jar -> jakarta-commons-logging-1.0.4.jar
-rw-r--r-- 1 root root    73310 Aug 20  2010 java_cup-0.10k.jar
lrwxrwxrwx 1 root root       18 May 14 01:24 java_cup.jar -> java_cup-0.10k.jar
-rw-r--r-- 1 root root     9053 Aug 20  2010 java_cup-runtime-0.10k.jar
lrwxrwxrwx 1 root root       26 May 14 01:24 java_cup-runtime.jar -> java_cup-runtime-0.10k.jar
lrwxrwxrwx 1 root root       26 May 14 01:24 javamail.jar -> /etc/alternatives/javamail
lrwxrwxrwx 1 root root       20 May 14 01:24 jaxp13.jar -> xml-commons-apis.jar
lrwxrwxrwx 1 root root       20 May 14 01:24 jaxp.jar -> xml-commons-apis.jar
lrwxrwxrwx 1 root root       34 May 14 01:24 jaxp_parser_impl.jar -> /etc/alternatives/jaxp_parser_impl
-rw-r--r-- 1 root root    84746 Aug 21  2010 jline-0.9.94.jar
lrwxrwxrwx 1 root root       16 Aug 16  2012 jline.jar -> jline-0.9.94.jar
lrwxrwxrwx 1 root root       25 May 14 01:24 jms.jar -> geronimo/spec-jms-1.1.jar
lrwxrwxrwx 1 root root       23 May 14 01:24 jmxri.jar -> /etc/alternatives/jmxri
lrwxrwxrwx 1 root root       13 Mar 20  2017 js-1.7.jar -> rhino-1.7.jar
lrwxrwxrwx 1 root root       13 Mar 20  2017 js.jar -> rhino-1.7.jar
lrwxrwxrwx 1 root root       28 May 14 01:24 jta.jar -> geronimo/spec-jta-1.0.1B.jar
-rw-r--r-- 1 root root 10163022 Mar 13 11:49 libgcj-4.4.4.jar
lrwxrwxrwx 1 root root       16 May 14 01:24 libgcj-4.4.7.jar -> libgcj-4.4.4.jar
-rw-r--r-- 1 root root   378087 Nov 11  2010 log4j-1.2.14.jar
lrwxrwxrwx 1 root root       16 May 14 01:24 log4j.jar -> log4j-1.2.14.jar
drwxr-xr-x 3 root root     4096 May 14 01:24 mx4j
-rw-r--r-- 1 root root   819803 Jun 22  2012 mysql-connector-java-5.1.17.jar
lrwxrwxrwx 1 root root       31 May 14 01:24 mysql-connector-java.jar -> mysql-connector-java-5.1.17.jar
-rw-r--r-- 1 root root   165789 Aug 20  2010 qname-1.5.2.jar
-rw-r--r-- 1 root root    44860 Aug 20  2010 regexp-1.5.jar
lrwxrwxrwx 1 root root       14 May 14 01:24 regexp.jar -> regexp-1.5.jar
-rw-r--r-- 1 root root  1069198 May 10  2016 rhino-1.7.jar
-rw-r--r-- 1 root root    18400 May 10  2016 rhino-examples-1.7.jar
lrwxrwxrwx 1 root root       22 Mar 20  2017 rhino-examples.jar -> rhino-examples-1.7.jar
lrwxrwxrwx 1 root root       13 Mar 20  2017 rhino.jar -> rhino-1.7.jar
-rw-r--r-- 1 root root   414906 Aug 18  2010 sinjdoc.jar
drwxr-xr-x 2 root root     4096 May 14 01:24 slf4j
-rw-r--r-- 1 root root   165789 Aug 20  2010 wsdl4j-1.5.2.jar
lrwxrwxrwx 1 root root       15 May 14 01:24 wsdl4j.jar -> qname-1.5.2.jar
-rw-r--r-- 1 root root   230522 Aug 18  2010 xml-commons-apis-1.3.04.jar
-rw-r--r-- 1 root root    90958 Aug 18  2010 xml-commons-apis-ext-1.3.04.jar
lrwxrwxrwx 1 root root       31 May 14 01:24 xml-commons-apis-ext.jar -> xml-commons-apis-ext-1.3.04.jar
lrwxrwxrwx 1 root root       27 May 14 01:24 xml-commons-apis.jar -> xml-commons-apis-1.3.04.jar
lrwxrwxrwx 1 root root       20 May 14 01:24 xml-commons-jaxp-1.3-apis.jar -> xml-commons-apis.jar
-rw-r--r-- 1 root root    56968 Aug 20  2010 xml-commons-resolver-1.1.jar
lrwxrwxrwx 1 root root       28 May 14 01:24 xml-commons-resolver.jar -> xml-commons-resolver-1.1.jar
[root@ip-172-31-16-48 java]# cd
[root@ip-172-31-16-48 ~]# cd /
[root@ip-172-31-16-48 /]# cd repofiles/
[root@ip-172-31-16-48 repofiles]# ll
total 4364
-rw-r--r-- 1 root root   25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.rpm
drwxr-xr-x 3 root root    4096 Feb 26 05:28 mysql-connector-java-5.1.46
-rw-r--r-- 1 root root 4434926 Feb 26 04:28 mysql-connector-java-5.1.46.tar.gz
[root@ip-172-31-16-48 repofiles]# cd mysql-connector-java-5.1.46
[root@ip-172-31-16-48 mysql-connector-java-5.1.46]# ll
total 2452
-rw-r--r-- 1 root root   91845 Feb 26 05:28 build.xml
-rw-r--r-- 1 root root  247456 Feb 26 05:28 CHANGES
-rw-r--r-- 1 root root   18122 Feb 26 05:28 COPYING
-rw-r--r-- 1 root root 1004840 Feb 26 05:28 mysql-connector-java-5.1.46-bin.jar
-rw-r--r-- 1 root root 1004838 Feb 26 05:28 mysql-connector-java-5.1.46.jar
-rw-r--r-- 1 root root   61407 Feb 26 05:28 README
-rw-r--r-- 1 root root   63658 Feb 26 05:28 README.txt
drwxr-xr-x 8 root root    4096 Feb 26 05:28 src
[root@ip-172-31-16-48 mysql-connector-java-5.1.46]# cp mysql-connector-java-5.1.46.jar /usr/share/java/mysql-connector-java.jar
