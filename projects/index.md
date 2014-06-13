---
layout: page
title:
---
<br />

### 译作：iOS编程指南

豆瓣地址：[iOS编程指南](http://book.douban.com/subject/25879700/)

本书是我和[徐可](https://twitter.com/tuoxie007)合作翻译的书，是一本iOS编程的入门书，讲解非常浅显易懂，包括如何申请iOS开发者帐号以及如果配置Provisioning Profile，这些东西在我学习iOS的过程中还真是耗费了不少时间，私心想着，当时要是有这本书就好了。

不过，这本书以_iOS 6_和_Xcode 4_为背景，略显过时。不过，一些老的东西仍然还是基础的东西，比如_[xib][1]_文件，虽然_[Story Board][2]_可能最终取代_[xib][1]_，了解一些技术的演进历程往往比技术本身更有意思，也更有意义。

<br />

### iOS应用：小豆书僮

iTunes下载地址：[小豆书僮][3]

这个不是我的项目，是我[爱人](http://weibo.com/xiejianfen)的项目，我只是在一旁多做了点家务、贡献了一点点代码。爱好读书的朋友可以下载玩一下，[小豆书僮][3]可以记录你的读书进度、同步读书状态到[豆瓣](http://www.douban.com)。唯一的问题是，这个项目暂时已经停滞了，看起来她似乎也没有计划将这个项目进展下去，不过，支持iOS
7是没问题的。虽然界面简陋点、不大和iOS 7搭配，但是依然是个好用的小工具。

<br />

### 博客：没有比人更高的山

Github地址：[zhlwish.github.io](https://github.com/zhlwish/zhlwish.github.io)

经营这个博客已经到了第五个年头，最初4年一直用[WordPress][4]，功能强大，容易设置，而且我还学习了如何创建[WordPress][4]主题以及插件，有一个小项目[新浪微博WordPress插件][5]，后来新浪微博将OAuth从1.0升级到了2.0，我就没有继续完善这个插件了，一直到2014年仍然有用户来找技术支持，但是用户群体毕竟太少，因此也没有计划在此花额外的时间。

到2014年，换了工作，技术也演进了很多，博客顺应技术发展更换成了[jekyll][6]平台，托管于[github][7]，并且将域名换成了_zhouliang.pro_，导入了最近一部分博客，工作量稍大，完整导入依然是一个长期工作。

陆陆续续写了这么些博客，也看出写作风格的变化，从闹着玩，逐步走向了严谨、顺序的叙述方式，虽然有志于成为一名技术作家，但是依然任重而道远。

<br />

## dotfiles

Github地址：[lzsh](https://github.com/zhlwish/lzsh)

Linux上的配置文件都以点号(.)开头，比如_.vimrc_、_.zshrc_等，因此配置文件也称为_dotfiles_.这个项目将我所常用的配置文件集成在了一起，包括zsh配置([.zshrc](https://github.com/zhlwish/lzsh/blob/master/rcfiles/zshrc))、Vim配置([.vimrc](https://github.com/zhlwish/lzsh/blob/master/rcfiles/vimrc))、tmux配置([.tmux.conf](https://github.com/zhlwish/lzsh/blob/master/confs/tmux.conf))，甚至常用的[git
alias](https://github.com/zhlwish/lzsh/blob/master/shells/gitconfig.sh)、国内的[maven仓库镜像](https://github.com/zhlwish/lzsh/blob/master/confs/maven/settings.xml)。同时使用了[vim-pathogen](https://github.com/tpope/vim-pathogen)以及[git submodule](http://git-scm.com/docs/git-submodule)来管理Vim插件，能方便的升级插件和安装。

使用`curl -L https://raw.githubusercontent.com/zhlwish/lzsh/master/install.sh | sh`一行语句就可以全部安装好，你也可以fork一个，然后自行配置。

<br />

[1]: http://www.speirs.org/blog/2007/12/5/what-are-xib-files.html
[2]: http://stackoverflow.com/questions/8436324/what-is-the-difference-between-a-xib-file-and-a-storyboard
[3]: https://itunes.apple.com/cn/app/xiao-dou-shu-tong-du-shu-jin/id629435651?mt=8
[4]: http://wordpress.org
[5]: http://wordpress.org/plugins/sina-weibo-plugin-for-wordpress/screenshots/
[6]: http://jekyllrb.com/
[7]: http://github.com

