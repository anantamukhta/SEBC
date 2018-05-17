# <center> Challenge Setup

* Challenge setup
  * List the cloud provider you are using : AWS
  * List your instances by IP address and DNS name : 
  
ec2-18-221-69-172.us-east-2.compute.amazonaws.com	18.221.69.172
ec2-18-191-28-149.us-east-2.compute.amazonaws.com	18.191.28.149
ec2-18-191-69-24.us-east-2.compute.amazonaws.com	18.191.69.24
ec2-18-188-140-101.us-east-2.compute.amazonaws.com	18.188.140.101
ec2-18-221-33-92.us-east-2.compute.amazonaws.com	18.221.33.92

  * List the Linux release you are using : REDHAT 7.3
  * List the file system capacity for the first node
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       50G  979M   50G   2% /
devtmpfs        7.8G     0  7.8G   0% /dev
tmpfs           7.7G     0  7.7G   0% /dev/shm
tmpfs           7.7G   17M  7.7G   1% /run
tmpfs           7.7G     0  7.7G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000

  * List the command and output for `yum repolist enabled`
yum repolist enable
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
rhui-REGION-client-config-server-7                                          | 2.9 kB  00:00:00     
rhui-REGION-rhel-server-releases                                            | 3.5 kB  00:00:00     
rhui-REGION-rhel-server-rh-common                                           | 3.8 kB  00:00:00     
(1/7): rhui-REGION-client-config-server-7/x86_64/primary_db                 | 3.3 kB  00:00:00     
(2/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/group               |  104 B  00:00:00     
(3/7): rhui-REGION-rhel-server-releases/7Server/x86_64/updateinfo           | 2.8 MB  00:00:00     
(4/7): rhui-REGION-rhel-server-releases/7Server/x86_64/group                | 855 kB  00:00:00     
(5/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/primary_db          | 120 kB  00:00:00     
(6/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/updateinfo          |  33 kB  00:00:00     
(7/7): rhui-REGION-rhel-server-releases/7Server/x86_64/primary_db           |  51 MB  00:00:00     
repolist: 0

* list /etc/passwd
jimenez:x:2800:2902::/home/jimenez:/bin/bash
beltran:x:2900:2903::/home/beltran:/bin/bash

* list /etc/group
astros:x:2900:beltran
rangers:x:2800:jimenez

# Challenge 1: Install a MySQL/MariaDB server
[mariadb]
name = MariaDB-5.5.39
baseurl=http://yum.mariadb.org/5.5/rhel7-amd64/
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1

Dependencies Resolved

===================================================================================================
 Package                   Arch     Version               Repository                          Size
===================================================================================================
Installing:
 MariaDB-server            x86_64   5.5.60-1.el7.centos   mariadb                             40 M
 MariaDB-shared            x86_64   5.5.60-1.el7.centos   mariadb                            1.0 M
     replacing  mariadb-libs.x86_64 1:5.5.52-1.el7
Installing for dependencies:
 MariaDB-client            x86_64   5.5.60-1.el7.centos   mariadb                            8.6 M
 MariaDB-common            x86_64   5.5.60-1.el7.centos   mariadb                             23 k
 libaio                    x86_64   0.3.109-13.el7        rhui-REGION-rhel-server-releases    24 k
 perl                      x86_64   4:5.16.3-292.el7      rhui-REGION-rhel-server-releases   8.0 M
 perl-Carp                 noarch   1.26-244.el7          rhui-REGION-rhel-server-releases    19 k
 perl-Compress-Raw-Bzip2   x86_64   2.061-3.el7           rhui-REGION-rhel-server-releases    32 k
 perl-Compress-Raw-Zlib    x86_64   1:2.061-4.el7         rhui-REGION-rhel-server-releases    57 k
 perl-DBI                  x86_64   1.627-4.el7           rhui-REGION-rhel-server-releases   802 k
 perl-Data-Dumper          x86_64   2.145-3.el7           rhui-REGION-rhel-server-releases    47 k
 perl-Encode               x86_64   2.51-7.el7            rhui-REGION-rhel-server-releases   1.5 M
 perl-Exporter             noarch   5.68-3.el7            rhui-REGION-rhel-server-releases    28 k
 perl-File-Path            noarch   2.09-2.el7            rhui-REGION-rhel-server-releases    27 k
 perl-File-Temp            noarch   0.23.01-3.el7         rhui-REGION-rhel-server-releases    56 k
 perl-Filter               x86_64   1.49-3.el7            rhui-REGION-rhel-server-releases    76 k
 perl-Getopt-Long          noarch   2.40-3.el7            rhui-REGION-rhel-server-releases    56 k
 perl-HTTP-Tiny            noarch   0.033-3.el7           rhui-REGION-rhel-server-releases    38 k
 perl-IO-Compress          noarch   2.061-2.el7           rhui-REGION-rhel-server-releases   260 k
 perl-Net-Daemon           noarch   0.48-5.el7            rhui-REGION-rhel-server-releases    51 k
 perl-PathTools            x86_64   3.40-5.el7            rhui-REGION-rhel-server-releases    83 k
 perl-PlRPC                noarch   0.2020-14.el7         rhui-REGION-rhel-server-releases    36 k
 perl-Pod-Escapes          noarch   1:1.04-292.el7        rhui-REGION-rhel-server-releases    51 k
 perl-Pod-Perldoc          noarch   3.20-4.el7            rhui-REGION-rhel-server-releases    87 k
 perl-Pod-Simple           noarch   1:3.28-4.el7          rhui-REGION-rhel-server-releases   216 k
 perl-Pod-Usage            noarch   1.63-3.el7            rhui-REGION-rhel-server-releases    27 k
 perl-Scalar-List-Utils    x86_64   1.27-248.el7          rhui-REGION-rhel-server-releases    36 k
 perl-Socket               x86_64   2.010-4.el7           rhui-REGION-rhel-server-releases    49 k
 perl-Storable             x86_64   2.45-3.el7            rhui-REGION-rhel-server-releases    77 k
 perl-Text-ParseWords      noarch   3.29-4.el7            rhui-REGION-rhel-server-releases    14 k
 perl-Time-HiRes           x86_64   4:1.9725-3.el7        rhui-REGION-rhel-server-releases    45 k
 perl-Time-Local           noarch   1.2300-2.el7          rhui-REGION-rhel-server-releases    24 k
 perl-constant             noarch   1.27-2.el7            rhui-REGION-rhel-server-releases    19 k
 perl-libs                 x86_64   4:5.16.3-292.el7      rhui-REGION-rhel-server-releases   688 k
 perl-macros               x86_64   4:5.16.3-292.el7      rhui-REGION-rhel-server-releases    43 k
 perl-parent               noarch   1:0.225-244.el7       rhui-REGION-rhel-server-releases    12 k
 perl-podlators            noarch   2.5.1-3.el7           rhui-REGION-rhel-server-releases   112 k
 perl-threads              x86_64   1.87-4.el7            rhui-REGION-rhel-server-releases    49 k
 perl-threads-shared       x86_64   1.43-6.el7            rhui-REGION-rhel-server-releases    39 k

Transaction Summary
===================================================================================================
Install  2 Packages (+37 Dependent packages)

Total download size: 62 M

* hostname -f
ip-172-31-23-110.us-east-2.compute.internal

* mysql -u <user> -p<password> -e "status;"
[root@ip-172-31-23-110 yum.repos.d]# mysql -u scm -pscm -e "status;"
--------------
mysql  Ver 15.1 Distrib 5.5.60-MariaDB, for Linux (x86_64) using readline 5.1

Connection id:		3
Current database:	
Current user:		scm@localhost
SSL:			Not in use
Current pager:		stdout
Using outfile:		''
Using delimiter:	;
Server:			MariaDB
Server version:		5.5.60-MariaDB MariaDB Server
Protocol version:	10
Connection:		Localhost via UNIX socket
Server characterset:	latin1
Db     characterset:	latin1
Client characterset:	utf8
Conn.  characterset:	utf8
UNIX socket:		/var/lib/mysql/mysql.sock
Uptime:			20 min 0 sec

Threads: 1  Questions: 11  Slow queries: 0  Opens: 0  Flush tables: 2  Open tables: 26  Queries per second avg: 0.009
--------------

* mysql -u <user> -p<password> -e "show databases;"
[root@ip-172-31-23-110 yum.repos.d]# mysql -u scm -pscm -e "show databases;"
+--------------------+
| Database           |
+--------------------+
| information_schema |
| scm                |
| test               |
+--------------------+

* cloudera manager repo
[cloudera-manager]
# Packages for Cloudera Manager, Version 5.13.3, on RedHat or CentOS 7 x86_64
name=Cloudera Manager
baseurl=http://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.13.3/
gpgkey =http://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
gpgcheck = 0