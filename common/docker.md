## Red hat系列启动docker

> 检测是否成功安装

```shell
sudo docker info
```

> 在RHEL 7中启动docker守护进程

```shell
sudo systemctl start docker
```

> 在RHEL 6中启动docker守护进程

```shell
sudo service docker start
```



## docker相关命令

| 运行docker镜像                         | docker run name                  |
| -------------------------------------- | -------------------------------- |
| 进入容器内交互运行                     | docker run -it name              |
| 运行并映射端口号                       | docker run -it -p 8080:8080 name |
| 直接进入容器（exit退出会导致容器停止） | docker attach 容器ID             |
| 在容器内打开新的终端进入容器           | docker exec 容器ID               |
| 在实体机对容器进行操作例子             | docker exec 容器ID ls -l /tmp    |
| 查看docker内进程                       | docker top                       |
| 查看当前docker进程的详情（容器ID等）   | docker ps                        |
| 停止运行容器                           | docker stop name                 |
| 从容器拷贝到实体机                     | docker cp 容器ID:路径 实体机路径 |
| 容器不停止退出                         | ctrl+p+q                         |
| 容器停止退出                           | exit                             |
| 从镜像库拉到docker服务器               | docker pull name                 |
| 重启运行的容器                         | docker restart name              |
| 移除一个或多个容器                     | docker rm                        |
| 移除镜像                               | docker -rmi name                 |
| 强制移除镜像                           | docker -rmi -f name              |
| 保存一个容器为一个tar包                | docker save                      |
| 在docker hub搜索镜像                   | docker search                    |
|                                        | docker start                     |
|                                        | docker tag                       |
|                                        | docker unpause                   |
|                                        | docker version                   |
|                                        | docker wait                      |



