[TOC]

##### 1.修改flume-env.sh文件

```
export JAVA_HOME=/home/hadoop/jdk1.8.0_45
```

##### 2.修改flume-conf.properties

#####3.复制hadoopjar包

```
[hadoop@hadoop apache-flume-1.6.0-bin]$ cp ~/app/hadoop-2.6.0/share/hadoop/common/*.jar lib/
[hadoop@hadoop apache-flume-1.6.0-bin]$ cp ~/app/hadoop-2.6.0/share/hadoop/common/lib/*.jar lib/
[hadoop@hadoop apache-flume-1.6.0-bin]$ cp ~/app/hadoop-2.6.0/share/hadoop/hdfs/*.jar lib/
```

##### 4.启动flume

```
nohup bin/flume-ng agent --conf conf --conf-file conf/flume-conf.properties --name a1 -Dflume.root.logger=INFO,console &
```

