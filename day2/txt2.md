## Js是一种客户端语言
> js是一种客户端语言，不仅要操作dom对象，还要操作浏览器的某些功能
- ECMAScript ES3/5(老版本规范) ES6/7(新语法规范)：提供变量语法操作语句等
- DOM(document object model)：提供一些js的属性和方法，用来操作页面中的dom元素
- BOM(browser object model):提供一些js属性和方法，用来操作浏览器
## parseInt  转数字
> 从左往右依次查找，一旦遇到非有效数字，就停止查找，把数字返回
  - 如果把数组转化为数字，那就是数组的第一项，
## parseFloat   转数字
>从左往右依次查找，一旦遇到非有效数字(第一个小数点除外)，就停止查找，把数字返回
## string字符串类型
> 用单引号、双引号、反引号[es6模板字符串]
- 把别的数据类型转化为string类型[val.toString();字符串拼接]
## val.toString
+ 把对象转字符串 ==>'[Object,Object]'
+ 把数组转换为字符串；把数组的括号去掉，然后用字符串
+ 把数字，布尔值转化为字符串：直接加引号
+ 把null和undefined不能直接调用toString方法，会报错，（可以使用字符串拼接）
## 四则运算（加法有可能出现字符串拼接）
-  在四则运算中包括加减乘除，除了加法，其他的都是正常科学运算
- 加法就有可能出现字符串拼接，如果在加法中出现了字符串，那就不是数学运算就是字符串拼接
- 载入在运算的时候出现了不是数字类型的值，先把值转换为数字类型然后再运算
- 在转换的时候遇到字符串时就直接拼接
   + []+{} ==>'[Object,Object]'
   + [123]+{name:'aa'}==>"123[Object,Object]"
- 运算过程中出现NaN,结果为NaN。
   + []+[] ==>""
   + {}+{} ==>"[Object,Object][Object,Object]"
   + unde==>会报错   不是基本数据类型浏览器识别不出来
   + Number ==> 会出现number函数
- 在拼接过程中如果出现有数组或者普通对象，要转化为字符串。
## Boolean 布尔
> false/ture
- Boolean
- ！/！！
- if 判断
## false
其他的数据类型转化false:false,null,undefined,0,NaN,空字符串
## ！和！！
- 取反：先把值转换为布尔值再取反值
- ！！转换布尔值
## if条件判断
>如果判断的条件转布尔是true，就执行大括号里的代码，如果是false就不执行。
## null和undefined
> null和undefined代表空
- null 空对象