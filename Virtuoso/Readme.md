# Virtuoso Installation

Here are the commands to install virtuoso 

```
* https://logd.tw.rpi.edu/tutorial/installing_using_virtuoso_sparql_endpoint
```
```
* Download tar from https://sourceforge.net/projects/virtuoso/
```
* tar xvzf virtuoso/virtuoso-opensource-7.2.4.2.tar.gz -C virtuoso/
```
```
* sudo apt-get install autoconf
```
```
* sudo apt-get install automake
```
```
* sudo apt-get install libtool
```
```
* sudo apt-get install flex
```
```
* sudo apt-get install bison
```
```
* sudo apt-get install gperf
```
```
* sudo apt-get install gawk
```
```
* sudo apt-get install m4
```
```
* sudo apt-get install build-essential //make
```
```
* sudo apt-get install openssl
```
```
* sudo apt-get install libssl-dev
```
```
* CFLAGS="-O2 -m64"
```
```
* export CFLAGS
```
```
* cd virtuoso/virtuoso-opensource-7.2.4.2/
```
```
* ./autogen.sh
```
```
* ./configure
```
##
Virtuoso Open Source Edition (Column Store) 7.2.4.2 configuration summary
================================================================
Installation variables
layout                  	default
prefix                  	/usr/local/virtuoso-opensource
exec_prefix            	${prefix}
Installation paths
programs                	${exec_prefix}/bin
include files           	${prefix}/include
libraries               	${exec_prefix}/lib
manual pages            	${datarootdir}/man
vad packages            	${datarootdir}/virtuoso/vad
database                	${prefix}/var/lib/virtuoso/db
hosting                 	${exec_prefix}/lib/virtuoso/hosting
Options
BUILD_OPTS             xml ssl imsg pldebug bz2 pthreads
```
sudo make install
```
```
* cd /usr/local/virtuoso-opensource/var/lib/virtuoso/db
```
```
* sudo usr/local/virtuoso-opensource/bin/virtuoso-t -f
```
```
* http://ipaddress:8890/sparql
```
```
* /usr/local/virtuoso-opensource/bin/isql 1111 dba dba
```
	isql> select * from DB.DBA.load_list;
 	isql> delete from DB.DBA.load_list;
	isql> ld_dir('/usr/local/virtuoso-opensource/share/virtuoso/vad/files','rdf files','graphname');
 	isql> rdf_loader_run();
 	isql> sparql clear graph <graphname>;

