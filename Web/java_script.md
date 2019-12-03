# JavaScript
## 简介
+ 一种轻量级的、动态的脚本语言
+ 可以是网页产生交互
+ 一种Web标准
+ 解释性语言
+ 面向对象
+ 宽松的语法和规则
+ 关键结构是函数而不是类
+ 运行在客户端
+ 事件驱动型

## 基本语法
+ 区分大小写
+ 句尾`;`可省略
+ 忽略多余空格
+ 句尾添加`\`用于换行
+ `//`进行单行注释
+ `/* ... */`用于多行注释

## 数据结构
### 常量
```js
const rate:Number = 0.5
```
### 变量
```js
var username,pwd,age
var username = "Tom"
username = "Jack"
```
### 数据类型
+ `Undefined` 未定义类型的变量
+ `Null` 定义空的或不存在的引用
+ `Boolean` 表示一个逻辑数值
+ `Number` 数值类型
+ `String` 字符串类型
+ `Object` 原始数据类型，可以包括上述其他类型

> JavaScript中的变量如果没有初始化（赋值），默认值为undefined

## 运算符
### 算数运算符
+ `+`加
+ `-`减
+ `*`乘
+ `/`除
+ `%` 求余数
+ `++` 变量加一后赋值给该变量
+ `--` 变量减一后赋值给该变量

### 比较运算符
+ `==` 判断是否相等
+ `!=` 判断是否不等
+ `>` 判断是否大于
+ `<` 判断是否小于
+ `>=` 判断是否大于等于
+ `<=` 判断是否小于等于

### 位运算符
+ `&` 与运算，操作数中的两个都为1，结果为1
+ `|` 或运算，操作数中的两个都为0，结果为0
+ `^` 异或运算，两个操作位相同时为0，不同时为1
+ `~` 取补运算，操作数按个位取反，1变为0，0变为1
+ `<<` 左移位，操作数按位左移，高位被丢弃，低位顺序补零
+ `>>` 右移位，操作数按位右移，低位被丢弃，其他各位依次右移

### 逻辑运算符
+ `&&`逻辑与
+ `||`逻辑或
+ `!`逻辑非

### 条件运算符
```js
(x>y)? 100*3:11 //条件? 表达式1：表达式2
```

### 赋值运算符
+ `=`
+ `+=`
+ `-=`
+ `*=`
+ `/=`
+ `%=`
+ `&=`
+ `|=`
+ `^=`

## 在`HTML`中的使用
### 在`HTML`中嵌入
可以在`HTML`文件的头部，也可以在网页内容中。用`<script>` `</script>`标签对嵌入即可
```HTML
<!doctype html>
<html>
<head>
<meta charset="utf-8">
    <title>JavaScript in HTML</title>
    <script language="javascript">
		document.write("This is a script")
	</script>
</head>
<body>
	<p>JavaScript</p>
	<script language="javascript">
	    document.write("This is a script too")
	</script>
</body>
</html>
```
### 调用JavaScript文件
在`html`文件中：
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>JavaScript</title>
    <script type="text/javascript" src="demo.js"></script>
</head>
<body>
<div>
    <button onclick="sayMagicWord();">Say the Magic Word</button>
</div>
</body>
</html>
```
在对应的`js`文件中：
```js
function sayMagicWord(){
    alert("Please!")
}
```
>对于不含有`JavaScript`的元素可以使用`<noscript>` `</noscript>`进行标示

## 控制结构
### 条件语句
#### `if`语句
`if`语句语法：
```js
if(test) {
  statements
}
```

#### `if-else`语句
```js
if(test) {
  statements
} else {
  statements
}
```

#### `if-else-if`语句
```js
if(test) {
  statements
} else if(test) {
  statements
} else {
  statements
}
```

#### `switch`语句
```js
switch (statement)
{
  case value1:
  statements
  break
  case value2:
  statements
  break
  ...
  default:
  statements
  break
}
```
### 循环控制语句
#### `while`语句
```js
while (test)
{
  statements
}
```

#### `do-while`语句
```js
do {
  statements
} while (test);
```

#### `for`语句
```js
for (var i=0; i<5; i++)
{
  statements
}
```

### 跳转语句
+ `break`跳出当前层循环
+ `continue`跳出本次循环

### 对话框
+ `alert`该对话框只用于提醒，不能对脚本产生任何的改变
+ `confirm`该对话框一般用于确认信息，只有一个参数，返回值为`true`或`false`
+ `prompt`该对话框可以进行输入，并返回用户输入的字符串，有两个参数，第一个用来显示提示信息，第二个用来显示输入框

## 函数
```js
function funcName(arg1, arg2, ...)
{
  statements
}
```
### 嵌套函数
```js
function outerFunc(arg1, arg2, ...)
{
  function innerFunc(arg3, arg4, ...)
  {
    statements
  }
  statements
}
```
### 递归函数
```js
function recursiveFunc(arg1)
{
  recursiveFunc(arg2)
}
```
### 常见内置函数
#### `eval`函数
返回当前字符串作为代码在上下文环境中执行的结果
+ `eval`函数有返回值
  + 如果参数字符串是一个表达式，就会返回表达式的值
  + 如果参数字符串不是表达式，没有值，那么返回`undefined`
+ 参数字符串作为代码执行时，是与`emal`函数的上下文相关的，即其中出现的函数或者变量调用必须在调用`eval`的上下文环境中可用

#### `isFinite`函数
`isFinite(number)`用来确定参数是否是一个有限的数值，其中`number`为必选项，可以是任意的数值。如果该参数是非数值、正无穷数或负无穷数，则返回`false`，否则返回`true`，如果是字符串类型的数值，则将会自动转换成数值型。

#### `isNaN`函数
`isNaN(number)`用来指明提供的值是否为保留值`NaN`，如果是则返回`true`，反之返回`false`

#### `parseInt`和`parseFloat`
将数值字符串转化为一个数值。`parseInt(str, [radix])`函数中，`str`为要转换成数值的字符串，`radix`为可选项，确定`str`的进制数

#### `Number`和`String`函数
`Number`将对象转换为数值型，`String`将对象转换为字符串

#### `escape`和`unescape`函数
`escape(charString)`对`String`对象进行编码，`unescape`返回指定值的`ASCII`字符串

## 对象
### 对象访问语句
#### `for-in`循环语句
```js
for (variable in object)
{
  statements
}
```
#### `with`语句
```js
with object
{
  statements
}
```
### `Array`对象
```js
var myArray = new Array([size])
var myArray = new Array(element0[, element1 ...])
```
#### 常用属性
##### `length`数组的长度
```js
var len = Array.length
```
##### `prototype`将新定义的属性或方法添加到`Array`对象中
```js
Array.prototype.methodName = functionName
```
+ `methodName` 必选项，新增方法的名称
+ `functionName` 必选项，要添加到对象中的函数的名称

#### 常用方法
##### `concat`
把当前数组与指定数组相连接，返回一个新的数组
```js
array1.concat(array2)
```
##### `join`
将数组中的所有元素连接为一个字符串，各元素之间用指定的符号分隔
```js
array.join(separator)
```
与`split`方法相反
##### `push`
将指定的一个或多个数据添加到数组中，该方法的返回值为添加数据后的数组的长度
```js
array.push([data1[, data2, ...]])
```
##### `reverse`
该方法将数组中的元素反序排列
```js
array.reverse()
```
##### `slice`
提取数组中的一个片段或子字符串
```js
array.slice([start[, end]])
```
+ `start` 指定片段起始点索引的数值
+ `end` 指定片段终点索引的数值，省略此参数则表示数组从开头`start`到结尾的所有元素

##### `sort`
将数组按照`Unicode`编码进行排序，并返回排序后的数组
```js
array.sort([cmpfun(arg1, arg2)])
```
+ `array` 必选项，数组名称
+ `cmpfun` 可选项，比较函数
+ `arg1`、`arg2` 可选项，比较函数的两个参数

##### `splice`
通过指定起始索引和数据个数的方式，删除或替换数组中的部分数据
```js
array.splice(start, count[, data1, ...])
```
不指定`data`则数据将会被删除

##### `toString`
把数组转化成字符串，中间用半角`,`分隔

##### `toLocaleString`
把数组转化成字符串，中间用全角`，`分隔

##### `unshift`
将指定元素插入到数组的开头位置
```js
array.unshift(newelement1, newelement2, ...)
```

### 自定义对象
```js
function Student(iName, iAdress, iGrade, iScore)
{
  this.name = iName
  this.adress = iAdress
  this.grade = iGrade
  this.score = iScore
  this.information = showInformation //showInformation is a definded function
}
```
#### 修改和删除对象实例的属性
修改属性可以直接利用赋值进行，删除对象实例的属性需要使用`delete`
```js
delete Student.score
```

#### 为对象添加新属性或新方法
通过`prototy`属性添加，自定义对象将直接被更改原型，但是内置对象只是动态的更改，不会更改原型

#### 自定义对象的嵌套
直接使用对象的某个实例作为另一个对象的属性即可




## DOM
元素对象，可以通过`js`利用`ID`等调用
在`html`文件中：
```html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript example2</title>
    <script src="please2.js" type="text/javascript"></script>
</head>
<body>
    <button onclick="sayMagicWord();">Say the Magic Word</button>
    <p id="result">What do you say?</p>
</body>
</html>
```
在对应的`js`文件中：
```js
function sayMagicWord() {
var paragraph = document.getElementById("result");
paragraph.innerHTML =  "PLEASE!";
}
```

### JavaScript语法
#### 数据类型
|   Type    |   Description |   Examples    |
|   :-: |   :-: |   :-: |
|   Number  |   integer or real |   42, -17, 3.14   |
|   Boolean |   logical value   |   true, false |
|   String  |   text string |   "hello, JS" |
|   Array   |   indexed list of elements    |   [12, 17, -5, 42]    |
|   Object  |   entity containing data and behavior |   \{name: "Marty", age: 12\}    |
|   function    |   "group of statements to execute"    |   "function message() \{alert(""hello, JS!"");\}"    |
|   null    |   an empty value  |   null    |
|   undefined   |   "the lack of a value; an undefined value"    |   undefined   |

#### 变量声明和赋值
```js
var age
var weight = 127.4;
var clientName = "Connie Client";
```
> JavaScript中的变量如果没有初始化（赋值），默认值为undefined

#### 注释
```js
// single-line comment
/* multi-line comment */
```
>4 种注释的语法：
```
HTML:<!-- comment  -->
CSS/JS/PHP:/* comment  */
Java/JS/PHP:// comment
PHP: # comment
```

#### DOM
|   Property    |   Type    |   Description |
|   :-: |   :-: |   :-: |
|   className   |   string  |   The class attribute of the element  |
|   id  |   string  |   The id attribute of the element |
|   innerHTML   |   string  |   The HTML markup and content inside the element  |
|   style   |   object  |   An object representing the element's style attributes   |
|   tagName |   string  |   The element's HTML tag, in uppercase    |
|   checked |   boolean |   Whether a checkbox or radio button is checked   |
|   disabled    |   boolean |   Whether a form control is disabled  |
|   href    |   string  |   Target URL for a link (a)   |
|   src |   string  |   Source URL for a image (img)    |
|   value   |   string  |   "Text inside a form control such as an input or textarea"   |

在`html`文件中：
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>JavaScript</title>
    <script type="text/javascript" src="demo.js"></script>
</head>
<body>
<h1>The Amazing Multiplier</h1>
<div>
<input id="num1" type="text" size="3" /> *
<input id="num2" type="text" size="3" /> =
<span id="answer"></span> <br />
<button onclick="compute();">Compute!</button>
</div>
</body>
</html>
```
在对应的`js`文件中：
```js
function compute() {
    var input1 = document.getElementById("num1");
    var input2 = document.getElementById("num2");
    var answer = document.getElementById("answer");
    var result = input1.value * input2.value;
    answer.innerHTML = result;
}
```

#### string
转义字符

|Name|Escape Sequences|
|:-:|:-:|
|single quote|`\'`|
|double quote|`\"`|
|backslash|`\\`|
|new line|`\n`|
|horizontal tab|`\t`|

字符与数值计算按照计算规则添加字符运算规则

|Expression|Result|
|:-:|:-:|
|1+"2"|"12"|
|1+3+"5"+7+9|"4579"|
|1+(3+"5")+(7+9)|"13516"|

#### parseInt和parseFloat

|   Expression  |   Result  |
|   :- |   :-: |
|   parseInt("42")  |   42  |
|   parseInt("12pt font")   |   m 12    |
|   parseInt("   4erver young!")    |   4   |
|   parseInt("")    |   NaN |
|   parseInt("Sacha Baron Cohen")   |   NaN |
|   parseInt("2.56")    |   2   |
|   parseFloat("2.56")  |   2.56    |
|   parseFloat("3.14159ppp09348")   |   3.14159 |
|   parseFloat("00000000.0000") |   0   |

#### string属性和方法

|   方法名 |   功能描述    |
|   :- |   :- |
|   charAt(index)   |   返回指定位置的字符，index从0开始 |
|   charCodeAt(index)   |   返回指定位置的字符的  ASCII  编码   |
|   String.fromCharCode(value)  |   返回指定ASCII码对应的字符串    |
|   indexof(searchStr)<br>indexof(searchStr,  fromIndex) |   返回某个指定的字符串值在字符串中首次出现的位置 |
|   split(delimeter) <br>split(delimeter,  Howmany) |   用于把一个字符串分割成字符串数组    |
|   substring(start)<br>substring(start,  stop)    |   提取字符串中介于两个指定下标之间的字符 |
|   toLowerCase()   |   用于把字符串转换为小写 |
|   toUpperCase()   |   用于把字符串转换为大写 |
|   trim()  |   返回取掉字符串两端空格后的字符串    |

#### for循环
基本结构：
```js
for (initialation; test; update) {
   statements;
}
```
示例：
在`html`文件中：
```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>JavaScript</title>
	<script type="text/javascript" src="demo.js"></script>
</head>
<body>
<h1>Factorializer</h1>
<p>Type an integer:</p>
<div>
	<input type="text" id="number" size="4">
	<button onclick="factorial();">Compute</button>
	<span id="result"></span>
</div>
</body>
</html>
```
在对应的`js`文件中：
```js
function factorial(){
	var input = document.getElementById("number");
	var number = input.value;
	var result_infor = 1;
	for (var i = number; i > 0; i--) {
		result_infor = result_infor * i;
	}
	var result = document.getElementById("result");
	result.innerHTML = result_infor;
}
```

#### Math对象
基本语法：
```js
Math.property
Math.method(parameters)
```
数学常量：

|常量|描述|
|:-|:-|
|Math.E|自然对数的底数，即2.718281828459045|
|Math.LN2|2的自然对数，约为0.693|
|Math.PI|圆周率，3.1415926|

数学函数：

|	函数	|	描述	|
|	:-	|	:-	|
|	Math.abs(x)	|	返回x的绝对值	|
|	Math.ceil(x)	|	返回x的向上取整值	|
|	Math.cos(x)	|	返回x的余弦值	|
|	Math.floor(x)	|	返回x的向下取整值	|
|	Math.log(x)	|	返回x的自然对数值	|
|	Math.max(x,y)	|	返回x和y中的大值	|
|	Math.in(x,y)	|	返回x和y中的小值	|
|	Math.pow(x,y)	|	返回x^y值	|
|	Math.random()	|	返回0-1之间的一个伪随机数	|
|	Math.round(x)	|	返回对x进行四舍五入后的值	|
|	Math.sin(x)	|	返回x的正弦值	|
|	Math.sqrt(x)	|	返回x的平方根值	|
|	Math.tan(x)	|	返回x的正切值	|

### 关系运算符
关系运算符包括：
`>` `>=` `<` `<=` `==` `===` `!=` `!==`

|表达式| 结果|
|:-:|:-:|
|5 < 10.0| true|
|7 === "7"| false|
|7 != "7.0" |false|
|7 !== "7.0" |true|
|42 < "hello"|false|
|42 >= "hello" |false|
|10 > "3 french hens"| false|

>`==`为不考虑数据类型的相等
`===`为考虑数据类型的相等
`!=` `!==`同理
**在实际使用时尽量使用`===`和`!==`运算符，而不用`==`和`!=`**
**原因：** 以下关系式若使用 `===`，则结果均为`false`
+ `""=="0"` is `false`
+ `0 == ""` is `true`
+ `null == undefined` is `true`
+ `"\t" == 0` is `true`
