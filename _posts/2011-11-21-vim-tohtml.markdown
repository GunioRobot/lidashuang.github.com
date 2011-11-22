---
title  vim  TOhtml
excerpt:  vim to html 
location: 
layout: blog-post
category: tool

---
vim Tohtml功能
测试下vim的Tohtml功能，在命令模式下

	:28,46Tohtml

<style type="text/css">
pre { font-family: monospace; color: #d0d0d0; background-color: #121212; }
.lnr { color: #bcbcbc; background-color: #1c1c1c; }
.Type { color: #5fd7ff; }
.String { color: #afaf87; }
.Number { color: #af5fff; }
.Special { color: #5fd7ff; background-color: #080808; }
.Statement { color: #d7005f; font-weight: bold; }
</style>


<pre>
<span class="Statement">CREATE</span> <span class="Special">TABLE</span> <span class="Special">IF</span> <span class="Statement">NOT</span> <span class="Statement">EXISTS</span> `typecho_comments` (
  `coid` int(<span class="Number">10</span>) unsigned <span class="Statement">NOT</span> <span class="Special">NULL</span> AUTO_INCREMENT,
  `cid` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
  `created` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
  `author` <span class="Type">varchar</span>(<span class="Number">200</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
  `authorId` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
  `ownerId` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
  `mail` <span class="Type">varchar</span>(<span class="Number">200</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
  `url` <span class="Type">varchar</span>(<span class="Number">200</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
  `ip` <span class="Type">varchar</span>(<span class="Number">64</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
  `agent` <span class="Type">varchar</span>(<span class="Number">200</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
  `text` text,
  `<span class="Special">type</span>` <span class="Type">varchar</span>(<span class="Number">16</span>) <span class="Special">DEFAULT</span> <span class="String">'comment'</span>,
  `status` <span class="Type">varchar</span>(<span class="Number">16</span>) <span class="Special">DEFAULT</span> <span class="String">'approved'</span>,
  `parent` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
  PRIMARY KEY (`coid`),
  KEY `cid` (`cid`),
  KEY `created` (`created`)
) ENGINE=MyISAM  <span class="Special">DEFAULT</span> CHARSET=utf8 AUTO_INCREMENT=<span class="Number">1320</span> ;
</pre>
























