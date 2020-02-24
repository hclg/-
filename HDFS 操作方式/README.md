# HDFS 操作

### 1. 文件操作

* [`命令行方式`](#HDFS 操作)
* API方式

`注意`：Hadoop没有当前目录的概念，也没有cd命令

```bash
命令模式：hadoop dfs -命令
例如： hadoop dfs -ls
hadoop dfs -mkdir newtext
等等
```

上传文件：

```bash
hadoop dfs -put 
```

