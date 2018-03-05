# Installations

## JDK installation
```
* sudo apt-add-repository ppa:webupd8team/java
```
```
* sudo apt-get update
```
```
* sudo apt-get install oracle-java8-installer
```
```
* java –version (to check)
```
```
* java 9 not compatible with scala, 
```
```
* sudo update-alternatives –remove-all java
```
```
* sudo update-alternatives –remove-all javac
```
```
* sudo update-alternatives –remove-all javaws
```
```
* sudo rm –rf  /usr/lib/jvm/*
```
```
* export JAVA_HOME=/usr/lib/jvm/java-8-oracle
```
```
* export PATH=$PATH:$JAVA_HOME/bin
```

## Tomcat Installation

```
* sudo apt-get install tomcat7
```
```
* sudo vi /etc/default/tomcat7
```
	JAVA_HOME=/usr/lib/jvm/java-8-oracle
	JAVA_OPTS="-Djava.security.egd=file:/dev/./urandom -Djava.awt.headless=true -Xmx512m -XX:MaxPermSize=256m -XX:+UseConcMarkSweepGC"
```
* sudo vi /etc/tomcat7/server.xml
```
	<connector port=”9090” …… />
```
* sudo vi /etc/tomcat7/tomcat-users.xml
```
	<user username=”roopteja” password=”password” roles=”manager-gui,admin-gui”/>
```
* sudo service tomcat7 restart
```

## Glassfish Installation

```
* wget download.java.net/glassfish/4.0/release/glassfish-4.0.zip
```
```
* sudo apt-get install unzip
```
```
* unzip glassfish-4.0.zip
```
```
* export PATH=$PATH:/home/glassfish4/bin
```
```
* vi /home/glassfish4/glassfish/domains/domain1/config/domain.xml
```
```
* Search for port 8080 and chage to 9190 and secondary port to 9191
```
```
* asadmin set server-config.network-config.protocols.protocol.http-listener-1.http.request-timeout-seconds=-1
```
```
* /home/glassfish4/bin/asadmin start-domain
```
```
* /home/glassfish4/bin/asadmin deploy example.war
```

## Scala Installation

```
* sudo apt-get remove scala-library scala
```
```
* sudo wget http://www.scala-lang.org/files/archive/scala-2.11.8.deb
```
```
* sudo dpkg -i scala-2.11.8.deb
```
```
* sudo apt-get update
```
```
* sudo apt-get install scala
```
```
* wget http://dl.bintray.com/sbt/debian/sbt-0.13.11.deb
```
```
* sudo dpkg -i sbt-0.13.11.deb 
```
```
* sudo apt-get update
```
```
* sudo apt-get install sbt
```
```
* scala –version 
```
```
* export SCALA_HOME=/usr/lib/scala/scala-2.11.8
```
```
* export PATH=$PATH:$SCALA_HOME/bin
```

## Python 

```
* wget http://repo.continuum.io/archive/Anaconda2-4.0.0-Linux-x86_64.sh
```
```
* bash ./Anaconda2-4.0.0-Linux-x86_64.sh
```
```
* conda update –all –yes
```
```
* python –version
```
```
* pip install tweepy
```

## Git installation

```
* sudo apt-get install git
```

## Maven installation

```
* sudo apt-get install maven
```

## R installation

```
* sudo apt-get update 
```
```
* sudo apt-get install r-base r-base-dev
```

## MongoDB Installation

```
* sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
```
```
* echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
```
```
* sudo apt-get update
```
```
* sudo apt-get install -y mongodb-org
```
```
* sudo service mongod start
```
Check /var/log/mongodb/mongod.log for a line reading [initandlisten] waiting for connections on port <port> where <port> is the port configured in /etc/mongod.conf, 27017 by default.

