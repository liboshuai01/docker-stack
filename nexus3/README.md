## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export TEMP_PORT=$(awk -F= '/^HOST_PORT=/ {print $2}' .env) && \
curl 127.0.0.1:${TEMP_PORT}
```

> 部署过程较长，请耐心等待。

## 获取admin密码

```bash
docker-compose exec nexus3 cat /nexus-data/admin.password
```
