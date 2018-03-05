# 图片引入

测试内容图应该写上表明图片尺寸的占位图，可以用线上占位图生成服务，如：

```html
http://placeholder.qiniudn.com/300x200
```

![image](http://placeholder.qiniudn.com/300x200)

HTML 中图片引入不需添加 width、height 属性，alt 属性应该写上

```html
<!-- 推荐 -->
<img src="" alt="" >

<!-- 不推荐 -->
<img src="" width="" height="" >
```

CSS 中图片引入不需要引号

```css
.max {
  background-image: url(icon.png);
}
```

### CSS Sprites 使用建议

* 适合使用频率高更新频率低的小图标
* 尽量不留太多的空白
* 体积较大的图片不合并
* 确保要合并的小图坐标数值和合并后的 Sprites 图尺寸均为偶数

### Data URIs（base64编码）使用建议

* 适合更新频率高的小图片，如某些具备自定义功能的标题icon等
* 转换成 Base64 编码的图片应小于 2KB
* 移动端不使用 Base64 编码
* 要兼容 IE6/IE7 的不使用