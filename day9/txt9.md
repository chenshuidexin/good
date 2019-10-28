# 区别
- 在赋值的时候，简单数据类型是按值操作
- 引用数据类型是按址操作
# 属性操作
- className
- href
- src
- value
- innerHTML
- innerTxet
# 变量
>可变的量，数据，把数据存储到一个自定义的名字中(用let/var声明)，达到复用的目的
- let==var==const==class A{}==import a from"../a.js"==
```js
document.getElementById('nn').style.width='100px';
```
## 手写push
```js
let ary=[1,2]
function push(ary,...arg){
    let ary2=[...ary,...arg]
    for(var i=0;i<ary.length;i++){
        ary[i]=ary2[i];
    }
    return ary2.length
}
console.log(push(ary,3,4,5))
```
# map
>map(callback,changeThis)循环数组，返回一个新数组，新数组和旧数组的长度一致
>callback(每个数据，索引，整个数组)=>回调函数(return后面是什么，新数组的成员就是什么)
```js
//手写map的代码
let ary=[1,2,3,4,5]
function map(ary,callback){
    let ary2=[];
    for(let i=0;i<ary.length;i++){
        ary2.push(callback(ary[i],i,ary))
    }
    return ary2;
}
console.log(map(ary,(item,index,all)=>{
    return [`<li>${item}</li>`].join('')
}))
//用法
let ary=[1,2,3,4,5]
console.log(ary.map((item,i,all)=>{
    return '<li>'+item+'</li>'
}))
//在body里上写ul标签
ul.innerHTML=ary.map(function(item,index,all){
    return '<li>'+item+'</li>'
}).join('')
```
# some(functio(){},x修改this指向)
>查看数组中的每个成员是否有一项是符合条件，只要有一个符合就返回true，否则false。
```js
let ary=[1,2,3,4,5];
let b=ary.some(function(item){
    return item >=11;
});
console.log(ary)
```
# every(回调函数，修改this指向)
>查看数组中的每个成员是否都符合条件,都符合返回true,否则返回false
```js
let ary=[1,2,3,4,5];
let bb=ary.every(function(item){
    return !!item===true;
})
console.log(bb);
```
```html
<!-- 全选和单选的小李子 -->
<!-- body上 -->
<div>
全选：<input type="checkbox" id="all"/>
</div>
<div id="b">
<input type="checkbox"/>
<input type="checkbox"/>
<input type="checkbox"/>
<input type="checkbox"/>
<input type="checkbox"/>
</div>
```
```js
const checkeds=document.querySelectorAll('#b input');
let aryChecked=[];
for(let i=0;i<checkeds.length;i++){
    aryChecked[i]=false;
    checkeds[i].onclick=function(){
        aryChecked[i]=this.checked;
        all.checked = aryChecked.every(item=>item)
    }

}
```
# filter(回调函数，修改this指向)
>过滤：把数组中符合条件的数据放到一个新数组中，并且返回这个新数组
```js
//函数机理
let ary=[true,false,false,false,false]
let newAry=[];
for(var i=0;i<ary.length;i++){
    if(ary[i] ===false){
        newAry.push(ary[i]);
    }
}
console.log(newAry)
//用法
console.log(ary.filter(item=>item===false));
```
# find(回调函数，修改this指向)
>查找符合的数据，找到就返回数据，找不到就返回undefined。  
```js
let 
function find(ary,callback){
for(var i=0,i<ary.length;i++){
    let b=callback(ary[i],i,ary)
    if(b){
        return ary[i]
    }
}
// return null;
}
let f=find(ary,function(item)=>item==='李磊');
console.log(f);
//用法
console.log(ary.find(item=>item.name==='xx'));
```
# findIndex(回调函数，修改this指向)
>查找回调函数中，符合规则数据所对应的索引值，找到就返回索引值，找不到就返回-1。
```js
ary.findIndex((item)=>item.name==='xx')
//返回的是索引值，找不到为-1
```
# flat(数组扁平化)
>数组里有多少个[]就写多少(数字)
```js
let ary=[1,2,[3,4,5],6,7,8];
let aa=[];
function flat(ary){
    ary.forEach((item,i)=>{
        if(Array.isArray(item)){
            //Array.isArray()检测数据是否为数组，是为true否为false。
            flat(item);//回调函数
        }else{
            aa.push(item);
        }
    })
}
flat(ary);
console.log(aa);
//另一种写法
function flat(ary){
    for(var i=0;i<ary.length;i++){
        if(!!ary[i].push){//数组
            flat(ary[i])
        }else{
            aa.push(ary[i])
        }
    }
}
flat(ary);
console.log(aa);
//用法
console.log(ary.flat(Infinity));//Infinity无穷大 属于数据Number类型
```
# reduce(回调函数，修改this指向)
>计数,本次返回的结果会作为下一次的上一次进行计算。
```js
let ary = [1,2,3,4,5];

let num = ary.reduce(function(prev,next){
console.log(prev);
return prev + next;
},0);
console.log(num);
```
# 
## Math方法
>存着数学属性和方法  console.dir(Math)
- 圆周率=========Math.PI
- 向上取整=======Math.ceil
- 向下取整=======Math.floor
- 四舍五入=======Math.round
- 绝对值=========Math.abs
- 最大值=========Math.max
- 最小值=========Math.min
- 取幂===========Math.pow
- 0-1之间无限不循环小数==Math.random
```js
let ary=[1,2,3,4,5]
console.log(Math.max(...ary));//(xxx)里面是数字而不是数组
//原生random的代码
function random(n,m){
    return Math.round(Math.random()*(m-n))+n
}
comsole.log(random(0,5))
```
```js
//获取四位数随机验证码
let
str='1234567890qwertyuiopasdfghjklzxcvbnmQWERTYUIOPASDFGHJKLZXCVBNM'
let obb='';
for(var i=0;i<4;i++){

obb +=str[return Math.round(Math.random()*(str.length-1))]
}
console.log(obb);
```
# 
# Data日期
>Date:记录计算机当前的时间(本地)==console.dir(Date)==不安全==使用服务器时间(安全))
- new Date() 当前的时间
- new Date(传入一个时间)
```js
let date=new Date;
console.log(date.getFullYear());//获取当前的年份
console.log(date.getMonth()+1);//获取当前的月份
console.log(date.getDate())//获取当前的日期
console.log(date.getDay())//获取当前的周几//周日为0
console.log(date.getHours())//获取当前的小时
console.log(date.getMinutes())//获取当前的分钟
console.log(date.getSeconds())//获取当前的秒数
//1s=1000毫秒
```
## 时间戳 1970年到现在的时间
```js
console.log(Date.now())//格林威治时间1970年01月01日00时00分00秒(北京时间1970年01月01日08时00分00秒)起至现在的总秒数
let data=now Date;//时间戳
console.log(+date);
```
# 
## 定时器
>setTimeout:到了指定时间之后执行函数==console.dir(window)==只执行一次
>setTimeout(回调函数，间隔时间（毫秒），回调函数的实参)
>返回值是一个数字
```js
setTimeout(function(){
    alert('ss');
},2000)
//回调函数的实参
setTimeout(function(t){
    alert('ss');
    console.log(t)
},2000,66)
//返回值
let timr=setTimeout(function(){
    alert('ss');
},2000)
console.log(timr)//一个数字
```
## 关闭定时器
>clearTimeout(定时器的返回值，编号)
```js
btn[i].onclick=function(){//点击关闭计时器
    clearTimeout(timr);
}
```
## setInterVal =>一到指定时间之后执行函数==重复多次
>setTimeout(回调函数，间隔时间（毫秒），回调函数的实参)
```js
setTimeout(function(){
    alert(66)
},2000)
```
## clearInterVal(定时器的返回值，编号)
# 计时器的应用案例
```css
    *{
        margin: 0;
        padding: 0;
    }
    #box{
        position: absolute;
        top: -300px;
        left:0;
        width: 300px;
        height: 300px;
        background: lightcoral;
        transition: 2s;
    }
```
```js
//框架
    <button id="btn">停止</button>
    <div id="box">
//色块自动走自动留
        setTimeout(function(){
            box.style.top=0;
            setTimeout(function(){
                box.style.top='-300px';
            },5000)
        },5000)
//小案例
//定时器和关闭定时器的应用
        let timer=setTimeout(function(t){
            box.style.top=t;
        },2000,0)
        btn.onclick=function(){
            clearTimeout(timer);
        }
        box.onclick=function(){
            box.style.top='-300px';
        }
```
# 数码时钟的案例
```js
//框架
    <div id="box"></div>
    // <script>
        function fn(){
            let d=new Date;
            let str=d.getFullYear()+'年'+(d.getMonth()+1)+'月'+d.getDate()+'日'+d.getHours()+'时'+d.getMinutes()+'分'+d.getSeconds()+'秒';
            box.innerHTML=str;
        }
        fn();//执行定时器中的函数，是一秒钟之后，但是一秒之前页面中是不会显示的
        //所以要在定时器调用之前执行一次fn函数
        setInterval(fn,1000)
    // </script>

```
# 倒计时安利
```js
 <div id="box"></div>
    // <script>
    let d=new Date('2019 10 27 09:20');
    function fn(){
        let d2=new Date;//现在的时间
        let t=Math.floor((d-d2)/1000)//秒
        console.log(t)
        let dd=Math.floor(t/86400);//向上取整数是天
        t%=86400;//余下的还是秒，重新赋值
        // console.log(dd)
        let Hour=Math.floor(t/3600);
        t%=3600;
        // console.log(Hour)
        let mi=Math.floor(t/60);
        t%=60;
        console.log(mi)
        box.innerHTML=dd+'天'+Hour+'时'+mi+'分'+t+'秒'
    }
fn();//执行定时器中的函数，是一秒钟之后，但是一秒之前页面中是不会显示的
//所以要在定时器调用之前执行一次fn函数
setInterval(fn,1000)
```