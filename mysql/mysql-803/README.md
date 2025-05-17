## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

```shell
[lbs@test mysql-803]$ docker run --rm -it \
> bitnami/mysql:8.0.39 \
> mysql -h ${HOST_IP} -P 3308 -u lbs -pYOUR_PASSWORD
mysql 03:46:33.41 INFO  ==> 
mysql 03:46:33.41 INFO  ==> Welcome to the Bitnami mysql container
mysql 03:46:33.41 INFO  ==> Subscribe to project updates by watching https://github.com/bitnami/containers
mysql 03:46:33.41 INFO  ==> Submit issues and feature requests at https://github.com/bitnami/containers/issues
mysql 03:46:33.41 INFO  ==> Upgrade to Tanzu Application Catalog for production environments to access custom-configured and pre-packaged software components. Gain enhanced features, including Software Bill of Materials (SBOM), CVE scan result reports, and VEX documents. To learn more, visit https://bitnami.com/enterprise
mysql 03:46:33.42 INFO  ==> 

mysql: [Warning] Using a password on the command line interface can be insecure.
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.39 Source distribution

Copyright (c) 2000, 2024, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| performance_schema |
| test               |
+--------------------+
3 rows in set (0.00 sec)
```
