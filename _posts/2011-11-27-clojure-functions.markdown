---
title: clojure函数
excerpt: clojure 函数学习笔记
location: 
layout: blog-post
category: clj

---

clojure 函数学习笔记

fn定义匿名函数
------------------

例如在REPL中执行下面的代码，函数fn 后面是在vector数据结构里的两个参数，后边是函数体      
最后返回一个函数。    

	user=> (fn [x,y](+ x y))
	#<user$eval__1$fn__3 user$eval__1$fn__3@1e808ca>

直接给参数       

	((fn [x] (+ x 1)) 9) ; => 10

现在我们可以将这个函数绑定到一个符号，以便我们能使用这个函数      

	user=> (def add (fn [x,y] (+ x y)))
	#'user/add

现在我们就可以使用这个函数了。     
也可以直接给函数传递参数，不用绑定到具体符号上。     

	user=>((fn [x,y] (+ x y)) 1 2)
	user=>3

defn 定义函数
----------------
clojure提供了一个函数绑定到符号的快捷方法defn,函数体中最后一个
表达式结果被返回，也可能是nil 。

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

控制结构 if if-not 
-----------------------------
if 的写法     

     	(println (if  (<  34  100)  "yes" ))       
        ; => yes      

如要第一个if逻辑语句错误，你又指定else语句，则返回nil     

	(if  (<  50000  100)  "yes" )
	; => nil

if-not

	(if-not test consequent alternative?)

如果test 是false,consequent会被执行，否则执行alternative     

cond和condp     

cond 相当于case语句,只不过后边的条件是表达式，例如     

		(def x 10)
		(cond
		(< x 0) (println "Negative!")
		(= x 0) (println "Zero!"))
		; => nil

都不符合条件时，返回nil,可以用:default 指定默认不符合条件时的默认规则         

	(cond
	(< x 0) (println "Negative!")
	(= x 0) (println "Zero!")
	:default (println "Positive!"))
	; => Positive!
cond  中每个case条件都是一个测试的语句    

condp宏

两个例子：   

	(condp = 1
	1 "Clojure"
	2 "Ruby"
	3 "Java"
	"Sorry, no match")
	; => "Clojure"

	(condp = 5
	1 "Clojure"
	2 "Ruby"
	3 "Java"
	"Sorry, no match")
	; => "Sorry, no match"

condp 比较类似其他语言里的case语句

* when,when-not 
when比较类似天if, 不同的是when 没有 else 条件， 
	
<pre>
(when true "do-this-first" "then-that" "finally this") ; => "finally this"
</pre>

when-not 与 when相反，当false的时候，后边的表达式会被执行     

	(when-not true "do-this-first" "then-that" "finally this") ; => nil
	(when-not false "do-this-first" "then-that" "finally this") ; => "finally this"

* do 
do 会执行序列中的所有表达式      
	
<pre>
(do (println "Hello.") (+ 2 2))
Hello.
4
</pre>

什么时候用do呢？当我们使用if的时候，只会执行其中的一条表达式语句，可以用do执行多条语句      

	(if (odd? 3) (println "First true form") (println "Second true form (will not print)")) ;
	=> First true form

	(if (odd? 3) (do (println "First true form") (println "Second true form (will print)")))
	; => First true form
	; => Second true form (will print)


参考
* [clojure-notes](http://clojure-notes.rubylearning.org/)
* [Practical Clojure](http://shu.im/books/4e9af8976cccb37698000531)

