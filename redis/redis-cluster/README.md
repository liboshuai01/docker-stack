## 前提准备

1. 修改`.env`文件中的`HOST_IP`值为你的宿主机IP，例如：192.168.1.1。

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

浏览器访问`http://${HOST_IP}:46000`，出现open-wen-ui页面即表示成功。
