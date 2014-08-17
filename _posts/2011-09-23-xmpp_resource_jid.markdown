---
layout: post
status: publish
published: true
title: XMPP中资源/Resource的解释和JID
author: 周亮
author_login: admin
author_email: zhlwish@gmail.com
author_url: http://www.zhlwish.com
excerpt: "因为之前写过<a href=\"http://www.zhlwish.com/2011/04/04/pyxmpp_gtalk/\"
  title=\"使用PyXMPP向GTalk发送消息\">《使用PyXMPP向GTalk发送消息》</a>一文，最近被一个研究XMPP协议的学妹问到XMPP协议中的资源（Resource）的意思。其实我开始也是一知半解，而且学妹挺诚心的样子，就仔细看了看XMPP协议的文档，这里也感谢这位学妹提供的XMPP协议（RFC3920）的<a
  href=\"http://zhlwish.googlecode.com/files/RFC3920%E4%B8%AD%E6%96%87%E7%BF%BB%E8%AF%91%E7%89%88.doc\"
  target=\"_blank\">中文版</a>和<a href=\"http://zhlwish.googlecode.com/files/rfc3920.pdf\"
  target=\"_blank\">英文版</a>，其实我以前写用pyxmpp的时候也没有仔细看XMPP协议的。不看不知道，一看吓一跳，原来所谓的Resource和我一直很欣赏的Google
  Talk的多客户端同时在线的功能有关系，Google Talk就是基于XMPP协议的。"
wordpress_id: 816
wordpress_url: http://www.zhlwish.com/?p=816
date: '2011-09-23 16:31:20 +0800'
date_gmt: '2011-09-23 08:31:20 +0800'
categories:
- Linux
tags:
- Python
comments:
- id: 483
  author: zluyuer
  author_email: zluyuer@gmail.com
  author_url: http://www.zluyuer.com/
  date: '2011-09-26 06:49:16 +0800'
  date_gmt: '2011-09-25 22:49:16 +0800'
  content: 有这样的学妹多好。。
- id: 993
  author: 展视刘怀山
  author_email: ''
  author_url: http://weibo.com/uniview
  date: '2012-08-22 23:21:11 +0800'
  date_gmt: '2012-08-22 15:21:11 +0800'
  content: 您好，多个资源识别client的时候。在XMPP的范畴里，是否允许一个同一个JID的一个资源，发送到另外一个资源里？当然，我们知道GTALK是不可以的。我的前提是，用XMPP的技术，做一个消息系统，同一个JID在不同终端中，自我通讯，是否可能？
- id: 994
  author: 点团队周亮
  author_email: zhlwish@gmail.com
  author_url: http://weibo.com/zhlwish
  date: '2012-08-26 19:30:18 +0800'
  date_gmt: '2012-08-26 11:30:18 +0800'
  content: 是在抱歉，我没有深入研究过XMPP，可能帮不了你...
- id: 1112
  author: Kenny
  author_email: kang.song@hotmail.com
  author_url: ''
  date: '2013-09-26 10:35:37 +0800'
  date_gmt: '2013-09-26 02:35:37 +0800'
  content: 可行
---

因为之前写过<a href="http://www.zhlwish.com/2011/04/04/pyxmpp_gtalk/" title="使用PyXMPP向GTalk发送消息">《使用PyXMPP向GTalk发送消息》</a>一文，最近被一个研究XMPP协议的学妹问到XMPP协议中的资源（Resource）的意思。其实我开始也是一知半解，而且学妹挺诚心的样子，就仔细看了看XMPP协议的文档，这里也感谢这位学妹提供的XMPP协议（RFC3920）的<a href="http://zhlwish.googlecode.com/files/RFC3920%E4%B8%AD%E6%96%87%E7%BF%BB%E8%AF%91%E7%89%88.doc" target="_blank">中文版</a>和<a href="http://zhlwish.googlecode.com/files/rfc3920.pdf" target="_blank">英文版</a>，其实我以前写用pyxmpp的时候也没有仔细看XMPP协议的。
不看不知道，一看吓一跳，原来所谓的Resource和我一直很欣赏的Google Talk的多客户端同时在线的功能有关系，Google Talk就是基于XMPP协议的。

首先举几个JID的例子，比如下面几个都是完整的JID:

```
xxx@gmail.com /gtalk-client
xxx@gmail.com /plus.google.com
xxx@gmail.com /gmail
xxx@gmail.com /sony-errision-x10-android
```

JID实际上是3部分组成的：节点名（上面四个JID中的“xxx”），域名（上面四个JID中的“gmail.com”，一般是主服务器的域名），资源名（上面四个JID中最后面不同的那部分）
这四个JID都对应到某人的google帐号（xxx@gmail.com），只不过一个对应windows gtalk客户端，第二个对应google plus网页的上的那个聊天窗口，第三个对应google talk的网页窗口，第四个对应手机上的google talk。注意这里资源的名字只是我自己瞎想出来的，可能一般实现的时候会直接有服务器生成一个随机字符串吧。

和QQ不一样的是，XMPP允许一个帐号在不同的地方登录，比如我的电脑、google plus网页、gmail、手机上的google talk现在都是登录状态，别人给我发送消息的时候，我的四个client都会提示我有收到新的消息，但是当我选择用手机回复的时候，本次会话（session）所有消息都会只发送到我的手机，而其他的client（如windows上的google client、gmail里面的client）就不会再收到消息了。

因此除了帐号(xxx@gmail.com)以外，会有另外一个标识符来标识我使用的这种client，这个client就是上文提到的resource，这里上面4个帐号中，email地址后面的字符串就是resource id了
因此为了确认你使用的哪一个客户端，需要resource绑定。绑定后的JID才是一个完整的JID。
上面就是我对XMPP中Resource的理解，也特别感谢这位学妹的问题，才让我对XMPP有了更深入了解的机会。
