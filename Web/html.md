# HTML
## 基本结构
```HTML
<!DOCTYPE HTML>
<html>
<head>
  <meta charset="utf-8">
  <title>Title of the page</title>
</head>
<body>
</body>
</html>
```
### 文档标记`<html>`
包含文档的所有内容
### 头部标记`<head>`
包含文档的标题信息，如标题、关键字、说明、样式等
### 主体标记`<body>`
包含文档的内容。
#### 常用属性
+ `BACKGROUND=URI` 文档的背景图像，URI指图像文件的路径
+ `BGCOLOR=Color` 文档的背景色
+ `TEXT=Color` 文本颜色
+ `LINK=Color` 链接颜色
+ `VLINK=Color` 已访问的链接颜色
+ `ALINK=Color` 被选中的链接颜色
+ `ONLOAD=Script`文档已被加载
+ `ONUNLOAD=Script` 文档已退出

## 特殊符号
+ `&nbsp;`  空格
+ `&amp;`   &
+ `&lt;`   <
+ `&gt;`    >
+ `&quot;`  " 双引号
+ `&qpos;`  ' 单引号
+ `&copy;` &copy; 版权符号
+ `&rsquo;` &rsquo; 撇号
+ `&mdash;` &mdash; 长破折号
+ `&#124;` &#124; 竖线

## 常用工具
### HTML语法校验
+ [http://validator.w3.org](http://validator.w3.org)
+ [http://html5.validator.nu](http://html5.validator.nu)
+ [http://www.onlinewebcheck.com](http://www.onlinewebcheck.com)

## 常用标记
### 标题标记`<h1>`到`<h6>`
```HTML
<h1>Class 1 Title</h1>
<h2>Class 2 Title</h2>
```
### 段落标记`<p>`
```HTML
<p>text</p>
```
### 块引用标记`<blockquote>`
```HTML
<blockquote>quote text</blockquote>
```
### 换行标记`<br>`
```HTML
text<br>
text<br>
```
### 水平标尺标记`<hr>`
形成分隔符，表示新开一个主题
```html
text
<hr>
text
```
### 短语元素
+ `<abbr>` 标识文本是缩写
+ `<b>` 文本没有额外的重要性，但样式采用加粗字体
+ `<cite>` 标识文本是引文或参考，通常倾斜显示
+ `<code>` 标识文本是程序代码，通常使用等宽字体
+ `<dfn>` 标识文本是词汇或术语定义，通常倾斜显示
+ `<em>` 使文本强调或突出于周边的普通文本，通常倾斜显示
+ `<i>` 文本没有额外的重要性，但样式采用倾斜字体
+ `<kbd>` 标识要用户输入的文本，通常用等宽字体显示
+ `<mark>` 文本高亮显示以便参考
+ `<samp>` 标识是程序的实例输出，通常使用等宽字体显示
+ `<small>` 用小号字体显示的免责声明
+ `<strong>` 使文本强调或突出与周边的普通文本，通常加粗显示
+ `<sub>` 在基线以下用小文本显示的下标
+ `<sup>` 在基线以上用小文本显示的上标
+ `<var>` 标识并显示变量或程序输出，通常倾斜显示

### 链接标记`<a>`
```HTML
<a href="a.html">Content shown in Page</a>
<a href="b.html"><img src="images/logo.gif"></a>
```
#### 链接目标属性
控制链接是在新窗口打开还是在当前窗口打开默认当前窗口打开，`target="_blank"`表示在新窗口打开
```html
<a href="b.html" target="_blank"><img src="images/logo.gif"></a>
```
#### 邮件链接`mailto`
```HTML
<a href="mailto:adress@outlook.com">mail</a>
```
### 列表标记`<ul>`和`<ol>`
#### 无序列表`<ul>`
```html
<ul>
  <li>subject</li>
  <li>subject
    <ul>
      <li>subsubject</li>
      <li>subsubject</li>
    </ul>
  </li>
</ul>
```
#### 有序列表`<ol>`
```html
<ol>
  <li>subject</li>
  <li>subject
    <ul>
      <li>subsubject</li>
      <li>subsubject</li>
    </ul>
  </li>
</ol>
```
##### 常用属性
+ `type` 改变列表的序号类型
 + `type="1"` 数字
 + `type="A"` 大写字母
 + `type="a"` 小写字母
 + `type="I"` 大写罗马数字
 + `type="i"` 小写罗马数字
+ `start` 指定序号的起始值
+ `reversed="reversed"` 指定降序排序

#### 描述列表`<dl>`
```html
<dl>
<dt>Term</dt>
<dd>define of the Term</dd>
</dl>
```
### 图像标记`<img>`
```HTML
<img src="path">
```
#### 常用属性
+ `alt=text` 定义图形的相关描述
+ `src=URL` 要显示图像的URL
+ `height=pixels / %` 定义图像的高度
+ `width=pixels / %` 定义图像的宽度
+ `ismap=URL` 把图像定义为服务端的图像映射
+ `usemap=URL` 把图像定义为客户端图像映射的一幅图像
+ `vspace=pixels` 定义图像顶部和底部的空白

### 表格标记`<table>`
#### 行标记`<tr>`
```html
<tr>...</tr>
```
#### 列标记`<td>`
```HTML
<td>...</td>
```
```html
<table>
  <tr>
    <br>a</br>
    <br>b</br>
  </tr>
  <tr>
    <br>c</br>
    <br>d</br>
  </tr>
</table>
```
### 表单标记`<form>`
```html
<form action="url" method="get|post" enctype="mime">
</form>
```
> action=url 用于指定处理提交表单的格式
> method=get/post 用于指明提交表单的HTTP方法
> enctype=cdata 用于指定把表单提交给服务器时的互联网媒体形式

```html
<form method="post">
  <p>name:
    <input type="text" class="txt" size="12" maxlength="20" name="username" />
  </p>
</form>
```
### 结构元素
+ `<div>` 创建一个常规结构区域，块显示元素
+ `<header>` 包含标题的区域，块显示元素
+ `<nav>` 建立一个导航链接区域，块显示元素
+ `<main>` 包含网页文档的主要内容，块显示元素
+ `<footer>` 创建页脚，块显示元素
