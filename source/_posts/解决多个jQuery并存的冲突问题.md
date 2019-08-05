---
title: 解决多个jQuery并存的冲突问题
date: 2018-09-21
tags:
- 笔记  
- jQuery
- 前端
categories: 学习笔记 
---

我在开发某个web项目的时候，想给页面加上日历，天气查询等小功能。最快的方式自然是使用别人已经写好的jQuery插件。在引用这些插件的时候，出现了jQuery冲突问题，即多个不同版本的jQuery文件的并存导致$的使用上出现紊乱最终导致功能无效。

<!-- more -->

解决多个jQuery并存的冲突问题
常用的方法是释放$的使用权，eg：

```java
<script type="text/javascript" src="js/jquery-1.12.4.js"></script>
 <script>
    //1.释放$的使用权
    var jq = $.noConflict();
    //2.用jq代替$
     jq(function(){
        alert("hello world")
	    });
   </script>

```