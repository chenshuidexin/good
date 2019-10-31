# DOM
- ECMAScript:标准语法=====进行一些数据的操作。
- DOM:document object model     文档对象模型
>它的出现就是通过document提供的api(接口文档)，赋予开发者操作页面的能力。==console.dir(document)
- 如果要操作某个元素，首先要先获取出来  document。。。
- 获取的元素是个对象，在js中，标签和对象是相映射的关系。修改对象下的属性有可能会改变标签，修改标签会修改到对象身上。
>## 难点 ==复杂关系  
>- DOM树-把页面中所有的节点组织在一个树形结构中，方便我们通过关系去操作页面。
>- 节点：页面中所有内容都是由不同节点组成的
    >+ 元素节点=====>标签,{},[],''=====1
    >+ 注释节点=====>注释==============8
    >+ 属性节点=====>标签上的属性=======2
    >+ 文本节点=====>文字，回车，空格===3
    >+ 文档节点=====>document=========9
>+ 查看节点类型==>nodeType======返回数字
>+ 操作节点内容==>nodeValue=====返回内容
>+ 读取节点名字==>nodeName======返回名字
>- 查找当前元素下的所有子节点==childNodes
>- 查看属性节点===============attributes
## 
>- 查找当前元素下的所有子节点====childNodes
>- 查找当前元素下的元素子节点====children
>- 查找父级的第一个子元素========firstElementChild
>- 查找父级的最后一个子元素======lastElementChild
>- 查找上一个兄弟元素节点=====previousElementSibling
>- 查找下一个兄弟元素节点========nextElementSibling

## 
>- 查找某个元素的父级节点======parentNode
# 手写一个children
```js
   <ul id="ul">
       <!-- li*5{$} Tab键 -->
       <li>1</li>
       <li>2</li>
       <li>3</li>
       <li>4</li>
       <li>5</li>
   </ul> 
   /*
   1.通过childNode去拿到所有的子节点
   2.通过判断这些子节点哪个是元素子节点
   3.是的话就push到一个数组
   4.最后把数组再返回去
   */
   function children(parent){
       //如果是字符串就获取
       //是元素就不需获取
       if(typeof parent ==='string'){//字符串类型获取元素
           parent=document.querySelector(parent);//获取变量parent的所有元素
       }else if(parent.nodeType === 1){//元素节点
           parent=parent;
       }if(parent === null)return '正确传参'
    //    console.log(parent);
       const childrens=parent.childNodes;//获取所有子节点
       let arr=[];
       for(let i=0;i<childrens.length;i++){
           if(childrens[i].nodeType === 1){//节点类型是元素节点
               arr.push(childrens[i]);//数组增加
           }
       }
       return arr;
   }
   console.log(children('ul'))//'#ul'   ul  都可以获取到。
```
## 增删改
- 创建元素
>回流(重排):当某个元素发生了几何、位置。。的变化，会使页面局部刷新，导致整个页面刷新;
>重绘:元素几何、坐标。。不发生改变，只是外观、颜色、风格发生变化的时候会导致某个样式重新绘制
>不管是回流还是重绘，都是性能的杀手。我们要进可能去少操作DOM，页面至少会回流一次，页面进行一次加载。
>回流一定重绘，而重绘不一定会导致回流
>```js
   >  //基本操作
   > ul.innerHTML+="<li>+i+</li>"
   >//重新加载页面
   >//性能优化
   >let html='';
   >for(var i=0;i<500;i++){
   >html+='<li>'+i+'</li>'
   >}//时间更短
   >ul.innerHTML=html;
>```
   >- document.createElement('标签名')
   >- 让元素的末尾添加一个元素:
        >- parent.appendChild(child)
- 删除元素
 - >parentNode.removeChild(删除的元素)
 - >parentNode.appendChild(元素) 方法在指定元素节点的最后一个子节点之后添加节点。 
- 增加元素
- >parentNode.insertBefore(插入新元素，老元素) 把新元素插到老元素的前面
- 改元素
  - >parentNode.replaceChild(新元素，老元素)
  ```js
  //看本文件中的第7个
  ```
>页面中通过元素属性获取出来的都是字符串
classList 元素对象的类名
- add 添加一个或多个class
- contains 指定的class是否存在是的话true 否则为false
- remove删除一个或多个class
- replace(老的，新的) 替换class
- toggle(开关的效果)
### 行间属性
- element.getAttribute('属性名') 获取标签身上行间的属性
- element.setAttribute('属性名','内容') 设置行间属性
- element.removeAttribute('属性名') 删除行间属性
>除了标准中定义的行间属性(id,class),别的行间属性都在attributes上，也就是说直接通过对象.属性去查找行间属性，一般是找不到的，因为对象上就没有定义过(undefined)，标准行间属性和自定义行间属性，他们所在的空间地址是不一样的。
>使用对象下的xx去访问的属性，要通过对象下的xx去创建才能访问得到
>使用getAttribute获取的标签上的自定义属性，要通过手写标签上的属性，要setAttribute设置才能访问的到
>img.getAttribute('src')===可以避免获取到的路径是绝对路径的情况