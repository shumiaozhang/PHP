#  caller callee

## callee

​	 是argument对象的一个属性，它返回正在执行的当前函数本身的引用，注意：callee只有在函数执行时才有效。

1. 用来指向当前指向的函数也就是函数本身。

```js
 	function fun() {
  		console.log(arguments.callee);
	}
	fun();
	//返回结果为
	ƒ fun() {
		console.log(arguments.callee);
	}

```



2 .它有一个length属性，可以表示形参的个数。

```javascript
// ①
 	function fun (fun1, fun2){
	 if(arguments.length===arguments.callee.length){
		console.log("参数相等");
	 }else {
	 	console.log("参数不相等");
 		}
	}
	 fun(1, 1);   //参数相等

	 ② function fn(a, b, c) {
    // 实参长度为 2
	     console.log(arguments.length);  //2
   // 形参长度为 3
	     console.log(arguments.callee.length); //3
	 }
	 fn(0, 1);

```



3. 递归。

​		

```javascript
    function fn(num) {
         if(num <= 1) {
            return 1;
         }else {
               return num * fn(num - 1);
        }
     }
     fn(5);  //54321=120

```

```javascript
//改  为避免函数名修改导致函数内部报错，可以改成一下写法

		function fn(num) {
		    if(num <= 1) {
		        return 1;
		    }else {
		        return num * arguments.callee(num - 1);
		    }
		}

		fn(5);  //54321=120

```


​		

## caller  

​	caller 返回一个调用当前函数的引用（caller就是给你打电话的人，谁给你打电话，谁就调用了你），在浏览器中，如果调用当前函数的是window，则返回null。

​		

```javascript
        function fun1 (){
             console.log(fun1.caller);
         }
         function fun2(){
             	fun1();
         }
         fun1(); //null
         fun2();

          // ƒ fun2(){
          //   fun1();
          // }

```

​		

```javascript
 function fn() {
			console.log(fn.caller);
 }
 function fun() {
   fn();
  }
 fun();

//结果为
    //f fun() {
    //   fn();
    //  }

```

