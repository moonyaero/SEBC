# Test HDFS throughput #

[root@ip-172-31-30-109 ~]# useradd moonyaero
[root@ip-172-31-30-109 ~]# passwd moonyaero
Changing password for user moonyaero.
New password:
Retype new password:
passwd: all authentication tokens updated successfully.
[root@ip-172-31-30-109 ~]# cat /etc/passwd | grep moonyaero
moonyaero:x:502:502::/home/moonyaero:/bin/bash

### To be consistent with the rest of the nodes, add the following options when you add user in other nodes

[root@ip-172-31-28-176 ec2-user]# useradd -u 502 moonyaero
[root@ip-172-31-28-176 ec2-user]# cat /etc/passwd | grep moonyaero
moonyaero:x:502:502::/home/moonyaero:/bin/bash
[root@ip-172-31-28-176 ec2-user]# ^C
[root@ip-172-31-28-176 ec2-user]# passwd moonyaero
Changing password for user moonyaero.
New password:
Retype new password:
passwd: all authentication tokens updated successfully.
[root@ip-172-31-28-176 ec2-user]# cat /etc/passwd | grep moonyaero
moonyaero:x:502:502::/home/moonyaero:/bin/bash

[root@ip-172-31-30-109 moonyaero]# sudo -u hdfs hadoop fs -mkdir /user/moonyaero
[root@ip-172-31-30-109 moonyaero]# sudo -u hdfs hadoop fs -chown moonyaero: /user/moonyaero
[root@ip-172-31-30-109 moonyaero]# sudo -u hdfs hadoop fs -chown moonyaero:moonyaero /user/moonyaero

