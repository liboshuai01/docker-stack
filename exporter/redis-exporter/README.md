## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

> 必须修改配置`REDIS_ADDR`、`REDIS_PASSWORD`为对应实际值。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export HOST_PORT=$(awk -F= '/^HOST_PORT=/ {print $2}' .env)
curl 127.0.0.1:${HOST_PORT}
```
