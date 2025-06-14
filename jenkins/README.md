## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

浏览器访问`http://${HOST_IP}:28080`，出现jenkins页面即表示成功。

> 唯一生成的密码可以在卷内的 secrets/initialAdminPassword 文件中找到.