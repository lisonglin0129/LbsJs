## 2019年11月17日 V2.0

该版本主要包含了一个移动端模板引擎加密，建议更新

- 改进DEBUG输出模式
- 模板自动加密
- 新加了外部异步加载模板
- 改进动态加载Js
- 身份证认证方法

* assign支持加密
* 异步加载模板
* 改进闭包的参数
* 新加了HTML5动画特性
* 修正IE下不兼容问题
* 修复移动端像素转换问题
* 新加了模板下动态加载Css/JavaScript

## 2019年11月17日 V2.0



* 支持调试模式
* 改进Log类


## 开始使用
### 引入文件：
```html
	<script src="js/lbs.min.js"></script>
```	
### 通过Lbs.get.Id来获取html元素dom

`
函数原型 (domElement) Lbs.get.Id(String dom, callback)

dom ：为div的id为字符串类型

callback ：该参数是function类型回调函数

如果该参数是一个函数，当传入的节点被浏览器渲染完后会调用该函数并向该函数传入
当前加载完后的dom节点对象`

## 使用例子

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>libJs</title>
		<script src="js/lbs.min.js">Hello This LbsJs</script>
	</head>
	<body>
	  <script>
	        //--通过第二个参数来获取未加载的dom对象达到实时监控该dom的事件
			lbs.get.Id("test",function(obj){
				alert("dom信息为"+obj.innerHTML);
			});
	  </script>
	  <div id="test"></div>
	  <script>
			var divDom = lbs.get.Id("test");
			alert(divDom.innerHTML);
	  </script>
	</body>
</html>
```
### 通过Lbs.get.TagName来获取html多个元素

函数原型 (Array domElement) Lbs.get.Tag(String dom,String TagName)

dom ：为div的id为字符串类型

TagName ：该参数是该节点的名称

`
该函数是通过html标签来获取指定的节点对象
`
## 使用例子

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>libJs</title>
		<script src="js/lbs.min.js">Hello This LbsJs</script>
	</head>
	<body>
	  <ul id="test">
		<li>1</li>
		<li>2</li>
		<li>3</li>
		<li>4</li>
	  </ul>
	  <script>
			var divDom = lbs.get.Tag("test","li");
			var length = divDom.length;
			alert("当前元素下面的li个数为"+);
			for(var i=0; i<length; i=-~i) {
			   (function(index){
					divDom[i].addEventListener("click",(event)=>{
						alert("你点击了第"+index+"个li标签,li内容为"+this.innerHTML);
					},false);		
			   })(-~i);
			}
	  </script>
	</body>
</html>
```

### 通过Lbs.get.Name来获取input至

函数原型 (Array domElement) Lbs.get.Name(String Name)

Name 表单的 name

`
该函数会返回当前html中所有name相同的节点
`

## 使用例子

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>libJs</title>
		<script src="js/lbs.min.js">Hello This LbsJs</script>
	</head>
	<body>
	   <from id="from">
		 <input type="text" name="test" value="">
		 <button id="getText">点击我获取输入框里面的内容</button>
	   </from>
	  <script>
			lbs.get.Id("getText").onclick = function(){
				alert(lbs.get.Name("test")[0].value);
				lbs.get.Name("test")[0].value = "这里可以设置一个值";
			}
	  </script>
	</body>
</html>
```

### 通过Lbs.get.Attr 来获取自定义属性值

函数原型 String Lbs.get.Attr(String id, String AttrKey)


id ：为div的id为字符串类型

AttrKey ：自定义属性值

`
该函数会返回当前html中指定的元素自定义的值
`

## 使用例子

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>libJs</title>
		<script src="js/lbs.min.js">Hello This LbsJs</script>
	</head>
	<body>
	  <div id="test" use="这个是自定义值"></div>
	  <script>
			var val = lbs.get.Attr(lbs.get.Id("test"), "use");
			alert("div自定义值为"+val)；
	  </script>
	</body>
</html>
```

### 通过Lbs.setCookie 来设置Cookie

函数原型 String Lbs.setCookie(String name, String value)

name ： 存储的Key

value ：值

`
该函数设置浏览器的Cookie，当设置了Cookie后可以通过 Lbs.getCookie(String name)
来获取存储的值需要用户浏览器开启Cookie
`
函数原型 String Lbs.getCookie(String name)

name ： 存储的Key

`
该函数获取设置的Cookie值，如果存在则返回存储的Cookie值，如果不存在则返回null
`

### 通过lbs.string.toHex 来加密字符串，lbs.string.hextoString解密

函数原型  String lbs.string.toHex(String str)

函数原型  String lbs.string.hextoString(String str)

## 使用例子

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>libJs</title>
		<script src="js/lbs.min.js">Hello This LbsJs</script>
	</head>
	<body>
	  <script>
			var  str = "hello !!!";
			var encode = lbs.string.toHex(str);
			alert(str);
			alert("加密后的内容"+encode)；
			alert("解密"+lbs.string.hextoString(encode))；
	  </script>
	</body>
</html>
```

### 通过lbs.string.base64encode 来加编码 lbs.string.base64decode来解码

函数原型  String lbs.string.base64encode(String str)

函数原型  String lbs.string.base64decode(String str)

## 使用例子

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>libJs</title>
		<script src="js/lbs.min.js">Hello This LbsJs</script>
	</head>
	<body>
	  <script>
			var  str = "hello !!!";
			var encode = lbs.string.base64encode(str);
			alert(str);
			alert("加密后的内容"+encode)；
			alert("解密"+lbs.string.base64decode(encode))；
	  </script>
	</body>
</html>
```

### 通过Lbs.Server 来请求服务器获取数据

`
函数原型   lbs.Server(Json Object)

Object.type  为String类型表示请求方式可以为get或则post，默认get

Object.url   为String类型表示请求服务器的地址，必须传

Object.data  为Object类型表示请求服务器Api的数据

Object.success  为Object类型表示请求服务器成功后返回的数据
`

## 使用例子

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>libJs</title>
		<script src="js/lbs.min.js">Hello This LbsJs</script>
	</head>
	<body>
	  <script>
			var dat = new Object();
			dat.username = "aaaaaaaa";		
			lbs.Server({
			   type:"post",
			   url:"要请求服务器的地址",
			   data:dat,
			   success:function(e){
					alert(e);
			   }
			});
	  </script>
	</body>
</html>
```

### lbs的模板引擎使用

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>标题</title>
		<script src="js/lbs.min.js"></script>
		<script>
			function us(data){
			    return data;
			}
		</script>
	</head>
	<body>
			<main id="lbs"></main>
			<main id="lbs2"></main>
			<main id="lbs4"></main>
			<main id="lbs5"></main>
			<main id="lbs6"></main>
		    <main id="lbs7"></main>
			<script id="template" type="text/html">
				   <h1>这是一个js模板</h1>
			</script>
			<!--例子2-->
			<script id="template2" type="text/html">
				<s:"hello world"> 
			  <p><s:"你好这是动态设置现在时间是:"><span id="times"></span></p>
				<s:setInterval(function(){ var myDate = new Date();  lbs.get.Id("times").innerHTML=myDate.toLocaleTimeString(); },100);>
				<s:for(var i = 0; i<5; i++){>
					<s:if(i==3){>
					  <h2 class="x<s:i>">这是第三行</h2>
				  <s:}else{>
				    <h2>这是第<s:i>行i*i=<s:i*i></h2>
					<s:}>
				<s:}>
				你好,我叫<s:datas.name>诞生了
			</script>
			<!--动态引入css/js-->
			<script id="template3" type="text/html">
				 你好，<s:us("我是自定义函数")>。。。。。
				 @<link href="css/css.css">
				 @<meta name="viewport" content="width=device-width,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no">
				 @<script src="js/test.js"></script>
			</script>
			<!--使用Lbs_lin编辑器可以对Js加密编译-->
			<script id="template4" type="text/html">
				  43,67,6B,4A,43,51,6B,67,49,43,59,6A,4D,6A,41,7A,4D,6A,41,37,4A,69,4D,79,4D,6A,6B,77,4F,54,73,6D,49,7A,49,31,4D,54,41,31,4F,79,59,6A,4D,6A,59,78,4E,54,6B,37,4A,69,4D,79,4D,54,45,31,4D,6A,73,6D,49,7A,49,7A,4E,44,6B,30,4F,79,59,6A,4D,7A,41,7A,4E,44,41,37,43,67,6B,4A,43,51,3D,3D
			</script>
			
			<script id="template7" type="text/html">
					<s:for(var j=0; j<13; j++){>
						  <s:for(var k=0; k<j; k++) {>
						     <p><s:k></p>
						  	 <p>双重循环<s:Math.sin(k)/Math.cos(j)></p>
						  <s:}>
				     <s:}>
			</script>
			<script id="template7" type="text/html">
					<s:for(var j=0; j<datas.length; j++){>
						  <s:if(datas[j].name == "LBS框架"){>
								<p class="x3"><s:datas[j].name></p>
						  <s:}else{>
							    <p><s:datas[j].name></p>
						  <s:}>
				     <s:}>
			</script>
			
			<script>
				  var test = lbs.assign("template",{});
				  console.log(test.context);
				  var test2 = lbs.assign("template2",{"name":"LBS框架"});
				  lbs.display("lbs",test2);
				  var test3 = lbs.assign("template3",{});
				  lbs.display("lbs2",test3);
				  var test4 =  lbs.assign("template4",{},false,"hash");
				  lbs.display("lbs4",test4);
				  //--实战
				  {
				  	//--定义一个数据集合
				     var data = [
				     		{"name":"李四"},
				     	  {"name":"张三"},
				     	  {"name":"LBS框架"},
				     	  {"name":"王二"}
				     ]
				      var test7 =  lbs.assign("template7",data);
				      lbs.display("lbs7",test7);
				  } 
				  var test7 =  lbs.assign("template4",{},false,"hash");
				  //--这种方式请开启http模式
				  //--第三个参数为true则第一个参数传的是外部文件模板文件后缀以.lin结尾,第四个参数则是回调模板
				  lbs.assign("template/test",{},function(tenplate){
				      lbs.display("lbs6",tenplate);
				  });
			</script>
	</body>
</html>
```

### 通过Lbs.log 来输出调试信息

lbs.log()

 ` 
 使用?debug=true 来开启debug
  
 <script src="js/lbs.min.js?debug=true">Hello This LbsJs</script>
 `
## 使用例子

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>libJs</title>
		<script src="js/lbs.min.js?debug=true">Hello This LbsJs</script>
	</head>
	<body>
	  <script>
			lbs.d("输出DEBUG");
			lbs.d("参数一","参数二","参数三");
	  </script>
	</body>
</html>
```

