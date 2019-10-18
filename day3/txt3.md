## object的普通对象
>{name:"nijao"，age:20;}
- 任何一个对象外层由大括号包裹，由0到多组键值对组成，键值对之间用逗号隔开，每一个键值对由属性名和属性值组成，属性名由字符串或者数字组成[属性名不能重复]   => {[key]:[value],...}
- 属性名不能重复，如果重复了就会后面的覆盖前面的值
- 查找属性：对象.属性名、对象['属性名']
  > 如果属性名是数字，只能用{对象['属性名']}去获取。
- 新增键值对：对象.属性名="xxx"(如果有这个属性名就是修改，如果没有就是新增)
- 删除： 
     + 假删除：手动赋值为null
     + 真删除： delete 对象.属性名
## 数组
>[1,3,4,5,"dc"]
- 外层由中括号包裹，里面写的是属性值，它的属性名是数字，从0计数依次递增，并且代表值的位置  => 索引
- length：代表着组的长度，也是数组值的个数
- 数组的第一项索引值为0
- 在数组末尾追加一项 => ary[ary.length]
## 堆栈内存的区别（阿里面试题）
>浏览器运行代码要有两个条件：
 - 1.在内存分配出一块内存去执行代码（提供代码执行的环境）
 - 2.提供一个主线程来运行代码（提供代码执行者）
> - 1.创建一个变量放到变量存储区
> - 2.创建一个值，如果是一个基本数据类型就直接放到值存储区，如果是引用数据类型就**执行以下代码**
> - 3.=把值赋值给变量
> - 4.执行以下代码：开辟一个堆内存，生成一个16进制的地址=======把值储存进去=======把16进制的地址放到值存储区
## 数据类型比较
> - 对象==对象    比较的是对象地址(永远不相等)
> - 对象==数字    比较的是数字类型
> - 对象==字符串  比较的是字符串比较
> - 对象==布尔    比较的是数字类型
> - 数字==字符串  比较的是数字类型
> - 数字==布尔    比较的是数字类型
> - 字符串==布尔  比较的是数字类型
- **null，undefined和其他值都不相等，自身相等===[null==undefined]//true**
- **NaN和其他值都不相等，包括自己本身**
### ===    全等
### 逻辑运算符
> - '-' ,'+','%','*','/'
> - i++;++i
> - i--;--i
> - -=/+=(自增)
## js的操作语句（for循环，if判断语句）
- if/else if
- 三元运算符
- swith case
### if/else if/else
*** ||   有一个条件成立走结果 ***

*** &&    两个条件都成立走结果 ***

## 三元运算符
> 判断的条件？条件成立的结果：条件不成立的结果;

>一定要有占位符，不能空着
## swith  case
>适应多种条件多种结果，必须要break来结束执行，否则会贯穿。
```js
 switch(val){
    case 1:
  console.log(1);
    break;
    case 2:
    console.log(2);
    break;
    default:
    console.log(3);
  }
  ```