# Hadoop 集群的部署与使用

### 1. Hadoop 集群中的节点类型

> 最核心的设计是海量数据提供存储的HDFS和对数据进行计算的MapReduce

####	1.1 MapReduce 的作业

1. 从磁盘或从网络读取数据，即IO密集工作
2. 计算数据，即cpu密集工作

* 性能取决于CPU、内存、网络以及存储之间的性能平衡

#### 1.2 一个基本的Hadoop集群的节点

* NameNode：负责协调集群中的数据存储
* DataNode：存储被拆分的数据块
* JobTracker：协调数据计算任务
* TaskTracker：负责执行由JobTracker指派的任务
* SecondaryNameNode：帮助NameNode收集文件系统运行的状态信息

### 2. 集群硬件配置

​	在集群中，大部分的机器设备是作为Datanode 和 TaskTracker工作的

#### 2.1 Datanode/TaskTracker的硬件规格方案：

* 4个磁盘驱动器（单盘1-2T），支持JBOD
* 2个4核CPU，至少2-2.5GHz
* 16-24GB内存
* 千兆以太网

### 3. 集群网络拓扑

* 普通的Hadoop集群结构由一个两阶网络构成
* 每个机架有30-40个服务器，1G交换机
* 在相同的机架中的节点间的宽带的总和,要大于机架间的节点间带宽总和。

![image-20200218095844493](C:\Users\黄才龙\AppData\Roaming\Typora\typora-user-images\image-20200218095844493.png)

### 4. 集群的建立与安装

​	这里选用自动化安装：参考[链接](http://dblab.xmu.edu.cn/blog/install-hadoop/)

##### 4.1 完全分布式模式的安装和配置

* 配置hosts文件

* 建立hadoop运行账户

* 配置ssh免密连入

* 下载解压hadoop

* 配置namenode，修改site文件

* 配置hadoop-env.sh

* 配置master和slaves文件

* 向各节点复制hadoop

* 格式化namenode

* 启动hadoop

* 用jps检验

  > 以上都在链接中有详细教程

