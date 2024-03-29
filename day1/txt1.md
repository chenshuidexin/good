## 第一天笔记
- web1.0：静态页面
- web2.0：动态页面
   + 1.弱前端时代：服务端渲染
   + 2.客户端渲染
- 前端侵占移动端市场
- node.js
## 前端三大核心知识
- HTML  结构
- CSS   样式
- JS    行为   能让整个页面动起来
>JS的出现其实是为了页面与用户进行交互的
>应用：开发pc端，移动端，服务器
## 浏览器
- webkit (v8引擎)
  + 谷歌
  + 手机浏览器
  + 国产的浏览器
- Gecko 
  + 火狐
- Presto
  + 欧朋
- Trident
  + IE
  + IE EDGE()

  ## 浏览器的控制台  [F12或FN+12]
- Elements:可以查看或调整页面的元素样式
- Console:可以运行代码，可以打印console的值
- NetWork:存放的是所有的资源请求
- Sources:存放的是页面所有的资源文件
- debugger:可以详细看见运行流程
## JS
> JS作为客户端的一种语言，不仅要做操作DOM对象，还要操作浏览器的基本功能
- ECMAScript3/5(老版本)  ES6/7等(新语法规范):规定了js的语法，变量，操作语句
- DOM:文档对象模型(document object model)提供一些js的语法和功能来操作页面中的DOM元素。
- BOM:浏览器对象模型(browser object model)提供一些js的属性和功能来操作浏览器。
## JS中的变量
- 创建变量 let 变量名=值;(es6新增)
+ 创建变量 var 变量名=值;
- 创建常量 conset (es6新增)
- function 创建函数变量
- class  F{}创建函数
- import a from '../a.js'  es6的语法导入
- symbol 创建唯一值
## JS的使用方式
- 内嵌式
   + 直接在标签身上写JS
- 内联式
   + script标签放到body结束标签的上方
- 外联式
   + 通过script标签的src属性，添加../xx.js文件(不只是.js文件)的路径 
>如果使用了外链，script标签中的代码是不响应的
## js的命名规范
- 严格区分大小写；
- 由数字、字母、下划线、$组成，但是不能以数字开头
    + _a  代表公共变量
    + $a  在JQ中获取什么什么，都是以$开头
- 不能以保留字或者关键字作为变量
- 变量名为驼峰命名法(变量名的开头一个单词开头小写，以后每一个有意义的单词开头都大写)
## 调试的方式
- alert()=========浏览器默认弹框
- console.log()===浏览器打印输出
- console.dir()===浏览器打印输出内部细节
>读操作===输出、打印、弹框
>写操作===改变、设置、赋值
## 表单内容
>获取表单元素的内容，要使用value属性才能获取到select框[选择框、option]、input框[表框]、textarea框[文本框]
>background在读操作的时候，每个浏览器显示的是不一样的。
>img标签的src属性读取的时候获取绝对路径
>a标签禁止跳转使用[href="javascript:;"]
## js中的数据类型
- 基本数据类型
   + number
   + string
   + boolean
   + null
   + undefined
   + symbol
- 引用数据类型
   + 对象数据类型 object
       - {name:xxx，age：www,} 普通对象
       -  [] 数组对象
       - Math  数学对象
       - /^$/  正则对象
       - Date  日期对象
   + 函数类型  function
- 基本数据类型之number
  + 包括NaN和有效数字
>NaN (not a  number) 
+ 把其他值转化为数字  
   - 只要字符串中出现非有效数字，那么结果就是NaN(第一个小数点不算)
   - 空字符串转化数字为0
- 把布尔值转化为数字
     + Number(false)//0
     + Number(true)//1
- null和undefined
   - Number(null)//0
   - Number(undefined)//NaN
- NaN转化数字
  - Number(NaN)//NaN
  - NaN和任何值都不相等，包括自己本身
- 引用数据类型转化数字  
  - 普通对象转化数字，是先把对象转化为字符串，然后在转化为数字
  - Number({})//NaN    ({}).toString()//[Obiect,Obiect] 
- 数组转化数字
  - Number([12,13])//转化为字符串 按字符串方法走
- isNaN 检测数据类型值是否是非有效数字，是返回true，不是返回false。
>在js中变量值如果出现文字(英文，中文...),要么是变量要么是字符串。