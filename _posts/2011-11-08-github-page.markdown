---
title: github上搭建自己的博客
excerpt: 在github上搭建博客，用git管理博客
layout: blog-post
category: git

--- 

github.com的[jekyll](https://github.com/mojombo/jekyll)是个简单的用于生成静态站点的工具。     
  
所有的文章会生成静态的html文件，关键是这东西可以放在github上，可以绑定自己的域名,    
有稳定的服务器给你。支持rss,评论，代码高亮。符合程序员的口味。		

# 搭建过程
大体过程如下，如果这也不想做，你也可以去jekyll项目主页的wiki看下别人的站点，直接用别做的    
也可以。



# github pages

首先得用到github 的pages功能，github pages可以很方便的建立项目主页，个人主页。    
按照下面的步骤创建自己的pages    

1. 以你的用户名(比如我的是lidashuang)创建lidashuang.github.com的版本库。    
1. 在本地clone刚创建的版本库，创建index.html 添加点内容。
1. push 到github的远程版本库。

现在就可以访问<http://lidashuang.github.com> 

# 绑定域名

1. 将你的域名的ip指向 207.97.227.245
1. 在你版本库目录下创建CNAME文件，并写上你的域名。 

# jekyll

jekyll 不是服务器，只是一个转换工具。当然也可以在本地搭建相应的环境，写好的结构      	化文本，直接就可以查看转换成网页后的效果。Jekyll解析（parsing）在\_posts目录   
中的文件，以获取博客文章的列表。每篇文章文件标题里包括有，最终生成静态HTML文    
件的发布日期和略缩名（slug，出现在URL中的名字）		

# 安装jekyll相应工具

安装好ruby环境及相应的依赖包，用ruby的包管理工具直接安装。   
	
	gem install jekyll 

# 使用

在版本库目录运行 

	jekyll --server 

打开浏览器，<http://127.0.0.1:4000> 访问。这会在目录里生成\_site 文件夹，存放   
临时文件。 可以.gitingore 里配置，不在版本库里添加此类文件。		


# jekyll 处理规则

目录结构		

\_config.yml      
存储了一些设置，大部分的设置都可以通过命令行指定，但放到配置文件里更方便些

\_layouts     
\_layouts文件夹存放的是模板文件，文章会被渲染到这些模板里，变量指代的是文章内容

\_posts       
这里就是真正存放博客文章的地方了，文件命名要遵守这种格式:year-month-day-title.markup

\_site			
这个文件夹是程序生成的，如果本地没有安装jekyll的话，是不会有这个文件夹的，		
如果想要先本地预览一下，再提交到github，最好通过.gitignore把这个文件夹排除。

index.html		
这个文件也有一个yaml前缀 ，可以指定使用哪个模板，标题等等，所有根文件夹下的		
.html/.htm/.textile/.markdown都会被解析。

other files/folders    
上面没有列出的文件/文件夹都会被jekyll放到\_site文件夹下，如css/image/script等等。		

#  支持的格式 

github支持很多种标记语言，我用的是markdown,很简单易用。
这里有个教程
http://qingbo.net/picky/502-markdown-syntax.html


# 一些函数

循环输出 3 篇文章			
	for post in site.posts limit:3
	endfor

循环输出最近 3 篇		

	for post in site.posts offset:3 limit:3
	endfor

日期

	page.date | date:"%B %b, %Y"

分页输出

	for post in paginator.posts
	  content
	endfor

分页

	if paginator.previous_page
	    //判断输出前一个分页
	    //"page" + paginator.previous_page
	endif
	if paginator.next_page
	    //判断输出后一个分页
	    //"page" + paginator.next_page
	endif
	for page in (1..paginator.total_pages)
	if page == paginator.page
	       //如果是当前分页
	       //page
	else
	     //不是的话输出其他分页链接号码
	     //"page" + page
	endif
	endfor

文章页面显示前一篇文章和后一篇文章

	if page.previous
		//url:    page.previous.url
		//title:  page.previous.title | truncatewords:5
	endif
	if page.next
	//url:    page.next.url
	//title:  page.next.url | truncatewords:5


# 语法高亮 

github 默认是支持代码高亮的。


highlight 后边是语言，也可以python,java等等。支持很多种高亮，具体   
可以在这查看 http://pygments.org/docs/lexers/		

# 评论系统

评论可以用[disqus](http://www.disqus.com)  社会化评论系统。		
disqus的文档 http://docs.disqus.com/


#links

官方的pages教程 [pages](http://pages.github.com/)    
jekyll项目主页 [jekyll](https://github.com/mojombo/jekyll)     
一些托管在github的站点[site](https://github.com/mojombo/jekyll/wiki/Sites)      
模版语言[Liquid](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers)     
[Textile](http://en.wikipedia.org/wiki/Textile_%28markup_language%29)一种标记语言     
[markdown](http://en.wikipedia.org/wiki/Markdown)另一种简单的标记语言    
[pygment](http://pygments.org/docs/lexers/)		  
[YAML Front Matter](https://github.com/mojombo/jekyll/wiki/yaml-front-matter)		  
