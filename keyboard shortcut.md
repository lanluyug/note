## 一、navicat快捷键

1. 打开查询窗口

```
ctrl+q 
```

2.  注释

```
ctrl+/
```



3. 解除注释

```
ctrl +shift+/
```



4. 运行选中的SQL语句

```
ctrl+r 
```



5.  删除选中行内容

```
ctrl+l
```

6. 复制当前行内容并粘贴到下一行

```
 ctrl+d 
```

7. 关闭当前查询窗口

```
ctrl+w
```

----

## 二、IDEA快捷方式

> 打开所有父类的所有方法

```
Ctrl + o 
```

> 导入方法的包

```
Alt + enter
```

> 重新编译

```
Ctrl + F9 
```

> 上下移动当前行代码

```
Ctrl+Shift+上下键 
```

> 快速复制当前行代码

```
Ctrl + D 
```

> 快速删除当前行

```
Ctrl + Y 
```

> 快速添加javadoc

```
/** + enter 
```

-----

## DOCKER

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
|                                        |                                  |