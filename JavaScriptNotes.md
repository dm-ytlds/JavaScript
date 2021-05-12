## JavaScript

简称JS。JS是一门事件驱动型的编程语言。依靠事件去驱动，然后执行对应的程序。在JS中有很多事件，比如：鼠标单击click。并且任何事件都会对应一个事件句柄，比如click的事件句柄叫做onclick。【！！：事件和事件句柄的区别是：事件句柄是在事件的单词前面添加一个on。】事件句柄是以HTML标签的属性存在的。

以onclick为例：

 1.  onclick="js代码"，执行原理是什么？

     页面打开的时候，js代码并不会执行，只是把这段js代码注册到按钮的click事件上了。等这个按钮发生click事件之后，注册在onclick后面dejs代码会被浏览器自动调用。

 2.  怎么使用js代码弹出消息框？

     在JS中有一个内置的对象叫做window，可以直接拿来使用，window代表的是浏览器对象。window对象有一个函数叫做alert，用法是：window.alert("消息"); 这样就可以弹窗了。“window.”可以省略。

HTML中有三种方式引入JS代码。参考html文件。

​	方式1：事件句柄后面写代码；

```html
<html>
<title>HTML中嵌入JS代码的第一种方式</title>
<body>
	<input type="Button" value="点我" onclick="alert('Js code')" />
</body>
</html>
```

​	方式2：脚本语句块；

```html

<!--注释方式1-->
<!--
	javascript可以在一个页面中出现多次；
	javascript可以放在HTML页面的各个地方。
-->
<html>

<head>
<title>HTML中嵌入JS代码的第二种方式</title>
</head>

<body>
	<script type="text/javascript">
	/*	注释方式2：用于代码块中
		暴露在脚本块当中的程序，在页面打开的时候执行，
		并且遵循自上而下的顺序依次逐行执行。
	*/
	window.alert("JS code");
	</script>
</body>
</html>
```

​	方式3：引入外部js文件进入脚本标签。

```html
<html>
<title>HTML中嵌入JS代码的第三种方式：引入外部独立的js文件</title>
<body>
	<!--在引入外部独立的js文件的时候，js文件中的代码会自动遵循自上而下的顺序依次逐行执行-->
	<script type="text/javascript" src="js/test.js">
	</script>
</body>
</html>
```

JavaScript是一种弱类型的编程语言。
JS中声明变量的方式：
	var 变量名;
在JS中，当一个变量没有手动赋值，系统会默认赋值undefined

JS中的函数不需要指定返回值类型。

语法格式：

```javascript
第一种格式：
	function 函数名(形式参数列表) {
		函数体;
	}
第二种方式：
	函数名 = function(形式参数列表) {
		函数体;
	}
```

NaN是一个具体存在的值，该值表示不是一个数字。

JS中不存在函数重载，同名函数会出现覆盖的情况，同名的只有最后一个函数才会起作用。

JS中的数据类型

​	虽然在声明变量的时候不用指定数据类型，但是在赋值的时候还是有类型的。

​	1.JS中数据类型有：原始类型和引用类型。

​		原始类型：Undefined, Number, String, Boolean, Null

​		引用类型：Object以及Object的子类。

​	2.ES规范（ECMAScript规范），在ES6之后，又基于以上的6中数据类型之外添加了一种新的s类型：Symbol

​	3.JS中有一个运算符叫做：typeof，这个运算符可以在程序的运行阶段动态的获取变量的数据类型。

​		typeof运算符的语法格式：
​			typeof 变量名

​		typeof运算符的运算结果是以下6个字符串之一：注意字符串全部都是小写。

​			"undefined" "number" "string" "boolean" "object" "function"

​		在JS中比较字符串是否相等只有 ==， 没有equal

​	4.数据类型

​		4.1 注意：var i;和var i = undefined 是一回事，而var = "undefined" 是string类型。

​		4.2 Number类型包括哪些值？

​			整数、小数、正数、负数、不是数字（NaN）、无穷大（Infinity）都属于Number类型。

​			！什么情况下会出现NaN？
​			运算结果本应该是一个数字，最后算完不是一个数字的时候，结果就会返回NaN。

​	isNaN函数： isNaN：is Not a Number 。

​		用法：isNaN(数据)，结果是true表示不是一个数字，结果是false表示是一个数字。

​	parseInt()：可以将字符串自动转换成数字，并且取整数位。

​	parseFloat()：可以将字符串自动转换成小数。

​	Math.ceil("数字")：向上取整。

​		JS中的布尔类型永远只有2个值：true和false。

​		在Boolean类型中有一个Boolean()函数。作用：将非布尔类型转换成布尔类型。

​		！！！对于JS，在判断语句的小括号中（if()），如果不是布尔类型，系统会自动调用Boolean()函数转换成布尔类型。

​		String是一个内置类，可以直接使用，String的父类是Object 。

​		"字符串a".indexof("字符串b");  // 字符串a中是否包含字符串b

​		考点：substr和substring的区别？

​			substr(startIndex, length);

​			substring(startIndex, endIndex); 不包含endIndex

​	Object类型

​			Object是所有类型的超类，自定义类型默认继承该类，

​			Object类包括哪些属性？

​				prototype（常用这个），作用：给类动态的扩展属性和函数。

​				constructor 属性。

​			Object类包括哪些函数？

​				toString(), valueOf(), toLocalString()

​		创建类：

​		语法格式：

```javascript
第一种格式：
	function 函数名(形式参数列表) {
		函数体;
	}
第二种方式：
	函数名 = function(形式参数列表) {
		函数体;
	}
创建类和函数的区别？
	调用的时候，用new 函数名()，就是当做一个类来处理；
如果直接函数名()，则是当做一个函数来使用。
```

