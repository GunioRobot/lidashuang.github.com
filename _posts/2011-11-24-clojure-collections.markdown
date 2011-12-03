---
title: clojure collections 
excerpt: clojure 学习笔记
location: 
layout: blog-post
category: clojure

---
clojure里的collection 数据类型有list，vector，set，map。     
特点：     	
具有不变性,那些被认为是“改变了“它们的操作实际上是返回了一个全新的依旧不可变的对象        
持久性，快速高效    
与java里的数据类型互操作    

list列表 
-----------
列表中可以包含任何元素		
空列表	  
{% highlight clj %}
	() ; => ()
{% endhighlight %}

列表不但可以表示数据，函数调用也是用列表完成到。       

	(println "Hello World!")		

它是一串可执行的代码，同时也是一个列表。首先，Clojure读取程序将它作为一个列表
来解析，然后将其第一个元素（在这里是println）作为函数来对它求值，然后将剩余的
部分（"Hello World!"）作为参数传递给它。
如果只是作为数据结构而不是可执行代码来使用列表，只需要给列表加一个单引号作为前			
缀即可		

	(def nums '(1 2 3 4 5))

quote 
(a b c)会被当作函数调用，可以用'或quote表明是数据，而不是代码'(1 2 3)和				
(quote (1 2 3))只是表示相同事物的不同方法而已　　			

Vectors向量
------------
类似数组，可以用索引访问。用法类似于list。总的来说，对于很多应用来讲向量更好因       
为跟列表相比向量毫无劣势而且更快。　					
向量在Clojure程序中的字面表示是使用方括号。 

	(def nums [1 2 3 4 5])
	[ ] ; => [ ]
通过索引访问

	(["hello" "world" 1 2 3] 1) ; => "world"
	
sets 集合
--------------
集合数据项是唯一的，集合的字面语法是一个井号后面跟着包围在花括号里的集合成员。				
例如如下的代码：

	(def languages #{:java :lisp :c++})

当不允许有重复数据项，不需要保持数据项的添加顺序的话，用集合更好。clojure支持        
两种类型到集合，排序和未排序到。			

	(sorted-set "Mandy" "Anita" "Rich") ; #{"Anita" "Mandy" "Rich"}
	(hash-set "Mandy" "Anita" "Rich") ; #{"Anita" "Mandy" "Rich"}

重复项会移除			

	(hash-set "Rich" "Mandy" "Anita" "Rich") ; #{"Anita" "Mandy" "Rich"}

Maps 映射
-----------
映射 键值对，唯一到键，每一个键有值对应						

	{ } ; => { }
	{:Ruby  "Matz"  :Clojure  "Hickey"} ; => {:Ruby  "Matz"  :Clojure  "Hickey"}

可以不用绑定符号，通过键访问				

	(:a {:a 1, :b 2}) ; => 1

也可以绑定到变量					

	(def  inventors  {:Ruby  "Matz"  :Clojure  "Hickey"})

键不存在到话，返回nil						

	(inventors :Java) ; => nil

keys 函数返回键

	(keys inventors) ; => (:Ruby :Clojure)

vals函数返回值			

	(vals inventors) ; => ("Matz" "Hickey")
	
一些有用到函数
------------------

count 函数返回数据项个数

	(count [22 "green" false]) ; => 3
	(count '()) ; => 0

reverse 反转

	(reverse [2 42 72]) ; => (72 42 2)
	(reverse "hello") ; => (\o \l \l \e \h)
	(reverse '(2 42 72)) ; => (72 42 2)

apply函数将某一函数应用到collection的所有到数据项	

	(apply - [34 23 9])  ; => 2

map接受参数是一个函数，collection，并返回新到collection

	(map * [1 2 3 4] [1 2 3 4]) ; => (1 4 9 16)

参考    

* [clojure-notes](http://clojure-notes.rubylearning.org/)
* [Practical Clojure](http://shu.im/books/4e9af8976cccb37698000531)







