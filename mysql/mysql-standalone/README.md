## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export MYSQL_ROOT_PASSWORD=$(awk -F= '/^MYSQL_ROOT_PASSWORD=/ {print $2}' .env.example)
docker-compose exec -e MYSQL_PWD="${MYSQL_ROOT_PASSWORD}" mysql-standalone mysql -u root -e "SHOW DATABASES;"
```
