# 代码规范

## 编码规范

* 样式文件必须写上 @charset 规则，并且一定要在样式文件的第一行首个字符位置开始写，编码名用 “UTF-8”
* 字符 @charset “”; 都用小写字母，不能出现转义符，编码名允许大小混写
* 考虑到在使用“UTF-8”编码情况下 BOM 对代码的污染和编码显示的问题，在可控范围下，坚决不使用 BOM。

*推荐*

```css
@charset "UTF-8";
.max {}
```

*不推荐*

```css
/**
 * @desc File Info
 * @author Author Name
 * @date 2018-02-27
 */
 
/* @charset规则不在文件首行首个字符开始 */
@charset "UTF-8";
.max {}
```

```css
@CHARSET "UTF-8";
/* @charset规则没有用小写 */
.max {}
```

```css
/* 无@charset规则 */
.max {}
```

## 代码风格

### 代码格式化

样式书写一般有两种：一种是紧凑格式 (Compact)

```css
.max { display: block; width: 50px; }
```

一种是展开格式（Expanded）

```css
.max {
  display: block;
  width: 50px;
}
```

推荐使用展开格式书写样式

### 代码大小写

样式选择器，属性名，属性值关键字全部使用小写字母书写，属性字符串允许使用大小写。

```css
/* 推荐 */
.max {
  display: block;
}
	
/* 不推荐 */
.MAX {
  DISPLAY: BLOCK;
}
```

### 选择器

* 尽量少用通用选择器 `*`
* 不使用 ID 选择器
* 不使用无具体语义定义的标签选择器

```css
/* 推荐 */
.max {}
.max li {}
.max li p {}

/* 不推荐 */
* {}
#max {}
.max div {}
```

### 代码缩进

统一使用两个空格进行代码缩进，使得各编辑器表现一致（各编辑器有相关配置）

```css
/* 推荐 */
.max {
  width: 100%;
  height: 100%;
}

/* 不推荐 */
.max {
    width: 100%;
    height: 100%;
}
```

### 分号

每个属性声明末尾都要加分号 `;`

```css
/* 推荐 */
.max {
  width: 100%;
  height: 100%;
}

/* 不推荐 */
.max {
  width: 100%;
  height: 100%
}
```

### 代码易读性

左括号与类名之间一个空格，冒号与属性值之间一个空格

```css
/* 推荐 */
.max {
  width: 100%;
}

/* 不推荐 */
.max{
  width: 100%;
}
```

逗号分隔的取值，逗号之后一个空格

```css
/* 推荐 */
.max {
  box-shadow: 1px 1px 1px #333, 2px 2px 2px #ccc;
}

/* 不推荐 */
.max {
  box-shadow: 1px 1px 1px #333,2px 2px 2px #ccc;
}
```

为单个css选择器或新声明开启新行

```css
/* 推荐 */
.max, 
.max-logo, 
.max-hd {
  color: #ff0;
}
.nav {
  color: #fff;
}

/* 不推荐 */
.max,.max-logo,.max-hd {
  color: #ff0;
}.nav {
  color: #fff;
}
```

颜色值 `rgb()` `rgba()` `hsl()` `hsla()` `rect()` 中逗号后面一个空格，且取值不要带有不必要的 0

```css
/* 推荐 */
.max {
  color: rgba(255, 255, 255, .5);
}

/* 不推荐 */
.max {
  color: rgba(255,255,255,0.5);
}
```

属性值十六进制数值能用简写的尽量用简写

```css
/* 推荐 */
.max {
  color: #fff;
}

/* 不推荐 */
.max {
  color: #ffffff;
}
```

不要为 `0` 指明单位

```css
/* 推荐 */
.max {
  margin: 0 10px;
}

/* 不推荐 */
.max {
  margin: 0px 10px;
}
```

### 属性值引号

css属性值需要用到引号时，统一使用单引号

```css
/* 推荐 */
.max {
  font-family: 'Hiragino Sans GB';
}

/* 不推荐 */
.max {
  font-family: "Hiragino Sans GB";
}
```

### 属性书写顺序

建议遵循以下顺序：

1. 布局定位属性：display / position / float / clear / visibility / overflow
2. 自身属性：width / height / margin / padding / border / background
3. 文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word
4. 其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background: linear-gradient …

```css
.max {
  display: block;
  position: relative;
  float: left;
  width: 100px;
  height: 100px;
  margin: 0 10px;
  padding: 20px 0;
  background: rgba(0, 0, 0, .5);
  font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;
  color: #333;
  box-shadow: 1px 1px 1px #333, 2px 2px 2px #ccc;
}
```

### CSS3浏览器私有前缀写法

CSS3 浏览器私有前缀在前，标准前缀在后

```css
.max {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -ms-border-radius: 10px;
  -o-border-radius: 10px;
  border-radius: 10px;
}
```