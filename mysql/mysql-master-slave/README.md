## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

```shell
# 安装mysql客户端（如果已安装，则跳过此步骤即可）
[lbs@test mysql-803]$ sudo yum install -y mysql
# 通过mysql客户端连接docker中的mysql服务
[lbs@test mysql-803]$ mysql -h ${HOST_IP} -P 3308 -u root -p
```
