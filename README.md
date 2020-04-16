## 导入外部样式表

- 使用 <Link> 标签导入外部样式表文件的代码如下：
```css
<link href="1.css" rel="stylesheet" type="text/css" />
```
href：定义样式表文件的 URL。
type：定义导入的文件类型，同 style 元素一样。
rel：用于定义文档关联，这里表示关联样式表。



## @import 导入样式

在 <style> 标签内使用 @import 关键字导入外部样式表文件的方法如下：

```css
<style type="text/css">
    @import url("./1.css");
</style>
```



## 绝对值
绝对值在网页上很少使用，一般用在特殊场合。常见的绝对值单位包括：
英寸（in）：使用最广泛的长度单位。
厘米（cm）：最常用的长度单位。
毫米（mm）：在研究领域使用广泛
磅（pt）：也称点，在印刷领域使用广泛。
pica（pc）：在印刷领域使用广泛。



## 相对值

### em 

表示字体高度，它能够根据字体的 font-size 值来确定大小，例如：

```css
p {
    font-size: 12px;
    line-height: 2em; /* 行高为 24px */
}
```
em 会根据父元素的 font-size 属性值来确定，如果父元素的 font-size 属性单位也为 em，则依次向上元素寻找 font-size 属性值，如果都没有定义，则会根据浏览器默认字体进行换算，默认字体一般为 16px。



### rem

rem 表示字体高度，他们转换为像素大小取决于页根元素的字体大小，即 html 元素的字体大小。根元素字体大小乘以你的 rem 值，例如：

```css
html {
    font-size: 16px;
}
p {
    width: 10rem; /* 160px */
}
```


### ex 

表示字母 x 的高度



### px

px 根据屏幕像素点来确定大小。这样不同的显示分辨率就会使相同取值的 px 单位所显示出来的效果截然不同。



### %

%（百分比）也是一个相对绝对值。一般参考父对象中相同属性的值。例如，如果父元素宽度为 500px，子元素的宽度为百分之 50%，则子元素的实际宽度为 250px。



# 字体

## 字体简写方式
```css
font: [font-style] [font-variant] [font-weight] [font-size]/[line-height] [font-family];
```



## 定义字体大小（font-size）

- xx-small（最小）
- x-small（较小）
- small（小）
- medium（正常）
- large（大）
- x-large（较大）
- xx-large（最大）
- larger（增大）
- smaller（减少）
- length（尺寸）



## 定义字体颜色（color）

取值包括颜色名、十六进制值、RGB/RGBA 等颜色函数
- color: color



## 定义字体粗细（font-weight）

- normal（默认值，相当于取值 400）
- bold（粗体，相当于取值 700）
- bolder（较粗）
- lighter（较细）
- 100 - 900（越大越粗，相反越细）



## 定义艺术字体（font-style）

- normal（默认值）
- italic（斜体）
- oblique（倾斜）



## 定义修饰线（text-decoration）

- none（没有）
- normal（默认值，表示无装饰线）
- underline（下划线效果）
- blink（闪烁效果）
- overline（上划线效果）
- line-through（贯穿线效果）
### text-decoration-line
- 设置装饰线的位置（ none、underline、overline、line-through、blink）
### text-decoration-color
- 设置装饰线的颜色
### text-decoration-style
- 设置装饰线的形状（ solid、double、dotted、dashed、wavy(波浪线) ）
### text-decoration-skip
- 设置文本装饰线必须略过内容中的那些部分
### text-decoration-position
- 设置对象中的下划线的位置



## 定义字体的变体（font-variant）

仅支持拉丁字体，中文字体没有大小写效果区分
- normal（默认值）
- small-caps（小型的大写字母字体）



## 定义大小写字体（text-transfrom）

- none（默认值，表示无转换发生）
- capitalize（表示每个单词的第一个字母转换为大写）
- uppercase（表示把所有字母都转换为大写）
- lowercase（表示把所有字母都转换为小写）



## 定义文本对齐（text-align）

定义文本的水平对齐方式，该属性仅对行内对象有效，如文本、图像、超链接，如果想让块元素对齐显示，如设计网页居中显示，需要特殊方法。
- left、start（默认值，左对齐）
- right、end（右对齐）
- center（居中对齐）
- justify（两端对齐）



## 定义垂直对齐（vertical-align）

world 对准 hello ---- 的基线
```html
<p>hello<span>world</span></p>
```
- auto（将根据 layout-flow 属性的值对齐对象内容）
- baseline（表示默认值，表示将支持 valign 特性的对象内容与基线对齐）
- sub（表示垂直对齐文本的下标）
- super（表示垂直对齐文本的上标）
- top（表示将支持 valign 特性的对象的内容与对象顶部对齐）
- text-top（表示将支持 valign 特性的对象的文本与对象顶部对齐）
- middle（表示将支持 valign 特性的对象的内容与对象中部对齐）
- bottom（表示将支持 valign 特性的对象的内容与对象底部对齐）
- text-bottom（表示将支持 valign 特性的对象的文本与对象底部对齐）
- length（表示由浮点数和单位标识组成的长度值或者百分比）



## 定义文本间距（letter-spacing、word-spacing）

这两个属性的取值都是长度值，由浮点数字和单位标识符组成，默认值为 normal，表示默认间隔
### letter-spacing
- 定义字距
### word-spaing
- 定义词距，以空格为基准进行调节，如果多个单词被连在一起，则视为一个单词，如果汉字被空格分隔，则分隔的多个汉字被视为不同的单词



## 定义行高（line-height）

- normal（默认值，一般为 1.2em）
- length（表示百分比数字，或者浮点数和单位标识符组成的长度值，允许为负值）



## 定义首行缩进（text-index）

- length（表示百分比数字，或者浮点数和单位标识符组成的长度值，允许为负值。建议在设置缩进单位时，以 em 为位置单位，它表示一个字距，这样比较精确确定首行缩进效果）



## 定义图像大小

当为图像仅定义宽度和高度，则浏览器能够自动调整纵横比，使宽和高能够协调缩放，避免图像变形。
- width（宽度）
- height（高度）



## 定义图像边框（border）

```css
div { border: 1px solid red }
```
### border-width
- 定义边框粗细
- ```css
  border-width: 10px 20px 30px 40px;
  /* 上10px 右20px 下30px 左40px */
  ```
### border-style
- 定义边框样式（ solid（实线）、double（双线框）、groove（立体凹槽）、rideg（立体凸槽）、inset（立体凹边）、outset(立体凸边) ）
### border-color
- 定义图像颜色
### opacity
- 不透明度



## 定义圆角特效（border-radius）

- none（初始值）
- length（浮点数字和单位标识符组成的长度值，不可为负值）
### border-top-left-radius
- 定义左上角的圆角
### border-top-right-radius
- 定义右上角的圆角
### border-bottom-left-radius
- 定义左下角的圆角
### border-bottom-right-radius
- 定义右下角的圆角



## 定义阴影特效（box-shadow）

```css
box-shadow: inset 10px 10px 4px orange;
/* 内阴影 水平偏移 垂直偏移 阴影大小 阴影颜色 */
```
- none（初始值，表示没有阴影）
- inset（内阴影）
### 阴影叠加
```css
box-shadow: -10px 0 12px red,
            10px 0 12px blue,
            0 -10px 10px pink,
            0 10px 12px green
```
### 阴影兼容
```css
-moz-box-show: inset 10px 10px orange;			/* 兼容 Gecko 引擎 */
-webkit-box-show: inset 10px 10px 4px orange;	/* 兼容 Webkit 引擎 */
```



## 控制文本溢出（text-overflow）

强制文本换行需要定义两条样式：
1. 强制文本在一行内显示 white-space: nowrap
2. 溢出内容为隐藏 overflow: hidden
- clip（当内联内容移出块容器时，将溢出部分裁切掉，为默认值）
- ellipsis（当内联内容溢出块容器时，将溢出部分替换为 ...）



## 控制文本换行（word-break）

- normal（默认值，依照亚洲语言和非亚洲语言的文本规则，允许在字内换行）
- keep-all（对于中文、韩文、日文，不允许字断开）
- break-all（与 normal 相同）



# 背景图像

## 设置背景（background）
设置所有背景属性如下：
```css
background: [color] [image] [repeat] [attachment] [position] / [size] [origin] [clip];
```



## 设置背景图像（background-image）

- none（默认值，表示无背景图）
- url（表示使用绝对或相对地址指定背景图像）



## 设置显示模式（background-repeat）

- repeat-x（背景图像在横向上平铺）
- repeat-y（背景图像在纵向上平铺）
- repeat（背景图像在横向和纵向上平铺）
- no-repeat（背景图像不平铺）
- space（背景图像以相同的间距平铺且填充满整个容器或某个方向）
- round（背景图像自动缩放，直到适应且填充满整个容器）



## 设置显示模式（background-position）

取值包括两个值，分别是用来定位背景图像的 x 轴，y 轴坐标，取值单位没有限制。具体用法如下：
- length length 、% % 、legnth % （像素 百分比）
- top left 、left top （0% 0%）
- right top 、top right（100% 0）
- bottom left 、left bottom （0 100%）
- center 、center center（50% 50%）
- top 、top center 、center top（50% 0）
- left 、left center 、center left（0 50%）
- right 、right center 、center right（100% 50%）
- bottom 、bottom center 、center bottom （50% 100%）



## 设置固定背景（background-attachment）

- fixed（背景图像相对于浏览器窗口固定）
- local（背景图像相对于元素固定，也就是说，当元素内容滚动时背景图像不会跟着滚动，因为背景图像总是要跟着元素本身）
- scroll（背景图像相对于元素内容固定，也就是说，当元素内容滚动时背景图像也会跟着滚动）



## 设置定位原点（background-origin）

该属性是定位 background-position 属性的定位原点
- border-box（从边框区域开始显示背景）
- padding-box（从补白区域开始显示背景，为默认值）
- content-box（仅在内容区域显示背景）



## 设置裁剪区域（background-cilp）

定义背景图像的裁剪区域
- border-box（从边框区域向外裁剪背景）
- padding-box（从内容区域向外裁剪背景）
- content-box（从内容区域向外裁剪背景）
- text（从前景内容，如文字，区域向外裁剪背景）



## 设置背景图像大小（background-size）

控制背景图像的显示大小
```css
background-size: 600px auto;
background-size: 400px 400px;
background-size: cover;
background-size: contain;
```
- length（浮点数和单位标识符组成的长度值，不可为负值）
- percentage（取值为 0 ~ 100% 的值，不可为负值）
- cover（保持背景图像本身的宽高比例，将图片缩放到正好完全覆盖所定义背景的区域）
- contain（保持图像本身的宽高比例，将图片缩放到宽度或高度正好适应所定义背景区域）



## 设计渐变背景（linaer-gradient）

创建一个线性渐变至少需要两个颜色值，也可以选择设置一个起点或一个方向。简明语法格式如下
```css
linear-gradient( angle, color-stop1, color-stop2 );
linear-gradient( angle, color-stop1, color-stop2 );
linear-gradient( angle, color-stop1, color-stop2 );
```
angle：用来指定渐变的方向，可以使用角度或者关键字来设置。
- tp left（设置渐变从右到左）
- to right（设置渐变从左到右）
- to top（设置渐变从下到上）
- to bottom（设置渐变从上到下，默认值）



## 定义光标样式（cursor）

默认情况下，鼠标指针经过超链接时显示为手形状，使用 css 可以改变这种默认效果。
| 取值                                                         | 说明                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| auto                                                         | 基于上下文决定应该显示什么光标                               |
| crosshair                                                    | 十字线光标（+）                                              |
| default                                                      | 基于平台的默认光标样式，通常渲染为一个箭头                   |
| pointer                                                      | 指针光标，表示一个超链接                                     |
| move                                                         | 十字箭头光标，用于标示对象可被移动                           |
| e-resize、ne-resize、nw-resize、n-resize、se-resize、sw-resize、s-resize、w-resize | 表示正在移动某个边，如 se-resize 光标用来表示框的移动开宇于东南角 |
| text                                                         | 表示可以选择文本。通常渲染为 I 形光标                        |
| wait                                                         | 表示程序在忙，需要用户等待，通常渲染为手表或者沙漏           |
| help                                                         | 光标下的对象包含有帮助内容，通常渲染为一个问号或一个气球     |
| <url>URL                                                     | 自定义光标类型的图标路径                                     |



## 定义项目符号类型（list-style-type）

定义列表项目符号的类型，也可以取消项目符号。
|     属性值      |        说明        |     属性值     |        说明        |
| :-------------: | :----------------: | :------------: | :----------------: |
|      disc       |       实心圆       |  upper-roman   |    大写罗马数字    |
|     circle      |       空心圆       |  lower-alpha   |    小写英文字母    |
|     square      |      实心方块      |  upper-latin   |    大写拉丁字母    |
|     decimal     |     阿拉伯数字     |  upper-alpha   |    大写英文字母    |
|   lower-raman   |    小写罗马数字    |      none      |   不使用项目符号   |
| cjk-ideographic |   浅白的表意数字   |    armenian    | 传统的亚美尼亚数字 |
|   lower-greek   | 基本的希腊小写字母 |    georgian    |   传统的乔治数字   |
|    hiragana     |   日文平假名字符   |     hebrew     |  传统的希伯来数字  |
|    katakana     |   日文片假名字符   | hiragana-iroha |   日文平假名序号   |
|   lower-latin   |    小写拉丁字母    | katakana-iroha |   日文片假名序号   |
### list-style-position
定义项目符号的显示位置
- outside（把项目符号显示在列表项的文本行以外，默认值）
- inside（把项目符号显示在列表项的文本行以内）
### list-style-image
自定义项目符号
- url



# 多列布局

## 设置列宽（column-width）
定义单列显示的宽度
- length（用长度值来定义列宽，不允许为负值）
- auto（根据 column-count 自定分配宽度，为默认值）



## 设置列数（column-count）

定义显示的列数，如果定义网页的列数为 3，则不管浏览器窗口怎么调整，页面内容总是遵循三列布局。
- integer（用整数来定义列数，不允许为负值）
- auto（根据 column-width 自定义分配宽度，为默认值）



## 设置间距（column-gap）

定义两栏之间的距离
- length（用长度值来定义列与列之间的空隙，不允许为负值）
- normal（与 font-size 大小相同。假设对象的 font-size 为 16px，则 normal 值为16px）



## 设置列边框（column-rule）

定义每列之间边框的宽度、样式和颜色。

### column-rule-width
设置对象的列与列之间的边框厚度

### column-rule-style
设置对象的列与列之间的边框样式（none、hidden、dotted、dashed、solid、double、groove、ridge、inset、outset）

### column-rule-color
设置对象的列与列之间的边框颜色



## 设置跨列显示（column-span）

定义跨列显示
- none（不跨列）
- all（横跨所有列）



## 设置列高度（column-fill）

定义栏目的高度是否统一
- auto（列高度自适应内容）
- balance（所有列的高度与其中最高的一列统一）



# 选择器

## 元素选择器
- 标签选择器
标签选择器也称为类型选择器，它直接引用 HTML 标签名称，用来匹配同名的所有标签。
```css
p {
    font-size: 12px;
    color: red;
}
```

- 类选择器
类选择器以（.）为前缀，后面是一个类名。应用方法：在标签定义 class 属性，然后设置属性值为类选择器的名称。
```css
.red {
    color: red;
}
.underline {
    text-decoration: underline;
}
```

- ID选择器
ID 选择器以井号（#）为前缀，后面是一个 ID 名。应用方法：在标签定义 id 属性，然后设置属性值为 ID 选择器的名称。
```css
#box {
    width: 200px;
    height: 200px;
    background-color: red;
}
```



## 关系选择器

### 包含选择器
包含选择器通过空格连续两个简单的选择器，前面选择器表示包含的对象，后面选择器表示被包含的对象。

```html
<div id="wrap">
    <div id="header">
        <p>头部区域段落文本</p>
    </div>
    <div id="main">
        <p>主体区域段落文本</p>
    </div>
</div>
```
使用选择器来快速定义样式
```css
#header p {
    font-size: 14px;
}
#main p {
    font-size: 12px;
}
```



### 子选择器
子选择器使用尖角号（>）连续两个简单的选择器，前面选择器表示包含的对象，后面选择器表示被包含的对象。

```html
<h2>
    <span>虞美人 · 春花秋月何时了</span>
</h2>
<div>
    <span>文君能有几多愁？恰似一江春水向东流</span>
</div>
```
使用所有 span 元素的字体大小为 18 像素，再用子选择器定义 h2 元素包含的 span 子元素的字体大小为 28 像素。
```css
span {
    font-size: 18px;
}
h2 > span {
    font-size: 28px;
}
```



### 相邻选择器

相邻选择器使用加号（+）链接两个简单的选择器，前面的选择器指定相邻的前面一个元素，后面选择器指定相邻的后面一个元素。

```html
<style type="text/css">
    h2,h2+p {
        text-align: center;
    }
</style>
<h2>虞美人 · 花月何时了</h2>
<p>李煜</p>
<p>春花秋月何时了</p>
<p>往事知多少</p>
```



### 兄弟选择器

兄弟选择器使用波浪符号（~）链接两个简单的选择器，前面的选择器指定同级的前置元素，后面选择器指定其后同级所有匹配的元素。

```html
<style type="text/css">
    h2~p {
        font-size: 14px;
        color: red;
    }
</style>
<h2>虞美人 · 花月何时了</h2>
<p>李煜</p>
<p>春花秋月何时了</p>
<p>往事知多少</p>
```



### 分组选择器
分组选择器使用逗号（，）链接两个简单的选择器，前面的选择器匹配的元素与后面选择器匹配的元素混合在一起作为分组选择器的结果集。

```css
h1, h2, h3, h4, h5, h6 {
    margin: 0;
    margin-bottom: 10px;
}
```



## 属性选择器

```html
<div class="pic_box">
    <img src="images/bg1.jpg" />
    <div class="nav">
        <a href="#1" class="links item first" title="w3cplus" target="_blank" id="first">1</a>
        <a href="#2" class="links active item" title="test website" target="_blank" lang="zh">2</a>
        <a href="#3" class="links item" title="this is a link" lang="zh-cn">3</a>
        <a href="#4" class="links item" target="_blank" lang="zh-tw">4</a>
        <a href="#5" class="links item" title="zh-cn">5</a>
        <a href="#6" class="links item" title="website link" lang="zh">6</a>
        <a href="#7" class="links item" title="open the website" lang="cn">7</a>
        <a href="#8" class="links item" title="colse the website" lang="en-zh">8</a>
        <a href="#9" class="links item" title="http://www.baidu.com">9</a>
        <a href="#10" class="links item last" id="last">10</a>
    </div>
</div>
```



### E[attr]
选择具有 attr 属性的 E 元素，例如：

```css
.nav a[id] {
    background-color: blue;
    color: yellow;
    font-weight: bold;
}
.nav a[href][title]{
    color: green;
}
```
先择 div.nav 下所有带有 id 属性的元素。



### E[attr="value"]

选择具有 attr 属性，且属性值等于 value 属性的 E 元素

```css
.nav a[id="first"] {
    background: red;
}
.nav a[href="#1"][title]{
    background: yellow;
}
```



### E[attr~="value"]

选择具有 attr 属性，且属性值为用空格分隔的字词列表，其中一个等于 value 的 E 元素。包含由一个值，且该值为 val 的情况。例如：

```css
nav a[title~="website"] {
    background-color: red;
}
```
在 div.nav 下的 a 元素的 title 的属性中，只要其属性值中含有 "website" 就会被选择。



### E[attr^="value"]
选择具有 attr 属性，且属性值为以 value 开头的字符串的 E 元素。例如：

```css
.nav a[title^="http://"] {
    background-color: red;
}
.nav a[title^="moilto:"] {
    background-color: green;
}
```
上面代码表示的是选择了以 title 属性，并且以 "http://" 和 "mailto:" 开头的属性值的所有 a 元素。



### E[attr$="value"] 

选择具有 attr 属性，且属性值为以 value 结尾的字符串的 E 元素。例如：

```css
.nav a[href$="png"] {
    background-color: red;
}
```



### E[attr*="value"]

选择具有 attr 属性，且属性值包含 value 的字符串的 E 元素，例如：

```css
.nav a[title*="site"] {
    color: white;
}
```



### E[attr|="value"]

选择具有 attr 属性，其值是以 value 开头，并用 | 分割的字符串的 E 元素；如果值仅为 value 也将会被选择。例如：

```css
.nav a[lang|="zh"] {
    color: yellow;
}
```
上面的代码会选中 div.nav 中 lang 属性等于 zh 或以 zh- 开头的所有 a 元素



# 伪选择器

伪选择器包括伪类选择器和伪对象选择器。伪选择器能够根据元素或对象的特征、状态、行为进行匹配。
伪选择器以冒号（:）作为前缀标识符。冒号前可以添加限定选择符，限定伪类应用的范围，冒号后为伪类和伪对象名，冒号前后没有空格。



## 伪类选择器列表

| 选择器                | 说明                                                         |
| --------------------- | ------------------------------------------------------------ |
| E:link                | 设置超链接 a 在未被访问前的样式                              |
| E:visited             | 设置超链接 a 在其链接地址已被访问过时的样式                  |
| E:hover               | 设置样式在其鼠标悬停时的样式                                 |
| E:focus               | 设置对象在成为输入焦点时的样式                               |
| E:lang(fr)            | 匹配使用特殊语言的 E 元素                                    |
| E:not(s)              | 匹配不含有 s 选择符的元素 E，除了本身                        |
| E:root                | 匹配 E 元素在文档的根元素。在 HTML 中，根元素永远是 HTML。   |
| E:first-child         | 匹配父元素的第一个子元素 E                                   |
| E:last-child          | 匹配父元素的最后一个子元素 E                                 |
| E:only-child          | 匹配父元素仅有的一个子元素 E                                 |
| E:nth-child(n)        | 匹配父元素的第 n 个子元素 E，假设该子元素不是 E，则选择器无效 |
| E:nth-last-child(n)   | 匹配父元素的倒数第 n 个子元素 E，假设该子元素不是 E，则选择器无效 |
| E:first-of-type       | 匹配同类型中的第一个同级兄弟元素 E                           |
| E:last-of-type        | 匹配同类型中的最后一个同级兄弟元素 E                         |
| E:only-of-type        | 匹配同类型中唯一的一个同级兄弟元素 E                         |
| E:nth-of-type(n)      | 匹配同类型中的第 n 个同级兄弟元素 E                          |
| E:nth-last-of-type(n) | 匹配同类型中的倒数第 n 个同级兄弟元素 E                      |
| E:empty               | 匹配没有任何子元素（包括 text 节点）的元素 E，<p></p>        |
| E:checked             | 匹配用户界面处于选中状态的元素 E，用于 input 的 type 为 radio 与 checkbox 时 |
| E:enabled             | 匹配用户界面上处于可用状态的元素 E                           |
| E:disabled            | 匹配用户界面尚处于禁止状态的元素 E                           |
| E:target              | 匹配相关 URL 指向的 E 元素                                   |



## 伪对象选择器列表

| E:first-letter/E::first-letter | 设置对象内的第一个字符的样式。注意，仅作用于块对象           |
| ------------------------------ | ------------------------------------------------------------ |
| E:first-line/E::first-line     | 设置对象内的第一行的样式。注意，仅作用于块对象               |
| E:before/E::before             | 设置在对象前发生的内容。与 content 属性一起使用，且必须定义 content 属性。 |
| E:after/E::after               | 设置在对象后发生的内容。与 content 属性一起使用，且必须定义 content 属性。 |
| E::placeholder                 | 设置对象文字占位符的样式                                     |
| E::selection                   | 设置对象被选择时的样式                                       |



## 选择器优先级

当多个样式作用于同一个对象，则根据选择器的优先级，确定对象最终应用的样式
- 标签选择器：权重值为 1
- 伪元素或伪对象选择器：权重值为 1
- 类选择器：权重值为 10
- 属性选择器：权重值为 10
- ID 选择器：权重值 100
- 其他选择器：权重值为 0，如通配选择器



# 伸缩盒模型

## 认识 Flebox
Flebox（伸缩盒模型）是一个新的盒子模型，它主要优化了 UI 布局，可以简单地使一个元素居中（包括水平和垂直居中）可以扩大或收缩元素来填充容器的可利用空间，可以改变布局顺序等。
在伸缩容器中，每个子元素都是一个伸缩项目，伸缩项目可以是任意数量的，伸缩容器外和伸缩项目内的一切元素都不受影响。
伸缩项目沿着伸缩容器内的一个伸缩行定位，通常每个伸缩容器有一个伸缩行，在默认情况下，伸缩行和文本方向一致；从左到右，从上到下。
常规布局是基于块和文本流方向，而 Flex 布局是基于 flex-flow 流。

![](https://segmentfault.com/img/remote/1460000008823768?w=659&h=281)

伸缩项目主要是沿着主轴（main axis）,从主轴起点（main-start）到主轴重点（main-end），或者沿着侧轴（cross-axis），从侧轴起点（cross-start）到侧轴重点（cross-end）排列。

主轴（main axis）：伸缩容器的主轴，伸缩项目主要是沿着这条轴进行排列布局。注意，它不一定是水平的，主要取决于 `justify-content` 属性设置。

主轴起点（main-start）和主轴终点：伸缩项目放置在伸缩容器内从主轴起点（main- start）向主轴重点（main-end）方向。

主轴尺寸（main size）：伸缩项目在主轴方向的宽度或高度就是主轴的宽度，伸缩项目垂直于主轴方向的高度或高度属性是主轴的高度。

侧轴（cross axis）：垂直于主轴称为侧轴。它的方向主要取决于主轴方向。

侧轴尺寸（cross size）：伸缩项目在侧轴方向的宽度或高度就是项目的侧轴长度，由哪一个对着侧轴方向来决定。

一个伸缩项目就是一个伸缩容器的子元素，伸缩容器中的文本也被视为一个伸缩项目。伸缩项目中的内容与普通文本流一样。例如，当一个伸缩项目被设置为浮动，用户依然可以在这个伸缩项目中放置一个浮动元素。


## 启动收缩盒（display）

设置元素的 display 属性为 flex 或 inline-flex 可以定义一个伸缩容器。设置为 flex 的容器被渲染为一个块级元素，而设置为 inline-flex 的容器则渲染为一个行内元素。

- flex
- inline-flex

定义伸缩容器，，属性决定容器时行内显示，还是块级显示，它的所有子元素将变成 flex 文档流，被称为伸缩项目。此时，CSS 的 column 属性在伸缩容器上没有效果，同时 float、clear、vertical-align 属性在伸缩项目也没有效果。



## flex-flow（flex-direction + flex-wrap）

flex-flow 属性是 flex-direction 属性和 flex-wrap 属性的简写形式，默认值为 row nowrap。

```css
flex-flow: <flex-direction> || <flex-wrap>;
```



## 设置主轴方向（flex-direction）

定义主轴方向，它适用于伸缩容器。

![](https://upload-images.jianshu.io/upload_images/13944531-c2f97bb8a47d139c.png?imageMogr2/auto-orient/strip|imageView2/2/w/796/format/webp)

- row（ 主轴与行内轴方向作为默认的书写模式，即横向从左到右排列(左对齐) ）
- row-reverse（对齐方式与 row 相反）
- column（主轴与行块轴方向作为默认的书写模式，即纵向从上到下排列(顶对齐)）
- column-reverse（对齐方式与 column 相反）







## 设置行数（flex-wrap）

定义伸缩容器时单行还是多行显示伸缩项目，侧轴的方向决定了新行堆放的方向。

![](https://upload-images.jianshu.io/upload_images/13944531-262f5854ece5b1fd.png?imageMogr2/auto-orient/strip|imageView2/2/w/798/format/webp)

- nowrap（容器为单行，该情况下 flex 子项可能会溢出容器）

![](https://upload-images.jianshu.io/upload_images/13944531-ce8c6f815b5bfc0a.png?imageMogr2/auto-orient/strip|imageView2/2/w/700/format/webp)

- wrap（容器多行，该情况下 flex 子项溢出的部分会被放置在新行，子项内部会发生断行）

![](https://upload-images.jianshu.io/upload_images/13944531-0701b857c3588b37.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/700/format/webp)

- wrap-reverse（反转 wrap 排列）

![](https://upload-images.jianshu.io/upload_images/13944531-0ae21f2bd8af65f8.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/700/format/webp)



## 设置对齐方式（justify-content）

定义伸缩项目沿着主轴线的对齐方式，该属性适用于收缩容器。

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071010.png)

- flex-start（默认值，伸缩项目向一行的起始位置靠齐）

- flex-end（伸缩项目向一行的结束位置靠齐）
- center（伸缩项目向一行的中间位置靠齐）
- space-between（伸缩项目会平均的分布在行里。第一个伸缩项目一行中的最开始位置，最后一个收缩项目在一行中最终点的位置）
- space-around（伸缩项目会平均的分布在行里，两端保留一半的空间）



## 侧轴对齐（align-items）

定义伸缩项目在侧轴上的对齐方式，该属性适用于伸缩容器，注意：需要高度。

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071011.png)

- flex-start（伸缩项目在侧轴起点边的外边距紧靠住该行在侧轴起始的边）
- flex-end（伸缩项目在侧轴终点边的外边距紧靠住该行在侧轴终点的边）
- center（伸缩项目的外边距在该行的侧轴上居中放置）
- baseline（伸缩项目根据他们的基线对齐）
- stretch（默认值，伸缩项目拉伸填充整个伸缩容器）



## 伸缩行对齐（align-content）

定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。。

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071012.png)

- flex-start（各行向伸缩容器的起点位置堆叠）
- flex-end（各行向伸缩容器的结束位置堆叠）
- center（各行向伸缩容器的中间位置堆叠）
- space-between（各行在伸缩容器中平均分布）
- space-around（各行在伸缩容器中平均分布，在两边各有一半的空间）
- stretch（默认值，各行将会伸展以占用剩余空间）



## 设置伸缩项目

### flex 属性

flex 属性是 flex-grow,  flex-shrink 和 flex-basis 的简写，默认值为 0 1 auto 。后两个属性可选。

```css
flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
```



### 项目排序（order）

控制伸缩项目在伸缩容器里的显示顺序

```css
.flex-item { order: <integer> }
```
![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071013.png)



###  扩展项目（flex-grow）

定义伸缩项目的扩展能力，决定伸缩容器剩余空间按比例应扩展多少空间。

```css
flex-grow: <number>
```

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071014.png)

如果所有项目的 flex-grow 属性都为 1，则它们将等分剩余空间（如果有的话）。如果一个项目的 flex-grow 属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。



##  收缩项目（flex-shrink）

属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。

```css
flex-shrink: <number>
```

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071015.jpg)

<number> 数值定义收缩比率。不允许为负值，默认值为 1



## 伸缩比例（flex-basis）

设置伸缩基准值，剩余的空间按比例进行伸缩。

- length（用长度值来定义宽度，不允许为负值）
- percentage（用百分比来定义宽度。不允许为负值）
- auto（无特定宽度值，取决于其他属性值）
- content（基于内容自动计算宽度）



## 对齐方式（align-self）

属性允许单个项目有与其他项目不一样的对齐方式，可覆盖`align-items`属性。默认值为`auto`，表示继承父元素的`align-items`属性，如果没有父元素，则等同于`stretch`。

- flex-start（伸缩项目在侧轴起点边的外边距紧靠住该行在侧轴起始的边）
- flex-end（伸缩项目在侧轴终点边的外边距紧靠住该行在侧轴终点的边）
- center（伸缩项目的外边距在该行的侧轴上居中放置）
- baseline（伸缩项目根据他们的基线对齐）
- stretch（默认值，伸缩项目拉伸填充整个伸缩容器）
- auto
- flex-start
- flex-end
- center
- baseline
- stretch




