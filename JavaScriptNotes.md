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

