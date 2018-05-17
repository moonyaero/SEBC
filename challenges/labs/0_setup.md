Cloud Provider : AWS

## Instance List
|Instance Name | DNS | IP| OS |
|------|----|----|---|
|challenges:NN|ec2-54-169-189-117.ap-southeast-1.compute.amazonaws.com|54.169.189.117| Redhat 7.5|
|challenges:CM|ec2-52-77-241-203.ap-southeast-1.compute.amazonaws.com|52.77.241.203| Redhat 7.5|
|challenges:DN1|ec2-52-77-237-244|ec2-52-77-237-244.ap-southeast-1.compute.amazonaws.com |52.77.237.244| Redhat 7.5|
|challenges:DN2|ec2-13-229-248-50.ap-southeast-1.compute.amazonaws.com|13.229.248.50| Redhat 7.5|
|challenges:DN3|ec2-52-221-216-46.ap-southeast-1.compute.amazonaws.com|52.221.216.46| Redhat 7.5|

## File System Capacity
```
[root@ip-172-31-31-108 ec2-user]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       50G  945M   50G   2% /
devtmpfs        7.8G     0  7.8G   0% /dev
tmpfs           7.8G     0  7.8G   0% /dev/shm
tmpfs           7.8G   17M  7.8G   1% /run
tmpfs           7.8G     0  7.8G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000

```

## Yum Repository

```
[root@ip-172-31-31-108 ec2-user]# yum repolist enabled
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
[root@ip-172-31-31-108 ec2-user]# cat /etc/passwd | grep jimenez
jimenez:x:2800:2800::/home/jimenez:/bin/bash
[root@ip-172-31-31-108 ec2-user]# cat /etc/passwd | grep beltran
beltran:x:2900:2900::/home/beltran:/bin/bash

```

## /etc/group

```
[root@ip-172-31-31-108 ec2-user]# cat /etc/group | grep astros
astros:x:2902:beltran
[root@ip-172-31-31-108 ec2-user]# cat /etc/group | grep rangers
rangers:x:2901:jimenez
```
