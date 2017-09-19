[TOC]

#### 1.配置hbase home

```
export HBASE_HOME=/usr/software/hbase-1.2.5
export PATH=$HBASE_HOME/bin:$PATH
```



#### 2.hbase-env.sh

+ 配置java home

+ ```
  export HBASE_MANAGES_ZK=true  #配置由hbase自己管理zookeeper，不需要单独的zookeeper。
  ```

#### 3.hbase-site.xml

```xml
  <property>
    <name>hbase.rootdir</name>
    <value>hdfs://ubuntu:9000/hbase</value>
  </property>
  <property>
    <name>hbase.cluster.distributed</name>
    <value>true</value>
  </property>
<property>  
    <name>hbase.zookeeper.property.dataDir</name>  
    <value>/usr/software/zkdata</value>  
</property> 

```

#### 4.开启

```
start-hbase.sh
jps 有9个进程
hbase shell
```

