## 把下面的程序改写成为三元运算符，并算出结果
```js
 let a = 12;
 if (a >= 0 && a <= 20) {
     if (a % 2 === 0) {
         a += 2;
     }
 } else {
     a -= 2;
 }
 console.log(a);//14
 >a>=0 && a<=20?(a%2===0?a+=2:null):a-=2
 ```
 ## 算出输出的结果
```js
let a = '10';
a == 10 ? a++ : a--;
console.log(a);//11
​
//switch case 比较的是全等 ===
let b = '10';
switch (b) {
    case 10:
        b++;
        break;
    default:
        b--;
}
console.log(b);//9
```
## buer
```js
!(!"Number(undefined)");//true
​
isNaN(parseInt(new Date())) + Number([1]) + !undefined;//3
​
Boolean(Number("")) + !isNaN(Number(null)) + Boolean("parseInt([])") + !!null;//  2
​
parseFloat("1.6px") + parseInt("1.2px") +  parseInt(null);//NaN
​
isNaN(Number(!!Number(parseInt("0.8"))));//fasle
​
console.log(1 + "2" + "2");//122
​
parseFloat("0");//0
​
Number("");//0
​
"parseInt(null)" + 12 + !!Number(NaN);//parseInt(null)12false
​
! (isNaN("")) + parseInt(NaN);//NaN
​
!parseInt(null) + !isNaN(null);//2

! false == !! true;//true

parseInt('35.4.2') === parseFloat('35.A.2')//true

!Number(undefined) == isNaN( Boolean('') )//false

[] == [];//false
'' == 0;//true
[0] == false;//true
true == 1;//true
({}) == '';//false
'12' > 2;//true
'12' > '2';//false
[] == 0;//true
****0 == null;//false****
'{}' == 1;//false
undefined == null;//true
null == undefined ;//ture
{name:1} == {name:1};//false
undefined == 0;//false
```
## 输出以下结果
```js
let i=0  
console.log(i++ == ++i)  //false
console.log(++i == i++)  //true
console.log(i);//4
```
## 如何判断一个数字为整数？（用浏览器的方法来判断）
```js
通过parseInt(xx)===parseFloat(xx)结果为true
function fn(num){
    if(num === parseInt(num)){
        alert("整数")
    }else{
        alert("重新")
    }
}
```
```js
    function isInteger(num) {
        if (!isNaN(num) && num%1 === 0 ) {
            return true;
        }else{
            return false;
        }
    }
    var a = 8; //给a赋的值就是需要进行判断的数字
    var isNum = isInteger(a);
    console.log(isNum);
//当返回值为true时，需要判断的数字为整数
```
## 把其他数据类型转换为数字有几种转换方式？
- >Number()转化
- >parseInt()/parseFloat()转化
- >四则运算
## js的数据类型有哪些？
- >基本数据类型：Number，String，Boolean，null,undefined
- >引用数据类型：
    + 对象======普通对象，数组对象，数学对象，日期对象，正则对象
    + 函数对象