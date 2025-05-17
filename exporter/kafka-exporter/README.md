## 前提准备

1. 修改`.env`中的变量为你的实际数据。

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
