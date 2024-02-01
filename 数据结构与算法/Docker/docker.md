# 介绍
### 简介
docker是一个容器引擎
解决项目开发过程中的开发,测试等不同环境的问题,一次开发,到处运行.
### 优势
可移植性
可伸缩性
隔离性 ^[docker容器提供隔离的运行环境]
### 组成
客户端
docker主机(service)
注册中心->仓库^[用来存储镜像]
镜像
容器
docker安装软件 1.下载相应镜像2.容器安装
一个镜像可以安装多个容器,只需要容器名称和端口号不同即可
镜像相当于类,容器是镜像的实例对象
# 使用
## 安装与卸载
参考官方文档
[https://docs.docker.com/engine/install/centos/](https://docs.docker.com/engine/install/centos/)
### 卸载:

yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
### 安装
#### 安装依赖
sudo yum install -y yum-utils
#### 安装docker的下载源
yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
#通过阿里源进行设置docker的下载源
 yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
#### 安装docker    
 yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
## 服务
查看运行状态: systemctl status docker
启动docker服务: systemctl start docker
关闭docker服务: systectl stop docker
重启docker服务: systemctl restart docker

## docker镜像
1. 搜索镜像 docker search 镜像关键字
2. 拉取镜像 docker pull 镜像名称^[根据 搜索镜像 中找出来的镜像的名称]
3. 查看本地镜像 docker images
4. 删除镜像 docker rmi 镜像名称
5. 帮助文档 docker images  --help ,docker --help
## docker容器
1. 查询容器 docker ps\ docker ps -a
2. **创建容器**,通过镜像来进行创建 docker run 
类型参数选项：
-d,--detach								# 以后台的模式执行命令
-t, --tty								# 分配一个虚拟终端，通常和-i参数一起使用
-i,--interactive						# 把交互界面一直保留，通常和-t参数一起使用
docker run -it 镜像名称/id 交互型
docker run -d 镜像名称/id 守护型,后台运行
docker run -d --name 为镜像生成的容器起名 -p 6379:6379 镜像名称/镜像id
## 容器服务
docker stop 容器名称/容器id											# 关闭容器
docker start  容器名称/容器id											# 启动容器
docker restart 容器名称/容器id										# 重启容器
## 删除容器
docker rm 容器名称/容器id
docker rm -f 容器名称/容器id   --> 删除正在运行的容器
## 进入容器
docker exec
示例1：docker exec -it redis01 /bin/bash					 	  # 进入到容器中同时打开一个shell窗口
## 其他命令
docker logs -f 容器名称/容器的id						# 查询容器内进程日志，-f参数表示实时监控日志信息
docker inspect 容器名称/容器的id						# 查看容器的详情信息
docker cp 											 # 完成容器和宿主机之间的文件copy
## 备份与迁移
将docker容器保存为一个镜像
		docker commit 容器名称.容器id 镜像名称(起名)
将镜像保存为tar文件
		docker save -o 镜像tar文件名 镜像名称,镜像id
将tar文件恢复为一个镜像
		docker load -i tar文件名称
## 数据卷操作
1. 查看数据卷 docker volume ls
2. 创建数据卷 docker volume create 数据卷名称
3. 查询数据卷详情 docker volume inspect 数据卷名称
4. 删除数据卷 docker volume rm 数据卷名称
5. 删除未使用的数据卷 docker volume prune
## 数据卷挂载
格式: -v 数据卷名称:容器目录
docker run -d --name 容器别名 -p 外端口:内端口 -v 数据卷名称:容器目录  容器名称/容器id
## 目录挂载
格式: -v 宿主机目录:容器目录
示例：docker run -d --name redis03(容器别名) -p 6381:6379 -v (宿主机目录:容器目录)/redis-data:/data redis:7.0.10(容器名称,容器id)


_默认创建的数据卷目录都在 /var/lib/docker/volumes_


docker run -d -p 81:81 \
 --name nginx-spzx \
 -v nginx_html:/user/share/nginx/html \
 -v nginx_conf:/etc/nginx/ \
  -v nginx_logs:/var/log/nginx nginx