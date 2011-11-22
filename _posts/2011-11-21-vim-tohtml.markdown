---
title  vim  TOhtml
excerpt:  vim to html 
location: 
layout: blog-post
category: tool

---

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
	<span class="lnr">28 </span>
	<span class="Statement">CREATE</span> 
	<span class="Special">TABLE</span>
	<span class="Special">IF</span>
	<span class="Statement">NOT</span> 
	<span class="Statement">EXISTS</span> `typecho_comments` (
	<span class="lnr">29 </span>  `coid` int(<span class="Number">10</span>) unsigned <span class="Statement">NOT</span> <span class="Special">NULL</span> AUTO_INCREMENT,
		<span class="lnr">30 </span>  `cid` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
		<span class="lnr">31 </span>  `created` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
		<span class="lnr">32 </span>  `author` <span class="Type">varchar</span>(<span class="Number">200</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
		<span class="lnr">33 </span>  `authorId` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
		<span class="lnr">34 </span>  `ownerId` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
		<span class="lnr">35 </span>  `mail` <span class="Type">varchar</span>(<span class="Number">200</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
		<span class="lnr">36 </span>  `url` <span class="Type">varchar</span>(<span class="Number">200</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
		<span class="lnr">37 </span>  `ip` <span class="Type">varchar</span>(<span class="Number">64</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
		<span class="lnr">38 </span>  `agent` <span class="Type">varchar</span>(<span class="Number">200</span>) <span class="Special">DEFAULT</span> <span class="Special">NULL</span>,
		<span class="lnr">39 </span>  `text` text,
		<span class="lnr">40 </span>  `<span class="Special">type</span>` <span class="Type">varchar</span>(<span class="Number">16</span>) <span class="Special">DEFAULT</span> <span class="String">'comment'</span>,
		<span class="lnr">41 </span>  `status` <span class="Type">varchar</span>(<span class="Number">16</span>) <span class="Special">DEFAULT</span> <span class="String">'approved'</span>,
		<span class="lnr">42 </span>  `parent` int(<span class="Number">10</span>) unsigned <span class="Special">DEFAULT</span> <span class="String">'0'</span>,
		<span class="lnr">43 </span>  PRIMARY KEY (`coid`),
		<span class="lnr">44 </span>  KEY `cid` (`cid`),
		<span class="lnr">45 </span>  KEY `created` (`created`)
		<span class="lnr">46 </span>) ENGINE=MyISAM  <span class="Special">DEFAULT</span> CHARSET=utf8 AUTO_INCREMENT=<span class="Number">1320</span> ;

</pre>
