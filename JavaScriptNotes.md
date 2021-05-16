

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

​				<font color=#FF00>prototype（常用这个），作用：给类动态的扩展属性和函数。</font>

​				<font color=#FFFF00>例如：String.prototype.函数名=function(){ }; "任意字符串".函数名(); 就是说，给字符串类型扩展一个函数，那么任意的字符串都可以调用该函数。</font>

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

​	在JS中，有两个特殊的运算符：	
​		== ：等同运算符，只判断值是否相等；
​		=== ：全等运算符，既判断值是否相等，又判断数据类型是否相等。

​	null NaN undefined有什么区别？

​		首先，三者是不同的数据类型（null(oobject) NaN(number) undefined(undefined)）。

JS中的事件

​	常见的事件：

​		blur 失去焦点
​		focus 获得焦点

​		click 鼠标单击
​		dblclick 鼠标双击

​		keydown 鼠标按下
​		keyup 鼠标弹起

​		mousedown 鼠标按下
​		mouseover 鼠标经过
​		mousemove 鼠标移动
​		mouseout 鼠标离开
​		mouseup 鼠标弹起

​		reset 表单重置
​		ubmit 表单提交

​		change 下拉列表选中项改变，或文本框内容改变

​		load 页面加载完毕（整个HTML页面中所有的元素全部加载完毕之后发生。）

​		select 文本被选中

​	事件的注册

​		注册事件的第一种方式：
​			直接在标签中使用事件句柄

```html
<!--举例说明-->
<input type="button" value="JS" onclick="JS 代码" />
<!--对于当前程序来说，onclick中的JS代码被称为回调函数（别人调用）-->
```

​		注册事件的第二种方式：使用纯JS代码完成事件的注册。

```html
<input type="button" value="js01" id="mybtn1" />
<input type="button" value="js02" id="mybtn2" />

<script type="text/javascript">
    
    // 关于回调函数有两种写法：定义一个函数或者使用匿名函数的写法
    function do(){
        alert("abcd");
    }
    
    // 第一步：先获取按钮对象（document全部小写，内置对象，可以直接使用，document就代表整个HTML页面。）
    var btnobj1 = document.getElementById("mybtn1");
    // 第二步：给按钮对象的onclick属性赋值
    //btnobj.onclick = 回调函数; 注意：回调函数后面千万别加小括号。
    // 回调函数的第一种写法
    btnobj1.onclick = do;
    
    var btnobj2 = document.getElementById("mybtn2");
    // 回调函数的第二种写法
    btnobj2.onclick = function(){
        alert("acbdasfddg...");
    }

    
</script>
```

​	JS中代码的执行顺序

```html
onload 的用法：
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>onload的用法</title>
	</head>
	<body>
		<script type="text/javascript">
			// 用window.onload 调用load事件，等整个页面加载完毕该事件才会发生。
			// 页面加载过程中，将回调函数 a 注册给load事件
			// 页面加载完毕后，load事件执行回调函数 a
			// 回调函数a执行过程中，把b函数注册给了id="btn"的click事件
			// 当id="btn"的节点发生click事件之后，b函数被调用并执行
			window.onload = function(){  // 回调函数 a 
				document.getElementById("btn").onclick = function(){  // 回调函数 b
					alert("How to use JS' onload and onclick")
				};
				
			}
		</script>
		<input type="button" value="mybtn" id="btn"/>
	</body>
</html>

```

​	JS代码中设置节点的属性

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>JS中设置节点的属性</title>
	</head>
	<input type="text" id="mytext" />
	<input type="button" value="btn" id="mybtn" />
	<!--实现将文本框变成复选框-->
	<body>
		<script type="text/javascript">
			window.onload = function(){
				document.getElementById("mybtn").onclick = function(){
					var mytext = document.getElementById("mytext");
					mytext.type = "checkbox";
				}
			}
		</script>
	</body>
</html>
```

​	keydown事件的应用案例：捕捉回车键

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>JS代码捕捉回车键</title>
	</head>
	<body>
		<script type="text/javascript">
			// load事件：全部元素执行完成后才执行onload事件句柄中的代码
			window.onload = function(){
				// keydown事件：键盘按下事件，
				// 对于JS来说，键盘上每一个键都对应一个keyCode值，比如Enter的keyCode是13，Esc的keyCode是27
				// 注意：必须通过document.getElementById("mytext")来定位你要捕捉的是哪一个文本框。
				document.getElementById("password").onkeydown = function(event) {
					if(event.keyCode === 13) {
						alert("正在验证");
					}
				}
			}
		</script>
		<input type="text" id="username" />
         <br />
		<input type="password" id="password" />
	</body>
</html>

```

​	JS中的void运算符

​		将“javascript:void(0)”放在超链接的属性herf中时，该超链接不会跳转到任何地方。即表示没有路径可跳转。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>JS中void运算符</title>
	</head>
	<body>
		<a href="javascript:void(0)" onclick="window.alert('test void(0)')">点击该超链接，页面不会跳转</a>
	</body>
</html>
```

​	JS创建数组

​		语法格式：var 数组名=[];    // 数组中元素类型和元素个数随意。

​	数组的遍历：

```javascript
var arr = [1, 1.0, 'a', "abc", false];
// 方式1：
for(var i = 0; i < arr.length; i++) {
	alert(arr[i]);
}
// 方式2：for...in
for(var i in arr) {
    alert(arr[i]);
}
```

​	for.. in还可以用于遍历对象属性

​	with(){} 函数的用法

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>JS的控制语句</title>
	</head>
	<body>
		<script type="text/javascript">
			function User(username, password){
				this.username = username;
				this.password = password;
			}
			var user = new User("zs", 1233);
			// for...in的第二种用法：遍历对象的属性
			for(var attr in user) {
				alert(user[attr]);
			}
			
			// with(){}函数的用法:小括号中的参数如果放的是对象名，就会自动遍历对象的相关属性值
			with(user) {
				alert(username + ", " + password);
			}
		</script>
	</body>
</html>

```

JavaScript 包括三部分：

​	ECMAScript（核心基础语法（ES规范/ECMA-262标准））；

​	DOM：Document Object Model。（文档对象类型：对网页当中的节点进行增删改的过程）HTML文档被当成一棵DOM树来看待；

​	BOM：Browser Object Model。（浏览器对象模型）screen（关闭浏览器窗口、打开新的浏览器窗口）、history（后退、前进）、浏览器地址栏（location）上的地址等等，都是BOM编程。

DOM和BOM的区别和联系：

​	BOM的顶级对象是：window，DOM的顶级对象是：document 。也就是说BOM是包含DOM的。

DOM编程-innerHTML和innerText

​	innerHTML和innerText的区别？
​		相同点：都是设置元素内部的内容；
​		不同点：InnerHTML会把后面的内容当成HTML代码解释并执行，而innerText即使后面是一串代码，都只是当成文本来执行。

JS的DOM编程的正则表达式

​	正则表达式的作用？
​		主要用来字符串格式匹配方面。正则表达式实际上是一门独立的学科，所有的编程语言都可以用。

​	常见的正则表达式符号：

| 符号 |             描述             |
| :--: | :--------------------------: |
|  .   | 匹配除换行符以外得我任意字符 |
|  \w  | 匹配字母或数字或下划线或汉字 |
|  \s  |        匹配任意空白符        |
|  \d  |           匹配数字           |
|  \b  |     匹配单词的开始或结束     |
|  ^   |       匹配字符串的开始       |
|  $   |       匹配字符串的结束       |
| ...  |             ...              |

​	正则表达式的创建和使用

​		第一种创建方式：
​			var 变量名 = /正则表达式/ [flags];  

​		第二种创建方式：使用内置支持类RegExp
​			var 变量名 = new  RegExp("正则表达式", ["flags"]);

​		关于"flags"：
​			g: 表示全局匹配；
​			i: 忽略大小写；
​			m: 多行搜索。当前面是正则表达式的时候 m 不能使用。只有当前面是普通字符串的时候才可以用。

​		正则表达式的test()方法：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>DOM编程：正则表达式</title>
	</head>
	<body>
		<script type="text/javascript">
			// 案例：实现邮箱验证
			window.onload = function(){
				// 给按钮绑定click事件
				window.document.getElementById("btn").onclick = function(){
					var email = window.document.getElementById("email").value;
					// 正则表达式
					var regExp = /^([a-zA-Z]|[0-9])(\w|\-)+@[a-zA-Z0-9]+\.([a-zA-Z]{2,4})$/;
					var ok = regExp.test(email);
					if(!ok) {
						document.getElementById("emailError").innerText = "邮箱地址不合法";
						// 给文本框绑定focus事件
						window.document.getElementById("email").onfocus = function(){
							// 提示内容消失
							document.getElementById("emailError").innerText = "";
							// 邮箱格式错误，再次点击文本框，内容消失
							document.getElementById("email").onclick(this.value="");
						}	
					}else{
						document.getElementById("emailCurrent").innerText = "邮箱地址合法";
						window.document.getElementById("email").onfocus = function(){
							document.getElementById("emailCurrent").innerText = "";
                              // 邮箱格式正确，再次点击文本框，内容全选
							document.getElementById("email").onclick(this.select());
						}
					}	
				}
			}
		</script>
		<input type="text" id="email" />
		<span id="emailError" style="color: red; font-size: 0.75rem;"></span>
		<span id="emailCurrent" style="color: green; font-size: 0.75rem;"></span>
		<br />
		<input type="button" id="btn" value="验证邮箱"/>
	</body>
</html>
```

​	字符串的trim()方法：去除字符串的空白字符（空格）；
​			"字符串".trim();

​	如果浏览器版本不支持trim()方法，可以用prototype对String类扩展一个全新的trim()函数。

```javascript
String.prototype.trim = function() {
    // 去除当前字符串的前后空白
    // 在当前的方法中this代表的就是当前字符串
    return this.replace(/^\s+/, "").repalce(/\s+$/,"");
}
```

JSON：JavaScript Object Notation 。数据交换格式。

​	JSON主要的作用是：一种标准的轻量级的数据交换格式。（目前很流行）

​	JSON也被称为无类型数据对象。

​		体积小、易解析。（区别于另一种文件存储形式XML。XML文件体积大，解析麻烦。）

```json
// 创建JSON对象
var JSON对象名 = {
    "属性名1" : "属性值1",
    "属性名2" : "属性值2",
    "属性名3" : "属性值3",
    ...
};
// 访问JSON对象的属性
alert(JSON对象名.属性名, ... );

--------------------------------------------
// JSON数组
var 数组名 = [{"属性名" : "属性值", ...},{}, ... {}];
// 遍历JSON数组
for(var i = 0; i < 数组名.length; i++) {
    var json = 数组名[i];
	alert(json.属性名, ... );
}
```

​	JSON对象可以在其中嵌套（在属性中）：JSON对象、数组。

​	window.eval()函数的作用：将字符串当做一段JS代码解释并执行。

​	java连接数据库，查询数据之后，将数据在java程序中拼接成JSON格式的“字符串”，将JSON格式的字符串响应到浏览器。也就是说，java响应到浏览器上的仅仅只是一个“JSON格式的字符串”，还不是一个JSON对象，可以使用eval函数将JSON格式的字符串转换成JSON对象。