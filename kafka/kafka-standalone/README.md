## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

> 必须修改配置`KAFKA_IP`为对应实际值。

## 启动服务

```bash
docker-compose up -d
```

## 验证服务

```bash
export TEMP_IP=$(awk -F= '/^KAFKA_IP=/ {print $2}' .env) && \
export TEMP_PORT=$(awk -F= '/^HOST_KAFKA_PORT=/ {print $2}' .env) && \
docker-compose exec kafka kafka-topics.sh --create --bootstrap-server ${TEMP_IP}:${TEMP_PORT} --topic test_topic && \
docker-compose exec kafka kafka-topics.sh --list --bootstrap-server ${TEMP_IP}:${TEMP_PORT}
```
