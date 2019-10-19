## for in
>一般用于遍历对象
- key代表对象的属性名，而且是字符串类型。
- 有多少键值对就会循环多少次
- 在for in循环中，获取属性名对应的属性值只能用xx[属性名]形式。
- 如果属性名是数字，那么就会按照从小到大的顺序在前面输出。
```js
let obj={
    name:'ni',
    age:4,
    hobby:'ff'
}
for(let a in obj ){
    console.log(a);//属性名
    console.log(obj[a])//属性值
}
```
## while
- 一般用于不知道输出多少次的循环
```js
var i=3;
while(i>0){
    console.log(100);
    i++;
}
li[i].index=i
```
# 选项卡
