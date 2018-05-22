---
layout: post
title:  "wifi光猫配置教程"
date:   2018-05-22 14:06:05
categories: 配置
tags: 光猫 wifi pppoe
excerpt: wifi光猫配置教程。
---

* content
{:toc}


**只适用** 建平wifi光猫，目的是让光猫代替路由器进行拨号.

### 配置流程 ###
 1.连接光猫wifi或者插线，配置同网段ip后进入光猫管理地址：
	
	光猫管理地址：192.168.100.1
	光猫高级模式帐号
	用户名：telecomadmin
	密码：admintelecom
 
 2.点击`wan`标签，如果存在wan配置，则删除所有，然后新建一个wan口配置，参数如下：

	使能wan：勾选
	封装类型·pppoe
	wan类型：路由wan
	使能vlan：勾选
	vlanid：111
	优先级策略：从ip拷贝
	MRU：1492
	用户名：问大厅
	密码：123456
	绑定项：ssid1（这个选项是让wifi能访问外网），其他不要勾选
	ip地址获取方式：pppoe
	使能NAT：勾选
3.配置dhcp服务器，让猫能够有发放私网地址的能力：
	
	打开lan标签-DHCP服务配置
	配置如下图：
	
![](http://youyefu.oss-cn-beijing.aliyuncs.com/18-5-22/40697377.jpg)
	

4.上一步操作完，wifi应该就能上网了，下面接下来要配置光猫的lan口，让lan口拥有相应业务的能力：
	
	点击lan标签-lan口工作模式
	勾选lan1（请勿勾选lan2）
![](http://youyefu.oss-cn-beijing.aliyuncs.com/18-5-22/6677401.jpg)
5.至此，此光猫的wifi、lan1口已经具备上网能力，lan2具备点播能力

- ps1.现在的光猫是不能当作平时用的光猫来进行业务的，如果想让wifi光猫拥有和普通光猫一样的能力，可以按屁股后面的reset按钮重置光猫，如果还不能用，就检查下配置：wan口所有配置都删除，lan口工作模式对勾全取消即可
- ps2.如果后续用户想接路由，可以在lan1直插路由wan口，配置路由wan口为自动获取ip，，路由的dhcp服务避开192.168.100.x的网段即可。


  