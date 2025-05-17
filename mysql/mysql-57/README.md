## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

```shell
# 安装mysql客户端
[lbs@test mysql-57]$ sudo yum install -y mysql
# 通过mysql客户端连接docker中的mysql服务
[lbs@test mysql-57]$ mysql -h ${宿主机IP} -P 3307 -u root -p
```
