---
title: django 静态文件的处理

excerpt: 

location: 

layout: blog-post

---
django notes


**目录结构**  
├── settings.py  
├── media  
│   ├── css  
│   │   ├── print.css  
│   │   └── styles.css  
│   └── images  
│       ├── ad180.png   
│       ├── colbg.png   
│       └── headerimg.jpg   
├── settings.py   

**settings.py 配置**
<pre>
MEDIA_ROOT = os.path.join(os.path.dirname(__file__),'media').replace('\\','/')
MEDIA_URL = 'media' 
</pre>

**urls.py配置**
导入
<pre>
from django.views.static import *   
from django.conf import settings   
</pre>

url里添加

`url(r'^media/(?P<path>.*)$','django.views.static.serve',{'document_root':settings.MEDIA_ROOT})`

