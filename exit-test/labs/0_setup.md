* cluster setup 
 * Run the uptime command on every node
[ec2-user@ip-172-31-22-135 ~]$ uptime
 22:52:26 up 14 min,  1 user,  load average: 0.00, 0.03, 0.07
[ec2-user@ip-172-31-29-229 ~]$ uptime
 22:52:26 up 14 min,  1 user,  load average: 0.00, 0.01, 0.05
[ec2-user@ip-172-31-20-199 ~]$ uptime
 22:52:26 up 14 min,  1 user,  load average: 0.00, 0.03, 0.05
[ec2-user@ip-172-31-24-79 ~]$ uptime
 22:52:26 up 14 min,  1 user,  load average: 0.00, 0.02, 0.05
[ec2-user@ip-172-31-28-187 ~]$ uptime
 22:52:26 up 14 min,  1 user,  load average: 0.00, 0.02, 0.05

 * List the cloud provider you are using
AWS

 * List your instances by IP address and DNS name (don't use /etc/hosts for this)
ec2-18-219-92-237.us-east-2.compute.amazonaws.com	18.219.92.237	
ec2-13-59-113-141.us-east-2.compute.amazonaws.com	13.59.113.141
ec2-18-218-67-77.us-east-2.compute.amazonaws.com	18.218.67.77
ec2-13-58-158-66.us-east-2.compute.amazonaws.com	13.58.158.66
ec2-18-217-27-82.us-east-2.compute.amazonaws.com	18.217.27.82

 * List the Linux release you are using
cat /etc/redhat-release
Red Hat Enterprise Linux Server release 7.3 (Maipo)

 * List the file system capacity for the first node
[ec2-user@ip-172-31-22-135 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       50G  980M   50G   2% /
devtmpfs        7.8G     0  7.8G   0% /dev
tmpfs           7.7G     0  7.7G   0% /dev/shm
tmpfs           7.7G   17M  7.7G   1% /run
tmpfs           7.7G     0  7.7G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000

 * List the command and output for yum repolist enabled
sudo yum repolist enable
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repolist: 0

* List the /etc/passwd entries for all 3 users
thanos:x:2500:2500::/home/thanos:/bin/bash
hulk:x:2600:2600::/home/hulk:/bin/bash
groot:x:2700:2700::/home/groot:/bin/bash

* List the /etc/group entries for blackorder and avengers
blackorder:x:1002:thanos
avengers:x:1003:hulk,groot