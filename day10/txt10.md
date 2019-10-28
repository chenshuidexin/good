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
```js

```
>- 查找当前元素下的所有子节点====childNodes
>- 查找当前元素下的元素子节点====children
>- 查找父级的第一个子元素========firstElementChild
>- 查找父级的最后一个子元素======lastElementChild
>- 查找上一个兄弟元素节点=====previousElementSibling
>- 查找下一个兄弟元素节点========nextElementSibling
```css
*{
    margin:0;
    padding:0;
}

```
```js
//小李子

```
>- 查找某个元素的父级节点======parentNode
>-  

## 

# 手写一个children
## 增删改
- 创建元素
>```js
   >  //基本操作
   > ul.innerHTML+="<li>+i+</li>"
   >//性能优化
   >let html='';
   >for(var i=0;i<500;i++){
   >html='<li>'+i+'</li>'
   >}
   >ul.innerHTML=html;
>```
   >- document.createElement('标签名')
   >- 让元素的末尾添加一个元素:
        >- parent.appendChild(child)
- 删除元素
 - >parent.removeChild(删除的元素)
- 改元素
  - >parent.replaceChild