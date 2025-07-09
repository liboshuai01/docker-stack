# 个人 Docker 应用部署方案集合

## 项目简介

本项目是一个个人使用的 Docker 容器化部署清单集合，主要包含了各种常用服务（如数据库、消息队列、监控工具、Web 应用、开发工具等）的 Docker Compose 配置文件。旨在提供一个便捷、快速的方式来部署这些服务，避免重复配置工作。

本项目就像一个“Docker 部署菜谱”，每种服务都是一道“菜”，您可以在相应的目录中找到制作（部署）这道“菜”所需的配方（`docker-compose.yaml` 和 `.env` 文件）。

## 特点

*   **一站式集合:** 收录了作者常用的多种服务的 Docker Compose 配置，持续更新。
*   **快速启动:** 每个服务通常包含 `docker-compose.yaml` 和 `.env` 文件，易于理解和快速上手部署。
*   **模块化:** 每个服务配置独立存放于自己的目录中，互不干扰，方便查找、管理和选择性部署。
*   **可定制:** 通过修改 `.env` 文件或 `docker-compose.yaml` 文件，可以轻松 Anpassung 配置，如端口映射、数据卷路径、环境变量等。

## 环境要求

在使用本项目中的配置之前，请确保您的系统已经安装了以下软件：

*   **Docker:** 容器运行时。
*   **Docker Compose:** 用于定义和运行多容器 Docker 应用的工具。
*   **设置HOST_IP环境变量**：推荐在`~/.bashrc`中添加`export HOST_IP=你的实际宿主机IP`，方便后续使用。

> 推荐安装教程: [CentOS系统指定版本Docker与Docker Compose在线安装教程](https://lbs.wiki/pages/987e17e9/)

## 项目结构

项目根目录 `docker-stack` 下包含了各个服务的独立子目录。每个服务目录的命名通常对应于服务的名称。

每个服务子目录下通常包含以下关键文件：

*   `docker-compose.yaml`: 定义了服务的容器、网络、卷等配置。
*   `.env.example`: 存储了服务可能需要的环境变量，如默认端口、用户名、密码、数据卷名称等。**在使用前，您应该根据自己的需求修改此文件。**
*   `README.md` (可选): 针对该服务的具体说明、配置细节、使用注意事项或访问方式等。**强烈建议查看该文件以获取更详细信息。**

```
docker-stack/
├── .idea/             # IDE相关文件 (可忽略)
├── service-a/         # 服务 A 目录
│   ├── .env.example
│   ├── docker-compose.yaml
│   └── README.md (可选)
├── service-b/         # 服务 B 目录
│   ├── nested-part/   # 可能存在嵌套结构
│   │   ├── .env.example
│   │   └── docker-compose.yaml
│   ├── .env.example
│   └── docker-compose.yaml
├── ...
└── README.md          # 本文件
```

## 如何使用 (部署一个服务)

要部署某个服务，请执行以下步骤：

1.  **克隆本项目** (如果尚未克隆):
    ```bash
    git clone <repository_url>
    cd docker-stack
    ```
    *请将 `<repository_url>` 替换为您的实际仓库地址。*

2.  **进入您想要部署的服务目录**:
    例如，如果您想部署 MySQL，请进入 `mysql` 目录：
    ```bash
    cd mysql
    ```
    或者部署 Doris 单机版：
    ```bash
    cd doris/doris-standalone
    ```

3.  **配置服务**:
    *   **务必**检查并根据您的实际需求修改该目录下的 `.env.example` 文件。例如，您可能需要修改服务暴露的端口、设置数据库的 root 密码或更改数据存储路径。
    *   仔细阅读该目录下的 `README.md` 文件（如果存在），它可能包含重要的配置说明和使用细节。
    *   如果需要更高级的定制，可以直接编辑 `docker-compose.yaml` 文件。

4.  **启动服务**:
    在服务目录中，运行以下命令使用 Docker Compose 启动服务：
    ```bash
    docker compose up -d
    ```
    * `-d` 参数表示在后台运行容器。*

5.  **查看服务状态**:
    您可以使用以下命令查看服务是否成功启动：
    ```bash
    docker compose ps
    ```

6.  **访问服务**:
    根据您在 `.env` 或 `docker-compose.yaml` 中配置的端口，通过浏览器或相应的客户端访问服务。具体访问方式通常会在该服务目录下的 `README.md` 中说明。

### 停止和删除服务

*   **停止服务** (保留容器但停止运行):
    在服务目录中运行：
    ```bash
    docker compose stop
    ```
*   **停止服务并移除容器** (保留数据卷):
    在服务目录中运行：
    ```bash
    docker compose down
    ```
*   **停止服务并移除容器及数据卷** (会丢失数据，请谨慎使用!):
    在服务目录中运行：
    ```bash
    docker compose down -v
    ```
