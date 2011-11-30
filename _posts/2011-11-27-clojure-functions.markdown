---
title: clojure函数
excerpt: clojure 函数学习笔记
location: 
layout: blog-post
category: clj
---
clojure 函数学习笔记

fn定义函数
------------

例如在REPL中执行下面的代码，函数fn 后面是在vector数据结构里的两个参数，后边是函数体      
最后返回一个函数。    

{% highlight lisp %}

	user=> (fn [x,y](+ x y))
	#<user$eval__1$fn__3 user$eval__1$fn__3@1e808ca>
{% endhighlight %}

现在我们可以将这个函数绑定到一个符号，以便我们能使用这个函数      

	user=> (def add (fn [x,y] (+ x y)))
	#'user/add

现在我们就可以使用这个函数了。     
也可以直接给函数传递参数，不用绑定到具体符号上。     

	user=>((fn [x,y] (+ x y)) 1 2)
	user=>3

defn 定义函数
----------------
clojure提供了一个函数绑定到符号的快捷方法defn     

	user=> (defn add [x,y] (+ x y))
	#'user/add
	user=> (add 3 4)
	7

其他快捷定义函数
-------------------
例如下面的这个函数，#后边就是函数体，%表示参数        

	user=> (def add #(+ % %)) 
	#'user/add
	user=> (add 3)
	6

也可在%后加个数字，表示第几个参数,如下边%1 表示第一个参数，     
	
	user=> (def add #(+ %1 %2))
	#'user/add
	user=> (add 3 2)
	5

	


