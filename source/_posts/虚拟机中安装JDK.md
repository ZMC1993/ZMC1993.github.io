---
title: 虚拟机中安装JDK
date: 2019-03-07 20:36:59
tags:
---
* 一、原始jdk清理
1. 检查系统中版本：java -version
2. 检测jdk安装包：rpm -qa | grep java
3. 卸载openjdk：yum remove *openjdk*
4. 可再次使用2查看卸载情况

* 二、下载JDK并安装
1. 将下载好的tar.gz放置到一个目录
2. 使用cd命令跳到该目录
3. 创建安装目标文件夹：mkdir -p /usr/lib/jvm
4. 解压文件到该目录：tar -zxvf jdk-8u131-linux-x64.tar.gz -C /usr/lib/jvm

* 三、设置环境变量
1. 打开profile文件：vim /etc/profile
2. 在文件的最后添加：
export JAVA_HOME=/usr/lib/jvm/jdk1.8.0_131  
export JRE_HOME=${JAVA_HOME}/jre  
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib  
export  PATH=${JAVA_HOME}/bin:$PATH
3. 执行profile文件：source /etc/profile
4. 检查版本：java -version