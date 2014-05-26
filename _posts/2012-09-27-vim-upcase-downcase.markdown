---
layout: post
status: publish
published: true
title: VIM字符大小写转换
author: 周亮
author_login: admin
author_email: zhlwish@gmail.com
author_url: http://www.zhlwish.com
excerpt: |+
  VIM提供了字符大小写转换的快捷键，在coding的时候会感觉很贴心，当然，前提是记住他们。

wordpress_id: 1139
wordpress_url: http://www.zhlwish.com/?p=1139
date: '2012-09-27 11:57:59 +0800'
date_gmt: '2012-09-27 03:57:59 +0800'
categories:
- Linux
tags:
- vim
comments:
- id: 1006
  author: gxc
  author_email: hustgxc@gmail.com
  author_url: ''
  date: '2012-09-27 11:56:55 +0800'
  date_gmt: '2012-09-27 03:56:55 +0800'
  content: 2.1和2.2好像反了
- id: 1007
  author: ThankCreate
  author_email: thankcreate@gmail.com
  author_url: http://www.thankcreate.com
  date: '2012-09-27 12:33:34 +0800'
  date_gmt: '2012-09-27 04:33:34 +0800'
  content: 楼上SX
- id: 1008
  author: 点团队周亮
  author_email: zhlwish@gmail.com
  author_url: http://weibo.com/zhlwish
  date: '2012-09-27 12:49:50 +0800'
  date_gmt: '2012-09-27 04:49:50 +0800'
  content: 果然，赞！
- id: 1009
  author: 点团队周亮
  author_email: zhlwish@gmail.com
  author_url: http://weibo.com/zhlwish
  date: '2012-09-27 12:49:58 +0800'
  date_gmt: '2012-09-27 04:49:58 +0800'
  content: SX是什么意思？
- id: 1011
  author: ThankCreate
  author_email: thankcreate@gmail.com
  author_url: http://www.thankcreate.com
  date: '2012-09-29 09:49:43 +0800'
  date_gmt: '2012-09-29 01:49:43 +0800'
  content: 就是S13，本来是说gxc的，现在你把他的楼占了，哈哈~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
- id: 1012
  author: ThankCreate
  author_email: thankcreate@gmail.com
  author_url: http://www.thankcreate.com
  date: '2012-09-29 09:55:04 +0800'
  date_gmt: '2012-09-29 01:55:04 +0800'
  content: 补充一小点,guw只能在当前光标在单词头才能将整个单词转化，如果不在单词头，可以先b一下.不过，从语义上来说，用gue应该更合适一点，虽然效果是一样的
- id: 1013
  author: 点团队周亮
  author_email: zhlwish@gmail.com
  author_url: http://weibo.com/zhlwish
  date: '2012-10-06 21:03:32 +0800'
  date_gmt: '2012-10-06 13:03:32 +0800'
  content: 赞
---
VIM提供了字符大小写转换的快捷键，在coding的时候会感觉很贴心，当然，前提是记住他们。

## 转换一个字符

大小写转换(大写转换成小写，小写转换成大写)快捷键`~`。

* 转换1个字符，光标移动到要转换的字符上，按`~`
* 转换多个字符，将光标移动到想要大小写转换的地方然后键入: 个数 + '~'。如:转换(大写转小写，小写转大写)10个字母:`10~`

## 转换一个单词

将小写单词转换为大写单词：`gUw`

将大写单词转换为小写：`guw`

将单词中的大写改为小写，将小写改为大写：`g~w`

其中：

* `gu`表示把选定范围全部小写
* `gU`表示把选定范围全部大写
* `w`表示选定范围为单词

依此类推，`ggguG`表示把整篇文章转换为小写，`gg`表示光标移动到文章开头，`G`表示选定范围为到文章结尾

## 转换一行

将整行转换为小写：`guu`。

将整行转换为大写：`gUU`。

将一行中的大写转换为小写，将小写转换为大写：`g~~`

## 总结

`gu`和`gU`分别表示转换为小写和大写，后面跟转换范围，比如`5w`（5个单词）等。
