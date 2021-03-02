 

# IoTDB
[![Build Status](https://www.travis-ci.org/apache/incubator-iotdb.svg?branch=master)](https://www.travis-ci.org/apache/incubator-iotdb)
[![codecov](https://codecov.io/gh/thulab/incubator-iotdb/branch/master/graph/badge.svg)](https://codecov.io/gh/thulab/incubator-iotdb)
[![GitHub release](https://img.shields.io/github/release/apache/incubator-iotdb.svg)](https://github.com/apache/incubator-iotdb/releases)
[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)
![](https://github-size-badge.herokuapp.com/apache/incubator-iotdb.svg)
![](https://img.shields.io/github/downloads/apache/incubator-iotdb/total.svg)
![](https://img.shields.io/badge/platform-win10%20%7C%20macox%20%7C%20linux-yellow.svg)
![](https://img.shields.io/badge/java--language-1.8-blue.svg)
[![IoTDB Website](https://img.shields.io/website-up-down-green-red/https/shields.io.svg?label=iotdb-website)](https://iotdb.apache.org/)

# Overview

IoTDB (Internet of Things Database) is a data management system for time series data, which can provide users specific services, such as, data collection, storage and analysis. Due to its light weight structure, high performance and usable features together with its seamless integration with the Hadoop and Spark ecology, IoTDB meets the requirements of massive dataset storage, high throughput data input and complex data analysis in the industrial IoTDB field.

# Main Features

Main features of IoTDB are as follows:

1. Flexible deployment strategy. IoTDB provides users a one-click installation tool on either the cloud platform or the terminal devices, and a data synchronization tool bridging the data on cloud platform and terminals.
2. Low cost on hardware. IoTDB can reach a high compression ratio of disk storage.
3. Efficient directory structure. IoTDB supports efficient organization for complex time series data structure from intelligent networking devices, organization for time series data from devices of the same type, fuzzy searching strategy for massive and complex directory of time series data.
4. High-throughput read and write. IoTDB supports millions of low-power devices' strong connection data access, high-speed data read and write for intelligent networking devices and mixed devices mentioned above.
5. Rich query semantics. IoTDB supports time alignment for time series data across devices and sensors, computation in time series field (frequency domain transformation) and rich aggregation function support in time dimension.
6. Easy to get started. IoTDB supports SQL-Like language, JDBC standard API and import/export tools which is easy to use.
7. Seamless integration with state-of-the-practice Open Source Ecosystem. IoTDB supports analysis ecosystems such as, Hadoop, Spark, and visualization tool, such as, Grafana.

For the latest information about IoTDB, please visit [IoTDB official website](https://iotdb.apache.org/). If you encounter any problems or identify any bugs while using IoTDB, please report an issue in [jira](https://issues.apache.org/jira/projects/IOTDB/issues).

 

## Outline

- Quick Start
 - Prerequisites
 - Installation
    - Build from source
       - Configurations
 - Start
    - Start IoTDB
    - Use IoTDB
       - Use Cli
       - Basic commands for IoTDB
    - Stop IoTDB
 - Only build server
 - Only build client
 - Usage of import-csv.sh
    - Create metadata
    - An Example of import csv file
    - Run import shell
    - Error data file
 - Usage of export-csv.sh
    - Run export shell
    - Input query

 

# Quick Start

This short guide will walk you through the basic process of using IoTDB. For a more detailed introduction, please visit our website's [User Guide](https://iotdb.apache.org/#/Documents/0.10.0/chap1/sec1).

## Prerequisites

To use IoTDB, you need to have:

1. Java >= 1.8 (1.8, 11, and 13 are verified. Please make sure the environment path has been set accordingly).
2. Maven >= 3.1 (If you want to compile and install IoTDB from source code).
3. Set the max open files num as 65535 to avoid "too many open files" error.

## Installation

IoTDB provides three installation methods, you can refer to the following suggestions, choose the one fits you best:

* Installation from source code. If you need to modify the code yourself, you can use this method.
* Installation from binary files. Download the binary files from the official website. This is the recommended method, in which you will get a binary released package which is out-of-the-box.(Comming Soon...)
* Using Docker：The path to the dockerfile is https://github.com/apache/incubator-iotdb/blob/master/docker/Dockerfile


Here in the Quick Start, we give a brief introduction of using source code to install IoTDB. For further information, please refer to Chapter 4 of the User Guide.

## Build from source

You can download the source code from:

```
git clone https://github.com/apache/incubator-iotdb.git
```

Under the root path of incubator-iotdb:

```
> mvn clean package -DskipTests
```

Then the binary version (including both server and client) can be found at **distribution/target/apache-iotdb-{project.version}-incubating-bin.zip**

> NOTE: Directories "service-rpc/target/generated-sources/thrift" and "server/target/generated-sources/antlr3" need to be added to sources roots to avoid compilation errors in the IDE.

### Configurations

configuration files are under "conf" folder

  * environment config module (`iotdb-env.bat`, `iotdb-env.sh`),
  * system config module (`tsfile-format.properties`, `iotdb-engine.properties`)
  * log config module (`logback.xml`).

For more information, please see [Chapter3: Server](https://iotdb.apache.org/#/Documents/progress/chap3/sec1) and [Chapter4: Client](https://iotdb.apache.org/#/Documents/progress/chap4/sec1) in detail.

## Start

You can go through the following steps to test the installation, if there is no error returned after execution, the installation is completed.

### Start IoTDB

Users can start IoTDB by the start-server script under the sbin folder.

```
# Unix/OS X
> sbin/start-server.sh

# Windows
> sbin\start-server.bat
```


### Use IoTDB

#### Use Cli

IoTDB offers different ways to interact with server, here we introduce the basic steps of using Cli tool to insert and query data.

After installing IoTDB, there is a default user 'root', its default password is also 'root'. Users can use this
default user to login Cli to use IoTDB. The startup script of Cli is the start-client script in the folder sbin. When executing the script, user should assign
IP, PORT, USER_NAME and PASSWORD. The default parameters are "-h 127.0.0.1 -p 6667 -u root -pw -root".

Here is the command for starting the Cli:

```
# Unix/OS X
> sbin/start-client.sh -h 127.0.0.1 -p 6667 -u root -pw root

# Windows
> sbin\start-client.bat -h 127.0.0.1 -p 6667 -u root -pw root
```

The command line client is interactive, so you should see the welcome logo and statements if everything is ready:

```
 _____       _________  ______   ______
|_   _|     |  _   _  ||_   _ `.|_   _ \
  | |   .--.|_/ | | \_|  | | `. \ | |_) |
  | | / .'`\ \  | |      | |  | | |  __'.
 _| |_| \__. | _| |_    _| |_.' /_| |__) |
|_____|'.__.' |_____|  |______.'|_______/  version x.x.x


IoTDB> login successfully
IoTDB>
```

#### Basic commands for IoTDB

Now, let us introduce the way of creating timeseries, inserting data and querying data.

The data in IoTDB is organized as timeseries. Each timeseries includes multiple data-time pairs, and is owned by a storage group. Before defining a timeseries, we should define a storage group using SET STORAGE GROUP first, and here is an example:

```
IoTDB> SET STORAGE GROUP TO root.ln
```

We can also use SHOW STORAGE GROUP to check the storage group being created:

```
IoTDB> SHOW STORAGE GROUP
+-----------------------------------+
|                      Storage Group|
+-----------------------------------+
|                            root.ln|
+-----------------------------------+
storage group number = 1
```

After the storage group is set, we can use CREATE TIMESERIES to create a new timeseries. When creating a timeseries, we should define its data type and the encoding scheme. Here We create two timeseries:

```
IoTDB> CREATE TIMESERIES root.ln.wf01.wt01.status WITH DATATYPE=BOOLEAN, ENCODING=PLAIN
IoTDB> CREATE TIMESERIES root.ln.wf01.wt01.temperature WITH DATATYPE=FLOAT, ENCODING=RLE
```

In order to query the specific timeseries, we can use SHOW TIMESERIES  .   represent the location of the timeseries. The default value is "null", which queries all the timeseries in the system(the same as using "SHOW TIMESERIES root"). Here are some examples:

1. Querying all timeseries in the system:

```
IoTDB> SHOW TIMESERIES
+-------------------------------+---------------+--------+--------+
|                     Timeseries|  Storage Group|DataType|Encoding|
+-------------------------------+---------------+--------+--------+
|       root.ln.wf01.wt01.status|        root.ln| BOOLEAN|   PLAIN|
|  root.ln.wf01.wt01.temperature|        root.ln|   FLOAT|     RLE|
+-------------------------------+---------------+--------+--------+
Total timeseries number = 2
```

2. Querying a specific timeseries(root.ln.wf01.wt01.status):

```
IoTDB> SHOW TIMESERIES root.ln.wf01.wt01.status
+------------------------------+--------------+--------+--------+
|                    Timeseries| Storage Group|DataType|Encoding|
+------------------------------+--------------+--------+--------+
|      root.ln.wf01.wt01.status|       root.ln| BOOLEAN|   PLAIN|
+------------------------------+--------------+--------+--------+
Total timeseries number = 1
```

Insert timeseries data is a basic operation of IoTDB, you can use ‘INSERT’ command to finish this. Before insertion, you should assign the timestamp and the suffix path name:

```
IoTDB> INSERT INTO root.ln.wf01.wt01(timestamp,status) values(100,true);
IoTDB> INSERT INTO root.ln.wf01.wt01(timestamp,status,temperature) values(200,false,20.71)
```

The data that you have just inserted will display as follows:

```
IoTDB> SELECT status FROM root.ln.wf01.wt01
+-----------------------+------------------------+
|                   Time|root.ln.wf01.wt01.status|
+-----------------------+------------------------+
|1970-01-01T08:00:00.100|                    true|
|1970-01-01T08:00:00.200|                   false|
+-----------------------+------------------------+
Total line number = 2
```

You can also query several timeseries data using one SQL statement:

```
IoTDB> SELECT * FROM root.ln.wf01.wt01
+-----------------------+--------------------------+-----------------------------+
|                   Time|  root.ln.wf01.wt01.status|root.ln.wf01.wt01.temperature|
+-----------------------+--------------------------+-----------------------------+
|1970-01-01T08:00:00.100|                      true|                         null|
|1970-01-01T08:00:00.200|                     false|                        20.71|
+-----------------------+--------------------------+-----------------------------+
Total line number = 2
```

The commands to exit the Cli are:

```
IoTDB> quit
or
IoTDB> exit
```

For more information about the commands supported by IoTDB SQL, please see [Chapter 5: IoTDB SQL Documentation](https://iotdb.apache.org/#/Documents/0.10.0/chap5/sec1).

### Stop IoTDB

The server can be stopped with "ctrl-C" or the following script:

```
# Unix/OS X
> sbin/stop-server.sh

# Windows
> sbin\stop-server.bat
```

## Only build server

Under the root path of incubator-iotdb:

```
> mvn clean package -pl server -am -DskipTests
```

After being built, the IoTDB server is located at the folder: "server/target/iotdb-server-{project.version}".


## Only build client

Under the root path of incubator-iotdb:

```
> mvn clean package -pl client -am -DskipTests
```

After being built, the IoTDB client is located at the folder "client/target/iotdb-client-{project.version}".

## Usage of import-csv.sh

### Create metadata
```
SET STORAGE GROUP TO root.fit.d1;
SET STORAGE GROUP TO root.fit.d2;
SET STORAGE GROUP TO root.fit.p;
CREATE TIMESERIES root.fit.d1.s1 WITH DATATYPE=INT32,ENCODING=RLE;
CREATE TIMESERIES root.fit.d1.s2 WITH DATATYPE=TEXT,ENCODING=PLAIN;
CREATE TIMESERIES root.fit.d2.s1 WITH DATATYPE=INT32,ENCODING=RLE;
CREATE TIMESERIES root.fit.d2.s3 WITH DATATYPE=INT32,ENCODING=RLE;
CREATE TIMESERIES root.fit.p.s1 WITH DATATYPE=INT32,ENCODING=RLE;
```

### An example of import csv file

```
Time,root.fit.d1.s1,root.fit.d1.s2,root.fit.d2.s1,root.fit.d2.s3,root.fit.p.s1
1,100,'hello',200,300,400
2,500,'world',600,700,800
3,900,'IoTDB',1000,1100,1200
```

### Run import shell
```
# Unix/OS X
> tools/import-csv.sh -h   -p   -u   -pw   -f  

# Windows
> tools\import-csv.bat -h   -p   -u   -pw   -f  
```

### Error data file

`csvInsertError.error`

## Usage of export-csv.sh

### Run export shell
```
# Unix/OS X
> tools/export-csv.sh -h   -p   -u   -pw   -td   [-tf  ]

# Windows
> tools\export-csv.bat -h   -p   -u   -pw   -td   [-tf  ]
```

### Input query

```
select * from root.fit.d1
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)