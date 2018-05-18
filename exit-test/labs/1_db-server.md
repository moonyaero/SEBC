# Hostname
```
[root@ip-172-31-27-72 ~]# hostname -f
ip-172-31-27-72.ap-southeast-1.compute.internal
```

# The command mysql -u <user> -p<password> -e "status;" and its output
```
[root@ip-172-31-27-72 ~]# mysql -u root -pxQc42u75 -e "status";
--------------
mysql  Ver 15.1 Distrib 5.5.56-MariaDB, for Linux (x86_64) using readline 5.1

Connection id:          11
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
Uptime:                 13 min 16 sec

Threads: 1  Questions: 44  Slow queries: 0  Opens: 1  Flush tables: 2  Open tables: 27  Queries per second avg: 0.055
```

# The command mysql -u <user> -p<password> -e "show databases;" and its output
```
[root@ip-172-31-27-72 ~]# mysql -u root -pxQc42u75 -e "show databases";
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

