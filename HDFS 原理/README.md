# HDFS 原理

目标缘由：硬件经常错误，寿命短，因此需要冗余也是嵌入了备份多个数据。对大数据进行规模一致性模型，一写入就不能修改，只能删除在重发。

### 1. HDFS体系

* NameNode
* DataNode
* 事务日志
* 映像文件
* SecondaryNameNode

![img](HDFS体系结构.png)

