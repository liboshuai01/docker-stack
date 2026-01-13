## 配置环境

复制文件`.env.example`为`.env`，并根据需求修改配置。

## 启动服务

```bash
docker-compose up -d
```

## 配置服务

**1. 进入`wiki`容器**
```bash
docker-compose exec wiki bash
```

**2. 修改`postgres`分页配置**
```bash
vi /wiki/server/modules/search/postgres/definition.yml

# 修改文件内容如下
# 前面内容省略
props:
  dictLanguage:
    type: String
    title: Dictionary Language
    hint: Language to use when creating and querying text search vectors.
    default: english
    enum:
      ......
      ......
      ......
      - swedish
      - turkish
      - chinese_zh # 新增此行内容
    order: 1
```

## 验证服务

```bash
export TEMP_PORT=$(awk -F= '/^PANEL_APP_PORT_HTTP=/ {print $2}' .env) && \
curl 127.0.0.1:${TEMP_PORT}
```
