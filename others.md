## Python 

```
wget http://repo.continuum.io/archive/Anaconda2-4.0.0-Linux-x86_64.sh
```
```
bash ./Anaconda2-4.0.0-Linux-x86_64.sh
```
```
conda update –all –yes
```
```
python –version
```
```
pip install tweepy
```

## Git installation

```
sudo apt-get install git
```

## Maven installation

```
sudo apt-get install maven
```

## R installation

```
sudo apt-get update 
```
```
sudo apt-get install r-base r-base-dev
```

## MongoDB Installation

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
```
```
echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
```
```
sudo apt-get update
```
```
sudo apt-get install -y mongodb-org
```
```
sudo service mongod start
	Check /var/log/mongodb/mongod.log for a line reading [initandlisten] waiting 
	for connections on port <port> where <port> is the port configured 
	in /etc/mongod.conf, 27017 by default.
```

