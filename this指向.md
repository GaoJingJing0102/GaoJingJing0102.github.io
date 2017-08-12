# JavaScript -- this指向问题  

#### 函数中的this  
  
**函数中的this默认指向window，当函数有所有者时，this指向所有者**  

	
	function fn(){  
		var name = "hello";  
		console.log(this.name);//undefined  
		console.log(this);//window  
	}  
	fn(); 

#### 方法中的this  

**this指向对象**  

	var obj = {  
		name:"hello",
		fn:function(){  
			console.log(this.name);//hello  
		}  
	}  
	obj.fn();  
	此时的this指向的是obj对象，obj对象调用了fn  

#### 构造函数中的this  

**this指向new出来的实例化对象,new可以改变this的指向**    
	
	function Fn(){  
		this.name = "hello";  
	}  
	var a = new Fn();  
	console.log(a.name);//hello    
	
#### call和apply可以改变this指向  

**	第一个参数都是this指向的对象  区别：call方法第一个参数之后的参数不限制类型和个数  apply方法接受的第二个参数只能是数组**   
		function fn(){  		console.log(this.name);   	}  	var obj = {  		name:"hello"  	}  	fn.call(obj);//输出4，this指向obj对象  
#### 定时器中的this  
**定时器中的this始终指向window**
