[TOC]

#### 1.修改xml配置文件 /etc/hadoop

#### 2.修改/etc/hadoop/hadoop-env.sh中java home

#### 3.配置ssh互信

```shell
sudo apt-get install openssh-server
sudo apt-get install openssh-client

cd ~/.ssh               # 如果没有该目录，先执行一次ssh localhost
rm ./id_rsa*            # 删除之前生成的公匙（如果有）
ssh-keygen -t rsa 
cat ./id_rsa.pub >> ./authorized_keys
```

#### 4.java home hadoop home

```

sudo gedit /etc/profile

//在末尾写上 注意hadoop地址
HADOOP_HOME=/usr/local/hadoop
PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
export HADOOP_HOME PATH

$JAVA_HOME
sudo gedit /etc/profile
//在文件最末尾添加
export JAVA_HOME=/usr/lib/jdk1.8.0_121
export CLASSPATH=.:$JAVA_HOME/lib:$JAVA_HOME/jre/lib:$CLASSPATH
export PATH=$JAVA_HOME/bin:$JAVA_HOME/jre/bin:$PATH

sudo java  command not found
sudo update-alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_121/bin/javac 50
sudo update-alternatives --install /usr/bin/java java /opt/jdk1.8.0_121/bin/java 50
```

#### 5.修改hosts文件

```
sudo gedit /etc/hosts
ip hostname
```



#### 6.开启hadoop

```
hadoop namenode -format
start-all.sh
stop-all.sh
```

