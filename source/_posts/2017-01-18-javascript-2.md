---
title: "慕课网笔记：Javascript 进阶篇"
date: 2017-01-18 18:46:57
tags:
---

课程页面：http://www.imooc.com/learn/10

# 准备启航 
## 让你认识JS
## 编程练习

# JS基础语法
## 什么是变量
## 变量命名
## 变量声明
## 变量赋值
## 表达式
## +号操作符
## 自加一，自减一 （++和--）
## 比较操作符
## 逻辑与操作符
## 逻辑或操作符
## 逻辑非操作符
## 操作符优先级
## 编程练习

# 一数组
## 什么是数组
## 如何创建数组
## 数组赋值
## 向数组增加一个新元素
## 使用数组元素
## 数组属性length
## 二维数组
## 编程练习

# 流程控制语句
## if语句
## if...else语句
## if..else嵌套语句
## switch语句
## for循环
## while循环
## do...while循环
## 退出循环break
## 继续循环continue
## 编程练习

# 函数
## 什么是函数
## 定义函数
## 函数调用
## 有参数的函数
## 返回值的函数
## 编程练习

# 事件响应，让网页交互
## 什么是事件
## 鼠标单击事件（onclick）
## 鼠标经过事件（onmouseover）
## 鼠标移开事件（onmouseout）
## 光标聚焦事件（onfocus）
## 失焦事件（onblur）
## 内容选中事件（onselect）
## 文本框内容改变事件（onchange）
## 加载事件（onload）
## 卸载事件（onunload）
## 编程练习

# JavaScript内置对象 

## 什么是对象

JavaScript 中的所有事物都是对象，如：字符串、数值、数组、函数等，每个对象带有**属性**和**方法**。
- **对象的属性**：反映该对象某些特定的性质。如：字符串的长度、图像的长宽等；
- **对象的方法**：能够在对象上执行的动作。例如，表单的“提交”(`Submit`)，时间的“获取”(`getYear`)等；

JavaScript 提供多个内建对象，比如 `String`、`Date`、`Array` 等等。使用对象前先定义。如下使用数组对象：
``` javascript
  var objectName = new Array(); // 使用 new 关键字定义对象
```
或者
``` javascript
  var objectName =[];
```
访问对象属性的语法：
``` javascript
objectName.propertyName
```
如使用 `Array` 对象的 `length` 属性来获得数组的长度：
``` javascript
var myarray=new Array(6); // 定义数组对象
var myl=myarray.length;   // 访问数组长度 length 属性
```
以上代码执行后，`myl` 的值将是：`6`。

访问对象的方法：
``` javascript
objectName.methodName()
```
如使用 `string` 对象的 `toUpperCase()` 方法来将文本转换为大写：
``` javascript
var mystr = "Hello world!";        // 创建一个字符串
var request = mystr.toUpperCase(); // 使用字符串对象方法
```
以上代码执行后，`request` 的值是：`HELLO WORLD!`。

 
## Date 日期对象

日期对象可以储存任意一个日期，并且可以精确到毫秒数（`1/1000` 秒）。

定义一个时间对象：
``` javascript
var Udate = new Date(); 
```
注意：使用关键字 `new`，`Date()` 的首字母必须大写。 

使 `Udate` 成为日期对象，并且已有初始值：当前时间（当前电脑系统时间）。

如果要自定义初始值，可以用以下方法：
``` javascript
var d = new Date(2012, 10, 1);    //2012年10月1日
var d = new Date('Oct 1, 2012');  //2012年10月1日
```
我们最好使用下面介绍的“方法”来严格定义时间。

访问方法语法：
``` javascript
<日期对象>.<方法>
```
`Date 对象中处理时间和日期的常用方法：

![Date 对象](/images/javascript-2-7-2-date-object.jpg)


## 返回/设置年份方法

get/setFullYear() 返回/设置年份，用四位数表示。
``` javascript
var mydate=new Date();//当前时间2014年3月6日
document.write(mydate+"<br>");//输出当前时间
document.write(mydate.getFullYear()+"<br>");//输出当前年份
mydate.setFullYear(81); //设置年份
document.write(mydate+"<br>"); //输出年份被设定为 0081年。
```
注意：不同浏览器，`mydate.setFullYear(81)` 结果不同，年份被设定为 `0081` 或 `81` 两种情况。

结果：
``` bash
Thu Mar 06 2014 10:57:47 GMT+0800
2014
Thu Mar 06 0081 10:57:47 GMT+0800
```

注意：
1.结果格式依次为：星期、月、日、年、时、分、秒、时区。（火狐浏览器）
2. 不同浏览器，时间格式有差异。

注意：
我输入函数的时候漏掉了括号：
``` html
<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>获得年份 </title>
<script type="text/javascript">
var mydate=new Date(); 
var myyear=mydate.getFullYear
document.write("年份："+myyear);
</script>
</head>
<body>
</body>
</html>
```
结果是：
``` bash
年份：function getFullYear() { [native code] }
```


## 返回星期方法

`getDay()` 返回星期，返回的是 `0-6` 的数字，`0` 表示星期天。如果要返回相对应“星期”，通过数组完成，代码如下：
``` javascript
<script type="text/javascript">
  var mydate=new Date();//定义日期对象
  var weekday=["星期日","星期一","星期二","星期三","星期四","星期五","星期六"];
//定义数组对象,给每个数组项赋值
  var mynum=mydate.getDay();//返回值存储在变量mynum中
  document.write(mydate.getDay());//输出getDay()获取值
  document.write("今天是："+ weekday[mynum]);//输出星期几
</script>
```
注意：以上代码是在 `2014` 年 `3` 月 `7` 日，星期五运行。

结果：
``` bash
5
今天是：星期五
```


## 返回/设置时间方法

`get/setTime()` 返回/设置时间，单位毫秒数，计算从 `1970` 年 `1` 月 `1` 日零时到日期对象所指的日期的毫秒数。

如果将目前日期对象的时间推迟 `1` 小时，代码如下：
``` javascript
<script type="text/javascript">
  var mydate=new Date();
  document.write("当前时间："+mydate+"<br>");
  mydate.setTime(mydate.getTime() + 60 * 60 * 1000);
  document.write("推迟一小时时间：" + mydate);
</script>
```
结果：
``` bash
当前时间：Thu Mar 6 11:46:27 UTC+0800 2014
推迟一小时时间：Thu Mar 6 12:46:27 UTC+0800 2014
```

注意：
1. 一小时 60 分，一分 60 秒，一秒 1000 毫秒
2. 时间推迟 1 小时,就是：`x.setTime(x.getTime() + 60 * 60 * 1000);`。


## String 字符串对象

在之前的学习中已经使用字符串对象了，定义字符串的方法就是直接赋值。比如：
``` javascript
var mystr = "I love JavaScript!"
```
定义 `mystr` 字符串后，我们就可以访问它的属性和方法。

访问字符串对象的属性 `length`：
stringObject.length; 返回该字符串的长度。
``` javascript

var mystr="Hello World!";
var myl=mystr.length;
```
以上代码执行后，`myl` 的值将是：12。

访问字符串对象的方法：

使用 `String` 对象的 `toUpperCase()` 方法来将字符串小写字母转换为大写：
``` javascript
var mystr="Hello world!";
var mynum=mystr.toUpperCase();
```
以上代码执行后，`mynum` 的值是：`HELLO WORLD!`。


## 返回指定位置的字符

`charAt()` 方法可返回指定位置的字符。返回的字符是长度为 1 的字符串。

语法：
``` javascript
stringObject.charAt(index)
```
参数说明：

![String charAt](/images/javascript-2-7-7-string-index.jpg)

注意：
1.字符串中第一个字符的下标是 `0`。最后一个字符的下标为字符串长度减一（`string.length-1`）。
2.如果参数 `index` 不在 `0` 与 `string.length-1` 之间，该方法将返回一个空字符串。

如：在字符串 `"I love JavaScript!"` 中，返回位置 `2` 的字符：
``` javascript
<script type="text/javascript">
  var mystr="I love JavaScript!"
  document.write(mystr.charAt(2));
</script>
```
注意：一个空格也算一个字符。

以上代码的运行结果：
``` bash
l
```

注意：
``` html
<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>string对象 </title>
  <script type="text/javascript">
  var mystr="I love JavaScript!"
  document.write(mystr[mystr.length-1]);
</script>
</head>
<body>
</body>
</html>
```

我没有所用 `charAt()`，而是用的 `[]`。
注意这里的区别。


## 返回指定的字符串首次出现的位置

`indexOf()` 方法可返回某个指定的字符串值在字符串中首次出现的位置。

语法：
``` javascript
stringObject.indexOf(substring, startpos)
```
参数说明：

![String indexOf](/images/javascript-2-7-8-string-indexof.jpg)

说明：

1.该方法将从头到尾地检索字符串 stringObject，看它是否含有子串 substring。
2.可选参数，从stringObject的startpos位置开始查找substring，如果没有此参数将从stringObject的开始位置查找。
3.如果找到一个 substring，则返回 substring 的第一次出现的位置。stringObject 中的字符位置是从 0 开始的。

注意：
1.indexOf() 方法区分大小写。
2.如果要检索的字符串值没有出现，则该方法返回 -1。

例如：对 "I love JavaScript!" 字符串内进行不同的检索：
``` javascript
<script type="text/javascript">
  var str="I love JavaScript!"
  document.write(str.indexOf("I") + "<br />");
  document.write(str.indexOf("v") + "<br />");
  document.write(str.indexOf("v",8));
</script>
```
以上代码的输出：
``` bash
0
4
9
```


## 字符串分割split()

知识讲解：

`split()` 方法将字符串分割为字符串数组，并返回此数组。

语法：
``` javascript
stringObject.split(separator,limit)
```
参数说明：

![String split](/images/javascript-2-7-9-string-split.jpg)

注意：如果把空字符串 ("") 用作 separator，那么 stringObject 中的每个字符之间都会被分割。

我们将按照不同的方式来分割字符串：

使用指定符号分割字符串，代码如下：
``` javascript
var mystr = "www.imooc.com";
document.write(mystr.split(".")+"<br>");
document.write(mystr.split(".", 2)+"<br>");
```
运行结果：
``` bash
www,imooc,com
www,imooc
```
将字符串分割为字符，代码如下：
``` javascript
document.write(mystr.split("")+"<br>");
document.write(mystr.split("", 5));
```
运行结果：
``` bash
w,w,w,.,i,m,o,o,c,.,c,o,m
w,w,w,.,i
```


## 提取字符串 substring()

`substring()` 方法用于提取字符串中介于两个指定下标之间的字符。

语法：
``` javascript
stringObject.substring(startPos,stopPos) 
```

参数说明：

![String substring](/images/javascript-2-7-10-string-substring.jpg)

注意：
1. 返回的内容是从 start开始(包含start位置的字符)到 stop-1 处的所有字符，其长度为 stop 减start。
2. 如果参数 start 与 stop 相等，那么该方法返回的就是一个空串（即长度为 0 的字符串）。
3. 如果 start 比 stop 大，那么该方法在提取子串之前会先交换这两个参数。

使用 substring() 从字符串中提取字符串，代码如下：
``` javascript
<script type="text/javascript">
  var mystr="I love JavaScript";
  document.write(mystr.substring(7));
  document.write(mystr.substring(2,6));
</script>
```
运行结果：
``` bash
JavaScript
love
```


## 提取指定数目的字符 substr()

`substr()` 方法从字符串中提取从 `startPos` 位置开始的指定数目的字符串。

语法：
``` javascript
stringObject.substr(startPos,length)
```
参数说明：

![String substr](/images/javascript-2-7-11-string-substr.jpg)

注意：如果参数 `startPos` 是负数，从字符串的尾部开始算起的位置。也就是说，`-1` 指字符串中最后一个字符，`-2` 指倒数第二个字符，以此类推。

如果 `startPos` 为负数且绝对值大于字符串长度，`startPos` 为 `0`。

使用 `substr()` 从字符串中提取一些字符，代码如下：
``` javascript
<script type="text/javascript">
  var mystr="I love JavaScript!";
  document.write(mystr.substr(7));
  document.write(mystr.substr(2,4));
</script>
```
运行结果：
``` bash
JavaScript!
love
```


## Math对象

`Math` 对象，提供对数据的数学计算。

使用 `Math` 的属性和方法，代码如下：
``` javascript
<script type="text/javascript">
  var mypi=Math.PI; 
  var myabs=Math.abs(-15);
  document.write(mypi);
  document.write(myabs);
</script>
```
运行结果：
``` bash
3.141592653589793
15
```
注意：`Math` 对象是一个固有的对象，无需创建它，直接把 `Math` 作为对象使用就可以调用其所有属性和方法。这是它与 `Date`、`String` 对象的区别。

`Math` 对象属性：

![Math 对象](/images/javascript-2-7-12-math-1.jpg)

`Math` 对象方法：

![Math 对象](/images/javascript-2-7-12-math-2.jpg)

以上方法不做全部讲解，只讲解部分方法。此节没有任务，快快进入下节学习。


## 向上取整 ceil()

`ceil()` 方法可对一个数进行向上取整。

语法：
``` javascript
Math.ceil(x)
```
参数说明：

![Math.ceil()](/images/javascript-2-7-13-math-ceil.jpg)

注意：它返回的是大于或等于 `x`，并且与 `x` 最接近的整数。

我们将把 `ceil()` 方法运用到不同的数字上，代码如下：
``` javascript
<script type="text/javascript">
  document.write(Math.ceil(0.8) + "<br />")
  document.write(Math.ceil(6.3) + "<br />")
  document.write(Math.ceil(5) + "<br />")
  document.write(Math.ceil(3.5) + "<br />")
  document.write(Math.ceil(-5.1) + "<br />")
  document.write(Math.ceil(-5.9))
</script>
```
运行结果：
``` bash
1
7
5
4
-5
-5
```

## 向下取整 floor()

`floor()` 方法可对一个数进行向下取整。

语法：
``` javascript
Math.floor(x)
```
参数说明：

![Math.floor()](/images/javascript-2-7-14-math-floor.jpg)


注意：返回的是小于或等于 `x`，并且与 `x` 最接近的整数。

我们将在不同的数字上使用 `floor()` 方法，代码如下：
``` javascript
<script type="text/javascript">
  document.write(Math.floor(0.8)+ "<br>")
  document.write(Math.floor(6.3)+ "<br>")
  document.write(Math.floor(5)+ "<br>")
  document.write(Math.floor(3.5)+ "<br>")
  document.write(Math.floor(-5.1)+ "<br>")
  document.write(Math.floor(-5.9))
</script>
```
运行结果：
``` bash
0
6
5
3
-6
-6
```

## 四舍五入 round()

`round()` 方法可把一个数字四舍五入为最接近的整数。

语法：
``` javascript
Math.round(x)
```
参数说明：

![Math.round()](/images/javascript-2-7-15-math-round-1.jpg)

注意：
1. 返回与 `x` 最接近的整数。
2. 对于 `0.5`，该方法将进行上舍入。（`5.5` 将舍入为 `6`）
3. 如果 `x` 与两侧整数同等接近，则结果接近 `+∞` 方向的数字值 。（如 `-5.5` 将舍入为 `-5`；`-5.52` 将舍入为 `-6`），如下图：

![Math.round()](/images/javascript-2-7-15-math-round-2.jpg)

把不同的数舍入为最接近的整数，代码如下：
``` javascript
<script type="text/javascript">
  document.write(Math.round(1.6)+ "<br>");
  document.write(Math.round(2.5)+ "<br>");
  document.write(Math.round(0.49)+ "<br>");
  document.write(Math.round(-6.4)+ "<br>");
  document.write(Math.round(-6.6));
</script>
```
运行结果：
``` bash
2
3
0
-6
-7
```

## 随机数 random()

`random()` 方法可返回介于 `0~1`（大于或等于 `0` 但小于 `1`)之间的一个随机数。

语法：
``` javascript
Math.random();
```
注意：返回一个大于或等于 `0` 但小于 `1` 的符号为正的数字值。

我们取得介于 `0` 到 `1` 之间的一个随机数，代码如下：
``` javascript
<script type="text/javascript">
  document.write(Math.random());
</script>
```
运行结果：
``` bash
0.190305486195328  
```
注意：因为是随机数，所以每次运行结果不一样，但是 `0~1` 的数值。
获得 `0~10` 之间的随机数，代码如下：
``` javascript
<script type="text/javascript">
  document.write((Math.random())*10);
</script>
```
运行结果：
``` bash
8.72153625893887
```

## Array 数组对象

数组对象是一个对象的集合，里边的对象可以是不同类型的。数组的每一个成员对象都有一个“下标”，用来表示它在数组中的位置，是从零开始的

数组定义的方法：

1. 定义了一个空数组：
``` javascript
var  数组名= new Array();
```
2. 定义时指定有n个空元素的数组：
``` javascript
var 数组名 =new Array(n);
```
3.定义数组的时候，直接初始化数据：
``` javascript
var  数组名 = [<元素1>, <元素2>, <元素3>...];
```
我们定义 `myArray` 数组，并赋值，代码如下：
``` javascript
var myArray = [2, 8, 6]; 
```
说明：定义了一个数组 `myArray`，里边的元素是：`myArray[0] = 2; myArray[1] = 8; myArray[2] = 6`。

数组元素使用：
``` javascript
数组名[下标] = 值;
```
注意：数组的下标用方括号括起来，从 `0` 开始。

数组属性：
`length` 用法：`<数组对象>.length`；
返回：数组的长度，即数组里有多少个元素。它等于数组里最后一个元素的下标加一。

数组方法：

![Array 对象](/images/javascript-2-7-17-array.jpg)

以上方法不做全部讲解，只讲解部分方法。此节没有任务，快快进入下节学习。


## 数组连接 concat())

`concat()` 方法用于连接两个或多个数组。此方法返回一个新数组，不改变原来的数组。

语法：
``` javascript
arrayObject.concat(array1,array2,...,arrayN)
```
参数说明：

![Array concat()](/images/javascript-2-7-18-concat.jpg)

注意：该方法不会改变现有的数组，而仅仅会返回被连接数组的一个副本。

我们创建一个数组，将把 `concat()` 中的参数连接到数组 `myarr` 中，代码如下：
``` javascript
<script type="text/javascript">
  var mya = new Array(3);
  mya[0] = "1";
  mya[1] = "2";
  mya[2] = "3";
  document.write(mya.concat(4,5)+"<br>");
  document.write(mya); 
</script>
```
运行结果：
``` bash
1,2,3,4,5
1,2,3
```
我们创建了三个数组，然后使用 `concat()` 把它们连接起来，代码如下：
``` javascript
<script type="text/javascript">
  var mya1= new Array("hello!")
  var mya2= new Array("I","love");
  var mya3= new Array("JavaScript","!");
  var mya4=mya1.concat(mya2,mya3);
  document.write(mya4);
</script>
```
运行结果：
``` bash
hello!,I,love,JavaScript,!
```


## 指定分隔符连接数组元素 join()

`join()` 方法用于把数组中的所有元素放入一个字符串。元素是通过指定的分隔符进行分隔的。

语法：
``` javascript
arrayObject.join(分隔符)
```
参数说明：

![Array join()](/images/javascript-2-7-19-join.jpg)

注意：
返回一个字符串，该字符串把**数组**中的各个元素串起来，用`<分隔符`>`置于元素与元素之间。这个方法不影响数组原本的内容。 我们使用 `join()` 方法，将数组的所有元素放入一个字符串中，代码如下：

``` javascript
<script type="text/javascript">
  var myarr = new Array(3);
  myarr[0] = "I";
  myarr[1] = "love";
  myarr[2] = "JavaScript";
  document.write(myarr.join());
</script>
```
运行结果：
``` bash
I,love,JavaScript
```

我们将使用分隔符来分隔数组中的元素，代码如下：
``` javascript
<script type="text/javascript">
  var myarr = new Array(3)
  myarr[0] = "I";
  myarr[1] = "love";
  myarr[2] = "JavaScript";
  document.write(myarr.join("."));
</script>
```
运行结果：
``` bash
I.love.JavaScript
```


## 颠倒数组元素顺序 reverse()

`reverse()` 方法用于颠倒数组中元素的顺序。

语法：
``` javascript
arrayObject.reverse()
```
注意：该方法**会改变原来的数组**，而不会创建新的数组。换句话说，`reverse()` 是“in-place”的。

定义数组 `myarr` 并赋值，然后颠倒其元素的顺序：
``` javascript
<script type="text/javascript">
  var myarr = new Array(3)
  myarr[0] = "1"
  myarr[1] = "2"
  myarr[2] = "3"
  document.write(myarr + "<br />")
  document.write(myarr.reverse())
</script>
```
运行结果：
``` bash
1,2,3
3,2,1
```


## 选定元素 slice()

`slice()` 方法可从已有的数组中返回选定的元素。

语法：
``` javascript
arrayObject.slice(start,end)
```
参数说明：

![Array slice()](/images/javascript-2-7-21-slice.jpg)

1. 返回一个新的数组，包含从 `start` 到 `end` （不包括该元素，即 `end-1`）的 `arrayObject` 中的元素。
2. 该方法并不会修改数组，而是返回一个子数组。

注意：
1. 可使用负值从数组的尾部选取元素。
2. 如果 `end` 未被规定，那么 `slice()` 方法会选取从 `start` 到数组结尾的所有元素。
3. `String.slice()` 与 `Array.slice()` 相似。

我们将创建一个新数组，然后从其中选取的元素，代码如下：
``` javascript
<script type="text/javascript">
  var myarr = new Array(1,2,3,4,5,6);
  document.write(myarr + "<br>");
  document.write(myarr.slice(2,4) + "<br>");
  document.write(myarr);
</script>
```
运行结果：
``` bash
1,2,3,4,5,6
3,4
1,2,3,4,5,6
```


## 数组排序 sort()

`sort()` 方法使数组中的元素按照一定的顺序排列。

语法：
``` javascript
arrayObject.sort(方法函数)
```
参数说明：

![Array sort()](/images/javascript-2-7-22-sort.jpg)

1.如果不指定 `<方法函数>`，则按 unicode 码顺序排列。
2.如果指定 `<方法函数>`，则按 `<方法函数>` 所指定的排序方法排序。

``` javascript
myArray.sort(sortMethod);
```

注意：
该函数要比较两个值，然后返回一个用于说明这两个值的相对顺序的数字。比较函数应该具有两个参数 `a` 和 `b`，其返回值如下： 
- 若返回值 `<=-1`，则表示 `A` 在排序后的序列中出现在 `B` 之前。
- 若返回值 `>-1 && <1`，则表示 `A` 和 `B` 具有相同的排序顺序。
- 若返回值 `>=1`，则表示 `A` 在排序后的序列中出现在 `B` 之后。

1.使用 `sort()` 将数组进行排序，代码如下：
``` javascript
<script type="text/javascript">
  var myarr1 = new Array("Hello","John","love","JavaScript"); 
  var myarr2 = new Array("80","16","50","6","100","1");
  document.write(myarr1.sort()+"<br>");
  document.write(myarr2.sort());
</script>
```
运行结果：
``` bash
Hello,JavaScript,John,love
1,100,16,50,6,80
```
注意：上面的代码没有按照数值的大小对数字进行排序。

2.如要实现这一点，就必须使用一个排序函数，代码如下：
``` javascript
<script type="text/javascript">
  function sortNum(a,b) {
  return a - b;
 //升序，如降序，把“a - b”该成“b - a”
}
 var myarr = new Array("80","16","50","6","100","1");
  document.write(myarr + "<br>");
  document.write(myarr.sort(sortNum));
</script>
```
运行结果：
``` bash
80,16,50,6,100,1
1,6,16,50,80,100
```


## 编程练习

编程练习
某班的成绩出来了，现在老师要把班级的成绩打印出来。

效果图：
``` bash
XXXX年XX月X日 星期X--班级总分为：81
```

格式要求：

1、显示打印的日期。 格式为类似“XXXX年XX月XX日 星期X” 的当前的时间。
2、计算出该班级的平均分（保留整数）。

同学成绩数据如下：

"小明:87; 小花:81; 小红:97; 小天:76;小张:74;小小:94;小西:90;小伍:76;小迪:64;小曼:76"

任务：
第一步：可通过 Javascript 的日期对象来得到当前的日期。
提示：使用 `Date()` 日期对象，注意星期返回值为 `0-6`，所以要转成文字"星期X"。
第二步：一长窜的字符串不好弄，找规律后分割放到数组里更好操作哦。

第三步：分割字符串得到分数，然后求和取整。

提示：`parseInt()` 字符串类型转成整型。

标准答案：
``` javascript
<script type="text/javascript">
  //通过javascript的日期对象来得到当前的日期，并输出。
  var date = new Date();  // 实例化日期对象  
  var timeStr = '';//日期 
  timeStr = date.getFullYear() + "年" ;  
  timeStr += date.getMonth() + 1 +"月";  
  timeStr += date.getDate()+"日";  
  var day  = date.getDay(); //星期 
  var week = '';
  switch(day){
	case  0 :
		week  = '星期一';
		break;
	case  1 :
		week  = '星期二';
	break;
	case  2 :
		week  = '星期三';
		break;
	case  3 :
		week  = '星期四';
		break;
	case  4 :
		week  = '星期五';
		break;
	case  5 :
		week  = '星期六';
		break;
	case  6 :
		week  = '星期天';
		break; 
  }
  timeStr += "&nbsp;"+week;
  //打印出日期
  document.write(timeStr);
  //成绩是一长窜的字符串不好处理，找规律后分割放到数组里更好操作哦
  var sorceStr = "小明:87; 小花:81; 小红:97; 小天:76;小张:74;小小:94;小西:90;小伍:76;小迪:64;小曼:76";
  var arr  = sorceStr.split(';');//按 ; 符号进行数组分割
  var sum = 0;
  var av= 0;
  for( var i =0;i<arr.length;i++ ){
	    var index = arr[i].indexOf(':'); //根据 ： 符号确定数字开始的位置 
		sum += parseInt(  arr[i].substr(index+1,2)  );  // parseInt() 字符串类型转成整型
   }
	av = sum/arr.length;
    av = Math.floor(av);  // 取整
   
  //从数组中将成绩撮出来，然后求和取整，并输出。
   document.write("--班级总分为："+av);
</script>
```

我的答案：
``` javascript
<script type="text/javascript">
  //通过javascript的日期对象来得到当前的日期，并输出。
  var weekday = new Array("星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六")
  var wd = myD.getDay();
  var myD = new Date();
  document.write(
      myD.getFullYear() + "年" + parseInt(myD.getMonth()+1) + "月" + myD.getDate() + "日 "
            + weekday[wd] + " -- 班级总分为：");
  //成绩是一长窜的字符串不好处理，找规律后分割放到数组里更好操作哦
  var scoreStr = "小明:87;小花:81;小红:97;小天:76;小张:74;小小:94;小西:90;小伍:76;小迪:64;小曼:76";
  var scoreArray = scoreStr.split(";");
  var scores = new Array(scoreArray.length);
  var total = 0;
  for (i = 0; i < scores.length; i++) {
      scores[i] = parseInt(scoreArray[i].split(":")[1]);
      total += scores[i];
  }
  //从数组中将成绩撮出来，然后求和取整，并输出。
  document.write(Math.round(total/scores.length));

</script>
```


# 浏览器对象 

## window 对象

`window` 对象是 `BOM` 的核心，`window` 对象指当前的浏览器窗口。

`window` 对象方法:

![](/images/javascript-2-8-01-window-object.jpg "Window 对象")

注意：
在 JavaScript 基础篇中，已讲解了部分属性，`window` 对象重点讲解计时器。


## JavaScript 计时器

在 JavaScript 中，我们可以在设定的时间间隔之后来执行代码，而不是在函数被调用后立即执行。
计时器类型：
一次性计时器：仅在指定的延迟时间之后触发一次。
间隔性触发计时器：每隔一定的时间间隔就触发一次。
计时器方法：

![计时器方法](/images/javascript-2-8-02-timer-methods.jpg "计时器方法")


## 计时器 setInterval()

在执行时,从载入页面后每隔指定的时间执行代码。

语法：
``` javascript
setInterval(代码,交互时间);
```
参数说明：
1. 代码：要调用的函数或要执行的代码串。
2. 交互时间：周期性执行或调用表达式之间的时间间隔，以毫秒计（1s=1000ms）。

返回值：
一个可以传递给 `clearInterval()` 从而取消对“代码”的周期性执行的值。

调用函数格式（假设有一个 `clock()` 函数）：
``` javascript
setInterval("clock()",1000)
```
或
``` javascript
setInterval(clock,1000)
```
我们设置一个计时器，每隔 100 毫秒调用 `clock()` 函数，并将时间显示出来，代码如下：
``` html
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>计时器</title>
<script type="text/javascript">
  var int=setInterval(clock, 100)
  function clock(){
    var time=new Date();
    document.getElementById("clock").value = time;
  }
</script>
</head>
<body>
  <form>
    <input type="text" id="clock" size="50"  />
  </form>
</body>
</html>
```

这一节的解析器貌似有点问题。


## 取消计时器 clearInterval()

`clearInterval()` 方法可取消由 `setInterval()` 设置的交互时间。

语法：
``` javascript
clearInterval(id_of_setInterval)
```
参数说明：
`id_of_setInterval`：由 `setInterval()` 返回的 ID 值。

每隔 100 毫秒调用 `clock()` 函数,并显示时间。当点击按钮时，停止时间,代码如下：
``` html
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>计时器</title>
<script type="text/javascript">
   function clock(){
      var time=new Date();                     
      document.getElementById("clock").value = time;
   }
// 每隔100毫秒调用clock函数，并将返回值赋值给i
     var i=setInterval("clock()",100);
</script>
</head>
<body>
  <form>
    <input type="text" id="clock" size="50"  />
    <input type="button" value="Stop" onclick="clearInterval(i)"  />
  </form>
</body>
</html>
```


## 计时器 setTimeout()

`setTimeout()` 计时器，在载入后延迟指定时间后，去执行一次表达式；且仅执行一次。

语法：
``` javascript
setTimeout(代码,延迟时间);
```
参数说明：
1. 要调用的函数或要执行的代码串。
2. 延时时间：在执行代码前需等待的时间，以毫秒为单位（1s=1000ms)。

当我们打开网页3秒后，在弹出一个提示框，代码如下：
``` html
<!DOCTYPE HTML>
<html>
<head>
<script type="text/javascript">
  setTimeout("alert('Hello!')", 3000 );
</script>
</head>
<body>
</body>
</html>
```
当按钮 start 被点击时，`setTimeout()` 调用函数，在 5 秒后弹出一个提示框。
``` html
<!DOCTYPE HTML>
<html>
<head>
<script type="text/javascript">
function tinfo(){
  var t=setTimeout("alert('Hello!')",5000);
 }
</script>
</head>
<body>
<form>
  <input type="button" value="start" onClick="tinfo()">
</form>
</body>
</html>
```
要创建一个运行于无穷循环中的计数器，我们需要编写一个函数来调用其自身。在下面的代码，当按钮被点击后，输入域便从 0 开始计数。
``` html
<!DOCTYPE HTML>
<html>
<head>
<script type="text/javascript">
var num=0;
function numCount(){
 document.getElementById('txt').value=num;
 num=num+1;
 setTimeout("numCount()",1000);
 }
</script>
</head>
<body>
<form>
<input type="text" id="txt" />
<input type="button" value="Start" onClick="numCount()" />
</form>
</body>
</html>
```

## 取消计时器 clearTimeout()

`setTimeout()` 和 `clearTimeout()` 一起使用，停止计时器。

语法：
``` html
clearTimeout(id_of_setTimeout)
```
参数说明：
`id_of_setTimeout`：由 `setTimeout()` 返回的 ID 值。该值标识要取消的延迟执行代码块。

下面的例子和上节的无穷循环的例子相似。唯一不同是，现在我们添加了一个 "Stop" 按钮来停止这个计数器：
``` html
<!DOCTYPE HTML>
<html>
<head>
<script type="text/javascript">
  var num=0,i;
  function timedCount(){
    document.getElementById('txt').value=num;
    num=num+1;
    i=setTimeout(timedCount,1000);
  }
    setTimeout(timedCount,1000);
  function stopCount(){
    clearTimeout(i);
  }
</script>
</head>
<body>
  <form>
    <input type="text" id="txt">
    <input type="button" value="Stop" onClick="stopCount()">
  </form>
</body>
</html>
```

## History 对象

history对象记录了用户曾经浏览过的页面(URL)，并可以实现浏览器前进与后退相似导航的功能。

注意:从窗口被打开的那一刻开始记录，每个浏览器窗口、每个标签页乃至每个框架，都有自己的history对象与特定的window对象关联。

语法：

window.history.[属性|方法]
注意：window可以省略。

History 对象属性

![History 属性](/images/javascript-2-8-07-history-attr.jpg "History 属性")

History 对象方法

![History 方法](/images/javascript-2-8-07-history-methods.jpg "History 方法")

使用length属性，当前窗口的浏览历史总长度，代码如下：
``` html
<script type="text/javascript">
  var HL = window.history.length;
  document.write(HL);
</script>
```


## 返回前一个浏览的页面

返回前一个浏览的页面
back()方法，加载 history 列表中的前一个 URL。

语法：

window.history.back();
比如，返回前一个浏览的页面，代码如下：

window.history.back();
注意：等同于点击浏览器的倒退按钮。

back()相当于go(-1),代码如下:

window.history.go(-1);


## 返回下一个浏览的页面

forward()方法，加载 history 列表中的下一个 URL。

如果倒退之后，再想回到倒退之前浏览的页面，则可以使用forward()方法,代码如下:

window.history.forward();
注意：等价点击前进按钮。

forward()相当于go(1),代码如下:

window.history.go(1);

## 返回浏览历史中的其他页面

go()方法，根据当前所处的页面，加载 history 列表中的某个具体的页面。

语法：

window.history.go(number);
参数：

![history.go()](/images/javascript-2-8-10-history-go.jpg "history.go()")

浏览器中，返回当前页面之前浏览过的第二个历史页面，代码如下：

window.history.go(-2);
注意：和在浏览器中单击两次后退按钮操作一样。

同理，返回当前页面之后浏览过的第三个历史页面，代码如下：

window.history.go(3);


## Location 对象

`location` 用于获取或设置窗体的 URL，并且可以用于解析 URL。

语法：
``` javascript
location.[属性|方法]
```
`location` 对象属性图示：

![`location` 对象属性图示](/images/javascript-2-8-11-location-attrs-1.jpg "`location` 对象属性图示")

`location` 对象属性：

![`location` 对象属性](/images/javascript-2-8-11-location-attrs-2.jpg "`location` 对象属性")

`location` 对象方法：

![`location` 对象方法](/images/javascript-2-8-11-location-methods.jpg "`location` 对象方法")


## navigator 对象

`navigator` 对象包含有关浏览器的信息，通常用于检测浏览器与操作系统的版本。

对象属性：

![navigator 对象属性](/images/javascript-2-8-12-navigator.jpg "Navigator 对象属性")

查看浏览器的名称和版本，代码如下：
``` javascript
<script type="text/javascript">
   var browser=navigator.appName;
   var b_version=navigator.appVersion;
   document.write("Browser name"+browser);
   document.write("<br>");
   document.write("Browser version"+b_version);
</script>
```


## userAgent

返回用户代理头的字符串表示(就是包括浏览器版本信息等的字符串)

语法：
``` javascript
navigator.userAgent
```
几种浏览的 `user_agent.`，像 360 的兼容模式用的是 IE、极速模式用的是 chrome 的内核。

![](/images/javascript-2-8-13-useragent-1.jpg)

使用 `userAgent` 判断使用的是什么浏览器（假设使用的是 IE8 浏览器），代码如下：
``` javascript
function validB(){ 
  var u_agent = navigator.userAgent; 
  var B_name="Failed to identify the browser"; 
  if(u_agent.indexOf("Firefox")>-1){ 
      B_name="Firefox"; 
  }else if(u_agent.indexOf("Chrome")>-1){ 
      B_name="Chrome"; 
  }else if(u_agent.indexOf("MSIE")>-1&&u_agent.indexOf("Trident")>-1){ 
      B_name="IE(8-10)";  
  }
    document.write("B_name:"+B_name+"<br>");
    document.write("u_agent:"+u_agent+"<br>"); 
} 
```
运行结果：

![](/images/javascript-2-8-13-useragent-2.jpg)


## screen 对象

`screen` 对象用于获取用户的屏幕信息。

语法：
``` javascript
`window.screen` 属性
```
对象属性：

![](/images/javascript-2-8-14-screen.jpg)


## 屏幕分辨率的高和宽

`window.screen` 对象包含有关用户屏幕的信息。
1. `screen.height` 返回屏幕分辨率的高
2. `screen.width` 返回屏幕分辨率的宽
注意：
1. 单位以像素计。
2. `window.screen` 对象在编写时可以不使用 `window` 这个前缀。
我们来获取屏幕的高和宽，代码如下：
``` javascript
<script type="text/javascript">
  document.write( "屏幕宽度："+screen.width+"px<br />" );
  document.write( "屏幕高度："+screen.height+"px<br />" );
</script>
``` 


## 屏幕可用高和宽度

1. `screen.availWidth` 属性返回访问者屏幕的宽度，以像素计，减去界面特性，比如任务栏。
2. `screen.availHeight` 属性返回访问者屏幕的高度，以像素计，减去界面特性，比如任务栏。

注意：

不同系统的任务栏默认高度不一样，及任务栏的位置可在屏幕上下左右任何位置，所以有可能可用宽度和高度不一样。

我们来获取屏幕的可用高和宽度，代码如下：
``` javascript
<script type="text/javascript">
document.write("可用宽度：" + screen.availWidth);
document.write("可用高度：" + screen.availHeight);
</script>
```
注意：根据屏幕的不同显示值不同。


## 编程练习

制作一个跳转提示页面：

要求：

1. 如果打开该页面后，如果不做任何操作则5秒后自动跳转到一个新的地址，如慕课网主页。

2. 如果点击“返回”按钮则返回前一个页面。

效果:

![](/images/javascript-2-8-17-exercise-1.jpg)

注意: 在窗口中运行该程序时，该窗口一定要有历史浏览记录，否则"返回"无效果。

任务
第一步： 先编写好网页布局，如下:

![](/images/javascript-2-8-17-exercise-2.jpg)

第二步： 获取显示秒数的元素，通过定时器来更改秒数。

第三步： 通过window的location和history对象来控制网页的跳转。


``` html
<!DOCTYPE html>
<html>
 <head>
  <title>浏览器对象</title>  
  <meta http-equiv="Content-Type" content="text/html; charset=gkb"/>   
 </head>
 <body>
  <!--先编写好网页布局-->
  <p> 操作成功 </p>
  5秒后回到主页
  <type="text" onClick="b()">返回</input>
  
  <script type="text/javascript">  
   function jump() {
       window.open("www.imooc.com");
   }
   setInterval(jump, 5000);
   //获取显示秒数的元素，通过定时器来更改秒数。

   //通过window的location和history对象来控制网页的跳转。
   function b() {
       window.history.back();
   }
 </script> 
</body>
</html>
```

答案代码：
``` html
<!DOCTYPE html>
<html>
 <head>
  <title>浏览器对象</title>  
  <meta http-equiv="Content-Type" content="text/html; charset=gb2312"/>   
 </head>
 <body>
  <h4>操作成功</h4>
  <p>
     <b id="second">5</b>秒后回到主页<a href="javascript:goBack();">返回</a>  
  </p>

<script type="text/javascript">  
 
	var sec = document.getElementById("second");
	var i = 5;
	var timer = setInterval(function(){
		i--;
		sec.innerHTML = i;
		if(i==1){
			window.location.href =  "http://www.imooc.com/";
		}
	},1000);
	 
  function goBack(){ 
	window.history.go(-1);
  }  
  </script> 
 </body>
</html>

```

# DOM 对象，控制 HTML 元素 
## 认识 DOM
## getElementsByName() 方法
## getElementsByTagName() 方法
## 区别 getElementByID、getElementsByName、getElementsByTagName
## getAttribute() 方法
## setAttribute() 方法
## 节点属性
## 访问子节点 childNodes
## 访问子节点的# 第一和最后项
## 访问父节点 parentNode
## 访问兄弟节点
## 插入节点 appendChild()
## 插入节点 insertBefore()
## 删除节点 removeChild()
## 替换元素节点 replaceChild()
## 创建元素节点 createElement
## 创建文本节点 createTextNode
## 浏览器窗口可视区域大小
## 网页尺寸 scrollHeight
## 网页尺寸 offsetHeight
## 网页卷去的距离与偏移量
## 编程练习


# 编程挑战 
## 编程挑战