---
title: 多个github帐号问题解决
excerpt:fatal: The remote end hung up unexpectedly 解决 
layout: blog-post
---

github.com使用ssh公匙认证。一台如果使用多个github的帐号提交会出现权限问题，不能提交。
解决方法 
配置~/.ssh/config文件，ssh访问服务器的时候，对于不同的帐号，使用不同的ssh公匙。
已经生成两个公匙 。

    # Default github user(first@mail.com)
    Host github.com
    HostName github.com
    User git
    IdentityFile /home/lidashuang/.ssh/lidashuang_rsa

    # second user(second@mail.com)
    Host github-second
    HostName github.com
    User git
    IdentityFile  /home/lidashuang/.ssh/dashuang_rsa

第二个帐号添加远程仓库方式

	git remote add test git@github-second:second/test.git 
	并非原来的git@github.com:second/test.git


