## 前提准备

1. 修改`.env`文件中的`HOST_IP`值为你的宿主机IP，例如：192.168.1.1。

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

进入`kafka`容器中，查询`broker`在线状态：
```shell
# 宿主机中执行
[lbs@test kafka-standalone]$ docker-compose exec kafka bash
# 进入容器后执行
I have no name!@6becd92b141e:/$ zookeeper-shell.sh zookeeper:2181 ls /brokers/ids
Connecting to zookeeper:2181

WATCHER::

WatchedEvent state:SyncConnected type:None path:null
[1001]
```
