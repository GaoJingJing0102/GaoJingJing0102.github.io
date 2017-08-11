# JavaScript--数组、字符串方法 
## 数组  
#### join() ` 数组转化为字符串 `  
** 参数问题 **  
如果不写参数，默认以逗号分割，join()可以接受参数，表示以这个指定的参数进行字符串分割  
	
	var arr = [1,2,3,4];
	console.log(arr.join());//"1,2,3,4"
	console.log(arr.join(" "));//"1 2 3 4"  
#### reverse() ` 数组逆序  会修改原数组 `  
** 参数问题 **   
没有参数  
	
	var arr1 = ["nihao","shijie","biancheng"];
	
	console.log(arr1.reverse());//["biancheng", "shijie", "nihao"]
	
	console.log(arr1);//["biancheng", "shijie", "nihao"]  
#### sort() ` 将数组排序  会修改原数组 `  
** 参数问题 **  
sort()方法如果想按照从小到大或从大到小的方式排序，需要我们传递参数，参数的形式是函数，如果不传参数会默认按照Unicode编码进行排序
		
	var arr2 = [1,8,5,10,6,28];
	console.log(arr2.sort());// [1, 10, 28, 5, 6, 8]
	console.log(arr2);// [1, 10, 28, 5, 6, 8]
	console.log(arr2.sort(asce));// [1, 5, 6, 8, 10, 28]
	console.log(arr2.sort(desc));// [28, 10, 8, 6, 5, 1]
	// 升序
	function asce (a,b) {
		return a-b;
	}
	// 降序
	function desc(a,b){
		return b-a;
	}  
#### concat() ` 将数组进行合并  不会修改原数组 `  
** 参数问题 **   
参数可以是数字，也可以是数组，如果是一维数组的话，会把合并数组拉伸，跟原数组合并为同一个数组；但是如果是二维数组或多维数组的话，只会将合并数组的第一层拉伸合并，保留内层的数组  
	
	var arr3 = [1,2,3];
	console.log(arr3.concat([4,5]));//[1,2,3,4,5]
	console.log(arr3.concat([4,[1,5]]));//[1,2,3,4,[1,5]]  
#### slice() ` 返回数组的某一部分 不会改变原数组 `  
 ** 参数问题 **    
 两个参数：1.开始截取的位置；2.截取到的位置，前闭后开。当只有一个参数时，这个参数表示开始截取的下标位置，一直截取到数组的最后一项
 	
 	var arr = ["123","456","789","1","2","3"];
	console.log(arr.slice(2,5));//["789", "1", "2"]
	console.log(arr.slice(1));//["456", "789", "1", "2", "3"]  
#### splice() ` 数组拼接  会改变原数组 `  
 ** 参数问题 **   
 有三个参数：1.表示插入的下标位置；2.表示删除多少项；3.表示插入的内容  
 	
 	var arr = ["this","is","a","very","boring","thing"];
	arr.splice(4,1,"interesting");
	console.log(arr);//["this", "is", "a", "very", "interesting", "thing"]
	arr.splice(6,0,"ahha");
	console.log(arr);//["this", "is", "a", "very", "interesting", "thing", "ahha"]  
#### pop() ` 移除数组中的最后一个元素并返回该元素 会改变原数组 `  
 ** 参数问题 **  
 没有参数  
 
 	var arr = [1,2,3,4,5];
	console.log(arr.pop());//5
	console.log(arr);//[1, 2, 3, 4]

#### shift() ` 移除数组中的第一个元素并返回该元素 会改变原数组 `  
 ** 参数问题 **   
 没有参数  
 
 	var arr = [1,2,3,4,5];
 	console.log(arr.shift());//1
	console.log(arr);//[2, 3, 4]   
#### push() ` 往数组的最后添加一项内容，返回的是新数组的长度  会修改原数组 `  
 ** 参数问题 **   
 有参数  
 	
 	var arr = ["this","is","a","beauty"];
	console.log(arr.push("girl"));//5
	console.log(arr);// ["this", "is", "a", "beauty", "girl"]  
#### unshift() ` 往数组的第一项添加内容，返回的是新数组的长度 会修改原数组 `  
 ** 参数问题 **   
 有参数    
 	
 	var arr = [1,2,3,4];
	console.log(arr.unshift(0));//5
	console.log(arr);//[0, 1, 2, 3, 4]  
#### indexOf() ` 检测数组是否包含某一项内容，如果有，返回下标，如果没有，返回-1 `  
 ** 参数问题 **    
 参数为要检测的内容  
 	
 	var arr = ["张三","李四"];
	console.log(arr.indexOf("哈哈"));//-1  
#### lastIndexOf() ` 和indexOf()类似，从后往前查找 `  

****
## 新增数组方法  
#### forEach() ` 遍历数组 `  
 ** 参数问题 **    
 参数是匿名函数，匿名函数接受1-3个形参：  
1.表示数组的每一项内容  
2.表示每一项内容所对应的下标  
3.表示原数组  
	
	var arr = ["haha","hehe","xixi"];
	arr.forEach(function(x,y,z){
		console.log(x,y,z);
	});
	//haha 0 (3) ["haha", "hehe", "xixi"]  
	hehe 1 (3) ["haha", "hehe", "xixi"]
	xixi 2 (3) ["haha", "hehe", "xixi"]  
#### map() ` 指“映射”，对数组中的每一项运行给定函数，返回每次函数调用的结果组成的数组。 `  
 ** 参数问题 **   
 参数接受一个匿名函数，匿名函数可以传递两个形参  
1.原数组里的每一项内容  
2.原数组里每一项内容对应的下标  
	
	var arr = [1, 2, 3, 4, 5];	var arr2 = arr.map(function(item){	return item*item;	});	console.log(arr2); //[1, 4, 9, 16, 25]  
#### filter() ` “过滤”功能，数组中的每一项运行给定函数，返回满足过滤条件组成的数组。filter() 不会对空数组进行检测 `  

	var arr = [11,2,33,5,7,24];    function fn(x){        return x > 10;    } 	console.log(arr.filter(fn)); //[11,33 24]  
#### every() ` 判断数组中每一项都是否满足条件，只有所有项都满足条件，才会返回true。 `  
		var arr = [1, 2, 3, 4, 5];	var arr2 = arr.every(function(x) {	return x < 10;	});	console.log(arr2); //true	var arr3 = arr.every(function(x) {	return x < 3;	});	console.log(arr3); // false  
#### some() ` 判断数组中是否存在满足条件的项，只要有一项满足条件，就会返回true。 `  

	var arr = [1, 2, 3, 4, 5];	var arr2 = arr.some(function(x) {	return x < 3;	});	console.log(arr2); //true	var arr3 = arr.some(function(x) {	return x < 1;	});	console.log(arr3); // false****
****## 字符串方法  
#### indexOf() ` 查找字符串出现的位置返回该字符串的下标，如果查询的字符在对应的字符串里找不到，则返回-1  `   ** 参数问题 **    参数可以传递两个：  
	第一个参数：要查找的字符串；  
	第二个参数（可选）：开始查找的下标位置  
		
	var str = "hello world!";
	console.log(str.indexOf("l",6));//9  
#### lastIndexof() ` 跟indexOf（）类似，在一个字符串中的指定位置从后向前搜索。`   
	var str = "hello world!";
	console.log(str.lastIndexOf("ll"));//2 
 ** 注意：整体查找的话，无论是从前往后找还是从后往前找，返回的都是第一个字母出现的下标 **   
#### slice() ` 截取字符串的某个部分  该方法不会改变原来的字符串 `  
 ** 参数问题 **   
 所有的截取字符串的操作，截取的范围都是前闭后开【0，5）即第二个参数 - 第一个参数 = 截取字符串长度  
如果只传递一个参数，那这个参数会视为开始截取的下标，默认截取到字符串的最后一位  
如果一个参数都没有，默认截取整个字符串  
参数：两个    
第一个 表示开始截取的下标位置  
第二个 表示截取结束的下标位置  
	
	var str = "hello world!";
	console.log(str.slice(0,5));//hello
	console.log(str.slice(2));//llo world!
	console.log(str.slice());//hello world!  
#### substring() ` 截取字符串 不会改变原字符串 `  
 ** 参数问题 **  
 参数：两个    
第一个 表示开始截取的下标位置  
第二个 表示截取结束的下标位置  
如果只传递一个参数，那这个参数会视为开始截取的下标，默认截取到字符串的最后一位，如果一个参数都没有，默认截取整个字符串  
	
	var str = "hello world!";
	console.log(str.substring(0,5));//hello
	console.log(str.substring(9,1));//ello wor
	console.log(str);//hello world!  
 ** 注意:substring()方法会自动比较两个参数的大小，如果我们给的第一个参数大于第二个的话，那该方法会自动进行参数位置的调整 **   
#### split() ` 把字符串分割成字符串数组 `   
 ** 参数问题 **  
如果没有参数，那原字符串就是转化数组的唯一一项内容  
如果有一个参数，那这个参数就是字符串分割的依据  
如果有第二个参数，那第二个参数表示数组的长度
 