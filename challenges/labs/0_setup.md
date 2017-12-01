List the cloud provider you are using (AWS, GCE, Azure, CloudCat, other)
```sh
AWS
```

List your instances by IP address and DNS name (don't use /etc/hosts for this)

```sh
[root@ip-172-31-19-21 ~]# getent hosts $(ifconfig eth0 | grep inet | awk '{print $2}')
172.31.19.21    ip-172-31-19-21.ec2.internal
fe80::8e8:c0ff:fe52:5ae4 ip-172-31-19-21.ec2.internal


[root@ip-172-31-30-64 ~]# getent hosts $(ifconfig eth0 | grep inet | awk '{print $2}')
172.31.30.64    ip-172-31-30-64.ec2.internal
fe80::894:28ff:fee0:e3ee ip-172-31-30-64.ec2.internal

root@ip-172-31-25-195 ~]# getent hosts $(ifconfig eth0 | grep inet | awk '{print $2}')                                
172.31.25.195   ip-172-31-25-195.ec2.internal                                                                          
fe80::856:afff:fe38:98ec ip-172-31-25-195.ec2.internal

[root@ip-172-31-26-68 ~]# getent hosts $(ifconfig eth0 | grep inet | awk '{print $2}')
172.31.26.68    ip-172-31-26-68.ec2.internal
fe80::891:f9ff:fea4:84da ip-172-31-26-68.ec2.internal


[root@ip-172-31-24-75 ~]# getent hosts $(ifconfig eth0 | grep inet | awk '{print $2}') 
172.31.24.75    ip-172-31-24-75.ec2.internal
fe80::8a3:74ff:fe45:c40 ip-172-31-24-75.ec2.internal

```

List the Linux release you are using

```sh

[root@ip-172-31-19-21 ~]# cat /etc/redhat-release
Red Hat Enterprise Linux Server release 7.4 (Maipo)

```

List the file system capacity for the first node

```sh

[root@ip-172-31-19-21 data]# lsblk
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk 
├─xvda1 202:1    0   1M  0 part 
└─xvda2 202:2    0  50G  0 part /
xvdb    202:16   0  80G  0 disk /data/disk0
xvdc    202:32   0  80G  0 disk /data/disk1




```

List the command and output for yum repolist enabled

```sh

[root@ip-172-31-19-21 ~]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
rhui-REGION-client-config-server-7                                                                                                                                                          | 2.9 kB  00:00:00     
rhui-REGION-rhel-server-releases                                                                                                                                                            | 3.5 kB  00:00:00     
rhui-REGION-rhel-server-rh-common                                                                                                                                                           | 3.8 kB  00:00:00     
(1/7): rhui-REGION-client-config-server-7/x86_64/primary_db                                                                                                                                 | 6.6 kB  00:00:00     
(2/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/group                                                                                                                               |  104 B  00:00:00     
(3/7): rhui-REGION-rhel-server-releases/7Server/x86_64/group                                                                                                                                | 709 kB  00:00:00     
rhui-REGION-rhel-server-releas FAILED                                          
https://rhui2-cds02.us-east-1.aws.ce.redhat.com/pulp/repos//content/dist/rhel/rhui/server/7/7Server/x86_64/os/repodata/d8fa53a986b3cd02aeabe8545bbed7cedf68ea9d866065026ed34c7c4168d739-updateinfo.xml.gz: [Errno 14] HTTPS Error 401 - Unauthorized
Trying other mirror.
(4/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/primary_db                                                                                                                          | 119 kB  00:00:00     
rhui-REGION-rhel-server-rh-com FAILED                                          
https://rhui2-cds02.us-east-1.aws.ce.redhat.com/pulp/repos//content/dist/rhel/rhui/server/7/7Server/x86_64/rh-common/os/repodata/3281dac9d5f57a1bf1578ce333b07b920f0a2b2867e6bee4401dd2b36cd2360d-updateinfo.xml.gz: [Errno 14] HTTPS Error 401 - Unauthorized
Trying other mirror.
(5/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/updateinfo                                                                                                                          |  32 kB  00:00:00     
(6/7): rhui-REGION-rhel-server-releases/7Server/x86_64/updateinfo                                                                                                                           | 2.4 MB  00:00:00     
(7/7): rhui-REGION-rhel-server-releases/7Server/x86_64/primary_db                                                                                                                           |  44 MB  00:00:00     
repo id                                                                                        repo name                                                                                                     status
rhui-REGION-client-config-server-7/x86_64                                                      Red Hat Update Infrastructure 2.0 Client Configuration Server 7                                                    8
rhui-REGION-rhel-server-releases/7Server/x86_64                                                Red Hat Enterprise Linux Server 7 (RPMs)                                                                      17,521
rhui-REGION-rhel-server-rh-common/7Server/x86_64                                               Red Hat Enterprise Linux Server 7 RH Common (RPMs)                                                               228
repolist: 17,757



```

Add the following Linux accounts to all nodes
	User saturn with a UID of 2800
	User haley with a UID of 2900
	Create the group comets and add haley to it
	Create the group planets and add saturn to it

```sh

useradd -u 2800 saturn
useradd -u 2900 haley
groupadd comets
usermod -aG comets haley
groupadd planets
usermod -aG planets saturn

```

List the /etc/passwd entries for saturn and haley
Do not list the entire file

```sh

[root@ip-172-31-19-21 ~]# cat /etc/passwd | grep 'saturn\|haley'
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash

```



List the /etc/group entries for comets and planets
Do not list the entire file

```sh

[root@ip-172-31-19-21 ~]# cat /etc/group | grep 'comets\|planets'
comets:x:2901:haley
planets:x:2902:saturn

```

