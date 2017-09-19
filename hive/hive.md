[TOC]

#### 1.安装mysql

```
sudo apt-get install mysql-server
apt-get isntall mysql-client
sudo apt-get install libmysqlclient-dev
```

#### 2.配置hive home

```
HIVE_HOME=/usr/software/hive-1.2.2
export PATH=$PATH:$HIVE_HOME/bin
```

#### 3.配置hive-site.xml

#### 4.修改hive-env.sh

```
export HADOOP_HEAPSIZE=1024 
# Set HADOOP_HOME to point to a specific hadoop install directory 
HADOOP_HOME=/home/hadoop/hadoop-2.4.1 
# Hive Configuration Directory can be controlled by: 
export HIVE_CONF_DIR=/home/hadoop/apache-hive-1.0.0-bin/conf 
# Folder containing extra ibraries required for hive compilation/execution can be controlled by: 
export HIVE_AUX_JARS_PATH=/home/hadoop/apache-hive-1.0.0-bin/lib
```

#### 5. 拷贝mysql-connector-java-***-bin.jar到hive 的lib下面

#### 6.把jline-2.12.jar拷贝到hadoop相应的目录下，替代jline-0.9.94.jar

```
cp /usr/software/hive-1.2.2/lib/jline-2.12.jar /usr/software/hadoop/share/hadoop/yarn/lib/
```

#### 7.在mysql中创建hive数据库

```
create database hive;
```



#### 8.配置mysql远程连接

```
/etc/mysql/mysql.conf.d/mysqld.cnf         #bind_address=127.0.0.1，将其注释掉。
```

#### 9.解析json 

```
cp json-serde-1.3.6-SNAPSHOT-jar-with-dependencies.jar /usr/software/hive-1.2.2/lib
建表：
	create table user_movie(custid string, movieid string, activity string, recommended string, time string, price string, rating string, position string) ROW FORMAT SERDE 'org.openx.data.jsonserde.JsonSerDe'  STORED AS TEXTFILE;
```

