## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

> 推荐修改配置`DOCKGE_STACKS_DIR`为自定义路径。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export TEMP_PORT=$(awk -F= '/^HOST_PORT=/ {print $2}' .env) && \
curl 127.0.0.1:${TEMP_PORT}
```
