---
title: Hello world in clojure 

excerpt: clojure 一门jvm上的lisp方言

location:

layout: blog-post

---

## clojure 
clojre 是jvm上一门新语言，也是lisp的一门方言。这门语言简单实用，相比java,它处理同类问题更加健壮，     
代码量更少。从 20 世纪 50 年代开始至今，Lisp 语言家族已经存在很长时间了。Lisp 使用的是截然不同的 S-表达式或前缀 注释。这个注释可以被归结为 (function arguments...)。通常总是从函数名开始，然后列出要向这个函数添加的零个或多个参数。函数及其参数通过圆括号组织在一起。数量众多的括号也成为了 Lisp 的一大特征。
##REPL
REPL是clojure的解释器环境(read/eval/print/loop)，类似于python的IDLE 。在官网下载clojure 安装文件。     
执行下面的命令进入REPL环境：
	java -jar clojure-1.3.0.jar
提示符:
	Clojure 1.3.0
	user=>
#hello world 
	user=>(println "Hello world")
	"Hello world"
	
