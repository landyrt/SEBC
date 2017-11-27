1. Check vm.swappiness on all your nodes
        Set the value to 1 if necessary

```sh
[root@ip-172-31-31-84 ~]# sysctl -w vm.swappiness=1
vm.swappiness = 1
[root@ip-172-31-31-84 ~]# cat /proc/sys/vm/swappiness
1
```

Aplicar cambio en /etc/sysctl.conf

```sh
vi /etc/sysctl.conf

vm.swappiness = 1

```

2. Show the mount attributes of your volume(s)

```sh
[root@ip-172-31-31-84 ~]# lsblk -fm
NAME    FSTYPE LABEL UUID                                 MOUNTPOINT  NAME    SIZE OWNER GROUP MODE
xvda                                                                  xvda     50G root  disk  brw-rw----
├─xvda1                                                               ├─xvda1   1M root  disk  brw-rw----
└─xvda2 xfs          de4def96-ff72-4eb9-ad5e-0847257d1866 /           └─xvda2  50G root  disk  brw-rw----
xvdb    ext4         5b86013e-dab3-4d2c-968d-be3596c1556f /data/disk0 xvdb     80G root  disk  brw-rw----
xvdc    ext4         dda26a10-2202-430c-9ce0-dbda91011fae /data/disk1 xvdc     80G root  disk  brw-rw----

[root@ip-172-31-31-84 var]# ls -lad /opt /var/log
lrwxrwxrwx. 1 root root 15 Nov 27 15:06 /opt -> /data/disk0/opt
lrwxrwxrwx. 1 root root 15 Nov 27 15:08 /var/log -> /data/disk1/log
```
3. If you have ext-based volumes, list the reserve space setting
        XFS volumes do not support reserve space

```sh
[root@ip-172-31-31-84 ~]# tune2fs -l /dev/xvdb | grep "Reserved block count"; tune2fs -l /dev/xvdc | grep "Reserved block count"
Reserved block count:     0
Reserved block count:     0
```

4.Disable transparent hugepage support

```sh
[root@ip-172-31-31-84 ~]# cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]
[root@ip-172-31-31-84 ~]# cat /sys/kernel/mm/transparent_hugepage/defrag 
always madvise [never]
[root@ip-172-31-31-84 ~]# cat /proc/meminfo  | grep -i huge
AnonHugePages:      8192 kB
HugePages_Total:       0
HugePages_Free:        0
HugePages_Rsvd:        0
HugePages_Surp:        0
Hugepagesize:       2048 kB
```

5. List your network interface configuration

```sh
[root@ip-172-31-31-84 ~]# ifconfig eth0
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.31.84  netmask 255.255.240.0  broadcast 172.31.31.255
        ether 0a:7a:dd:72:bd:b2  txqueuelen 10000  (Ethernet)
        RX packets 283370  bytes 400977251 (382.4 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 35226  bytes 5961242 (5.6 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

6.Show that forward and reverse host lookups are correctly resolved

    For /etc/hosts, use getent

```sh
[root@ip-172-31-31-84 ~]# getent hosts $(ifconfig eth0 | grep inet | awk '{print $2}')
172.31.31.84    ip-172-31-31-84.ec2.internal ip-172-31-31-84.ec2 aws_elephant
```

    For DNS, use nslookup
```sh
[root@ip-172-31-31-84 ~]# nslookup $(hostname -f)
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-31-84.ec2.internal
Address: 172.31.31.84
```

6.Show the nscd service is running

```sh
[root@ip-172-31-31-84 ~]# systemctl status nscd
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-11-27 14:00:32 CST; 41min ago
 Main PID: 12257 (nscd)
   CGroup: /system.slice/nscd.service
           └─12257 /usr/sbin/nscd

Nov 27 14:00:32 ip-172-31-31-84.ec2.internal nscd[12257]: 12257 monitoring directory `/etc` (2)
Nov 27 14:00:32 ip-172-31-31-84.ec2.internal nscd[12257]: 12257 monitoring file `/etc/resolv.conf` (5)
Nov 27 14:00:32 ip-172-31-31-84.ec2.internal nscd[12257]: 12257 monitoring directory `/etc` (2)
Nov 27 14:00:32 ip-172-31-31-84.ec2.internal nscd[12257]: 12257 monitoring file `/etc/services` (6)
Nov 27 14:00:32 ip-172-31-31-84.ec2.internal nscd[12257]: 12257 monitoring directory `/etc` (2)
Nov 27 14:00:32 ip-172-31-31-84.ec2.internal nscd[12257]: 12257 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
Nov 27 14:00:32 ip-172-31-31-84.ec2.internal nscd[12257]: 12257 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
Nov 27 14:00:32 ip-172-31-31-84.ec2.internal nscd[12257]: 12257 Access Vector Cache (AVC) started
Nov 27 14:00:32 ip-172-31-31-84.ec2.internal systemd[1]: Started Name Service Cache Daemon.
Nov 27 14:00:51 ip-172-31-31-84.ec2.internal nscd[12257]: 12257 checking for monitored file `/etc/netgroup': No such file or directory
```

7.Show the ntpd service is running

```sh
[root@ip-172-31-31-84 ~]# systemctl status ntpd
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-11-27 13:55:46 CST; 48min ago
 Main PID: 12229 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─12229 /usr/sbin/ntpd -u ntp:ntp -g

Nov 27 13:55:46 ip-172-31-31-84.ec2.internal ntpd[12229]: Listen normally on 2 lo 127.0.0.1 UDP 123
Nov 27 13:55:46 ip-172-31-31-84.ec2.internal ntpd[12229]: Listen normally on 3 eth0 172.31.31.84 UDP 123
Nov 27 13:55:46 ip-172-31-31-84.ec2.internal ntpd[12229]: Listening on routing socket on fd #20 for interface updates
Nov 27 13:55:46 ip-172-31-31-84.ec2.internal systemd[1]: Started Network Time Service.
Nov 27 13:55:47 ip-172-31-31-84.ec2.internal ntpd[12229]: 0.0.0.0 c016 06 restart
Nov 27 13:55:47 ip-172-31-31-84.ec2.internal ntpd[12229]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Nov 27 13:55:47 ip-172-31-31-84.ec2.internal ntpd[12229]: 0.0.0.0 c011 01 freq_not_set
Nov 27 13:55:53 ip-172-31-31-84.ec2.internal ntpd[12229]: 0.0.0.0 c614 04 freq_mode
Nov 27 14:12:38 ip-172-31-31-84.ec2.internal ntpd[12229]: 0.0.0.0 0612 02 freq_set kernel -0.146 PPM
Nov 27 14:12:38 ip-172-31-31-84.ec2.internal ntpd[12229]: 0.0.0.0 0615 05 clock_sync
```



