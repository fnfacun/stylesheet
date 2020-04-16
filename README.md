# 样式（Style）

# 导入外部样式表
- 使用 <Link> 标签导入外部样式表文件的代码如下：
```css
<link href="1.css" rel="stylesheet" type="text/css" />
```
href：定义样式表文件的 URL。
type：定义导入的文件类型，同 style 元素一样。
rel：用于定义文档关联，这里表示关联样式表。

**使用 @import 关键字**
在 <style> 标签内使用 @import 关键字导入外部样式表文件的方法如下：
```css
<style type="text/css">
    @import url("./1.css");
</style>
```

# css 属性值

## 绝对值
绝对值在网页上很少使用，一般用在特殊场合。常见的绝对值单位包括：
英寸（in）：使用最广泛的长度单位。
厘米（cm）：最常用的长度单位。
毫米（mm）：在研究领域使用广泛
磅（pt）：也称点，在印刷领域使用广泛。
pica（pc）：在印刷领域使用广泛。

## 相对值
- em 表示字体高度，它能够根据字体的 font-size 值来确定大小，例如：
```css
p {
    font-size: 12px;
    line-height: 2em; /* 行高为 24px */
}
```
em 会根据父元素的 font-size 属性值来确定，如果父元素的 font-size 属性单位也为 em，则依次向上元素寻找 font-size 属性值，如果都没有定义，则会根据浏览器默认字体进行换算，默认字体一般为 16px。

- rem 表示字体高度，他们转换为像素大小取决于页根元素的字体大小，即 html 元素的字体大小。根元素字体大小乘以你的 rem 值，例如：
```css
html {
    font-size: 16px;
}
p {
    width: 10rem; /* 160px */
}
```
- ex 表示字母 x 的高度
- px 根据屏幕像素点来确定大小。这样不同的显示分辨率就会使相同取值的 px 单位所显示出来的效果截然不同。
- %（百分比）也是一个相对绝对值。一般参考父对象中相同属性的值。例如，如果父元素宽度为 500px，子元素的宽度为百分之 50%，则子元素的实际宽度为 250px。


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

***

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

# 设计渐变背景（linaer-gradient）
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

# 定义光标样式（cursor）
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