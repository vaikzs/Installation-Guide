# JDK installation
```
sudo apt-add-repository ppa:webupd8team/java
```
```
sudo apt-get update
```
```
sudo apt-get install oracle-java8-installer
```
```
java –version (to check)
```
```
java 9 not compatible with scala, 
```
```
sudo update-alternatives –remove-all java
```
```
sudo update-alternatives –remove-all javac
```
```
sudo update-alternatives –remove-all javaws
```
```
sudo rm –rf  /usr/lib/jvm/*
```
```
export JAVA_HOME=/usr/lib/jvm/java-8-oracle
```
```
export PATH=$PATH:$JAVA_HOME/bin
```