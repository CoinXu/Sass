## SassCx 文档说明 

### 还没有写完，所以这个文档也还没写完
#### 该框架借鉴了 `EST(less)` 和 `compass(Sass)`，其作者表示感谢
### 
_____________________________________________________________________

### 此框架用Sass语法书写，关于Sass的安装及基础语法，请参考官网。学习成本很低，大约半小时。
[Sass官网](http://sass-lang.com/ "Click This Anchor")

[Sass中文资料](http://www.ruanyifeng.com/blog/2012/06/sass.html)

_____________________________________________________________________

### 此文档用__ markDown __ 书写，请在浏览器上安装markdown插件，以取得更好的阅读效果
[markDown语法及支持](http://wowubuntu.com/markdown/ "Click This Anchor")

_____________________________________________________________________


* ###__ 安装 __
	
	
		在项目文件中，引入Sass/all.scss即可

	
	
	
* ###__变量 variables__



		全局变量
		
		$support-old-ie: false;   					// 支持ie6/7，值取 false / true，默认为false 
		$support-html5: true;     					// 支持 html5
		$support-css3: true;      					// 支持 Css3

		$default-font-size: 14;	  					// 默认字体
		$default-text-color: #666; 					// 默认字体颜色
		$default-input-placeholder-color: #999;		// placeholder颜色

		$default-base-font-family: 'Helvetical Neue', Arial, sans-serif;				// 默认字体
		$default-heading-font-family: 'Helvetical Nenu', Arial, 'Hiragino Sans GB','Microsoft Yahei', 'WenQuanYi Micro Hei', sans-serif;
		$default-old-ie-heading-font-family: 'Microsoft Yahei', Arial, sans-serif;		
		$default-code-font-family: 'Monaco','Consolas','monospace';
		
		// default visual settings
		$default-border-radius: 5px;
		$default-box-shadow: 0 1px 3px rgba(0, 0, 0, 0.25);
	
	
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//
		//	以上为默认取值，引用的时候可以重新定义，比如
		//
		//	 $default-border-radius:10px;
		//
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
	
	
   

_____________________________________________________________________

* ###__reset__



		// 两种情况：

		// 其一：单独的页面或者是一个小的专题

		// 调用小的 `reset`,直接调用,不用写在.className下面
		@include reset-global();

		// 其二：整站的 reset 
		@include global-normalize();


* ###__兼容 Compatibility__



		__ inline-block __	
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	生成的代码就是display:inline-block;
		//	如果变量 `$support-old-ie` 为true,则会增加
		//	*display:inline;
		//	*zoom:1;
		//	这两条规则
		//  
		//	调用方法:
		//	.className{
		//		@include inline-block();
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


* ###__版式相关 Typography__

  

		__ inline-block __	
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	生成的代码就是display:inline-block;
		//	如果变量 `$support-old-ie` 为true,则会增加
		//	*display:inline;
		//	*zoom:1;
		//	这两条规则
		//  
		//	调用方法:
		//	.className{
		//		@include inline-block();
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		__ ellipsis __
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	legal value: ellipsis / clip / string(no support);
		//  
		//	封装的是text-overflow
		//	ellipsis       以省略号来表示被修剪的文本
		//	clip           修剪文本
		//	string         以指定的文本来代表被修剪的文本
		//	.className{
		//		@include ellipsis(clip);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		__ force-wrap __	
		   阻止长字符打破布局(比如：连续的字母、URL)
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	.className{
		//		@include force-wrap();
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

		__ hide-text __	
		   隐藏文字，比如用icon替换文字的时候
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	.className{
		//		@include hide-text();
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ img-replace __	
		   用图片替换文字。参数很明白，不用解释了；引用这个的时候，要给元素设置宽高
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	img-replace($img-url, $pos-x: 0, $pos-y: 0, $repeat: no-repeat)
		//
		//	.className{
		//		@include img-replace('http://example.com/img/aa.jpg','0','0',no-repeat);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ hover-link __	
		   默认无下划线，hover后加下划线
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	.className{
		//		@include hover-link();
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ unstyled-link __	
		   将链接变为默认的文字样式
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	.className{
		//		@include unstyled-link();
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ drop-cap __	
		   首字下沉：
		   第一个参数为所有文本的行高
		   第二个参数为下沉的行位
		   第三个参数为与右边文本的距离第一个参数为所有文本的行高
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	drop-cap($line-height, $lines, $margin-right)
		//
		//	.className{
		//		@include drop-cap(20px, 2, 10px)
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ drop-cap-inline __	
		   行内元素下沉
		   第一个参数为所有文本的行高
		   第二个参数为下沉的行位
		   第三个参数为与右边文本的距离第一个参数为所有文本的行高
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	drop-cap-inline($line-height, $lines, $margin-right)
		//
		//	.className{
		//		@include drop-cap-inline(20px, 2, 10px)
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


* ###__小工具 Utils__

  
  
		__ clearfix __	
		   这个就不用说了...
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	drop-cap-inline($line-height, $lines, $margin-right)
		//
		//	.className{
		//		@include clearfix();
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


		__ font-size-zero __	
		   设置 `font-size:0` 兼容safari
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	font-size-zero($class-name, $default-font-size-element)
		//	Note:
		//	$class-name:     需要设置 font-size:0 的 className
		//	$default-font-size-element: 需要设置正常字体的 element
		//	
		//	调用：直接调用，不要写在className里面
		//	font-size-zero($class-name, $default-font-size-element)
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


		__ set-size __	
		   设置元素的尺寸，前提是元素是 `block` 或者 `inline-block`
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	set-size($width, $height: auto)
		//	### Example:
		//	`set-size(20px)`
		//	`set-size(20px 30px)`
		//	
		//	Note:如果参数只写一个，那么宽高会取一样的值
		//
		//	.className{
		//		@include set-size(20px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-	


		__ no-bullet __  __ no-bullets __	
		   去掉 `list` 的样式
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	no-bullet()		// 去掉 `li` 的样式
		//	no-bullets()	// 去掉所有 `list` 的样式，用于 `ol/ul`
		//
		//	.className{
		//		@include no-bullet();
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


		__ layout-fixed-header __	
		   定高、相对视口固定的页头
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	layout-fixed-header($height: auto, $header-z-index: 999);
		//
		//	用于整个页面，且要给 header 和 main 分另添加 Cx-header 和 Cx-main
		//	html结构为 page > Cx-header & Cx-mian，切记html结构。
		//
		//	.className{
		//		@include layout-fixed-header(300px, 100);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


		__ layout-fixed-footer __	
		   定高、相对视口固定的页脚
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	layout-fixed-footer($height: auto, $header-z-index: 999);
		//	用于整个页面，且要给 header 和 main 分另添加 Cx-header 和 Cx-main
		//	html结构为 page > Cx-header & Cx-mian，切记html结构。
		//
		//	.className{
		//		@include layout-fixed-footer(300px, 100);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ layout-align-center __	
		   居中对齐
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	layout-align-center($width)
		//
		//	.className{
		//		@include layout-align-center(200);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ llayout-absolute-direction __	
		   元素定位在父元素的四角
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	layout-absolute-direction($width, $height, $direction-horizontal, $direction-vertical)
		//	
		//	$direction-horizontal: left | right
		//	$direction-vertical: top | bottom
		//
		//	.className{
		//		@include llayout-absolute-direction(100px,100px,left,top);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ llayout-horizontal-list __	
		   将列表排成一行
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	layout-horizontal-list($direction: left, $gap: 10px)
		//	参数分别为：浮动方向、每个之间的 gap。
		//	gap的值可以是任意合法的 `margin` 取值。	
		//	html的结构为 `layout-horizontal-list > ul/ol > li`
		//
		//	.className{
		//		@include layout-horizontal-list(right,2px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
	
	
* ###__文字效果 Utils__	



		__ embossed-text __	
		   文字浮凸效果
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	embossed-text($color)
		//
		//	.className{
		//		@include embossed-text(#f00);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ debossed-text __	
		   文字凹陷效果
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	debossed-text($color)
		//
		//	.className{
		//		@include debossed-text($f00);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ threeD-text __	
		   3d文字效果
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	threeD-text($color)
		//
		//	.className{
		//		@include threeD-text($f00);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ glow-text __	
		   文本发光效果
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	glow-text($color: #175fcc, $radius: 5px)
		//
		//	.className{
		//		@include glow-text($f00, 5px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ blurry-text __	
		   文本模糊效果
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	blurry-text($color, $radius: 0.15em)
		//
		//	.className{
		//		@include blurry-text(#ff0, 1.5em);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

	
## __ Css3 相关 __

* ### __ animation __

	
	
  
		// @keyframes	                定义一个动画,@keyframes定义的动画名称用来被animation-name所使用。	
		// animation	                复合属性。检索或设置对象所应用的动画特效。	
		// animation-name	            检索或设置对象所应用的动画名称
		//								必须与规则@keyframes配合使用，因为动画名称由@keyframes定义	
		//
		// animation-duration	        检索或设置对象动画的持续时间	
		// animation-timing-function	检索或设置对象动画的过渡类型	
		/*
			linear						动画从头到尾的速度是相同的。	
			ease						默认。动画以低速开始，然后加快，在结束前变慢。	
			ease-in						动画以低速开始。	
			ease-out					动画以低速结束。	
			ease-in-out					动画以低速开始和结束。	
			cubic-bezier(n,n,n,n)
		*/ 

		// animation-delay	            检索或设置对象动画的延迟时间	
		// animation-iteration-count	检索或设置对象动画的循环次数	
		// animation-direction	        检索或设置对象动画在循环中是否反向运动  normal || alternate	
		// animation-play-state	        检索或设置对象动画的状态    runing || paused
		

		$default-animation-name:                     CxAnimations           
		$default-animation-timing-function:          linear               
		$default-animation-duration:                 2000ms                
		$default-animation-delay:                    0                     
		$default-animation-iteration-count:          1                      
		$default-animation-direction:                normal                 
		$default-animation-play-state:               running   

		
		__ animation __	
		   定义一个完整的动画
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	animation(
		//		$name:              $default-animation-name, 
		//		$duration:          $default-animation-duration, 
		//		$timing-function:   $default-timing-function, 
		//		$delay:             $default-animation-delay, 
		//		$iteration-count:   $default-animation-iteration-count, 
		//		$direction:         $default-animation-direction, 
		//		$play-state:        $default-animation-play-state
		//	)
		//
		//	.className{
		//		@include animation(names,2000ms,ease-in-out,0,2,alternate,runing);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ animation-name __	
		   定义动画名称
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	animation-name($name: $default-animation-name)
		//
		//	.className{
		//		@include animation-name(testName);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ animation-duration __	
		   定义动画持续时间
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	animation-duration($duration: $default-animation-duration)
		//
		//	.className{
		//		@include animation-duration(3s);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ animation-duration __	
		   定义动画持续时间
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	animation-duration($duration: $default-animation-duration)
		//
		//	.className{
		//		@include animation-duration(3s);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ animation-tming-function __	
		   定义动画函数
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	animation-timing-function($timing-function: $default-animation-timing-function)
		//
		//	.className{
		//		@include animation-timing-function(ease-in-out);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ animation-delay __	
		   定义动画延迟时间
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	animation-delay($delay: $default-animation-delay)
		//
		//	.className{
		//		@include animation-delay(1s);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ animation-iteration-count __	
		   定义动画循环次数
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	animation-iteration-count($iteration-count: $default-animation-iteration-count)
		//
		//	.className{
		//		@include animation-iteration-count(1);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		
		__ animation-direction __	
		   设置动画在循环中是否反向
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	animation-direction($direction: $default-animation-direction)
		//
		//	.className{
		//		@include animation-direction(alternate);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ animation-play-state __	
		   定义动画状态
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	animation-play-state($direction: $default-animation-direction)
		//
		//	.className{
		//		@include animation-play-state(paused);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
	
	

* ### __ background __	



		__ background __	
		   定义动画状态
		   (Note：这个函数的意义不大，background最好是根据项目需求自己写)
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	background($color, 
		//		$imageUrl,
		//		$repeat, 
		//		$PosX, 
		//		$PosY, 
		//		$size, 
		//		$origin, 
		//		$clip, 
		//		$attachment)
		//
		//	.className{
		//		@include background(#11bcc3,'http://img.xx.xx/img/img.jpg',
		//		0,0,
		//		100px,60px,
		//		content-box,
		//		padding-box,
		//		scroll);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


* ### __ border-radius __		
	
	
		__ border-radius __	
		   定义四个边角圆弧
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	border-radius($radius: $default-border-radius, $vertical-value: false)	
		//
		//	.className{
		//		border-radius(3px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ border-corner-radius __	
		   定义不同位置的边角圆弧
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	border-corner-radius($vertical, $horizontal, $radius: $default-border-radius)
		//
		//	.className{
		//		// 左上角3px的圆弧如下
		//		border-corner-radius(top,left,3px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ border-top-left-radius __	
		   定义左上角的圆弧
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	border-top-left-radius($radius: $default-border-radius)
		//
		//	.className{
		//		// 左上角3px的圆弧如下
		//		border-top-left-radius(3px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ border-top-right-radius __	
		   定义右上角的圆弧
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	border-top-right-radius($radius: $default-border-radius)
		//
		//	.className{
		//		// 左上角3px的圆弧如下
		//		border-top-right-radius(3px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ border-bottom-right-radius __	
		   定义右下角的圆弧
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	border-bottom-right-radius($radius: $default-border-radius)
		//
		//	.className{
		//		// 左上角3px的圆弧如下
		//		border-bottom-right-radius(3px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ border-bottom-left-radius __	
		   定义左下角的圆弧
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	border-bottom-left-radius($radius: $default-border-radius)
		//
		//	.className{
		//		border-bottom-left-radius(3px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		当然还可以去扩展，譬如【左边两角】、【右边两角】、【对角】等。
		对应的文件为 border-radius.scss
	
	
* ### __ box-shadow __


		__ box-shadow __	
		   定义阴影
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	box-shadow(
		//		$color  : $default-box-shadow-color,              
		//		$hoff   : $default-box-shadow-horizontal-offset, 
		//		$voff   : $default-box-shadow-vertical-offset,    
		//		$blur   : $default-box-shadow-blur,              
		//		$spread : $default-box-shadow-spread,            
		//		$inset  : $default-box-shadow-inset              
		//	)
		//
		//		$color  : 阴影颜色         
		//		$hoff   : 水平位置 
		//		$voff   : 垂直位置    
		//		$blur   : 模糊距离             
		//		$spread : 阴影尺寸          
		//		$inset  : inset | outset   
		//	
		//	.className{
		//		@include box-shadow(#11bcc3,2px,2px,5px,0px,inset);
		//	}
		//
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


* ### __ box-sizing __


		__ box-sizing __	
		   定义浏览器盒模型
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	box-sizing($box-sizing)
		//	$box-sizing : content-box | border-box | inherite
		//	.className{
		//		@include box-sizing(content-box);
		//	}
		//
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

	
	
* ### __ column-rule __



		__ bcolumn-rule __	
		   将元素排成多列
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-rule($width: 300px, $style: solid, $color: silver)
		//
		//	$width: 每一列的宽度
		//	$style:	分隔线的样式
		//	$color: 分隔线的颜色
		//
		//	.className{
		//		@include column-rule(300px,dotted,purple);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ columns __	
		   规定设置 column-width 和 column-count 的简写属性
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-rule($width-and-count)
		//
		//	.className{
		//		每一列200px，分成3列
		//		@include columns(200px,3);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ column-count __	
		   规定分成的列数
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-count($count)
		//
		//	.className{
		//		分成3列
		//		@include column-count(3);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ column-gap __	
		   规定每列之间的间隙
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-gap($gap)
		//
		//	.className{
		//		分成3列
		//		@include column-gap(10px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ column-width __	
		   规定每列的宽度
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-width($width)
		//
		//	.className{
		//		@include column-width(300px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ column-span __	
		   规定横跨的列数
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-span($width)
		//	$width:  number | all
		//	.className{
		//		@include column-span(1);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ column-fill __	
		   规定如何填充列（主流浏览器暂时都不支持）
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-fill($fill)
		//	$fill: balance | auto
		//	.calssName{
		//		@include column-fill(balance)
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

		
		__ column-rule-color __	
		   规定列之间规则的颜色
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-rule-color($color)
		//	.calssName{
		//		@include column-rule-color(pink)
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ column-rule-style __	
		   规定列之间规则的样式
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-rule-style($style)
		//	.calssName{
		//		@include column-rule-style(solid)
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

		
		__ column-rule-width __	
		   规定列之间规则的宽度
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	column-rule-width($width)
		//	.calssName{
		//		@include column-rule-width(10px)
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

		
* ### __ filter __
		
		
		
		__ filter __	
		   规定列之间规则的宽度
		   目前支持非常不完整，不建议用，老实用图片吧。
		   没测试哪些浏览器支持，有兴趣的可以自测下。
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	filter($filter)
		//
		//	$filter:
		// grayscale       灰度
		// sepia           褐色（
		// saturate        饱和度
		// hue-rotate      色相旋转
		// invert          反色
		// opacity         透明度
		// brightness      亮度
		// contrast        对比度
		// blur            模糊(px)
		// drop-shadow     阴影(px)
		//
		// ### Example:grayscale(1);
		// 若没有指定值，将以100%来渲染
		//
		//	.calssName{
		//		@include filter(sepia(0.5));
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
	
	
	
* ### __ flexible-box __
	这就是传说中非常牛叉风骚的flex了！
	速度去找资料，这里这提供使用方法，不提供原理说明。
	虽然这被浏览器完全支持，但本人还是强烈建议骚年们去看看。
	  		
	
		//
		// box-align	          start | end | center | baseline | stretch
		// box-direction	      normal|reverse|inherit;
		// box-flex	              value: number	
		// box-flex-group	      显示的位置:index  `0 ~ num`
		// box-lines	          single|multiple  
		// box-ordinal-group	  
		// box-orient	          horizontal|vertical|inline-axis|block-axis|inherit;
		// box-pack	              start|end|center|justify;
		
		
		__ box-align __	
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	box-align($box-align, $box-pack);
		//
		//	.calssName{
		//		@include box-align(start,justify);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-	
		
			
		__ box-direction __	
		   指定在哪个方向，显示一个框的子元素
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	box-direction($direction)
		//	.calssName{
		//		@include box-direction(normal);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


		__ box-flex __	
		   指定一个框的子元素是否是灵活的或固定的大小 
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	box-flex($number)
		//	.calssName{
		//		@include box-flex(1.0);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ box-flex-group __	
		   可伸缩元素能够随着框的缩小和扩大而伸缩。
		   目前没有浏览器支持该属性
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	box-flex-group($number)
		//	.calssName{
		//		@include box-flex-group(1);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ box-lines __	
		   规定如果列超出了父框中的空间，是否要换行显示。
		   目前没有浏览器支持该属性
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	box-lines($lines)
		//	$line: single | multiple
		//	.calssName{
		//		@include box-lines(multiple);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ box-orient __	
		   属性规定框的子元素应该被水平或垂直排列。
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	box-orient($orient)
		//	$orient: horizontal|vertical|inline-axis|block-axis|inherit;
		//	.calssName{
		//		@include box-orient(vertical);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
	

* ### __ font-face __	


		__ font-face __	
		   自定义字体	
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	font-face(
		//		$name,				字体名
		//		$font-files,		字体文件路径
		//		$eot : false,		是否支持ie6-8
		//		$weight : false,	是否加粗
		//		$style  : false		font-style的值
		//	)
		// 调用此函数时，需要有 `.eot, .woff, .ttf, .svg` 四种字体在同一目录下，并且同名
		// $font-files 格式 : http:// ..../font-name(后面不要写类型'.tft')
		//
		//	@include font-face(name,'http:// ..../font-name',false,normal);
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
	
	
* ### __ opacity __	

	
		__ opacity __	
		   设置透明度
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	.className{
		//		@include opacity(0.5);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-	
	
	
* ### __ transform __	

元素的2D或3D转换，允许将元素旋转、绽放、移动、倾斜等
	 
	 

		// 默认 translation value

		$defalute-translation-x   : 1em                         !default;
		$defalute-translation-y   : $defalute-translation-x     !default;
		$defalute-translation-z   : $defalute-translation-x     !default;

		// 默认 scale 
		$default-scale-x          : 1.25                        !default; 
		$default-scale-y          : $default-scale-x            !default;
		$default-scale-z          : $default-scale-x            !default;

		// 默认 rotate angle
		$default-rotate-angle     : 45deg                       !default;
		$default-rotate-vector-x  : 1                           !default;
		$default-rotate-vector-y  : $default-rotate-vector-x    !default;
		$default-rotate-vector-z  : $default-rotate-vector-x    !default;

		// 默认 skew
		$default-skew-x           : 5deg                        !default;
		$default-skew-y           : 5deg                        !default;

		// 默认 origin
		$default-origin-x         : 50%                         !default;
		$default-origin-y         : $default-origin-x           !default;
		$default-origin-z         : $default-origin-x           !default;

		__ translate __	
		   平移
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	translate(
		//		$translate-x: $default-translation-x,
		//		$translate-y: $defaulte-translation-y,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include translate(10px,20px,false);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-	
		
		
		__ translate3d __	
		   3d平移
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	translate3d(
		//		$translate-x: $default-translation-x,
		//		$translate-y: $defaulte-translation-y,
		//		$translate-z: $defaulte-translation-z,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include translate(10px,20px,10px,false);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-	
		
		
		__ translateX __	
		   X轴上平移
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	translate3d(
		//		$translate-x: $default-translation-x,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include translateX(10px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-	
		
		
		__ translateY __	
		   Y轴上平移
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	translate3d(
		//		$translate-y: $default-translation-y,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include translateY(10px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-


		__ translateZ __	
		   Z轴上平移
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	translateZ(
		//		$translate-z: $default-translation-z,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include translateZ(10px);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		
		
		__ Scale __	
		   缩放
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	scale(
		//		$scale-x: $defaulte-scale-x,
		//		$scale-y: $defaulte-scale-y,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include scale(1,2);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
			
		__ scale3d __	
		   3d缩放
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	scale3d(
		//		$scale-x: $defaulte-scale-x,
		//		$scale-y: $defaulte-scale-y,
		//		$scale-z: $defaulte-scale-z,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include scale3d(1,2,1.2);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ scaleX __	
		   X轴缩放
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	scaleX(
		//		$scale-x: $defaulte-scale-x,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include scaleX(1.5);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ scaleY __	
		   Y轴缩放
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	scaleY(
		//		$scale-y: $defaulte-scale-y,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include scaleZ(1.5);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ scaleZ __	
		   Z轴缩放
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	scaleZ(
		//		$scale-z: $defaulte-scale-z,
		//		$perspective: false
		//	)
		
		//	.className{
		//		@include scaleZ(1.5);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ rotate __	
		   旋转
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	rotate(
		//		$angle: $default-rotate-angle,
		//		$perspective: false
		//	)
		//
		//	.className{
		//		@include rotate(30deg);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ rotate3d __	
		   3d旋转
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	rotate3d(
		//		$vector-x: $default-rotate-vector-x,
		//		$vector-y: $default-rotate-vector-y,
		//		$vector-z: $default-rotate-vector-z,
		//		$rotate  : $defalut-rotate-angle,
		//		$perspective:false
		//	)
		//
		//	.className{
		//		@include rotate3d(20deg,10deg,10deg);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ rotateX __	
		   X轴旋转
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	rotateX(
		//		$vector-x: $default-rotate-vector-x,
		//		$perspective:false
		//	)
		//
		//	.className{
		//		@include rotateX(20deg);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ rotateY __	
		   Y轴旋转
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	rotateY(
		//		$vector-y: $default-rotate-vector-y,
		//		$perspective:false
		//	)
		//
		//	.className{
		//		@include rotateY(20deg);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ rotateZ __	
		   Z轴旋转
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	rotateZ(
		//		$vector-Z: $default-rotate-vector-Z,
		//		$perspective:false
		//	)
		//
		//	.className{
		//		@include rotateZ(20deg);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		
		__ skew __	
		   倾斜
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	skew(
		//		$skew-x: $default-skew-x,
		//		$skew-y: $default-skew-y,
		//		$perspective: false
		//	)
		//
		//	.className{
		//		@include skew(5deg,10deg);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ skewX __	
		   X轴上倾斜
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	skewX(
		//		$skew-x: $default-skew-x,
		//		$perspective: false
		//	)
		//
		//	.className{
		//		@include skewX(10deg);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ skewY __	
		   Y轴上倾斜
		   
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	skewX(
		//		$skew-x: $default-skew-y,
		//		$perspective: false
		//	)
		//
		//	.className{
		//		@include skewY(10deg);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

		
		__ transform-origin __
		   设置变换的基点
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	transform-origin(
		//		$origin-x: $default-origin-x,
		//		$origin-y: $default-origin-y,
		//		$origin-z: false
		//	)
		//
		//	.className{
		//		@include transform-origin(50%,50%);
		//	}
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		
		
		__ create-transform __
		   一个函数中创建一个transform
		
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
		//	create-transform(
		//		$perspective:     false,
		//
		//		$translate-x:     false,
		//		$translate-y:     false,
		//		$translate-z:     false,
		//
		//		$skew-x:          false,
		//		$skew-y:          false,
		//
		//		$rotate-x:        false,
		//		$rotate-y:        false,
		//		$rotate-z:        false,
		//		$rotate3d:        false,
		//
		//		$scale-x:         false,
		//		$scale-y:         false,
		//		$scale-z:         false,
		//		$scale3d:         false,
		//
		//		$origin-x:        false,
		//		$origin-y:        false,
		//		$origin-z:        false
		//	)
		//
		//	.className{
		//		@include create-transform(false,
		//		100px,100px,100px,
		//		false,20deg,
		//		45deg,20deg,20deg,false,
		//		false,1.5,1,2,
		//		flase,center,top);
		//	}
		//	Note：不需要的项，值取false
		// +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
	
	
	

  