## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

### 主节点

```bash
export MYSQL_ROOT_PASSWORD=$(awk -F= '/^MYSQL_ROOT_PASSWORD=/ {print $2}' .env.example.example)
docker-compose exec -e MYSQL_PWD="${MYSQL_ROOT_PASSWORD}" mysql-master mysql -u root -e "SHOW MASTER STATUS;"
```

### 从节点1

```bash
export MYSQL_ROOT_PASSWORD=$(awk -F= '/^MYSQL_ROOT_PASSWORD=/ {print $2}' .env.example.example)
docker-compose exec -e MYSQL_PWD="${MYSQL_ROOT_PASSWORD}" mysql-slave1 mysql -u root -e "SHOW SLAVE STATUS\G"
```

### 从节点2

```bash
export MYSQL_ROOT_PASSWORD=$(awk -F= '/^MYSQL_ROOT_PASSWORD=/ {print $2}' .env.example.example)
docker-compose exec -e MYSQL_PWD="${MYSQL_ROOT_PASSWORD}" mysql-slave2 mysql -u root -e "SHOW SLAVE STATUS\G"
```
