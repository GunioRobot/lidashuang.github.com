---
title: clojure里的序列操作 
excerpt: 
location: 
layout: blog-post
category: clojure

---

clojue 中的序列操作

什么是序列？
----------------
在Clojure中，任何逻辑上可看做数据项集合（collection of items）     
的数据结构都可以使用序列这样一种统一的方式来读取，写入和修改。    
类似于lisp里的列表。序列可以为空。在clojure里大多数的序列是惰性    
惰性意味着，只有这个序列被真正需要的时候，才会去求值。序列还有    
一个特性就是不变性,也就是说序列一旦创建是不会改变的。    
seq 
------

seq 接受一个序列，返回一个序列或者是返回nil,大多数操作序列函数    
会自动调用这个函数对序列处理。     

{% highlight clj %}
	(seq [1 2 3]) ; => (1 2 3)
	(seq [ ]) ; => nil
{% endhighlight %}

first 
--------------

得到序列中的第一个元素    
如果参数是空或是nil则返回nil    

example: 
	
{% highlight clj %}
	(first [34 23 15]) ; => 34
	(first [ ]) ; => nil
{% endhighlight %}

rest 
----------
得到除第一个元素外其他的元素     

example: 
	
{% highlight clj %}
	(rest [34 23 15]) ; => (23 15)
	(rest [ ]) ; => ()
{% endhighlight %}
cons
--------
可以用这个函数构造新的序列通过对先前的序列添加元素     

example:

{% highlight clj %}
	(cons 1 [2 3 4]) ; => (1 2 3 4)
{% endhighlight %}

next 
--------------
next会返回第一个元素以后的所有元素      
(next aseq) 相当于 (seq (rest (aseq)))          

example:

{% highlight clj %}
	(next [1 2 3 4]) ; => (2 3 4)
	(next [ ]) ; => nil
{% endhighlight %}

conj,into 
--------------
(conj  coll  element  &  elements)       
(into  to-coll  from-coll)       
conj将一个或多个元素添加到序列中，而into是将一个序列中    
的元素添加到另一个序列中。

对列表操作时会将元素添加到前面的位置。	
example:
{% highlight clj %}
	(conj  '(10  20  30)  :a) ; => (:a 10 20 30)
	(into  '(10  20  30)  '(:a  :b  :c)) ; => (:c :b :a 10 20 30)
{% endhighlight %}

对向量操作时，会将元素添加到后边
example:

{% highlight clj %}
	(conj  [10  20  30]  :a) ; => [10 20 30 :a]
	(into  [10  20  30]  [:a  :b  :c]) ; => [10 20 30 :a :b :c]
{% endhighlight %}

range 
----------
类似python里的函数，指定起始，终点，步进，返回所有符合的元素    

example:
	
{% highlight clj %}
	(range  10  20  2) ; => (10 12 14 16 18)
	(range 1 10) ;=>(1 2 3 4 5 6 7 8 9)
{% endhighlight %}

repeat 
---------
重复一个元素n 次     

example:
	
{% highlight clj %}
	(repeat  5  "p") ; => ("p" "p" "p" "p" "p")
{% endhighlight %}

iterate, take
--------------
函数原型     
(iterate  f  x)      
(take  n  sequence)      
iterate 会将一个函数f作用于x,x是一个起始值， 没有终点     
而take 取得序列的前n个元素,take进行的是惰性求值        
example: 
	
{% highlight clj %}
	(take  10  (iterate  inc  1)) ; => (1 2 3 4 5 6 7 8 9 10)
{% endhighlight %}
	
concat 
-----------
用于任何序列的串连,序列可以是不同的类型          

example:
	
{% highlight clj %}
	(concat [22 "green" false] [33 44]) ; => (22 "green" false 33 44)
	(concat #{22 "green" false} '(33 44)) ; => ("green" false 22 33 44)
{% endhighlight %}


参考    
* [clojure-notes](http://clojure-notes.rubylearning.org/)
* [Practical Clojure](http://shu.im/books/4e9af8976cccb37698000531)











