## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

> 推荐修改`MongoDB 初始化配置`为自定义内容。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export TEMP_PASSWORD=$(awk -F= '/^MONGODB_ROOT_PASSWORD=/ {print $2}' .env) && \
export TEMP_PORT=$(awk -F= '/^HOST_PORT=/ {print $2}' .env) && \
docker-compose exec mongodb-standalone mongo -u root -p "${TEMP_PASSWORD}" --eval "db.version()"
```
