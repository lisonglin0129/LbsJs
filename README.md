## 2019年11月17日 V2.0

本次更新包含了一个安全更新，建议更新

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

该版本主要包含了一个移动端模板引擎加密安全更新。

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
callback ：该参数是function类型回调函数，
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










