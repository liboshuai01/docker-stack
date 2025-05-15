## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

访问`node-exporter`服务，确保正常返回html页面即可。
```shell
[lbs@test node-exporter]$ curl -X GET "http://localhost:9100"
<html lang="en">
......
......
......
</style>
  </head>
  <body>
    <header>
      <h1>Node Exporter</h1>
    </header>
......
......
......
</html>
```
