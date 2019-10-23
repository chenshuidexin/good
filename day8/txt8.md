## 字符串的方法
- str.length 字符串的长度
- str[0]   字符串的第一项
- str[str.length-1]  字符串的最后一项
- str.length--  不能删除字符串的最后一项
- str[str.length]='x'  不能增加字符串的最后一项
>- 通过length不能操作字符串
>- 字符串的方法都不会改变原字符串
>- 1.charAt:通过索引获取指定的字符串
>- 2.charCodeAt:通过索引找到对应的ASCII码（Unicode编码）
```js
str.charAt(100)//''
str[100]//undefined
str.charCodeAt(2)//获取对应的编码
String.fromCharCode(97)//通过值获取相对应的图形
```
### 字符串的查询
- substr(n,m):从索引n开始，查询m个
```js
console.log(str.substr(0))//查询到底
console.log(str.substr())//查询到底
```
- substring(n,m):从索引n开始，查询到索引m（不包括索引m对应的那一项）
```js
console.log(str.substring(0))//查询到底
console.log(str.substr())//查询到底
```
- slice(n,m):从索引n开始，查询到索引m（不包括索引m对应的那一项）====支持负数
```js
console.log(str.slice(-1,-3))//每一个参数加上length后在取值  ''
console.log(str.slice(-3,-1))//前面的值比后面的值要小
```
>如果传的参数是负数，那就把负数+length然后再取值
- indexOf(x,y):检测某个值在字符串第一次出现的位置，把对应的索引值返回去
- lastIndexOf(x,y):检测某个值最后一次出现的位置，把对应的索引值返回去
- 没有就返回-1
```js
console.log(str.indexOf('qq',2))//查找的值，开始查询的位置
```
- includes：查询某个值有没有，有就返回true没有就返回false
- 字符串转化字母大小写,不涉及到其他的影响
-返回值就转化完成的字符串
```js
str.toUpperCase()//转字母大写
str.toLowerCase()//转字母小写
```
-  把字符串转数组
- split：把字符串以指定分隔符分割为数组
- 一般是和join组合使用。
```js
str.split('')//默认为一个字符串占一个数组
str.split()//默认为原数组
//把str转化为以逗号分割的字符串
str.split('|').toString()
str.split('|').join()
```
- replace(老字符，新字符)：替换
```js
let str='sdgwwfde'
console.log(str.replace('w','q'))//正常来说替换成第一个
console.log(str.replace('w','q').replace('w','q'))//有两个替换就出现两个replace即可。
console.log(str.replace(/w/g,'q'))//正则全部替换
```
```js
let str='2019-10-23 12:33 '
console.log(str.replace('-','年').replace('-','月').replace(' ','日').replace(':','时').replace(' ','分'))
//如果替换失败就返回原字符串
```
```js
let  sst='https://www.baidu.com/?name=nihao&age=null&sex=null'
let index=str.indexOf('?')//21
let newStr=str.substring(index+1)//获取索引值(21)之后的所有值(链接的参数)
//str.split('?')[1]//获取的是？之后的值(获取链接的参数)
let ary=newStr.split('&')
for(var i=0;i<ary.length;i++){
    let cur=ary[i];
    let newAry=cur.split('=')
    obj[newAry[0]]=newAry[1];
}
console.log(obj);
```
## 