## 前提准备

无

## 启动服务

```shell
docker-compose up -d
```

## 验证服务

```shell
[lbs@test redis-standalone]$ docker run --rm -it \
> bitnami/redis:7.4.2 \
> redis-cli -h ${HOST_IP} -p 6379 -a YOUR_PASSWORD
redis 06:29:27.09 INFO  ==> 
redis 06:29:27.09 INFO  ==> Welcome to the Bitnami redis container
redis 06:29:27.10 INFO  ==> Subscribe to project updates by watching https://github.com/bitnami/containers
redis 06:29:27.10 INFO  ==> Did you know there are enterprise versions of the Bitnami catalog? For enhanced secure software supply chain features, unlimited pulls from Docker, LTS support, or application customization, see Bitnami Premium or Tanzu Application Catalog. See https://www.arrow.com/globalecs/na/vendors/bitnami/ for more information.
redis 06:29:27.10 INFO  ==> 

Warning: Using a password with '-a' or '-u' option on the command line interface may not be safe.
192.168.6.201:6379> info
# Server
redis_version:7.4.2
redis_git_sha1:00000000
redis_git_dirty:1
......
......
......
```
