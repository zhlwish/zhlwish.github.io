---
layout: post
title: 弹出消息框的命令行工具terminal-notifier
date: 2014-06-04 14:56:26
category: Mac
excerpt: <a href="https://github.com/alloy/terminal-notifier/">terminal-notifier</a>是一个开源项目，适用于Mac系统，可以在通过命令的方式弹出Mac消息提示框。如果一个Shell脚本的运行时间较长，则可以用ternimal-notifier在执行完成后弹出消息框提示你，特别适合使用命令行较多的程序员。
---

[terminal-notifier](https://github.com/alloy/terminal-notifier/)是一个开源项目，适用于Mac系统，可以在通过命令的方式弹出Mac消息提示框。如果一个Shell脚本的运行时间较长，则可以用ternimal-notifier在执行完成后弹出消息框提示你，特别适合使用命令行较多的程序员。

安装：

    brew install terminal-notifier

通过命令来弹出消息提示框：

    terminal-notifier -message "Hello, this is my message" \
                        -title "Message Title" \ 
                        -sound default

本身是一个Mac程序，也有对应的gem包，在Ruby程序中可以使用：

安装gem包：

    gem install terminal-notifier

在Ruby程序中使用：

    TerminalNotifier.notify('Hello World', 
                        :title => 'Ruby', 
                        :subtitle => 'Programming Language', 
                        :sound => 'default')

sound对应Mac系统 System Preference -> Sound -> Sound Effects 中的声效。