# blog 模板
[Bill_blog](http://feng139967.github.io)  

## 说明文档

* 开始
	* [开始](#get-started)
	* [写一篇博文](#write-posts)
* 各组成部分
	* [侧边栏](#sidebar)
	* [mini-about-me](#mini-about-me)
	* [标签云](#featured-tags)
	* [好友链接](#friends)
	* [HTML5演示文档布局](#keynote-layout)
* 评论与 Google/Baidu Analytics
	* [评论](#comment)
	* [网站分析](#analytics) 
* 高级部分
	* [自定义](#customization)
	* [标题底图](#header-image)

# 
#### Get Started

你可以通用修改 `_config.yml`文件来轻松的开始搭建自己的博客:

```
# Site settings
title: XXX Blog             # 你的博客网站标题
SEOTitle: XXX Blog			# 在后面会详细谈到
description: "Cool Blog"    # 随便说点，描述一下

# SNS settings      
github_username: XXXXXX     # 你的github账号
weibo_username: XXXXXX      # 你的微博账号，底部链接会自动更新的。

# Build settings
# paginate: 10              # 一页你准备放几篇文章
```

Jekyll官方网站还有很多的参数可以调，比如设置文章的链接形式...网址在这里：[Jekyll - Official Site](http://jekyllrb.com/) 中文版的在这里：[Jekyll中文](http://jekyllcn.com/).

#### write-posts

要发表的文章一般以markdown的格式放在这里`_posts/`，你只要看看这篇模板里的文章你就立刻明白该如何设置。

yaml 头文件长这样:

```
---
layout:     post
title:      "Hello 2015"
subtitle:   "Hello World, Hello Blog"
date:       2015-01-29 12:00:00
author:     "XXX"
header-img: "img/post-bg-2015.jpg"
tags:
    - first_tags
    - Second_tags
---

```

#### SideBar

设置是在 `_config.yml`文件里面的`Sidebar settings`那块。
```
# Sidebar settings
sidebar: true  #添加侧边栏
sidebar-about-description: "简单的描述一下你自己"
sidebar-avatar: /img/avatar-xx.jpg     #你的大头贴，请使用绝对地址.
```

侧边栏是响应式布局的，当屏幕尺寸小于992px的时候，侧边栏就会移动到底部。具体请见bootstrap栅格系统 <http://v3.bootcss.com/css/>


#### Mini About Me

Mini-About-Me 这个模块将在你的头像下面，展示你所有的社交账号。这个也是响应式布局，当屏幕变小时候，会将其移动到页面底部，只不过会稍微有点小变化，具体请看代码。

#### Featured Tags

看到这个网站 [Medium](http://medium.com) 的标签云非常的炫酷，所有我在将他加了进来。
这个模块现在是独立的，可以呈现在所有页面，包括主页和发表的每一篇文章标题的头上。

```
# Featured Tags
featured-tags: true  
featured-condition-size: 1     # A tag will be featured if the size of it is more than this condition value
```

唯一需要注意的是`featured-condition-size`: A tag will be featured if the size of it is more than this condition value. 
 
内部有一个条件模板 `{% if tag[1].size > {{site.featured-condition-size}} %}` 是用来做筛选过滤的.


#### Friends

好友链接部分。这会在全部页面显示。

设置是在 `_config.yml`文件里面的`Friends`那块，自己加吧。

```
# Friends
friends: [
    {
        title: "Blog",
        href: ""
    }
]
```


#### Keynote Layout

HTML5幻灯片的排版：

这部分是用于占用html格式的幻灯片的，一般用到的是 Reveal.js, Impress.js, Slides, Prezi 等等.我认为一个现代化的博客怎么能少了放html幻灯的功能呢~

其主要原理是添加一个 `iframe`，在里面加入外部链接。你可以直接写到头文件里面去，详情请见下面的yaml头文件的写法。

```
---
layout:     keynote
iframe:     "http://"
---
```

iframe在不同的设备中，将会自动的调整大小。保留内边距是为了让手机用户可以向下滑动，以及添加更多的内容。


#### Comment

博客不仅的多说[Duoshuo](http://duoshuo.com)评论系统，也支持disqus[Disqus](http://disqus.com)评论系统。

disqus国际比较流行，界面也很大气、简介，如果有人评论，还能实时通知，直接回复通知的邮件就行了。缺点是评论必须要去注册一个disqus账号，分享一般只有Facebook和Twitter，另外在墙内加载速度略慢了一点。想要知道长啥样，可以看以前的版本点[这里](http://brucezhaor.github.io/about.html) 最下面就可以看到。

多说国内主流社交软件都有分享按钮，登陆方便，比较好管理，就是界面丑了一点。当然你是可以自定义界面的css的，详情请看多说开发者文档。

**首先**，你需要去注册一个账号，不管是disqus还是多说的。**不要直接使用我的啊！**

**其次**，你只需要在下面的yaml头文件中设置一下就可以了。

```
duoshuo_username: _你的用户名_
# 或者
disqus_username: _你的用户名_
```

**最后**多说是支持分享的，如果你不想分享，请这样设置：`duoshuo_share: false`。你可以同时使用两个评论系统，不过个人感觉怪怪的。

#### Analytics

网站分析，现在支持百度统计和Google Analytics。需要去官方网站注册一下，然后将返回的code贴在下面：

```
# Baidu Analytics
ba_track_id: 4cc1f2d8f3067386cc5cdb626a202900

# Google Analytics
ga_track_id: 'UA-49627206-1'            # Format: UA-xxxxxx-xx
ga_domain: XXX
```

#### Customization

如果你喜欢折腾，你可以去自定义我的这个模板的code，[Grunt](gruntjs.com)的环境已经搭好了。（非常感谢Clean Blog这个模板）

There are a number of tasks it performs like minification of the JavaScript, compiling of the LESS files, adding banners to keep the Apache 2.0 license intact, and watching for changes. Run the grunt default task by entering `grunt ` into your command line which will build the files. You can use `grunt watch` if you are working on the JavaScript or the LESS.

**Try to understand code in `_include/` and `_layouts/`, then you can modify Jekyll [Liquid](https://github.com/Shopify/liquid/wiki) template directly to do more creative customization.**

#### Header Image

本模板的标题是**白色**的，所以背景色要设置为**灰色**或者**黑色**，总之深色系就对了。
