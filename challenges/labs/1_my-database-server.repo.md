## CM repo configuration 
```
[cloudera-manager-5.13.3]
# Packages for Cloudera Manager, Version 5.13.3, on RedHat or CentOS 7 x86_64
name=Cloudera Manager 5.13.3
baseurl=https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.13.3/
gpgkey =https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
gpgcheck = 1

```

## CM installed packages
```
[root@ip-172-31-31-108 yum.repos.d]# yum list all | grep cloudera-manager
cloudera-manager-agent.x86_64 5.13.3-1.cm5133.p0.6.el7
                                                @cloudera-manager-5.13.3
cloudera-manager-daemons.x86_64
                                                @cloudera-manager-5.13.3
cloudera-manager-server.x86_64
                                                @cloudera-manager-5.13.3
cloudera-manager-server-db-2.x86_64
                                                cloudera-manager-5.13.3
                                                cloudera-manager-5.13.3
jdk.x86_64                    2000:1.6.0_31-fcs cloudera-manager-5.13.3
oracle-j2sdk1.7.x86_64        1.7.0+update67-1  cloudera-manager-5.13.3
```

## Oracle JDK 1.8 Installed
```
[root@ip-172-31-31-108 yum.repos.d]# rpm -qa | grep oracle
oracle-j2sdk1.8-1.8.0+update121-1.x86_64
```

## The command hostname -f and its output
```
[root@ip-172-31-31-108 ~]# hostname -f
ip-172-31-31-108.ap-southeast-1.compute.internal
```
## The command mysql -u <user> -p<password> -e "status;" and its output

MariaDB [(none)]> show databases;
```
[root@ip-172-31-31-108 ~]# mysql -u root -p -e status;
Enter password:
--------------
mysql  Ver 15.1 Distrib 5.5.56-MariaDB, for Linux (x86_64) using readline 5.1

Connection id:          14
Current database:
Current user:           root@localhost
SSL:                    Not in use
Current pager:          stdout
Using outfile:          ''
Using delimiter:        ;
Server:                 MariaDB
Server version:         5.5.56-MariaDB MariaDB Server
Protocol version:       10
Connection:             Localhost via UNIX socket
Server characterset:    latin1
Db     characterset:    latin1
Client characterset:    utf8
Conn.  characterset:    utf8
UNIX socket:            /var/lib/mysql/mysql.sock
Uptime:                 15 min 47 sec

Threads: 1  Questions: 68  Slow queries: 0  Opens: 2  Flush tables: 2  Open tables: 27  Queries per second avg: 0.071
--------------

```

## The command mysql -u <user> -p<password> -e "show databases;" and its output
```
[root@ip-172-31-31-108 ~]# mysql -u root -pxQc42u75 -e "show databases;"
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hue                |
| metastore          |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+

```


