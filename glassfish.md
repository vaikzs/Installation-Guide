## Glassfish Installation

```
wget download.java.net/glassfish/4.0/release/glassfish-4.0.zip
```
```
sudo apt-get install unzip
```
```
unzip glassfish-4.0.zip
```
```
export PATH=$PATH:/home/glassfish4/bin
```
```
vi /home/glassfish4/glassfish/domains/domain1/config/domain.xml
	Search for port 8080 and chage to 9190 and secondary port to 9191
```
```
asadmin set server-config.network-config.protocols.protocol.http-listener-1.http.request-timeout-seconds=-1
```
```
/home/glassfish4/bin/asadmin start-domain
```
```
/home/glassfish4/bin/asadmin deploy example.war
```