# Installing maria db from default repo

[root@ip-172-31-27-72 ~]# yum -y install mariadb-server
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Resolving Dependencies
--> Running transaction check
---> Package mariadb-server.x86_64 1:5.5.56-2.el7 will be installed
--> Processing Dependency: mariadb(x86-64) = 1:5.5.56-2.el7 for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: /usr/bin/perl for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.1)(64bit) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.4)(64bit) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(DBI) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(Data::Dumper) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(File::Basename) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(File::Copy) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(File::Path) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(File::Temp) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(Getopt::Long) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(POSIX) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(Sys::Hostname) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(strict) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(vars) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl-DBD-MySQL for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl-DBI for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: libaio.so.1()(64bit) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Running transaction check
---> Package libaio.x86_64 0:0.3.109-13.el7 will be installed
---> Package mariadb.x86_64 1:5.5.56-2.el7 will be installed
--> Processing Dependency: perl(Exporter) for package: 1:mariadb-5.5.56-2.el7.x86_64
---> Package perl.x86_64 4:5.16.3-292.el7 will be installed
--> Processing Dependency: perl-libs = 4:5.16.3-292.el7 for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Scalar::Util) >= 1.10 for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Socket) >= 1.3 for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Carp) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Cwd) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(File::Spec) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(File::Spec::Functions) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(File::Spec::Unix) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Filter::Util::Call) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Pod::Simple::Search) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Pod::Simple::XHTML) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Scalar::Util) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Socket) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Storable) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Time::HiRes) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Time::Local) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(constant) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(threads) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(threads::shared) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl-libs for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl-macros for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: libperl.so()(64bit) for package: 4:perl-5.16.3-292.el7.x86_64
---> Package perl-DBD-MySQL.x86_64 0:4.023-6.el7 will be installed
---> Package perl-DBI.x86_64 0:1.627-4.el7 will be installed
--> Processing Dependency: perl(RPC::PlClient) >= 0.2000 for package: perl-DBI-1.627-4.el7.x86_64
--> Processing Dependency: perl(RPC::PlServer) >= 0.2001 for package: perl-DBI-1.627-4.el7.x86_64
---> Package perl-Data-Dumper.x86_64 0:2.145-3.el7 will be installed
---> Package perl-File-Path.noarch 0:2.09-2.el7 will be installed
---> Package perl-File-Temp.noarch 0:0.23.01-3.el7 will be installed
---> Package perl-Getopt-Long.noarch 0:2.40-3.el7 will be installed
--> Processing Dependency: perl(Pod::Usage) >= 1.14 for package: perl-Getopt-Long-2.40-3.el7.noarch
--> Processing Dependency: perl(Text::ParseWords) for package: perl-Getopt-Long-2.40-3.el7.noarch
--> Running transaction check
---> Package perl-Carp.noarch 0:1.26-244.el7 will be installed
---> Package perl-Exporter.noarch 0:5.68-3.el7 will be installed
---> Package perl-Filter.x86_64 0:1.49-3.el7 will be installed
---> Package perl-PathTools.x86_64 0:3.40-5.el7 will be installed
---> Package perl-PlRPC.noarch 0:0.2020-14.el7 will be installed
--> Processing Dependency: perl(Net::Daemon) >= 0.13 for package: perl-PlRPC-0.2020-14.el7.noarch
--> Processing Dependency: perl(Compress::Zlib) for package: perl-PlRPC-0.2020-14.el7.noarch
--> Processing Dependency: perl(Net::Daemon::Log) for package: perl-PlRPC-0.2020-14.el7.noarch
--> Processing Dependency: perl(Net::Daemon::Test) for package: perl-PlRPC-0.2020-14.el7.noarch
---> Package perl-Pod-Simple.noarch 1:3.28-4.el7 will be installed
--> Processing Dependency: perl(Pod::Escapes) >= 1.04 for package: 1:perl-Pod-Simple-3.28-4.el7.noarch
--> Processing Dependency: perl(Encode) for package: 1:perl-Pod-Simple-3.28-4.el7.noarch
---> Package perl-Pod-Usage.noarch 0:1.63-3.el7 will be installed
--> Processing Dependency: perl(Pod::Text) >= 3.15 for package: perl-Pod-Usage-1.63-3.el7.noarch
--> Processing Dependency: perl-Pod-Perldoc for package: perl-Pod-Usage-1.63-3.el7.noarch
---> Package perl-Scalar-List-Utils.x86_64 0:1.27-248.el7 will be installed
---> Package perl-Socket.x86_64 0:2.010-4.el7 will be installed
---> Package perl-Storable.x86_64 0:2.45-3.el7 will be installed
---> Package perl-Text-ParseWords.noarch 0:3.29-4.el7 will be installed
---> Package perl-Time-HiRes.x86_64 4:1.9725-3.el7 will be installed
---> Package perl-Time-Local.noarch 0:1.2300-2.el7 will be installed
---> Package perl-constant.noarch 0:1.27-2.el7 will be installed
---> Package perl-libs.x86_64 4:5.16.3-292.el7 will be installed
---> Package perl-macros.x86_64 4:5.16.3-292.el7 will be installed
---> Package perl-threads.x86_64 0:1.87-4.el7 will be installed
---> Package perl-threads-shared.x86_64 0:1.43-6.el7 will be installed
--> Running transaction check
---> Package perl-Encode.x86_64 0:2.51-7.el7 will be installed
---> Package perl-IO-Compress.noarch 0:2.061-2.el7 will be installed
--> Processing Dependency: perl(Compress::Raw::Bzip2) >= 2.061 for package: perl-IO-Compress-2.061-2.el7.noarch
--> Processing Dependency: perl(Compress::Raw::Zlib) >= 2.061 for package: perl-IO-Compress-2.061-2.el7.noarch
---> Package perl-Net-Daemon.noarch 0:0.48-5.el7 will be installed
---> Package perl-Pod-Escapes.noarch 1:1.04-292.el7 will be installed
---> Package perl-Pod-Perldoc.noarch 0:3.20-4.el7 will be installed
--> Processing Dependency: perl(HTTP::Tiny) for package: perl-Pod-Perldoc-3.20-4.el7.noarch
--> Processing Dependency: perl(parent) for package: perl-Pod-Perldoc-3.20-4.el7.noarch
---> Package perl-podlators.noarch 0:2.5.1-3.el7 will be installed
--> Running transaction check
---> Package perl-Compress-Raw-Bzip2.x86_64 0:2.061-3.el7 will be installed
---> Package perl-Compress-Raw-Zlib.x86_64 1:2.061-4.el7 will be installed
---> Package perl-HTTP-Tiny.noarch 0:0.033-3.el7 will be installed
---> Package perl-parent.noarch 1:0.225-244.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===================================================================================================================================================================
 Package                                   Arch                     Version                               Repository                                          Size
===================================================================================================================================================================
Installing:
 mariadb-server                            x86_64                   1:5.5.56-2.el7                        rhui-REGION-rhel-server-releases                    11 M
Installing for dependencies:
 libaio                                    x86_64                   0.3.109-13.el7                        rhui-REGION-rhel-server-releases                    24 k
 mariadb                                   x86_64                   1:5.5.56-2.el7                        rhui-REGION-rhel-server-releases                   9.1 M
 perl                                      x86_64                   4:5.16.3-292.el7                      rhui-REGION-rhel-server-releases                   8.0 M
 perl-Carp                                 noarch                   1.26-244.el7                          rhui-REGION-rhel-server-releases                    19 k
 perl-Compress-Raw-Bzip2                   x86_64                   2.061-3.el7                           rhui-REGION-rhel-server-releases                    32 k
 perl-Compress-Raw-Zlib                    x86_64                   1:2.061-4.el7                         rhui-REGION-rhel-server-releases                    57 k
 perl-DBD-MySQL                            x86_64                   4.023-6.el7                           rhui-REGION-rhel-server-releases                   140 k
 perl-DBI                                  x86_64                   1.627-4.el7                           rhui-REGION-rhel-server-releases                   802 k
 perl-Data-Dumper                          x86_64                   2.145-3.el7                           rhui-REGION-rhel-server-releases                    47 k
 perl-Encode                               x86_64                   2.51-7.el7                            rhui-REGION-rhel-server-releases                   1.5 M
 perl-Exporter                             noarch                   5.68-3.el7                            rhui-REGION-rhel-server-releases                    28 k
 perl-File-Path                            noarch                   2.09-2.el7                            rhui-REGION-rhel-server-releases                    27 k
 perl-File-Temp                            noarch                   0.23.01-3.el7                         rhui-REGION-rhel-server-releases                    56 k
 perl-Filter                               x86_64                   1.49-3.el7                            rhui-REGION-rhel-server-releases                    76 k
 perl-Getopt-Long                          noarch                   2.40-3.el7                            rhui-REGION-rhel-server-releases                    56 k
 perl-HTTP-Tiny                            noarch                   0.033-3.el7                           rhui-REGION-rhel-server-releases                    38 k
 perl-IO-Compress                          noarch                   2.061-2.el7                           rhui-REGION-rhel-server-releases                   260 k
 perl-Net-Daemon                           noarch                   0.48-5.el7                            rhui-REGION-rhel-server-releases                    51 k
 perl-PathTools                            x86_64                   3.40-5.el7                            rhui-REGION-rhel-server-releases                    83 k
 perl-PlRPC                                noarch                   0.2020-14.el7                         rhui-REGION-rhel-server-releases                    36 k
 perl-Pod-Escapes                          noarch                   1:1.04-292.el7                        rhui-REGION-rhel-server-releases                    51 k
 perl-Pod-Perldoc                          noarch                   3.20-4.el7                            rhui-REGION-rhel-server-releases                    87 k
 perl-Pod-Simple                           noarch                   1:3.28-4.el7                          rhui-REGION-rhel-server-releases                   216 k
 perl-Pod-Usage                            noarch                   1.63-3.el7                            rhui-REGION-rhel-server-releases                    27 k
 perl-Scalar-List-Utils                    x86_64                   1.27-248.el7                          rhui-REGION-rhel-server-releases                    36 k
 perl-Socket                               x86_64                   2.010-4.el7                           rhui-REGION-rhel-server-releases                    49 k
 perl-Storable                             x86_64                   2.45-3.el7                            rhui-REGION-rhel-server-releases                    77 k
 perl-Text-ParseWords                      noarch                   3.29-4.el7                            rhui-REGION-rhel-server-releases                    14 k
 perl-Time-HiRes                           x86_64                   4:1.9725-3.el7                        rhui-REGION-rhel-server-releases                    45 k
 perl-Time-Local                           noarch                   1.2300-2.el7                          rhui-REGION-rhel-server-releases                    24 k
 perl-constant                             noarch                   1.27-2.el7                            rhui-REGION-rhel-server-releases                    19 k
 perl-libs                                 x86_64                   4:5.16.3-292.el7                      rhui-REGION-rhel-server-releases                   688 k
 perl-macros                               x86_64                   4:5.16.3-292.el7                      rhui-REGION-rhel-server-releases                    43 k
 perl-parent                               noarch                   1:0.225-244.el7                       rhui-REGION-rhel-server-releases                    12 k
 perl-podlators                            noarch                   2.5.1-3.el7                           rhui-REGION-rhel-server-releases                   112 k
 perl-threads                              x86_64                   1.87-4.el7                            rhui-REGION-rhel-server-releases                    49 k
 perl-threads-shared                       x86_64                   1.43-6.el7                            rhui-REGION-rhel-server-releases                    39 k

Transaction Summary
===================================================================================================================================================================
Install  1 Package (+37 Dependent packages)

Total download size: 33 M
Installed size: 147 M
Downloading packages:
(1/38): libaio-0.3.109-13.el7.x86_64.rpm                                                                                                    |  24 kB  00:00:00
(2/38): perl-Carp-1.26-244.el7.noarch.rpm                                                                                                   |  19 kB  00:00:00
(3/38): perl-Compress-Raw-Bzip2-2.061-3.el7.x86_64.rpm                                                                                      |  32 kB  00:00:00
(4/38): mariadb-5.5.56-2.el7.x86_64.rpm                                                                                                     | 9.1 MB  00:00:00
(5/38): perl-Compress-Raw-Zlib-2.061-4.el7.x86_64.rpm                                                                                       |  57 kB  00:00:00
(6/38): perl-5.16.3-292.el7.x86_64.rpm                                                                                                      | 8.0 MB  00:00:00
(7/38): perl-DBD-MySQL-4.023-6.el7.x86_64.rpm                                                                                               | 140 kB  00:00:00
(8/38): mariadb-server-5.5.56-2.el7.x86_64.rpm                                                                                              |  11 MB  00:00:00
(9/38): perl-DBI-1.627-4.el7.x86_64.rpm                                                                                                     | 802 kB  00:00:00
(10/38): perl-Data-Dumper-2.145-3.el7.x86_64.rpm                                                                                            |  47 kB  00:00:00
(11/38): perl-Encode-2.51-7.el7.x86_64.rpm                                                                                                  | 1.5 MB  00:00:00
(12/38): perl-Exporter-5.68-3.el7.noarch.rpm                                                                                                |  28 kB  00:00:00
(13/38): perl-File-Path-2.09-2.el7.noarch.rpm                                                                                               |  27 kB  00:00:00
(14/38): perl-File-Temp-0.23.01-3.el7.noarch.rpm                                                                                            |  56 kB  00:00:00
(15/38): perl-Filter-1.49-3.el7.x86_64.rpm                                                                                                  |  76 kB  00:00:00
(16/38): perl-Getopt-Long-2.40-3.el7.noarch.rpm                                                                                             |  56 kB  00:00:00
(17/38): perl-HTTP-Tiny-0.033-3.el7.noarch.rpm                                                                                              |  38 kB  00:00:00
(18/38): perl-Net-Daemon-0.48-5.el7.noarch.rpm                                                                                              |  51 kB  00:00:00
(19/38): perl-IO-Compress-2.061-2.el7.noarch.rpm                                                                                            | 260 kB  00:00:00
(20/38): perl-PathTools-3.40-5.el7.x86_64.rpm                                                                                               |  83 kB  00:00:00
(21/38): perl-PlRPC-0.2020-14.el7.noarch.rpm                                                                                                |  36 kB  00:00:00
(22/38): perl-Pod-Escapes-1.04-292.el7.noarch.rpm                                                                                           |  51 kB  00:00:00
(23/38): perl-Pod-Perldoc-3.20-4.el7.noarch.rpm                                                                                             |  87 kB  00:00:00
(24/38): perl-Pod-Simple-3.28-4.el7.noarch.rpm                                                                                              | 216 kB  00:00:00
(25/38): perl-Pod-Usage-1.63-3.el7.noarch.rpm                                                                                               |  27 kB  00:00:00
(26/38): perl-Scalar-List-Utils-1.27-248.el7.x86_64.rpm                                                                                     |  36 kB  00:00:00
(27/38): perl-Socket-2.010-4.el7.x86_64.rpm                                                                                                 |  49 kB  00:00:00
(28/38): perl-Storable-2.45-3.el7.x86_64.rpm                                                                                                |  77 kB  00:00:00
(29/38): perl-Text-ParseWords-3.29-4.el7.noarch.rpm                                                                                         |  14 kB  00:00:00
(30/38): perl-Time-Local-1.2300-2.el7.noarch.rpm                                                                                            |  24 kB  00:00:00
(31/38): perl-Time-HiRes-1.9725-3.el7.x86_64.rpm                                                                                            |  45 kB  00:00:00
(32/38): perl-constant-1.27-2.el7.noarch.rpm                                                                                                |  19 kB  00:00:00
(33/38): perl-libs-5.16.3-292.el7.x86_64.rpm                                                                                                | 688 kB  00:00:00
(34/38): perl-macros-5.16.3-292.el7.x86_64.rpm                                                                                              |  43 kB  00:00:00
(35/38): perl-parent-0.225-244.el7.noarch.rpm                                                                                               |  12 kB  00:00:00
(36/38): perl-podlators-2.5.1-3.el7.noarch.rpm                                                                                              | 112 kB  00:00:00
(37/38): perl-threads-1.87-4.el7.x86_64.rpm                                                                                                 |  49 kB  00:00:00
(38/38): perl-threads-shared-1.43-6.el7.x86_64.rpm                                                                                          |  39 kB  00:00:00
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                               35 MB/s |  33 MB  00:00:00
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : 1:perl-parent-0.225-244.el7.noarch                                                                                                             1/38
  Installing : perl-HTTP-Tiny-0.033-3.el7.noarch                                                                                                              2/38
  Installing : perl-podlators-2.5.1-3.el7.noarch                                                                                                              3/38
  Installing : perl-Pod-Perldoc-3.20-4.el7.noarch                                                                                                             4/38
  Installing : 1:perl-Pod-Escapes-1.04-292.el7.noarch                                                                                                         5/38
  Installing : perl-Text-ParseWords-3.29-4.el7.noarch                                                                                                         6/38
  Installing : perl-Encode-2.51-7.el7.x86_64                                                                                                                  7/38
  Installing : perl-Pod-Usage-1.63-3.el7.noarch                                                                                                               8/38
  Installing : 4:perl-macros-5.16.3-292.el7.x86_64                                                                                                            9/38
  Installing : 4:perl-libs-5.16.3-292.el7.x86_64                                                                                                             10/38
  Installing : perl-threads-1.87-4.el7.x86_64                                                                                                                11/38
  Installing : perl-Storable-2.45-3.el7.x86_64                                                                                                               12/38
  Installing : perl-Exporter-5.68-3.el7.noarch                                                                                                               13/38
  Installing : perl-constant-1.27-2.el7.noarch                                                                                                               14/38
  Installing : perl-Time-Local-1.2300-2.el7.noarch                                                                                                           15/38
  Installing : perl-Socket-2.010-4.el7.x86_64                                                                                                                16/38
  Installing : perl-Carp-1.26-244.el7.noarch                                                                                                                 17/38
  Installing : 4:perl-Time-HiRes-1.9725-3.el7.x86_64                                                                                                         18/38
  Installing : perl-threads-shared-1.43-6.el7.x86_64                                                                                                         19/38
  Installing : perl-PathTools-3.40-5.el7.x86_64                                                                                                              20/38
  Installing : perl-Scalar-List-Utils-1.27-248.el7.x86_64                                                                                                    21/38
  Installing : perl-File-Temp-0.23.01-3.el7.noarch                                                                                                           22/38
  Installing : perl-File-Path-2.09-2.el7.noarch                                                                                                              23/38
  Installing : perl-Filter-1.49-3.el7.x86_64                                                                                                                 24/38
  Installing : 1:perl-Pod-Simple-3.28-4.el7.noarch                                                                                                           25/38
  Installing : perl-Getopt-Long-2.40-3.el7.noarch                                                                                                            26/38
  Installing : 4:perl-5.16.3-292.el7.x86_64                                                                                                                  27/38
  Installing : perl-Data-Dumper-2.145-3.el7.x86_64                                                                                                           28/38
  Installing : perl-Compress-Raw-Bzip2-2.061-3.el7.x86_64                                                                                                    29/38
  Installing : perl-Net-Daemon-0.48-5.el7.noarch                                                                                                             30/38
  Installing : 1:perl-Compress-Raw-Zlib-2.061-4.el7.x86_64                                                                                                   31/38
  Installing : perl-IO-Compress-2.061-2.el7.noarch                                                                                                           32/38
  Installing : perl-PlRPC-0.2020-14.el7.noarch                                                                                                               33/38
  Installing : perl-DBI-1.627-4.el7.x86_64                                                                                                                   34/38
  Installing : perl-DBD-MySQL-4.023-6.el7.x86_64                                                                                                             35/38
  Installing : 1:mariadb-5.5.56-2.el7.x86_64                                                                                                                 36/38
  Installing : libaio-0.3.109-13.el7.x86_64                                                                                                                  37/38
  Installing : 1:mariadb-server-5.5.56-2.el7.x86_64                                                                                                          38/38
  Verifying  : perl-HTTP-Tiny-0.033-3.el7.noarch                                                                                                              1/38
  Verifying  : perl-threads-shared-1.43-6.el7.x86_64                                                                                                          2/38
  Verifying  : perl-Storable-2.45-3.el7.x86_64                                                                                                                3/38
  Verifying  : perl-threads-1.87-4.el7.x86_64                                                                                                                 4/38
  Verifying  : perl-Exporter-5.68-3.el7.noarch                                                                                                                5/38
  Verifying  : perl-constant-1.27-2.el7.noarch                                                                                                                6/38
  Verifying  : perl-PathTools-3.40-5.el7.x86_64                                                                                                               7/38
  Verifying  : 4:perl-macros-5.16.3-292.el7.x86_64                                                                                                            8/38
  Verifying  : 1:mariadb-server-5.5.56-2.el7.x86_64                                                                                                           9/38
  Verifying  : perl-Compress-Raw-Bzip2-2.061-3.el7.x86_64                                                                                                    10/38
  Verifying  : 1:perl-parent-0.225-244.el7.noarch                                                                                                            11/38
  Verifying  : perl-Net-Daemon-0.48-5.el7.noarch                                                                                                             12/38
  Verifying  : 4:perl-5.16.3-292.el7.x86_64                                                                                                                  13/38
  Verifying  : perl-File-Temp-0.23.01-3.el7.noarch                                                                                                           14/38
  Verifying  : 1:perl-Pod-Simple-3.28-4.el7.noarch                                                                                                           15/38
  Verifying  : perl-Time-Local-1.2300-2.el7.noarch                                                                                                           16/38
  Verifying  : 4:perl-libs-5.16.3-292.el7.x86_64                                                                                                             17/38
  Verifying  : perl-DBI-1.627-4.el7.x86_64                                                                                                                   18/38
  Verifying  : libaio-0.3.109-13.el7.x86_64                                                                                                                  19/38
  Verifying  : perl-Socket-2.010-4.el7.x86_64                                                                                                                20/38
  Verifying  : perl-Carp-1.26-244.el7.noarch                                                                                                                 21/38
  Verifying  : perl-Data-Dumper-2.145-3.el7.x86_64                                                                                                           22/38
  Verifying  : 4:perl-Time-HiRes-1.9725-3.el7.x86_64                                                                                                         23/38
  Verifying  : perl-Scalar-List-Utils-1.27-248.el7.x86_64                                                                                                    24/38
  Verifying  : 1:perl-Compress-Raw-Zlib-2.061-4.el7.x86_64                                                                                                   25/38
  Verifying  : 1:perl-Pod-Escapes-1.04-292.el7.noarch                                                                                                        26/38
  Verifying  : perl-IO-Compress-2.061-2.el7.noarch                                                                                                           27/38
  Verifying  : perl-Pod-Usage-1.63-3.el7.noarch                                                                                                              28/38
  Verifying  : perl-PlRPC-0.2020-14.el7.noarch                                                                                                               29/38
  Verifying  : perl-Encode-2.51-7.el7.x86_64                                                                                                                 30/38
  Verifying  : perl-Pod-Perldoc-3.20-4.el7.noarch                                                                                                            31/38
  Verifying  : perl-podlators-2.5.1-3.el7.noarch                                                                                                             32/38
  Verifying  : perl-File-Path-2.09-2.el7.noarch                                                                                                              33/38
  Verifying  : perl-DBD-MySQL-4.023-6.el7.x86_64                                                                                                             34/38
  Verifying  : perl-Filter-1.49-3.el7.x86_64                                                                                                                 35/38
  Verifying  : perl-Getopt-Long-2.40-3.el7.noarch                                                                                                            36/38
  Verifying  : perl-Text-ParseWords-3.29-4.el7.noarch                                                                                                        37/38
  Verifying  : 1:mariadb-5.5.56-2.el7.x86_64                                                                                                                 38/38

Installed:
  mariadb-server.x86_64 1:5.5.56-2.el7

Dependency Installed:
  libaio.x86_64 0:0.3.109-13.el7                        mariadb.x86_64 1:5.5.56-2.el7                         perl.x86_64 4:5.16.3-292.el7
  perl-Carp.noarch 0:1.26-244.el7                       perl-Compress-Raw-Bzip2.x86_64 0:2.061-3.el7          perl-Compress-Raw-Zlib.x86_64 1:2.061-4.el7
  perl-DBD-MySQL.x86_64 0:4.023-6.el7                   perl-DBI.x86_64 0:1.627-4.el7                         perl-Data-Dumper.x86_64 0:2.145-3.el7
  perl-Encode.x86_64 0:2.51-7.el7                       perl-Exporter.noarch 0:5.68-3.el7                     perl-File-Path.noarch 0:2.09-2.el7
  perl-File-Temp.noarch 0:0.23.01-3.el7                 perl-Filter.x86_64 0:1.49-3.el7                       perl-Getopt-Long.noarch 0:2.40-3.el7
  perl-HTTP-Tiny.noarch 0:0.033-3.el7                   perl-IO-Compress.noarch 0:2.061-2.el7                 perl-Net-Daemon.noarch 0:0.48-5.el7
  perl-PathTools.x86_64 0:3.40-5.el7                    perl-PlRPC.noarch 0:0.2020-14.el7                     perl-Pod-Escapes.noarch 1:1.04-292.el7
  perl-Pod-Perldoc.noarch 0:3.20-4.el7                  perl-Pod-Simple.noarch 1:3.28-4.el7                   perl-Pod-Usage.noarch 0:1.63-3.el7
  perl-Scalar-List-Utils.x86_64 0:1.27-248.el7          perl-Socket.x86_64 0:2.010-4.el7                      perl-Storable.x86_64 0:2.45-3.el7
  perl-Text-ParseWords.noarch 0:3.29-4.el7              perl-Time-HiRes.x86_64 4:1.9725-3.el7                 perl-Time-Local.noarch 0:1.2300-2.el7
  perl-constant.noarch 0:1.27-2.el7                     perl-libs.x86_64 4:5.16.3-292.el7                     perl-macros.x86_64 4:5.16.3-292.el7
  perl-parent.noarch 1:0.225-244.el7                    perl-podlators.noarch 0:2.5.1-3.el7                   perl-threads.x86_64 0:1.87-4.el7
  perl-threads-shared.x86_64 0:1.43-6.el7

Complete!
[root@ip-172-31-27-72 ~]# rpm -qa | grep mariadb
mariadb-libs-5.5.56-2.el7.x86_64
mariadb-5.5.56-2.el7.x86_64
mariadb-server-5.5.56-2.el7.x86_64
