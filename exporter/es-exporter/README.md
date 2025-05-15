## 前提准备

1. 修改`.env`文件中的`ES_IP`值为你的ES任意节点IP。
2. 修改`.env`文件中的`ES_PORT`值为你的ES任意节点PORT。

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

检查集群健康状况，确保`status`为`green`：
```shell
[lbs@test es]$ curl -X GET "http://localhost:9200/_cluster/health?pretty"
{
  "cluster_name" : "docker-cluster",
  "status" : "green",
  "timed_out" : false,
  "number_of_nodes" : 1,
  "number_of_data_nodes" : 1,
  "active_primary_shards" : 0,
  "active_shards" : 0,
  "relocating_shards" : 0,
  "initializing_shards" : 0,
  "unassigned_shards" : 0,
  "delayed_unassigned_shards" : 0,
  "number_of_pending_tasks" : 0,
  "number_of_in_flight_fetch" : 0,
  "task_max_waiting_in_queue_millis" : 0,
  "active_shards_percent_as_number" : 100.0
}
```