## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

```shell
# 启动一个临时的mongo容器，用于验证连接mongo服务
[lbs@test mongo-standalone]$ docker run --rm -it \
>   bitnami/mongodb:4.4.2 \
>   mongo \
>   --host ${HOST_IP} \
>   --port 27018 \
>   --username lbs \
>   --password 'YOUR_PASSWORD' \
>   --authenticationDatabase starlink_risk \
>   starlink_risk
mongodb 03:31:17.50 
mongodb 03:31:17.50 Welcome to the Bitnami mongodb container
mongodb 03:31:17.51 Subscribe to project updates by watching https://github.com/bitnami/bitnami-docker-mongodb
mongodb 03:31:17.51 Submit issues and feature requests at https://github.com/bitnami/bitnami-docker-mongodb/issues
mongodb 03:31:17.51 

MongoDB shell version v4.4.2
connecting to: mongodb://192.168.6.201:27018/starlink_risk?authSource=starlink_risk&compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("502a7a67-b82d-4945-8f4e-e69bb21f6c8d") }
MongoDB server version: 4.4.2
>
```
