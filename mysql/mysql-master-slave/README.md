## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

```shell
# 安装mysql客户端（如果已安装，则跳过此步骤即可）
[lbs@test mysql-master-slave]$ sudo yum install -y mysql
```

> 验证master节点

```shell
# 通过mysql客户端连接docker中的mysql-master节点
[lbs@test mysql-master-slave]$ mysql -h ${HOST_IP} -P 3310 -u root -p
# 只要这里有File/Position信息，就表示 master 的二进制日志功能是正常开启的。
mysql> SHOW MASTER STATUS\G
*************************** 1. row ***************************
             File: mysql-bin.000003
         Position: 157
     Binlog_Do_DB:
 Binlog_Ignore_DB:
Executed_Gtid_Set:
1 row in set (0.00 sec)
# 退出
mysql> exit
```

> 验证slave1节点

```shell
# 通过mysql客户端连接docker中的mysql-slave节点1
[lbs@test mysql-master-slave]$ mysql -h ${HOST_IP} -P 3311 -u root -p
# 确保Master_Host有值，Slave_IO_Running为Yes即可认为关联master节点成功
mysql> SHOW SLAVE STATUS\G
*************************** 1. row ***************************
               Slave_IO_State: Waiting for source to send event
                  Master_Host: mysql_master
                  Master_User: repl_user
                  Master_Port: 3306
                Connect_Retry: 10
              Master_Log_File: mysql-bin.000003
          Read_Master_Log_Pos: 157
               Relay_Log_File: mysql-relay-bin.000006
                Relay_Log_Pos: 373
        Relay_Master_Log_File: mysql-bin.000003
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
```

> 对于mysql-slave2节点也是相同的操作即可