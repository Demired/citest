---
title: php判断是否ajax请求
date: 2017-01-25 11:47
tags: mysql
---

有时我们需要判断是不是ajax请求来决定模块输出还是json格式输出.


## PHP判断ajax请求的原理:

在发送ajax请求的时候，我们可以通过XMLHttpRequest这个对象，创建自定义的header头信息， 在jquery框架中，对于通过它的$.ajax, $.get, or $.post方法请求网页内容时，它会向服务器传递一个HTTP_X_REQUESTED_WITH的参数，php中就是在header一层判断是否是ajax请求，对应的根据$_SERVER['HTTP_X_REQUESTED_WITH']判断。

```
function isAjax()··
 {
     return isset($_SERVER['HTTP_X_REQUESTED_WITH']) && strtolower($_SERVER['HTTP_X_REQUESTED_WITH']) == 'XMLHttpRequest';
 }
```

(完)
