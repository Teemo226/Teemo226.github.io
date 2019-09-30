---
layout: article
title: Ubuntu proxychains + shadowsocks 安装DropBox
tags: Ubuntu
mathjax: true
---

# Ubuntu proxychains + shadowsocks 安装 DropBox

---
## 下载 Dropbox 安装包
​	[Dropbox 下载](https://www.dropbox.com/install)，下载之后安装。

​	![](http://p0mrjv57m.bkt.clouddn.com/FmfVYDbDvg_7YNVbA4ZNOU6IJy0V.png)

## 使用代理安装 Dropbox
上面安装 DropBox 后，运行 dropbox，发现并不能使用(貌似软件还需要下载一些东西，不用代理不能下载成功)，所以需要继续下面的操作：

1. **proxychains安装**:    [proxychains项目地址](https://github.com/rofl0r/proxychains-ng)
```bash
$ git clone https://github.com/rofl0r/proxychains-ng.git
./configure --prefix=/usr --sysconfdir=/etc
$ make
$ sudo make install
$ sudo make install-config
```
2.**编辑proxychains配置**
```bash
$ sudo vim /etc/proxychains.conf
```
3.**将 socks4 127.0.0.1 9095 改为**
```bash
$ socks5 127.0.0.1 1080
```
4.**Dropbox**
```bash
$ proxychains4 dropbox start -i
```

待软件运行后，根据提示进行配置即可。



