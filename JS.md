# JavaScript入门

## 1.基础语法

- <script></script>
  > 成对出现 否则闭合可能会有问题

- 严格区分大小写

- 1.定义变量 

  ```javascript
  var num=1; var a="abc";
  ```

- 2.条件控制 可嵌套

```javascript
If(score>60&&score<70){
	alert()
}
Else if(){
}
```

- 浏览器调试技巧——网页右键 “检查元素”

- - Console可调试js:   打印变量console.log()
  - Source 断点 单步调试

 

## 2.数据类型

### 2.1概述

- 数值、文本、图形、音频、视频

- `number`  js不区分小数和整数，统一用`number`

- 字符串 `"abc"` `'abc'`

- 布尔值  `true`      `false`

- 逻辑运算  `&&`  `||`  `！`

- 位运算 

    -  `与 或 非 异或`  `&`  `|`      `~`  `^`

    - 左移 <<  用0填充  右移  >>  用符号位填充

        无符号右移  >>>  用0填充

- 比较运算符

- - `=`  赋值
  
  - `==` 类型不一样 值一样也会判断为true       e.g. 1 "1"相等  null==undeifned 为true
  - `===`绝对等于（类型一样，值相等）
  
- ```
    NaN==NaN
    ```
  
    >  false 因为NaN与所有数值都不相等，包括自己
  
   只能通过
  
  ```javascript
  isNaN(NaN)
  ```
  
   判断数是否为NaN
  
  > isNaN("10")  false 	//可以**转换为数值**10
  
  > isNaN("blue")   true 	//不可以转换为数值
  >
  > isNaN("true")     false    //可以转换为数值
  >
  > 
  
- 浮点数精度问题：

  ```javascript
  (1/3)===(1-2/3) 
  ```

  > false 尽量避免使用浮点数进行运算，有精度问题   
  >
  > ```javascript
  > Math.abs(1/3-(1-2/3))<0.00000001
  > ```
  >
  > 为true

- null和undefined

> Null 已定义，为空
>
> Undefined 未定义

- 整数转换  

  - Number()  任何数据类型转数值

  - parseInt()  字符串转数值

    ```javascript
    var num = parseInt("0xAF", 16);
    var num = parseInt("AF", 16); //175  可不带"0x“
    ```

  - parseFloat() 字符串转数值  只解析十进制，若字符串包含的是一个可解析为整数的数，会返回整数

- 数组

js中的数组不需要是相同类型的数组 e.g.

```javascript
var arr=[1,2,3,4,5,'hello',true]
```

> 取数组下标，如果越界了，就是undefined
>

- 对象

| 对象用大括号  | Var  person={name:"aa",age:3} |
| ------------- | ----------------------------- |
| 取对象的值用. | person.name                   |

 

**严格检查模式****strict**

- ES6中 局部变量用let定义
- 'use strict' //IDEA需要设置支持ES6语法；严格检查模式，预防JS的随意性会产生问题,必须写在第一行

e.g. 

```html
<script>

'use strict';

</script>
```

### 2.2字符串

1.正常字符串用单双引号包裹

2.注意转义字符  `\'`  `\n`换行  `\t`制表  `\unnnnn` Unicode字符  `\xnnnnn`  AscII字符

<img src="C:\Users\little_scenery\AppData\Roaming\Typora\typora-user-images\image-20200915154222295.png" alt="image-20200915154222295" style="zoom:67%;" />

3.多行字符串编写

```javascript
var msg=`hello
		world
        today
        rain`;
```

4.模板字符串

```javascript
let name="user";
let age=30;
let msg=`Hello, ${name}`;
```

5.字符串长度

```javascript
console.log(str.length);
```

6.字符串不可变

<img src="C:\Users\little_scenery\AppData\Roaming\Typora\typora-user-images\image-20200915160157271.png" alt="image-20200915160157271" style="zoom:67%;" />

7.大小写转换

```javascript
//这里是方法，不是属性
student.toUpperCase()
student.toLowerCase()
```

8.student.indexOf('t')

9.substring

```javascript
student.substring(1) //从第一个字符串截取到最后一个字符串
student.substring(1,3)  //[1,3)
```

10.转换为字符串  toString()  &  String() 可返回null  undefined

```javascript
var num=10;
alert(num.toString());//"10"
alert(num.toString(2));//"1010"

var val1;
alert(String(null));    //"null"
alert(String(val1));	//"undefined"
alert(String(10));		//"10"
```

### 2.3数组

**Array可以包含任意类型的数据类型**

```javascript
var arr=[1,2,3,4,5,6]
arr[0]
arr[0]=1
```

1.长度

```javascript
arr.length
```

> 若给arr.length赋值，数组大小会发生变化，若赋值小于数组原长度，元素就会丢失

2.indexOf, 通过元素获得下标索引

```javascript
arr.indexOf(2)
1
```

3.slice()   截取Array的一部分，返回一个新数组，类似string中的substring

4.push() & pop()

```javascript
arr.push('a')  //将'a'压入尾部
arr.pop()    //弹出尾部的一个元素
```

5.unshift() & shift()

```javascript
arr.unshift("a","b")   //压入到头部
arr.shift()    //弹出头部的一个元素
```

6.排序 sort()

```javascript
arr=['d','a','b','c']
(4) ["d", "a", "b", "c"]
arr.sort()
(4) ["a", "b", "c", "d"]
```

7.元素反转  reverse()

```javascript
arr.sort()
(4) ["a", "b", "c", "d"]
arr.reverse()
(4) ["d", "c", "b", "a"]
```

8.拼接 concat()

```javascript
arr.concat([1,2])
(6) ["d", "c", "b", "a", 1, 2]
arr
(4) ["d", "c", "b", "a"]
```

> 该方法并未修改数组，只是会返回一个新的数组

9.连接符 join

打印拼接数组，使用特定字符串连接

```javascript
arr.join('-')
"d-c-b-a"
```

10. 多维数组

```javascript
arr=[[1,2],[3,4],["5","6"]]
arr[1][1]
4
```

### 2.4对象

若干个键值对

```javascript
var 对象名={
	属性名: 属性值,
	属性名: 属性值,
	属性名: 属性值
}

var person={
    name:"wendy",
    age:4,
    email:"wendy@126.com",
    score:100
}
```

JavaScript中的所有键都是字符串，值是任意对象

1.对象赋值

```javascript
person.name="irene"
"irene"
person.name
"irene"
```

2.使用一个不存在的对象属性不会报错 只是undefined

```javascript
person.habby
undefined
```

3.动态的删减属性，通过delete删除对象的属性

```javascript
delete person.name
true
person
{age: 4, email: "wendy@126.com", score: 0}
```

4.动态的添加，直接给新属性添加值

```javascript
person.habby="JAVA"
"JAVA"
person
{age: 4, email: "wendy@126.com", score: 0, habby: "JAVA"}
```

5.判断属性值是否在这个对象中  xxx  in xxx

```javascript
'age' in person
true
//继承
'toString' in person
true
```

6.判断一个属性是否是这个对象自身拥有的  *hasOwnProperty("属性名")*

```javascript
person.hasOwnProperty('age')
true
person.hasOwnProperty('toString')
false
```

### 2.5流程控制

1.if语句

```javascript
var a=3;
if(a>3){
	alert("Sun");
}else if(a<5){
    alert("Star");
}
else{
	alert("Moon");
}
```

2.循环

> while循环

```javascript
 while(a<100){
	a=a+1;
	console.log(a);
}
```

> for循环

```javascript
 for(let i=0;i<100;i++){
     console.log(i);
}
```

> forEach 循环

```javascript
var t=[1,2,3,11,32,134,43,22]
t.forEach(function (value) {
     console.log(value)
})
```

> for...in

```javascript
for(let i in t){
      console.log(t[i]);
}
```

### 2.6 Map和Set

> ES6的新特性

**Map**

```javascript
let map = new Map([['Kenn',100],['Louis',90],['Dan',80]]);
let name=map.get('Kenn');//通过key获得value
map.set('admin',123456);   //新增或修改
map.delete('Dan')  //删除元素
```

**Set**   无需不重复的集合

```javascript
var set =new Set([3,1,2,2])//set可以去重
set.delete(2);   //删除
set.add(6);   //添加
console.log(set.has(3));  //是否包含某个元素
```

