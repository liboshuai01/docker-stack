## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export TEMP_PORT=$(awk -F= '/^PANEL_APP_PORT_HTTP=/ {print $2}' .env) && \
curl 127.0.0.1:${TEMP_PORT}
```
