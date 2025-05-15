## 前提准备

1. 确保宿主机内存大于6G，否则启动会失败。

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

检查集群健康状况，确保`status`为`green`，且`number_of_nodes`为3：
```shell
[lbs@test es]$ curl -X GET "http://localhost:9201/_cluster/health?pretty"
{
  "cluster_name" : "es-docker-cluster",
  "status" : "green",
  "timed_out" : false,
  "number_of_nodes" : 3,
  "number_of_data_nodes" : 3,
  "active_primary_shards" : 0,
  "active_shards" : 0,
  "relocating_shards" : 0,
  "initializing_shards" : 0,
  "unassigned_shards" : 0,
  "delayed_unassigned_shards" : 0,
  "number_of_pending_tasks" : 18,
  "number_of_in_flight_fetch" : 0,
  "task_max_waiting_in_queue_millis" : 224,
  "active_shards_percent_as_number" : 100.0
}
```