## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
docker-compose exec kafka zkCli.sh -server 127.0.0.1:2181 stat /
```
