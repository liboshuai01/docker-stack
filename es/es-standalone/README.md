## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export TEMP_PORT=$(awk -F= '/^HOST_PORT=/ {print $2}' .env) && \
curl "http://localhost:${TEMP_PORT}/_cluster/health?pretty"
```
