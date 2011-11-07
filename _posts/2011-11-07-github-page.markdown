---
title: github上搭建自己的博客
excerpt: 在github上搭建博客，用git管理博客
location: 
category: git
layout: blog-post
--- 
github.com出的[jekyll](https://github.com/mojombo/jekyll)是个简单的用于生成静态站点的工具。     
所有的文章会生成静态的html文件，关键是这东西可以放在github上，可以绑定自己的域名。还有稳定的     
服务器给你。用git方便的管理源文件。

# github pages

首先得用到github 的pages功能，github pages可以很方便的建立项目主页，个人主页。按照下面的步骤创建自己的pages      
1. 以你的用户名(比如我的是lidashuang)创建lidashuang.github.com的版本库。
1. 在本地clone刚创建的版本库，创建index.html 添加点内容。
1. push 到github的远程版本库。


# jekyll
jekyll 不是服务器，只是一个转换工具。只要将你写好的结构化文本push到github上，jekyll会自动转换成相应的   
html文件。
## jekyll 的规则

# 一些函数


#links
官方的教程 [pages](http://pages.github.com/)
