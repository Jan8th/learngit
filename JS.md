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

- 数值、文本、图形、音频、视频

- `number`  js不区分小数和整数，统一用`number`

- 字符串 `"abc"` `'abc'`

- 布尔值  `true`      `false`

- 逻辑运算 `&&`  `||`      `!`

- 比较运算符

- - `=`  赋值
  
  - `==` 类型不一样 值一样也会判断为true       e.g. 1 "1"相等
  
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
>

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

