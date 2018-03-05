# 安全性

### XSS攻击

**跨站脚本攻击**（Cross Site Scripting）为了与CSS重叠样式表区分开来，所以简称为XSS攻击。 
简单来说XSS是一种在web应用中的计算机安全漏洞，它允许恶意Web用户将代码植入到提供给其它用户使用的页面中，，可以理解为一种JavaScript代码注入，如编写JavaScript代码到公共评论模块中。

**防御措施：**

* 过滤**转义**输入输出
* 避免使用 `eval` 执行字符串
* 后端 set cookie 时可定义 `HttpOnly` 属性

参考文章[《HttpOnly介绍以及防止XSS攻击时的作用》](http://desert3.iteye.com/blog/869080)

**注意**：敏感信息（例如 pkey ）要以cookie形式存储，并设置 `HttpOnly` 属性以确保cookie信息不能通过客户端脚本访问

### CSRF攻击

**跨站请求伪造**（Cross-site request forgery）,简称CSRF攻击。 

要完成一次CSRF攻击，受害者必须依次完成两个步骤：

* 登录受信任网站A，并在本地生成Cookie
* 在不登出A的情况下，访问危险网站B

比如在受信任网站的Cookie还没过期的情况下，点击了恶意网站，恶意网站利用类同JSONP方式，在某 `<img>` 元素中定义了 `src` 属性以GET的形式调用受信任网站中的资源或函数方法。

**防御措施：**

* 关键请求使用验证码
* 检测 `http referer` 是否是同域名

参考文章[《浅谈CSRF攻击方式》](http://www.cnblogs.com/hyddd/archive/2009/04/09/1432744.html)


