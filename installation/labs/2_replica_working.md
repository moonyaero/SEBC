# Creating a MySQL Replica Server

## 1) Creating MySQL Replica Server on Datanode 1

[ec2-user@ip-172-31-28-176 ~]$ cd /repofiles/
[ec2-user@ip-172-31-28-176 repofiles]$ ll
total 4368
-rw-r--r-- 1 root root   25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.rpm
drwxr-xr-x 3 root root    4096 Feb 26 05:28 mysql-connector-java-5.1.46
-rw-r--r-- 1 root root 4434926 Feb 26 04:28 mysql-connector-java-5.1.46.tar.gz
drwxr-xr-x 2 root root    4096 May 14 21:13 repodata
[ec2-user@ip-172-31-28-176 repofiles]$ ^C
[ec2-user@ip-172-31-28-176 repofiles]$ yum install mysql80-community-release-el6-1.noarch.rpm
Loaded plugins: fastestmirror, security
You need to be root to perform this command.
[ec2-user@ip-172-31-28-176 repofiles]$ sudo su
[root@ip-172-31-28-176 repofiles]# yum install mysql80-community-release-el6-1.noarch.rpm
Loaded plugins: fastestmirror, security
Setting up Install Process
Examining mysql80-community-release-el6-1.noarch.rpm: mysql80-community-release-el6-1.noarch
Marking mysql80-community-release-el6-1.noarch.rpm to be installed
Bad id for repo: Cloudera Manager, byte =   8
Loading mirror speeds from cached hostfile
 * base: mirror.vodien.com
 * extras: mirror.vodien.com
 * updates: mirror.vodien.com
base                                                                                       | 3.7 kB     00:00
cloudera-manager                                                                           |  951 B     00:00
extras                                                                                     | 3.4 kB     00:00
mysql55-community                                                                          | 2.5 kB     00:00
updates                                                                                    | 3.4 kB     00:00
Resolving Dependencies
--> Running transaction check
---> Package mysql80-community-release.noarch 0:el6-1 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

==================================================================================================================
 Package                          Arch          Version      Repository                                      Size
==================================================================================================================
Installing:
 mysql80-community-release        noarch        el6-1        /mysql80-community-release-el6-1.noarch         31 k

Transaction Summary
==================================================================================================================
Install       1 Package(s)

Total size: 31 k
Installed size: 31 k
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : mysql80-community-release-el6-1.noarch                                                         1/1
  Verifying  : mysql80-community-release-el6-1.noarch                                                         1/1

Installed:
  mysql80-community-release.noarch 0:el6-1

Complete!
[root@ip-172-31-28-176 repofiles]#

[root@ip-172-31-28-176 yum.repos.d]# yum -y install mysql-server
Loaded plugins: fastestmirror, security
Setting up Install Process
Bad id for repo: Cloudera Manager, byte =   8
Loading mirror speeds from cached hostfile
 * base: centos.usonyx.net
 * extras: centos.usonyx.net
 * updates: centos.usonyx.net
Package mysql-server is obsoleted by mysql-community-server, trying to install mysql-community-server-5.5.60-2.el6.x86_64 instead
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
--> Processing Dependency: libmysqlclient_r.so.16()(64bit) for package: MySQL-python-1.2.3-0.3.c1.1.el6.x86_64
--> Processing Dependency: libmysqlclient_r.so.16(libmysqlclient_16)(64bit) for package: MySQL-python-1.2.3-0.3.c1.1.el6.x86_64
--> Running transaction check
---> Package mysql-community-libs-compat.x86_64 0:5.5.60-2.el6 will be obsoleting
---> Package postfix.x86_64 2:2.6.6-6.el6_7.1 will be updated
---> Package postfix.x86_64 2:2.6.6-8.el6 will be an update
--> Finished Dependency Resolution

Dependencies Resolved

==================================================================================================================
 Package                               Arch             Version                 Repository                   Size
==================================================================================================================
Installing:
 mysql-community-libs                  x86_64           5.5.60-2.el6            mysql55-community           1.7 M
     replacing  mysql-libs.x86_64 5.1.73-8.el6_8
 mysql-community-libs-compat           x86_64           5.5.60-2.el6            mysql55-community           1.6 M
     replacing  mysql-libs.x86_64 5.1.73-8.el6_8
 mysql-community-server                x86_64           5.5.60-2.el6            mysql55-community            38 M
Installing for dependencies:
 mysql-community-client                x86_64           5.5.60-2.el6            mysql55-community            15 M
 mysql-community-common                x86_64           5.5.60-2.el6            mysql55-community           277 k
 perl-DBI                              x86_64           1.609-4.el6             base                        705 k
Updating for dependencies:
 postfix                               x86_64           2:2.6.6-8.el6           base                        2.0 M

Transaction Summary
==================================================================================================================
Install       6 Package(s)
Upgrade       1 Package(s)

Total download size: 59 M
Downloading Packages:
(1/7): mysql-community-client-5.5.60-2.el6.x86_64.rpm                                      |  15 MB     00:00
(2/7): mysql-community-common-5.5.60-2.el6.x86_64.rpm                                      | 277 kB     00:00
(3/7): mysql-community-libs-5.5.60-2.el6.x86_64.rpm                                        | 1.7 MB     00:00
(4/7): mysql-community-libs-compat-5.5.60-2.el6.x86_64.rpm                                 | 1.6 MB     00:00
(5/7): mysql-community-server-5.5.60-2.el6.x86_64.rpm                                      |  38 MB     00:00
(6/7): perl-DBI-1.609-4.el6.x86_64.rpm                                                     | 705 kB     00:00
(7/7): postfix-2.6.6-8.el6.x86_64.rpm                                                      | 2.0 MB     00:00
------------------------------------------------------------------------------------------------------------------
Total                                                                              47 MB/s |  59 MB     00:01
warning: rpmts_HdrFromFdno: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Retrieving key from file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
Importing GPG key 0x5072E1F5:
 Userid : MySQL Release Engineering <mysql-build@oss.oracle.com>
 Package: mysql80-community-release-el6-1.noarch (@/mysql80-community-release-el6-1.noarch)
 From   : /etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : mysql-community-common-5.5.60-2.el6.x86_64                                                     1/9
  Installing : mysql-community-libs-5.5.60-2.el6.x86_64                                                       2/9
  Installing : mysql-community-client-5.5.60-2.el6.x86_64                                                     3/9
  Installing : mysql-community-libs-compat-5.5.60-2.el6.x86_64                                                4/9
  Installing : perl-DBI-1.609-4.el6.x86_64                                                                    5/9
  Installing : mysql-community-server-5.5.60-2.el6.x86_64                                                     6/9
  Updating   : 2:postfix-2.6.6-8.el6.x86_64                                                                   7/9
  Cleanup    : 2:postfix-2.6.6-6.el6_7.1.x86_64                                                               8/9
  Erasing    : mysql-libs-5.1.73-8.el6_8.x86_64                                                               9/9
  Verifying  : mysql-community-server-5.5.60-2.el6.x86_64                                                     1/9
  Verifying  : mysql-community-libs-5.5.60-2.el6.x86_64                                                       2/9
  Verifying  : mysql-community-client-5.5.60-2.el6.x86_64                                                     3/9
  Verifying  : 2:postfix-2.6.6-8.el6.x86_64                                                                   4/9
  Verifying  : perl-DBI-1.609-4.el6.x86_64                                                                    5/9
  Verifying  : mysql-community-common-5.5.60-2.el6.x86_64                                                     6/9
  Verifying  : mysql-community-libs-compat-5.5.60-2.el6.x86_64                                                7/9
  Verifying  : 2:postfix-2.6.6-6.el6_7.1.x86_64                                                               8/9
  Verifying  : mysql-libs-5.1.73-8.el6_8.x86_64                                                               9/9

Installed:
  mysql-community-libs.x86_64 0:5.5.60-2.el6            mysql-community-libs-compat.x86_64 0:5.5.60-2.el6
  mysql-community-server.x86_64 0:5.5.60-2.el6

Dependency Installed:
  mysql-community-client.x86_64 0:5.5.60-2.el6            mysql-community-common.x86_64 0:5.5.60-2.el6
  perl-DBI.x86_64 0:1.609-4.el6

Dependency Updated:
  postfix.x86_64 2:2.6.6-8.el6

Replaced:
  mysql-libs.x86_64 0:5.1.73-8.el6_8

Complete!
[root@ip-172-31-28-176 yum.repos.d]# service mysqld start
Initializing MySQL database:  180515 10:48:23 [Note] Ignoring --secure-file-priv value as server is running with --bootstrap.
180515 10:48:23 [Note] /usr/sbin/mysqld (mysqld 5.5.60) starting as process 27456 ...
180515 10:48:23 [Note] Ignoring --secure-file-priv value as server is running with --bootstrap.
180515 10:48:23 [Note] /usr/sbin/mysqld (mysqld 5.5.60) starting as process 27463 ...

PLEASE REMEMBER TO SET A PASSWORD FOR THE MySQL root USER !
To do so, start the server, then issue the following commands:

/usr/bin/mysqladmin -u root password 'new-password'
/usr/bin/mysqladmin -u root -h ip-172-31-28-176 password 'new-password'

Alternatively you can run:
/usr/bin/mysql_secure_installation

which will also give you the option of removing the test
databases and anonymous user created by default.  This is
strongly recommended for production servers.

See the manual for more instructions.

Please report any problems at http://bugs.mysql.com/

                                                           [  OK  ]
Starting mysqld:                                           [  OK  ]
[root@ip-172-31-28-176 yum.repos.d]# /usr/bin/mysql_secure_installation




NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MySQL
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!


In order to log into MySQL to secure it, we'll need the current
password for the root user.  If you've just installed MySQL, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none):
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)
Enter current password for root (enter for none):
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)
Enter current password for root (enter for none):
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MySQL
root user without the proper authorisation.

Set root password? [Y/n] Y
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

Remove anonymous users? [Y/n] Y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] n
 ... skipping.

By default, MySQL comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] Y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] Y
 ... Success!

Cleaning up...



All done!  If you've completed all of the above steps, your MySQL
installation should now be secure.

Thanks for using MySQL!

#On the master MySQL node, grant replication privileges for your replica node:

[root@ip-172-31-28-176 yum.repos.d]#

mysql> GRANT REPLICATION SLAVE ON *.* TO 'root'@'ip-172-31-28-176.ap-southeast-1.compute.internal' IDENTIFIED BY 'password';
Query OK, 0 rows affected (0.00 sec)

mysql> SET GLOBAL binlog_format = 'ROW';
Query OK, 0 rows affected (0.00 sec)

mysql> FLUSH TABLES WITH READ LOCK;
Query OK, 0 rows affected (0.00 sec)

mysql> SHOW MASTER STATUS;
+-------------------------+----------+--------------+------------------+
| File                    | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+-------------------------+----------+--------------+------------------+
| mysql_binary_log.000002 | 11431289 |              |                  |
+-------------------------+----------+--------------+------------------+
1 row in set (0.00 sec)



## Do a master.bin dump

[root@ip-172-31-30-109 x86_64]# `mysqldump -A -u root -p --flush-privileges --master-data=1 | gzip -1 > master.sql.gz`
Enter password:
-- Warning: Skipping the data of table mysql.event. Specify the --events option explicitly.
[root@ip-172-31-30-109 x86_64]`# zgrep -m 1 -P 'CHANGE MASTER' master.sql.gz`
CHANGE MASTER TO MASTER_LOG_FILE='mysql_binary_log.000002', MASTER_LOG_POS=11462134;
[root@ip-172-31-30-109 x86_64]# cp master.sql.gz /repofiles/

## Copy the master.sql.gz from your MySQL Master to Replica

Note: host master.sql.gz inside one of the folder under /var/www/html, download it from browser, SFTP into MySQL Replica Server under /home/ec2-user, then copy to where you want it.


## Login to the replica server and configure a connection to the master:

`CHANGE MASTER TO MASTER_HOST='ec2-52-221-200-239.ap-southeast-1.compute.amazonaws.com', MASTER_USER='root', MASTER_PASSWORD='password', MASTER_LOG_FILE='mysql_binary_log.000002', MASTER_LOG_POS=11462134;`


#OUTPUT

[ec2-user@ip-172-31-28-176 ~]$ hostname -f
ip-172-31-28-176.ap-southeast-1.compute.internal
[ec2-user@ip-172-31-28-176 ~]$ cd /home/ec2-user/
[ec2-user@ip-172-31-28-176 ~]$ ll
total 4
drwxrwxr-x 2 ec2-user ec2-user 4096 May 16 00:47 files
[ec2-user@ip-172-31-28-176 ~]$ cd files/
[ec2-user@ip-172-31-28-176 files]$ ll
total 3320
-rw-rw-r-- 1 ec2-user ec2-user 3399602 May 16 00:47 master.sql.gz
[ec2-user@ip-172-31-28-176 files]$ sudo su
[root@ip-172-31-28-176 files]# cp master.sql.gz /repofiles/
[root@ip-172-31-28-176 files]# cd /repofiles/
[root@ip-172-31-28-176 repofiles]# ll
total 146400
-rw-r--r-- 1 root root   3399602 May 16 00:47 master.sql.gz
-rw-r--r-- 1 root root     25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.rpm
drwxr-xr-x 3 root root      4096 Feb 26 05:28 mysql-connector-java-5.1.46
-rw-r--r-- 1 root root   4434926 Feb 26 04:28 mysql-connector-java-5.1.46.tar.gz
-rw-r--r-- 1 root root 142039186 Apr 18 07:43 oracle-j2sdk1.7-1.7.0+update67-1.x86_64.rpm
drwxr-xr-x 2 root root      4096 May 14 21:13 repodata
[root@ip-172-31-28-176 repofiles]# gunzip master.sql.gz
[root@ip-172-31-28-176 repofiles]# ll
total 181404
-rw-r--r-- 1 root root  39240880 May 16 00:47 master.sql
-rw-r--r-- 1 root root     25800 Apr 17 22:24 mysql80-community-release-el6-1.noarch.rpm
drwxr-xr-x 3 root root      4096 Feb 26 05:28 mysql-connector-java-5.1.46
-rw-r--r-- 1 root root   4434926 Feb 26 04:28 mysql-connector-java-5.1.46.tar.gz
-rw-r--r-- 1 root root 142039186 Apr 18 07:43 oracle-j2sdk1.7-1.7.0+update67-1.x86_64.rpm
drwxr-xr-x 2 root root      4096 May 14 21:13 repodata
[root@ip-172-31-28-176 repofiles]# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 3
Server version: 5.5.60-log MySQL Community Server (GPL)

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> @master.sql
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '@master.sql' at line 1
mysql> exit
Bye
[root@ip-172-31-28-176 repofiles]# mysql -u root -p < master.sql
Enter password:
[root@ip-172-31-28-176 repofiles]# CHANGE MASTER TO MASTER_HOST='ec2-54-169-75-184.ap-southeast-1.compute.amazonaws.com', MASTER_USER='root', MASTER_PASSWORD='password', MASTER_LOG_FILE='mysql_binary_log.000002', MASTER_LOG_POS=11462134;
bash: CHANGE: command not found
[root@ip-172-31-28-176 repofiles]# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 5
Server version: 5.5.60-log MySQL Community Server (GPL)

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> CHANGE MASTER TO MASTER_HOST='ec2-54-169-75-184.ap-southeast-1.compute.amazonaws.com', MASTER_USER='root', MASTER_PASSWORD='password', MASTER_LOG_FILE='mysql_binary_log.000002', MASTER_LOG_POS=11462134;
Query OK, 0 rows affected (0.01 sec)

mysql> start slave;
Query OK, 0 rows affected (0.00 sec)

mysql> show slave status\G;
*************************** 1. row ***************************
               Slave_IO_State:
                  Master_Host: ec2-54-169-75-184.ap-southeast-1.compute.amazonaws.com
                  Master_User: root
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql_binary_log.000002
          Read_Master_Log_Pos: 11462134
               Relay_Log_File: mysqld-relay-bin.000001
                Relay_Log_Pos: 4
        Relay_Master_Log_File: mysql_binary_log.000002
             Slave_IO_Running: No
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 11462134
              Relay_Log_Space: 107
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: NULL
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 1593
                Last_IO_Error: Fatal error: The slave I/O thread stops because master and slave have equal MySQL server ids; these ids must be different for replication to work (or the --replicate-same-server-id option must be used on slave but this does not always make sense; please check the manual before using it).
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 2
1 row in set (0.00 sec)

ERROR:
No query specified

mysql> exit
Bye
[root@ip-172-31-28-176 repofiles]# cd /etc/my.cnf
bash: cd: /etc/my.cnf: Not a directory
[root@ip-172-31-28-176 repofiles]# vi /etc/my.cnf
[root@ip-172-31-28-176 repofiles]# service mysqld restart
Stopping mysqld:                                           [  OK  ]
Starting mysqld:                                           [  OK  ]
[root@ip-172-31-28-176 repofiles]# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 5
Server version: 5.5.60-log MySQL Community Server (GPL)

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show slave status\G;
*************************** 1. row ***************************
               Slave_IO_State:
                  Master_Host: ec2-54-169-75-184.ap-southeast-1.compute.amazonaws.com
                  Master_User: root
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql_binary_log.000002
          Read_Master_Log_Pos: 11462134
               Relay_Log_File: mysqld-relay-bin.000002
                Relay_Log_Pos: 4
        Relay_Master_Log_File: mysql_binary_log.000002
             Slave_IO_Running: No
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 11462134
              Relay_Log_Space: 107
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: NULL
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 1593
                Last_IO_Error: Fatal error: The slave I/O thread stops because master and slave have equal MySQL server ids; these ids must be different for replication to work (or the --replicate-same-server-id option must be used on slave but this does not always make sense; please check the manual before using it).
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 2
1 row in set (0.00 sec)

ERROR:
No query specified

mysql> CHANGE MASTER TO MASTER_HOST='ec2-52-221-200-239.ap-southeast-1.compute.amazonaws.com', MASTER_USER='root', MASTER_PASSWORD='password', MASTER_LOG_FILE='mysql_binary_log.000002', MASTER_LOG_POS=11462134;
ERROR 1198 (HY000): This operation cannot be performed with a running slave; run STOP SLAVE first
mysql> stop slave;
Query OK, 0 rows affected (0.00 sec)

mysql> CHANGE MASTER TO MASTER_HOST='ec2-52-221-200-239.ap-southeast-1.compute.amazonaws.com', MASTER_USER='root', MASTER_PASSWORD='password', MASTER_LOG_FILE='mysql_binary_log.000002', MASTER_LOG_POS=11462134;
Query OK, 0 rows affected (0.01 sec)

mysql> start slave;
Query OK, 0 rows affected (0.00 sec)

mysql> show slave status\G;
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: ec2-52-221-200-239.ap-southeast-1.compute.amazonaws.com
                  Master_User: root
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql_binary_log.000003
          Read_Master_Log_Pos: 9235
               Relay_Log_File: mysqld-relay-bin.000003
                Relay_Log_Pos: 9388
        Relay_Master_Log_File: mysql_binary_log.000003
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 9235
              Relay_Log_Space: 240111
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error:
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 1
1 row in set (0.00 sec)

ERROR:
No query specified

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| hue                |
| metastore          |
| mysql              |
| nav                |
| navms              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
| test               |
+--------------------+
13 rows in set (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| hue                |
| metastore          |
| mysql              |
| nav                |
| navms              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
12 rows in set (0.00 sec)

mysql> Ctrl-C -- exit!
Aborted
[root@ip-172-31-28-176 repofiles]#
