# HDFS Installation

```
* ssh-keygen -t rsa -f ~/.ssh/id_rsa -N ''
```
```
* chmod 400 ~/.ssh/id_rsa
```
```
* cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
```
```
* chmod 750 ~/.ssh/authorized_keys
```
```
* ssh-keyscan -t rsa -Hv  domain_name >> ~/.ssh/known_hosts
```
```
* mkdir hadoop
```
```
* sudo touch /etc/profile.d/hadoop_variables.sh
```
```
* sudo chown domain_name /etc/profile.d/hadoop_variables.sh
```
```
* sudo echo export JAVA_OPTS=-Xmx1300m >> /etc/profile.d/hadoop_variables.sh
```
```
* sudo chmod 755 /etc/profile.d/hadoop_variables.sh
```
```
* mkdir –p /home/hadoop/tmp
```
```
* mkdir –p /home/hadoop/dfs/name
```
```
* mkdir –p /home/hadoop/dfs/data
```
```
* wget http://mirrors.sonic.net/apache/hadoop/common/hadoop-2.6.0/hadoop-2.6.0.tar.gz
```
```
* tar xvzf hadoop/hadoop-2.6.0.tar.gz –C hadoop/
```
```
* echo export HADOOP_PREFIX=/home/hdfs/lib/hadoop/hadoop-2.6.0 >> /etc/profile.d/hadoop_variables.sh
```
```
* echo export HADOOP_MAPRED_HOME=/home/hdfs/lib/hadoop/hadoop-2.6.0 >> /etc/profile.d/hadoop_variables.sh
```
```
* echo export HADOOP_COMMON_HOME=/home/hdfs/lib/hadoop/hadoop-2.6.0 >> /etc/profile.d/hadoop_variables.sh
```
```
* echo export JAVA_HOME=/usr/lib/jvm/java-8-oracle >> /etc/profile.d/hadoop_variables.sh
```
```
* echo export JAVA_HOME=/usr/lib/jvm/java-8-oracle >> /home/hdfs/lib/hadoop/hadoop-2.6.0/etc/hadoop/hadoop-env.sh
```
```
* mkdir -p /home/hdfs/lib/hadoop/hadoop-1.2.0.1.3.3.0-58/logs/userlogs
```
```
* vi /home/hadoop/hadoop-2.6.0/etc/hadoop/core-site.xml
<configuration>
	<property>
		<name>fs.default.name</name>
		<value>hdfs://locahost:54310 </value>
	</property>
	<property>
		<name>hadoop.tmp.dir</name>
		<value>/home/hadoop/tmp</value>
	</property>
	<property>
		<name>hadoop.proxyuser.hdfs.hosts</name>
		<value>*</value>
	</property>
	<property>
		<name>hadoop.proxyuser.hdfs.groups</name>
		<value>*</value>
	</property>
	<property>
     		 <name>hadoop.proxyuser.oozie.hosts</name>                                  
     		 <value>*</value>
 </property>
 	<property>
      		<name>hadoop.proxyuser.oozie.groups</name>
      		<value>*</value>
 	</property>
</configuration>
```
```
* vi /home/hadoop/hadoop-2.6.0/etc/hadoop/hdfs-site.xml
<configuration>
	<property>
		<name>dfs.permissions</name>
		<value>false</value>
	</property>
	<property>
		<name>dfs.replication</name>
		<value>1</value>
	</property>
	<property>
		<name>dfs.name.dir</name>
		<value>/home/hadoop/dfs/name</value>
	</property>
	<property>
		<name>dfs.data.dir</name>
		<value>/home/hadoop/dfs/data</value>
	</property>
</configuration>
```
```
* cp /home/hadoop/hadoop-2.6.0/etc/hadoop/mapred-site.xml.template /home/hadoop/hadoop-2.6.0/etc/hadoop/mapred-site.xml
```
```
* vi /home/hadoop/hadoop-2.6.0/etc/hadoop/mapred-site.xml
<configuration>
	<property>
		<name>mapred.job.tracker</name>
		<value>localhost:54311</value>
	</property>
	<property>
		<name>mapred.framework.name</name>
		<value>yarn </value>
	</property>
</configuration>
```
```
* vi /home/hadoop/hadoop-2.6.0/etc/hadoop/yarn-site.xml
<configuration>
	<property>
      		<name>yarn.nodemanager.aux-services</name>
     		 <value>mapreduce_shuffle</value>
</property>
<property>
      		<name>yarn.nodemanager.aux-services.mapreduce.shuffle.class</name>
     		 <value>org.apache.hadoop.mapred.ShuffleHandler</value>
</property>
</configuration>
```
```
* /home/hadoop/hadoop-2.6.0/bin/hadoop namenode –format
```
```
* /home/hadoop/hadoop-2.6.0/sbin/start-dfs.sh
```
```
* Jps
```
27187 Datanode
27395 SecondaryNameNode
27019 NameNode
