# javascript

### js能干什么（生机活力、强大）

1、进行数据验证（是否符合格式）

2、操作dom元素：内容、样式、属性

3、动态的创建、删除元素

4、动画

5、cookie（）、本地存储

6、ajax（动态获取数据）

....

# js组成

### ECMAScript

> 基础语法：变量、数据类型、运算符、代码执行流程、函数、对象

### BOM（browser object model）

> 地址（url）、历史记录、DOM、屏幕、

### DOM（document object model）

> 节点、

## 引入方式

1、嵌入式：通过script标签写到任意位置

​	弹出警示窗口：alert（1）;/alert（‘张三’）;/alert（“a”）;

​	控制台输出:console.log（1）;/console.log（'张三'）;/console.log（“a”）;

​	写在页面：document.write（1）;/document.write（'张三'）;（括号里面写文字字母都行）/document.write（“a”）;（括号里面写文字字母都行）

```HTML
<script>
		// alert(1);
		// alert('张三');
		// alert("a");
		// console.log(1);
		// console.log('张三');
		document.write('张三');
	</script>
```

2、通过外部js文件引入

//index.html

```HTML
<script src='index.js'></script>
```

//index.js

#### 注意事项

1、可以引入多个JS文件、js文件整体，相互联系相互影响相互作用

```HTML
<script src='index.js'></script>
<script>
  	alert（1）;
</script>
```

2、外部js文件中不允许写script标签对

3、如果引入外部js文件script标签对中间不允许出现js代码

```HTML
<script src='index.js'>
	alert（1）;
</script>×
```

## 调试工具

alert();

console.log();

document.write();

## js特点

基于对象和事件驱动的松散型解释性语言。

松散型（弱类型）:没有规矩、不严谨

> 变量声明（var）、加不加分号都行、

基于对象：一切对象；



## 变量

存储数据的一个容器

### 变量声明

> var 变量的名
>
> > 由数字、字母、下划线、$符号组成；单独的数字不行，数字不能开头；不能用关键字声明变量；保留字不用；区分大小写；有意义；遵循规则：首字母大写、驼峰命名;

```HTML
先声明后赋值
<secript>
	var a=1;
  	alert(1);
</secript>
```

```HTML
声明的同时进行赋值
<secript>
	var a;
  	a=1;
  	alert(1);
</secript>
```

一次性声明多个变量，然后再赋值

```HTML
var zhangsan lisi wangwu
zhangsan=1；
lisi=3；
wangwu=5；
```

一次性声明多个变量，同时进行赋值

```HTML
var a=1；b=3；c=5；
```

##### 变量注意事项

1、变量值修改;

2、变量允许重复声明同一个变量;

> 如果不给新的变量赋值，用的还是原来的值；若给新的变量赋值，新值会覆盖旧值。

3、声明变量需要var去修饰;

> 如果没用var修饰并且也没有赋值，会**报错**；
>
> 如果没用var修饰并且赋值，变成全局变量（不推荐）；

4、变量声明没有赋值，默认值undefined。赋值之前调用默认值undefined.

### 数据类型

根据在内存中存储的位置

##### 初始数据类型（栈区：数据简单，读取快，信息少）

1、undefined

2、number

3、string

4、null

5、boolean

##### 复合数据类型（堆区：数据复杂，读取慢，信息多）

   object

#### 检测数据类型

typeof（variable）  typeof variable

|   数据类型    |               值               |  typeof   |
| :-------: | :---------------------------: | :-------: |
| undefined |           undefined           | undefined |
|  boolean  |          true/false           |  boolean  |
|   null    |        null（空   什么都没有）        |  object   |
|  number   |    数字、十进制、十六进制、二进制、八进制、特殊值    |  number   |
|  string   | 通过‘单引号’“双引号”包裹起来就是字符串（数字、字符、） |  string   |
|  object   |          属性和方法的无序集合           |  object   |

二进制：0b;

八进制：0o;

十六进制：0x;

最大值：number.MAX-VALUE;

最小值：number.MIN-VALUE;

**如何操作数据**

#### **运算符**

**1、算术运算符**：+（1、加法运算两边都是数字 2、拼接如果有字符串（括号可以改变优先级））、—、×、÷ 、%（取余数，得到某一范围之内的数）、++（1、var++先运算后自增  2、++var先自增后参与运算 3、undefined+数字=NAN（NOT A NUMBER）4、常量不能进行++ ）、——、

 在字符串中\为转义字符

| 代码   | 输出   | 代码   | 输出   |
| ---- | :--- | ---- | ---- |
| \'   | 单引号  | ...  | 拆分元素 |
| \"   | 双引号  |      |      |
| \&   | 和号   |      |      |
| \\   | 反斜杠  |      |      |
| \n   | 换行符  |      |      |
| \r   | 回车符  |      |      |
| \t   | 制表符  |      |      |
| \b   | 退格符  |      |      |
| \f   | 换页符  |      |      |

**注**：其中反双点：不需要拼接，数字加字符中间加上${数字}

**2、赋值运算符：**=、+=、-=、*=、/=、%=、

> **a=a+5 相当于 a+=5**
>
> **给定 *x=10* 和 *y=5*，下面的表格解释了赋值运算符：**

| 运算符  | 例子   | 等价于   | 结果   |
| :--- | :--- | :---- | :--- |
| =    | x=y  |       | x=5  |
| +=   | x+=y | x=x+y | x=15 |
| -=   | x-=y | x=x-y | x=5  |
| *=   | x*=y | x=x*y | x=50 |
| /=   | x/=y | x=x/y | x=2  |
| %=   | x%=y | x=x%y | x=0  |

**3、关系（比较）运算符**：>、<、>=、<=、==（等于）、===（全等）、!=（不等）、!==（完全不等于）

关系运算符运算结果是boolean

**注意**：1、一个等于号相当于赋值，两个等于号是等于;

​	   2、两个等于号比较的是数值;

​	   3、三个等于号比较的是数值和数据类型;

​	   4、字符串（其中只有数字）与数字比较时，字符串当数字，然后进行比较大小;

   	   5、字符串中要是有字母不能转换成数字，不能与数字进行比较大小，返回NAN,整个表达式返回false， ‘ture’字符串不能转化;

 	   6、两个字符串比较，比较字符串首字符的ASCLL码值，ASCLL码值大的所在字符串就大；若第一个相等，需比较第二个字符串；以此类推，依次比较;

​	   7、数字和布尔值，true>=1,fales<=0;

​	   8、undefined与null相等，但不完全相等;

**4、逻辑运算符：**&&(与)、||(或)、!(非)

假值：false、0、null、undefined、NAN

&&（与逻辑）：全部为真，返回值则为真；反之则为假;

||（或逻辑）：有一个为真，返回值则为真；全部为假，返回值为假;

注意:1、逻辑运算值返回值并不一定是boolean；

​        2、a、当console.log（num>10 && num1），如果两个都是真的值时，返回值为后边值（最后一个）num1

​	      b、当console.log（num>10 && num1），如果两个中有一个假的值时，返回值为假的值

​										        如果两个值都是假的，返回值为前边（第一个）的值

​       3、当console.log（undefined && num++）;如果假值在前面时，后面是真值时，后边num++不执行

​		 console.log(num);	//num=num

​       	     当console.log（num++&& undefined ）;如果假值在后面时，前面是真值时，前边num++执行

​		 console.log(num)	;//num=(num++)

​       4、a、当console.log（num || num1），如果两个都是假的值时，返回值为前边值（第一个）num

​	      b、当console.log（num || num1），如果两个中有一个真的值时，返回值为真的值

​										 如果两个值都是真的，返回值为前边（第一个）的值

​       5、当console.log（undefined || num++）;如果假值在前面时，后边是真值，后边num++执行

​		 console.log(num);	//num=(num++)

​      	     当console.log（num1|| num++ ）;如果两个都为真值，后边真值不执行，返回值为第一个值

​		 console.log(num);	//num=num

 三元表达式

#### 一些关键词

> new用来创建对象;

> delete用来删除对象的属性和方法;

> ±10加减号代表正负号表示;

> ()调用函数;

>，逗号一次声明多个变量的时候分隔;

> ...[]

### 执行流程

#### 顺序结构

#### 分支结构（选择结构）（不要有重复）

##### 单路分支：

```HTML
var num=10;
if(num>0)｛
	alert（1）；
｝
```

##### 双路分支:

if（条件）｛

//条件成立执行的代码

｝else｛

//条件不成立执行的代码

｝

```HTML
var num=10;
if(num>0){
  alert(true);
}else{
  alert(false);
}
```

##### 多路分支：

if（条件）{

}else if（条件）{

}else if（条件）{

}else{

//上述条件都不满足，执行

}     

```HTML
var score=prompt('请输入你的成绩',90)；
if(score>=90 && score<=100){
	alert('优秀')
}else if(score>=80 && score<90){
    alert('良好')
}else if(score>=70 && score<80）{
    alert('中等')
}else if(score>=60 && score<70）{
    alert('及格')
}else if(score>=0 && score<60）{
    alert('不及格')
}else{
    alert('输入错误')
  } 
```

##### 嵌套分支（在一个支路中嵌套一个分支）

> **条件是一个范围（if）。条件是定值，情况可数，优先考虑switch**

##### switch用法

switch(值){

case 情况1:

代码;

break;

case 情况2:

代码;

break;

case 情况3:

代码;

break;

default;

}

break来阻止代码自动地向下一个case运行

```HTML
var week=prompt('请输入你的星期')*1;
switch(week){
   case 1:
      alert('一组');
	  break;
   case 2:
      alert('二组');
	  break;
   case 3:
      alert('三组');
	  break;
   case 4:
      alert('四组');
	  break;
   case 5:
      alert('五组');
	  break;
   case 6:
      alert('六组');
	  break;
   case 7:
      alert('七组');
	  break;
   default:
	  alert('输入错误');
}
```

#### 循环结构

##### 在满足条件的情况下，不停的执行某一段代码。 

```HTML
for（var i=1;i<11;i++）{
   alert(1);                  
}
```

##### 求和

```HTML
var sum=0;
for(var i=1;i<11;i++){
    sum+=i;                   
 }
alert(sum);
```

表格拼接法：

```HTML
var table='<table>';
	table+='<table>';
		for(var i=1;i<=10;i++){
			table+='<tr>';
			for(var j=1;j<=10;j++){
			table+='<td>'+j+'-'+i+'</td>';
			}
	table+='</tr>';
  }
table+='</table>';
document.write(table);
```

#### 数组：

> 存储一系列相同相关的数据的容器
>
> **优点**：1、方便管理数据
>
> ​	   2、逻辑清晰，代码方便管理维护
>
> **创建数组**：var=[];
>
> ​		   var arrl=new Array[]
>
> **赋值**：1、声明的同时赋值；
>
> ```HTML
> var arr=[1,2,3,4,5]
> ```
>
> ​	   2、声明之后赋值
>
> ```HTML
> var arr=[];
> arr[0]=1,arr[3]=5;
> ```
>
> **遍历**：for
>
> ```HTML
> 	for（var i=0;i<arr.length;i++）{
> 		arr[i]
> 	}
> ```
>
> **通过下标访问：**
>
> ​	var  arr=[1,2,3,4,5];
>
> ​	arr[0],arr[1],arr[2]
>
> > 下标从**0**开始，    最大：arr.length-1
>
> 二维最大值
>
> ```HTML
> var classes=[
> 			  [85,90,70],
> 			  [85,92,70],
> 			  [85,95,70]
> ]
> var max=classes[0][0];
> for(var i=1;i<classes.length;i++){
> 	for(var j=1;j<classes[i].length;j++){
> 			 if(max>classes[i][j]){
> 			  		max=classes[i][j];
> 			 }
> 	}
> }
> console.log(max);
> ```
>
> 二维数组
>
> ```HTML
> var classes[
>   [85,90,70]，
>   [85,90,70]，
>   [85,90,70]
> ]
> for(var i=1;i<classes.length;i++){
> 	for(var j=1;j<classes.length;j++){
>   		console.log(classes[i][j]);
> }
> }
> ```
>
> 去空格案例：
>
> ```HTML
> 第一种方法
> var arr=[1,2,3,,4,5,6,,7,8,9],newarr=[];
> 	for(var i=0;i<arr.length;i++){
> 		if(arr[i]!=undefined){
> 			console.log(newarr[newarr.length]=arr[i])
> 		}
> 	}
> 第二种方法
> var arr=[1,2,3,,4,5,6,,7,8,9],newarr=[];
> 	for(var i=0;i<arr.length;i++){
> 		if((typeof arr[i])!='undefined'){
> 			console.log(newarr[newarr.length]=arr[i])
> 		}
> 	}
> ```
>
> **注意**：1、数组元素默认undefined
>
> ​	    2、数组长度可变
>
> ​	    3、数组元素可以任意的数据类型

#### for

for(条件初始化；终止条件；变化量)｛

//循环体

｝

for(var i=0;i<10;i++){

console.log(i)

}

#### while（先判断后执行）（如果初始值不满足条件，一次都不执行）

​	while(循环条件){

​	//循环体

​	变化量

​	}

```HTML
var i=1;
while(i<=10){
 	console.log(i);
    i++;
}
```

#### do-while(先执行一次循环体，然后判断条件，如果条件超能力，会继续执行循环体，直到条件不成立，推出循环)（如果初始值不满足条件，执行一次）

​	do{

​	//循环体；

}while（条件）

```HTML
do{
  sum+=i;
  i++;
}while(i<=10)
console.log(sum);
```

**注：**知道循环次数，优先考虑for。知道循环条件，考虑while、do while；

#### 跳转

1、continue跳过当前这次循环，如果条件成立，继续执行循环；

2、break终止整个循环；

## 函数（打包、封装、重复调用）

将实现某一个特定功能的代码段封装，能够重复调用

> 优点：1、重复调用new Array
>
> ​	    2、逻辑结构、清晰
>
> ​	    3、维护、开发

### 1、基本语法声明

#### 格式：

函数名（10，10）（调用函数）

函数体变量->形参（rows，cols）->实参

函数名()（重复几次就调用几次）

function 函数名(rows，cols){

​    功能代码段

}

```HTML
function fnName（[形参1]，[形参2]）{
  //函数体
[return]
}
```



可在声明前后调用函数

### 2、字面量声明

#### 格式：

var fn（自变量）=function()（字面量）{

​	alert(1);

}

​	fn();

#### 注意：

只能在声明后调用函数

```HTML
var fn=function(){
  
}
```

### 3、面向对象

```HTML
new
```

### 4、调用函数

1、函数名（）自变量（）

2、事件后面

3、自调用函数

```HTML
(function fn（）{
  alert(1)'
})();
用括号将自己本身括起来
```

注意：

*函数名相同，后面的函数覆盖掉原来的函数

*基本语法声明的函数在声明的前后都可调用，以字面量声明的函数只能在赋值之后调用

### 参数：

动态的去改变函数体内部的变量，函数灵活强大。

#### 形参：

函数定义时，小括号里面的值，形参没有实际的值，接受实参的值。

#### 实参：

函数调用，小括号里面的值，实参给形参传递值。

注意：

1、实参给形参传递值按照先后顺序传递；

2、当形参值比实参多时，多出来的形参值显示undefined；

3、当实参值比形参值多时，多出来的实参值不显示



```HTML
var arr=[1,2,3,4,5,6,7,8];
function fn(arr){
	for(var i=1;i<arguments.length;i++){
		arr[arr.length]=arguments[i];
	}
	console.log(arr);
}
fn(arr,'a','b'); 
```

```HTML
arr=[13,24,36,47,52,64,75,86,9]
function sort(arr,type){
  默认升序：第一种：if(type=undefined){
  						type='<';
					}
            第二种：type=type==undefined? '<':type;
			第三种：type=type||'<';
  if(type=='<'){
      sortUP(arr);
  }else if(type=='>'){
  	   sortDown(arr);
  }
}
function sortUp(arr){
  for(var i=0;i<arr.length;i++){
		for(var j=i+1;j<arr.length;j++){
  			if(arr[i>arr[j]){
			var temp=arr[i];
				arr[i]=arr[j];
				arr[j]=temp;
			}
		}    
	}
}
function sortDown(arr){
  for(var i=0;i<arr.length;i++){
		for(var j=i+1;j<arr.length;j++){
  			if(arr[i>arr[j]){
			var temp=arr[i];
				arr[i]=arr[j];
				arr[j]=temp;
			}
		}    
	}
}
```

#### arguments

接受所有的实参，是一个对象object，用法和数组差不多，但不是数组，只能在函数内部调用

函数内部自动生成对象，只能函数内部调用，保存了函数调用时实参的信息

默认参数：

参数：传值，传进来的值。不传默认值；

分支

#### 三元表达式

```HTML
···js
type=type==undefined?默认值:type
```

#### 逻辑||

```HTML
​```js
type=type||默认值
```

#### ES6

```HTML
···
function fn（type=默认值）
```

#### rest参数

1、剩余参数，（没有形参对应的实参），是一个数组

2、没有剩余参数，空数组

3、rest参数必须在最后

```HTML
fn（arr，a，b，c）
function fn（arr,...rest（名字））{
  //rest
}
```

```HTML
arr=[13,24,36,47,52,64,75,86,9]
fn(arr,a,b,c)
function fun(arr,...rest){
  for(var i=1;i<arr.length;i++){
		arr[arr.length]=rest[i]
   }
  console.log(arr);
}
```

#### 返回值 return(返回、终止函数)

在函数调用地方返回一个值；

终止函数执行，return后面的代码不会执行；

函数的返回值可以是任意的数据类型；

一个函数只有一个返回值，允许写多个return，但只执行一个；

函数返回值只能返回一个；

```HTML
arr=[31,22,3,4,15,56,73,82]
var ex=exist(arr,5);
alert(ex);
function exist(arr,value){
  for(var i=0;i<arr.length;i++){
        if(arr[i]=value){
              return true;
        }
  }
  return false;
}
```

## 作用域

变量的作用范围

1、全局作用域（任意）：定义在函数最外层；变量不用var去声明；

2、局部作用域（某一个函数）：定义在函数内部

#### 环境

*宿主

*执行

*预编译

按照从上到下，script

var  function 变量名和函数名预先放置内存，记录声明环境

```HTML
var num=20;
function aa(){
	var num=10;
 	alert(num);//10
  	function bb(){
  		alert(num);//10
		var num=15;
		alert(num);//15
}
}
alert(num);//20
```

```HTML
function aa(num1,num2){
	return num1*num2/num2;
}
function bb(num1,num2){
	return num1*num2-num2;
}
function cc(num1,num2){
	return num1*num2+num2;
}
function math(num1,num2,fn){
	return fn(num1,num2);
}
var result=math(2,3,bb);
console.log(result);
```

## 回调函数

map：映射

```HTML
arr=[1,2,3,4,5,6,7]
var result=map(arr,function(value){
	return value*2
})
console.log(result);
function map(arr,fn){
	var newarr=[];
	for(var i=0;i<arr.length;i++){
		newarr[newarr.length]=fn(arr[i])
	}
	return newarr;
 }
```

filter：过滤

```HTML
arr=[1,2,3,4,5,6,7]
ar result=filter(arr,function(value){
	return value%2==1
})
console.log(result);
function map(arr,fn){
	var newarr=[];
	for(var i=0;i<arr.length;i++){
		if(fn(arr[i])){
		newarr[newarr.length]=arr[i];
		}
	}
	return newarr;
}
```

some：一些

```HTML
var arr=[1,2,-3,4,5,-6]
var result=some(arr,function(value){
	return value>0;
})
console.log(result)
function some(arr,fn){
	for(var i=0;i<arr.length;i++){
		if(fn(arr[i])){
			return true;
		}
	}
	return false;
}
```

every：每一个

```html
var arr=[1,4,3,5,-2]
var result=every(arr,function(value){
	return value>0;
})
console.log(result)
function every(arr,fn){
	for(var i=0;i<arr.length;i++){
		if(!fn(arr[i])){
			return false;
		}
	}
	return ture;
}
```

## 递归函数

不是循环，

函数自己调用自己本身，必须有临界条件，输出是从下往上，

```HTML
fn(1)
function fn(num){
  if(num<5){
          fn(+num) 	  
	}
    alert(num);
}
```

地址：浅拷贝

```HTML
var arr=[1,23,4,5]
var arr1=arr;
arr1[1]='a';
arr[3]='x'
console.loge(arr1)
console.loge(arr)
```

传值：深拷贝

```HTML
var arr1=[]
for(var i=0;i<rr.lenghht;i++){
     arr1[i]=arr[i]
}
arr[1]='a';
arr[3]='x'
console.log(arr1)
console.log(arr)
```

# github

new responsitory









