## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

> 推荐修改`Rdis 初始化配置`为自定义值。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export REDIS_PASSWORD=$(awk -F= '/^REDIS_PASSWORD=/ {print $2}' .env)
docker-compose exec redis-standalone redis-cli -a "${REDIS_PASSWORD}" INFO
```
