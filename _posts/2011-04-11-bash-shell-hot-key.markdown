---
layout: post
status: publish
published: true
title: Bash Shell快捷键
author: 周亮
author_login: admin
author_email: zhlwish@gmail.com
author_url: http://www.zhlwish.com
excerpt: "原文来自这里<a href=\"http://linuxhelp.blogspot.com/2005/08/bash-shell-shortcuts.html\">Bash
  Shell Shortcuts</a>和这里<a href=\"http://www.dbanotes.net/techmemo/shell_shortcut.html\">Bash
  Shell 快捷键的学习使用</a>，但是归根结底，还是来自这里<a href=\"http://linuxhelp.blogspot.com/2005/08/bash-shell-shortcuts.html\">Bash
  Shell Shortcuts</a>，我只是稍微翻译了一下，重新排了序\r\n"
date: '2011-04-11 20:49:36 +0800'
date_gmt: '2011-04-11 12:49:36 +0800'
categories:
- Linux技术
tags:
- shell
comments: []
---
原文来自这里<a href="http://linuxhelp.blogspot.com/2005/08/bash-shell-shortcuts.html">Bash Shell Shortcuts</a>和这里<a href="http://www.dbanotes.net/techmemo/shell_shortcut.html">Bash Shell 快捷键的学习使用</a>，但是归根结底，还是来自这里<a href="http://linuxhelp.blogspot.com/2005/08/bash-shell-shortcuts.html">Bash Shell Shortcuts</a>，我只是稍微翻译了一下，重新排了序。

## Ctrl系

快捷键        |说明
-------------|-----------------------------------------------------------
Ctrl + a     |光标跳转到命令的开头（当命令敲完了，结果发现开头敲错了的时候用）
Ctrl + e     |光标跳转到命令结尾
Ctrl + b     |光标往左移动一个字符
Ctrl + f     |光标往右移动一个字符
Ctrl + x + x |光标移动到最后和当前位置两个地方跳转
Ctrl + d     |删除光标所在位置的字符
Ctrl + h     |删除光标所在位置之前的一个字符
Ctrl + k     |删除光标所在位置之后（右边）的所有字符
Ctrl + u     |删除光标所在位置之前（左边）的所有字符 （密码输入错误的时候比较有用）
Ctrl + w     |删除最后输入的单词
Ctrl + c     |终止正在执行的命令
Ctrl + z     |挂起/停止正在执行的命令
Ctrl + l     |清屏，类似 clear 命令
Ctrl + r     |查找之前执行过的命令
Ctrl + y     |在当前光标处插入之前输入的命令 （有用）

## Alt系

快捷键      |说明
-----------|-----------------------------------------------------------
Alt + <    |显示历史命令中的第一条 （咱中文用户就不用试了，和输入法切换冲突）
Alt + >    |显示历史命中中的最后一条
Alt + ?    |显示命令不全的候选项
Alt + *    |插入命令不全的所有候选项
Alt + /    |补全文件（夹）名称
Alt + .    |插入前一个命令的最后一个参数 （这个很好很强大）
Alt + b    |光标往左移动一个单词
Alt + f    |光标往右移动一个单词（诶，和显示菜单的快捷键冲突了）
Alt + c    |将光标所在的字符变成大写
Alt + d    |删除光标所在位置的单词
Alt + l    |将单词中光标位置之后的字符变成大写
Alt + u    |将单词中光标位置之后的字符变成大写
Alt + t    |在单词中的字符间跳转（诶，和菜单的快捷键冲突了）
Alt + y    |在当前光标处插入**之前**_之前_（两个之前，不是我敲错了）输入的命令（请和Ctrl + y比较）
Alt + back-space    |删除光标所在位置之前（左边）的所有字符

## 其他特定的键绑定

输入 bind -P 可以查看所有的键盘绑定。这一系列我觉得更为实用。

> _下面的命令中2T表示按两下Tab键_

快捷键        |说明
-------------|-----------------------------------------------------------
2T           |命令行补全，显示所有候选项
(string)2T   |命令行补全，显示以string开头的所有候选项
/2T          |显示文件夹中的所有文件，包括.开头的隐藏文件
./2T         |显示文件夹的子文件夹，包括.开头的隐藏文件
*2T          |显示文件夹的子文件夹，不包括.开头的隐藏文件
~2T          |显示"/etc/passwd"vs中所有的用户？ （不是很明白这个是干什么用的）
$2T          |所有的系统变量
@2T          |"/etc/hosts"中的所有的项 （依然不明白）
=2T          |和ls或者dir输出的一样 （更不明白有了ls，还要这个干嘛，Tab控）
Esc + T      |交换光标前面的两个单词 （这个好玩）

有些不实用的被我直接删掉了，如果需要找的话，参考<a href="http://www.bigsmoke.us/readline/shortcuts">Readline shortcuts</a>这个把，里面居然有简单的图示。
