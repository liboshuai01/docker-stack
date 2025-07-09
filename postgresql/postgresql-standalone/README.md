## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

> 推荐修改`PostgreSQL 初始化配置`为自定义值。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export TEMP_PASSWORD=$(awk -F= '/^POSTGRESQL_POSTGRES_PASSWORD=/ {print $2}' .env) && \
docker-compose exec -e PGPASSWORD="${TEMP_PASSWORD}" postgresql-standalone psql -U postgres -c "\\l"
```
