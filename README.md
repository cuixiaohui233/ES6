## ES6

### 兼容性

> ES5 [http://kangax.github.io/compat-table/es5/](http://kangax.github.io/compat-table/es5/)

> ES6 [http://kangax.github.io/compat-table/es6/](http://kangax.github.io/compat-table/es6/)

### 编译、转换

		1.在线转换(不可取)		依赖browser.js
		
		2.提前编译

### 变量

	  	var     重复声明、函数级
	  	
	  	let     不能重复声明、块级、变量
	  	
	  	const   不能重复声明、块级、常量

### 函数——箭头函数

		1.如果只有一个参数，()可以省
		
		2.如果只有一个return，{}可以省

### 函数的参数

		1.参数扩展/数组展开
		
		2.默认参数
		
		参数扩展：
		
			1.收集参数
			
				function show(a, b, ...args){
					console.log(args);// [8, 9, 20, 21, 90]
				}
				show(12, 15, 8, 9, 20, 21, 90);
			    
				function show(a, b, ...args){}
				*Rest Parameter(剩余参数)必须是最后一个
				
			2.展开数组
			
				let arr=[1,2,3];
				function show(a, b, c){
				  	alert(a);
				  	alert(b);
				  	alert(c);
				}
				show(...arr);
			    
			  	...arr		=>		1,2,3
			  	*展开后的效果，跟数组的内容一致
		  	
		默认参数
		
			function show(a, b=5, c=12){
			  	console.log(a, b, c);//99,5,12
			}
			show(99);
			
			有实参走实参，无实参走默认

### 解构赋值

		1.左右两边结构必须一样
		
		2.右边必须是个东西
		
		3.声明和赋值不能分开(必须在一句话里完成)
		
		let [a,b,c]=[12,5,8];
		
		let {a,b,c}={a: 12, b: 5, c: 8};

### 字符串

		1.多了两个新方法
		
		  	startsWith:
		  		判断字符串中是不是以某个字符或者字符片段开始
			
			endsWith
				判断字符串中是不是以某个字符或者字符片段结束
		
		2.字符串模板(` `)
		
			直接把东西塞到字符串里面      ${东西}
			
			可以折行

### 面向对象的继承

```
	<!DOCTYPE html>
	<html>
		<head>
			<meta charset="UTF-8">
			<title></title>
		</head>
		<body>
			<script type="text/javascript">
				/*
					 ES6 面向对象的继承
					 super 父类：执行父类的构造函数
					 
				*/
				class User{
					constructor(name,pass){
						this.name = name;
						this.pass = pass;
					}
					showName(){
						alert(this.name)
					}
					showPass(){
						alert(this.pass)
					}
				}
	//			let u1 = new User('zyh',123456)
	//			u1.showName()
	//			u1.showPass()
				
				//继承
				//VipUser扩展自User
				class VipUser extends User{
					constructor(name,pass,level){//子类
						super(name,pass)//父类：执行父类的构造函数
						this.level = level;
					}
					showLevel(){
						alert(this.level)
					}
				}
				let v1 = new VipUser('zyh',123456,1)
				v1.showName()
				v1.showPass()
				v1.showLevel()
			</script>
		</body>
	</html>
```

### 面向对象应用——React

		React：
		
			1.组件化——class
			
			2.JSX
		
		JSX == babel == browser.js
		
		JSX   JS扩展版

### json
		1.JSON对象
		
		  	JSON.stringify		对象转JSON字符串
		  	
		  	JSON.parse			JSON字符串转对象
		
		2.简写
		
			名字跟值(key和value)一样的	留一个就行
			
			方法			: function一块删
		    
				show: function (){...}		=>		show(){...}
		
		json的标准写法：
		
			1.只能用双引号
			
			2.所有的名字都必须用引号包起来
		
		{a: 12, b: 5}       	×
		
		{"a": 12, "b": 5}   	√
		
		{a: 'abc', b: 5}    	×
		
		{"a": "abc", "b": 5}	√
