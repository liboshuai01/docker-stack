## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

> 重点修改配置`PASSWORD`与`SUDO_PASSWORD`为自己的强密码。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export HOST_PORT=$(awk -F= '/^HOST_PORT=/ {print $2}' .env) && \
curl 127.0.0.1:${HOST_PORT}
```
