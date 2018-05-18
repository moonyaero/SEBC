## Instance List
|Instance Name | DNS | IP| OS | UPTIME |
|------|----|----|---| ---------|
|Test-NM|ec2-54-169-156-171.ap-southeast-1.compute.amazonaws.com| Redhat 7.5| 02:43:04 up  1:37,  1 user,  load average: 0.00, 0.01, 0.05
|Test-CM|ec2-13-250-30-109.ap-southeast-1.compute.amazonaws.com|52.77.241.203| Redhat 7.5| 02:43:09 up  1:37,  1 user,  load average: 0.00, 0.01, 0.03
|Test-DN1|ec2-52-221-208-57.ap-southeast-1.compute.amazonaws.com|52.77.237.244| Redhat 7.5| 02:43:12 up  1:37,  1 user,  load average: 0.00, 0.01, 0.05
|Test-DN2|ec2-13-229-65-94.ap-southeast-1.compute.amazonaws.com|13.229.248.50| Redhat 7.5| 02:43:15 up  1:39,  1 user,  load average: 0.00, 0.01, 0.05
|Test-DN3|ec2-52-221-215-17.ap-southeast-1.compute.amazonaws.com|52.221.216.46| Redhat 7.5| 02:43:20 up  1:38,  1 user,  load average: 0.00, 0.01, 0.05

## File System Capacity
```
[root@ip-172-31-27-72 ec2-user]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       50G  947M   50G   2% /
devtmpfs        7.8G     0  7.8G   0% /dev
tmpfs           7.8G     0  7.8G   0% /dev/shm
tmpfs           7.8G   17M  7.8G   1% /run
tmpfs           7.8G     0  7.8G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/0
tmpfs           1.6G     0  1.6G   0% /run/user/1000

```
## Yum Repository

```
[root@ip-172-31-27-72 ec2-user]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
rhui-REGION-client-config-server-7                                                                                                          | 2.9 kB  00:00:00
rhui-REGION-rhel-server-releases                                                                                                            | 3.5 kB  00:00:00
rhui-REGION-rhel-server-rh-common                                                                                                           | 3.8 kB  00:00:00
(1/7): rhui-REGION-client-config-server-7/x86_64/primary_db                                                                                 | 2.5 kB  00:00:00
(2/7): rhui-REGION-rhel-server-releases/7Server/x86_64/group                                                                                | 855 kB  00:00:00
(3/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/group                                                                               |  104 B  00:00:00
(4/7): rhui-REGION-rhel-server-releases/7Server/x86_64/updateinfo                                                                           | 2.8 MB  00:00:00
(5/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/primary_db                                                                          | 120 kB  00:00:00
(6/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/updateinfo                                                                          |  33 kB  00:00:00
(7/7): rhui-REGION-rhel-server-releases/7Server/x86_64/primary_db                                                                           |  51 MB  00:00:00
repo id                                                                repo name                                                                             status
rhui-REGION-client-config-server-7/x86_64                              Red Hat Update Infrastructure 2.0 Client Configuration Server 7                            1
rhui-REGION-rhel-server-releases/7Server/x86_64                        Red Hat Enterprise Linux Server 7 (RPMs)                                              20,399
rhui-REGION-rhel-server-rh-common/7Server/x86_64                       Red Hat Enterprise Linux Server 7 RH Common (RPMs)                                       231
repolist: 20,631
```

## /etc/passwd

```
[root@ip-172-31-27-72 ec2-user]# cat /etc/passwd | grep thanos
thanos:x:2500:2500::/home/thanos:/bin/bash
[root@ip-172-31-27-72 ec2-user]# cat /etc/passwd | grep hulk
hulk:x:2600:2600::/home/hulk:/bin/bash
[root@ip-172-31-27-72 ec2-user]# cat /etc/passwd | grep groot
groot:x:2700:2700::/home/groot:/bin/bash

```

## /etc/group

```
[root@ip-172-31-27-72 ec2-user]# cat /etc/group | grep blackorder
blackorder:x:2701:thanos
[root@ip-172-31-27-72 ec2-user]# cat /etc/group | grep avengers
avengers:x:2702:hulk,groot

```