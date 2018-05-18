[root@ip-172-31-22-135 ec2-user]# hostname -f
ip-172-31-22-135.us-east-2.compute.internal
[root@ip-172-31-29-229 ec2-user]# hostname -f
ip-172-31-29-229.us-east-2.compute.internal
[root@ip-172-31-20-199 ec2-user]# hostname -f
ip-172-31-20-199.us-east-2.compute.internal
[root@ip-172-31-24-79 ec2-user]# hostname -f
ip-172-31-24-79.us-east-2.compute.internal
[root@ip-172-31-28-187 ec2-user]# hostname -f
ip-172-31-28-187.us-east-2.compute.internal

[root@ip-172-31-22-135 ec2-user]# mysql -u root -e "status"
--------------
mysql  Ver 15.1 Distrib 5.5.60-MariaDB, for Linux (x86_64) using readline 5.1

Connection id:		8
Current database:	
Current user:		root@localhost
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
Uptime:			9 min 22 sec

Threads: 1  Questions: 47  Slow queries: 0  Opens: 0  Flush tables: 2  Open tables: 26  Queries per second avg: 0.083
--------------

[root@ip-172-31-22-135 ec2-user]# mysql -u root -e "show databases;"
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
| test               |
+--------------------+