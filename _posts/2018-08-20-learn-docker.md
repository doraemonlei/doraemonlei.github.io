---
layout: post
title: "学习：Docker学习总结"
subtitle: " \"Hello World, Hello Work\""
date: 2018-08-20 09:52:40
author: "doraemonlei"
#header-img: "img/post-bg-2015.jpg"
#cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
categories: test
tags: 工作 Docker 服务器 
---

> “Yeah It's on. ”

# 0 资料
## Docker官方英文资源
- [Docker 官网](http://www.docker.com/)
- [Github Docker 源码](https://github.com/docker/docker)
- [Docker 菜鸟教程](http://www.runoob.com/docker/docker-tutorial.html)
- [Docker 中文社区](http://www.docker.org.cn/)
- [Docker windows入门](https://docs.docker.com/windows/)
- [Docker Linux 入门](https://docs.docker.com/linux/)
- [Docker mac 入门](https://docs.docker.com/mac/)
- [Docker 用户指引](https://docs.docker.com/engine/userguide/)
- [Docker 官方博客](http://blog.docker.com/)
- [Docker Hub](https://hub.docker.com/)
- [Docker 开源](https://www.docker.com/open-source)

## Docker中文资源
- [Docker中文网站](https://www.docker-cn.com/)
- [Docker安装手册](https://docs.docker-cn.com/engine/installation/)

## Docker 国内镜像

```shell
网易加速器：http://hub-mirror.c.163.com
官方中国加速器：https://registry.docker-cn.com
ustc的镜像：https://docker.mirrors.ustc.edu.cn
daocloud：https://www.daocloud.io/mirror#accelerator-doc（注册后使用）
```

## Docker 命令大全
[查看](http://www.runoob.com/docker/docker-command-manual.html)

# 1 Docker基本概念和框架
## 1.1 Docker简介
### 容器：
1. 一种虚拟化方案
2. 操作系统级别的虚拟化
3. 只能运行相同或相似内核的操作系统
4. 依赖于Linux内核特性（Namespace和Cgroups）

优点：
1. 资源占用少
2. 更多的服务能力

### Docker
1. 将应用程序自动部署到容器
2. Go语言
3. 2013年出
4. 基于Apache 2.0开源授权协议发行

### Docker目标
1. 提供简单轻量的建模方式
2. 职责的逻辑分明
3. 快速高效的开发生命周期
4. 鼓励使用面向服务的架构

### Docker的使用场景
1. 使用Docker容器开发、测试、部署服务
2. 创建隔离的运行环境
3. 搭建测试环境
4. 构建多用户的平台即服务（PasS）基础设施
5. 提供软件即服务（SasS）应用程序
6. 高性能、超大规模的宿主机部署

## 1.2 Docker基本组成
- Client客户端
- Daemon守护进程
- Image镜像
- Container容器
- Registry仓库

### 客户端/守护进程
- C/S架构 
- 本地/远程

### 镜像
- 容器的基石
- 层叠的只读文件系统
- 联合加载

### 容器
- 通过镜像启动
- 启动和执行阶段
- 写时复制

### 仓库
- 公有
- 私有
- Docker Hub

### 基本组成
![image](https://note.youdao.com/yws/api/personal/file/8DBB677C4F25406F89B9E3371BA5D49F?method=download&shareKey=b6a3279447a7c1da78894de24ae2ddda)

### 示例
```shell
docker version 查看版本
docker search tutorial
docker pull learn/tutorial
docker run learn/toturial echo 'hello world'
docker run learn/toturial apt-get install -y ping
docker ps -l
docker commit id learn/ping 提交容器
docker run learn.ping www.google.com
docker inspect id
docker images
docker push learn/ping
```

## 1.3 docker容器相关技术
- Namespace 命名空间
- Control groups（cgroups）控制组

### Namespace 命名空间
- 编程语言 
    - 封装->代码隔离
- 操作系统
    - 系统资源的隔离
    - 进程、网络、文件系统
- PID 进程隔离
- NET 管理网络接口
- IPC 管理跨进程通信的访问
- MNT 管理挂载点
- UTS 隔离内核和版本标识

### Control groups（cgroups）控制组
- 资源限制
- 优先级设定
- 资源计量
- 资源控制

### Docker能力
![image](https://note.youdao.com/yws/api/personal/file/4A76E92B2E3946C8B402A67D2371D711?method=download&shareKey=65fcf05d1c9a0561b2b281c565545133)

# 2 Docker的安装和部署
## 2.1 Ubuntu Docker 安装
- Docker 要求 Ubuntu 系统的内核版本高于 3.10

```shell
ubuntu14.04

1 查看当前的内核版本
uname -r
查看Device Mapper
ls -l /sys/class/misc/device-mapper

2 使用脚本安装 Docker
wget -qO- https://get.docker.com/ | sh
或者
sudo apt-get install -y curl
curl -sSL https://get.docker.com/ubuntu/ | sudo sh

3 启动docker 后台服务
sudo service docker start

4 测试运行hello world
docker run ubuntu echo 'hello-world'

5 使用非root用户
sudo groupadd docker
sudo gpasswd -a 用户名 docker
sudo service docker restart

注销后重新登录即可

6 镜像加速
鉴于国内网络问题，后续拉取 Docker 镜像十分缓慢，我们可以需要配置加速器来解决，我使用的是网易的镜像地址：http://hub-mirror.c.163.com。

新版的 Docker 使用 /etc/docker/daemon.json（Linux） 或者 %programdata%\docker\config\daemon.json（Windows） 来配置 Daemon。

请在该配置文件中加入（没有该文件的话，请先建一个）：

{
  "registry-mirrors": ["http://hub-mirror.c.163.com"]
}

```

```shell
Ubuntu 16.04 

1.选择国内的云服务商，这里选择阿里云为例
curl -sSL http://acs-public-mirror.oss-cn-hangzhou.aliyuncs.com/docker-engine/internet | sh -

2.安装所需要的包
sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual

3.添加使用 HTTPS 传输的软件包以及 CA 证书
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates

4.添加GPG密钥
sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D

5.添加软件源
echo "deb https://apt.dockerproject.org/repo ubuntu-xenial main" | sudo tee /etc/apt/sources.list.d/docker.list

6.添加成功后更新软件包缓存
sudo apt-get update

7.安装docker
sudo apt-get install docker-engine

8.启动 docker
sudo systemctl enable docker
sudo systemctl start docker

```

```shell
Ubuntu 18.04

1.更换国内软件源，推荐中国科技大学的源，稳定速度快（可选）
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
sudo sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn' /etc/apt/sources.list
sudo apt update

2.安装需要的包
sudo apt install apt-transport-https ca-certificates software-properties-common curl

3.添加 GPG 密钥，并添加 Docker-ce 软件源，这里还是以中国科技大学的 Docker-ce 源为例
curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu \
$(lsb_release -cs) stable"

4.添加成功后更新软件包缓存
sudo apt update

5.安装 Docker-ce
sudo apt install docker-ce

6.设置开机自启动并启动 Docker-ce（安装成功后默认已设置并启动，可忽略）
sudo systemctl enable docker
sudo systemctl start docker

7.测试运行
sudo docker run hello-world

8.添加当前用户到 docker 用户组，可以不用 sudo 运行 docker（可选）
sudo groupadd docker
sudo usermod -aG docker $USER

9.测试添加用户组（可选）
docker run hello-world

```
## 2.2 CentOS Docker 安装
- 目前，CentOS 仅发行版本中的内核支持 Docker。
- CentOS 7，要求系统为64位、系统内核版本为 3.10 以上。
- CentOS 6.5 或更高的版本的 CentOS 上，要求系统为64位、系统内核版本为 2.6.32-431 或者更高版本。


```shell
1 查看当前的内核版本
uname -r 3.10.0-327.el7.x86_64

从 2017 年 3 月开始 docker 在原来的基础上分为两个分支版本: Docker CE 和 Docker EE。Docker CE 即社区免费版，Docker EE 即企业版，强调安全，但需付费使用。

2 移除旧的版本
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-selinux \
                  docker-engine-selinux \
                  docker-engine
                  
3 安装一些必要的系统工具：
sudo yum install -y yum-utils device-mapper-persistent-data lvm2

4 添加软件源信息：
sudo yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

5 更新 yum 缓存：
sudo yum makecache fast

6 安装 Docker-ce：
sudo yum -y install docker-ce

7 启动 Docker 后台服务
sudo systemctl start docker

8 测试运行 hello-world
docker run hello-world

使用脚本安装 Docker
1 使用 sudo 或 root 权限登录 Centos。
 
2 确保 yum 包更新到最新。
sudo yum update

3 执行 Docker 安装脚本。
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
执行这个脚本会添加 docker.repo 源并安装 Docker。

4 启动 Docker 进程。
sudo systemctl start docker

5 验证 docker 是否安装成功并在容器中执行一个测试的镜像。
sudo docker run hello-world
docker ps
到此，Docker 在 CentOS 系统的安装完成。

6 删除 Docker CE
sudo yum remove docker-ce
sudo rm -rf /var/lib/docker
```

## 2.3 Windows Docker 安装
略

## 2.4 MacOS Docker 安装
略

# 3 Docker容器
## 3.1 容器的基本操作

```shell
1 启动交互式容器
docker run -i -t IMAGE /bin/bash

2 查看容器
docker ps 所有正在运行的容器
    -a 所有容器
    -l 最新创建的容器

3 查看容器详细信息
docker inspect IMAGE[CONTAINER ID][NAMES]

4 自定义容器名
docker run --name=自定义名 -i -t IMAGE /bin/bash

5 重新启动停止的容器(交互方式)
docker start [-i] IMAGE 

exit 退出

6 删除停止的容器
docker rm 容器名
```

## 3.2 守护式容器（长期运行的容器）

```shell
1 守护形式运行容器
docker run -i -t IMAGE /bin/bash
CTRL+P CTRL+Q

或者
docker run -d IMAGE
例：
docker run --name dc1 -d ubuntu /bin/sh -c "while true; do echo hello world; sleep 1; done" 

2 返回运行中的容器
docker attach IMAGE

3 查看容器日志
docker logs -ft --tail 0 IMAGE

4 查看容器内进程
docker top IMAGE

5 在运行的容器中启动新的进程
docker exec -d -i -t 容器名[COMMAND][ARG]

6 停止守护式容器
docker stop
docker kill

7帮助文件
man docker-run
······
```

## 3.3 部署静态网站

设置容器的端口映射
```shell
对容器暴漏的所有端口进行映射
docker run -P -i -t ubuntu /bin/bash

指定映射容器的哪些端口
docker run -p 80 -i -t ubuntu /bin/bash
docker run -p 8080:80 -i -t ubuntu /bin/bash
docker run -p 0.0.0.0:80 -i -t ubuntu /bin/bash
docker run -p 0.0.0.0:8080:80 -i -t ubuntu /bin/bash
```
例：部署静态网站
- 创建映射80端口的交互式容器
- 安装Nginx
- 安装文本编辑器vim
- 创建静态页面
- 修改Nginx配置文件
- 运行Nginx
- 验证网站访问

```shell
docker run -p 80 --name web -i -t ubuntu /bin/bash
apt-get install -y nginx
apt-get install -y vim
mkdir -p /var/www/html
vim index.html
whereis nginx
ls /etc/nginx/sites-enabled
vim /etc/nginx/sites-enabled
nginx
ps -ef
CTRL+P CTRL+Q
docker ps
docker port web
docker top web
curl http://127.0.0.1:49167

docker stop web
docker start -i web
docker exec web nginx
docker top web
```

# 4 Docker镜像与仓库
## 4.1 查看和删除镜像
```shell
镜像存储地址
/var/lib/docker

列出镜像
docker images IMAGE
-a 所有镜像
-f 过滤条件
--no-trunc 完整ID
-q 只显示ID

查看镜像
docker inspect -f 容器|镜像名:TAG|IMAGE ID

删除镜像
docker rmi IMAGE
-f 强制
--no-prune
docker rmi $(docker images -q ubuntu)
```

## 4.2 获取和推送镜像
```shell
1 查找镜像
Docker Hub
https://hub.docker.com/

docker search

2 拉取镜像
docker pull name：tag

加速
使用--registry-mirror选项
修改:/etc/default/docker
添加:DOCKER_OPTS="--registry-mirror="

curl -sSL https://get.daocloud.io/daotools/set_mirror.sh | sh -s http://e5afd4f9.m.daocloud.io

service docker restart
ps -ef | grep docker

3 推送镜像
docker push xx/xx
```

## 4.3 构建镜像
```shell
通过容器构建
docker commit 容器 
-a 指定镜像作者
-m 记录镜像构建的信息
-p 不暂停正在执行的容器

例：
docker run -it -p 80 --name commit_test ubuntu /bin/bash
apt-get update
apt-get install -y nginx
dacker commit -a 'Doraemonlei' -m 'nginx' commit_test doraeminlei/commit_test1

docker run -d --name nginx_web2 -p 80 doraeminlei/commit_test1 nginx -g "daemon off;"


通过Dockerfile构建镜像
docker build 

例：
FROM    centos:6.7
MAINTAINER      Fisher "fisher@sudops.com"

RUN     /bin/echo 'root:123456' |chpasswd
RUN     useradd runoob
RUN     /bin/echo 'runoob:123456' |chpasswd
RUN     /bin/echo -e "LANG=\"en_US.UTF-8\"" >/etc/default/local
EXPOSE  22
EXPOSE  80
CMD     /usr/sbin/sshd -D

docker build -t runoob/centos:6.7 .

```
## 4.4Dockerfile指令
```shell
注释
# xxx

FROM 镜像：标签
MAINTAINEAR 作者信息 doraemonlei "email"
RUN 执行指令
EXPOSE 指定端口
CMD 执行命令（容器运行的默认行为，覆盖run命令的指令）
ENTERYPOINT （容器运行的默认行为，不覆盖run命令的指令）
ADD 
COPY
VOLUME
WORKDIR 工作路径，绝对路径
ENV 环境变量
USER
ONBUILD
```

# 5 Docker客户端和守护进程
## 5.1 Docker的C/S模式


# 6 Docker容器的网络连接
## 容器的网络基础
```shell
ifconfig

docker0 
- linux的虚拟网桥->数据链接层
- 可以设置ip地址
- 相当于一个隐藏的虚拟网卡

网桥管理工具
apt-get install bridge-utils
brctl show
```
![7层](https://note.youdao.com/yws/api/personal/file/07A4AA56AF5941C1A962D3EDA7F1BCCF?method=download&shareKey=71cbe034cae2b331db0dc9f7e7cc1eb5)

![自定义虚拟网桥](https://note.youdao.com/yws/api/personal/file/0F4EC8205CAE46D294622B01389348EF?method=download&shareKey=71cbe034cae2b331db0dc9f7e7cc1eb5)

## 容器的互联
```shell
允许所有容器间互联

vim /etc/default/docker
--icc=trur

--link
docker run --link=容器名：别名 IMAGE COMMAND

拒绝所有容器间互联
--icc-false

允许特定容器间的连接
--icc=false --iptables=true
--link

iptables -L -n
iptables -F
```
## 容器与外部网络的连接
```shell
ip_forward
iptables
允许端口映射访问
限制IP访问容器

--ip-forward=true
sysctl net.ipv4.conf.all.forwarding

iptables
是与Linux内核集成的包过滤防火墙系统，几乎所有的linux发行版都会包含iptables的功能。

表
链
规则

iptables -t filter -L -n

阻止特定ip访问特定容器
iptables -I DOCKER -s 10.211.55.3 -d 172.17.0.7 -p TCP --dport 80 -j DROP
```

# 7 Docker容器的数据管理
## 容器的数据卷
```shell
什么是数据卷？
经过特殊设计的目录，可以绕过联合文件系统（UFS），为一个或多个容器提供访问

-数据的永久化

-在容器启动时初始化
-容器之间共享和重用
-可以对数据卷里的内容直接进行修改
-数据卷的变化不会影响镜像的更新
-卷会一直存在，即使挂载数据卷的容器已经被删除

docker run -it -v ~/datavolume:/data ubuntu /bin/bash

为数据卷添加权限
docker run -it -v ~/datavolume:/data:ro --name dvt1 ubuntu /bin/bash

使用Dockerfile构建包含数据卷的镜像
VOLUME["/data1","/data2"]
```

## 数据卷容器
```shell
数据卷容器?
命名的容器挂载数据卷，其他容器通过挂载这个容器实现数据共享，挂载数据卷的容器，就叫做数据卷容器

挂载数据卷容器的方法
docker run --volumes-from 容器名

例
docker run -it --name dvt4 doraemonlei/dvt
touch datavolume1.dvt4_1
ls datavolume1

docker run -it --name dvt5 --volumes-from dvt4 ubuntu /bin/bash

docker inspect --format="{{.volumes}}" dvt5
docker rm -v dvt8 同时删除数据卷
```

## 数据卷的备份和还原
```shell
备份
docker run --volumes-from 需要备份的容器名 -v$(pwd):/backup ubuntu tar cvf /backup/backup.tar 容器数据卷

还原
docker run --volumes-from 需要备份的容器名 -v$(pwd):/backup ubuntu tar xvf /backup/backup.tar 容器数据卷

例
docker restart dvt5
docker attach dvt5
ls datavolume1
exit
docker run --volumes-from fvt5 -v ~/backup:/backup --name dvt10 ubuntu tar cvf /backup/dvt5.tar /datavolume1

```

# 8 Docker容器的跨主机访问
## 使用网桥实现跨主机容器连接
```shell

```

## 使用open vswitch实现跨主机容器连接
```shell

```

## 使用weave实现跨主机容器连接
```shell

```

# 9 本地常用命令和Dockerfile
```shell
容器生命周期管理
run
start/stop/restart
kill
rm
pause/unpause
create
exec

容器操作
ps
inspect
top
attach
events
logs
wait
export
port

容器rootfs命令
commit
cp
diff

镜像仓库
login
pull
push
search

本地镜像管理
images
rmi
tag
build
history
save
import

info|version
info
version

```
[-----------命令查看-----------](http://www.runoob.com/docker/docker-command-manual.html)

```shell
新建容器
docker run -it -p 80 -p 443 -p 3306 -p 8080 -p 22 --name face stubuntu:latest /bin/bash

docker run -it -p 80 -p 443 -p 3306 -p 8080 -p 22 --name face stubuntu:latest /usr/sbin/sshd -D

更新
apt-get update
apt-get upgrade

安装ifconfig和ping
apt install net-tools 
apt install iputils-ping     

设置root密码passwd
passw0rd

查看版本
cat /etc/issue
查看内核
uname -a

退出
ctrl+P-Q

操作
docker stop face
docker start -i face
docker exec -it face /bin/bash
docker exec face nginx
docker top face

查看容器ip
docker inspect test |grep IPAddress

其他
service ssh start
```

Dockerfile

```shell
mkdir ssh_Dockerfile && cd ssh_Dockerfile

# ehealth

FROM stubuntu:latest
MAINTAINER doraeminlei leiyi9345@163.com
RUN apt-get update
RUN apt-get upgrade



```

# 10 实例
### Docker 给运行中的容器设置端口映射方法
方法1  
1、获得容器IP
将container_name 换成实际环境中的容器名
```shell
docker inspect `container_name` | grep IPAddress
```
2、 iptable转发端口
将容器的8000端口映射到docker主机的8001端口
```shell
iptables -t nat -A  DOCKER -p tcp --dport 8001 -j DNAT --to-destination 172.17.0.19:8000
```

方法2  
1.提交一个运行中的容器为镜像
```shell
docker commit containerid foo/live
```
2.运行镜像并添加端口
```shell
docker run -d -p 8000:80 foo/live /bin/bash
```

### 关于attach命令卡住问题
```shell
第一种 attach回车
docker attach face

第二种
docker exec -it face /bin/bash
```

### Docker的ubuntu镜像安装的容器无ifconfig和ping命令的解决

```shell
apt-get update
apt install net-tools       # ifconfig 
apt install iputils-ping     # ping
```