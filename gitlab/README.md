## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

> 必须修改配置`GITLAB_HOSTNAME`为宿主机IP或域名。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export TEMP_PORT=$(awk -F= '/^HOST_HTTP_PORT=/ {print $2}' .env) && \
curl 127.0.0.1:${TEMP_PORT}
```

> `gitlab`启动速度较慢，请耐心等待。
