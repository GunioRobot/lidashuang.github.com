---
title: Hello world in clojure 

excerpt: clojure 一门jvm上的lisp方言

location:

layout: blog-post

---

## clojure 
clojre 是jvm上一门新语言，也是lisp的一门方言。这门语言简单实用，相比java,它处理同类问题更加健壮，     
代码量更少。从 20 世纪 50 年代开始至今，Lisp 语言家族已经存在很长时间了。Lisp 使用的是截然不同的 S-表达式或前缀 注释。这个注释可以被归结为 (function arguments...)。通常总是从函数名开始，然后列出要向这个函数添加的零个或多个参数。函数及其参数通过圆括号组织在一起。数量众多的括号也成为了 Lisp 的一大特征。
##REPL 交互式编程环境
REPL是clojure的解释器环境(read/eval/print/loop)，类似于python的IDLE 。在官网下载clojure 安装文件。     
依赖jdk,运行REPL之前，确认安装好java环境。       
执行下面的命令进入REPL环境：
	java -jar clojure-1.3.0.jar
提示符:
	Clojure 1.3.0
	user=>

#hello world 
	user=>(println "Hello world")
	"Hello world"

#数据类型

clojure 是一门动态类型的语言。意味着你不必在你的程序里明确定义函数，符号参数等的类型。   
但是这些值也有自己的类型。 

##clojure 内建类型

* __number__	  普通数字			example: 16
* __String__	  字符串			example: "hello!"
* __Boolean __	  bool类型			example: ture 
* __Character__	  字符前有反斜杠    example:  \a
* __Keyword __	  关键字以冒号开头  example: :key
* __List __		  列表圆括号        example: '(1 2 3)
* __Vector__	  向量中括号		example: \[1 2 3\]
* __Map__		  键值对			example: \{:kel val :key val\}
* __Set__		  大括号前有井号    example: #{1 2 3}

##NIL
nil 表示nothing或novlaue 
nil 等同于java里的null

#vim 高亮

[vim高亮插件](http://www.vim.org/scripts/script.php?script_id=2501)
