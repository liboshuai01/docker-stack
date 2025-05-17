## 前提准备

1. 修改`.env`中的变量为你的实际数据。

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

```shell
[lbs@test redis-cluster]$ docker run --rm -it \
> bitnami/redis-cluster:7.4.2 \
> redis-cli -c -h ${HOST_IP} -p 6381 -a YOUR_PASSWORD
redis-cluster 06:21:04.01 INFO  ==> 
redis-cluster 06:21:04.01 INFO  ==> Welcome to the Bitnami redis-cluster container
redis-cluster 06:21:04.01 INFO  ==> Subscribe to project updates by watching https://github.com/bitnami/containers
redis-cluster 06:21:04.02 INFO  ==> Did you know there are enterprise versions of the Bitnami catalog? For enhanced secure software supply chain features, unlimited pulls from Docker, LTS support, or application customization, see Bitnami Premium or Tanzu Application Catalog. See https://www.arrow.com/globalecs/na/vendors/bitnami/ for more information.
redis-cluster 06:21:04.02 INFO  ==> 

Warning: Using a password with '-a' or '-u' option on the command line interface may not be safe.
192.168.6.201:6381> cluster nodes
a39752b01bc6ab67bceb19e5f42b54de543dc71d 192.168.6.201:6382@16382 master - 0 1747462865549 2 connected 5461-10922
5f59894ddb83917d5ac86d84aae916b3cf0d98b1 192.168.6.201:6385@16385 slave b2a55e4b5125668612669c9be9e1d950950f6e3d 0 1747462866553 1 connected
8dd0bfdf1cb0eac1382275c9718261b7d2b0b98c 192.168.6.201:6386@16386 slave a39752b01bc6ab67bceb19e5f42b54de543dc71d 0 1747462864546 2 connected
97d503ffa1a96728ecfa24d851d11c1788aeb679 192.168.6.201:6383@16383 master - 0 1747462865000 3 connected 10923-16383
ede3ca943e5cf6a96ba5c55bc5f90b87f4a79829 192.168.6.201:6384@16384 slave 97d503ffa1a96728ecfa24d851d11c1788aeb679 0 1747462864000 3 connected
b2a55e4b5125668612669c9be9e1d950950f6e3d 192.168.6.201:6381@16381 myself,master - 0 0 1 connected 0-5460
```
