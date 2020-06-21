---
layout:     post
title:      信息收集-dmitry
subtitle:   dmitry
date:       2020-05-08
author:     TL
header-img: img/home-bg-o.jpeg
catalog: true
tags:
    - kali
---

## **信息收集**-dmitry 

### 一、前言

渗透测试中第二个阶段——信息收集，在这个阶段我们需要尽可能多的收集目标的信息，例如：域名的信息，DNS，IP，使用的技术和配置，文件，联系方式等等。

方式可以分为两种：主动和被动。

主动的信息收集方式：通过直接访问、扫描网站，这种将流量流经网站的行为。被动的信息收集方式：利用第三方的服务对目标进行访问了解，比例：Google搜索，Whois，host查询。

几种常见的DNS记录类型：

 ![img](file:///C:/Users/19713/AppData/Local/Temp/msohtmlclip1/01/clip_image002.jpg)

### 二、什么是dmitry？

Dmitry--多功能信息收集工具,是一个由C语言编写的UNIX/(GNU)Linux命令行工具，它可用于收集主机相关信息，比如子域名、Email地址、系统运行时间信息。

### 三、具体可以做什么？

- 根据IP（或域名）来查询目标主机的Whois信息
- 在Netcraft.com的网站上挖掘主机信息
- 查找目标域中用的子域
- 查找目标域的电子邮件地址
- 探测目标主机上打开的端口、被屏蔽的端口和关闭的端口

·    通过-O参数将收集到的信息保存在一个文件中

### 四、支持的参数

 ![img](file:///C:/Users/19713/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

-o:将输出保存到％host.txt或由-o文件指定的文件

-i:对主机的IP地址执行whois查找

-w:对主机的域名执行whois查找

-n:在主机上检索Netcraft.com信息

-s:执行搜索可能的子域

-e:执行搜索可能的电子邮件地址

-p:在主机上执行TCP端口扫描

-f:在显示输出报告过滤端口的主机上执行TCP端口扫描

-b:读取从扫描端口接收的banner

-t :0-9扫描TCP端口时设置TTL（默认为2）

### 五、实例

> dmity -iwnse baidu.com

搜索baidu的IP、主机域名、子域和尽可能搜到的电子邮件

 ![img](file:///C:/Users/19713/AppData/Local/Temp/msohtmlclip1/01/clip_image006.png)

IP：39:156:69:79

以及聚合了该IP的Inet-whois信息

dmitry扫描端口哪些是开启的

> dmitry -p baidu,com -f -b

 ![img](file:///C:/Users/19713/AppData/Local/Temp/msohtmlclip1/01/clip_image010.png)

dmitry创建名为test.out的报告，并进行参数指定的动作扫描

> dmitry -iwns -o test.out taobao.com