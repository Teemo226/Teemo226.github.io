---
layout: article
title: Ubuntu 16.04 安装H3C iNode客户端
tags: Ubuntu
mathjax: true
show_title: true
show_edit_on_github: false
---

安装包：[百度云](https://pan.baidu.com/s/1miJSfcW) 密码：fs1g

1.检查本机是64位还是32位
```bash
$ dpkg --print-architecture
```
然后可以看到amd64，就说明当前系统是64位。
2.检查是否开启32位支持--输入：
```bash
$ dpkg --print-foreign-architectures
```
看到i386，就说明已开启32位支持，如果没有显示i386，则输入：
```bash
$ sudo dpkg --add-architecture i386
```
打开i386的支持，然后输入：
```bash
$ sudo apt-get update
```
进行更新，然后输入：
```bash
$ sudo apt-get dist-upgrade
```
对支持库进行更新
3.安装兼容包：
```bash
$ sudo apt-get install libncurses5:i386
$ sudo apt-get install libgtk2.0-0:i386
$ sudo apt-get install libpangoxft-1.0-0:i386
$ sudo apt-get install libpangox-1.0-0:i386
$ sudo apt-get install libxxf86vm1:i386
$ sudo apt-get install libsm6:i386
$ sudo apt-get install libjpeg62:i386
```
4.cd到iNode解压目录下，安装iNode：
```bash
$ sudo ./install
```
安装完成后，输入下面命令启动即可：
```bash
$ sudo ./iNodeClient.sh
```
