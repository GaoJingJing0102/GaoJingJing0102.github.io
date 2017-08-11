# JavaScript 
### 变量  
##### 1.全局变量
定义：在函数外部定义的变量以及一些在函数内部没有var关键字的变量  
##### 2.局部变量  
定义：在函数内部，用var关键字定义的变量叫局部变量  
##### 两者区别： 

全局变量在整个js代码中都可以访问；局部变量只能在函数内部访问 
 
注意：` 在函数内部可以访问到全局变量，但是在函数外部访问不到局部变量函数的返回值跟局部变量是两种不同的概念，不要混淆  `  
##### 变量命名规范：  
1.由数字、字母、下划线及美元符组成，第一个字符不能是数字  2.驼峰命名法 第二个单词及以后单词首字母大写  3.避免和系统关键字重复  4.区分大小写  
***  
### 数据类型  
#### 基本数据类型 
** typeof关键字检测数据类型 **  
* number 数字类型(NaN和数字)   ` isNaN检测是不是非数  如果是返回true,不是返回false `
* string 字符串类型（用单引号或双引号包裹的内容都属于字符串 包括数字）
* boolean 布尔类型 （有两个布尔值 true false）
* undefined 未定义的类型或者定义了没有初始值的类型  
* null 空对象类型    
#### 复杂数据类型  
* 数组  var arr = new Array();/var arr = [];
* 对象 object  
#### 数据类型转换  
##### 显示转换  
1. Number() 转换为数字类型 NaN not a number 不是一个数字 数字类型的一种 它与任何值都不相等，包括它自己  
2. String() 转换为字符串类型  
3. Boolean() 非0即为真  
4. parseInt() (取整) parseFloat()（取小数）  强制转换为数字类型  从左到右进行数字的提取，遇到非数字返回  	如果最开始就提取不到数字，返回NaN    
** 重点记忆 **  
	console.log(Number(str));//NaN 
	console.log(NaN == NaN);//false
	console.log(Number(true));//1
	console.log(Number(false));//0
	console.log(Number(undefined));//NaN
	console.log(Number(null));//0
	console.log(parseInt(true));//NaN
	console.log(parseInt(12.5567));//12
	console.log(parseInt("ab123cd"));//NaN
##### 隐式转换  
1. 数字 + 字符串 得到字符串  
2. '+' 字符串  得到数字类型   +号相当于取正数  
### 函数  
##### 命名函数  
function fnName(){}  

** 分类 **   
	
	1.无参数无返回值  
	2.无参数有返回值  
	3.有参数无返回值  
	4.有参数有返回值
##### 匿名函数  
没有函数名的函数 function(){} 
 
** 调用方式 **  

	1.把匿名函数赋值给元素的某个事件，事件触发，执行函数	btn.onclick = function(){}  	2.把匿名函数赋值给某个变量，变量名加小括号执行函数	var fn = function(){		alert(1);	}	fn();  
	3.匿名函数的自执行  把函数整体放到一个小括号内，后面加小括号执行	(function(){		console.log("匿名函数自执行");	})()##### 函数声明提升  
` 浏览器在读取我们代码的时候会先把变量名和函数名抓取到，然后在当前作用域的最顶层进行声明 `  
### 分支  
##### 分支语句  
1. if 如果...就...  
	if(条件){  
       //语句  
	}  
2. if...else... 如果...就...否则...  
	if(条件){  
		//语句1  
	}else{  
		//语句2  
	}  
3. if…else if… 如果…就...否则如果…就…  
	if (条件1) {  
    // 语句1  
    } else if (条件2) {  
    // 语句2  
} else {   
    // 语句3  
}   

##### 多分支语句    
switch...case  
switch (条件) {case 情况1:语句;break;case 情况2:语句;break;case 情况2:语句;break;default:语句;}  

** 注意事项 **  

	1.switch语句中的break表示结束当前的情况, 如果当前case中没有break, 会跳入下一个case继续执行, 直到找到break退出      
	2.根据对应条件可以执行case, 条件以外的判断会进入default执行
	3.在js中, switch和case的值可以是常量/变量/表达式  
### 循环语句  
##### for循环  
for(循环变量初始化;循环条件;循环变量变化){循环语句;}  
	
	for(var i = 0; i < 10; i++){
		循环语句;
	}  
#### while循环  
while(循环条件){循环变量变化；循环语句；}  
	
	var i = 0;
	while(i <= 10){
		console.log(i);
		i++;
	}  
** 适合未知次数的循环 **  
#### do...while循环  
do{循环语句；循环变量变化}while(循环条件)  
	
	var i = 1;
	do{
		console.log(i);
		i++;
	}while(i < 10)  
#### do...while循环和while循环的区别  
** while循环是只有满足循环条件的前提下，才会执行循环语句，不满足不执行 **  
** do...while循环，会先执行一遍do里面的内容，然后再判断循环条件是否满足，如果满足继续执行，如果不满足则终止 **  
#### 循环控制  
break语句会立即退出本层循环, 循环终止.  
continue语句会立即跳过本次循环, 循环继续.  
	
	
	for(var i=0;i<10;i++){
		// 当i=3时，终止循环
		if(i == 3){
			break;//终止循环
		}
		console.log(i);
	}

	for(var i=0;i<10;i++){
		// 当i=3和5时，不打印，继续下一个
		if(i == 3 || i == 5){
			continue;//跳过本次循环
		}
		console.log(i);
	}  


  
