# Tomcat Installation

```
sudo apt-get install tomcat7
```
```
sudo vi /etc/default/tomcat7
	JAVA_HOME=/usr/lib/jvm/java-8-oracle
	JAVA_OPTS="-Djava.security.egd=file:/dev/./urandom -Djava.awt.headless=true -Xmx512m -XX:MaxPermSize=256m -XX:+UseConcMarkSweepGC"
```
```
sudo vi /etc/tomcat7/server.xml
	<connector port=”9090” …… />
```
```
sudo vi /etc/tomcat7/tomcat-users.xml
	<user username=”roopteja” password=”password” roles=”manager-gui,admin-gui”/>
```
```
sudo service tomcat7 restart
```