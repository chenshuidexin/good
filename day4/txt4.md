## 数据类型检测
- typeof  ==检测数据的属性（不是方法）
- instanceof ==检测当前实例是否属于某个类
- constructor ==基于构造函数检测类型
- Object.prototype.toString.call() ==检测数据类型最好的方法
## typeof
- 检测的返回值一定是一个小写字符串 => "unmber"=>typeof(typeof(null))//'string'
- 字符串里放的是检测出来的类型
- typeof null ==> "object"
- 检测对象返回的都是"object",不能够详细区分数组和普通对象
## typeof 一元运算符 全局函数 检测7中数据类型
- 'number'
- string
- 'boolean'
- 'undefined'
- 'symbol'
- 'object'
- 'function'
>typeof (null)==>'object'==空对象
## 循环
- for
- while
- for in
- for of(ES6)
## for
>重复做某一件事

- 创建循环的初始值
- （设置）判断循环执行的条件
- 执行循环中的内容
- 当前轮循环结束，进行累计操作
- continue:结束当前轮循环==[跳过继续循环]
- break:结束整个循环=====[跳出不在循环不管后面的代码]
## 函数
函数就是一个方法或者一个功能，函数就是把实现某个功能的代码放在一起进行分装，以后想要实现这个功能，只需要把函数执行即可 =>“封装”：减少页面中的多余代码，提高代码重复利用率。[高内聚低耦合]
- 创建函数
   + 形参
   + 返回值
- 执行函数
  + 函数名(  )
  + 实参的概念
## 函数的形参和实参
- 创建函数，实参没有给形参赋值会出现undefined
- 形参跟实参是一一对应的关系
- 函数返回值return返回调用的位置
- return在函数里起到**阻断代码向下运行**的作用
## 点击事件
```js
//函数声明
let fn=function(){}
//自执行函数
(function(){})()
```
- >详细输入对象的信息  ===>console.log(xxx)
- >id:元素的id
- >className:元素的class姓名
- >innerHTML:元素的内容（识别标签）
- >innerText:元素的内容（不可以识别标签）
- >style:元素的行内样式（是一个对象）