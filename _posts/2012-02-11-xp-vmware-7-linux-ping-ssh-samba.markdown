---
layout: post
status: publish
published: true
title: XP系统Vmware 7安装Linux系统能ping通不能SSH连接的问题
author: 周亮
author_login: admin
author_email: zhlwish@gmail.com
author_url: http://www.zhlwish.com
excerpt: 一直用VMware Workstaion上安装Linux虚拟机进行开发的，安装软件等比Windows上方便很多，因为部署环境也是Linux，因此也避免了编码、换行符等平台兼容的问题，在Linux虚拟机中安装Samba解决文件系统共享的问题，一直都相安无事。最近为电脑重装了XP，安装好VMware Workstation 7后运行以前的ArchLinux的虚拟机，从发现samba连接不上了，可以在网络邻居的工作组中找到Linux虚拟机，但是共享无法连接，连登录的对话框都不显示。
wordpress_id: 949
wordpress_url: http://www.zhlwish.com/?p=949
date: '2012-02-11 20:28:42 +0800'
date_gmt: '2012-02-11 12:28:42 +0800'
categories:
- Linux技术
tags: []
comments:
- id: 984
  author: zhangbulun
  author_email: zhangbl@163.com
  author_url: ''
  date: '2012-07-12 11:30:32 +0800'
  date_gmt: '2012-07-12 03:30:32 +0800'
  content: 呵呵，山高人为峰
---
一直用VMware Workstaion上安装Linux虚拟机进行开发的，安装软件等比Windows上方便很多，因为部署环境也是Linux，因此也避免了编码、换行符等平台兼容的问题，在Linux虚拟机中安装Samba解决文件系统共享的问题，一直都相安无事。

最近为电脑重装了XP，安装好VMware Workstation 7后运行以前的ArchLinux的虚拟机，从发现samba连接不上了，可以在网络邻居的工作组中找到Linux虚拟机，但是共享无法连接，连登录的对话框都不显示。没办法，尝试安装vsftpd，用FTP来共享文件，结果FTP也无法连接，FTP显示已经建立连接，然后就没反应了。

后来发现ssh也无法连接，经检查，网络连接正常，也没有安装iptables防火墙，更没有Selinux。并且在同局域网内的其他电脑（Win 7系统）上可以访问samba和vsftpd以及ssh。

后来在终于在<a href="http://crazy123.blog.51cto.com/1029610/628287">http://crazy123.blog.51cto.com/1029610/628287</a>查到有人遇到同样的问题，解决方法为：

> 打开本机（winxp）的设备管理器中找到本机的网卡，打开其属性窗口，在高级标签中找到“offload checksum”将其值置为“Disable”，按确认后，重启电脑就可以通过SSH访问了。

但是，我是Realtek的网卡，高级标签中没有“offload checksum”，更新网卡驱动到最新版本也没有这个选项，经过查找资料，“offload checksum”就是“硬件校验和”，将这项设为“关闭”，重启XP，问题解决了。好像只有Nvidia的网卡才有“offload checksum”这一项，Realtek网卡如下图所示：

<a href="https://www.flickr.com/photos/zhlwish/14023130947/" title="Flickr 上 zhlwish 的 win-realtek"><img src="https://farm6.staticflickr.com/5531/14023130947_575fca1745_o.png" width="404" height="423" alt="win-realtek"></a>