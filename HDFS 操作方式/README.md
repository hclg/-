# HDFS 操作(Centos7环境下)
* <a href="#d1">命令行方式</a>
  * <a href="#d1_1">文件操作</a>
  * <a href="#d1_2">添加新节点</a>
* <a href="#d2">API方式</a>

### <div id = "d1">1 命令行</div>

#### <div id = "d1_1">&ensp;1.1 文件操作</div>

`注意`：Hadoop没有当前目录的概念，也没有cd命令

```bash
命令模式：hdfs dfs -命令
例如： hdfs dfs -ls /
hadoop dfs -mkdir newtext
等等
```

文件操作：

```bash
上传文件：hdfs dfs -put 源文件 传输位置（加上文件名也行）
下载文件：hdfs dfs -get 源文件 传输位置
```

查看信息：

```bash
hdfs dfsadmin -report 
#dfsadmin 分布式文件系统管理
#-report 显示空间等信息
其他命令有（都需要分布式文件管理）
#进入和退出安全模式
-safmode enter 
-safmode laeve

```

#### <div id = "d1_2">1.2 添加新节点<div>

* 安装好hadoop
* 把namenode的所有有关配置文件复制到该节点
* 修改master和slaves文件，添加该节点
* 设置ssh免密登陆
* 单独该节点上的datanode和tasktracker(hadoop-daemon.start dunxing atanode/tasktracker)
* 运行start-balancer.sh进行数据负载均衡

> 负载均衡->
>
> ```bash
> start-balancer.sh
> ```

### <div id = "d2">2. API方式</div>

网站：[传送门](hadoop.apache.org)