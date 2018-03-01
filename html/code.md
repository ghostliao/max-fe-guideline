# 代码规范

## DOCTYPE 声明

HTML文件必须加上 DOCTYPE 声明，并统一使用 HTML5 的文档声明：

```html
<!DOCTYPE html>
```

## 页面语言LANG

推荐使用属性值 cmn-Hans-CN（简体, 中国大陆），但是考虑浏览器和操作系统的兼容性，目前仍然使用 zh-CN 属性值

```html
<html lang="zh-CN">
```

## CHARSET

一般情况下统一使用 “UTF-8” 编码

```html
<meta charset="UTF-8">
```

## 元素及标签闭合

为了能让浏览器更好的解析代码以及能让代码具有更好的可读性，有如下约定：
* 所有具有开始标签和结束标签的元素都要写上起止标签，某些允许省略开始标签或和束标签的元素亦都要写上。
* 空元素标签都不加 “/” 字符

```html
<!-- 推荐 -->
<div>
  <h1>我是h1标题</h1>
  <p>我是一段文字，我有始有终，浏览器能正确解析</p>
</div>
	
<br>

<!-- 不推荐 -->
<div>
  <h1>我是h1标题</h1>
  <p>我是一段文字，我有始无终，浏览器亦能正确解析
</div>
<br/>
```

## 书写风格

### HTML代码大小写

HTML标签名、类名、标签属性和大部分属性值统一用小写

```html
<!-- 推荐 -->
<div class="demo"></div>

<!-- 不推荐 -->
<div class="DEMO"></div>

<DIV CLASS="DEMO"></DIV>
```
HTML文本、CDATA、JavaScript、meta标签某些属性等内容可大小写混合

```html
<!-- 优先使用 IE 最新版本和 Chrome Frame -->
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1"/>
<!-- HTML文本内容 -->
<h1>I AM WHAT I AM </h1>
<!-- JavaScript 内容 -->
<script type="text/javascript">
	var demoName = 'demoName';
	...
</script>
	
<!-- CDATA 内容 -->
<script type="text/javascript"><![CDATA[
...
]]></script>
```

### 类型属性

不需要为 CSS、JS 指定类型属性，HTML5 中默认已包含

```html
<!-- 推荐 -->
<link rel="stylesheet" href="demo.css" >
<script src="demo.js"></script>

<!-- 不推荐 -->
<link rel="stylesheet" type="text/css" href="demo.css" >
<script type="text/javascript" src="demo.js" ></script>
```

### 元素属性

* 元素属性值使用双引号语法
* 元素属性值可以写上的都写上

```html
<!-- 推荐 -->
<input type="text">
	
<input type="radio" name="name" checked="checked" >

<!-- 不推荐 -->
<input type=text>	
<input type='text'>
	
<input type="radio" name="name" checked >
```

### 特殊字符引用

在 HTML 中不能使用小于号 “<” 和大于号 “>”特殊字符，浏览器会将它们作为标签解析，若要正确显示，在 HTML 源代码中使用字符实体

```html
<!-- 推荐 -->
<a href="#">more&gt;&gt;</a>

<!-- 不推荐 -->
<a href="#">more>></a>
```

### 代码缩进

统一使用两个空格进行代码缩进，使得各编辑器表现一致（各编辑器有相关配置）

```html
<div class="max">
  <a href="#"></a>
</div>
```

### 纯数字输入框

使用 `type="tel"` 而不是 `type="number"`

```html
<input type="tel">
```

### 代码嵌套

元素嵌套规范，每个块状元素独立一行，内联元素可选

```html
<!-- 推荐 -->
<div>
  <h1></h1>
  <p></p>
</div>	
<p><span></span><span></span></p>

<!-- 不推荐 -->
<div>
  <h1></h1><p></p>
</div>	
<p> 
  <span></span>
  <span></span>
</p>
```

段落元素与标题元素只能嵌套内联元素

```html
<!-- 推荐 -->
<h1><span></span></h1>
<p><span></span><span></span></p>

<!-- 不推荐 -->
<h1><div></div></h1>
<p><div></div><div></div></p>
```


