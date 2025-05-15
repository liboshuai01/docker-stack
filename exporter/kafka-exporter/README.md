## 前提准备

1. 修改`.env`文件中的`KAFKA_SERVER_0x`值为你的各个Kafka节点地址，例如：192.168.1.1:9020。

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

访问`kafka-exporter`服务，确保正常返回html页面即可。
```shell
[lbs@test kafka-exporter]$  curl -X GET "http://localhost:9308"
<html>
                <head><title>Kafka Exporter</title></head>
                <body>
                <h1>Kafka Exporter</h1>
                <p><a href='/metrics'>Metrics</a></p>
                </body>
                </html>
```
