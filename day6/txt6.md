## 
>- 对象.属性名
>- 对象['属性名']
>- 如果属性名是数字，不可以用**对象.属性名** 会报错
>- 利用变量的形式获取对应的属性值  ==> 对象[变量名]==可以去对象外[全局作用域]查找  再去window上去找 没有找到会报错  找到后返回值[空的为undefined]
```js
let a='name';
let obj={
    name:'nin',//'name':'nin'
    age:30,
}
console.log(obj[a])//nin
console.lod(obj.a)//undefined
```
- 属性值可以是一个表达式
- 如果属性名是数字，会优先排列在前面输出，而且从小到大依次排序。
- 如果属性名和属性值一样，只能写一个，效果一样
```js
let name='name';
let obj={
    name,//相等的值，同是字符串
}
console.log(obj[name])//'name'
```
```js
let a='we';
let name='name';
let obj={
    name:i&a//变量a
}
console.log(obj[name])//we
```
>在全局作用域中找变量名，要是找不到就去window[console.log(window)]找，找不到就报错，""返回undefined[第二条情况]，有什么就返回什么！
## 函数的深入理解
- 函数执行：函数名()===括号里放实参(实参和形参是一一对应关系) === 没有实参传入，形参里的变量值为undefined。
- return的功能：
   + >把函数的执行结果返回外界，阻断代码向下执行。
- 匿名函数
```js
//函数表达式
let fn = function(){}
fn();
```
- 自执行函数
```js
(function(){})();
!function(){};()
```
>(函数)里面可以拿外边的变量，但是外边不可以拿(函数)里面的量(函数私有作用域[私有栈内存])
## arguments
>函数内的arguments：实参的数值集合
```js
function fn(){
    // console.log(arguments)
    let num=0;
    for(var i=0;i<arguments.length;i++){
        num+=arguments[i]
    }
    return num;
}
let dd=fn(1,2,3,4,5);
console.log(dd)
```
## 箭头函数 (ES6)
```js
let fn=(n,m)=>{console.log(n+m)}
fn(1,2)
```
>如果形参只有一个，可以省略小括号
```js
let fn=m=>{
    console.log(m)
};fn(1)
```
>如果函数体内只有return一行代码，可以省略return和大括号
```js
let fn=(n,m)=>n+m
console.log(fn(1,2))
```
```js
//箭头函数和自执行函数结合
((n,m)=>n+m)(1,2)
```
>箭头函数没有arguments和this
## 给形参赋值默认值
>如果不传实参，就走默认值，传了就走实参的值
```js
function fn(n=1,m=1){
    console.log(n，m)//1，1
}
fn()//调用函数
```
>如果箭头函数返回的只是一个{}，那就把{}加上()[ES6规定]
```js
let fn=()=>({})//把{}用()包裹起来
console.log(fn());//{}
```
## 收缩(展开)运算符
```js
let fn=(...a)=>{
    //收缩运算符
    console.log(a)//[1, 2, 3, 4, 5] 数组形式
    //展开运算符
    console.log(...a)//1 2 3 4 5    数字形式
}
fn(1,2,3,4,5)
```
>arguments.callee指的是函数的本身，在严格模式下已经严格禁止。
```js
function fn(){
    console.log(arguments.callee)//函数本身
}
fn();
```