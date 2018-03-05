# 图片命名

## 命名顺序

图片命名建议参考以下顺序进行命名：

**图片业务（可选） + 图片功能类别（必选）+ 图片模块名称（可选） + 图片精度（可选）**

* 图片业务：
  - 功能向
    - news_：新闻
    - heybox_：小黑盒
    - maxjia_：MAX+
    - ...
  - 游戏向
    - dota_：dota2
    - ow_：守望先锋
    - csgo_：CS:GO
    - pubg_：绝地求生
    - ...


* 图片功能类别：
	- icon：模块类固化的图标
	- logo：LOGO类
	- spr：单页面各种元素合并集合
	- btn：按钮
	- bg：可平铺或者大背景
	- ...
	

* 图片模块名称：
	- goodslist：商品列表 
	- goodsinfo：商品信息
	- userava	tar：用户头像
	- ...
	

* 图片精度：
	- 普清：@1x
	- Retina：@2x | @3x
	- ...


如下面例子：

	公共模块：
	wx_mod_btn_goodlist@2x.png
	wx_mod_btn_goodlist.png
	mod_btn_goodlist.png 

	非公共模块：
	wx_btn_goodlist@2x.png
	wx_btn_goodlist.png
	btn_goodlist.png

## 交叉业务协作

业务交叉协作的时候，为了避免图片命名冲突，建议图片名加上业务和模块前辍，如拍拍侧和手Q侧的业务交叉合作时，侧栏导航icon雪碧图命名：

	推荐：
	pp_icon_mod_sidenav.png

	不推荐：
	icon_mod_sidenav.png

处理高清图片的时候，命名应该加上图片相应的精度说明

	推荐：
	jdc_logo@1x.png
	jdc_logo@2x.png

	不推荐：
	jdc_logo.png
	jdc_logo_retina.png
