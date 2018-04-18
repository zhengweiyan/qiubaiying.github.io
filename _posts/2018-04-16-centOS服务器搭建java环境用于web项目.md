---
layout:     post                    # 使用的布局（不需要改）
title:      centOS服务器搭建java环境用于web项目               # 标题
subtitle:   test #副标题
date:       2018-04-16              # 时间
author:     zwy                      # 作者
header-img: /img/home-bg-4.jpg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - 后端
---

- 安装JDK
- JDK 是开发Java程序必须安装的软件，我们查看一下 `yum` 源里面的 JDK：

```shell
yum list java*
```

- 选择适合本机的JDK，并安装

```shell
yum install java-1.7.0-openjdk* -y
```

- 安装完成后，查看是否安装成功：

```shell
java -version
```

- 安装Tomcat
- Tomcat 是一个应用服务器，是开发和调试 jsp 程序的首选，可以利用它来响应 HTML 页面的访问请求。


- 进入本地文件夹

```shell
cd /usr/local
```

- 到官网找到 Tomcat 的下载链接，并下载到服务器中, 这里提供了一个快速下载 Tomcat 的地址：

```shell
wget https://mc.qcloudimg.com/static/archive/fa66329388f85c08e8d6c12ceb8b2ca3/apache-tomcat-7.0.77.tar.gz
```

- 解压这个文件夹：

```shell
tar -zxf apache-tomcat-7.0.77.tar.gz
```

- 重命名这个文件夹

```shell
mv apache-tomcat-7.0.77 /usr/local/tomcat7
```

- 进入 bin 文件夹

```shell
cd /usr/local/tomcat7/bin
```

- 给这个文件夹下的所有 shell 脚本授予权限：

```shell
chmod 777 *.sh
```

- 开启tomcat服务：

```shell
./startup.sh
```

- 安装MySQL


- 使用 `yum` 安装 MySQL：

```shell
yum install -y mysql-server mysql mysql-devel
```

- 安装完成后，启动 MySQL 服务：

```shell
service mysqld restart
```

- 设置密码

```shell
/usr/bin/mysqladmin -u root password '你的密码'
```

- 访问tomcat
- 此时，访问 [http://你的主机:8080]() 可访问到刚才启动的 Tomcat 的内置示例页面
