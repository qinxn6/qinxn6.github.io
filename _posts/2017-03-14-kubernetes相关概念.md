---
title: 相关概念Kubernetes
tags: K8S
categories: 技术
---
1.背景：云计算平台
     Iaas
	 Paas
	 Saas
	 那么兴起的docker服务可用于Iaas/Paas层。
	 docker技术优势：
	 -一次构建，到处运行
	 -容器的快速轻量
	 -完整的生态环境

2.kubernetes
  Kubernetes(k8s)是Google开源的容器集群管理系统（谷歌内部:Borg）。在Docker技术的基础上，为容器化的应用提供部署运行、资源调度、服务发现和动态伸缩等一系列完整功能，提高了大规模容器集群管理的便捷性。
  Kubernetes优势:
　　　　- 容器编排
　　　　- 轻量级
　　　　- 开源
　　　　- 弹性伸缩
　　　　- 负载均衡
3.Kubernetes的核心概念
①.Pod
　　运行于Node节点上，若干相关容器的组合。Pod内包含的容器运行在同一宿主机上，使用相同的网络命名空间、IP地址和端口，能够通过localhost进行通。Pod是Kurbernetes进行创建、调度和管理的最小单位，它提供了比容器更高层次的抽象，使得部署和管理更加灵活。一个Pod可以包含一个容器或者多个相关容器。
②.Replication Controller
　　Replication Controller用来管理Pod的副本，保证集群中存在指定数量的Pod副本。集群中副本的数量大于指定数量，则会停止指定数量之外的多余容器数量，反之，则会启动少于指定数量个数的容器，保证数量不变。Replication Controller是实现弹性伸缩、动态扩容和滚动升级的核心。
③.Service
　　Service定义了Pod的逻辑集合和访问该集合的策略，是真实服务的抽象。Service提供了一个统一的服务访问入口以及服务代理和发现机制，用户不需要了解后台Pod是如何运行。
④.Label
　　Kubernetes中的任意API对象都是通过Label进行标识，Label的实质是一系列的K/V键值对。Label是Replication Controller和Service运行的基础，二者通过Label来进行关联Node上运行的Pod。
⑤.Node
　　Node是Kubernetes集群架构中运行Pod的服务节点（亦叫agent或minion）。Node是Kubernetes集群操作的单元，用来承载被分配Pod的运行，是Pod运行的宿主机。