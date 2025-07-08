## 配置环境

1. 在mysql中执行`tables_xxl_job.sql`文件的所有语句。

2. 复制文件`.env.example`为`.env`，并根据需求修改配置。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

> 默认账号密码：admin/123456

```bash
export TEMP_PORT=$(awk -F= '/^HOST_PORT=/ {print $2}' .env) && \
curl 127.0.0.1:${TEMP_PORT}
```
