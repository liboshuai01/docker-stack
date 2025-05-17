## 前提准备

1. 在数据库中执行`tables_xxl_job.sql`文件的所有语句。
2. 修改`.env`中的变量为你的实际数据。

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

> 默认账号密码：admin/123456

浏览器访问`http://${HOST_IP}:8181/xxl-job-admin:`，出现xxl-job-admin页面即表示成功。
