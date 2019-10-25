## 数组方法
- 数组中存放的属性值，他的属性名是浏览器规定的，是从数字0开始依次递增，代表每一项的位置，数组的属性名叫索引
- 天生自带length属性，代表数组的长度
- 获取数组的最后一项：ary[length-1]
- 获取数组的第一项：ary[0]
- 增加数组的最后一项：ary[ary.length]
## 方法的含义
- 数组的增删减
    - push：向数组末尾增加内容
    - 传递的实参：可以传多个js数据值
    - 返回值：新数组的length
    - 原数组发生变化
    ```js
    let ary=[12,14,16,13,3,6];
    console.log(ary.push(11,78,45,25))//新数组的长度
    console.log(ary)
    ```
    >其他增加数组的方法：ary[ary.length]  数组length的方法   ========[...ary,1,5,6,4]  扩展运算符
    - unshift：项目组开头增加的内容
    - 传递的实参：可以传多个js数据值
    - 返回值：新数组的length
    - 原数组发生变化
    ```js
    let ary=[12,14,16,13,3,6] 
    console.log(ary.unshift(1))//7 新数组的长度
    ary[0]='ss';//修改值  重新赋值
    ary[-1]='aaa';//会破坏数组的原有结构
    console.log(ary);
    ```
    - shift：删除数组开头的第一项
    - 传递的实参：不传
    - 返回值：删除的那一项
    - 原数组发生变化
    ```js
    let ary=[12,14,16,13,3,6] ;
    console.log(ary.shift());//[12]
    console.log(ary);
    ```
    >delete ary[0] =>empty//破环数组结构
    - pop:删除数组末尾的一项
    - 传递的实参：不传
    - 返回值：删除的那一项
    - 原数组发生变化
    ```js
    let ary=[12,14,16,13,3,6] ;
    console.log(ary.pop())//[6]
    console.log(ary)
    ```
    >- ary.length=ary.length-1;
    >- ary.length--;
    - splice:实现数组的增删改
    - 传递的实参：看情况
    - 返回值：看情况
    - 原数组发生变化
    ```js
    //(n,m)：从索引n开始，删除m个  (n):从索引n开始删除到末尾
    //返回值是一个新数组，里边存储的是删除的那几项
    let ary=[12,14,16,13,3,6] ;
    console.log(ary.splice(1,2));//[14,16]
    console.log(ary.splice(2));//[16,13,3,6]
    console.log(ary.splice(0,1))//删除数组的第一项
    console.log(ary.length-1)//删除数组的最后一项
    console.lof(ary.splice(0));//复制整个数组
    console.log(ary);
    ```
    ```js
    //(n,m,x)从索引n开始，删除m个，用x替代(可以修改、新增值)
    //(n,0,x)在索引n值前面增加x
    //返回值是一个新数组，里边存储的是删除的那几项
    let ary=[12,14,16,13,3,6] ;
    console.log(ary.splice(1,2,"xixi","haha"))//[14,16]   替换的写多少都会显示出多少
    console.log(ary.solice(1,2,5))
    console.log(ary.splice(1,0,3))//[]
    console.log(ary.splice(0,0,1))//[]增加数组第一项
    console.log(ary.splice(ary.length,0,'ee'))//增加数组的最后一项
    console.log(ary)
    ```
    ## 向数组末尾增加一项
    - push
    - ary[ary.length]='xxx'
    - ary.splice(ary.length,0,'x')
    - [...ary,1,2]
    ## 向数组开头增加
    - unshift
    - ary.splice(0,0,9)
    - [1,2,3,...ary]
    ## 删除数组的最后一项
    - pop
    - ary.splice(ary.length-1)
    - ary.length--
    - ary.length=ary.leng-1
    ## 删除数组的第一项
    - shift
    - ary.splice(0,1)
- 数组的查询和拼接
    - slice：查询数组中的某一项
    - 传递的实参：看情况
    - 返回值：一个新数组，里面是存储查询的几项
    - 原数组不发生变化
    ```js
    //(n,m)：从索引n开始，查询到索引m(不包含索引m对应的项)
    let ary=[12,14,16,13,3,6]
    console.log(ary.slice(2,3))//[16]
    console.log(ary.slice(0));//数组浅克隆
    consolr.log(ary.slice());//数组浅克隆
    console.log(ary)
    ```
    - concat:数组拼接
    - 传递的实参：js数据值
    - 返回值：拼接后的新数组
    - 原数组不发生变化
    ```js
    let ary1=[1,2,3]
    let ary2=[4,5,6]
    console.log(ary1.concat(ary2,7,8,9))
    console.log(ary1);
    //第二种方法
    let newAry=[...ary1,...ary2,5,4,3,2,1]
    console.log(newAry)
    ```
    - toString:把数组转化为字符串  
    - 传递的实参：无
    - 返回值：转化完成的字符串
    - 原数组不发生变化
    ```js
    let ary=[12,14,16,13,3,6]
    console.log(ary.toString());
    console.log(ary);
    ```
    - join:把数组以指定的分隔符转化为字符串
    - 传递的实参：字符串类型的分隔符
    - 返回值：转化完成的字符串
    - 原数组不发生变化
    ```js
    let ary=[12,14,16,13,3,6]
    console.log(ary.join('$'))
    console.log(ary.join())//默认为逗号分隔符
    console.log(ary.join(''))//默认为空分隔符
    console.log(ary)//原值不变
    console.log(eval(ary.join('+')))//进行数字运算
    ```
    - indexOf和lastIndexOf：检测数组中的某一项
    - 传递的实参：要检测数组某一项第一次和最后一次索引出现的位置
    - 返回值：有就返回索引值没有就返回-1
    - 原数组不发生变化
    ```js
    let ary=[12,14,16,13,3,6]
    console.log(ary.indexOf(16))//2
    console.log(ary.lastIndexOf(16))//2
    console.log(ary.indexOf(11));//-1
    
    ```
    - includes:检测数组中是否包含某一项
    - 传递的实参：想要检测的值
    - 返回值：有就返回true;没有就返回false
    - 原数组不发生变化
    ```js
    let ary=[12,14,16,13,3,6]
    console.log(ary.includes(16))//ture
    console.log(ary.includes(2)//false
    ```
    - reverse:数组翻转
    - 传递的实参：无
    - 返回值：排序之后的数组
    - 原数组发生变化
    ```js
    let ary=[1,9,3,6]
    console.log(ary.reverse())
    console.log(ary)
    ```
    - sort：给数组排序
    - 传递的实参：函数 空
    - 返回值：排序之后的数组
    - 原数组发生变化
    ```js
    let ary=[1,9,3,6]
    console.log(ary.sort())
    //如果不传参，只能给个位数排序
    //如果排序的数组里有两位数就得用传参的方式去处理
    console.log(ary.sort((a,b)=>b-a))//降序
    console.log(ary.sort((a,b)=>a-b))//升序
    ```
    - forEach:遍历数组
    - 传递的实参：函数 
    - 返回值：
    - 原数组不发生变化
    ```js
    let ary =['q','e','f','r','u']
    ary.forEach((item,index)=>{
        //item数组每一项的值
        //index数组每一项的索引值
        //数组有多少项就循环多少次
        console.log(item,index)
    })
    ```