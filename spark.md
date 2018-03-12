# Spark Installation

Here are the commands to install spark 

```
wget http://d3kbcqa49mib13.cloudfront.net/spark-1.6.1.tgz
```
```
tar xvf spark-1.6.1.tgz
```
```
cd spark-1.6.1
```
```
sbt/sbt assembly
```
```
cp conf/spark-env.sh.template conf/spark-env.sh
```
```
vi conf/spark-env.sh
```
```
SPARK_LOCAL_IP=127.0.0.1
```
```
./bin/run-example SparkPi 10
```
```
sparkR
```
```
vi conf/spark-defaults.conf
    spark.master                        spark://locahost:7077
    spark.eventlog.enabled        true
    spark.eventlog.dir                 /home/roopteja/spark-1.6.1/eventlog
```
