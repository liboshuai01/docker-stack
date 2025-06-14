## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

浏览器访问`http://${HOST_IP}:18081`，出现nexus3页面即表示成功。

> 默认用户是 admin，唯一生成的密码可以在卷内的 admin.password 文件中找到.
