# Javascript

## 基本概念

前端三要素：

- Html:超文本标记语言，决定网站的结构和内容
- css:层叠式样式表，设定网页的表现形式 
- JavaScript:是一种弱类型脚本语言，其源代码不需要经过编译，而是由浏览器解释运行，用于控制网页的行为

## 基本使用

```JS
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

<!--  JavaScript严格区分大小写-->
  <script>
     // 1、定义变量  变量类型 变量名 = 变量值;
     var score = 1;
     // alert(num);
     // 2、 条件控制
     if (score > 60 && score < 70){
       alert("大于60小于70");
     } else  if (score > 50 && score < 60){
       alert("大于50小于60");
     }else {
       alert("other");
     }

     // console.Log(score)  在浏览器的控制台打印变量
  </script>
</head>
<body>

</body>
</html>
```

## 数据类型

**获取数据类型：typeof**

### number（数值）

js不区分小数和整数：Number

```js
123   //整数
123.1 //浮点数
1.123e3 //科学计数法
-99 //复数
NaN  //not a number
Infinity //表示无限大
```

### 字符串

```js
'abc'  "abd"
```

1.正常字符串我们使用 单引号，或者双引号

2.注意转义字符 \

```
\' 一个字符串
\n  换行
\t  tab缩进
\u42ed unicode字符
\xxx   Ascll字符
```

3.多行字符串编写

```js
var msg = `
sxxxx
xxx
xxx
`
```

4.模板字符串

```js
let name = "wsiadi"
let age = 3
let msg = `傻逼，${name}`
```

5.字符串长度

```js
str.length
```

6.字符串的可变性，不可变

7.大小写转换

```js
//注意这里是方法不是属性
str.toUpperCase()
str.toLowerCase()
```

8.获取指定的下标

```
str.index('要查找的字符')
```

9、substring

```js
[)
student.substring(1) // 从第一个字符串截取到最后一个字符串
student.substring(1,3) // [1,3)
```



### 布尔值

```js
true false
```

### 逻辑运算

```js
&&  与：两个为真，结果为真
||	或：一个为真，结果为真
!	非：真即假，假即真
```

### 比较运算符

```js
=  赋值符号
== 等于符号（类型不一样，值一样，也会判断为true）
===  绝对等于（类型一样，值一样，结果true）
```

这是js的一个缺陷，坚持使用===，不要使用==进行比较

注：

- NaN===NaN，这个与所有的数值都不相等，包括自己
- 只能通过isNaN(NaN)来判断这个数是否是NaN

浮点数问题：

```js
console.log((1/3) === (1-2/3))
```

尽量避免使用浮点数进行运算，存在精度问题

```
Math.abs(1/3-(1-2/3))<0.00000001
```

### null和undefined

- null空
- undefined未定义

### 数组

java中数组必须是一系列相同类型的对象，js不需要

```js
//保证代码的可读性，尽量使用[]
var arr = [1,2,3,"qbf",null,true]
//取值
var arr = [1,2,3,4,5]
arr[0] = 1
```

如果取数组下标，越界了

```js
undefined
```

1、长度

```js
arr.length
```

注意：加入给arr.length赋值，数组大小就会发生改变，如果赋值过小，元素就会丢失

2、indexOf，通过元素后的下标索引

```js
arr.indexOf (2)
//数字1和字符串的"1"不一样
```

3、slice()截取Array的一部分，返回一个新数组，类似于String中的substring

```js
arr.slice(1,6)//取1-6位的值
```

4、push(),pop()  尾部

```js
push: 压入到尾部
pop: 弹出尾部的一个元素，数组会减少
```

5、unshift(),shift() 头部

```js
unshift: 压入到头部
shift:弹出头部的一个元素，数组会减少
```

6、排序sort()

```js
(3)['b','c','a']
arr.sort()
(3)['a','b','c']
```

7、元素反转reverse()

```js
(3)['a','b','c']
arr.reverse()
(3)['c','b','a']
```

8、concat()

```js
(3)['c','b','a']
arr.concat(['1','2','3'])
(6)['c','b','a','1','2','3']
arr
(3)['c','b','a']
```

注意：concat（）并没有修改数组，只是会返回一个新的数组

9、连接符join

打印拼接数组，使用特定的字符串连接

```js
(3)['c','b','a']
arr.join('-')
"c-b-a"
```

10、多维数组

```js
arr = [[1,2],[3,4],["5","6"]]
```



数组：存储数据（如何存，如何取）



### 对象

对象是大括号，数组是中括号

```js
//Person person = new Person(1,2,3,4,5)
var person = {
    name:"wshishabi",
    age:3,
    tags:['js','html','java']
}
```

每个属性用” ,“隔开，最后一个不用

去对象的值

```js
person.name
>"wshishabi"
person.age
>3
```

若干个键值对

```js
var 对象名 = {
    属性名:属性值,
    属性名:属性值,
    属性名:属性值
}

//定义了一个person对象，他有四个属性
var person = {
    name: "xiaojianguo",
    age: 6,
    email: "1484472361@qq.com",
    score: 100
}


```

js中对象，{.....}表示一个对象，键值对描述属性xxxx:xxxx,

多个属性之间使用逗号隔开，最后一个属性不加逗号！

JavaScript中的所有的键都是字符串，值是任意对象

1、对象赋值

```js
person
{name: 'sb', age: 6, email: '4354354354', score: 100}
person.name = "nt"
'nt'
person.name
'nt'
```

2、使用一个不存在的对象属性，不会报错！undefined

```js
person.asd
undefined
```

3、动态的删减属性，通过delete删除对象的属性

```js
delete person.email
true
person
{name: 'nt', age: 6, score: 100}
```

4、动态的添加

```js
person.nt = "haha"
'haha'
person
{name: 'xiaotian', age: 6, score: 100, haha: 'haha'}
```

5、判断 属性值是否在这个对象中！xxx in xxx

```js
"age" in person
true
// 继承
"toString" in person
true
```

6、判断一个属性是否是这个对象自身拥有的hasOwnProperty()

```js
person.hasOwnProperty("age")
true
person.hasOwnProperty("toString")
false
```



### 变量

```js
var a = 1
//注意命名规范，不能使用数字开始，中文可以使用
```

### 流程控制

if 判断

```js
var age = 3;
if(age > 3){
    alert("hahaha");
}else{
    alert("kukuku");
}
```

while循环，避免程序死循环

```js
while(i < 100){
    i++;
    console.log(i);
}

do{
    i++;
    console.log(i);
}while(i < 100)
```

for循环

```js
for (let j = 0; j <100; j++) {
    j++;
    console.log(j)
}
```

数组循环

forEach循环

```js
var arr = [12,32,56,418,"asd","sd",null];
// 函数
arr.forEach(function (value) {
    console.log(value)
});
```

for..in

```js
// for(let index in object)
// num 是arr的索引
for (let num in arr){
    console.log(num);
    console.log(arr[num])
}
```

### Map和Set

> ES6的新特性

Map:

```js
// ES6  Map
// 学生的成绩，学生的名字
// var names = ["fangjiayi","xujiao","jixinyu"];
// var scores = [100,80,90];

var map = new Map([["fangjiayi",100],["xujiao",80],["jixinyu",90]]);
var name = map.get("jixinyu"); // 通过key获得value
map.set("shixinya",85); // 新增或修改
map.delete("shixinya"); // 删除
```

Set:无需不重复的集合

```js
var set = new Set([3,3,1,1,1])//去重
set.add(2); // 添加！
set.delete(1); // 删除！
console.log(set.has(3)); // 是否包含某个元素
```

#### iterator

> ES6 新增的特性

使用iterator来遍历迭代Map和Set

遍历数组

```js
// 通过for of / for in 下标
var arr = [3,4,5];
for(let x of arr){
    console.log(x)
}
```

遍历map

```js
var map = new Map([["fangjiayi",100],["xujiao",80],["jixinyu",90]]);
for(let el of map){
    console.log(el)
}
```

遍历set

```js
var set = new Set([5,6,7]);
for(let el of set){
    console.log(el)
}
```



## 严格检查模式：'use strict'

预防javascript的随意性导致产生的一些问题

局部变量尽量都是用let定义

## 函数

### 函数的定义和参数获取

> 定义方式一

绝对值函数

```js
function abs(x){
    if(x>=0){
        return x;
    }else{
        return -x;
    }
}
```

一旦执行到return代表函数结束，返回结果！

如果没有执行return，函数执行完也会返回结果，结果就是undefined



> 定义方式二

```js
var abs = function(x){
    if(x>=0){
        return x;
    }else{
        return -x;
    }   
}
```



> 调用函数

```js
abs(10) //10
abs(-10) //10
```

参数问题：JavaScript可以传任意个参数，也可以不传参数~

参数进来是否存在的问题？假设不存在参数，如何规避？

```js
var abs = function(x){
    // 手动抛出异常判断
    if(typeof x !== 'number'){
        throw 'Not a Number'
    }
    if(x>=0){
        return x;
    }else{
        return -x;
    }   
}
```



> argument

argument是一个JS免费赠送的关键词

代表，传递进来的所有的参数，是一个数组 

```js
var abs = function(x){
    console.log("x=>"+x);
    
    for(let i = 0; i<arguments.length;i++){
        console.log(arguments[i]);
    }
    
    if(x>=0){
        return x;
    }else{
        return -x;
    }   
}
```



问题：arguments包含所有的参数，我们有时候想使用多余的参数来进行附加操作。需要排除已有参数~



> rest

以前：

```js
if(arguments.length>2){
    for(let i = 2; i < arguments.length; i++){
        
    }
}
```



ES6引入的新特性，获取除了已经定义的参数之外的所有参数~ ...

```js
function aaa(a,b,...rest){
    console.log("a=>"+a);
    console.log("b=>"+b);
    console.log(rest);
}
```

rest参数只能写在最后面，必须用...标识

### 变量的作用域

在JavaScript中，var定义变量实际是有作用域的。

假设在函数体中声明，则在函数体外不可以使用~（非要实现的话，后面可以研究一下==闭包==）

```js
function qj(){
    var x = 1;
    x++;
}
x = x + 2; // Uncaught ReferenceError: x is not defined

```

- 如果两个函数使用了相同的变量名，只要在函数内部，就不冲突

```js
function qj(){
    var x = 1;
    x++;
}

function qj2(){
    var x = 'A';
    x++;
}
```

- 内部函数可以访问外部函数的成员，反之则不行

```js
function qj(){
    var x = 1;
    function qj2(){
        var y = 'A';
    }
    var z =  y + 1;
}
console.log(z) >Uncaught ReferenceError: y is not defined
```

- 假设，内部函数变量和外部函数的变量，重名！

```js
function qj(){
    var x = 1;
    function qj2(){
        var x = 'A';
        console.log('inner'+x);
    }
	console.log('outer'+x);
    qj2();
}
qj();

>outer1
>innerA
```

假设在JavaScript中函数查找变量从自身函数开始~，由

“内”向“外”查找，假设外部存在这个同名的函数变量，则内部函数会屏蔽外部函数的变量



> 提升变量的作用域

```js
function qj(){
    var x = "x" + y;
    console.log(x);
    var y = 'y';
}

>xundefined
```

说明：js执行引擎，自动提升了y的声明，但是不会提升变量y的赋值

其实际代码如下：

```js
function qj(){
    var y;
    var x = "x" + y;
    console.log(x);
    y = 'y';
}
```

这个是在JavaScript建立之初就存在的特性。养成规范，将所有的变量都定义在最前面，便于代码维护。



> 全局变量

```js
// 全局变量
var x = 1;

function f(){
    console.log(x);
}

f();
console.log(x);
```

全局变量window

```js
var x = 'xxx';
alert(x);
alert(window.x);默认所有的全局变量，都会自动绑定在window对象上
```

alert()这个函数本身是一个window变量

```js
var x = 'xxx'
window.alert(x)

var old_alert = window.alert
//old_alert(x)

window.alert = function(){
    
}
//发现alert失效了
window.alert(123)

//恢复
window.alert = old_alert
window.alert(456)
```



JavaScript实际上只有一个全局作用域，任何变量（函数也可以视为变量），假设没有在函数作用范围内找到，就会向外查找，如果在全局作用域都没有找到，报错`RefrenceError`



> 规范

由于我们所有的全局变量都会绑定到我们的window上。如果不同的js文件，使用了相同的全局变量，冲突->如果能够减少冲突。

```js
// 唯一全局变量
var XiaoApp = {};

// 定义全局变量
XiaoApp.name = 'XiaoJianGuo';
XiaoApp.add = function(a,b){
    return a + b;
} 
```

把自己的代码全部放入自己定义的唯一空间名字中，降低全局命名冲突的问题



> 局部作用域let

```js
function aaa(){
    for(var i = 0;i < 100;i++){
        console.log(i);
    }
    console.log(i);// 问题？i出了这个作用域还可以使用
}
```

ES6 let关键字，解决局部作用域冲突问题！

```js
function aaa(){
    for(let i = 0;i < 100;i++){
        console.log(i);
    }
    console.log(i);// Uncaught ReferenceError: i is not defined
}
```

建议使用 let 去定义局部作用域的变量；



> 常量 const

在ES6之前，怎么定义常量：只有用全部大写字母命名的变量就是常量，建议不要修改这样的值。（业内规范）

```js
var PI = '3.14';

console.log(PI);
PI = '213';// 可以改变这个值
console.log(PI);
```

在ES6引入了常量关键字`const`

```js
const PI = '3.14'; // 只读变量
console.log(PI);
PI = '123';// TypeError: Assignment to constant variable.类型错误
console.log(PI);
```

### 方法

> 定义方法

方法就是把函数放在对象的里面，对象只有两个东西：属性和方法

```js
'use strict';
var wshishbi = {
    name: '傻逼',
    birth: 2001,
    // 方法
    age: function (){
        // 今年 - 出生的年
        var now = new Date().getFullYear();
        return now - this.birth;
    }
}
// 属性
wshishbi.name
// 方法，，一定要带括号
wshishbi.age()
```

this.代表什么？拆开上面的代码看

```js
function getAge(){
     // 今年 - 出生的年
    var now = new Date().getFullYear();
    return now - this.birth;
}

var wshishbi = {
    name: '傻逼',
    birth: 2000,
    // 方法
    age: getAge
}
```

java中的this是无法指定的，是默认指向调用它的那个对象



> apply

在js中可以控制this指向

```js
function getAge(){
     // 今年 - 出生的年
    var now = new Date().getFullYear();
    return now - this.birth;
}

var wshishbi = {
    name: '傻逼',
    birth: 2000,
    // 方法
    age: getAge
}

var wshint = {
    name: '年团',
    birth: 2000,
    // 方法
    age: getAge
}

getAge.apply(xiaoming,[]);//参数是用数组表示，参数为空即用[]空数组表示
```

### 内部对象

标准对象

```js
typeof 123
'number'
typeof '123'
'string'
typeof true
'boolean'
typeof NaN
'number'
typeof []
'object'
typeof {}
'object'
typeof Math.abs
'function'
typeof undefined
'undefined'
```

#### data

> 基本使用

```js
'use strict';
var now = new Date(); // Sat Oct 23 2021 20:12:38 GMT+0800 (中国标准时间)
now.getFullYear(); // 年
now.getMonth(); // 月
now.getDate(); // 日
now.getDay(); // 星期
now.getHours(); // 时
now.getMinutes(); // 分
now.getSeconds(); // 秒

now.getTime(); // 时间戳 全世界统一 1970.1.1 0:00:00 毫秒数

console.log(new Date(now.getTime())); // 时间戳转换为时间
```

```js
now = new Date(now.getTime());
>Sat Oct 23 2021 20:12:38 GMT+0800 (中国标准时间)
now.toLocalString(); //注意调用是一个方式，不是一个属性
>'2021/10/23 下午8:12:38'
now.toGMTString()
"Mon, 28 Feb 2022 08:05:07 GMT"
```

#### JSON对象

> json是什么

- [JSON](https://baike.baidu.com/item/JSON)([JavaScript](https://baike.baidu.com/item/JavaScript) Object Notation, JS 对象简谱) 是一种轻量级的数据交换格式。
- 简洁和清晰的层次结构使得 JSON 成为理想的数据交换语言。
- 易于人阅读和编写，同时也易于机器解析和生成，并有效地提升网络传输效率。

在JavaScript 一切皆为对象、任何js支持的类型都可以使用JSON来表示；

格式：

- 对象都用{}
- 数组都用[]
- 所有的键值对都是用key:value

```json
//JSON字符串和js对的转化
var user = {
    name:"wshishibi",
    age:3,
    sex:"nan"
}
//对象转换为json字符串
var jsonuser =  JSON.stringify(user)
//json字符串转换位对象
JSON.parse('{"name":"wshishbi","age":3,"sex":"nan"}')
```

很多人搞不清楚，JSON和JS对象的区别

```js
var obj = {a:'hello',b:'hellob'}
var json = '{"a":"hello","b":"hellob"}'
```

###  Ajax

- 原生的js学法  xhr异步请求
- JQuery封装好的方法  $("#name").ajax("")
- axios请求

## 面向对象编程

#### 什么是面向对象

JavaScript，java，c#。。。。面向对象；JavaScript有些区别

- 类：模板
- 对象：具体的实例

```js
var student = {
    name:"sada",
    age:3
}
var xiaomi = {
    name:"xiaomi"
}
xiaomi._proto_ = student 
//原型
```

#### class继承

class关键字是在es6中引入的

定义一个类，属性，方法

```js
function student(name){
    this.name = name
}

//给student添加一个方法
//给他的原型加
student.prototype.hello = function(){
    alert('hello')
}
//es6之后
class student{
    constructor(name){
        this.name = name
    }
    hello(){
        alert('hello')
    }
}
var xiaomi = new student("xiaomi");
```

继承

```js
function student(name){
    this.name = name
}

//给student添加一个方法
//给他的原型加
student.prototype.hello = function(){
    alert('hello')
}
//es6之后
class student{
    constructor(name){
        this.name = name
    }
    hello(){
        alert('hello')
    }
}
class xiao exthends student{
    constructor(name,grade){
        super(name)
        this.grade = grade
    }
    myGrade(){
        alert('我是一个傻逼')
    }
}
var xiaomi = new student("xiaomi");
```

原型链：无限的

## 操作BOM对象

浏览器介绍

javaScript和浏览器关系

JavaScript诞生就是为了能够让他在浏览器中运行

BOM：浏览器对象模型

IE.Chrome,Safari,FireFox....(内核)

三方：QQ浏览器，360

> window

window代表 浏览器窗口

```js
window.innerHeight
//内部屏幕高度
window.innerWidth
//内部屏幕宽度
window.outerHeight
//外部屏幕高度
window.outerwidth
//外部屏幕宽度
```

> Navigator

Navigator，封装了浏览器信息

```js
navigator.appName
//浏览器软件信息
navigator.appVersion
//版本号
navigator.userAgent
//用户信息
```

大多数时候我们不会使用navigator对象，因为会被人认为修改，不建议使用这些属性来判断和编写代码

> screen

代表屏幕尺寸

```js
screen.width
screen.height
```

> location

location代表当前页面的URL信息

```js
host:"www.baidu.com"
//主机
href:"https://www.baidu.com"
//当前位置
protocol:"https:"
//协议
reload()
//重新加载，刷新，设置新的地址
```

> document（内容;  DOM）

document 代表当前的页面

```js
document.title
'百度一下，你就知道'
document.title = '傻逼'
'傻逼'
```

获取具体的文档树节点

```
<dl id="app">
  <dt>js study</dt>
  <dd>BOM</dd>
  <dd>DOM</dd>
</dl>

<script>
  var elementById = document.getElementById("app");
</script>
```

获取cookie

```js
document.cookie
'BIDUPSID=FA4F3E78EAC9F456B667D2CFEBDFCF85; PSTM=1562385108; MCITY=-293%3A; COOKIE_SESSION=0_0_1_1_0_0_0_0_1_0_0_0_0_0_0_0_0_0_1628253379%7C1%230_0_1628253379%7C1; BAIDUID=67ACE7C50FC7D0139A5938BEABFD92C3:FG=1; BD_HOME=1; H_PS_PSSID=34834_34068_31254_34712_34584_34517_34831_34579_34813_26350_34827; BD_UPN=12314753; BAIDUID_BFESS=67ACE7C50FC7D0139A5938BEABFD92C3:FG=1; BA_HECTOR=0l8g000g0k2h8k2g8q1gna2ff0q'
```

劫持 cookie 原理

www.taobao.com

```html
<script src = "aa.js"></script>
<!--恶意人员：获取你的cookie上传到他的服务器 -->
```

服务器端可以设置cookie：httpOnly



> history（不建议使用）

history代表浏览器的历史记录

```js
history.back(); // 后退
history.forward(); // 前进
```

## 操作DOM对象

DOM：文档对象模型

> 核心

浏览器网页就是一个DOM树形结构！

- 更新：更新DOM节点
- 遍历DOM节点：得到DOM节点
- 删除：删除一个DOM节点
- 添加：添加一个新的节点

要更新一个DOM节点，就必须要先获得这几个DOM节点

 获得DOM节点

```js
'use strict';

// 对应 css 选择器
//标签选择器
document.getElementsByTagName("h1");
//id选择器
document.getElementById("p1");
//类选择器
document.getElementsByClassName("p2");

//返回指定选择器的第一个元素对象
document.querySelect()

// 获取父节点下的所有子节点
var father = document.getElementById("father");
var children = father.children;
// father.firstChild;
// father.lastChild;
```

这是原生代码，之后尽量都使用JQuery();

### 更新节点

```html
<div id="id1"></div>

<script>
  var elementById = document.getElementById('id1');

</script>
```

操作文本

- `elementById.innerText='123'`修改文本的值
- `elementById.innnerHTML ='<em>234</em>'`可以解析HTML文本标签

操作js

```js
elementById.style.color = 'red'; // 属性使用字符串
elementById.fontSize = '30px'; // - 转 驼峰命名
elementById.style.padding = '2em';
```



### 删除节点

删除节点的步骤：先获取父节点，在通过父节点删除

```html
<div id="father">
  <h1>标题</h1>
  <p id="p1">p1</p>
  <p class="p2">p2</p>
</div>
<script>
    var self = document.getElementById('p1');
    var father = p1.parentElement;
    father.removeChild(self);
    
    father.removeChild(father.children[0]);
</script>
```

注意：删除多个节点的时候，children是在时刻变化的，删除节点的时候一定要注意！



### 插入节点

我们获得了某个DOM节点，假设这个DOM节点是空的，我们通过innerHTML、innerText就可以增加一个元素了但是这个DOM节点已经存在元素了，我们就不能这么干了！会产生覆盖！



#### **追加**

```html
<p id="js">JavaScript</p>
<div id="list">
  <p id="se">JAVASE</p>
  <p id="ee">JAVAEE</p>
  <p id="me">JAVAME</p>
</div>

<script>
  var list = document.getElementById('list');
  var js = document.getElementById('js');
  
  list.appendChild(js);// 追加到后面
</script>
```



#### 创建一个新的标签，实现插入

```js
var list = document.getElementById('list');
var js = document.getElementById('js');
list.appendChild(js);

// 通过js创建一个新的节点
var newh1 = document.createElement('h1');
newh1.id = 'h1';
newh1.innerText = '123';
list.appendChild(newh1);

// 通过这个属性可以设置任意的值
var myScript = document.createElement('script');;
myScript.setAttribute('type','text/javascript');

// getElementsByTagName 和 getElementsByClassName 返回的都是一个数组
var body = document.getElementsByTagName('body');
body[0].style.background = 'red';
```



#### insert

```js
var ee = document.getElementById('ee');
var js = document.getElementById('js');
var list = document.getElementById('list');
// 要包含的节点，insertBefore(new Node,targetNode)
list.insertBefore(js,ee);
```

## 操作表单 

> 表单是什么 from DOM树

- 文本框  text
- 下拉框  <select>
- 单选框  radio
- 多选框  checkbox
- 隐藏框  hidden
- 密码框  password
- ....

表单的目的：提交信息



> 获得要提交的信息

```html
<form action="#" method="post">
    <p>
        <span>用户名：</span><input type="text" id="username">
    </p>
    <p>
        <span>性别：</span>
        <input type="radio" name="sex" value="man" id="boy">男
        <input type="radio" name="sex" value="woman" id="girl">女
    </p>
</form>

<script>
    var input_text = document.getElementById('username');
    var boy = document.getElementById('boy');
    var girl = document.getElementById('girl');

    // 得到输入框中的值
    input_text.value;
    // 修改输入框中的值
    input_text.value = '123';

    // 对于单选框，多选框等等固定的值，boy.value 只能取到当前的值
    boy.checked; // 查看返回的结果，是否为true，如果为true，则被选中~
    girl.checked = true; // 赋值
</script>
```



> 提交表单。MD5 加密密码，表单优化

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
  <script src="https://cdn.bootcdn.net/ajax/libs/blueimp-md5/2.18.0/js/md5.js"></script>
</head>
<body>
<!--
表单绑定提交事件
onsubmit = 绑定一个提交检测的函数，true ，false
将这个结果返回给表单，使用 onsubmit 接受！
onsubmit = “return aaa()”
-->

<form action="https://www.baidu.com/" method="post" onsubmit="return submit()">
  <p>
    <span>用户名：</span>
    <input type="text" name="username" id="username">
  </p>
  <p>
    <span>密码：</span>
    <input type="password" id="input-password">
  </p>
  <input type="hidden" name="password" id="md5- password">

  <button type="submit">提交</button>

</form>

<script>
  function submit(){
    var username = document.getElementById('username');
    var pwd = document.getElementById('input-password');
    var md5pwd = document.getElementById('md5-password');
    // pwd.value = md5(pwd.value);
    md5pwd.value = md5(pwd.value)
    return true;
  }
</script>
</body>
</html>
```

## jquery

jquery对象，用jquery方式获取的对象

jquery对象只能使用jquery方法

> 获取jQuery

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    
    // 做项目时建议下载jquery来使用，不使用cdn的jquery
  <script src="https://cdn.bootcdn.net/ajax/libs/jquery/3.6.0/jquery.js"></script>
</head>
<body>
<!--
公式：$(selector).action()
-->

<a href="" id="test-jqery">点我</a>

<script>
    // 选择器就是css选择器
    $('#test-jqery').click(function (){
        alert('hello jqery');
    })
</script>
</body>
</html>
```

> DOM转换位jquery对象

```js
//获取元素，得到的就是jquery对象

```

> 选择器

$("#id|*|.class|div")  id，全选，类，标签

$("div,p,li") 并集

$("li.current") 交集

子代选择器   $("ul>li")  获取儿子层级的元素

后代选择器   $("ul li")    代表后代选择器，获取ul下所有的li元素

> 筛选选择器

:first  获取第一个元素  $("li:first")

:last  获取最后一个元素  $("li:last")

:eq(index)  获取第几个元素，从0开始  $("li:eq(2)")

:odd  获取奇数元素  $("li:odd")

:even  获取偶数元素  $("li:even")

> 事件

鼠标事件，建盘事件，其他事件。。。。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
  <script src="https://cdn.bootcdn.net/ajax/libs/jquery/3.6.0/jquery.js"></script>

  <style>
    #divMove{
      width: 500px;
      height: 500px;
      border: 1px solid red;
    }
  </style>
</head>
<body>

<!--要求获得鼠标当前的一个坐标-->
<p>mouse: <span id="mouseMove"></span></p>
<div id="divMove">
  在这里移动鼠标试试
</div>

<script>
  // 当网页元素加载完毕之后，相应事件
  $(function (){
    $('#divMove').mousemove(function (e){
      $('#mouseMove').text('x'+e.pageX+'y'+e.pageY);
    })
  })
</script>

</body>
</html>
```



> 操作DOM

节点文本操作

```js
$('#test-ul li[name=python]').text();// 获得值
$('#test-ul li[name=python]').text('设置值');// 获得值
$('#test-ul').html();// 获得值
$('#test-ul').html('<strong>123</strong>');// 设置值
```

css的操作

```js
$('#test-ul li[name=python]').css({"color","red"},{"background","black"})
```

元素的显示和隐藏：本质`display:none`;

```js
$('#test-ul li[name=python]').show();
$('#test-ul li[name=python]').hide();
```

娱乐测试

```js
$(window).width()
$(window).height()
```







