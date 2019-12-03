## CSS
### CSS的引入方式
引入方式有行内引入、内嵌式引入和链接式引入，常用链接式引入。
> 引用的优先度：行内引入 > 内嵌式引入 > 链接式引入

#### 行内引入
```html
<h1 style="color: blue;">
	This heading will be blue now.
</h1>
```
#### 内嵌式引入
```html
<!DOCTYPE html>
<html>
<head> <title>CSS</title>
<style type=“text/css”>
	h1 {
		color:red;
	}
</style>
</head>
<body>
<h1>This heading will be red now.</h1> </body>
```
#### 链接式引入
```html
<html>
<head>
<title>CSS</title>
<link href=“style.css” type=“text/css” rel=“stylesheet” />
</head>
<body>
<h1>This heading will be green now.</h1>
</body>
</html>
```
### CSS注释
格式：`/* */`  

```css
/* The following is patterned after cnn.com’s design. */
p {font-weight: bold; font-style: italic;
/* font-size: 200%; */
}
```
### CSS属性
#### 颜色
|CSS属性|描述|值|
|:--:|:--:|:--:|
|color|(文本)前景色|颜色(颜色名称、RGB或HEX)|
|background-color|元素的背景色|颜色(颜色名称、RGB或HEX)|

##### 颜色的表示方法
+ 预定义的颜色名称，如 orange
+ RGB颜色代码，如 rgb(255,165,0)
+ 十六进制颜色代码，如 #ffa500
+ 半透明RGBA代码，如rgba(255,165,0,0.5)(CSS3)
+ HSL代码，如HSL(128,128,64)(CSS3)

##### 标准颜色名
标准颜色名可以被所有浏览器支持，包括以下十六种颜色：

+ aqua(浅绿)
+ black(黑)
+ blue(蓝)
+ fuchsia(紫红)
+ gray(灰)
+ green(绿)
+ lime(酸橙)
+ maroon(褐红色)
+ navy(深蓝)
+ olive(橄榄色)
+ purple(紫色)
+ red(红)
+ silver(银灰)
+ teal(鸭翅绿)
+ white(白)
+ yellow(黄)

#### Font属性
|   属性  |   描述  |   值   |
|   :--: |   :--: |   :--: |
|   font    |   设置所有字体属性    |   style, weight, size, family |
|   font-family     |   所用字体    |   字体名称，如“宋体”，“黑体” |
|   font-size   |   字体大小    |   单元值，百分比，命名值     |
|   font-style  |   是否倾斜    |   normal, italic, oblique |
|   font-variant    |   设定小型大写字母    |   normal, small-caps, inherit |
|   font-weight     |   是否加粗    |   normal, bold, bolder, lighter,inherit, 100-900  |

>`font-size`的单位有`px` `pt` `em`，模糊字体尺寸包括`xx-small` `x-small` `small` `medium` `large` `x-large` `xx-large` `smaller` `larger`，还可以使用百分比尺寸，如`20%`

#### text属性
| 属性 | 描述 | 值 |
| :--: | :--: | :--: |
|text-align|行内容对齐|left, center, right, justify|
|text-decoration|添加下划线|underline, overline, line-through, blink, none|
|text-indent|首行缩进|px, pt, %, em|
|text-overflow|如何处理太长文本|clip, ellipsis, ellipsis-word|
|text-shadow|设置文本阴影|例：px, px, px, #ff0000|
|text-transform|修改文本大小写|capitalize, uppercase, lowercase|
|line-height|设置行高|px, pt, %, em|
|letter-spacing| 设置字符间距| px, pt, %, em|

#### background属性
|   属性  |   描述  |   值   |
|   :--: |   :--: |   :--: |
|   background-color    |   背景颜色    |   颜色(名称、RGB、HEX)  |
|   background-image    |   背景图片    |   url("图片URL")    |
|   background-position |   背景图片起始位置    |   水平位置 垂直位置 或x% y%    |
|   background-repeat   |   是否及如何重复背景图片     |   repeat, repeat-x, repeat-y, no-repeat   |
|   background-attachment   |   背景图片是否固定或者随着页面的其余部分滚动   |   fixed, scroll   |
|   background  |   简写属性，在一个声明中设置所有背景属性 |   #ff0000url(/i/eg_bg_03.gif) no-repeat fixed center  |

>`positon`特殊位置：  
>水平方向：`left` `center` `right`  
>垂直方向：`top` `center` `bottom`

#### list属性
```css
 ol { list-style-type: lower-roman; }
```
可能的取值：

+ none : No marker
+ disc (default), circle, square
+ Decimal: 1, 2, 3, etc.
+ decimal-leading-zero: 01, 02, 03, etc.
+ lower-roman: i, ii, iii, iv, v, etc.
+ upper-roman: I, II, III, IV, V, etc.
+ lower-alpha: a, b, c, d, e, etc.
+ upper-alpha: A, B, C, D, E, etc.
+ lower-greek: alpha, beta, gamma, etc.
+ others: hebrew, armenian, georgian, cjk-ideographic, hiragana...

#### 样式继承与冲突
多种样式应用到一个元素，这些样式将被继承，当样式发生冲突时，更紧的匹配将覆盖一般意义的继承
#### ID和ID选择器
一页上允许给任意元素一个唯一的`ID`，`css`文件中`ID`前需要加`#`。
>一个链接可能包含`ID`，前面需要加`#`，浏览器载入相关页面时将滚动到包含该`ID`的元素处

例如，在`html`中：
```html
<p>Spatula City!  Spatula City!</p>
<p id="mission">Our mission is to provide the most
spectacular spatulas and splurge on our specials until
our customers <q>esplode</q> with splendor!</p>
```
则在对应的`css`文件中：
```css
#mission {
    font-style: italic;
}
```

#### 类和类选择器
类可以为一组元素设置相同的样式，在`css`文件中需要在类前面加`.`，也可针对某一类元素中的类进行样式的修改，例如下面示例中的`p.shout`，仅针对`p`中的`shout`类进行样式修改。
>同一元素被多个类标记后作用样式，也将发生继承，同时拥有多种样式。

在`html`中：
```html
<p class="shout">Spatula City! Spatula City!</p>
<p class="special">See our spectacular spatula specials!</p>
<p class="special">Today only: satisfaction guaranteed.</p>
```
则在对应的`css`文件中：
```css
.special { /* any element with class="special" */
    font-weight: bold;
}
p.shout { /* only p elements with class="shout" */
    color: red;
    font-family: cursive;
}
```
#### 伪类选择器
|属性|描述|
|:--:|:--:|
|:active|向被激活的元素添加样式|
|:hover|当鼠标悬浮在元素上方时，向元素添加样式|
|:link|向未被访问的链接添加样式|
|:visited|向已被访问的链接添加样式|
|:focus|向拥有键盘输入焦点的元素添加样式|

```css
a:link {color: #FF0000}
a:visited {color: #00FF00}
a:hover {color: #FF00FF}
a:active {color: #0000FF}
```
### 页面划分
`div`可以对页面进行划分，将某些内容划分到一起后可以定义一个`class`然后针对这一个区域进行样式的修改。  
`span`针对较小的内容进行标记，然后定义一个`class`后对其样式进行修改

在`html`中：
```html
<!-- div example -->
<div class="shout">
<h2>Spatula City! Spatula City!</h2>
<p class="special">See our spectacular spatula specials!</p>
<p>We'll beat any advertised price!</p>
</div>

<!-- span example -->
<h2>Spatula City! Spatula City!</h2>
<p>See our <span class="special">spectacular</span> spatula specials!</p>
<p>We'll beat <span class="shout">any advertised price</span>!</p>
```
则在对应的`css`文件中：
```css
.special {
    background-color: yellow;
    font-weight: bold;
}
.shout {
    color: red;
    font-family: cursive;
}
```

### 上下文选择器
#### 后代选择器
基本语法`css`：
```css
outerSelector innerSelector {
    property: value;
    property: value;
    ...
    property: value;
}
```
例如：  
在`html`中：
```html
<p>Shop at <strong>Hardwick's Hardware</strong>...</p>
<ul>
  <li>The <strong>best</strong> prices in town!</li>
<li>Act while supplies last!</li>
</ul>
```
则在对应的`css`文件中：
```css
li strong { text-decoration: underline; }
```
得到结果为`li`中的`strong`标签内的所有内容被添加上下划线。

#### 子元素选择器
把后代选择器中的在`outerSelector`和`innerSelector`中的` `替换为`>`，代表仅该标签下的下一级标签中符合条件的内容，并不包括下下级标签。
#### 选择器综合
选择器可以多个配合使用，如在下例中，选择的元素为`ID = #ad`下`li`下`important`中`strong`标签内的元素。

在`html`中：
```html
<div id="ad">
<p>Shop at <strong>Hardwick's Hardware</strong>...</p> <ul>
    <li class="important">The <strong>best</strong>
prices!</li>
    <li>Act <strong>while supplies last!</strong></li>
  </ul>
</div>
```
则在对应的`css`文件中：
```css
#ad li.important strong { text-decoration: underline; }
```
#### 选择器冲突
如果出现冲突，最高得分者优先，记分规则如下：

|CSS选择器|示例|得分|
|:--:|:--:|:--:|
|元素选择器|p|1|
|类选择器|.banner|10|
|ID选择器|#logo|100|

### 页面布局
页面元素包括块元素`p` `h1` 等和行内元素`em` `a`等，还有整个页面。

### 盒模型
盒模型的主要思想是每个元素的布局由四部分组成：

+ 元素的内容显示区(content area)
+ 围绕着元素的边界(border)
+ 内容和边界的距离(padding)
+ 边界和其它内容外边界的距离(margin)

<img src="https://ws2.sinaimg.cn/large/006tKfTcly1g09kiukr5cj30fd0e774k.jpg" width="300">

#### border
|属性|含义|
|:--|:--:|
|border|4条边的所有属性|
|border-color  <br> border-width  <br> border-style        |                  4条边的颜色/厚度/风格    |
|border-bottom <br> border-left <br> border-right <br> border-top              |             底/左/右/顶4边的所有属性  |
|border-bottom-color<br>  border-bottom-style<br>  border-bottom-width <br> border-left-color <br> border-left-style <br> border-left-width<br> border-right-color<br>  border-right-style<br>  border-right-width <br> border-top-color <br> border-top-style<br>  border-top-width     |                      指定边的指定属性 |   
|border-collapse       |                  设置表格的边框是否折叠 |

#### box-shadow
```css
p {
border: 1px dotted black;
box-shadow: 10px 10px 5px gray;
}
h1 {
box-shadow: 20px 20px 10px gray inset;
}                                                  
```
#### padding
|属性      |            含义  |   
|:--|:--:|   
|padding         |        4边的padding     |     
|padding-bottom <br> padding-left<br>  padding-right <br> padding-top|                   1边的padding  |        

>`padding`属性可以设定可以是一个参数、两个参数，也可以是四个参数  
>一个参数时，表示四个方向相同
>两个参数时，第一个参数代表`top` `bottom`，第二个参数代表`right` `left`
>四个参数时，分别依次代表`top` `right` `bottom` `left`

```css
h1 { padding: 1em; background-color:yellow; border:3px solid black; }
h2 { padding: 0em; background-color:#BBFFBB; }
h3 { padding-left: 200px; padding-top: 30px; background-color:green; }
```

#### margin
|属性   |               含义    |  
|:--|:--:|   
|margin         |         4边的margin |          
|margin-bottom <br> margin-left <br> margin-right<br> margin-top|                 1边的margin   |        

>`margin`参数与`padding`相同

#### 默认样式
|   HTML标签  |   默认样式    |
|   :--: |   :--: |
|   body    |   margin: 8px;    |
|   p, blockquote, ul, ol, dl, fieldset, form, b    |   margin: 1.12em 0;   |
|   blockquote  |   margin-left: 40px; margin-right: 40px;  |
|   h1, h2, h3, h4, h5, h6, strong  |   font-weight: bold;  |
|   h1  |   font-size: 2em; margin: 0.67em 0;   |
|   h2  |   font-size: 1.5em; margin: 0.75em 0; |
|   h3  |   font-size: 1.17em; margin: 0.83em 0;    |
|   h4  |   font-size: 1em; margin: 1.12em 0;   |
|   h5  |   font-size: 0.83em; margin: 1.50em 0;    |
|   h6  |   font-size: 0.75em; margin: 1.67em 0;    |
|   cite, em, var, address, i   |   font-style: italic; |
|   pre, code, tt   |   font-family: monospace; |
|   ol, ul, dd  |   margin-left: 40px;  |
|   u   |   text-decoration: underline; |
|   table   |   border-spacing: 2px;    |
|   th  |   font-weight: bold; text-align: center;  |

### float元素
|属性| 含义 |值|
|   :--: |   :--: |   :--: |
|width |设置元素内容显示区的宽度 |一种尺寸(px, pt, %, em)|
|float |浮动，即从正常内容流中提升元素 |left, right, none(default)|
|clear|规定元素的哪一侧不允许其他浮动元素|left, right, both,none(default)|
|overflow |属性规定当内容溢出元素框时发生的事情|visible(default), hidden, scroll, auto|

>`width`属性仅对块元素和`img`元素有效

### 多列布局
#### 多列属性
|   CSS属性   |   描述  |   值   |
|   :--: |   :--: |   :--: |
|   column-count    |   规定元素应该被分隔的列数    |   1个整数    |
|   column-gap      |   规定列之间的间隔    |   尺寸(px,  pt,  em,  %)    |
|   column-rule     |   设置列之间的竖线宽度、样式和颜色规则  |   2px  solid  green   |
|   column-span     |   规定元素应横跨多少列  |   1或者all  |
|   column-width    |   规定列的宽度  |   尺寸(px,  pt,  em,  %)    |

#### width和height
|属性|含义|
|   :-- |   :--: |
|width,height|设置元素内容显示区的宽度和高度|
|max-width<br>  max-height<br> min-width<br> min-height|设置元素的最大、最小高度和宽度|

>以上属性仅对块元素和`img`元素有效

#### 垂直对齐
属性：`vertical-align`  
描述：设置元素的垂直对齐方式  
值：

+ baseline(默认),元素放置在父元素的基线上
+ top,元素的顶端与行中最高元素的顶端对齐
+ middle,元素放置在父元素的中部
+ bottom,元素的顶端与行中最低的元素的顶端对齐
+ sub,垂直对齐文本的下标
+ super,垂直对齐文本的上标
+ text-top,元素的顶端与父元素字体的顶端对齐
+ text-bottom,元素的底端与父元素字体的底端对齐
+ a size or %

### 定位
#### 位置属性
|属性     |         含义 | 值   |    
|   :--: |   :--: |   :-- |   
|position       |         对页面元素进行定位"  | static:默认值，没有定位  <br>   relative:相对于其正常位置的偏移量 <br> absolute:绝对定位的元素，相对于static定位以外的第一个父元素进行定位 <br> fixed:绝对定位的元素，相对于浏览器窗口进行定位   |             
|top,bottom, left,right      |        元素边界的偏移量  |  尺寸(px,  pt,  em,  %)|

>使用相对元素中的绝对位置需要设置父元素为`relative`需要相对父元素定位的子元素设置为`absolute`

#### z-index

|属性  |    含义       |           值     |
|   :--: |   :--: |   :-- |        
|z-index  |   设置元素的3维堆叠顺序      |           auto:堆叠顺序与父元素相等 <br>  an  integer:设置元素的堆叠顺序   |       

>默认的`z-index`是`0`，所以设置为正数具有将放置在较顶层，设置为负数将放置在较底层

### 元素可见性
|属性  |    含义       |           值     |
|   :--: |   :--: |   :-- |              
|display    |     设置元素应该生成的框的类型  |       block:元素将显示为块元素，元素前后带有换行符  <br> inline:默认值，元素会被显示为内联元素，元素前后没有换行符  <br>  none:元素不会被显示  |                 
|visibility   |       设置元素是否可见     |       visible:默认值，元素是可见的  <br> hidden:元素是不可见的|               
|opacity   |      设置元素的透明度      |      从  0.0  （完全透明）到  1.0（完全不透明）|                 

>**display和visibility的主要区别：**  
>display:none; 元素不会占用页面上的空间  
>visibility:hidden; 虽然它的内容用户看不到，但元素仍然占用页面空间
