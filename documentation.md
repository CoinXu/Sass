## SassCx 文档说明 

### 还没有写完，所以这个文档也还没写完

_____________________________________________________________________

* ###__变量 variables__

> 全局变量
    
    $support-old-ie: false;   // 支持ie6/7，值取 false / true，默认为false 
    $support-html5: true;     // 支持 html5
    $support-css3: true;      // 支持 Css3

    $default-font-size: 14;
    $default-text-color: #666;
    $default-input-placeholder-color: #999;

    $default-base-font-family: 'Helvetical Neue', Arial, sans-serif;
    $default-heading-font-family: 'Helvetical Nenu', Arial, 'Hiragino Sans GB','Microsoft Yahei', 'WenQuanYi Micro Hei', sans-serif;
    $default-old-ie-heading-font-family: 'Microsoft Yahei', Arial, sans-serif;
    $default-code-font-family: 'Monaco','Consolas','monospace';
    
    // default visual settings
    $default-border-radius: 5px;
    $default-box-shadow: 0 1px 3px rgba(0, 0, 0, 0.25);\

    // 以上为默认取值，引用的时候可以重新定义，比如

    $default-border-radius:10px;

_____________________________________________________________________

* ###__reset__

> 两种情况：
>> 其一：单独的页面或者是一个小的专题

    // 调用小的 `reset`，直接调用，不用写在.className下面
    @include reset-global;

>> 其二：整站的 reset 

    @include global-normalize;


* ###__兼容 Compatibility__

> `inline-block` 


* ###__版式相关 Typography__

>  
   * `inline-block` 
   * `ellipsis`
   * `force-wrap`	    // 阻止长字符打破布局
   * `hide-text`	    // 隐藏文字
   * `img-replace($img-url, $pos-x: 0, $pos-y: 0, $repeat: no-repeat)` // 用图片替换文字。参数很明白，不用解释了；引用这个的时候，要给元素设置宽高
   * `hover-link`       // 默认无下划线，horver的时候有下划线
   * `unstyled-link`    // 将链接变为默认的文字样式
   * `drop-cap($line-height, $lines, $margin-right)`         // 首字下沉，第一个参数为所有文本的行高，第二个参数为下沉的行位，第三个参数为与右边文本的距离
   * `drop-cap-inline`  // 行内元素沉


* ###__小工具 Utils__

>  
   * `clearfix`        // fix clear
   * `set-size($width,$height)`        // `set-size(20px)`,`set-size(20px,30px)` 若只取一个值，则将该值同时设定为 `width` 和 `height` 的值
   * `no-bullet`      // `no-bullet` 去掉 `li` 的样式
   * `no-bullets`     // `no-bullet` 去掉整个 `list` 的样式，用于 `ol/ul`
   * `layout-fixed-header($height: auto, $header-z-index:999)` // header $height，当然不设置也不会报错。html结构为 page > Cx-header & Cx-mian，切记html结构。
   * `layout-fixed-footer($height: auto, $header-z-index:999)` // 同 `layout-fixed-header`
   * `layout-align-center($width)`  // 水平居中，需要一个宽度的参数
   * `layout-absolute-direction($width, $height, $direction-horizontal, $direction-vertical)`  // absolute定位，参数分别为 width, height, 水平方向取值(left/right)，垂直方向仅值(top/bottom);
   * `layout-horizontal-list($direction: left, $gap:10px)`  // 将列表排成一列，兼容ie6。参数分别为：浮动方向，每个之间的 gap。gap的值可以是任意合法的 `margin` 取值。

   