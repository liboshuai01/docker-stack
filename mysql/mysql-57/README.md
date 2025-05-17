## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

```shell
[lbs@test mysql-57]$ docker run --rm -it \
> docker.io/bitnami/mysql:5.7.42 \
> mysql -h ${HOST_IP} -P 3307 -u lbs -pYOUR_PASSWORD
mysql 03:38:12.61 
mysql 03:38:12.61 Welcome to the Bitnami mysql container
mysql 03:38:12.61 Subscribe to project updates by watching https://github.com/bitnami/containers
mysql 03:38:12.61 Submit issues and feature requests at https://github.com/bitnami/containers/issues
mysql 03:38:12.61 

mysql: [Warning] Using a password on the command line interface can be insecure.
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 13
Server version: 5.7.42 MySQL Community Server (GPL)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| test               |
+--------------------+
2 rows in set (0.00 sec)
```
