---
title: php判断是否请求类型
date: 2017-02-23 11:47:23
tags:
     - ajax
     - php
categories: 技术
description: 在做web开发时我们可能需要判断请求类型（是api请求还是html请求）来决定输出内容
---

有些业务需要判断请求类型来决定输出模版还是api数据再或者直接ban掉,我这里只能提供一个思路，要想让自己的应用变的强壮，我们还需要更多更严谨的代码

## PHP判断请求类型:

### ajax

在发送ajax请求的时候，我们可以通过XMLHttpRequest这个对象，创建自定义的header头信息， 在jquery框架中，对于通过它的$.ajax, $.get, or $.post方法请求网页内容时，它会向服务器传递一个HTTP_X_REQUESTED_WITH的参数，php中就是在header一层判断是否是ajax请求，对应的根据$_SERVER['HTTP_X_REQUESTED_WITH']判断。

```
function isAjax()··
 {
     return isset($_SERVER['HTTP_X_REQUESTED_WITH']) && strtolower($_SERVER['HTTP_X_REQUESTED_WITH']) == 'xmlhttprequest';
 }
```

### system

在浏览器请求页面时会带上浏览器的HTTP_USER_AGENT，而这个参数通常是固定不变的，在服务器端我们可以通过$_SERVER['HTTP_USER_AGENT']获取这一参数，再通过字符串匹配来确定浏览器类型。

```
function isIos(){
  if(stripos($_SERVER['HTTP_USER_AGENT'], 'iPhone')||stripos($_SERVER['HTTP_USER_AGENT'], 'iPad')){
    return True;
  }
}
function isAndroid(){
  if(stripos($_SERVER['HTTP_USER_AGENT'], 'Android')){
    return True;
  }
}
```

(完)
