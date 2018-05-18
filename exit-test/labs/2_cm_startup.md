* first line log
[root@ip-172-31-29-229 yum.repos.d]# more /var/log/cloudera-scm-server/cloudera-scm-server.log
2018-05-18 00:25:47,195 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dl
og4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.roo
t.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-serv
er.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=tr
ue, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, 
-XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOut
OfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.11.2
 (#6 built by jenkins on 20170811-0014 git: 3c3ea33a12076fb83a8f11c4452c52fac685d01b)

* started jetty server 
2018-05-18 00:26:43,603 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
2018-05-18 00:26:45,709 INFO ScmActive-0:com.cloudera.server.cmf.components.ScmActive: ScmActive completed successfully