## 前提准备

1. 关闭宿主机swap分区，参考教程: [优化Centos关闭SELinux/Swap及资源限制调整](https://liboshuai.icu/pages/d040eabd/#%E5%85%B3%E9%97%AD-Swap-%E5%88%86%E5%8C%BA)
2. 调整宿主机虚拟内存最大映射数，参考教程：[优化Centos关闭SELinux/Swap及资源限制调整](https://liboshuai.icu/pages/d040eabd/#%E8%B0%83%E6%95%B4-vm-max-map-count%EF%BC%88%E8%99%9A%E6%8B%9F%E5%86%85%E5%AD%98%E6%9C%80%E5%A4%A7%E6%98%A0%E5%B0%84%E6%95%B0%EF%BC%89)
3. 修改`.env`文件中的`HOST_IP`值为宿主机实际IP。

## 启动服务

```shell
docker-compose up -d
```

## 添加 BE 节点 及设置 root 密码

> 容器启动后，需要进行以下操作才能真正使服务正常运行。

```shell
docker-compose exec fe bash

# 容器内部操作
mysql -h ${宿主机IP} -P 9030 -uroot
SET PASSWORD FOR 'root' = PASSWORD('YOUR_PASSWORD');
ALTER SYSTEM ADD BACKEND "${宿主机IP}:9050";
SHOW PROC '/backends';
```

## 验证服务

浏览器打开`http://${宿主机IP}:8030`，输入`root`和`YOUR_PASSWORD`，即可进入 Doris FE 管理页面。