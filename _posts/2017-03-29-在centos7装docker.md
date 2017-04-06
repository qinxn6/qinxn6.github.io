---
title: 在centos7装docker
tags: dockers
categories: 工具
---
http://blog.csdn.net/u012486840/article/details/53261564
按照步骤开始在vmware的centos7上安装docker。
没有设置代理，直接yum update 等待更新（期间会有yes或者n的选项）
su后用yum -y install docker,等待一会儿
安装成功
![](https://qinxn6.github.io/image/7.png)
启动后台服务
[root@centos7 ~]# service docker start
下载官方的 CentOS 镜像到本地
[root@localhost ~]# docker pull centos
确认 CentOS 镜像已经被获取
[root@localhost ~]# docker images centos
http://www.linuxprobe.com/install-use-docker-in-centos7.html